FROM conanio/clang11:1.37.1
RUN sudo apt-get update \
    && sudo apt-get install -y \
    ssh=1:7.6p1-4ubuntu0.3 \
    clang-format=1:6.0-41~exp5~ubuntu1 \
    curl=7.58.0-2ubuntu3.13 \
    jq=1.5+dfsg-2 \
    unzip=6.0-21ubuntu1.1 \
    wget=1.19.4-1ubuntu2.2 \
    gdb=8.1.1-0ubuntu1 \
    locales=2.27-3ubuntu1.4 \
    clang-tidy-11=1:11.1.0~++20210428103915+1fdec59bffc1-1~exp1~20210428204556.164

RUN wget https://github.com/danmar/cppcheck/archive/refs/tags/1.90.zip -O cppcheck.zip \
    && unzip cppcheck.zip \
    && cd cppcheck-1.90 \
    && cmake . -DCMAKE_BUILD_TYPE=Release \
    && sudo /opt/pyenv/shims/cmake --build . --target install

RUN echo "en_US.UTF-8 UTF-8" | sudo tee -a /etc/locale.gen \
    && sudo locale-gen

RUN sudo ln /usr/bin/clangd-11 /usr/bin/clangd \
    && sudo ln /usr/bin/clang-tidy-11 /usr/bin/clang-tidy

RUN conan profile new default --detect