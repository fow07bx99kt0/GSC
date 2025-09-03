# SGC — Sistema de Gestão do Conhecimento (Teams Tab)
Pronto para publicar no **GitHub Pages** e usar como **Aba do Microsoft Teams**.

## Passo a passo (time-to-value rápido)
1) **GitHub**
   - Crie um repositório público (ex.: `sgc-teams-app`).
   - Faça upload de todos os arquivos desta pasta (mantenha a estrutura).
   - Em *Settings → Pages*, selecione `Deploy from a branch` e a branch principal (ex.: `main`) e a pasta `/` (root). Aguarde a URL do GitHub Pages (ex.: `https://SEUUSUARIO.github.io/sgc-teams-app`).
2) **Ajuste de URL no manifest**
   - Abra `teams/manifest.json` e substitua todas as ocorrências de `https://SEUUSUARIO.github.io/sgc-teams-app` pela URL do seu Pages.
3) **Microsoft Teams (sideload)**
   - Compacte a pasta `teams/` (apenas os 3 arquivos: `manifest.json`, `color.png`, `outline.png`) em um `.zip`.
   - No Teams (versão Desktop), vá em **Apps → Manage your apps → Upload a custom app** e selecione o `.zip`.
   - Adicione como **Aba** no time/canal desejado.
4) **Observações importantes**
   - Este site tenta embutir os links do SharePoint em `<iframe>` com `?web=1` para reduzir a UI. Se o tenant bloquear `iframe`, use o botão **Abrir em nova aba** (já previsto).
   - Se quiser bloquear ao máximo a navegação para fora das pastas, prefira *links de pasta específicos* e permissões de leitura nos destinos.
   - Para uma experiência 100% white‑label dentro do Teams, considere futuramente usar Microsoft Graph + SSO (exige app registrado no Entra ID).

## Onde editar os links
Abra `index.html` e ajuste a constante `CATEGORIES` com as URLs do SharePoint (já pré-preenchidas).

## Ícones e identidade
Os SVGs ficam em `assets/icons`. Você pode substituir por ícones próprios.

## Suporte
Se algo quebrar no iframe, é limitação de `X-Frame-Options`/CSP do SharePoint. O fallback **Abrir em nova aba** resolve o fluxo de usuário.
