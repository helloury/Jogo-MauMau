# 🎲 Trabalho: Mau-Mau
Este repositório contém a solução do problema **Diagonal 6**, desenvolvido como trabalho da disciplina de **Estrutura de Dados I**.  
O trabalho foi implementado integralmente em **C++**, utilizando Pilha, Fila, Lista circular duplamente encadeada com alocação dinâmica e ponteiros.

---

### 🕹️ O Jogo : 
- Temos muitas variações do jogo. Para o trabalho siga as regras abaixo.
    - Número de jogadores: de 2 a 10 jogadores.
    - Objetivo: Uma rodada termina quando um jogador descartar todas as cartas da mão. Ao final da rodada o jogador que tem maior número de pontos sai do jogo. Inicia uma nova rodada até que reste apenas um jogador, o vencedor.
    - 2 Baralhos (104 cartas).
- Pontuação:
  - A (ás) = 1 ponto
  - 2 (dois) = 2 pontos
  - 3 (três) = 3 pontos
  - 4 (quatro) = 4 pontos
  - 5 (cinco) = 5 pontos
  - 6 (seis) = 6 pontos
  - 7 (sete) = 7 pontos
  - 8 (oito) = 8 pontos
  - 9 (nove) = 9 pontos
  - 10 (dez) = 10 pontos
  - J (valete) = 11 pontos
  - Q (dama) = 12 pontos
  - K (rei) = 13 pontos

### 🚀 Iniciando o Jogo
  As cartas são embaralhadas e em seguida distribuídas 5 para cada jogador.
  O jogo começa em sentido horário, mas pode mudar no decorrer do jogo.
  O jogador, na sua vez, descarta uma carta do mesmo valor ou do mesmo número da que está no
  topo do lixo. Se o jogador não tem uma carta que pode ser jogada, ele compra uma carta do monte e tenta
  jogar. Se ainda não é possível ele passa a vez ao próximo.
  Quando o lixo estiver vazio (inicio de cada rodada) o jogador pode jogar qualquer carta.
  Quando a ultima carta do monte for comprada, um novo monte será formado empilhando cada carta
  desempilhada do lixo, exceto o topo do lixo (para que o jogador não perca a referência). Dessa forma o monte passa
  a ser o (antigo lixo – topo) invertido e o lixo fica somente com o antigo topo.
  
- Existe 3 tipos de cartas: estado, castigo e neutra.  
    - estado: Q (dama ou rainha) inverte a rotação, de horário para anti-horário e vice-versa.
    - castigo: A (ás) faz com que o próximo jogador não jogue, direcionando o jogo ao “próximo do próximo”.
    - 7 (sete) o próximo jogador compra 2 cartas.
    - 9 (nove) o jogador anterior compra 3 cartas.
    - neutra: todas as outras cartas. 
    
---

### 📝 Entrada do programa
- Um inteiro N que define a quantidade de partidas.
- Para cada partida é dado:
    - Um inteiro 1 < J < 11 que define a quantidade de jogadores.
    - 104 cartas já embaralhadas separadas por espaço. O nome de uma carta é formado por 2 caracteres: o primeiro
    caracter indica o valor da carta ('A' = às, 'B' = 2, 'C' = 3, ..., 'J' = 10, 'K' = Valete, 'L' = Dama, 'M' = Rei) e o segundo o
    naipe da carta ('0' = paus, '1' = copas, '2' = espada, '3' = ouro). Por exemplo, 'K0' refere-se à carta Valete de paus.
#### Exemplo de entrada
```
1
2
A0 B0 C0 D0 E0 F0 G0 H0 I0 J0 K0 L0 M0 A1 B1 C1 D1 E1 F1 G1 H1 I1 J1 K1 L1 M1 A2 B2 C2 D2 E2 F2 G2 H2 I2 J2 K2 L2
M2 A3 B3 C3 D3 E3 F3 G3 H3 I3 J3 K3 L3 M3 A0 B0 C0 D0 E0 F0 G0 H0 I0 J0 K0 L0 M0 A1 B1 C1 D1 E1 F1 G1 H1 I1 J1
K1 L1 M1 A2 B2 C2 D2 E2 F2 G2 H2 I2 J2 K2 L2 M2 A3 B3 C3 D3 E3 F3 G3 H3 I3 J3 K3 L3 M3
```
