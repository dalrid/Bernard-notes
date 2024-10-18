ssh - Openssh
 -i oci-sandboox.key   -klucz
  opc@130.61.229.162  to jest info do którego serwera będzie tunel
 -L 127.0.0.1:6443:    -lokalny komputer
10.1.1.51:6443 - adres w sieci oci przez opc@130.61.229.162




ssh -i key/key  opc@130.61.229.162 -L 127.0.0.1:8090:10.0.3.229:8090