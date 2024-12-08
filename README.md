# Introdução à Robótica: Eletricidade, Eletrônica e Arduino

## Apontamentos Importantes

- Todas as imagens devem ser fotografias tiradas pelos próprios alunos, utilizando os equipamentos disponíveis na Universidade. Isso evitará problemas legais relacionados a direitos autorais.
- Os diagramas devem ser construídos pelos alunos, utilizando ferramentas como Inkscape, Fritzing ou criando GIFs animados.
- Cada seção deve incluir suas próprias referências bibliográficas.

## 1. Fundamentos de Eletricidade

### Conceitos Básicos

#### Carga elétrica (202110272411)

#### Corrente elétrica (202110049611)

#### Tensão (201910402211)

**Conceito de Tensão elétrica (ou voltagem)**

	A tensão elétrica (ou voltagem) é diferença de potencial elétrico entre dois pontos de um circuito elétrico. Ela é a força que "empurra" os elétrons através do circuito, permitindo o fluxo de corrente elétrica. Em termos técnicos, a tensão mede a quantidade de energia por unidade de carga elétrica e é medida em volts(V).
	
	1. Definição: Em um circuito elétrico, a tensão representa a energia necessária para mover uma carga de um ponto a outro.

	2. Unidade de Medida: Volts(V), e a fórmula básica é V = I x R, onde:
		- V é a tensão,
		- I é a corrente (medida em amperes),
		- R é a resistência (medida em ohms).

	3. Importância para Circuitos de Robótica: A tensão é cruscial para garantir que os componentes eletrônicos (sensores, motores LEDs, etc.) recebam a quantidade certa de energia. no caso de projetos com Arduino, por exemplo, o microcontrolador e os componentes conectados geralmente operam com tensões bixas, como 5V ou 3.3V.

	4. Exemplo prático em Arduíno: Ao trabalhar com arduíno, entender a tensão é essencial, pois cada pino de saída possui um limite específico de tensão. Além disso, saber controlar a tensão evita o superaquecimento e danos aos componentes.

Comparação com a corrente

	Tensão é como a "força" que empurra as partículas carregadas pelo circuito, enquanto a corrente é o fluxo dessas partículas. Em uma analogia com água, tensão seria a pressão da água em um cano, enquanto a corrente seria o volume de água fluindo.
	

Aqui estão alguns exemplos para ilustrar como a tensão é utilizada em projetos práticos com Arduino:

---

#### **1. Alimentação do Arduino**
O Arduino é alimentado por uma tensão específica, dependendo do modelo:
- O Arduino Uno, por exemplo, pode ser alimentado:
  - Pela porta USB: fornece uma tensão de **5V**.
  - Pelo conector de entrada DC: aceita tensões entre **7V e 12V**.
- Internamente, ele possui reguladores para garantir que os circuitos operem a **5V** (ou **3.3V** em alguns modelos).

Se a tensão de entrada ultrapassar os limites recomendados, isso pode danificar o microcontrolador ou outros componentes.

---

#### **2. Controle de LEDs**

Os LEDs são comuns em projetos de Arduino, e a tensão é essencial para que eles funcionem corretamente:

