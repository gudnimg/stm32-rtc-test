# stm32-rtc-test
In this repo I am trying out STM32's RTC peripheral

## Reading Material

* http://embedded-lab.com/blog/stm32s-internal-rtc/
* [Chapter 61: HAL RTC Generic Driver](https://www.st.com/resource/en/user_manual/dm00173145-description-of-stm32l4l4-hal-and-lowlayer-drivers-stmicroelectronics.pdf) (Page 937 / 2719)


## Important Registers

**RTC_CRH** 

**RTC_CRL**

**RTC_CNTL and RTC_CNTH**: keep the count of the seconds or in other words time.

## Other notes

* `HAL_RTC_GetDate()` must be called after `HAL_RTC_GetTime()` in order for `sTime` to receive updated values.

