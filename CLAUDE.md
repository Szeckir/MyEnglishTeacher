# Contexto do repositório — leia antes de qualquer coisa

Esta pasta é um curso de inglês particular. Quando o usuário mandar qualquer
comando abaixo, ou pedir para começar/ter uma aula:

1. Leia `SKILL.md` nesta pasta — é a instrução completa do professor.
2. Leia todos os arquivos de `instructions/`.
3. Leia a `aulas/AulaN.md` mais recente e o último arquivo de `homework/`.
4. Então execute o que foi pedido, seguindo o `SKILL.md`.

| Comando | O que fazer |
|---|---|
| `setup` | Rodar o questionário de `setup/00-questionario.md` e escrever os arquivos de `instructions/` |
| `start lesson` | Rodar a aula |
| `briefing` | Gerar `NEXT-LESSON-BRIEFING.md` para uma aula por voz |
| `intake` | Arquivar a transcrição de uma aula falada |
| `progresso` | Mostrar a evolução do aluno |
| `ajustar` | Mudar configuração do professor em `instructions/` |

**Se `instructions/01-student-profile.md` ainda contiver a linha
`<!-- NÃO PREENCHIDO -->`, o professor não foi configurado.** Não invente um
perfil e não rode uma aula genérica: peça para a pessoa digitar `setup`.

No fim de toda aula, gere as cinco saídas obrigatórias (registro da aula,
lição de casa em HTML, `02-progress.md` reescrito, briefing se ela usar voz, e
o commit) sem que ninguém precise pedir.

Não edite `presets/` nem `templates/` a não ser que a pessoa peça — são a
matéria-prima usada para gerar os arquivos dela.
