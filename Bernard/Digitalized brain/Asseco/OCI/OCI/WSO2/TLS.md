 <transportSender name="mailto" class="org.apache.axis2.transport.mail.MailTransportSender">
        <parameter name="mail.smtp.host">smtp.email.eu-frankfurt-1.oci.oraclecloud.com</parameter>
        <parameter name="mail.smtp.port">587</parameter>
        <parameter name="mail.smtp.starttls.enable">true</parameter>
        <parameter name="mail.smtp.auth">true</parameter>
        <parameter name="mail.smtp.user">ocid1.user.oc1..aaaaaaaa32txghenx54vzcb7brrguvgkh2emphsrqttug2gyfydfcr5n4tdq@ocid1.tenancy.oc1..aaaaaaaa6pfndasupjsj2peja3nj3jgyuli64hyz37qlmzm3wculwnbuheva.ba.com</parameter>
        <parameter name="mail.smtp.password">k2.l!ehuAKmM0R!vI1p7</parameter>
        <parameter name="mail.smtp.from">sandbox@asseco.pl</parameter>
    </transportSender>







openssl s_client -showcerts -connect <mail-server-hostname>:<port> -starttls smtp
keytool -import -alias <alias-name> -file <cert-name> -keystore client-truststore.jks -storepass wso2carbon
/usr/lib64/wso2/wso2am/2.6.0/repository/resources/security
keytool -import -alias smtp_oci -file smtp.email.eu-frankfurt-1.oci.oraclecloud.com.pem -keystore client-truststore.jks -storepass wso2carbon

