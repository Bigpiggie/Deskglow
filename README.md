# Deskglow

A beautiful, glowing **now-playing screen for Spotify** that runs in any browser. Built for a phone or tablet on your desk (landscape), but works anywhere.

*Português: [role para baixo](#português).*

- StandBy-style player: big cover, title, progress with remaining time, volume and the playing device
- **Swipe the cover** left/right (or use the buttons) to change songs; tap or drag the progress bar to seek
- Blurred, glowing background that follows the cover colours
- Star to save the song to your Spotify library, previous / play-pause / next, volume slider, and small lyrics / queue buttons in the corner
- Time-synced **lyrics** (via [LRCLIB](https://lrclib.net)) and a tappable **queue**
- Screen stays awake · English and Portuguese (auto-detected)
- **One HTML file.** No server, no build step, no tracking.

> Deskglow is an independent project. It is not affiliated with, endorsed by or sponsored by Spotify or Apple. "Spotify" is a trademark of Spotify AB.

## Quick start (about 5 minutes)

1. **Host the file over HTTPS.** Pick one:
   - **Netlify Drop** – go to <https://app.netlify.com/drop>, drag the folder with `index.html` in, done.
   - **GitHub Pages** – fork this repo → *Settings → Pages → Deploy from branch*.
   - **On your computer** – `python3 -m http.server 5173` in this folder, then open `http://127.0.0.1:5173/` (use `127.0.0.1`, not `localhost`).
2. **Open your site.** Deskglow shows a setup screen with the exact *Redirect URI* you need.
3. **Create a Spotify app** at the [Developer Dashboard](https://developer.spotify.com/dashboard): paste the Redirect URI, tick **Web API**, save.
4. **Paste your Client ID** into Deskglow, press *Save*, then *Connect Spotify*.
5. On iPhone/iPad: Safari → Share → **Add to Home Screen** for full-screen mode.

Each person uses **their own** Client ID, so your Spotify account is never tied to anyone else's app.

## Good to know

- **Spotify limits for new apps (Development mode):** the app owner needs **Spotify Premium**, an app can authorise at most **5 users** (add them under *User Management* in the dashboard), and each developer gets one dev Client ID. Spotify may change these rules — check their docs.
- **Playback buttons need Premium** (Spotify's rule for the Web API).
- **Volume:** Spotify blocks remote volume control on some devices, for example the phone that is itself playing the music. Deskglow then shows a note; use the device's own volume buttons.
- **Canvas videos** are not available in Spotify's public API, so Deskglow uses the blurred cover instead.
- Redirect URIs must be **HTTPS** (or `http://127.0.0.1:PORT`). `localhost` is not accepted by Spotify.

## Privacy

Everything runs in your browser. Your Client ID and Spotify tokens are stored in your browser's `localStorage` and are only sent to Spotify. Lyrics are fetched from LRCLIB using the song title, artist, album and duration. There are no analytics and no Deskglow server.

## Reset / language

- Add `?reset=1` to the address to forget the Client ID and sign out.
- Add `?lang=en` or `?lang=pt` to force a language.

## Contributing

Issues and pull requests are welcome. The whole app lives in `index.html`; translations are in the `I18N` object near the top of the script — adding a language is one more block.

## License

[MIT](LICENSE)

---

# Português

**Deskglow** é uma tela "tocando agora" do Spotify, bonita e com brilho, que roda em qualquer navegador. Feita para um celular ou tablet na mesa (deitado), mas funciona em qualquer lugar.

**Recursos:** layout estilo StandBy com capa grande (**deslize a capa** para trocar de música), fundo desfocado com as cores da capa, barra de tempo com tempo restante, botões (letra / anterior / play-pause / próxima / fila), volume e o aparelho que está tocando, **letra sincronizada** (LRCLIB), fila clicável, tela sempre ligada, inglês e português automáticos. É **um único arquivo HTML**, sem servidor.

> Projeto independente, sem ligação com Spotify ou Apple.

## Como usar (uns 5 minutos)

1. **Publique o arquivo em HTTPS:** [Netlify Drop](https://app.netlify.com/drop) (arraste a pasta), GitHub Pages, ou no seu computador com `python3 -m http.server 5173` e abra `http://127.0.0.1:5173/` (use `127.0.0.1`, não `localhost`).
2. **Abra o site.** O Deskglow mostra uma tela de configuração com o *Redirect URI* exato.
3. **Crie um app no Spotify** em [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard): cole o Redirect URI, marque **Web API** e salve.
4. **Cole o Client ID** no Deskglow, toque em *Salvar* e depois em *Conectar Spotify*.
5. No iPhone/iPad: Safari → Compartilhar → **Adicionar à Tela de Início**.

## Bom saber

- **Limites do Spotify para apps novos (modo Desenvolvimento):** o dono do app precisa de **Premium**, no máximo **5 usuários** autorizados (em *User Management* no painel) e um Client ID de desenvolvimento por desenvolvedor. O Spotify pode mudar essas regras.
- Os **botões de controle precisam de Premium**.
- **Volume:** em alguns aparelhos (como o próprio celular que toca a música) o Spotify bloqueia o controle remoto de volume. Use os botões do aparelho.
- Vídeos **Canvas** não existem na API pública; usamos a capa desfocada.
- **Privacidade:** tudo roda no seu navegador; Client ID e tokens ficam só no seu aparelho. Sem rastreamento.
- `?reset=1` no endereço apaga o Client ID e desconecta; `?lang=pt` força português.

Licença: [MIT](LICENSE).
