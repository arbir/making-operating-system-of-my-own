# LabOS
*** needed tool ***
nasm: apt-get install nasm
gcc: apt-get install gcc or g++
binutils: apt-get install binutils
make: apt-get install make

*** make command ***
make loader.o
make kernel.o
make mykernel.bin

After creating mykernel.bin :

now you can create an image using grub-mkrescue:
create a directory: iso
in that directory, create another directory: boot then in the boot directory, create a directory: grub and then create a file: grub.cfg with these contents(do not add the braces in a new line) in the grub directory:

*** grub.cfg ***

menuentry "myOS" {
multiboot /boot/kern
}

then copy your kernel (mykernel.bin) to iso/boot directory and run your shell again:
switch to the main directory of your kernel and type:

*** making kern.iso ***
*** need to install : apt-get install xorriso *** 

grub-mkrescue iso --output=kern.iso

now you can boot and enjoy from your first operating system:: this simple kernel without anything
