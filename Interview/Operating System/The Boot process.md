# The Boot Process

* The booting process is automated seuence that starts a computer, intialize hardwate and loading the operating system from storage into memory.

1. The POST(Power-On Self-Test)
   * The BIOS or UEFI(Stored in ROM) runs a quick diagnosic.
     * It checks if the RAM is functional.
     * It defines CPU speed and temperature.
     * If something is wrong it sends "Beep Codes"
     * Prepare system for bootloader execution.
     <div align="center"><img width="556" height="497" alt="image" src="https://github.com/user-attachments/assets/119c6a1d-db13-40dd-8884-8cf8a1deac36" />
     <img width="1334" height="426" alt="image" src="https://github.com/user-attachments/assets/ea9bbf77-6ef2-4cf5-8afc-a87201d91c40" /></div>
     * If the hardware is functional the BIOS/UEFI firmware intializes the system bus and begins searching for a "Bootable Device."

2. The Master Boor Record(MBR) or GUID Partition table(GPT)
   * Once bootable devices, the BIOS looks at the first sector of the bootable disk(the MBR).
     * MBR: MBR is tiny 512-byte sector contains Primary Boot Loader. Because it is so small, its only job is to know exactly where the real boot lader resides on the disk.
     * GPT: in modern URFI system, this process is more robust and involves reading partition information to locate the OS boot manager.
    
4. The Boot loader
   * The primary Boot loader hands off control to a more sphisticated program(Like GRUB) after this firmware job is finished.
   * The bootloader loads OS kernel.


Firmware(BIOS/UEFI) ---> POST --> MBR/GPT --> Bootloader --> OS kernel loads


## Secure and Leagcy boot

* secure boot is feature of UEFI firmware, UEFI can load the bootloader without verfiying and by verifying it, if loads without cheking anything like old BIOS firmware then it is called leagcy boot, if UEFI  cheks for digital signature of bootloader then it is secure boot.
