При первом запуске проекта возникает проблема с компиляцией:
![[Отсутствие файла SPI_h.jpg]]

Она возникает из-за того, что в каталоге 
[C:\Users\dimamokin\.platformio\packages\framework-energiativa\libraries\AIR430BoostEuropeETSI](C:\Users\dimamokin\.platformio\packages\framework-energiativa\libraries\AIR430BoostEuropeETSI)
размещён пустой заголовочный файл SPI.h
![[Пустой заголовочный файл SPI_h.jpg]]

Вместо него нужно поставить непустой файл из другого каталога, например отсюда:
[C:\Users\dimamokin\.platformio\packages\framework-energiativa\libraries\SPI](C:\Users\dimamokin\.platformio\packages\framework-energiativa\libraries\SPI)

Тогда всё должно заработать!