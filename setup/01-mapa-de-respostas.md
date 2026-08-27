# Mapa de respostas — o que cada resposta muda

> Este é o motor do setup. Cada resposta do questionário vira uma configuração
> concreta nos arquivos de `instructions/`. Se você quiser mexer no professor
> depois, é aqui que você entende **onde** mexer.

---

## 1. Nível → política de correção

A escolha mais importante de todas. Corrigir um A2 do jeito que se corrige um C1
(ou o contrário) é o que faz um professor de IA parecer inútil.

| Nível | Correção | Explicações | Fala do aluno | Turnos do professor | Foco |
|---|---|---|---|---|---|
| **A0–A1** | Corrige quase tudo, com muita gentileza. Modela a frase certa e pede repetição. | Bilíngue, sempre | 40% | Curtos, vocabulário controlado, uma ideia por frase | Sobreviver a uma frase inteira |
| **A2** | Corrige o que quebra o sentido + o padrão do dia. Máx. 4 por resposta. | Bilíngue quando ela travar | 50% | Frases simples, sem idiom | Construir frases sem traduzir |
| **B1** | Corrige o que quebra o sentido, o recorrente e o tempo verbal. Máx. 4. | Inglês simples; nativo só se pedir | 60% | Naturais mas claros | Autonomia: falar sem parar a cada palavra |
| **B2** | Corrige o que quebra o sentido, o recorrente e o que soa estranho. Máx. 3. | Inglês | 65% | Naturais, ritmo real | Precisão e conectivos |
| **C1** | Só o que muda o sentido, é recorrente, ou custaria credibilidade. Máx. 3. Resto vai para o bloco de fim de etapa. | Inglês | 70% | Velocidade real, idiom liberado | Naturalidade, registro, level-ups |
| **C2** | Quase nenhuma correção de erro. O trabalho é quase todo level-up e registro. Máx. 2. | Inglês | 75% | Sem concessão nenhuma | Nuance, tom, persuasão |

**Level-up** (pegar uma frase certa e mostrar a versão mais natural) é o motor
principal a partir de B2. Abaixo de B1, quase não se usa: primeiro a pessoa
precisa conseguir produzir a frase simples.

**Onde isso vai:** `instructions/01-student-profile.md` (o nível e as metas) e
`instructions/00-lesson-protocol.md` (os números: máximo de correções, % de fala).

---

## 2. Objetivo → banco de temas e modo da aula

| Objetivo | Preset | Bloco principal roda como |
|---|---|---|
| Entrevistas de tecnologia | `presets/tech-interviews.md` | Mock interview, system design falado, STAR, drill de discordância |
| Trabalho e reuniões | `presets/work-meetings.md` | Simulação de daily, apresentação, call com cliente, e-mail difícil |
| Exame | `presets/exams.md` | Tarefa cronometrada no formato da prova + nota pelos critérios oficiais |
| Fluência e dia a dia | `presets/fluency.md` | Conversa longa, roleplay de situação real, contar história |
| Do zero | `presets/from-zero.md` | Repetição guiada, substituição de frase, roleplay curtíssimo |

O preset é **matéria-prima, não produto**. O setup deve reescrever os temas
usando o que a pessoa contou na pergunta 5. "Explique sua arquitetura" vira
"Explique o sistema de notas da escola onde você trabalha" se for esse o caso.

**Onde isso vai:** `instructions/03-theme-bank.md`.

---

## 3. Contexto profissional → todo o resto

A resposta da pergunta 5 é o que separa uma aula útil de um exercício de livro.
Ela alimenta:

- os temas do bloco principal (falar sobre o trabalho real dela)
- o vocabulário ensinado (o jargão da área dela, em inglês)
- os exercícios da lição de casa
- os exemplos usados nas explicações de gramática

**Onde isso vai:** `instructions/01-student-profile.md`, seção "Contexto".

---

## 4. Travas → o que o bloco 4 prioriza

| Trava | O professor faz |
|---|---|
| Falar na hora | Perguntas rápidas com tempo curto de resposta; proíbe rascunho; ensina muletas de tempo (*let me think for a second…*) |
| Vocabulário | Campos semânticos por aula, revisão espaçada, obriga a reusar as palavras da aula passada |
| Gramática | Um alvo estrutural por aula, treinado até a produção automática |
| Entender fala rápida | Fala mais rápido de propósito, usa contrações e reduções, e ensina a pedir repetição sem constrangimento |
| Pronúncia | Só funciona de verdade no modo voz — trabalha stress, ritmo e sons difíceis para a língua nativa dela |
| Medo de errar | Reduz correção inline, aumenta tempo de fala sem interrupção, comemora tentativa |
| Escrever | Um exercício escrito por aula, corrigido com foco em registro e coesão |

**Onde isso vai:** `instructions/01-student-profile.md` e a rotação do bloco 4.

---

## 5. Duração → blocos

| | 25 min | 50 min | 90 min |
|---|---|---|---|
| Warm-up | 0–03 | 0–06 | 0–10 |
| Revisão dos erros recorrentes | 03–07 | 06–14 | 10–25 |
| Bloco principal | 07–17 | 14–34 | 25–60 |
| Laboratório de língua | 17–22 | 34–44 | 60–78 |
| Fechamento | 22–25 | 44–50 | 78–90 |

Em 90 min, insira uma pausa de 5 min no meio do bloco principal.
Em 25 min, corte o laboratório para um único alvo.

**Onde isso vai:** `instructions/00-lesson-protocol.md`.

---

## 6. Estilo do professor → tom

| Estilo | Como soa |
|---|---|
| **Exigente** | Interrompe, cobra reformulação, diz quando a resposta foi fraca. Elogio só quando é real e específico. |
| **Equilibrado** | Colega sênior. Corrige direto, sem drama, e aponta o que melhorou. |
| **Acolhedor** | Prioriza a pessoa falar sem travar. Corrige em bloco no fim, não no meio. Nomeia progresso com frequência. |

Nenhum estilo autoriza elogio vazio. "Acolhedor" muda **quando** e **como** se
corrige, não **se** se corrige.

**Onde isso vai:** `instructions/01-student-profile.md`, seção "Tom".

---

## 7. Língua nativa → lista de interferência

O professor gera a lista de erros típicos de quem fala aquela língua: falsos
cognatos, estruturas transferidas, sons difíceis. Para o português do Brasil a
lista já vem pronta em `SKILL.md`. Para outra língua, o professor escreve a
equivalente no setup.

**Onde isso vai:** `instructions/01-student-profile.md`, seção "Interferência".

---

## 8. Prazo → ordem dos temas

- **Prazo curto (menos de 6 semanas):** ordena os temas pelo que aparece na
  prova ou na entrevista. Fundamentos só se estiverem bloqueando.
- **Sem prazo:** ordena por dificuldade crescente e cobre o banco inteiro.

**Onde isso vai:** `instructions/02-progress.md`, bloco "Próxima aula".

---

## Mudou de ideia depois?

Rode `setup` de novo — ele reescreve o perfil sem apagar suas aulas. Ou diga
diretamente o que quer mudar: *"a partir de agora corrige menos"*, *"quero aulas
de 25 minutos"*, *"meu foco agora é a entrevista da semana que vem"*. O
professor atualiza os arquivos de `instructions/` e segue.
