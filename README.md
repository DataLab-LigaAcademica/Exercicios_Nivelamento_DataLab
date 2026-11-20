# 🐍 Exercícios de Nivelamento: DataLab

Listas de exercícios de **Python** do nivelamento da **DataLab Liga Acadêmica**, organizadas em notebooks Jupyter (`.ipynb`) e divididas por assunto e por nível de dificuldade.

---

> [!CAUTION]
> ### 🚫 NÃO faça `push` neste repositório
> Este repositório é o **gabarito em branco** usado por todo mundo. Se você enviar suas respostas para cá, vai apagar ou bagunçar a lista dos outros participantes.
>
> ✅ **Faça um _fork_** (uma cópia sua do repositório) e resolva os exercícios **no seu fork**. O passo a passo está logo abaixo.

---

## 📂 Estrutura do repositório

```text
Exercicios_Nivelamento_DataLab/
├── 01_Estrutura_Sequencial/
│   └── lista_01_estrutura_sequencial.ipynb
├── 02_Estrutura_de_Decisao/
│   └── lista_02_estrutura_de_decisao.ipynb
├── 03_Estrutura_de_Repeticao/
│   └── lista_03_estrutura_de_repeticao.ipynb
├── GUIA.md        ← guia detalhado: como resolver, erros comuns, Git
└── README.md      ← você está aqui
```

| Lista | Assunto | O que você vai praticar |
|:---:|---|---|
| **01** | Estrutura Sequencial | `input()`, `int()`/`float()`, operadores, f-strings, `math.ceil()` |
| **02** | Estrutura de Decisão | `if`/`elif`/`else`, comparações, `and`/`or`/`not` |
| **03** | Estrutura de Repetição | `for`, `range()`, `while`, `break`, acumuladores, listas |

Cada lista tem **9 exercícios**:

| Nível | Quantidade | O que esperar |
|:---:|:---:|---|
| 🟢 Fácil | 3 | Aplicação direta do conteúdo. Ótimo para aquecer. |
| 🟡 Médio | 3 | Exige combinar conceitos e prestar atenção nos detalhes. |
| 🔴 Difícil | 3 | Problemas maiores, com várias etapas. Planeje antes de codar! |

> 💡 **Faça as listas em ordem** (01 → 02 → 03). Cada uma usa o que foi aprendido na anterior.

---

## 🚀 Como começar (passo a passo)

### 1. Faça o fork

1. Entre na página deste repositório no GitHub: <https://github.com/DataLab-LigaAcademica/Exercicios_Nivelamento_DataLab>
2. Clique no botão **`Fork`** (canto superior direito).
3. Deixe o seu usuário como *Owner* e clique em **`Create fork`**.

Pronto! Agora existe uma cópia em `https://github.com/SEU-USUARIO/Exercicios_Nivelamento_DataLab`. **É nela que você vai trabalhar.**

### 2. Abra os exercícios (escolha uma opção)

<details>
<summary><b>Opção A: No seu computador (VS Code ou Jupyter)</b>, recomendada</summary>

<br>

**Pré-requisitos:** [Python 3](https://www.python.org/downloads/), [Git](https://git-scm.com/downloads) e um editor com suporte a notebooks: [VS Code](https://code.visualstudio.com/) com as extensões **Python** e **Jupyter**, ou o próprio Jupyter (`pip install notebook`).

```bash
# Clone o SEU fork (troque SEU-USUARIO pelo seu usuário do GitHub)
git clone https://github.com/SEU-USUARIO/Exercicios_Nivelamento_DataLab.git
cd Exercicios_Nivelamento_DataLab

# Abra no VS Code...
code .

# ...ou no Jupyter
jupyter notebook
```

Abra o arquivo `.ipynb` da lista e, se o editor pedir, selecione um **kernel Python**.

</details>

<details>
<summary><b>Opção B: No Google Colab</b>, sem instalar nada</summary>

<br>

1. Acesse <https://colab.research.google.com>.
2. Vá em **Arquivo → Abrir notebook → GitHub**.
3. Cole a URL do **seu fork** e escolha a lista.
4. Para salvar no GitHub: **Arquivo → Salvar uma cópia no GitHub**, escolhendo o **seu fork** como repositório.

</details>

### 3. Resolva e salve seu progresso no SEU fork

```bash
git add .
git commit -m "Resolve exercícios 01 a 03 da lista de estrutura sequencial"
git push origin main
```

> Como você clonou o **seu fork**, o `origin` aponta para ele e o `push` vai para a sua cópia. ✅
> Se o `git push` der erro de permissão, provavelmente você clonou o repositório original em vez do fork. Veja a seção *"Clonei o repositório errado"* no [GUIA.md](GUIA.md#-clonei-o-repositório-errado-e-agora).

---

## 📖 Guia de resolução

O arquivo **[GUIA.md](GUIA.md)** explica com calma:

- como usar o notebook (executar células, `input()`, reiniciar o kernel);
- um **método em 5 passos** para resolver qualquer exercício;
- os **erros mais comuns** de quem está começando e como corrigir;
- como **manter o seu fork atualizado** quando a lista ganhar novidades;
- comandos de Git que você vai usar no dia a dia.

**Leia o guia antes de começar a primeira lista!**

---

## 🤝 Regras de convivência

- ✍️ **Tente sozinho primeiro.** Abrir a dica faz parte do processo. Copiar a resposta pronta não ajuda você a aprender.
- 💬 **Dúvidas são bem-vindas.** Pergunte nos canais da liga. Explique o que tentou e mostre o erro que apareceu.
- 🐛 **Achou um erro no enunciado?** Abra uma [*Issue*](https://github.com/DataLab-LigaAcademica/Exercicios_Nivelamento_DataLab/issues) descrevendo o problema. Não altere este repositório diretamente.
- 🔒 **Nada de `push` ou *Pull Request* com suas respostas aqui.** Elas ficam no seu fork.

---

<p align="center">Feito com 💙 pela <b>DataLab Liga Acadêmica</b>. Bons estudos!</p>
