# Projeto: Controle de LEDs, Display OLED e Comunicação Serial com RP2040

## Descrição Geral
Este projeto tem como objetivo demonstrar o uso do microcontrolador RP2040 para controle de LEDs comuns e endereçáveis WS2812, exibição de informações em um display OLED SSD1306 via I2C e entrada de caracteres através da comunicação serial UART.

## Funcionalidades Implementadas

- **Controle de LEDs:** LEDs comuns (GPIOs 11 e 12) e matriz de LEDs WS2812 (GPIO 7).
- **Exibição no Display OLED:** Exibição de informações sobre o estado dos LEDs e comandos recebidos via UART.
- **Botões com Interrupções e Debounce:**
  - **Botão A (GPIO 5):** Alterna o estado do LED verde e atualiza o display.
  - **Botão B (GPIO 6):** Alterna o estado do LED azul e atualiza o display.
- **Comunicação Serial UART:**
  - Entrada de caracteres via PC.
  - Exibição dos caracteres recebidos no display OLED.
  - Controle da matriz de LEDs WS2812 conforme o número digitado.

## Componentes Utilizados

- **Microcontrolador:** RP2040 (BitDogLab)
- **Matriz de LEDs WS2812:** Conectada à GPIO 7
- **LEDs comuns:** Conectados às GPIOs 11 e 12
- **Botões:** A (GPIO 5), B (GPIO 6)
- **Display OLED SSD1306:** Conectado via I2C (GPIO 14 e 15)

## Requisitos do Sistema

1. **Interrupções GPIO:** Os botões são gerenciados com interrupção para alternar os LEDs.
2. **Debounce por Software:** Implementado para evitar leituras incorretas dos botões.
3. **Exibição no Display OLED:** Atualiza o estado dos LEDs e exibe caracteres recebidos via UART.
4. **Controle de LEDs:** LEDs comuns e WS2812 controlados dinamicamente.
5. **Comunicacao Serial UART:** Entrada de caracteres e controle remoto via PC.

## Como Executar o Projeto

### 1. Compilar e Carregar o Firmware
- Utilize o **VS Code** com a extensão para Raspberry Pi Pico e SDK configurado.
- Compile o código e gere o arquivo `.uf2`.
- Conecte a placa BitDogLab ao PC em modo BOOTSEL.
- Copie o arquivo `.uf2` para a unidade correspondente ao RP2040.

### 2. Teste e Depuração
- Abra o **Serial Monitor** no VS Code para monitorar a entrada de caracteres e logs do sistema.
- Pressione os botões A e B para testar a interação com os LEDs e display.
- Digite um número (0-9) no Serial Monitor e observe a matriz de LEDs WS2812 atualizar.

## Estrutura do Projeto

- `projeto_display.c` - Código principal: inicialização de pinos, interrupções e laço principal.
- `ssd1306.h/.c` - Biblioteca para comunicação com o display OLED via I2C.
- `ws2812.pio.h` - Biblioteca para controle dos LEDs WS2812.
- `font.h` - Fonte customizada para exibição de caracteres no display.
- `diagram.json` - Simulador WOKWI para testes virtuais.

## Observação
Os testes podem ser realizados tanto no hardware real quanto no simulador **WOKWI**, utilizando `diagram.json` para validação virtual antes da execução no dispositivo físico.

## Link do video 

(https://youtu.be/FpD6mXQGMQo?si=cgskC7u_tjA7bBdD)
## 👨‍💻 Autor
**Kauan Teixeira da Hora**

