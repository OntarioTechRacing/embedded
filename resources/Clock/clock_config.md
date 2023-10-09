# STM32CubeMX Clock Configuration

## `.ioc` Configuration

- Configure Clock In STM32CubeMX

## STM32CubeMX Screenshots

1) Navigate to Clock Configurations in your project using the tabs at the top of the interface. 

![Image of Clock config window in CubeMX](image1.png)

2) Change input frequency mux (sideways trapaziod) to HSE (High Speed External). This will change the SYSCLK and HCLK (grey boxes).

![Image of chaging input to HSE](image2.png)

3) If any boxes turn red, click on the resolve clock issues box. 

![Image of Resolve Clock Issues box highlighted](image3.png)

4) Use the APB prescalers (red box) to manipulate the output frequencies of the peripherals (grey box). 

![Image of Resolve Clock Issues box highlighted](image4.png)