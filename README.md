# Realtek RTL8811CU/RTL8821CU for SS524
[![](https://img.shields.io/badge/powered_by-dsh-4D6BFE?style=flat-square&logo=deepseek&logoColor=white)](https://github.com/deepseek-ai/deepseek-harness)

个人需求，因为在用的视频编程器用不了MT7921CU，手头还刚好只有个RT8821CU还刚好兼容4.19内核，专门编译了一份
原代码正常用SDK编译会因为ABI问题，不是无法加载就是一插网卡就panic，所以用了dsh+Deepseek-V4.1-Flash+GLM-5.3来修

安装需自行去从别的仓库找SSH密码传到编码器里，最好删了原来的网卡驱动，不然有可能会cannot allocate memory
仅保证自用，不考虑后续维护，出问题自行让AI改
避免纠纷不提供SDK

有SDK的编译命令
make ARCH=arm \
     CROSS_COMPILE={SDKDIR}/toolchains/arm-himix410-linux/bin/arm-himix410-linux- \
     KSRC={SDKDIR}/kbuild-4.19.90/linux-4.19.90 \
     -j$(nproc) HOSTCFLAGS=-fcommon modules