-----BEGIN CERTIFICATE-----
MIIHWTCCBkGgAwIBAgIQBWW7n4N+VGxG35zenUVLhzANBgkqhkiG9w0BAQsFADBZ
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMTMwMQYDVQQDEypE
aWdpQ2VydCBHbG9iYWwgRzIgVExTIFJTQSBTSEEyNTYgMjAyMCBDQTEwHhcNMjMx
MTE3MDAwMDAwWhcNMjQxMTIwMjM1OTU5WjCBjjELMAkGA1UEBhMCVVMxEzARBgNV
BAgTCkNhbGlmb3JuaWExFTATBgNVBAcTDFJlZHdvb2QgQ2l0eTEbMBkGA1UEChMS
T3JhY2xlIENvcnBvcmF0aW9uMTYwNAYDVQQDEy1zbXRwLmVtYWlsLmV1LWZyYW5r
ZnVydC0xLm9jaS5vcmFjbGVjbG91ZC5jb20wggEiMA0GCSqGSIb3DQEBAQUAA4IB
DwAwggEKAoIBAQDHL+JtdWcsYOd6nt813aqXydKJN8vcUipqeyz7Ux+hLF4086al
f6Ozv2WgzpvAUYII67FrHMmfrRUTyb1RR6o7i6SanN2PK7uHkFtTjuPiaTnCeJRs
ytLqLYHMreV2fWUs5tipXL4TFkq9+vpRCV2ORykm2PY3XnZ9dGTh5sBL6YeI/9p6
wdj2sLyfFcLdOvZwFh3JmYHTGG2aIwWy5nrvDz7XjUdhooreq5c1stI0ZErAUvxZ
uEqud54WimFIGpEjjuXoni0HPOVjzvYhLswEc+v08F9keHa3kB+by+Tk+21Gfvxw
h10mQFTRIV3pn7ouBBz80uPKLD3X3eA7v4mJAgMBAAGjggPlMIID4TAfBgNVHSME
GDAWgBR0hYDAZsffN97PvSk3qgMdvu3NFzAdBgNVHQ4EFgQUCuK6w6vN8+JsTtLj
02GYxBKUD1wwcQYDVR0RBGowaIItc210cC5lbWFpbC5ldS1mcmFua2Z1cnQtMS5v
Y2kub3JhY2xlY2xvdWQuY29tgjcqLnNtdHAtcHJpdmF0ZS5lbWFpbC5ldS1mcmFu
a2Z1cnQtMS5vY2kub3JhY2xlY2xvdWQuY29tMD4GA1UdIAQ3MDUwMwYGZ4EMAQIC
MCkwJwYIKwYBBQUHAgEWG2h0dHA6Ly93d3cuZGlnaWNlcnQuY29tL0NQUzAOBgNV
HQ8BAf8EBAMCBaAwHQYDVR0lBBYwFAYIKwYBBQUHAwEGCCsGAQUFBwMCMIGfBgNV
HR8EgZcwgZQwSKBGoESGQmh0dHA6Ly9jcmwzLmRpZ2ljZXJ0LmNvbS9EaWdpQ2Vy
dEdsb2JhbEcyVExTUlNBU0hBMjU2MjAyMENBMS0xLmNybDBIoEagRIZCaHR0cDov
L2NybDQuZGlnaWNlcnQuY29tL0RpZ2lDZXJ0R2xvYmFsRzJUTFNSU0FTSEEyNTYy
MDIwQ0ExLTEuY3JsMIGHBggrBgEFBQcBAQR7MHkwJAYIKwYBBQUHMAGGGGh0dHA6
Ly9vY3NwLmRpZ2ljZXJ0LmNvbTBRBggrBgEFBQcwAoZFaHR0cDovL2NhY2VydHMu
ZGlnaWNlcnQuY29tL0RpZ2lDZXJ0R2xvYmFsRzJUTFNSU0FTSEEyNTYyMDIwQ0Ex
LTEuY3J0MAwGA1UdEwEB/wQCMAAwggGBBgorBgEEAdZ5AgQCBIIBcQSCAW0BawB3
AO7N0GTV2xrOxVy3nbTNE6Iyh0Z8vOzew1FIWUZxH7WbAAABi9qUcSkAAAQDAEgw
RgIhAIDXNT7GUgGqw/B4DvckU3DlYvXMxJghEjcelEIpYnI7AiEAiJjDA/ChKAoI
bL/M0TZFe/nX7nzIob1aC7R4YL98bqYAdwBIsONr2qZHNA/lagL6nTDrHFIBy1bd
LIHZu7+rOdiEcwAAAYvalHDqAAAEAwBIMEYCIQDtFx1BvQF/Tm0ZOgVDKQHSQG9h
z02ktThgATCJH7Kq8QIhAKUPyq0K9l6aNv5/556U78rhGyvH7AbzZzc+TI+haCKt
AHcA2ra/az+1tiKfm8K7XGvocJFxbLtRhIU0vaQ9MEjX+6sAAAGL2pRw0QAABAMA
SDBGAiEAyacOf+PrL7PCIfyx4Z2xnckYCqUY8dGV+avG+W2WHSgCIQCIbWOvmMzB
6o40T9Dl7G9+pAJdiQx0qJgB22zqSHjbDzANBgkqhkiG9w0BAQsFAAOCAQEANg5W
ge5qaWCrLh5KLqIdTeb6tVbYmdKAZSn79BjSXFbAy9mvoUUhrnxLsQzI1/6vW66W
q1HAT4fhyb+6V1NIMtsHHQrlEX0m0DrUfqw1Q6hG3uBhnov5kNkW2D+SsKynM89S
DPJpkfBmlBVYAwZZTlASnGARVas/hUWUgYpq56U7H7ggX4wDIhxxqY5ZE+f547T8
DaaFIu48P8SKGM09p+9r4ZiGmOHKKTILPmLJD8JpVAvqaqFASHmLd5KVAzzOXS1v
M2yHP8aGXoenEWmw7kUPMWK1OseB3WUGISFEl1ZxtnNxp5S+tDGDBhGiiionwer4
fy6Zv5YxcQ3vy3xr9w==
-----END CERTIFICATE-----



