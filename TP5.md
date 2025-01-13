# TP5 - Titre du TP

## 0. Prérequis

##### 🌞 Créer un répertoire de travail dans votre répertoire personnel

```powershell
micho@Deb:~$ pwd
/home/micho
micho@Deb:~$ mkdir work
micho@Deb:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  work
```

## Partie I : Compilation étou tavu

### I. Programme minimal

#### 1. Compilation

##### --> Créer fichier nommé hello1.c avec le contenu suivant :

```powershell
micho@Deb:~/work$ cat hello1.c
void _start() {
    const char message[] = "Hello, World!\n";
    asm volatile (
        "mov $4, %%eax\n\t"          // Syscall number for write (4 in 32-bit)
        "mov $1, %%ebx\n\t"          // File descriptor 1 (stdout)
        "mov %[msg], %%ecx\n\t"      // Pointer to the message
        "mov %[len], %%edx\n\t"      // Length of the message
        "int $0x80"                  // Make the syscall (32-bit interrupt)
        :
        : [msg] "r" (message), [len] "r" (14)
        : "eax", "ebx", "ecx", "edx"
    );

    asm volatile (
        "mov $1, %%eax\n\t"          // Syscall number for exit (1 in 32-bit)
        "xor %%ebx, %%ebx\n\t"       // Exit code 0
        "int $0x80"                  // Make the syscall
        :
        :
        : "eax", "ebx"
    );
}
```

#### 2. Analyse du programme compilé

##### 🌞 Retrouvez à l'aide de readelf l'architecture pour laquelle le programme est compilé

```powershell
micho@Deb:~/work$ readelf -h hello1
ELF Header:
  Magic:   7f 45 4c 46 01 01 01 00 00 00 00 00 00 00 00 00
  Class:                             ELF32
  Data:                              2's complement, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  ABI Version:                       0
  Type:                              DYN (Position-Independent Executable file)
  Machine:                           Intel 80386
  Version:                           0x1
  Entry point address:               0x1000
  Start of program headers:          52 (bytes into file)
  Start of section headers:          13304 (bytes into file)
  Flags:                             0x0
  Size of this header:               52 (bytes)
  Size of program headers:           32 (bytes)
  Number of program headers:         11
  Size of section headers:           40 (bytes)
  Number of section headers:         21
  Section header string table index: 20
```

##### 🌞 Afficher la liste des sections contenues dans le programme

```powershell
micho@Deb:~/work$ readelf -S hello1
There are 21 section headers, starting at offset 0x33f8:

Section Headers:
  [Nr] Name              Type            Addr     Off    Size   ES Flg Lk Inf Al
  [ 0]                   NULL            00000000 000000 000000 00      0   0  0
  [ 1] .interp           PROGBITS        00000194 000194 000013 00   A  0   0  1
  [ 2] .note.gnu.bu[...] NOTE            000001a8 0001a8 000024 00   A  0   0  4
  [ 3] .gnu.hash         GNU_HASH        000001cc 0001cc 000018 04   A  4   0  4
  [ 4] .dynsym           DYNSYM          000001e4 0001e4 000010 10   A  5   1  4
  [ 5] .dynstr           STRTAB          000001f4 0001f4 000001 00   A  0   0  1
  [ 6] .text             PROGBITS        00001000 001000 00005d 00  AX  0   0  1
  [ 7] .eh_frame_hdr     PROGBITS        00002000 002000 00001c 00   A  0   0  4
  [ 8] .eh_frame         PROGBITS        0000201c 00201c 000058 00   A  0   0  4
  [ 9] .dynamic          DYNAMIC         00003f8c 002f8c 000068 08  WA  5   0  4
  [10] .got.plt          PROGBITS        00003ff4 002ff4 00000c 04  WA  0   0  4
  [11] .comment          PROGBITS        00000000 003000 00001f 01  MS  0   0  1
  [12] .debug_aranges    PROGBITS        00000000 00301f 000020 00      0   0  1
  [13] .debug_info       PROGBITS        00000000 00303f 000070 00      0   0  1
  [14] .debug_abbrev     PROGBITS        00000000 0030af 000062 00      0   0  1
  [15] .debug_line       PROGBITS        00000000 003111 000054 00      0   0  1
  [16] .debug_str        PROGBITS        00000000 003165 000085 01  MS  0   0  1
  [17] .debug_line_str   PROGBITS        00000000 0031ea 00001a 01  MS  0   0  1
  [18] .symtab           SYMTAB          00000000 003204 0000b0 10     19   6  4
  [19] .strtab           STRTAB          00000000 0032b4 00006a 00      0   0  1
  [20] .shstrtab         STRTAB          00000000 00331e 0000d9 00      0   0  1
Key to Flags:
  W (write), A (alloc), X (execute), M (merge), S (strings), I (info),
  L (link order), O (extra OS processing required), G (group), T (TLS),
  C (compressed), x (unknown), o (OS specific), E (exclude),
  D (mbind), p (processor specific)
```

