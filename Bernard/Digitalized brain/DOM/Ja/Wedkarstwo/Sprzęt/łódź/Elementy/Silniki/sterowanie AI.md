Oto, jak połączyć moduł IBT-2 z ESP32 oraz przypisania pinów dla sterowania dwoma silnikami szczotkowymi:

### Przypisanie Pinów IBT-2 do ESP32

Na module IBT-2 znajdziesz następujące piny:

- **RPWM** (sterowanie prędkością silnika w jednym kierunku)
- **LPWM** (sterowanie prędkością silnika w przeciwnym kierunku)
- **R_EN** (włączanie/wyłączanie kierunku RPWM)
- **L_EN** (włączanie/wyłączanie kierunku LPWM)
- **R_IS** i **L_IS** (sygnały diagnostyczne, które informują o stanie prądu; często nie są używane do podstawowego sterowania).

### Schemat Podłączenia

Zakładając, że chcesz sterować dwoma silnikami, przy czym każdy z nich ma swój osobny moduł IBT-2, poniżej przedstawiam przypisanie pinów dla ESP32:

1. **Silnik 1**:
    
    - `RPWM` do GPIO 18 na ESP32 (sterowanie prędkością w jednym kierunku)
    - `LPWM` do GPIO 19 na ESP32 (sterowanie prędkością w przeciwnym kierunku)
    - `R_EN` i `L_EN` mogą być podłączone do GND, aby nie były sterowane dodatkowo (można sterować samymi pinami RPWM/LPWM).
2. **Silnik 2**:
    
    - `RPWM` do GPIO 21 na ESP32 (sterowanie prędkością w jednym kierunku)
    - `LPWM` do GPIO 22 na ESP32 (sterowanie prędkością w przeciwnym kierunku)
    - `R_EN` i `L_EN` mogą być podłączone do GND, podobnie jak w przypadku pierwszego silnika.

### Zaktualizowany Kod dla ESP32

Zaktualizuję kod, aby dopasować go do nowego przypisania pinów. Teraz `RPWM` i `LPWM` będą odpowiedzialne za sterowanie kierunkiem i prędkością, zamiast jednego pinu `DIR`.
W tym kodzie:

- `RPWM` i `LPWM` odpowiadają za ruch do przodu i do tyłu odpowiednio dla każdego z silników.
- `controlMotor` przyjmuje argument `forward`, który decyduje, czy dany silnik ma obracać się w przód czy w tył, ustawiając odpowiedni kanał PWM na ESP32.

// Definicje pinów dla silników
#define MOTOR1_RPWM 18
#define MOTOR1_LPWM 19
#define MOTOR2_RPWM 21
#define MOTOR2_LPWM 22

// Ustawienia PWM
const int pwmFreq = 1000;       // Częstotliwość PWM
const int pwmResolution = 8;    // Rozdzielczość PWM (8 bitów: 0-255)
const int pwmChannel1_RPWM = 0; // Kanał PWM dla MOTOR1_RPWM
const int pwmChannel1_LPWM = 1; // Kanał PWM dla MOTOR1_LPWM
const int pwmChannel2_RPWM = 2; // Kanał PWM dla MOTOR2_RPWM
const int pwmChannel2_LPWM = 3; // Kanał PWM dla MOTOR2_LPWM

void setup() {
  // Inicjalizacja PWM
  ledcSetup(pwmChannel1_RPWM, pwmFreq, pwmResolution);
  ledcSetup(pwmChannel1_LPWM, pwmFreq, pwmResolution);
  ledcSetup(pwmChannel2_RPWM, pwmFreq, pwmResolution);
  ledcSetup(pwmChannel2_LPWM, pwmFreq, pwmResolution);
  
  // Przypisanie kanałów PWM do pinów
  ledcAttachPin(MOTOR1_RPWM, pwmChannel1_RPWM);
  ledcAttachPin(MOTOR1_LPWM, pwmChannel1_LPWM);
  ledcAttachPin(MOTOR2_RPWM, pwmChannel2_RPWM);
  ledcAttachPin(MOTOR2_LPWM, pwmChannel2_LPWM);
}

// Funkcja do ustawienia prędkości i kierunku silnika
void controlMotor(int motor, int speed, bool forward) {
  int rpwmChannel, lpwmChannel;

  // Wybór silnika
  if (motor == 1) {
    rpwmChannel = pwmChannel1_RPWM;
    lpwmChannel = pwmChannel1_LPWM;
  } else {
    rpwmChannel = pwmChannel2_RPWM;
    lpwmChannel = pwmChannel2_LPWM;
  }

  if (forward) {
    ledcWrite(rpwmChannel, abs(speed)); // Prędkość do przodu
    ledcWrite(lpwmChannel, 0);          // LPWM wyłączone
  } else {
    ledcWrite(rpwmChannel, 0);          // RPWM wyłączone
    ledcWrite(lpwmChannel, abs(speed)); // Prędkość do tyłu
  }
}

// Funkcje do sterowania katamaranem
void moveForward(int speed) {
  controlMotor(1, speed, true);
  controlMotor(2, speed, true);
}

void moveBackward(int speed) {
  controlMotor(1, speed, false);
  controlMotor(2, speed, false);
}

void turnRight(int speed) {
  controlMotor(1, speed, true); // Silnik 1 do przodu
  controlMotor(2, speed / 2, false); // Silnik 2 do tyłu (mniejsza prędkość dla łagodnego skrętu)
}

void turnLeft(int speed) {
  controlMotor(1, speed / 2, false); // Silnik 1 do tyłu (mniejsza prędkość dla łagodnego skrętu)
  controlMotor(2, speed, true); // Silnik 2 do przodu
}

void stopMotors() {
  controlMotor(1, 0, true);
  controlMotor(2, 0, true);
}

void loop() {
  moveForward(200);  // Do przodu
  delay(2000);

  turnRight(150);    // Skręt w prawo
  delay(1500);

  moveBackward(180); // Do tyłu
  delay(2000);

  turnLeft(150);     // Skręt w lewo
  delay(1500);

  stopMotors();      // Zatrzymanie
  delay(2000);
}
