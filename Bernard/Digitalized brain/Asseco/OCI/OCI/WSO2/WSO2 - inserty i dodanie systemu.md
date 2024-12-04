


/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/themes/wso2/templates/systems
asseco-voicebot/ initializer.jag  template.jag


/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/pages/systems/asseco-voicebot.jag

/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/blocks/systems/asseco-voicebot/block.jag



/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/conf/locales/jaggery/locale_pl.json



asseco-voicebot.1
asseco-cl.1

vi 

/site/blocks/systems/voicebot/block.jag 
/store/jagg/jagg.jag#647
/site/blocks/systems/voicebot/block.jag



INSERT INTO "PUBLIC"."SYSTEM_CREDENTIALS"("ID","SYSTEM_ID","ENVIRONMENT_ID","PROFILE_SYMBOL","PROFILE_DESCRIPTION","USERNAME","PASSWORD","GUI_LINK","OLD_GUI_LINK","API_LINK","CREATED_BY","CREATED_DATE")VALUES(?,?,?,?,?,?,?,?,?,?,?,?) 


	https://apo.banking.asseco.pl

INSERT INTO
SYSTEM_LINKS (SYSTEM_ID, ENVIRONMENT_ID, GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE)
VALUES
('asseco-cb',NULL,'https://developer.banking.asseco.pl:8443/application/gui','https://developer.banking.asseco.pl:8443/application/api','admin', NOW());



INSERT INTO SYSTEM_CREDENTIALS (SYSTEM_ID, ENVIRONMENT_ID, PROFILE_SYMBOL, PROFILE_DESCRIPTION, USERNAME, PASSWORD, GUI_LINK, OLD_GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE) VALUES ('asseco-po',1,'asseco-po','Asseco PO','test','test','https://apo.banking.asseco.pl',NULL,NULL,'admin',now());

INSERT INTO SYSTEM_CREDENTIALS (SYSTEM_ID, ENVIRONMENT_ID, PROFILE_SYMBOL, PROFILE_DESCRIPTION, USERNAME, PASSWORD, GUI_LINK, OLD_GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE) VALUES ('asseco-pwd',1,'asseco-pwd','Asseco PWD','test','test','https://apo.banking.asseco.pl',NULL,NULL,'admin',now());


INSERT INTO SYSTEM_LINKS (SYSTEM_ID, ENVIRONMENT_ID, GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE, OLD_GUI_LINK, PROFILE_SYMBOL) VALUES ('asseco-pwd',1,'https://apo.banking.asseco.pl',NULL,'admin',now(),NULL,NULL);

INSERT INTO SYSTEM_LINKS (SYSTEM_ID, ENVIRONMENT_ID, GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE, OLD_GUI_LINK, PROFILE_SYMBOL) VALUES ('asseco-po',1,'https://apo.banking.asseco.pl',NULL,'admin',now(),NULL,NULL);



INSERT INTO SYSTEM_CREDENTIALS (SYSTEM_ID, ENVIRONMENT_ID, PROFILE_SYMBOL, PROFILE_DESCRIPTION, USERNAME, PASSWORD, GUI_LINK, OLD_GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE) VALUES ('VOICEBOT',1,'VOICEBOT','VOICEBOT','test','test','https://vb.banking.asseco.pl',NULL,NULL,'admin',now());

INSERT INTO SYSTEM_LINKS (SYSTEM_ID, ENVIRONMENT_ID, GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE, OLD_GUI_LINK, PROFILE_SYMBOL) VALUES ('VOICEBOT',1,'https://vb.banking.asseco.pl',NULL,'admin',now(),NULL,NULL);


1. Template.jag - wskazanie na plik asseco-po (powinno być pwd)
2. odblokowane logowanie :
/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/themes/wso2/templates/systems/asseco-po


UPDATE SYSTEM_CREDENTIALS (SYSTEM_ID, ENVIRONMENT_ID, PROFILE_SYMBOL, PROFILE_DESCRIPTION, USERNAME, PASSWORD, GUI_LINK, OLD_GUI_LINK, API_LINK, CREATED_BY, CREATED_DATE) set ('asseco-po',1,'Default','[pl]Domyślny[/pl][en]Default[/en]','test','test','https://apo.banking.asseco.pl',NULL,NULL,'admin',now());



