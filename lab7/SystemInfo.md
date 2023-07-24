# System information

## Processor, RAM, and Network Information

### lscpu - Display Processor Information

* **Description**:

  The tool that is used to get CPU information

* **Command**:

  ```bash
    lscpu
  ```
* **Output**:
  ```text
  Architecture:            x86_64
    CPU op-mode(s):        32-bit, 64-bit
    Address sizes:         45 bits physical, 48 bits virtual
    Byte Order:            Little Endian
  CPU(s):                  2
    On-line CPU(s) list:   0,1
  Vendor ID:               GenuineIntel
    Model name:            11th Gen Intel(R) Core(TM) i5-11300H @ 3.10GHz
      CPU family:          6
      Model:               140
      Thread(s) per core:  1
      Core(s) per socket:  2
      Socket(s):           1
      Stepping:            1
      BogoMIPS:            5222.39
      Flags:               fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc arch_perfm
                           on rep_good nopl xtopology tsc_reliable nonstop_tsc cpuid tsc_known_freq pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_ti
                           mer aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti ssbd ibrs ibpb stibp fsgsbase tsc_adjust bmi1 avx2 smep bmi2 erms invp
                           cid avx512f avx512dq rdseed adx smap avx512ifma clflushopt clwb avx512cd sha_ni avx512bw avx512vl xsaveopt xsavec xgetbv1 xsaves arat avx512vbmi umip avx512
                           _vbmi2 gfni vaes vpclmulqdq avx512_vnni avx512_bitalg avx512_vpopcntdq rdpid fsrm avx512_vp2intersect flush_l1d arch_capabilities
  Virtualization features: 
    Hypervisor vendor:     VMware
    Virtualization type:   full
  Caches (sum of all):     
    L1d:                   96 KiB (2 instances)
    L1i:                   64 KiB (2 instances)
    L2:                    2,5 MiB (2 instances)
    L3:                    8 MiB (1 instance)
  NUMA:                    
    NUMA node(s):          1
    NUMA node0 CPU(s):     0,1
  Vulnerabilities:         
    Itlb multihit:         Not affected
    L1tf:                  Mitigation; PTE Inversion
    Mds:                   Vulnerable: Clear CPU buffers attempted, no microcode; SMT Host state unknown
    Meltdown:              Mitigation; PTI
    Mmio stale data:       Not affected
    Retbleed:              Mitigation; IBRS
    Spec store bypass:     Mitigation; Speculative Store Bypass disabled via prctl
    Spectre v1:            Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Spectre v2:            Mitigation; IBRS, IBPB conditional, STIBP disabled, RSB filling, PBRSB-eIBRS Not affected
    Srbds:                 Not affected
    Tsx async abort:       Not affected
  ```

### free - Display RAM Information

* **Description**:

  The tool that provides information about the system's memory usage, including total available memory, used memory,
  free memory, and cached memory.

* **Command**:

    ```bash
    free
    ```

* **Output**:

  ```text
                 total        used        free      shared  buff/cache   available
  Mem:         4005236      932860     2070512       46928     1001864     2806788
  Swap:        2744316           0     2744316
  ```

### ip - Display Network Information

* **Description**:

  The tool that displays information about network interfaces, including IP addresses, MAC addresses, and interface
  status.

* **Command**:

    ```bash
    ip addr
    ```

* **Output**:

  ```text
    1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
    2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:44:5e:57 brd ff:ff:ff:ff:ff:ff
    altname enp2s1
    inet 192.168.227.128/24 brd 192.168.227.255 scope global dynamic noprefixroute ens33
       valid_lft 1265sec preferred_lft 1265sec
    inet6 fe80::c360:d315:1429:139c/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
  ```

## Operating System Specifications

### uname - Display the operating system specifications

* **Description**:

  The tool that allows user to retrieve various information about the operating system.

* **Command**:

    ```bash
    uname -a
    ```

* **Output**:

  ```text
    Linux zaqbez39me-virtual-machine 5.19.0-46-generic #47~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Wed Jun 21 15:35:31 UTC 2 x86_64 x86_64 x86_64 GNU/Linux
  ```
