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
# RUN cd /opt \
#   && wget --no-verbose http://dl.google.com/android/android-sdk_r$ANDROID_SDK_VERSION-linux.tgz -O android-sdk.tgz \
#   && tar xzf android-sdk.tgz \
#   && rm -f android-sdk.tgz \
#   && cd android-sdk-linux/tools \
#   && mv -f emulator64-arm emulator \
#   && rm -f emulator64* emulator-* \
#   && chmod +x android emulator

#=====================
# Android SDK Manager
#=====================
# ENV ANDROID_COMPONENTS platform-tools,build-tools-25.0.3
# RUN echo y | android update sdk --all --force --no-ui --filter ${ANDROID_COMPONENTS}

#===================
# Nodejs and Appium
#===================
ENV APPIUM_VERSION 1.21.0
RUN apt update
RUN apt install -y nodejs
RUN apt install -y npm
RUN npm install -g appium@$APPIUM_VERSION --chromedriver-skip-install

#============================================
# Add udev rules file with USB configuration
#============================================
#ENV UDEV_REMOTE_FILE https://raw.githubusercontent.com/M0Rf30/android-udev-rules/master/51-android.rules
#RUN mkdir /etc/udev/rules.d \
#  && wget --no-verbose $UDEV_REMOTE_FILE -O /etc/udev/rules.d/51-android.rules

# Appium server port
EXPOSE 4723

CMD appium
