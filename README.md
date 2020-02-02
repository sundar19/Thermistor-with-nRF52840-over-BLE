# Thermistor-with-nRF52840-over-BLE
Getting temperature value from thermistor thru ADC and sending to App over BLE

## General instructions
The following instructions are written for Segger Embedded Studio download here https://www.segger.com/downloads/embedded-studio/
1. Go to the following website http://developer.nordicsemi.com/nRF5_SDK/nRF5_SDK_v15.x.x/ and download v15.2.0 
2. After which go to D:\nRF5_SDK_15.2.0_9412b96\examples\ble_peripheral\ble_app_uart\pca10056\s140\ses\ and open .emproject , then automatically segger studio will open along with main.c file
3. Change the main.c file to the attached file.

## Merging BLE with ADC
Go to sdk_config.h and search 

1. nrf_drv_timer   TIMER_ENABLED 1 (enable the timer by replacing 0 to 1),
                   TIMER3_ENABLED 1 (We have enabled timer instance 3 in our main.c)


2. nrfx_timer      NRFX_TIMER_ENABLED 1(enable the timer by replacing 0 to 1),
                   NRFX_TIMER3_ENABLED 1 (We have enabled timer instance 3 in our main.c)


3. nrfx_ppi        NRFX_PPI_ENABLED 1


4. nrf_drv_ppi     PPI_ENABLED 1


5. nrf_drv_saadc   SAADC_ENABLED 1


6. nrfx_saadc      NRFX_SAADC_ENABLED 1


Then include the following libraries in your main.c , #include""(already in program)

nrf_drv_saadc.h , nrf_drv_timer.h , nrf_drv_ppi.h , nrfx_ppi.h , nrfx_timer.h , nrfx_saadc.h


In your nRF_Drivers (A tab in your left)
Search and add the following files 

1.nrf_drv_ppi.c

2.nrfx_ppi.c

3.nrfx_timer.c

4.nrfx_saadc.c


                   
