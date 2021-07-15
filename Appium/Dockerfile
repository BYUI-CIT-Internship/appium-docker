FROM ubuntu:latest
MAINTAINER Ruben Gonzalez Alonso <rgonalo@gmail.com>

#===================================================================
# Miscellaneous packages
# Includes minimal runtime used for executing non GUI Java programs
#===================================================================
RUN apt update 
RUN apt install -y wget
RUN apt install -y openjdk-11-jdk
RUN apt install -y android-sdk
#=============
# Android SDK
#=============
ENV ANDROID_SDK_VERSION 11
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools


#===================
# Nodejs and Appium
#===================
ENV APPIUM_VERSION 1.21.0
RUN apt update
RUN apt install -y curl
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt install -y nodejs
RUN npm install -g appium@$APPIUM_VERSION --chromedriver-skip-install


# Appium server port
EXPOSE 4723

CMD appium
