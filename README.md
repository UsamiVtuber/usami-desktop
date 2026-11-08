# Usami Desktop

Pacotes oficiais do aplicativo nativo (Rust + GPUI) da companion Usami para
Windows: avatar VRM 3D, chat com o backend local, TTS com lipsync e modo
chamada mãos-livres.

O código-fonte fica no repositório privado do workspace; este repositório serve
à distribuição dos binários.

## Download

Baixe o `.zip` mais recente em **[Releases](../../releases/latest)** e
descompacte em qualquer pasta. O executável é `usami-desktop.exe`; a pasta
`assets/` precisa ficar ao lado dele.

## Requisitos

- Windows 10/11 x64.
- Backend da Usami no ar em `http://127.0.0.1:8787` (`npm run api`, com o n8n
  configurado). Sem o backend a janela abre, mas chat, TTS e STT não respondem.
- Um modelo `.vrm` próprio e, opcionalmente, clipes `.vrma`. Esses arquivos não
  acompanham o pacote por licença; sem um modelo a cena abre sem avatar.

## Configuração

Variáveis de ambiente opcionais:

| Variável | Padrão | Descrição |
|---|---|---|
| `USAMI_API_BASE` | `http://127.0.0.1:8787` | base do backend |
| `USAMI_VRM_PATH` | `assets/shiro.vrm` ao lado do .exe | arquivo `.vrm` do avatar |
| `USAMI_VRMA_DIR` | `assets/vrma` ao lado do .exe | pasta de animações `.vrma` |
| `USAMI_BACKGROUND` | `assets/background.png` | imagem de fundo da janela |

Para apontar um modelo sem mexer em variáveis, basta colocar o `.vrm` em
`assets/shiro.vrm` dentro da pasta descompactada.

## Primeiro uso

1. Suba o backend (`npm run api` no repositório principal).
2. Extraia o zip e rode `usami-desktop.exe`.
3. Se o Windows mostrar "O Windows protegeu o PC", o executável não é assinado:
   use **Mais informações → Executar assim mesmo**.

## Privacidade

Por padrão o app só conversa com `127.0.0.1:8787`; nada é enviado para fora da
máquina, exceto o que o próprio backend já faz.
