# STM32F103_UART_Receive
Using the UART to receive a string from PC (Software: Termite Serial)

Neste exemplo foi criado um código no STM32 que inverte o estado de um led sempre que a string "next" for enviada pelo PC.
Para o PC enviar a string foi usado o software gratuito Termite Serial.

Para a conexão com o PC foi usado o módulo conversor USB-TTL CH340. As conexões entre o STM32 e o módulo conversor estão descritas no
exemplo do repositório https://github.com/BernardoLima92/STM32F103_UART_TIMER.

1. Configuração do Clock

![UART_Receive_Clock](https://user-images.githubusercontent.com/114233216/194179061-ef1d9092-edf9-4f3f-acb2-c1963d6c76da.png)

2. Configuração do UART

![UART_Receive_UART](https://user-images.githubusercontent.com/114233216/194179092-d50ae3aa-4e34-4a14-85aa-e143d1a917be.png)

3. Configuração do GPIO

![UART_Receive_GPIO](https://user-images.githubusercontent.com/114233216/194179105-5a1f4641-de68-4c4d-bff7-98f86f6e50e4.png)


4. Principais partes do código.

![UART_Receive_Code_00](https://user-images.githubusercontent.com/114233216/194179133-c3261943-c580-462c-99f0-a01b8e66181d.png)

![UART_Receive_Code_01](https://user-images.githubusercontent.com/114233216/194179156-97deb569-73ef-4a8e-bce2-51855cce4b9a.png)

![UART_Receive_Code](https://user-images.githubusercontent.com/114233216/194179164-7635b2be-dacb-4eb2-ac2a-0751536eef5a.png)



