# My English Teacher

Um professor de inglês particular que roda dentro do Claude, se configura para o
**seu** nível e o **seu** objetivo, e lembra de todas as aulas anteriores.

Não é um chat solto onde você pede "me ensina inglês". É um curso com estado:
ele sabe o que você errou na aula passada, cobra de volta na próxima, monta
lição de casa em cima dos seus erros e acompanha sua evolução em números.

```
setup  →  start lesson  →  lição de casa  →  start lesson  →  ...
 5 min      50 min           ~25 min           50 min
```

---

## Índice

- [O que você precisa](#o-que-você-precisa)
- [Instalação](#instalação)
- [O setup](#o-setup-a-parte-que-faz-a-diferença)
- [Como é uma aula](#como-é-uma-aula)
- [Os três modos](#os-três-modos)
- [O que ele gera](#o-que-ele-gera-a-cada-aula)
- [**Como personalizar**](#como-personalizar)
- [Perguntas frequentes](#perguntas-frequentes)
- [Estrutura dos arquivos](#estrutura-dos-arquivos)

---

## O que você precisa

- Uma conta paga do Claude (Pro, Max ou Team) com **Cowork** ou **Claude Code** —
  precisa ser uma versão que consiga ler e escrever arquivos numa pasta sua
- Esta pasta salva em algum lugar do seu computador
- 25 a 90 minutos por aula, na frequência que der

Não funciona no claude.ai comum sem acesso a arquivos: sem isso ele não
consegue salvar as aulas nem lembrar do que aconteceu.

---

## Instalação

**1. Baixe a pasta** e coloque onde você quiser (Desktop, Documentos, tanto faz).

**2. Abra no Claude:** no app do Claude, clique em **Add folder** e escolha esta
pasta. No Claude Code, abra um terminal aqui e rode `claude`.

**3. Digite `setup`** e responda o questionário.

**4. Digite `start lesson`.**

**Opcional — versionar com git**, para acessar de qualquer computador:

```bash
cd MyEnglishTeacher
git init && git add -A && git commit -m "Meu professor de inglês"
git remote add origin git@github.com:SEU_USUARIO/meu-ingles.git
git push -u origin main
```

Depois é só `git clone` em qualquer máquina e continuar de onde parou. Deixe o
repositório **privado** — suas aulas vão ter coisa sua ali dentro.

---

## O setup (a parte que faz a diferença)

O `setup` é o que separa isto de um chatbot genérico. Ele pergunta:

| # | Pergunta | Para quê |
|---|---|---|
| 1 | Nome e onde você mora | Te chamar pelo nome, calibrar exemplos |
| 2 | Sua língua nativa | Gerar a lista de erros típicos de quem fala essa língua |
| 3 | Seu nível de inglês | **Define toda a política de correção** |
| 4 | Seu objetivo principal | Escolhe o banco de temas |
| 5 | O que você faz da vida | Faz as aulas serem sobre a sua vida, não sobre exercícios |
| 6 | Tem prazo? | Reordena os temas se a prova/entrevista é logo |
| 7 | O que mais te trava | Define o foco do laboratório de língua |
| 8 | Duração da aula | 25, 50 ou 90 min |
| 9 | Aulas por semana | Calibra o tamanho da lição de casa |
| 10 | Tipo de professor | Exigente, equilibrado ou acolhedor |
| 11 | Quanto de português é permitido | Nenhum, só quando você pedir, ou livre |
| 12 | Escrita, voz ou ditado | Como você quer ter as aulas |

**Não sabe seu nível?** Responda "não sei". Ele faz três perguntas em inglês de
dificuldade crescente e estima o seu nível pelo que você *produziu*, não pelo
que você achou que sabia.

**A pergunta 5 é a mais importante.** Quanto mais específico você for sobre o
que faz — ferramentas, com quem fala, o que gostaria de conseguir explicar em
inglês — mais as aulas viram sobre a sua vida real. "Sou dev" gera uma aula sem
graça. "Sou dev backend numa fintech, faço daily em inglês com um time na Índia
e travo quando preciso explicar por que uma decisão técnica deu errado" gera
cinco aulas boas.

### Os cinco objetivos que ele já sabe configurar

| Objetivo | O que muda |
|---|---|
| **Entrevistas de tecnologia** | Mock interview, system design falado, STAR, cultura de empresa gringa |
| **Trabalho e reuniões** | Daily, apresentação, call com cliente, e-mail difícil, negociação |
| **Exames (IELTS/TOEFL/Cambridge)** | Tarefa cronometrada no formato da prova, nota pelos critérios oficiais |
| **Fluência e dia a dia** | Conversa longa, roleplay, contar história, destravar a fala |
| **Começar do zero** | Sequência de 20 aulas, bilíngue, uma estrutura por aula |

Se o seu objetivo não está aí, responda "outro" e descreva — ele monta um banco
de temas do zero para você.

---

## Como é uma aula

Cinco blocos. Os tempos abaixo são de uma aula de 50 minutos; em 25 ou 90 ele
ajusta sozinho.

| Bloco | Min | O que acontece |
|---|---|---|
| **Aquecimento** | 0–06 | Conversa de verdade, puxando algo da aula passada. Revisão da lição de casa. |
| **Retomada** | 06–14 | Os seus erros recorrentes, treinados até saírem certos sob pressão |
| **Bloco principal** | 14–34 | O tema do dia. É aqui que a aula acontece de verdade |
| **Laboratório** | 34–44 | Um alvo de língua: uma estrutura, um registro, um conjunto de expressões |
| **Fechamento** | 44–50 | **Você** resume a aula em inglês (é assim que ele te avalia), ele dá o feedback |

### Comandos durante a aula

| Comando | Efeito |
|---|---|
| `/nativo` | Uma explicação curta em português, e volta pro inglês |
| `/again` | Reformula a última fala mais simples |
| `/harder` | Sobe a dificuldade agora |
| `/time` | Onde estamos na aula |
| `/skip` | Pula o bloco |
| `end lesson` | Encerra e gera os arquivos (use se precisar sair antes) |

### Como ele corrige

Depende do seu nível — e isso é a coisa mais importante do sistema inteiro.
Um A2 corrigido como C1 desiste; um C1 corrigido como A2 se entedia.

| Nível | Ele corrige | Você fala |
|---|---|---|
| A0–A1 | quase tudo, com jeito, modelando a frase certa | 40% |
| A2 | o que quebra o sentido + o padrão do dia | 50% |
| B1 | sentido, recorrência e tempo verbal | 60% |
| B2 | sentido, recorrência e o que soa estranho | 65% |
| C1 | só o que muda o sentido, se repete, ou pegaria mal numa entrevista | 70% |
| C2 | quase nada — o trabalho vira naturalidade e registro | 75% |

Do B2 pra cima entra o **level-up**: ele pega uma frase que você acertou e
mostra como um nativo diria. É o feedback que mais faz diferença nesse nível.

---

## Os três modos

### Escrita (o padrão)
Você digita, ele responde. Tudo automático: ele lê o histórico, dá a aula, salva
os arquivos e commita.

### Voz (conversa por áudio)
O voice mode do Claude não funciona dentro do Cowork — então funciona assim:

**Pré-requisito: você já rodou o `setup`.** O briefing é montado a partir do seu
perfil, e ele vai parar numa conversa que não tem acesso a esta pasta — se o
perfil estiver vazio, não tem como consertar de lá.

1. **Antes:** digite `briefing`. Ele gera o `NEXT-LESSON-BRIEFING.md`, um prompt
   com todo o seu contexto atual
2. **Durante:** abra uma conversa nova do Claude, cole o bloco entre `BEGIN` e
   `END`, clique no ícone de onda sonora e fale
3. **Depois:** copie a transcrição, volte aqui e digite `intake` + cole

Custa dois copy-pastes. Em troca você treina pronúncia, ritmo e escuta — que é
o que o modo escrito não consegue fazer.

**E na primeira aula?** Funciona, e para B1 pra cima costuma ser até melhor
começar por voz: é falando que a lacuna real aparece. O briefing da Aula 1 sai
como diagnóstico — sem erros recorrentes para revisar, small talk puxada do seu
perfil, e uma instrução explícita para o professor estimar o seu nível **falado**
de ouvido. Espere que ele venha uma faixa abaixo do seu nível escrito: quem
escreve em B2 costuma falar em B1, porque tem a gramática mas não tem a
velocidade de busca. Isso é informação, não fracasso — o `intake` atualiza o seu
perfil com os dois níveis.

**Exceção:** se você está começando do zero (A0–A2), faça as três primeiras
aulas por escrito. Colar um prompt de 900 palavras em inglês numa conversa em
branco e ser respondido em inglês falado é o jeito mais rápido de desistir. Da
quarta aula em diante, a voz vira a parte mais valiosa do curso.

### Ditado
Use o ditado do sistema para falar em vez de digitar, na aula escrita normal.
Meio-termo: você fala, ele responde escrito.

---

## O que ele gera a cada aula

```
aulas/Aula3.md                  registro completo: o que foi falado, todas as
                                correções, vocabulário novo, suas notas de 1 a 5

homework/Aula3-homework.html    lição de casa interativa, feita em cima dos SEUS
                                erros daquela aula — abre no navegador, corrige
                                sozinha, e tem um botão que copia suas respostas
                                pra você colar na aula seguinte

instructions/02-progress.md     reescrito: erros recorrentes, temas cobertos,
                                evolução das notas, e a próxima aula já planejada
```

E um commit no git, se você tiver inicializado.

Digite `progresso` a qualquer momento para ver sua evolução.

---

## Como personalizar

Tudo que define o professor está em texto, em `instructions/`. Você pode mudar
qualquer coisa de três jeitos:

### 1. Falando com ele

O jeito mais fácil. Durante ou depois da aula:

> *"a partir de agora corrige menos, tá me travando"*
> *"quero aulas de 25 minutos"*
> *"meu foco mudou, tenho entrevista em duas semanas"*
> *"quero mais exercício de escrita e menos conversa"*

Ele atualiza os arquivos de `instructions/` sozinho. Ou digite `ajustar` e diga
o que quer mudar.

### 2. Rodando `setup` de novo

Mudou de nível, de objetivo ou de vida? Rode `setup` outra vez. Ele reescreve o
perfil **sem apagar suas aulas** — o histórico e o progresso continuam lá.

### 3. Editando os arquivos na mão

| Quero mudar… | Edite… |
|---|---|
| Meu perfil, nível, objetivo, tom | `instructions/01-student-profile.md` |
| Duração dos blocos, quantidade de correção, % de fala | `instructions/00-lesson-protocol.md` |
| Os temas das aulas | `instructions/03-theme-bank.md` — risque, acrescente, reordene |
| Como o professor pensa em geral | `SKILL.md` |
| A cara da lição de casa | `templates/homework-template.html` |
| O formato do registro da aula | `templates/aula-template.md` |

O arquivo `setup/01-mapa-de-respostas.md` explica **exatamente** o que cada
configuração muda no comportamento do professor. Se você vai mexer em alguma
coisa, leia ele primeiro — está tudo em tabela.

### Criando o seu próprio preset

Um preset é só um arquivo markdown em `presets/` com três partes: como rodar o
bloco principal, uma lista de temas, e uma lista de alvos de língua. Copie um
dos cinco, troque o conteúdo, e diga ao professor para usar o seu.

Serve para qualquer objetivo específico: inglês para enfermagem, para aviação,
para atendimento, para academia, para o que for.

### Ideias do que dá pra mudar

- **Aula mais curta e mais frequente:** 25 min, 4x por semana bate 50 min 2x
- **Só conversa, sem correção:** peça para ele corrigir apenas no fim da aula
- **Foco em escrita:** peça um exercício escrito por aula e correção de registro
- **Vocabulário da sua área:** acrescente os temas no banco e ele puxa o jargão
- **Preparação relâmpago:** diga o prazo e ele reordena tudo pelo que cai primeiro

---

## Perguntas frequentes

**Preciso saber programar?**
Não. O git é opcional. Sem ele, funciona igual — você só não consegue abrir de
outro computador.

**Ele substitui um professor humano?**
Não. Ele te dá o que professor humano é caro demais para dar: prática diária,
correção paciente, e alguém que lembra de tudo que você já errou. Um humano vê
coisas que ele não vê. Se puder ter os dois, tenha.

**As aulas ficam salvas onde?**
Na sua pasta, no seu computador. Nada sai dali, a não ser que você suba pro
GitHub — e nesse caso, deixe privado.

**Funciona para outra língua além do inglês?**
A estrutura sim. Você teria que reescrever o `SKILL.md` e os presets para o
idioma-alvo. Dá trabalho, mas o esqueleto serve.

**E se ele começar a agir estranho ou esquecer o contexto?**
Comece uma conversa nova e digite `start lesson`. Todo o estado está nos
arquivos, não na conversa — é justamente por isso que o sistema é assim.

**Posso usar num nível bem baixo mesmo?**
Sim, o preset "começar do zero" foi feito para isso: aula bilíngue, sequência de
20 aulas, uma estrutura por vez. Mas aviso: aprender do zero sozinho é difícil,
com IA ou sem. Vá devagar e não pule a revisão.

---

## Estrutura dos arquivos

```
MyEnglishTeacher/
├── COMECE-AQUI.md              👈 leia isto primeiro
├── README.md                   este arquivo
├── SKILL.md                    o "cérebro" do professor
├── CLAUDE.md                   faz o Claude entender a pasta sozinho
├── NEXT-LESSON-BRIEFING.md     gerado quando você usa o modo voz
│
├── setup/
│   ├── 00-questionario.md      as perguntas do setup
│   └── 01-mapa-de-respostas.md 👈 o que cada resposta muda (leia p/ personalizar)
│
├── presets/                    os cinco objetivos prontos
│   ├── tech-interviews.md
│   ├── work-meetings.md
│   ├── exams.md
│   ├── fluency.md
│   └── from-zero.md
│
├── instructions/               👈 SEU professor, preenchido pelo setup
│   ├── 00-lesson-protocol.md   blocos, tempos, quanto ele corrige
│   ├── 01-student-profile.md   quem você é e o que você quer
│   ├── 02-progress.md          ESTADO VIVO: seus erros, sua evolução
│   ├── 03-theme-bank.md        os temas das suas aulas
│   └── 04-voice-mode.md        o fluxo das aulas por voz
│
├── aulas/                      Aula1.md, Aula2.md… o registro de tudo
├── homework/                   Aula1-homework.html… suas lições de casa
└── templates/                  os modelos que ele usa para gerar os arquivos
```

---

<sub>Criado por Thomaz — Algoritmo & Café. Use, modifique e repasse à vontade.</sub>
