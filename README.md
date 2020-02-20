# HowTo

## WiFI ADB

1. Подключаем девайс по USB
2. Открываем терминал в папке с adb по пути ПУТЬ_ДО_SDK/sdk/platform-tools
3. Убеждаемся что девайс и комп в одной Wi-Fi сети.
4. adb forward tcp:5555 tcp:5555
5. Набираем adb tcpip 5555
6. Набираем adb connect IP_ДЕВАЙСА
Далее, в 95% случаев достаточно выполнить лишь п6.

## Add ADB to PATH
echo 'export ANDROID_HOME=/Users/$USER/Library/Android/sdk' >> ~/.bash_profile
echo 'export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools' >> ~/.bash_profile
source ~/.bash_profile
