# 🎓 My English Teacher

> Um professor de inglês particular que roda dentro do Claude, se configura para
> o **seu** nível e o **seu** objetivo, e **lembra de todas as aulas anteriores**.

Não é um chat solto onde você pede "me ensina inglês". É um curso de verdade:

- 🧠 Ele **lembra** o que você errou na aula passada e cobra de volta na próxima
- 📝 Monta uma **lição de casa em cima dos seus erros** — não exercício genérico
- 📊 Acompanha sua **evolução em números**, aula a aula
- 🎯 Se adapta ao seu nível: do **zero absoluto ao C2**

```
setup  →  start lesson  →  lição de casa  →  start lesson  →  ...
 5 min       50 min            ~25 min          50 min
```

---

## ⚡ O que você precisa

| | |
|---|---|
| 💳 | Conta paga do Claude (**Pro**, **Max** ou **Team**) com **Cowork** ou **Claude Code** |
| 📁 | Esta pasta salva em qualquer lugar do seu computador |
| ⏰ | De 25 a 90 minutos por aula, na frequência que der |

> ⚠️ **Não funciona no claude.ai comum.** O professor precisa **ler e escrever
> arquivos** na sua pasta — é assim que ele lembra das aulas. Sem isso, ele
> esquece tudo a cada conversa.

---

## 🚀 Começar (3 passos)

**1️⃣ Conecte a pasta**
Abra o app do Claude → clique em **Add folder** → escolha esta pasta.
*(No Claude Code: abra um terminal aqui e rode `claude`.)*

**2️⃣ Configure o professor**
Digite:
```
setup
```
Ele faz umas **10 perguntas** — seu nível, seu objetivo, quanto tempo você tem,
como você gosta de ser corrigido. Leva **5 minutos**.

> 🤔 **Não sabe seu nível?** Responda **"não sei"**. Ele faz três perguntas em
> inglês de dificuldade crescente e estima seu nível pelo que você **produziu** —
> não pelo que você acha que sabe.

**3️⃣ Comece a aula**
```
start lesson
```

Pronto. É isso. 🎉

---

## 💬 Comandos

| Comando | O que faz |
|---|---|
| `setup` | **Configura** (ou reconfigura) o professor |
| `start lesson` | **Dá a aula** |
| `briefing` | Gera o prompt para uma **aula por voz** 🎙️ |
| `intake` | **Arquiva** a transcrição de uma aula por voz |
| `progresso` | Mostra sua **evolução** até aqui 📊 |
| `ajustar` | Muda alguma **configuração** |

**Durante a aula**, se precisar:

`/nativo` explicação em português · `/harder` sobe a dificuldade ·
`/time` onde estamos · `/skip` pula o bloco · `end lesson` encerra agora

---

## 📚 Como é uma aula

Cinco blocos. Os tempos abaixo são de uma aula de **50 minutos** — em 25 ou 90
ele ajusta sozinho.

| | Bloco | Min | O que acontece |
|---|---|---|---|
| ☕ | **Aquecimento** | 0–06 | Conversa de verdade + revisão da lição de casa |
| 🔁 | **Retomada** | 06–14 | Seus **erros recorrentes**, treinados até saírem certos |
| 🎯 | **Principal** | 14–34 | O tema do dia. É aqui que a aula acontece |
| 🔬 | **Laboratório** | 34–44 | **Um** alvo de língua: uma estrutura, um registro |
| ✅ | **Fechamento** | 44–50 | **Você** resume a aula em inglês, ele dá o feedback |

### 🎚️ Ele corrige de acordo com o seu nível

Essa é a parte mais importante do sistema. Corrigir um iniciante como se fosse
avançado faz ele desistir; o contrário faz o avançado se entediar.

| Nível | Ele corrige | Você fala |
|---|---|---|
| **A0–A2** 🌱 | quase tudo, com jeito, modelando a frase certa | 40–50% |
| **B1–B2** 🌿 | o que quebra o sentido, o que se repete, o que soa estranho | 60–65% |
| **C1–C2** 🌳 | só o essencial — o trabalho vira **naturalidade e registro** | 70–75% |

### 📦 No fim de cada aula ele gera

- 📄 **`aulas/Aula3.md`** — o registro completo: tudo que foi falado, todas as
  correções, vocabulário novo e suas notas de 1 a 5
- 🎮 **`homework/Aula3-homework.html`** — lição de casa **interativa**, feita em
  cima dos **seus** erros daquele dia. Abre no navegador, corrige sozinha, e tem
  um botão que copia suas respostas para você colar na aula seguinte
- 📈 **O próximo plano** — a aula seguinte já sai planejada

---

## 🎙️ Aula por voz (conversa por áudio)

Aqui está **a parte que confunde todo mundo** — leia com calma.

Existem **dois lugares diferentes dentro do mesmo app do Claude**:

| | 🗂️ **Cowork** | 💬 **Conversa normal** |
|---|---|---|
| Enxerga sua pasta? | ✅ **Sim** | ❌ Não |
| Tem modo de voz? | ❌ Não | ✅ **Sim** |
| Serve para | gerar o briefing e **arquivar** a aula | **ter a aula falada** |

**Nenhum dos dois faz as duas coisas.** É por isso que existe o vai-e-volta
abaixo — não é firula, é limitação do produto.

### 1️⃣ No Cowork, gere o briefing

Com a pasta conectada, digite:
```
briefing
```