UPDATE SYSTEM_LINKS SET PROFILE_SYMBOL  = NULL where SYSTEM_ID='asseco-pwd';
UPDATE SYSTEM_LINKS SET PROFILE_DESCRIPTION  = '[pl]Administrator[/pl][en]Administrator[/en]' where SYSTEM_ID='asseco-pwd';
UPDATE SYSTEM_LINKS SET PROFILE_SYMBOL  = 'default' where SYSTEM_ID='asseco-pwd';
UPDATE SYSTEM_LINKS SET PROFILE_DESCRIPTION  = '[pl]Administrator[/pl][en]Administrator[/en]' where SYSTEM_ID='asseco-pwd';


UPDATE SYSTEM_CREDENTIALS  SET GUI_LINK  = 'https://ars1.banking.asseco.pl/ars/login.ac' where SYSTEM_ID='asseco-ars';


UPDATE SYSTEM_CREDENTIALS SET PROFILE_SYMBOL  = NULL where SYSTEM_ID='asseco-po';
UPDATE SYSTEM_CREDENTIALS SET PROFILE_DESCRIPTION  = '[pl]Administrator[/pl][en]Administrator[/en]' where SYSTEM_ID='asseco-po';
UPDATE SYSTEM_CREDENTIALS SET PROFILE_SYMBOL  = NULL where SYSTEM_ID='asseco-pwd';
UPDATE SYSTEM_CREDENTIALS SET PROFILE_DESCRIPTION  = '[pl]Administrator[/pl][en]Administrator[/en]' where SYSTEM_ID='asseco-pwd';



/usr/lib64/wso2/wso2am/2.6.0/repository/database-29-09.tar.gz
/usr/lib64/wso2/wso2am/2.6.0/repository/deployment/server/jaggeryapps/store/site/themes/wso2/templates/systems/template.jag


docker tag wso2_image_20240928_am_bk_proddb-v3 fra.ocir.io/frkvgr6rogi5/wso-2/wso2_image_20240928_am_bk_proddb-v3
docker login fra.ocir.io
docker push fra.ocir.io/frkvgr6rogi5/wso-2/wso2_image_20240928_am_bk_proddb-v3


UAT mount 10.0.3.224:/db-h2 /home/opc2/mnt

PROD !!!! - 

kubectl delete deployment wso2-uat
kubectl create -f wso2-UAT.yaml


INSERT INTO SYSTEM (SYMBOL, NAME, DESCRIPTION_PL, DESCRIPTION_EN) VALUES ('asseco-voicebot','asseco-voicebot','<b>Voicebot Asseco</B>', '<B>Asseco's Voicebot </B> ');


lb wso2 prod - 10.0.3.193
lb wso2 uat  - 10.0.3.229



/10.1.1.254:8080  cl2/store


INSERT INTO SYSTEM (SYMBOL, NAME, DESCRIPTION_PL, DESCRIPTION_EN) VALUES ('asseco-voicebot','asseco-voicebot','<b>Voicebot Asseco</B>to Twój nowy specjalista obsługi klienta.Voicebot przekształca wypowiedź klienta na tekst dzięki technologii speech-to-text. Tekst analizują algorytmy natural language understanding (NLU), rozpoznając intencję i kontekst wypowiedzi. Bot pozyskuje z tekstu istotne informacje dla zapytania, rozpoznając pytania, polecenia czy potrzeby.Na podstawie zebranych danych oraz intencji użytkownika voicebot generuje odpowiedzi głosowe lub tekstowe kontrolowane przez administratora Voicebot wspomagany AI prowadzi dialog i zadaje szczegółowe pytania oraz potrafi prowadzić bardziej złożone interakcje. O zachowaniu bota i dostosowaniu odpowiedzi do potrzeb klientów decyduje administrator, eliminując niepożądane akcje Ciągłe uczenie pod nadzorem i możliwośćdodania modułu LLM, który uczy się na przekazanych materiałach <BR> Bazy danych, systemy CRM i inne ystemy dostarczają botom głosowym bardziej szczegółowych informacji.', '<B>Asseco's Voicebot </B> is your new customer service specialist. The voicebot converts customer speech into text using speech-to-text technology. The text is analyzed by natural language understanding (NLU) algorithms, which identify the intent and context of the conversation. The bot extracts key information from the text, recognizing questions, commands, or needs. Based on the gathered data and the user's intent, the voicebot generates voice or text responses, controlled by an administrator. AI-assisted, the voicebot conducts dialogue, asks detailed questions, and can handle more complex interactions. The bot's behavior and response customization to customer needs are overseen by an administrator, eliminating unwanted actions. Continuous supervised learning and the option to add an LLM module allow the bot to learn from provided materials. <BR> Databases, CRM systems, and other systems provide the voicebot with more detailed information.');












