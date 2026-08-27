# Setup — o questionário

> Este arquivo é lido pelo Claude quando o aluno digita `setup`.
> Ele conduz a entrevista, e no fim **escreve** os arquivos de `instructions/`.

## Regras para conduzir

- Fale no **idioma nativo do aluno** durante o setup (padrão: português do
  Brasil). A aula em si será em inglês; o setup não.
- **Uma pergunta por vez.** Nunca despeje as onze de uma vez. Onde houver
  ferramenta de múltipla escolha, use — é mais rápido do que pedir texto livre.
- Pode agrupar perguntas irmãs num único bloco (1+2, depois 8+9+10) para o setup
  caber em ~6 trocas. Nunca mais do que três perguntas por bloco.
- Reaja ao que a pessoa responde. Se ela diz "tenho entrevista em 3 semanas",
  comente e ajuste — não siga um roteiro robótico.
- Se ela responder algo fora das opções, aceite. As opções são atalhos, não uma
  gaiola.
- No fim, **mostre um resumo** do perfil montado e pergunte se está certo antes
  de escrever os arquivos.

---

## As perguntas

### 1. Nome e onde você mora
Para te chamar pelo nome e para calibrar exemplos culturais e fuso horário.

### 2. Qual é a sua língua nativa?
Padrão: português do Brasil. Isso define a **lista de interferência** — os erros
que falantes dessa língua cometem em inglês. Se não for português, gere a lista
equivalente para a língua dela.

### 3. Qual é o seu nível de inglês hoje?

| Opção | Significa |
|---|---|
| **Do zero (A0)** | Nunca estudei, ou só lembro de palavras soltas |
| **Básico (A1–A2)** | Entendo frases simples, falo com muita dificuldade |
| **Intermediário (B1)** | Me viro, mas travo e traduzo mentalmente |
| **Intermediário-avançado (B2)** | Converso bem, erro em precisão e naturalidade |
| **Avançado (C1)** | Fluente; meus erros são de naturalidade e registro |
| **Não sei** | → rode o **diagnóstico** abaixo |

**Diagnóstico (5 min), se ela não souber:** peça três coisas, em inglês, em
ordem crescente de dificuldade, uma de cada vez:

1. *"Tell me about your morning today."* — presente/passado simples, vocabulário
   do dia a dia
2. *"What would you change about your job or your studies, and why?"* —
   condicional, opinião, conectivos
3. *"Some people say learning English is easier now than ten years ago. What do
   you think?"* — argumentação, hedging, abstração

Classifique pelo que ela **produziu**, não pelo que ela disse que sabe. Diga o
nível estimado e por quê, em duas frases. Não exagere para agradar — um nível
inflado estraga todas as aulas seguintes.

### 4. Qual é o seu objetivo principal?

| Opção | Preset |
|---|---|
| Entrevistas de emprego em tecnologia | `presets/tech-interviews.md` |
| Trabalho e reuniões em inglês | `presets/work-meetings.md` |
| Exame (IELTS, TOEFL, Cambridge) | `presets/exams.md` |
| Fluência e conversação no dia a dia | `presets/fluency.md` |
| Começar do zero | `presets/from-zero.md` |
| Outro | monte um banco de temas do zero para o objetivo dela |

Se ela marcar mais de um, o primeiro é o principal e os outros entram como
temas secundários no rodízio.

### 5. Me conta o que você faz
Profissão, área, o que estuda, no que trabalha. **Esta é a pergunta mais
importante do questionário**: é ela que faz as aulas serem sobre a vida da
pessoa em vez de exercícios genéricos. Puxe detalhes: ferramentas que usa,
com quem fala no trabalho, o que gostaria de conseguir explicar em inglês.

### 6. Tem prazo?
Entrevista marcada, prova com data, viagem, mudança de país — ou é contínuo,
sem data? Prazo curto muda a ordem dos temas: vai direto no que cai na prova ou
na entrevista e deixa fundamentos para depois.

### 7. O que mais te trava hoje? (pode marcar vários)
Falar na hora · Vocabulário · Gramática · Entender quando falam rápido ·
Pronúncia · Medo de errar · Escrever

### 8. Quanto tempo dura cada aula?
25 min · **50 min** (padrão) · 90 min

### 9. Quantas aulas por semana você pretende ter?
Só para calibrar o tamanho da lição de casa — não crie cronograma fixo.

### 10. Que tipo de professor funciona com você?
**Exigente** (corrige muito, cobra, sem paninho quente) ·
**Equilibrado** (padrão) ·
**Acolhedor** (prioriza confiança e fluência; corrige menos e mais suave)

### 11. Quanto do seu idioma nativo é permitido na aula?
**Nenhum** · **Só quando eu pedir** (padrão) · **Livre quando eu travar**

> No nível A0–A2 ignore a resposta "nenhum" e use pelo menos "só quando eu
> pedir": aula 100% em inglês para quem está começando não ensina, só assusta.
> Explique isso à pessoa em vez de obedecer calado.

### 12. Como você quer ter as aulas?
**Escrita** (você digita, o professor responde) ·
**Por voz** (o professor gera um briefing para você colar numa conversa com
voice mode) · **Ditado** (você fala, ele responde escrito)

> **Se ela escolher voz e o nível for A0–A2:** diga, uma vez e sem insistir, que
> as três primeiras aulas rendem mais por escrito — ela consegue reler, ver as
> palavras e ir no próprio ritmo — e que a partir da quarta a voz passa a valer
> muito mais. Se ela quiser voz mesmo assim, respeite e registre a escolha.
>
> **Se ela escolher voz em qualquer nível:** avise que a Aula 1 por voz também
> serve para medir o nível **falado**, que costuma ficar uma faixa abaixo do
> escrito. Isso não é um problema — é a informação mais útil que a primeira
> aula pode dar.

---

## Depois de responder

Mostre o resumo, confirme, e então escreva — nesta ordem:

1. `instructions/01-student-profile.md` — o perfil completo
2. `instructions/03-theme-bank.md` — a partir do preset escolhido, **adaptado**
   ao que ela contou na pergunta 5. Não copie o preset cru: troque os exemplos
   pelos do mundo dela.
3. `instructions/00-lesson-protocol.md` — preencha os blocos de tempo conforme a
   duração escolhida e a política de correção conforme o nível
4. `instructions/02-progress.md` — zerado, com a Aula 1 já planejada
5. `NEXT-LESSON-BRIEFING.md` — se ela escolheu voz
6. `git add -A && git commit -m "Setup: perfil de {nome}"`

Depois diga, em três linhas: que está pronto, qual é o tema da Aula 1, e que ela
começa dizendo `start lesson`.
