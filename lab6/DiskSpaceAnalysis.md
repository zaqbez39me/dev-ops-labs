# 1. Analyze disk space

## Check disk space

### Operating system

`Windows 10 - 64 bit`

### Command

```bash
chkdsk <DISK NAME>:
```

Where DISK NAME is name of the disk for check. For example, disk C.
In my case was used command

```bash
chkdsk C:
```

### Command description

This is the command that shows the disk usage statistics, including the amount of free space.

### Command output

```
Тип файловой системы: NTFS.

ПРЕДУПРЕЖДЕНИЕ! Параметр F не указан.
CHKDSK выполняется в режиме только чтения.

Этап 1. Проверка базовой структуры файловой системы...
  Обработано записей файлов: 1459456.
Проверка файлов завершена.
 Длительность фазы (Проверка записи файла): 11.36 с.
  Обработано больших файловых записей: 12071.
 Длительность фазы (Восстановление потерянной файловой записи): 0.00 мс.
  Обработано поврежденных файловых записей: 0.
 Длительность фазы (Проверка поврежденной файловой записи): 0.63 мс.

Этап 2. Проверка связей имен файлов...
  Обработано записей повторного анализа: 796.
  Обработано записей индекса: 1976970.
Проверка индексов завершена.
 Длительность фазы (Проверка индексов): 34.10 с.
  Проверено неиндексированных файлов: 0.
 Длительность фазы (Переподключение потерянного элемента): 17.17 с.
  Восстановлено неиндексированных файлов в утерянное и найденное: 0.
 Длительность фазы (Восстановление потерянного элемента в раздел "Потерянные и найденные"): 0.38 мс.
  Обработано записей повторного анализа: 796.
 Длительность фазы (Проверка точки повторного анализа и ИД объекта): 9.99 мс.

Этап 3. Проверка дескрипторов безопасности...
Проверка дескрипторов безопасности завершена.
 Длительность фазы (Проверка дескриптора безопасности): 31.11 мс.
  Обработано файлов данных: 258758.
 Длительность фазы (Проверка атрибута данных): 1.31 мс.
CHKDSK проверяет журнал USN...
  Обработано байт USN: 41652328.
Завершена проверка журнала USN
 Длительность фазы (Проверка журнала USN): 185.81 мс.

Windows проверила файловую систему и не обнаружила проблем.
Дальнейшие действия не требуются.

 244196351 КБ всего на диске.
 213091424 КБ в 1096034 файлах.
    548564 КБ в 258759 индексах.
         0 КБ в поврежденных секторах.
   1579167 КБ используется системой.
     65536 КБ занято под файл журнала.
  28977196 КБ свободно на диске.

      4096 байт в каждой единице распределения.
Всего единиц распределения на диске:   61049087.
Доступно единиц распределения на диске:    7244299.
Общая длительность: 1.04 мин (62892 мс).
```

# 2. Analyze inodes

## Operating System

WSL under Windows

## Command

```bash
df -i
```

## Description

This command displays information about the inodes on a file system, including the number of inodes used and available,
as well as the percentage of inodes used.

## Output

```
Filesystem       Inodes   IUsed    IFree IUse% Mounted on
none            1012578       2  1012576    1% /mnt/wsl
none                999 -999001  1000000     - /usr/lib/wsl/drivers
none            1012578       5  1012573    1% /usr/lib/wsl/lib
/dev/sdc       67108864  191404 66917460    1% /
none            1012578      33  1012545    1% /mnt/wslg
rootfs          1011766      11  1011755    1% /init
none            1011774     164  1011610    1% /dev
none            1012578      10  1012568    1% /run
none            1012578       1  1012577    1% /run/lock
none            1012578       1  1012577    1% /run/shm
none            1012578       1  1012577    1% /run/user
tmpfs           1012578      16  1012562    1% /sys/fs/cgroup
none            1012578      48  1012530    1% /mnt/wslg/versions.txt
none            1012578      48  1012530    1% /mnt/wslg/doc
drvfs               999 -999001  1000000     - /mnt/c
drvfs               999 -999001  1000000     - /mnt/f
```

# 3. Resource Consumption Analysis

## Operating System

WSL under Windows

## Commands

* ### CPU usage

  #### Command

    ```bash
    ps aux --sort=-%cpu | head -2
    ```
  #### Description
  This command shows the process with most CPU usage in system. In my case it is the root process
  because root process operates with system in WSL.

  #### Output
    ```
    USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root         1  0.0  0.0   2324  1500 ?        Sl   22:29   0:00 /init
    ```

* ### RAM usage
  #### Command
    ```bash
    ps aux --sort=-%mem | head -2
    ```
  #### Description
  This command shows the process with most RAM usage in system. In my case it is the bash process
  because bash has a large history of commands entered by user.

  #### Output
  ```
  USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
  zaqbez3+     9  0.0  0.0  10064  5016 pts/0    Ss   22:29   0:00 -bash
  ```