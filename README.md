# clkdbg
   "clkdbg" is a built-in kernel driver as assitant for setting system clock and getting clock info which is based on linux CCF framework. After applying that, it's possible and convenient to do many operations on clock by shell commands.

   The main functions are listed below:

- prepare
- unprepare
- enable
- disable
- prepare_enable
- disable_unprepare
- set_rate
- round_rate
- get_rate
- set_parent
- get_parent



# Compile:

 - Copy clkdbg.c into your local linux kernel source, maybe drivers/clk/
 - Modify the Makeifle to compile this file, mayebe add this statement:
   obj-y		+=	clkdbg.o



# Usage:

- After linux is booted up, mount debugfs firstly:
  mount -t debugfs none /sys/kernel/debug
- run the shell commands as you want.
  (you can cat /sys/kernel/debug/clkdbg to get command help) 
  - echo prepare *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo unprepare *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo enable *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo disable *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo prepare_enable *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo disable_unprepare *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo set_rate *{clk_name}* *{rate(Hz)}* > /sys/kernel/debug/clkdbg
  - echo round_rate *{clk_name}* *{rate(Hz)}* > /sys/kernel/debug/clkdbg
  - echo get_rate *{clk_name}* > /sys/kernel/debug/clkdbg
  - echo set_parent *{clk_name}* *{parent_name}* > /sys/kernel/debug/clkdbg
  - echo get_parent *{clk_name}* > /sys/kernel/debug