> 📌 **Atenção:** ele **grava um arquivo** chamado `NEXT-LESSON-BRIEFING.md`
> dentro da pasta. **Não aparece nada na tela para copiar.** Abra esse arquivo
> e copie o trecho entre `BEGIN` e `END`.

### 2️⃣ Numa conversa normal, tenha a aula

Abra um **chat comum** do Claude (pode ser no celular) → **cole** o texto →
mande → clique no **ícone de onda sonora** 🔊 → **fale por 50 minutos**.

> 💡 **Por que o briefing é tão longo?**
> Porque aquele chat **não sabe nada sobre você**: não vê a sua pasta, não vê as
> aulas passadas, não vê nada. **O briefing É o contexto** — é a única coisa que
> ele vai saber. Depois de colado, o modo de voz **continua a mesma conversa** e
> enxerga tudo que você colou. ✅

### 3️⃣ De volta no Cowork, arquive

Digite `intake` e cole o relatório da aula.

> 📋 **De onde sai esse relatório?**
> No fim da aula o professor gera um bloco chamado **`LESSON REPORT`** — com as
> correções, notas de pronúncia, vocabulário novo, suas notas e o plano da
> próxima aula. Ele vem **dentro de um bloco de código**, então é **um clique no
> botão de copiar**. 🖱️
>
> **Você NÃO precisa copiar a conversa inteira.**
> Se ele esquecer de gerar, é só pedir: `give me the lesson report`

Ele então gera o registro da aula, a lição de casa e o **próximo briefing**. 🔄

### ❓ Dá pra começar já pela voz?

**Sim.** Do **B1 pra cima** é até melhor — é falando que a lacuna real aparece.
A Aula 1 sai como **diagnóstico** e o professor estima seu nível **falado** de
ouvido (normalmente uma faixa **abaixo** do escrito — quem escreve em B2 costuma
falar em B1). Isso é informação, não fracasso.

> 🌱 **Exceção:** se você está **começando do zero (A0–A2)**, faça as **três
> primeiras aulas por escrito**. Colar um prompt de 900 palavras em inglês e ser
> respondido em inglês falado é o jeito mais rápido de desistir. Da quarta em
> diante, a voz vira a melhor parte do curso.

---

## 🛠️ Personalizar

Tudo que define o professor está em **texto**, na pasta `instructions/`.
Três jeitos de mudar:

### 💬 1. Falando com ele *(o mais fácil)*

Durante ou depois da aula, é só dizer:

> *"corrige menos, tá me travando"*
> *"quero aulas de 25 minutos"*
> *"meu foco mudou, tenho entrevista em duas semanas"*

Ele atualiza os arquivos sozinho. Ou digite `ajustar`.

### 🔄 2. Rodando `setup` de novo

Mudou de nível, de objetivo ou de vida? Rode outra vez — ele reescreve seu
perfil **sem apagar suas aulas**. O histórico continua lá.

### ✏️ 3. Editando os arquivos na mão

| Quero mudar… | Edite… |
|---|---|
| Meu perfil, nível, objetivo, tom | `instructions/01-student-profile.md` |
| Tempos dos blocos, quanto ele corrige | `instructions/00-lesson-protocol.md` |
| Os temas das minhas aulas | `instructions/03-theme-bank.md` |
| Como o professor pensa em geral | `SKILL.md` |

> 📖 O arquivo **`setup/01-mapa-de-respostas.md`** documenta **exatamente** o que
> cada configuração muda no comportamento do professor. **Leia ele antes de
> mexer** — está tudo em tabela.

### 🎯 Seu objetivo não está na lista?

Os cinco prontos são:

🖥️ **Entrevistas de tecnologia** · 💼 **Trabalho e reuniões** ·
📝 **Exames** (IELTS/TOEFL/Cambridge) · 🗣️ **Fluência e dia a dia** ·
🌱 **Começar do zero**

Para qualquer outro, copie um arquivo de `presets/`, troque o conteúdo e diga ao
professor para usar o seu. Serve para inglês de enfermagem, aviação,
atendimento, o que for.

---

## ❓ Perguntas rápidas

<details>
<summary><b>Preciso saber programar?</b></summary>

Não. Você só precisa conectar a pasta e digitar comandos. O git é opcional.
</details>

<details>
<summary><b>Onde ficam as minhas aulas?</b></summary>

Na **sua pasta**, no **seu computador**. Nada sai dali — a não ser que você
suba para o GitHub, e nesse caso deixe o repositório **privado**.
</details>

<details>
<summary><b>Ele esqueceu o contexto / começou a agir estranho</b></summary>

Abra uma conversa nova e digite `start lesson`. Todo o estado está **nos
arquivos**, não na conversa — foi justamente por isso que o sistema é assim.
</details>

<details>
<summary><b>Substitui um professor humano?</b></summary>

**Não.** Ele te dá o que professor humano é caro demais para dar: prática
diária, correção paciente, e alguém que lembra de tudo que você já errou.
Um humano enxerga coisas que ele não enxerga. Se puder ter os dois, tenha.
</details>

<details>
<summary><b>Funciona para outro idioma além do inglês?</b></summary>

A estrutura sim. Você teria que reescrever o `SKILL.md` e os presets para o
idioma-alvo. Dá trabalho, mas o esqueleto serve.
</details>

---

<sub>Criado por <b>Thomaz</b> — Algoritmo & Café. Use, modifique e repasse à vontade. ☕</sub>
