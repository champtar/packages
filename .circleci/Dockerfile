FROM debian:9

RUN apt update && apt install -y \
build-essential \
jq \
gawk \
gettext \
git \
libncurses5-dev \
libssl-dev \
subversion \
zlib1g-dev \
&& rm -rf /var/lib/apt/lists/*

# LEDE Build System (LEDE GnuPG key for unattended build jobs)
RUN curl 'https://git.openwrt.org/?p=keyring.git;a=blob_plain;f=gpg/626471F1.asc' | gpg --import \
 && echo '54CC74307A2C6DC9CE618269CD84BCED626471F1:6:' | gpg --import-ownertrust

# LEDE Release Builder (17.01 "Reboot" Signing Key)
RUN curl 'https://git.openwrt.org/?p=keyring.git;a=blob_plain;f=gpg/D52BBB6B.asc' | gpg --import \
 && echo 'B09BE781AE8A0CD4702FDCD3833C6010D52BBB6B:6:' | gpg --import-ownertrust
