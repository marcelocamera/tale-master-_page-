---
layout: post
title: "FS2020 - Configurações Gráficas e Performance"
author: "Marcelo"
comments: true
tags: flight-simulator
---
Preparei uma análise do do impacto visual e de desempenho de cada configuração do Microsoft Flight Simulator 2020. Passados mais de 6 meses depois do lançamento dessa versão do Flight Simulator, ainda existem dúvidas quanto ao melhor setup para extrair a melhor configuração visual.

Este guia deve ajudá-lo a tomar decisões sobre o impacto visual em relação ao impacto da CPU / GPU no simulador. Observe que hardwares diferentes podem ter respostas de desempenho diferentes para configurações individuais, mas o objetivo desse post deve ser o suficiente para lhe dar uma ideia geral.

## ANTI ALIASING (recomentado = TAA)

### O que é?

O anti-aliasing visa reduzir ou remover os efeitos do aliasing temporal que é causado pela baixa taxa de amostragem (ou seja, número de quadros por segundo) de uma cena, que quando é baixa em comparação com a velocidade da cena faz com que os objetos apareçam em um local, em vez de dar a impressão de se mover suavemente em sua direção. Para evitar esse aliasing completamente, a taxa de amostragem de uma cena deve ser pelo menos duas vezes mais alta que o objeto mais rápido em movimento.

No FS2020 existem 3 opções de filtros anti-aliasing:
* **FXAA** (Fast approximate anti-aliasing) - A principal vantagem dessa técnica é que ela não requer grande capacidade computacional. Ele consegue isso suavizando bordas irregulares e indesejáveis chamadas de "jaggies" assim que elas aparecem na tela, ao invés de analisar o próprio modelo 3D como um todo.
* **DLAA** (Directionally Localized Anti Aliasing) - Ela reduz o número de "jaggies" analisando o modelo 3D como um todo. A principal desvantagem é requerer um maior poder computacional quando associada a objetos em movimento rápido.
* **TAA** (Temporal Anti-Aliasing) - Remove completamente os "jeggies" em objetos em movimento. Requer grande capacidade computacional.

### Quais os impactos?
* **Na CPU**
  * Não observado impactos na CPU.
* **Na GPU**
  * Off - 22,7 FPS
  * FXAA, DLAA - 22,3 FPS (redução de 1,7%)

## TERRAIN LEVEL OF DETAIL (recomendado = 100)

### O que é?
Determina a distância de visão geral e o nível de qualidade dos objetos no solo em uma cena. Essa configuração tem o maior efeito individual no desempenho do jogo.

### Quais os impactos?
* **Na CPU**
  * 10 - 105 FPS
  * 100 - 81 FPS (redução de 30%)
  * 200 - 68,5 FPS (redução de 53%)
* **Na GPU**
  * 10 - 24,2 FPS
  * 100 - 22,1 FPS (redução de 10%)
  * 200 - 21,4 FPS (redução de 13%)

## TERRAIN VECTOR DATA (recomendado = Ultra)
### O que é?
Determina a qualidade do mosaico usado como base para construção de margens de estradas, lagos, rios, montanhas e etc.

### Quais os impactos?
Não foram ainda determinados.

## BUILDINGS (recomendado = Ultra para CPUs High End, Medium para CPUs Low End)
### O que é?
Determina o nível de qualidade geral das estruturas e construções criadas na superfície (prédios, casas, torres, pontes, viadutos e etc.)
### Quais os impactos?
* **Na CPU**
  * Low - 64.5 FPS
  * Medium - 61 FPS (redução de 6%)
  * High - 60 FPS (redução de 7,5%)
  * Ultra - 59 FPS (redução de 9%)
* **Na GPU**
  * Low - 24,6 FPS
  * Medium - 22,7 FPS (redução de 8%)
  * High - 22,4 FPS (redução de 10%)
  * Ultra - 21,4 FPS (redução de 15%)

O principal impacto é na sintetização dos edifícios. Em Low os edifícios são muito básicos, se parecem com caixas pintadas, são muito básicos. Em Medium, há a adição de mais formas nos edifícios adiciona forma e mais detalhes nos edifícios.
Em High e Ultra há uma melhora no sombreamento dos edifícios.

## TREES (recomendado = Medium para CPUs High End, Low para CPUs Low End)
### O que é?
Determina o nível geral de qualidade das árvores 3D que são colocadas na paisagem.
### Quais os impactos?
* **Na CPU**
  Sem impactos na CPU.
* **Na GPU**
  * Low - 21,3 FPS
  * Medium - 19,5 FPS (redução de 9%)
  * High - 18,5 FPS (redução de 15%)
  * Ultra - 18 FPS (redução de 18%)

Configurações baixas tem maior contraste, aparecendo nas texturas das árvores dando a impressão de serem objetos planos. Configuração média faz com que as árvores pareçam significativamente mais exuberantes e 3D, e corrige um pouco o problema de contraste. Configuração ultra parece ter uma densidade de árvores ligeiramente maior do que média.

## GRASS AND BUSHES (recomendado = High)
### O que é?
Determina a qualidade geral dos modelos 3D de gramas e arbustos espalhados pela paisagem.

### Quais os impactos?
* **Na CPU**
  Sem impactos na CPU.
* **Na GPU**
  * Off - 26 FPS
  * Low - 25,3 (redução de 3%)
  * Medium - 25 FPS (redução de 4%)
  * High - 24 FPS (redução de 8%)
  * Ultra - 23 FPS (redução de 13%)

