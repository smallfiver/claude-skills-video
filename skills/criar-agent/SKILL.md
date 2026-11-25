---
name: criar-agent
description: Cria um agent do Claude Code a partir de uma ideia solta do usuário. Melhora a ideia, pergunta o que falta, escolhe as ferramentas e salva o arquivo em ~/.claude/agents/. Use quando o usuário pedir "criar agent", "fazer um agent", "transformar isso em agent" ou digitar /criar-agent. Se a pessoa quiser também uma skill, gera a skill irmã.
---

# Criar agent

Transforma a ideia do usuário em um agent pronto do Claude Code.

## Skill x agent (explique se o usuário perguntar)

- **Skill** = receita. Fica em `~/.claude/skills/<nome>/SKILL.md`. O Claude lê e segue na própria conversa.
- **Agent** = trabalhador separado. Fica em `~/.claude/agents/<nome>.md`. Roda em contexto próprio e devolve só o resultado.
- Tarefa curta e repetitiva: skill. Tarefa longa, que lê muita coisa ou roda em paralelo: agent.

## Passo a passo

1. **Pegue a ideia.** Se o usuário ainda não disse, pergunte: o que o agent faz, para quê, e um exemplo de uso.
2. **Melhore a ideia.** Deixe claro: objetivo em 1 frase, o que entra, o que sai, o que ele NÃO deve fazer.
3. **Pergunte o que falta.** No máximo 3 perguntas. Se já dá para seguir, não pergunte.
4. **Escolha as ferramentas.** Só as necessárias. Referência:
   - Ler/procurar arquivos: `Read, Grep, Glob`
   - Criar/editar arquivos: `Write, Edit`
   - Rodar comandos: `Bash`
   - Internet: `WebSearch, WebFetch`
5. **Escreva o agent** no modelo abaixo.
6. **Mostre e espere o OK.** Não salve antes.
7. **Salve** em `~/.claude/agents/<nome>.md` (nome em minúsculas, com hífen). Se já existir um com esse nome, pergunte antes de sobrescrever.
8. **Pergunte se quer a skill irmã.** Se sim, crie `~/.claude/skills/<nome>/SKILL.md` com o mesmo passo a passo, para usar direto na conversa com `/<nome>`.
9. **Entregue:** caminho do arquivo e 2 frases de exemplo para chamar o agent. Avise que precisa reiniciar o Claude Code.

## Modelo do agent

```markdown
---
name: nome-do-agent
description: O que ele faz e QUANDO usar. Ex: "Use quando o usuário pedir X ou Y."
tools: Read, Write, Bash
model: sonnet
---

# Papel
Você é [quem ele é] e sua missão é [objetivo em 1 frase].

# Entrada
O que ele recebe (link, arquivo, texto).

# Passo a passo
1. ...
2. ...
3. ...

# Regras
- Sempre ...
- Nunca ...

# Entrega
Formato exato da resposta final (lista, tabela, arquivo salvo em tal pasta).
```

## Regras de qualidade

- A `description` é o campo mais importante: é por ela que o Claude decide chamar o agent. Sempre inclua "Use quando...".
- Entrega com formato exato. Sem isso, cada execução sai diferente.
- Passos numerados e curtos. Uma ação por passo.
- Nunca coloque senha, token ou chave dentro do agent. Indique onde a chave fica (variável de ambiente).
