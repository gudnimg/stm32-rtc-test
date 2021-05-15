# stm32-rtc-test
In this repo I am trying out STM32's RTC peripheral

## Reading Material

* http://embedded-lab.com/blog/stm32s-internal-rtc/ *Note: the registers used in this article are not the same as for L4 series.*
* [Chapter 61: HAL RTC Generic Driver](https://www.st.com/resource/en/user_manual/dm00173145-description-of-stm32l4l4-hal-and-lowlayer-drivers-stmicroelectronics.pdf) (Page 937 / 2719)

----


I'll be playing around with Nucleo L412RB-P

## STM32L412RB documents

* [STM32L412RB datasheet](https://www.st.com/resource/en/datasheet/stm32l412rb.pdf)
* [L4xxx reference manual](https://www.st.com/resource/en/reference_manual/dm00151940-stm32l41xxx42xxx43xxx44xxx45xxx46xxx-advanced-armbased-32bit-mcus-stmicroelectronics.pdf) (Details about RTC registers in chapter 34.6 at page 1047/1999)

## Important Registers

**RTC time register (`RTC_TR`)** Keeps track of hours, minutes, and seconds in BCD format.

**RTC date register (`RTC_DR`)** Keeps track of years, week days, months, and date in BCD format.

**RTC status register (`RTC_SR`)**

**RTC timestamp time register (`RTC_TSTR`)**

Note: The content of this register is valid only when TSF is set to 1 in `RTC_SR`. It is cleared when TSF bit is reset.

**RTC control register (`RTC_CR`)**

**RTC status clear register (`RTC_SCR`)**

----

## Why is BCD format used?

* https://www.youtube.com/watch?v=RDoYo3yOL_E&ab_channel=Computerphile
* https://embedded.fm/blog/2018/6/5/an-introduction-to-bcd
* https://electronics.stackexchange.com/questions/12606/why-do-real-time-clock-chips-use-bcd

----

## Other notes

* `HAL_RTC_GetDate()` must be called after `HAL_RTC_GetTime()` in order for `sTime` to receive updated values.

