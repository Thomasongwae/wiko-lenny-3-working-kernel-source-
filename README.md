# wiko-lenny-3-working-kernel-source-
i have fixed all the bugs including the vertical lines that were present on the screen after flashing it also i have fixed sim card detection by providing new firmware files

the kernel works on Wiko lenny 3,Walton Primo GH6 (by using v3702_defconfig ) and Symphony i10 (by using p4200_defconfig)

configure prebuilts/gcc $PATH

  export CROSS_COMPILE=/home/thomasongwae/kernel/toolchain/bin/arm-eabi-
  (the path where your toolchain is located)

export ARCH=arm
mkdir out
make O=out TARGET_ARCH=arm  v3702_defconfig(defconfig for wiko lenny3 and Walton Primo GH6 )


after doing all this you should close the terminal 
look in the kernel source code to see the dir "out" and open it
now open the terminal inside it and
 type the command "make nconfig" and make any changes to the kernel you are making 

after that save the .config

and type this command 

make -j4 -C $PWD O=$PWD/out ARCH=arm (you can change 4 to the number of jobs you want on your cpu) this starts the compilation 

also you can use this command "make O=out TARGET_ARCH=arm" but this one is slowler compared to the first one



