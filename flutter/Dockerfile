FROM openjdk:8

LABEL maintainer="Daniel Jun Suguimoto <danielsuguimoto@gmail.com>"

RUN apt update && apt install -y curl git unzip xz-utils zip libglu1-mesa wget

RUN mkdir -p Android/Sdk
ENV ANDROID_SDK_ROOT /Android/Sdk
RUN mkdir -p .android && touch .android/repositories.cfg

RUN wget -O sdk-tools.zip https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
RUN unzip sdk-tools.zip && rm sdk-tools.zip
RUN mv tools Android/Sdk/tools
RUN cd Android/Sdk/tools/bin && yes | ./sdkmanager --licenses
RUN cd Android/Sdk/tools/bin && ./sdkmanager "build-tools;29.0.2" "patcher;v4" "platform-tools" "platforms;android-29" "sources;android-29"

RUN git clone https://github.com/flutter/flutter.git
ENV PATH "$PATH:/flutter/bin"

RUN flutter precache

WORKDIR /app

ENTRYPOINT ["/flutter/bin/flutter"]
