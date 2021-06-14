FROM conanio/gcc11:1.37.1
RUN sudo apt-get update \
    && sudo apt-get install -y \
    ssh=1:8.2p1-4ubuntu0.2 \
    clang-format=1:10.0-50~exp1 \
    curl=7.68.0-1ubuntu2.5 \
    jq=1.6-1ubuntu0.20.04.1 \
    unzip=6.0-25ubuntu1 \
    wget=1.20.3-1ubuntu1 \
    gdb=10.2-0ubuntu1~20.04~1 \
    clangd=1:10.0-50~exp1 \
    locales=2.31-0ubuntu9.2 \
    clang-tidy-11=1:11.0.0-2~ubuntu20.04.1 \
    cppcheck=1.90-4build1

RUN echo "en_US.UTF-8 UTF-8" | sudo tee -a /etc/locale.gen \
    && sudo /sbin/locale-gen

RUN conan profile new default --detect
