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
```
echo 'export ANDROID_HOME=/Users/$USER/Library/Android/sdk' >> ~/.bash_profile
echo 'export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools' >> ~/.bash_profile
source ~/.bash_profile
```

## Git

#### Нужны изменения из feature/TASK-1 для того, чтобы делать feature/TASK-2 и затем, когда feature/TASK-1 будет влита в develop, нужно перекинуть изменения feature/TASK-2 на develop. 
1. Создаем ветку feature/TASK-2 от ветки feature/TASK-1.
2. Ждем когда feature/TASK-1 будет вмержен в develop.
3. Выпонляем: 
```
git rebase --onto develop feature/TASK-1 feature/TASK-2
```
#### Добавляем все изменения в последний коммит
```
git add .
git commit --amend --no-edit
```

## Open deeplink
adb shell am start -a android.intent.action.VIEW -d "android-app://com.app/path/"
