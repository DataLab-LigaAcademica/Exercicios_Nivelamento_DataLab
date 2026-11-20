# 📖 Guia de Resolução dos Exercícios

Este guia é para quem vai resolver as listas de nivelamento. Leia uma vez antes de começar e volte aqui sempre que travar.

## Sumário

1. [Antes de tudo: o fluxo de trabalho](#1-antes-de-tudo-o-fluxo-de-trabalho)
2. [Como usar o notebook](#2-como-usar-o-notebook)
3. [Como cada exercício está organizado](#3-como-cada-exercício-está-organizado)
4. [Método em 5 passos para resolver qualquer exercício](#4-método-em-5-passos-para-resolver-qualquer-exercício)
5. [Erros comuns (e como corrigir)](#5-erros-comuns-e-como-corrigir)
6. [Git e GitHub no dia a dia](#6-git-e-github-no-dia-a-dia)
7. [Perguntas frequentes](#7-perguntas-frequentes)

---

## 1. Antes de tudo: o fluxo de trabalho

```text
   Repositório da DataLab                    Seu fork (sua cópia)                 Seu computador
 ┌──────────────────────────┐   Fork    ┌──────────────────────────┐   clone   ┌──────────────────┐
 │ DataLab-LigaAcademica/   │ ────────► │ SEU-USUARIO/             │ ────────► │ pasta local      │
 │ Exercicios_Nivelamento   │           │ Exercicios_Nivelamento   │ ◄──────── │ (você resolve    │
 │                          │           │                          │   push    │  aqui)           │
 │ 🚫 NÃO faça push aqui    │           │ ✅ suas respostas ficam  │           │                  │
 └──────────────────────────┘           │    aqui                  │           └──────────────────┘
                                        └──────────────────────────┘
```

- O **repositório da DataLab** é a lista em branco, igual para todo mundo. **Ninguém resolve nele.**
- O **fork** é a sua cópia no GitHub. É lá que suas respostas ficam salvas.
- O **clone** é a cópia do seu fork no seu computador, onde você realmente escreve o código.

O passo a passo do fork está no [README](README.md#-como-começar-passo-a-passo).

---

## 2. Como usar o notebook

Um notebook Jupyter (`.ipynb`) é formado por **células**:

- **Células de texto (Markdown):** enunciados, exemplos e dicas. Você não precisa mexer nelas.
- **Células de código:** é aqui que você escreve e executa Python.

| Ação | Como fazer |
|---|---|
| Executar a célula e ir para a próxima | `Shift + Enter` |
| Executar e continuar na mesma célula | `Ctrl + Enter` |
| Interromper um programa travado (ex.: laço infinito) | Botão **■ Interrupt** / **Interromper** |
| Começar do zero (apaga todas as variáveis) | **Restart** / **Reiniciar kernel** |

### Sobre o `input()` no notebook

Quando o código chega em um `input()`, o notebook mostra uma **caixa de texto**. No VS Code ela aparece no **topo da janela**. No Jupyter e no Colab, aparece **logo abaixo da célula**. Digite o valor e aperte `Enter`.

> ⚠️ Enquanto a caixa estiver esperando, a célula fica "rodando" (aparece `[*]`). Se você executar outra célula nesse meio tempo, ela fica na fila. Responda o `input()` ou interrompa a execução.

### Cada exercício é independente

Escreva cada solução **completa** na sua própria célula, com todos os `input()` e `import` necessários. Assim, qualquer pessoa consegue executar qualquer exercício sem depender das células anteriores.

---

## 3. Como cada exercício está organizado

```text
## Exercício 04 🟡 — Salário com descontos     ← número, nível e título
Enunciado...                                    ← o que o programa deve fazer
Exemplo de execução                             ← o que aparece no terminal
💡 Dica (clique para abrir)                     ← use se travar
[ célula de código vazia ]                      ← sua solução vai aqui
```

**Lendo o exemplo de execução:** as linhas com `:` seguido de um valor mostram o que o **usuário digitou**. O resto é o que o **programa mostrou**.

```text
Peso dos peixes (kg): 62.5     ← o programa perguntou, o usuário digitou 62.5
Excesso: 12.5 kg               ← o programa mostrou
Multa a pagar: R$ 50.00        ← o programa mostrou
```

> As mensagens **não precisam ser idênticas** às do exemplo. O que importa é a lógica e os resultados.

---

## 4. Método em 5 passos para resolver qualquer exercício

### Passo 1: Entenda o problema
Leia o enunciado **duas vezes**. Sublinhe mentalmente os números e as regras (porcentagens, limites, "inclusive", "acima de"...).

### Passo 2: Separe Entrada → Processamento → Saída

| Pergunta | Exemplo (pescador João) |
|---|---|
| **Entrada:** o que o usuário informa? | o peso dos peixes |
| **Processamento:** que contas/decisões o programa faz? | excesso = peso − 50 (mínimo 0); multa = excesso × 4 |
| **Saída:** o que o programa mostra? | o excesso e a multa |

### Passo 3: Escreva o plano em português (comentários)

```python
# 1. ler o peso
# 2. calcular o excesso (nunca negativo)
# 3. calcular a multa
# 4. mostrar os resultados
```

### Passo 4: Transforme cada linha do plano em código
Faça **um pedaço de cada vez** e execute com frequência. Use `print()` para conferir valores no meio do caminho.

### Passo 5: Teste
1. Teste com os **valores do exemplo**. A saída bate?
2. Teste **casos extremos**: zero, números negativos, valores iguais, o valor exato de um limite (ex.: salário de exatamente R$ 280,00).
3. Só abra a 💡 dica depois de tentar de verdade.

---

## 5. Erros comuns (e como corrigir)

### ❌ Comparar ou somar números que ainda são texto

```python
a = input('Número: ')   # o usuário digita 10
b = input('Número: ')   # o usuário digita 9
print(a + b)            # '109'  → juntou os textos!
print(a > b)            # False  → comparou texto, '1' vem antes de '9'
```

✅ **Correção:** converta com `int(input(...))` ou `float(input(...))`.

### ❌ `ValueError: invalid literal for int()`
Você usou `int()` e o usuário digitou um valor com casas decimais (`7.5`) ou um texto. Use `float()` quando o valor puder ter casas decimais.

> 🇧🇷 Atenção: o Python usa **ponto** como separador decimal. Digite `7.5`, e não `7,5`.

### ❌ `IndentationError` / código "fora" do `if` ou do laço
O Python usa a **indentação** (4 espaços) para saber o que está dentro de cada bloco.

```python
if nota >= 7:
print('Aprovado')        # ❌ IndentationError

if nota >= 7:
    print('Aprovado')    # ✅
```

### ❌ Usar `=` no lugar de `==`
`=` **guarda** um valor; `==` **compara** dois valores. `if x = 5:` dá erro de sintaxe.

### ❌ Ordem errada das condições

```python
if media >= 7:
    print('Aprovado')
elif media == 10:                    # ❌ nunca chega aqui: 10 já é >= 7
    print('Aprovado com Distinção')
```

✅ Teste primeiro a condição **mais específica**.

### ❌ Laço infinito
Se a célula fica rodando para sempre, a condição do `while` nunca ficou falsa. Interrompa (**■**) e confira se a variável da condição muda **dentro** do laço.

### ❌ `range()` "parando antes"
`range(1, 10)` vai de 1 até **9**. Para incluir o 10, use `range(1, 11)`.

### ❌ `NameError: name 'x' is not defined`
A variável não existe ainda: erro de digitação, ou você está usando algo de outra célula que não foi executada (ou o kernel foi reiniciado). Deixe cada exercício completo na própria célula.

### ❌ Resultado com muitas casas decimais (`0.30000000000000004`)
É normal: computadores representam decimais de forma aproximada. Para exibir, formate: `f'{valor:.2f}'`.

---

## 6. Git e GitHub no dia a dia

### Salvar seu progresso

```bash
git status                       # vê o que mudou
git add .                        # prepara todas as mudanças
git commit -m "Resolve lista 02, exercícios 1 a 5"
git push origin main             # envia para o SEU fork
```

> 💡 Faça commits **pequenos e frequentes**, com mensagens que digam o que você fez.
> 💡 Antes do commit, salve o notebook (`Ctrl + S`). Se não salvar, as mudanças não entram no commit.

### Manter seu fork atualizado com a lista original

Se a DataLab corrigir um enunciado ou adicionar uma lista nova, você pode trazer essas mudanças para o seu fork:

**Pelo site (mais fácil):** na página do seu fork, clique em **`Sync fork` → `Update branch`** e depois rode `git pull` no seu computador.

**Pelo terminal:**

```bash
# só na primeira vez: cadastra o repositório original como "upstream"
git remote add upstream https://github.com/DataLab-LigaAcademica/Exercicios_Nivelamento_DataLab.git

# sempre que quiser atualizar
git fetch upstream
git merge upstream/main
git push origin main
```

> `origin` = **seu fork** (pode dar push) · `upstream` = **repositório da DataLab** (só para baixar, **nunca** dê push)

Confira com `git remote -v`:

```text
origin    https://github.com/SEU-USUARIO/Exercicios_Nivelamento_DataLab.git (push)    ✅
upstream  https://github.com/DataLab-LigaAcademica/Exercicios_Nivelamento_DataLab.git  🚫 não dê push
```

### 🆘 Clonei o repositório errado, e agora?

Se `git remote -v` mostra `DataLab-LigaAcademica` como `origin`, você clonou o original. Para corrigir **sem perder seu trabalho**:

```bash
# 1. Faça o fork pelo site (se ainda não fez)
# 2. Aponte o origin para o SEU fork:
git remote rename origin upstream
git remote add origin https://github.com/SEU-USUARIO/Exercicios_Nivelamento_DataLab.git
git push -u origin main
```

---

## 7. Perguntas frequentes

**Preciso fazer todos os exercícios?**
O ideal é fazer todos, em ordem. Se o tempo estiver curto, garanta pelo menos os 🟢 fáceis e os 🟡 médios de cada lista.

**Posso usar coisas que ainda não foram ensinadas (listas, funções...)?**
Pode, mas o objetivo é treinar o assunto da lista. Tente primeiro só com o conteúdo daquela lista e da anterior.

**Minha saída não ficou igual à do exemplo. Está errado?**
Não necessariamente. Textos e formatação podem variar. Os **valores** e a **lógica** é que precisam estar corretos.

**Posso usar IA ou procurar a resposta na internet?**
Para tirar uma dúvida pontual (o que faz `range()`? por que esse erro?), tudo bem. Para pedir a solução pronta, não: você perde justamente o treino que o nivelamento quer dar. Tente, erre, depure. É assim que se aprende a programar.

**Encontrei um erro em um enunciado. O que faço?**
Abra uma *Issue* no repositório da DataLab explicando o problema. Não envie correções direto para o repositório original.

**O notebook não encontra o Python / pede para escolher um kernel.**
No VS Code, clique em **Select Kernel** (canto superior direito) e escolha uma instalação do Python 3. Se não aparecer nenhuma, instale a extensão **Jupyter** e confirme que o Python está instalado (`python --version` no terminal).

---

<p align="center">Bons estudos! Qualquer dúvida, chame a galera da <b>DataLab</b>. 💙</p>