##### 🌞 Affichez le code assembleur de la section .text à l'aide d'objdump

```powershell
micho@Deb:~/work$ objdump -d hello1

hello1:     file format elf32-i386


Disassembly of section .text:

00001000 <_start>:
    1000:       55                      push   %ebp
    1001:       89 e5                   mov    %esp,%ebp
    1003:       57                      push   %edi
    1004:       56                      push   %esi
    1005:       53                      push   %ebx
    1006:       83 ec 10                sub    $0x10,%esp
    1009:       e8 4b 00 00 00          call   1059 <__x86.get_pc_thunk.ax>
    100e:       05 e6 2f 00 00          add    $0x2fe6,%eax
    1013:       c7 45 e5 48 65 6c 6c    movl   $0x6c6c6548,-0x1b(%ebp)
    101a:       c7 45 e9 6f 2c 20 57    movl   $0x57202c6f,-0x17(%ebp)
    1021:       c7 45 ed 6f 72 6c 64    movl   $0x646c726f,-0x13(%ebp)
    1028:       c7 45 f0 64 21 0a 00    movl   $0xa2164,-0x10(%ebp)
    102f:       8d 75 e5                lea    -0x1b(%ebp),%esi
    1032:       bf 0e 00 00 00          mov    $0xe,%edi
    1037:       b8 04 00 00 00          mov    $0x4,%eax
    103c:       bb 01 00 00 00          mov    $0x1,%ebx
    1041:       89 f1                   mov    %esi,%ecx
    1043:       89 fa                   mov    %edi,%edx
    1045:       cd 80                   int    $0x80
    1047:       b8 01 00 00 00          mov    $0x1,%eax
    104c:       31 db                   xor    %ebx,%ebx
    104e:       cd 80                   int    $0x80
    1050:       90                      nop
    1051:       83 c4 10                add    $0x10,%esp
    1054:       5b                      pop    %ebx
    1055:       5e                      pop    %esi
    1056:       5f                      pop    %edi
    1057:       5d                      pop    %ebp
    1058:       c3                      ret

00001059 <__x86.get_pc_thunk.ax>:
    1059:       8b 04 24                mov    (%esp),%eax
    105c:       c3                      ret
```

#### 2. Librairie et compilation dynamique

#### C. Tracer les appels à des librairies

##### 🌞 Tracez à l'aide de la commande ldd les librairies appelées par...

```powershell
micho@Deb:~/work$ ldd hello2
        linux-gate.so.1 (0xf7f8d000)
        libc.so.6 => /lib32/libc.so.6 (0xf7d49000)
        /lib/ld-linux.so.2 (0xf7f8f000)
micho@Deb:~/work$ ldd hello1
        statically linked
        micho@Deb:~/work$ ldd /bin/ls
        linux-vdso.so.1 (0x00007ffcd1fe5000)
        libselinux.so.1 => /lib/x86_64-linux-gnu/libselinux.so.1 (0x00007f2536fa8000)
        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f2536dc7000)
        libpcre2-8.so.0 => /lib/x86_64-linux-gnu/libpcre2-8.so.0 (0x00007f2536d2d000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f253700f000)
```

##### 🌞 Parmi les librairies appelées par hello2, déterminer le type du fichier nommé libc.so.X

```powershell
micho@Deb:~/work$ file /lib32/libc.so.6
/lib32/libc.so.6: ELF 32-bit LSB shared object, Intel 80386, version 1 (GNU/Linux), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b3f5646d25dc90cc34d2507f197561065c7e630c, for GNU/Linux 3.2.0, stripped
```

#### 3. Compilation statique

##### 🌞 Affichez le type des fichiers hello2 et hello3

