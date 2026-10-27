# /watch (claude-video): fazer o Claude "assistir" um vídeo

Origem: https://github.com/inematds/claude-video (cópia de bradautomates/claude-video), licença MIT (arquivo LICENSE mantido).
Copiado em 2026-10-27, com uma adaptação: legendas automáticas em **português** primeiro (o original só buscava inglês).

## O que faz
Recebe um link (YouTube, TikTok, Instagram, Loom...) ou um arquivo (.mov, .mp4), tira quadros do vídeo com ffmpeg
(nos cortes de cena), pega a transcrição com tempos (legenda da plataforma; se não houver, Whisper via chave Groq ou OpenAI)
e o Claude olha cada quadro. Serve para: analisar gancho e estrutura de referências, conferir os vídeos do Bruno antes de postar,
transcrever falas com tempo para legenda dinâmica.

## Como usar aqui (container do projeto)
```
pip install yt-dlp        # ffmpeg já vem instalado
python3 ferramentas/watch/scripts/watch.py "/mnt/project-files/IMG_2133.MOV" --no-whisper --detail efficient --out-dir /tmp/w1
```
Depois o Claude lê os JPGs listados. Testado em 2026-10-27 com IMG_2133.MOV: 27 quadros em poucos segundos.

**Limites no container:** a rede bloqueia YouTube, TikTok e Instagram (erro 403 do proxy), então aqui só funciona com
**arquivo enviado pelo Bruno**. Sem chave Groq/OpenAI, vídeo sem legenda sai só com imagens (sem a fala).

## Como usar no computador do Bruno (funciona com links)
No Claude Code do Mac:
```
/plugin marketplace add inematds/claude-video
/plugin install watch@claude-video
```
Depois: `/watch <link do reel> qual é o gancho nos 3 primeiros segundos?`
No Mac ele instala ffmpeg e yt-dlp sozinho via Homebrew. Para ouvir vídeos sem legenda (a maioria dos Reels e TikToks),
criar uma chave grátis/barata em https://console.groq.com/keys e colar em `~/.config/watch/.env` como `GROQ_API_KEY=...`.
