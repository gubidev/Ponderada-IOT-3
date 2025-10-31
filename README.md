# Projeto: Semáforo com Arduino (POO)

Este projeto implementa um semáforo simples de três luzes (vermelho, amarelo, verde) utilizando um Arduino. A lógica de programação foi feita usando Programação Orientada a Objetos (POO).

## 1. Descrição

O objetivo é controlar um semáforo, alternando as luzes de acordo com uma temporização pré-definida. O código utiliza uma classe chamada `Semaforo` para encapsular toda a funcionalidade, e um ponteiro é usado no arquivo principal (`.ino`) para instanciar e gerenciar o objeto.

## 2. Componentes Necessários

* 1x Placa Arduino (UNO ou compatível)
* 1x Protoboard
* 1x Base LED
* 1x LED Vermelho
* 1x LED Amarelo
* 1x LED Verde
* 3x Resistores de 220Ω (ou 330Ω)
* Jumpers (fios de conexão)

## 3. Montagem (Conexões)

As conexões de hardware devem seguir o esquema abaixo, conforme definido nas constantes do código:

* **`PINO_LED_VERMELHO` (Porta 10):** Conectar o ânodo (pino longo) do LED vermelho a esta porta, através de um resistor.
* **`PINO_LED_AMARELO` (Porta 9):** Conectar o ânodo (pino longo) do LED amarelo a esta porta, através de um resistor.
* **`PINO_LED_VERDE` (Porta 8):** Conectar o ânodo (pino longo) do LED verde a esta porta, através de um resistor.
* **`GND` (Terra):** Conectar o cátodo (pino curto) de **todos** os LEDs ao pino `GND` do Arduino.

## 4. Lógica de Funcionamento

O programa executa um ciclo contínuo (`executarCiclo()`) que alterna entre os estados (luzes) do semáforo. A temporização de cada fase, definida na classe `Semaforo`, é:

1. **Vermelho:** Aceso por 6000 ms (6 segundos).
2. **Verde:** Aceso por 4000 ms (4 segundos).
3. **Amarelo:** Aceso por 2000 ms (2 segundos).

Após a luz amarela, o ciclo recomeça imediatamente com a luz vermelha.

## 5. Estrutura do Código

* **Classe `Semaforo`:** Contém todas as variáveis (pinos, tempos) e métodos (`vermelho`, `verde`, `amarelo`) para o funcionamento do semáforo.
* **`setup()`:** Função principal do Arduino que cria o objeto `Semaforo` (usando `new`) e chama `configurarPinos()` para definir os pinos como saídas.
* **`loop()`:** Função principal do Arduino que chama repetidamente `semaforo->executarCiclo()` para manter o semáforo em operação.