```powershell
micho@Deb:~/work$ file hello2
hello2: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=1dc471fdd700342bf3e9736f46b6278786fcd1e7, for GNU/Linux 3.2.0, with debug_info, not stripped
micho@Deb:~/work$ file hello1
hello1: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=a710a3228b7570ebfa52a7e34b3ca434259080c1, with debug_info, not stripped
```

##### 🌞 Affichez leurs tailles

```powershell
micho@Deb:~/work$  du -h hello2 hello3
16K     hello2
728K    hello3
```

#### 4. Compilation cross-platform

##### 🌞 Affichez l'architecture de votre CPU

```powershell
micho@Deb:~/work$ cat /proc/cpuinfo
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 183
model name      : 13th Gen Intel(R) Core(TM) i9-13900HX
stepping        : 1
microcode       : 0xffffffff
cpu MHz         : 2419.198
cache size      : 36864 KB
physical id     : 0
siblings        : 1
core id         : 0
cpu cores       : 1
apicid          : 0
initial apicid  : 0
fpu             : yes
fpu_exception   : yes
cpuid level     : 22
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx rdtscp lm constant_tsc rep_good nopl xtopology nonstop_tsc cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 sse4_1 sse4_2 movbe popcnt aes rdrand hypervisor lahf_lm abm 3dnowprefetch ibrs_enhanced fsgsbase bmi1 bmi2 invpcid rdseed adx clflushopt sha_ni arat md_clear flush_l1d arch_capabilities
bugs            : spectre_v1 spectre_v2 spec_store_bypass swapgs retbleed eibrs_pbrsb rfds bhi
bogomips        : 4838.39
clflush size    : 64
cache_alignment : 64
address sizes   : 39 bits physical, 48 bits virtual
power management:
```

##### 🌞 Vérifiez que vous avez la commande x86-64-linux-gnu-gcc

```powershell
micho@Deb:~/work$ which x86_64-linux-gnu-gcc
/usr/bin/x86_64-linux-gnu-gcc
```

##### 🌞 Compilez votre fichier hello3.c dans un fichier cible nommé hello4 vers une autre architecture que la vôtre

```powershell
micho@Deb:~/work$ file hello4
hello4: ELF 32-bit LSB pie executable, ARM, EABI5 version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.3, BuildID[sha1]=4e45c657751a03c9a336e0a144633ddff8ac5bc9, for GNU/Linux 3.2.0, not stripped
```

##### 🌞 Désassemblez hello3 et hello4 à l'aide d'objdump