![LEDs](https://cdn.instructables.com/ORIG/FX8/TKPT/JT2SKNZY/FX8TKPTJT2SKNZY.jpg?frame=1)

- A maioria dos LEDs requer uma tensão de **2V a 3.3V**, dependendo da cor.
- Quando conectados ao Arduino, é necessário usar resistores em série para limitar a corrente, evitando que a tensão excessiva queime o LED.

Exemplo de cálculo:
- Suponha que você tenha um LED vermelho (2V, 20mA) e esteja usando um pino do Arduino que fornece 5V. 
- O resistor necessário seria calculado assim:
  
  **R = ( V_fonte - V_LED ) / I = (5 - 2) / 0.02 = 150 Ohms**
 

---

#### **3. Motores e Servomotores**
Motores e servomotores geralmente exigem uma tensão maior do que o Arduino pode fornecer diretamente:

![LEDs](http://www.manelsoft.com/projects/project_images/arduino_servo_2.jpg)

- Motores DC simples podem precisar de **6V ou 12V** para operar de forma eficiente.
- Neste caso, é comum usar uma fonte de alimentação externa conectada a um driver de motor (como o L298N) para controlar a tensão e corrente fornecidas ao motor.
- O Arduino envia apenas sinais de controle para o driver, que fornece a tensão necessária ao motor.

---

#### **4. Sensores**
Muitos sensores populares no ecossistema do Arduino, como o DHT11 (sensor de temperatura e umidade) ou o HC-SR04 (sensor ultrassônico), operam com tensões específicas, geralmente **5V** ou **3.3V**.

![LEDs](https://universal-solder.ca/wp-content/uploads/2020/03/1824_1c07a19c-cac8-4643-82a7-8386e17f3b880.jpg)

- Usar a tensão errada pode resultar em leituras imprecisas ou danos permanentes ao sensor.
- Alguns sensores requerem divisores de tensão para reduzir a tensão de entrada, caso você esteja usando um microcontrolador de **3.3V** e o sensor opera em **5V**.

---

#### **5. Conversores de Tensão**
Às vezes, é necessário usar **conversores de tensão** para adaptar os níveis de tensão entre diferentes dispositivos:
- **Conversor Step-Down**: Reduz a tensão (por exemplo, de 12V para 5V) para alimentar o Arduino e outros componentes sensíveis.
- **Conversor Step-Up**: Eleva a tensão (por exemplo, de 5V para 9V) para alimentar motores ou dispositivos mais exigentes.

---

#### **6. Comunicação com Módulos Externos**
Alguns módulos (como o módulo WiFi ESP8266 ou ESP32) podem operar em **3.3V**, enquanto o Arduino Uno fornece sinais de 5V. Nesses casos:

![LEDs](https://thecustomizewindows.com/wp-content/uploads/2019/03/Base64-Encoding-on-ESP32-Arduino.png)

- É necessário usar um **divisor de tensão** ou **conversores de nível lógico** para adaptar os sinais, protegendo o módulo.

---



#### Resistência (202310053411)

### Lei de Ohm (202110048211)

### Circuitos em Série e Paralelo (201910351011)

### Referências

## 2. Eletrônica Básica

### Componentes Passivos

#### Resistores (202010358111)
Tipos, código de cores, aplicações

#### Capacitores (201410064011)
Tipos (cerâmico, eletrolítico, poliéster), capacitância, aplicações

#### Indutores (202110272211)
Tipos, indutância, aplicações

### Componentes Ativos

#### Diodos (201810051811)
Tipos (retificador, Zener, LED), curva característica, aplicações

#### Transistores (202110048111)
Tipos (BJT, FET), princípio de funcionamento, aplicações em chaveamento e amplificação

### Circuitos Integrados

#### Amplificadores Operacionais (202110050111)
Características, configurações básicas (inversor, não-inversor, somador)

#### Microcontroladores (202010357611)
Introdução, arquitetura básica, comparação com Arduino

### Sensores e Atuadores

#### Sensores (202110271811)
Tipos (temperatura, luz, proximidade), princípios de funcionamento

#### Atuadores (201910072711)
Motores DC, servomotores, motores de passo

### Referências

## 3. Introdução ao Arduino

### O que é Arduino? (202110048411)

### Hardware do Arduino

#### Placa Arduino (201910350611)

#### Pinos digitais e analógicos (202010077411)

#### Alimentação (202420657550)

### Software do Arduino

#### IDE do Arduino (202110047911)

#### Estrutura básica de um sketch (202110048311)

### Programação Básica

#### Variáveis e tipos de dados (202110272411)

#### Estruturas de controle (202110049611)

#### Funções (201910402211)

### Referências

## 4. Projetos Práticos com Arduino

### Controle de LED (202310053411)

### Leitura de Sensores (202110048211)

### Controle de Motores (201910351011)

### Referências
