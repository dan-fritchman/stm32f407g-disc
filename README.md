stm32f407g-disc
===============

_stm32f407g-disc_ contains a basic board support package for the
[STM32F407G-DISC][] microcontroller board (also known as STM32F4DISCOVERY, but
easy to confuse with other STM32F4 discovery boards which also exist) to write
firmwares using the Rust language. This experimentation board features multiple
user programmable LEDs an accelerometer, an audio DAC with amplified, a
microphone jack, a microphone and a user programmable USB connector. A shield
with breakout for Ethernet, RS232 serial port, SD-Card reader, and LCD
connector is also available.

It also contains a (non-removable) capable ST-Link V2 debugging interface.

[STM32F407G-DISC]: https://www.st.com/en/evaluation-tools/stm32f4discovery.html

License
-------

[0-clause BSD license](LICENSE-0BSD.txt).


Standing This Up
-----------------

* In one terminal: 

```
openocd -f interface/stlink-v2-1.cfg -f target/stm32f4x.cfg   
```

* Then in another:

```
cargo build --target thumbv7em-none-eabihf
arm-none-eabi-gdb -q target/thumbv7em-none-eabihf/debug/stm32f407g-disc
```

* Then inside of GDB: 

```
target remote :3333
load 
monitor reset halt
break main
continue
```

* To enter source-review mode:

```
layout src
```

Shout-Outs
---------- 

* https://docs.rust-embedded.org/discovery/index.html - for STM32F*3*