```powershell
micho@Deb:~/work$ objdump -d hello4

hello4:     file format elf32-littlearm


Disassembly of section .init:

000003a4 <_init>:
 3a4:   e92d4008        push    {r3, lr}
 3a8:   eb000025        bl      444 <call_weak_fn>
 3ac:   e8bd8008        pop     {r3, pc}

Disassembly of section .plt:

000003b0 <.plt>:
 3b0:   e52de004        push    {lr}            @ (str lr, [sp, #-4]!)
 3b4:   e59fe004        ldr     lr, [pc, #4]    @ 3c0 <.plt+0x10>
 3b8:   e08fe00e        add     lr, pc, lr
 3bc:   e5bef008        ldr     pc, [lr, #8]!
 3c0:   00001c40        .word   0x00001c40

000003c4 <__libc_start_main@plt>:
 3c4:   e28fc600        add     ip, pc, #0, 12
 3c8:   e28cca01        add     ip, ip, #4096   @ 0x1000
 3cc:   e5bcfc40        ldr     pc, [ip, #3136]!        @ 0xc40

000003d0 <__cxa_finalize@plt>:
 3d0:   e28fc600        add     ip, pc, #0, 12
 3d4:   e28cca01        add     ip, ip, #4096   @ 0x1000
 3d8:   e5bcfc38        ldr     pc, [ip, #3128]!        @ 0xc38

000003dc <puts@plt>:
 3dc:   e28fc600        add     ip, pc, #0, 12
 3e0:   e28cca01        add     ip, ip, #4096   @ 0x1000
 3e4:   e5bcfc30        ldr     pc, [ip, #3120]!        @ 0xc30

000003e8 <__gmon_start__@plt>:
 3e8:   e28fc600        add     ip, pc, #0, 12
 3ec:   e28cca01        add     ip, ip, #4096   @ 0x1000
 3f0:   e5bcfc28        ldr     pc, [ip, #3112]!        @ 0xc28

000003f4 <abort@plt>:
 3f4:   e28fc600        add     ip, pc, #0, 12
 3f8:   e28cca01        add     ip, ip, #4096   @ 0x1000
 3fc:   e5bcfc20        ldr     pc, [ip, #3104]!        @ 0xc20

Disassembly of section .text:

00000400 <_start>:
 400:   e3a0b000        mov     fp, #0
 404:   e3a0e000        mov     lr, #0
 408:   e49d1004        pop     {r1}            @ (ldr r1, [sp], #4)
 40c:   e1a0200d        mov     r2, sp
 410:   e52d2004        push    {r2}            @ (str r2, [sp, #-4]!)
 414:   e52d0004        push    {r0}            @ (str r0, [sp, #-4]!)
 418:   e59fa01c        ldr     sl, [pc, #28]   @ 43c <_start+0x3c>
 41c:   e28f3018        add     r3, pc, #24
 420:   e08aa003        add     sl, sl, r3
 424:   e3a03000        mov     r3, #0
 428:   e52d3004        push    {r3}            @ (str r3, [sp, #-4]!)
 42c:   e59f000c        ldr     r0, [pc, #12]   @ 440 <_start+0x40>
 430:   e79a0000        ldr     r0, [sl, r0]
 434:   ebffffe2        bl      3c4 <__libc_start_main@plt>
 438:   ebffffed        bl      3f4 <abort@plt>
 43c:   00001bc4        .word   0x00001bc4
 440:   0000002c        .word   0x0000002c

00000444 <call_weak_fn>:
 444:   e59f3014        ldr     r3, [pc, #20]   @ 460 <call_weak_fn+0x1c>
 448:   e59f2014        ldr     r2, [pc, #20]   @ 464 <call_weak_fn+0x20>
 44c:   e08f3003        add     r3, pc, r3
 450:   e7932002        ldr     r2, [r3, r2]
 454:   e3520000        cmp     r2, #0
 458:   012fff1e        bxeq    lr
 45c:   eaffffe1        b       3e8 <__gmon_start__@plt>
 460:   00001bac        .word   0x00001bac
 464:   00000028        .word   0x00000028

00000468 <deregister_tm_clones>:
 468:   e59f002c        ldr     r0, [pc, #44]   @ 49c <deregister_tm_clones+0x34>
 46c:   e59f302c        ldr     r3, [pc, #44]   @ 4a0 <deregister_tm_clones+0x38>
 470:   e08f0000        add     r0, pc, r0
 474:   e08f3003        add     r3, pc, r3
 478:   e1530000        cmp     r3, r0
 47c:   e59f3020        ldr     r3, [pc, #32]   @ 4a4 <deregister_tm_clones+0x3c>
 480:   e08f3003        add     r3, pc, r3
 484:   012fff1e        bxeq    lr
 488:   e59f2018        ldr     r2, [pc, #24]   @ 4a8 <deregister_tm_clones+0x40>
 48c:   e7933002        ldr     r3, [r3, r2]
 490:   e3530000        cmp     r3, #0
 494:   012fff1e        bxeq    lr
 498:   e12fff13        bx      r3
 49c:   00001bc4        .word   0x00001bc4
 4a0:   00001bc0        .word   0x00001bc0
 4a4:   00001b78        .word   0x00001b78
 4a8:   00000024        .word   0x00000024

000004ac <register_tm_clones>:
 4ac:   e59f0038        ldr     r0, [pc, #56]   @ 4ec <register_tm_clones+0x40>
 4b0:   e59f3038        ldr     r3, [pc, #56]   @ 4f0 <register_tm_clones+0x44>
 4b4:   e08f0000        add     r0, pc, r0
 4b8:   e08f3003        add     r3, pc, r3
 4bc:   e0433000        sub     r3, r3, r0
 4c0:   e1a01fa3        lsr     r1, r3, #31
 4c4:   e0811143        add     r1, r1, r3, asr #2
 4c8:   e59f3024        ldr     r3, [pc, #36]   @ 4f4 <register_tm_clones+0x48>
 4cc:   e1b010c1        asrs    r1, r1, #1
 4d0:   e08f3003        add     r3, pc, r3
 4d4:   012fff1e        bxeq    lr
 4d8:   e59f2018        ldr     r2, [pc, #24]   @ 4f8 <register_tm_clones+0x4c>
 4dc:   e7933002        ldr     r3, [r3, r2]
 4e0:   e3530000        cmp     r3, #0
 4e4:   012fff1e        bxeq    lr
 4e8:   e12fff13        bx      r3
 4ec:   00001b80        .word   0x00001b80
 4f0:   00001b7c        .word   0x00001b7c
 4f4:   00001b28        .word   0x00001b28
 4f8:   00000030        .word   0x00000030

000004fc <__do_global_dtors_aux>:
 4fc:   e59f304c        ldr     r3, [pc, #76]   @ 550 <__do_global_dtors_aux+0x54>
 500:   e59f204c        ldr     r2, [pc, #76]   @ 554 <__do_global_dtors_aux+0x58>
 504:   e08f3003        add     r3, pc, r3
 508:   e5d33000        ldrb    r3, [r3]
 50c:   e08f2002        add     r2, pc, r2
 510:   e3530000        cmp     r3, #0
 514:   112fff1e        bxne    lr
 518:   e59f3038        ldr     r3, [pc, #56]   @ 558 <__do_global_dtors_aux+0x5c>
 51c:   e92d4010        push    {r4, lr}
 520:   e7923003        ldr     r3, [r2, r3]
 524:   e3530000        cmp     r3, #0
 528:   0a000002        beq     538 <__do_global_dtors_aux+0x3c>
 52c:   e59f3028        ldr     r3, [pc, #40]   @ 55c <__do_global_dtors_aux+0x60>
 530:   e79f0003        ldr     r0, [pc, r3]
 534:   ebffffa5        bl      3d0 <__cxa_finalize@plt>
 538:   ebffffca        bl      468 <deregister_tm_clones>
 53c:   e59f301c        ldr     r3, [pc, #28]   @ 560 <__do_global_dtors_aux+0x64>
 540:   e3a02001        mov     r2, #1
 544:   e08f3003        add     r3, pc, r3
 548:   e5c32000        strb    r2, [r3]
 54c:   e8bd8010        pop     {r4, pc}
 550:   00001b30        .word   0x00001b30
 554:   00001aec        .word   0x00001aec
 558:   00000020        .word   0x00000020
 55c:   00001b00        .word   0x00001b00
 560:   00001af0        .word   0x00001af0
micho@Deb:~/work$
00000564 <frame_dummy>:
 564:   eaffffd0        b       4ac <register_tm_clones>

00000568 <main>:
 568:   e92d4800        push    {fp, lr}
 56c:   e28db004        add     fp, sp, #4
 570:   e59f3014        ldr     r3, [pc, #20]   @ 58c <main+0x24>
 574:   e08f3003        add     r3, pc, r3
 578:   e1a00003        mov     r0, r3
 57c:   ebffff96        bl      3dc <puts@plt>
 580:   e3a03000        mov     r3, #0
 584:   e1a00003        mov     r0, r3
 588:   e8bd8800        pop     {fp, pc}
 58c:   000000b0        .word   0x000000b0

Disassembly of section .fini:

00000590 <_fini>:
 590:   e92d4008        push    {r3, lr}
 594:   e8bd8008        pop     {r3, pc}
micho@Deb:~/work$ objdump -d hello3
Disassembly of section .fini:

080b6228 <_fini>:
 80b6228:       53                      push   %ebx
 80b6229:       83 ec 08                sub    $0x8,%esp
 80b622c:       e8 bf 33 f9 ff          call   80495f0 <__x86.get_pc_thunk.bx>
 80b6231:       81 c3 c3 5d 03 00       add    $0x35dc3,%ebx
 80b6237:       83 c4 08                add    $0x8,%esp
 80b623a:       5b                      pop    %ebx
 80b623b:       c3                      ret
 trop long
```

