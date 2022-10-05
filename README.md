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


_______________________________________________________________________________________________________________________________________
#include "main.h"
#include <string.h>

UART_HandleTypeDef huart1;

char recebido[10]; 	// buffer que armazena a string recebida.
char resp1[4] = {'n', 'e', 'x', 't'};
int ret;

void SystemClock_Config(void);
static void MX_GPIO_Init(void);
static void MX_USART1_UART_Init(void);

int main(void)
{
  HAL_Init();

  SystemClock_Config();

  MX_GPIO_Init();
  MX_USART1_UART_Init();

  while (1)
  {

	  HAL_UART_Receive(&huart1, recebido, 6, 100);
	  ret = strncmp(recebido, resp1, 4);

	  if (ret == 0){		// Se ret = 0 as duas strings são iguais.
		  HAL_GPIO_TogglePin(GPIOB, GPIO_PIN_5);
		  recebido[0] = 'a';
	  }

  }
}
_______________________________________________________________________________________________________________________________________
