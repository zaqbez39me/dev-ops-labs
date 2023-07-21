# Traceroute

## 1. Traceroute

### Command

First of all, on WSL we need to install util using
`sudo apt install traceroute`
Then we can traceroute with restriction on quotes number using
`traceroute -q 2 youtube.com`

### Description

This command initiates a traceroute to the domain name youtube.com, with a max TTL value of 64. The number of
probes is set to 2 to minimize the time taken for the traceroute.

### Output

```
traceroute to youtube.com (108.177.14.190), 30 hops max, 60 byte packets
 1  DESKTOP-FOT3382.mshome.net (172.29.64.1)  0.720 ms  0.675 ms
 2  10.244.1.1 (10.244.1.1)  1.053 ms  1.030 ms
 3  10.250.0.2 (10.250.0.2)  1.254 ms  1.230 ms
 4  10.252.5.1 (10.252.5.1)  2.149 ms  2.030 ms
 5  188.130.155.1 (188.130.155.1)  1.980 ms  2.439 ms
 6  1.123.18.84.in-addr.arpa (84.18.123.1)  11.057 ms  11.033 ms
 7  188.254.80.81 (188.254.80.81)  14.278 ms  11.927 ms
 8  95.167.92.161 (95.167.92.161)  33.168 ms *
 9  * *
10  * *
11  * *
12  108.170.250.33 (108.170.250.33)  35.384 ms *
13  * 108.170.250.130 (108.170.250.130)  33.252 ms
14  142.251.237.154 (142.251.237.154)  48.251 ms 72.14.234.54 (72.14.234.54)  47.759 ms
15  142.250.233.0 (142.250.233.0)  48.126 ms 74.125.253.109 (74.125.253.109)  47.692 ms
16  142.250.56.13 (142.250.56.13)  49.928 ms 172.253.79.237 (172.253.79.237)  47.868 ms
17  * *
18  * *
19  * *
20  * *
21  * *
22  * *
23  * *
24  * *
25  * *
26  lt-in-f190.1e100.net (108.177.14.190)  47.810 ms  45.789 ms
```

### Observation

The biggest latency was met on the way from local internet provider to some third party node.

## 2. Dig

### Command

```bash
dig google.com
```

### Description

This is a flexible tool for interrogating DNS name servers , which performs DNS lookups and displays the answers that
are returned from the name server.

### Output

```bash
; <<>> DiG 9.16.1-Ubuntu <<>> google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 500
;; flags: qr rd ad; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 0
;; WARNING: recursion requested but not available

;; QUESTION SECTION:
;google.com.                    IN      A

;; ANSWER SECTION:
google.com.             0       IN      CNAME   forcesafesearch.google.com.
forcesafesearch.google.com. 0   IN      A       216.239.38.120

;; Query time: 0 msec
;; SERVER: 172.29.64.1#53(172.29.64.1)
;; WHEN: Fri Jul 21 23:51:39 MSK 2023
;; MSG SIZE  rcvd: 120
```

### Observation

The actual ip address of google.com in my case occurs to be **216.239.38.120**.