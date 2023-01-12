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
password: pJQusLaw4N<br/>


>root@85:~# v-list-mail-domain-dkim admin onelplus.ru