A densidade e a distância de renderização da grama mudam conforme as configurações aumentam, isto é, surgem mais gramas e arbustos quanto maior for a configuração.

## OBJECTS LEVEL OF DETAILS (recomendado = 100)
### O que é?
Determina a qualidade visual de objetos como veículos ou adereços aleatórios encontrados em aeroportos maiores ou outras estruturas. Ele controla a distância de renderização do nível de detalhe de vários objetos do tráfego.

### Quais os impactos?
* **Na CPU**
  * 10 - 79 FPS
  * 100 - 67 (redução de 18%)
  * 200 - 65 FPS (redução de 21,5%)
* **Na GPU**
  Sem impactos na CPU.

## VOLUMETRIC CLOUDS (recomendado = Medium para CPUs low end, High para CPUs mid range ou Ultra para CPUs high end)
### O que é?
Determina a qualidade visual das nuvens, incluindo como elas projetam suas sombras e como a luz passa por elas.

### Impactos
* **Na CPU**
  * Sem impactos na CPU.
* **Na GPU**
  * Low - 22,7
  * MEDIUM - 21,7 FPS (redução de 4,5%)
  * HIGH - 20,5 FPS (redução de 11%)
  * ULTRA - 18,4 FPS (redução de 23%)

### Meus comentários...
Afeta principalmente a resolução da nuvem, nível Low apresenta nuvens terríveis, o nível MEDIUM são o início do aceitável, níveis HIGH e ULTRA são onde as nuvens realmente brilham.

## TEXTURE RESOLUTION (recomendado = ULTRA)
### O que é?
Determina a qualidade geral da textura em uma cena para objetos como pistas, sujeira, etc.
### Impactos
* **Na CPU**
  * Sem impactos na CPU.
* **Na GPU**
  * Sem impactos na GPU.

### Meus comentários...
Esta configuração não parece afetar a qualidade da própria aeronave usando a visualização da cabine ou câmeras externas. Em configurações Low as imagens parecem ligeiramente borradas, em configurações mais elevadas a textura é mais nítida.

## ANISOTROPIC FILTERING (recomendado = 16x)
### Definição
Alterna a filtragem anisotrópica. Essa configuração pode melhorar a qualidade das texturas, mas se torna menos perceptível à distância.
### Impactos
* **Na CPU**
  * Sem impactos na CPU.
* **Na GPU**
  * Off - 23,7
  * 4x - 23,3 FPS (redução de 2%)
  * 16x - 21,9 FPS (redução de 8%)

### Comentários
  Remove a percepção de falta de foco (blur).

---

## TEXTURE SUPERSAMPLING (recomendado = 8x8)
### Definição
Permite a redução da resolução de texturas para aumentar a qualidade percebida. Níveis mais altos podem estender a distância em que a configuração de Filtragem Anisotrópica funciona. Parece não funcionar se a Filtragem Anisotrópica estiver desativada.
### Impactos
  * **Na CPU**
    * Sem impactos na CPU.
  * **Na GPU**
    * Off - 22,3
    * 2x2 - 22,2 FPS (redução de 0,05%)
    * 4x4 - 22 FPS (redução de 1%)
    * 8x8 - 21,4 FPS (redução de 4%)

### Comentários
As texturas do solo à distância tornam-se mais nítidas, claras e suaves à medida que a configuração aumenta. Remove a percepção de falta de foco (blur).

---

## TEXTURE SYNTHESIS (recomendado = ULTRA)
### Definição
Determina a qualidade geral das texturas sintetizadas.
### Impactos
  * **Na CPU**
    * Low - 40 FPS
    * Ultra - 38 FPS (redução de 5%)
  * **Na GPU**
    * Sem impactos na GPU.

### Comentários
Esta configuração parece aumentar o detalhe das texturas do cenário, mais notadamente à distância.

---

## WATER WAVES (recomendado = MEDIUM)
### Definição
Determina a qualidade da simulação da superfície da água.
### Impactos
  * **Na CPU**
    * Sem impactos na CPU.
  * **Na GPU**
    * Low - 25,4 FPS
    * Medium - 24,3 FPS (redução de 4,5%)
    * High - 23,5 FPS (redução de 8%)

### Comentários
Níveis mais altos oferecem a ilusão de um movimento mais dinâmico da água e mais pontos de reflexão de luz.

---

## SHADOW MAPS (recomendado = 1536)
### Definição
Determina a resolução das sombras projetadas por objetos complexos (principalmente aeronaves).
### Impactos
  * **Na CPU**
    * Sem impactos na CPU.
  * **Na GPU**
    * 768 e 1024 - 25,5 FPS
    * 1536 - 25,1 FPS (redução de 1,5%)
    * 2048 - 24,8 FPS (redução de 3%)

### Comentários
Níveis mais altos podem oferecer sombras mais nítidas que diminuem conforme você ganha altitude.

---

## TERRAIN SHADOW (recomendado = 512)
### Definição
Permite que o terreno projete sombras sobre si mesmo.
### Impactos
  * **Na CPU**
    * Sem impactos na CPU.
  * **Na GPU**
    * Off - 32 FPS
    * 128 - 31,3 FPS (redução de 2%)
    * 256 - 31,2 FPS (redução de 2,5%)
    * 512 - 30,9 FPS (redução de 3,5%)
    * 1024 - 29,7 FPS (redução de 8%)
    * 2048 - 27,2 FPS (redução de 17,5%)

### Comentários
Níveis mais altos oferecem simulação mais realista. Mais perceptível ao amanhecer e ao anoitecer, quando os raios do sol atingem as montanhas.

---
