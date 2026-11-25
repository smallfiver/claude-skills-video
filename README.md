# Skills de vídeo para o Claude Code

Skills e um agent para **transcrever vídeos**, **ler quadro a quadro** e **transformar vídeo em skill**.

## O que tem

| Pasta | O que faz |
|---|---|
| `skills/youtube-to-skill` | Transforma um vídeo (link do YouTube ou arquivo) em uma skill pronta: transcreve, tira print das telas importantes e escreve o `SKILL.md`. |
| `skills/social-video-transcript` | Transcreve Reels, TikTok e YouTube pelo link (Whisper, 90+ idiomas, SRT/VTT). |
| `skills/eyes` | "Assiste" o vídeo: folhas de miniaturas, busca do que foi dito ou mostrado com segundo exato, zoom em momentos, estilo de edição. |
| `skills/video-sharingan` | Desmonta um vídeo de referência em números (ritmo, motion) e gera guia para recriar. |
| `skills/rea-video` | Diz, cena por cena, como o vídeo foi feito (gravação real, IA, 3D, animação). |
| `skills/reverse-any-video` | Refaz o vídeo como projeto editável (HyperFrames) e confere com o original quadro a quadro. |
| `agents/clonagem-transcricao.md` | Agent que transcreve uma VSL com timestamps e marca o pitch. |

## Como instalar

1. Baixe este repositório (botão **Code → Download ZIP**, ou `git clone`).
2. Copie as pastas de `skills/` para `~/.claude/skills/`
   - Windows: `C:\Users\SEU_USUARIO\.claude\skills\`
3. Copie os arquivos de `agents/` para `~/.claude/agents/`
4. Reinicie o Claude Code.

## O que precisa ter no PC

- [ffmpeg](https://ffmpeg.org/download.html)
- Python 3 e `pip install faster-whisper yt-dlp`

Cada skill tem detalhes extras no próprio `SKILL.md`.

## Para criar suas próprias skills

Instale pelo `/plugin` no Claude Code:
- `skill-creator` (plugin oficial da Anthropic)
- `superpowers` (traz a skill `writing-skills`)

## Créditos

As skills foram reunidas de vários autores. A `video-sharingan` tem licença própria (ver `LICENSE` na pasta). As demais são de terceiros: confira a origem antes de usar comercialmente.