-----BEGIN CERTIFICATE-----
MIIEyDCCA7CgAwIBAgIQDPW9BitWAvR6uFAsI8zwZjANBgkqhkiG9w0BAQsFADBh
MQswCQYDVQQGEwJVUzEVMBMGA1UEChMMRGlnaUNlcnQgSW5jMRkwFwYDVQQLExB3
d3cuZGlnaWNlcnQuY29tMSAwHgYDVQQDExdEaWdpQ2VydCBHbG9iYWwgUm9vdCBH
MjAeFw0yMTAzMzAwMDAwMDBaFw0zMTAzMjkyMzU5NTlaMFkxCzAJBgNVBAYTAlVT
MRUwEwYDVQQKEwxEaWdpQ2VydCBJbmMxMzAxBgNVBAMTKkRpZ2lDZXJ0IEdsb2Jh
bCBHMiBUTFMgUlNBIFNIQTI1NiAyMDIwIENBMTCCASIwDQYJKoZIhvcNAQEBBQAD
ggEPADCCAQoCggEBAMz3EGJPprtjb+2QUlbFbSd7ehJWivH0+dbn4Y+9lavyYEEV
cNsSAPonCrVXOFt9slGTcZUOakGUWzUb+nv6u8W+JDD+Vu/E832X4xT1FE3LpxDy
FuqrIvAxIhFhaZAmunjZlx/jfWardUSVc8is/+9dCopZQ+GssjoP80j812s3wWPc
3kbW20X+fSP9kOhRBx5Ro1/tSUZUfyyIxfQTnJcVPAPooTncaQwywa8WV0yUR0J8
osicfebUTVSvQpmowQTCd5zWSOTOEeAqgJnwQ3DPP3Zr0UxJqyRewg2C/Uaoq2yT
zGJSQnWS+Jr6Xl6ysGHlHx+5fwmY6D36g39HaaECAwEAAaOCAYIwggF+MBIGA1Ud
EwEB/wQIMAYBAf8CAQAwHQYDVR0OBBYEFHSFgMBmx9833s+9KTeqAx2+7c0XMB8G
A1UdIwQYMBaAFE4iVCAYlebjbuYP+vq5Eu0GF485MA4GA1UdDwEB/wQEAwIBhjAd
BgNVHSUEFjAUBggrBgEFBQcDAQYIKwYBBQUHAwIwdgYIKwYBBQUHAQEEajBoMCQG
CCsGAQUFBzABhhhodHRwOi8vb2NzcC5kaWdpY2VydC5jb20wQAYIKwYBBQUHMAKG
NGh0dHA6Ly9jYWNlcnRzLmRpZ2ljZXJ0LmNvbS9EaWdpQ2VydEdsb2JhbFJvb3RH
Mi5jcnQwQgYDVR0fBDswOTA3oDWgM4YxaHR0cDovL2NybDMuZGlnaWNlcnQuY29t
L0RpZ2lDZXJ0R2xvYmFsUm9vdEcyLmNybDA9BgNVHSAENjA0MAsGCWCGSAGG/WwC
ATAHBgVngQwBATAIBgZngQwBAgEwCAYGZ4EMAQICMAgGBmeBDAECAzANBgkqhkiG
9w0BAQsFAAOCAQEAkPFwyyiXaZd8dP3A+iZ7U6utzWX9upwGnIrXWkOH7U1MVl+t
wcW1BSAuWdH/SvWgKtiwla3JLko716f2b4gp/DA/JIS7w7d7kwcsr4drdjPtAFVS
slme5LnQ89/nD/7d+MS5EHKBCQRfz5eeLjJ1js+aWNJXMX43AYGyZm0pGrFmCW3R
bpD0ufovARTFXFZkAdl9h6g4U5+LXUZtXMYnhIHUfoyMo5tS58aI7Dd8KvvwVVo4
chDYABPPTHPbqjc1qCmBaZx2vN4Ye5DUys/vZwP9BFohFrH/6j/f3IL16/RZkiMN
JCqVJUzKoZHm1Lesh3Sz8W2jmdv51b2EQJ8HmA==
-----END CERTIFICATE-----





cd /sandbox/wso2 && rm wso2.tar.gz && tar zcvf wso2.tar.gz wso2 && docker build -t wso2_image_20240928_am_bk_proddb-v4_smtp . && docker run -d --name wso2_image_20240928_am_bk_proddb-v4_smtp -p 9444:9443 -p 8090:8090 wso2_image_20240928_am_bk_proddb-v4_smtp



docker container stop wso2_image_20240928_am_bk_proddb-v4_smtp && docker container rm wso2_image_20240928_am_bk_proddb-v4_smtp && docker image rm wso2_image_20240928_am_bk_proddb-v4_smtp