##### 🌞 Essayez d'exécuter le programme hello4

```powershell
micho@Deb:~/work$ ./hello3
Hello, World!
micho@Deb:~/work$ ./hello4
-bash: ./hello4: cannot execute binary file: Exec format error
```

## Partie II : Crack des trucz

### II. Ptits challenges de cracking

#### 1. Install Ghidra

##### 🌞 Avec une commande apt search, déterminez si le paquet ghidra est disponible

```powershell
micho@Deb:~/work$ apt search ghidra
Sorting... Done
Full Text Search... Done
```

##### 🌞 Ajouter l'URL des dépôts Kali à vos dépôts existants

```poweershell
micho@Deb:~/work$ sudo nano /etc/apt/sources.list
```

##### 🌞 Ajoutez la clé publique des gars de chez Kali

```powershell
micho@Deb:~/work$ wget https://archive.kali.org/archive-key.asc -O /etc/apt/trusted.gpg.d/kali-archive-keyring.asc
/etc/apt/trusted.gpg.d/kali-archive-keyring.asc: Permission denied
micho@Deb:~/work$ sudo !!
sudo wget https://archive.kali.org/archive-key.asc -O /etc/apt/trusted.gpg.d/kali-archive-keyring.asc
--2024-11-20 16:34:35--  https://archive.kali.org/archive-key.asc
Resolving archive.kali.org (archive.kali.org)... 192.99.45.140, 2607:5300:60:508c::
Connecting to archive.kali.org (archive.kali.org)|192.99.45.140|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3155 (3.1K) [application/octet-stream]
Saving to: ‘/etc/apt/trusted.gpg.d/kali-archive-keyring.asc’

/etc/apt/trusted.gpg. 100%[========================>]   3.08K  --.-KB/s    in 0s

2024-11-20 16:34:36 (41.7 MB/s) - ‘/etc/apt/trusted.gpg.d/kali-archive-keyring.asc’ saved [3155/3155]
```

