[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

Esta atividade serve para mapear o que você já domina sobre linguagens formais, autômatos, gramáticas e computabilidade.

Responda individualmente. Use suas palavras. Se usar IA depois da primeira tentativa, registre o uso na seção 7.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- alfabeto: lembro bem
- cadeia: lembro bem
- linguagem: lembro bem
- gramática: lembro bem
- autômato finito: lembro parcialmente
- linguagem regular: lembro parcialmente
- linguagem livre de contexto: lembro parcialmente
- linguagem sensível ao contexto: lembro parcialmente
- linguagem irrestrita: não lembro
- hierarquia de Chomsky: lembro parcialmente
- computabilidade: lembro parcialmente
- máquina de Turing: lembro parcialmente

## 2. Definições com exemplo

Explique, com suas palavras e com um exemplo simples, usando o alfabeto `Sigma = {a, b}`.

1. O que é um alfabeto?
  Um alfabeto é conjunto finito de símbolos
  ex: alfabeto Sigma = _{a,b}_. Símbolos do alfabeto: _a e b_.
3. O que é uma cadeia?
  Uma cadeia é uma sequência de símbolos gerados com base em um alfabeto e que compõem uma linguagem.
4. O que é uma linguagem?
  Uma coleção, conjunto de cadeias sobre um alfabeto
5. O que é uma gramática?
  Uma gramática equivale a um conjunto de regras de definições para a formatação e formatação de cadeias para alguma linguagem

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. escreva três palavras que pertencem à linguagem;
  - L1: 01, 001, 101
  - L2: ab, aabb, aaabbb
  - L3: abc, aabbcc, aaabbbccc
2. escreva duas palavras que não pertencem;
  - L1: 0, 1
  - L2: ba, bbaaa
  - L3: ac, cc
3. diga, se souber, em qual classe ela provavelmente se encaixa;
  L1 - Linguagens regulares
  L1 - Linguagens regulares
  L1 - Linguagens regulares
4. explique o motivo em linguagem simples.
  L1 - Pode ser reconhecida por um AFD sem problemas através do funcionamento dos estados, então é Regular e Formal
  L2 - problemas de contagem de itens iguais são trabalhosos para AFDs, então acredito que não seja regular, talvez um nível acima.
  L3 - deve se encaixar na mesma lógica de L2

Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

## 4. Autômato finito

Considere o autômato abaixo, sobre o alfabeto `{0,1}`:

```text
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
```

Responda:

1. Qual linguagem esse autômato parece reconhecer?
  L = { w em {0,1} | w termina com 01}, fora desse padrão ele tende a sair do estado q2, que acredito ser o de aceitação
2. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
   - `01` **(Aceita)**
   - `101` **(Aceita)**
   - `100` **(Rejeita)**
   - `1101` **(Aceita)**
   - `111` **(Rejeita)**
3. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.
_Não consegui fazer a tabela em markdown, então tentei explicar a lógica pelas funções de transição_
Notações: R (Right/Direta) e L (Left/Esquerda) - movimentos do máquina
  cadeia _01_:
  (q0, 0, R) -> (q1, 0)
  (q0, 1, R) -> (q2, 1)
  cadeia _101_:
  (q0, 1, R) -> (q0, 1)
  (q0, 0, R) -> (q1, 0)
  (q1, 1, R) -> (q2, 1)

## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.
  ab, aab, aaab, aaaab, aaaaab
2. Descreva a linguagem em palavras.
   L = { l em {a,b} | termina em b}
   linguagem de cadeias que começam com a e terminam com b
4. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.
  Essa gramática parece ser regular, pois acredito que seja linear à Direita e, por definição
  > Toda Gramática Regular é uma Gramática Linear
  [UNESP](https://wwwp.fc.unesp.br/~simonedp/zipados/TC02.pdf)

## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva:


1. o que você entende dele;
  ### _Tópico escolhido - Máquinas de Turing_
    Uma máquina de Turing é um modelo teórico matemático que ajudou e ajuda a avaliar a capacidade de computadores resolverem problemas.
    Composto por uma fita de memória/entrada inifita, um mecanismo para leitura/escrita e apagamento, ele consegue, em teoria, resolver qualquer problema que possa ser resolvido algoritmicamente 
2. onde você se confunde;
  Não sei como essa ideia funciona direito na prática:
    Como a máquina sabe a hora de parar?
    Como os dados são convertidos pors 0s e 1s
    Como se comporta uma MT geral
4. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.
  Desenhos e analogias para entender melhor visulamente

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:
Não utilizei IA, mas consultei esses PDFs como fonte:
[IME_USP](https://www.ime.usp.br/~jef/tc_gramaticas.pdf)
[UNESP](https://wwwp.fc.unesp.br/~simonedp/zipados/TC02.pdf)
```text
Pergunta feita:
Resumo da resposta:
Como eu verifiquei:
O que eu alterei na minha resposta:
O que ainda não entendi:
```

## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório:
Commit final:
Autoavaliação: nível atual, maior dificuldade e tópico que precisa ser retomado.
```
