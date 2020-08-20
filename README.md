# clkdbg
"clkdbg" is a built-in kernel driver as assitant for setting system clock and
getting clock info which is based on linux CCF framework. After applying that,
it's possible and convenient to do many operations on clock by shell commands.

How to compile:
	1. Copy clkdbg.c into your local linux kernel source, maybe drivers/clk/
	2. Modify the Makeifle to compile this file, mayebe add this statement:
		obj-y		+=	clkdbg.o

How to use:
	1. After linux is booted up, mount debugfs firstly:
		mount -t debugfs none /sys/kernel/debug
	2. run the shell commands as you want.
		(you can cat /sys/kernel/debug/clkdbg to get command help) 
