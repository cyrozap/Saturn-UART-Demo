# Saturn-UART-Demo

[![Build Status](https://jenkins.cyrozap.com/job/Saturn-UART-Demo/badge/icon)](https://jenkins.cyrozap.com/job/Saturn-UART-Demo/)
[![License](http://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

## Prerequisites

- Xilinx ISE (tested with version 14.7)
- `git`
- `make` (Linux only)

## Building

### Linux

Since the Saturn board comes with either an LX16 or an LX45, before the
"make bin" step, you need to make sure the device in the Makefile is the same
as the one you have.

    git clone https://github.com/cyrozap/Saturn-UART-Demo.git
    cd Saturn-UART-Demo
    git submodule update --init
    source /opt/Xilinx/14.7/ISE_DS/settings64.sh
    make bin

### Windows

1.  Clone the repository with your favorite git client
    - `git clone https://github.com/cyrozap/Saturn-UART-Demo.git`
2.  Using your git client, run a submodule update with init
    - `cd Saturn-UART-Demo && git submodule update --init`
3.  Open the Xilinx ISE Project Navigator
4.  Create a new project (File -> New Project...)
    - You can enter anything you want for the name, but the Location
    and Working Directory must be the same as the folder you just
    cloned the repository into
    - The "Top-level source type" is "HDL"
    - Family: Spartan6
    - Device: XC6SLX16/XC6SLX45
    - Package: CSG324
    - Speed: -2
    - Preferred Language: Verilog
5.  Add source files (Project -> Add Source...)
    - Select `uart_demo.v` and `saturn.ucf`
    - Click "OK"
6.  Open the properties for the "Generate Programming File" process
    - Under "General Options", enable "Create Binary Configuration File"
7.  Run the "Generate Programming File" process
