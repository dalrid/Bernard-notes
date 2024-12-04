
![[Pasted image 20241018230157.png]]

host -> smtp.email.eu-frankfurt-1.oci.oraclecloud.com  
port -> 587 (może być też 25)

jeszcze user/passwd wchodzisz w profil swojego usera i:

![[Pasted image 20241018230236.png]]

SMTP Credentials wygeneruje user i passwd w tym approved senders trzeba uważać na to, żeby nie dawać FROM jakiegoś usera fikcyjnego ale z asseco.pl bo na nasz serwer asseco blokował wtedy najlepiej z jakiejś fikcyjnego adresu > **Aleksander Zawada**
> 
> najlepiej z jakiejś fikcyjnego adresu

albo z rzecywistego istniejącego


 <transportSender name="mailto" class="org.apache.axis2.transport.mail.MailTransportSender">
        <parameter name="mail.smtp.host">smtp.email.eu-frankfurt-1.oci.oraclecloud.com</parameter>
        <parameter name="mail.smtp.port">587</parameter>
        <parameter name="mail.smtp.starttls.enable">true</parameter>
        <parameter name="mail.smtp.auth">true</parameter>
        <parameter name="mail.smtp.user">ocid1.user.oc1..aaaaaaaa32txghenx54vzcb7brrguvgkh2emphsrqttug2gyfydfcr5n4tdq@ocid1.tenancy.oc1..aaaaaaaa6pfndasupjsj2peja3nj3jgyuli64hyz37qlmzm3wculwnbuheva.ba.com</parameter>
        <parameter name="mail.smtp.password">k2.l!ehuAKmM0R!vI1p7</parameter>
        <parameter name="mail.smtp.from">sandbox@asseco.pl</parameter>
    </transportSender>
