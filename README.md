<h3 align="center">
   List of most used commands for: Linux, Git and others sistems and programs
</h3>

<p align="center">
  <a href="#star-linux">
    Linux
  </a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#star-git">
    Git
  </a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#star-docker">
    Docker
  </a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#star-react-native">
    React-Native
  </a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
</p>

***


### :pushpin: List of most used commands
This file is used to help me and others to remember some useful commands.



## :star: Linux
<p style='color:#c1c1c1'>
  In this section you'll find most used linux commands to help you in your daily tasks
</p>

List all **LISTEN PORTS**:
```
netstat -tulpn | grep LISTEN
```

Look for a **SPECIFIC PORT**
```
sudo lsof -i:22
```

## :star: Git
<p style='color:#c1c1c1'>
  In this section you'll find most used git commands to help you in your daily tasks
</p>


## :star: Docker
<p style='color:#c1c1c1'>
  In this section you'll find most used docker commands to help you in your daily tasks
</p>

## :star: React-Native
<p style='color:#c1c1c1'>
  Troubleshooting for react-native instalation
</p>

Install all needed packeges:
  ```
  sudo npm install -g react-native-
  sudo add-apt-repository ppa:openjdk-r/ppa
  sudo apt-get update
  sudo apt-get install openjdk-8-jdk
  sudo apt-get install gcc-multilib lib32z1 lib32stdc++6 
  ```

  Verify java instalation:
  ```
  java -version
  ```

  Download android [SDK][sdk] commandline version for ubuntu

  Configure ubuntu path (~/.profile, ~/.zshrc ou ~/.bashrc):
  ```
  export ANDROID_HOME=~/Android/Sdk
  export PATH=$PATH:$ANDROID_HOME/tools
  export PATH=$PATH:$ANDROID_HOME/platform-tools
  ```

  Install sdk packages forcing path
  ```
  yes | ~/Android/Sdk/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME} --licenses
  yes | ~/Android/Sdk/tools/bin/sdkmanager --sdk_root=${ANDROID_HOME} "platform-tools" "platforms;android-27" "build-tools;27.0.3"
  ```

  Install apk through wifi (cell phone must be connect on usb for this step)
  ```
  adb tcpip 5555
  adb -s 34e4569 tcpip 5555
  adb connect 192.168.0.3:5555
  ```
  
  Start react-native application:
  ```
  yarn start --port 8050
  ```

  Now it's possible to install apk using wifi
  ```
  ~/Android/Sdk/platform-tools/adb -s 192.168.0.3:5555 reverse tcp:8050 tcp:8050
  cd android && adb -s 192.168.0.3:5555 install -r -d app/build/outputs/apk/debug/app-debug.apk 
  ```
  <p>
    1 line: Set ADB tcp port to device 192.168.0.3:5555
  </p>
  <p>
    2 line: Install APK into Android mobile.
  </p>
  <br />

  <b>Steps to restart application</b>

  Start react-native application:
  ```
  yarn start --port 8050
  ```

  Afeter that, you can simple use the command:
  ```
  react-native run-android --deviceId=192.168.0.3:5555 --verbose
  ```
  to start app



###### Thanks to rxaviers for the list of icons, you can find in this [link][icons-url]

<!-- Markdown link & img dfn's -->
[icons-url]: https://gist.github.com/rxaviers/7360908
[sdk]: https://developer.android.com/studio/#downloads