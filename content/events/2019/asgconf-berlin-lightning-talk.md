# Works on Arm: Third year of support of fundamental user-space software for arm64 (aarch64)

## Ed Vielmetti, Packet 

### ed@packet.com

### Presented at All Systems Go, Berlin, 2019-09-20

## Who am I

Ed Vielmetti, Packet.

Insert photo here.

Old time Unix user and systems administrator, since 1985, back in the old days when every time
you got a new server, it ran a brand new different operating system on a different CPU with
a different architecture.

Based in Ann Arbor.
Works at Workantile, a not-for-profit coworking community in Ann Arbor.
Employed by Packet.
Works on Arm is a project funded by Arm Holdings now in its 3d year.

## What is "Works on Arm"?

Build and test and CI infrastructure for arm64 Linux, primarly user-space software. Runs at
Packet, a bare metal hosting company based in New York.

## Where are the servers, and what are they?

Arm ervers are in Packet core data centers. 

Primary data centers in 

* Amsterdam (AMS1)
* New Jersey (EWR1)
* Texas (DFW2)
* San Jose (SJC1)
* Tokyo (NRT1)

Hardware includes

* Ampere eMag / Lenovo HR330A "c2.large.arm"
* Cavium (now Marvell) ThunderX "c1.large.arm"
* Marvell ThunderX2
* Hisilicon D03, D05
* QDT "Amberwing"
* lots of single-board computers in Packet Labs, not in Packet's public cloud.

## When did you get started?

Packet launched c1.large.arm in 2016. 96-core ThunderX.
I was a beta tester, found a bunch of issues.
At some point it was obvious that there was a full-time job chasing issues.

## Why is this necessary?

Well, we call them issues, and if they are interesting enough,
we call them enhancement and optimization opportunities.

* Go: "page size" bug; improved high-core count support
* ThunderX firmware to support OpenJDK / Java applications with huge heaps

## Thank you!

# THUNDEROUS APPLAUSE
