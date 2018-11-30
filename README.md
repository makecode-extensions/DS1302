# DS1302

makecode DS1302 RTC extension for micro:bit  

Author: shaoziyang  
Date:   2018.Mar  

  
![](ds1302.jpg)

## Add extension

open your microbit makecode project, in add extension, paste  

https://github.com/microbit-makecode-packages/DS1302  

to search box then search.

## Basic usage
```
let b = 0
let tmy: number[] = []
let a = 0
let tmx: number[] = []
let item: DS1302.DS1302RTC = null
let old = 0
let sec = 0
sec = 0
old = -1
item = DS1302.create(DigitalPin.P13, DigitalPin.P14, DigitalPin.P15)
tmx = [2, 3, 4, 4, 4, 3, 2, 1, 0, 0, 0, 1]
tmy = [0, 0, 1, 2, 3, 4, 4, 4, 3, 2, 1, 0]
basic.forever(() => {
    sec = item.getSecond()
    if (sec != old) {
        old = sec
        a = sec / 5
        b = sec % 5
        if (4 == b) {
            led.unplot(tmx[a], tmy[a])
        } else {
            led.plotBrightness(tmx[a], tmy[a], 20 + b * 20)
        }
        led.toggle(2, 2)
    }
    basic.pause(300)
}) 
```


## API

- **function DateTime(year: number, month: number, day: number, weekday: number, hour: number, minute: number, second: number)**  
set Date and Time.  

- **function setSecond(dat: number)**  
set second.

- **function getSecond(dat: number)**  
get second.

- **function setMinute(dat: number)**  
set minute.

- **function getMinute(dat: number)**  
get minute.

- **function setHour(dat: number)**  
set hour.

- **function getHour(dat: number)**  
get hour.

- **function setWeekday(dat: number)**  
set week day.

- **function getWeekday(dat: number)**  
get week day.

- **function setDay(dat: number)**  
set day.

- **function getDay(dat: number)**  
get day.

- **function setMonth(dat: number)**  
set month.

- **function getMonth(dat: number)**  
get month.

- **function setYear(dat: number)**  
set year.

- **function getYear(dat: number)**  
get year.

- **writeRam(reg: number, dat: number)**  
write data to ram  
reg: 0-30

- **readRam(reg: number)**  
read data from ram  
reg: 0-30

## Demo

![](demo.jpg)  

![](demo.gif)  

## License

MIT

Copyright (c) 2018, microbit/micropython Chinese community  

## Supported targets

* for PXT/microbit


[From microbit/micropython Chinese community](http://www.micropython.org.cn)
