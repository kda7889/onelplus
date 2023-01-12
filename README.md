# onelplus.ru
оформлен через 1Gb.ru<br/>
домен делегирован на:<br/>
ns1.timeweb.ru <br/>
ns2.timeweb.ru <br/>
ns3.timeweb.org <br/>
ns4.timeweb.org <br/>

# mail.onelplus.ru
-> 85.193.95.31 (TimeWeb Cloud - Польша)
Ubuntu 18.04 LTS
сразу после установки прописываем hostname = mail.onelplus.ru
>nano /etc/hostname

установлена Vestacp

  1) Скачивайте последнюю версию VestaCP на виртуальный сервер:
  >wget http://vestacp.com/pub/vst-install.sh
  2) Запускайте скрипт установки:
  >bash vst-install.sh --force
  3) Нужно подтвердить согласие на установку, вводите заглавную “Y” и жмите Enter, затем
  ввести электронную почту и задать Hostname, вы можете указать ip-адрес виртуального сервера, если нет доменного имени.
  4) В конце установки вы увидите адрес для входа, логин и пароль.


https://85.193.95.31:1525<br/>
username: admin<br/>
password: yCvxmgbSLo<br/>


Стираем из Vestacp домены в разделе Web, DNS.<br/>
Добавляем в раздел почта mail.onelplus.ru<br/>
Затем в консоли пишем:<br/>
> v-list-mail-domain-dkim admin onelplus.ru
<br/>
-----BEGIN RSA PRIVATE KEY-----<br/>
MIICXAIBAAKBgQDpWrATLGIEPl8asZdVHjRVAuFoGtymwzAZscrOaldl2kPNNlg0
PPiqgdidv7K9UQM9Xa8vr/c4mNwKdRqjAYCLqFdy7bKqoUqtBYzxQVccEHB6yh3m
fNNrJlMdrpzYWWgthdXnA+2jEfx6jv5ZWP1sEiXl3kw2xdR8LzF4mx08UQIDAQAB
AoGATl6wp5/OQ1KXKiXehy2fsbVH8mijFjaTXu3BCNXaCFDnWHIZ6WFYuhrlnwUU
iFQ+3EssXL2iL5XWwIRXr8r/WkOioD4TFPD61BFTBpIK2vvXo6dXwxwLKxDyfHbH
k1R+ZrXXKVzENJDQZEnRDGZm8flx65N+2VeKzM+hdB5SbakCQQD97Lhf7/qYs6sq
NMVsnrjyJn2TLKXtfOWcyZHYDiqSwiHbnOVt2AzoitAhdl1txtyjzPNb9M6lU7Jv
86gszWVXAkEA60LtuOtuXSCRRCaltlLEIvsRBcXi4q7bvtYJ/0/qjyXzPKLbt2Cj
VvT3v7Npd3fgQzKHlG83qtdph55a4816lwJBAMS1p7eanxXAyi6uJusYosnki4+C
HSC3iuFFPhiUEOMURUpuZ0YLAyT6tHXXzlUGo1K5qSVpptRo3Gjh5zyd+Y0CQHwA
L+qK9QXS955TPH7oCwdhC+zeC6NthNeGW4idp8VBvH4WXPa/0fgwcDEzsIBOx/7D
MGEVaeL7XV0lI0T09gsCQEC3qqGDSBvXBsmgNgpw/Kq5Di86a9lAI0IwqhaeSdz1
A+m2yxqR7lQuJ1zAWW723sMWYM7enQ9UV0sCM1SXYMA=
<br/>-----END RSA PRIVATE KEY-----
<br/>
-----BEGIN PUBLIC KEY-----<br/>
MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDpWrATLGIEPl8asZdVHjRVAuFo
GtymwzAZscrOaldl2kPNNlg0PPiqgdidv7K9UQM9Xa8vr/c4mNwKdRqjAYCLqFdy
7bKqoUqtBYzxQVccEHB6yh3mfNNrJlMdrpzYWWgthdXnA+2jEfx6jv5ZWP1sEiXl
3kw2xdR8LzF4mx08UQIDAQAB
<br/>-----END PUBLIC KEY-----
<br/>

## DMS записи
<br/>
добавляем в админке домена на хостинге

### для onelplus.ru

A

onelplus.ru

77.66.179.220



TXT

_dmarc

v=DMARC1; p=none; aspf=r; sp=none



TXT

mail._domainkey

v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDpWrATLGIEPl8asZdVHjRVAuFoGtymwzAZscrOaldl2kPNNlg0PPiqgdidv7K9UQM9Xa8vr/c4mNwKdRqjAYCLqFdy7bKqoUqtBYzxQVccEHB6yh3mfNNrJlMdrpzYWWgthdXnA+2jEfx6jv5ZWP1sEiXl3kw2xdR8LzF4mx08UQIDAQAB



TXT

onelplus.ru

v=spf1 ip4:85.193.95.31 a mx ~all



MX

onelplus.ru

mail.onelplus.ru

### для mail.onelplus.ru
A

mail.onelplus.ru

85.193.95.31

# создание пользователей

проверяем в консоли сервера что есть связь с почтовыми сервисами
>telnet smtp.gmail.com 25

если все ок, то создаем в Vestacp пользователей почты и тестируем<br/>
если нет, то просим провайдера открыть порты<br/>

# добавление в gmail

добавляем в действующий gmail аккаунт почту на нашем домене <br/>
>SMTP mail.onelplus.ru Защищенное соединение через порт 587
>POP mail.onelplus.ru Соединение через порт 110
