---
title: 32-bit Arm on Arm
---
# Notes on building 32-bit Arm on Arm at Packet

Ed Vielmetti, Packet

## Problem statement

Execute 32-bit Arm codes in a 32-bit only environment on
a server that is capable of running both 32-bit and 64-bit 
code. 

## Hosted CI options

[Drone Cloud](https://cloud.drone.io) offers a 32-bit build environment. 
Drone supports multi-machine, multi-platform pipelines. This is useful 
when you need to build and test your code on multiple architectures and operating systems.
See the Drone documentation for [Multi-Platfrom](https://readme.drone.io/config/pipeline/multi-platform/)
for detailed instructions.

[Balena](https://www.balena.io/) offers a 32-bit build environment.
Balena is a complete set of tools for building, deploying, and managing fleets of connected Linux devices.

## Hardware options at Packet

### Ampere eMag

The Ampere eMag 1 chip offers both 32-bit and 64-bit
execution. See the [Wikichip eMag page](https://en.wikichip.org/wiki/ampere_computing/emag)
for details on this processor family.

### Hisilicon

The Hisilicon Hi1616 chip offers both 32-bit and 64-bit
execution. See the [Wikichip Hi1616 page](https://en.wikichip.org/wiki/hisilicon/hi16xx/hi1616)
for details on this processor family.

## Software configurations

### Balena

[Docker builds on ARM servers: you’re not crazy, your builds really are 5x faster](https://www.balena.io/blog/docker-builds-on-arm-servers-youre-not-crazy-your-builds-really-are-5x-faster/), 2 August 2017.

### Docker

### Drone CI

[Announcing Drone Cloud, A Free Continuous Integration Service for x86 and Arm](https://blog.drone.io/drone-cloud/), 21 November 2018.

### Gitlab CI

Use the [GitLab Runner](https://docs.gitlab.com/runner/) in a suitable execution environment.

### Jenkins + libvirt (Lollipop Cloud)

[libvirt](https://libvirt.org/) is a virtualization API for virtual machines.

### Linux native support