##### 🌞 Mettez à jour la liste des dépôts que votre OS connaît actuellement

```powershell
micho@Deb:~/work$ sudo apt update -y
Get:1 http://security.debian.org/debian-security bookworm-security InRelease [48.0 kB]
Hit:2 http://deb.debian.org/debian bookworm InRelease
Get:3 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
Get:4 http://kali.download/kali kali-rolling InRelease [41.5 kB]
Get:5 http://security.debian.org/debian-security bookworm-security/main Sources [126 kB]
Get:6 http://security.debian.org/debian-security bookworm-security/main amd64 Packages [204 kB]
Get:7 http://security.debian.org/debian-security bookworm-security/main Translation-en [125 kB]
Get:8 http://kali.download/kali kali-rolling/main amd64 Packages [20.3 MB]
Get:9 http://kali.download/kali kali-rolling/contrib amd64 Packages [112 kB]
Get:10 http://kali.download/kali kali-rolling/non-free amd64 Packages [197 kB]
Get:11 http://kali.download/kali kali-rolling/non-free-firmware amd64 Packages [10.6 kB]
Fetched 21.2 MB in 43s (495 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
1232 packages can be upgraded. Run 'apt list --upgradable' to see them.
```

##### 🌞 Avec une commande apt search, déterminez si le paquet ghidra est disponible

```powershell
micho@Deb:~/work$ apt search ghidra
Sorting... Done
Full Text Search... Done
ghidra/kali-rolling 11.0+ds-0kali1 amd64
  Software Reverse Engineering Framework

ghidra-data/kali-rolling 10.5-0kali1 all
  FID databases for Ghidra

ghidra-dbgsym/kali-rolling 11.0+ds-0kali1 amd64
  debug symbols for ghidra

quark-engine/kali-rolling 23.9.1-0kali2 all
  Android Malware (Analysis | Scoring System)

rz-ghidra/kali-rolling 0.7.0-0kali1+b1 amd64
  ghidra decompiler and sleigh disassembler for rizin

rz-ghidra-dbgsym/kali-rolling 0.7.0-0kali1+b1 amd64
  debug symbols for rz-ghidra

```

##### 🌞 Installez le paquet ghidra

```powershell
micho@Deb:~/work$ apt search ghidra
Sorting... Done
Full Text Search... Done
ghidra/kali-rolling 11.0+ds-0kali1 amd64
  Software Reverse Engineering Framework

ghidra-data/kali-rolling 10.5-0kali1 all
  FID databases for Ghidra

ghidra-dbgsym/kali-rolling 11.0+ds-0kali1 amd64
  debug symbols for ghidra
```

#### 2. Patch manuel programme simple

##### 🌞 Récupérez le code de password_2.c sur la machine Linux et compilez-le

```powershell
micho@Deb:~/work$ x86_64-linux-gnu-gcc -fno-stack-protector -g -o password_2 password_2.c -lcrypto -Wno-deprecated-declarations
micho@Deb:~/work$ ghidra

```

#### 3. Root-me

```powershell

```
