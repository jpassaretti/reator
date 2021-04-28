# reator
Reator Fotoquímico(Central de controle)

Nesse projeto foi desenvolvido um sistema de controle de um reator fotoquímico

![controle](https://user-images.githubusercontent.com/9045259/116277535-f4736d80-a75b-11eb-9812-8094eb0a3acd.png)

Componentes da montagem

Micro controlador DOIT ESP32 dev KIT 1

A - Fluxomêtro 1/2 pol.
B - Sensor de condutividade
C – Relé estado sólido (dois canais)
D - Termopar tipo K

O ESP32 permite o desenvolvimento de aplicações com interfaces webserver e comunicação sem fio com diferentes tipos de clientes homologados, facilitando a transferência de tecnologias para aplicações em laboratórios ou industriais.

![aaaaa](https://user-images.githubusercontent.com/9045259/116328202-e3981b80-a79e-11eb-8143-9ca8f5bbdd0b.jpg)

O microcontrolador ESP32 é compatível com as bibliotecas arduino o que facilitando o uso de shields e bibliotecas disponíveis. O ESP32 pode atuar como uma estação Wi-Fi, como um ponto de acesso ou ambos e programável a partir do Arduino IDE. Existe um complemento para o Arduino IDE que permite programar o ESP32 usando o Arduino IDE e sua linguagem de programação. É possível instalar a placa ESP32 no Arduino IDE no Windows, Mac OS X ou Linux:

Windows
https://randomnerdtutorials.com/installing-the-esp32-board-in-arduino-ide-windows-instructions/

LINUX e MAC
https://randomnerdtutorials.com/installing-the-esp32-board-in-arduino-ide-mac-and-linux-instructions/

O programa de controle está disponível anexo em “fotoreator.ino”. O código pode ser e carregado no microcontrolador através do Arduino IDE:

![Screenshot_2021-04-27_21-03-47](https://user-images.githubusercontent.com/9045259/116328282-104c3300-a79f-11eb-9c88-3de5c24319e4.png)

O sistema final é controlado pelo ESP32 transferindo em tempo real as informações de um: (A) fluxômetro com sensor de feito hall, o programa faz a contagem de giros de uma ventoinha interna presente no dispositivo; (B) Um sensor de condutividade construído usando um Lm393 que consiste em dois comparadores de voltagem de precisões independentes com um máximo de 2,0mV, dois comparadores que operam em uma única fonte de alimentação em uma faixa mais ampla de diferença de potencial; (C) Relé estado sólido (dois canais), Corrente da fonte alimentação (mínima): 160mA e relés G3MB -202P; e (D) Um termopar tipo K usando um chip MAX6675, o chip realiza compensação de junta fria e digitaliza o sinal de um termopar tipo K. Os dados são enviados em uma resolução de 12 bits em formato somente de leitura. Este conversor resolve temperaturas de 0,25 ° C, permite leituras de até + 1024 ° C e exibe precisão de termopar de 8LSBs para temperaturas que variam de 0 °C a + 700 °C.

Todo o conjunto foi montado em uma placa ilhada 9,5 x 9,5 e protegido por uma caixa de PVC 11 x 19 x 5 cm e os cabos externos para conexão com dispositivos físicos do reator.

![realfoto](https://user-images.githubusercontent.com/9045259/116277889-4d430600-a75c-11eb-9d7e-ed8edf68194c.jpeg)

Os Canais 1 e 2 controlados pelas GPIO 26 e 27 do ESP32 podem ser controlados via navegador acessado pelo ip do microcontrolador registrado em diferentes clientes como celulares, tabletes e computadores conectados numa mesma rede local.

![WhatsApp Image 2021-04-27 at 20 21 01](https://user-images.githubusercontent.com/9045259/116330580-32947f80-a7a4-11eb-9fdb-e2122e109e83.jpeg)

Com o arduino IDE é possivel obter os valores em tempo real do ESP32 via USB. Com programas como o Putty (https://www.putty.org/) é posível acompanhar os sinais dos sensores, estados do relés, dispositivos em rede e gravação de resultados obtidos durante experimentos usando o reator.

![putty1](https://user-images.githubusercontent.com/9045259/116330858-c6664b80-a7a4-11eb-8063-f78ebaeb81a3.png)
![putty2](https://user-images.githubusercontent.com/9045259/116330856-c5cdb500-a7a4-11eb-9aaa-bd7cc4ca3393.png)
![putty3](https://user-images.githubusercontent.com/9045259/116330855-c5351e80-a7a4-11eb-83b2-0880e8c11a5f.png)
