# Matechique Digital Signage

Página web para exibir vídeo em loop e tela cheia, ideal para TVs e displays digitais.

## URL do Projeto

**https://danersc.github.io/matechique-signage/**

### 🔄 Sistema de Rotação Inteligente

A página agora possui **controles de rotação interativos**!

**3 formas de usar:**

#### 1️⃣ Controles Visuais (Recomendado)
- Acesse a URL principal
- Na primeira vez, você verá 4 botões de rotação
- Escolha a orientação correta para sua TV:
  - ⬆️ **Normal (0°)** - TV horizontal ou vertical reconhecida
  - ➡️ **Direita (90°)** - TV vertical, rotacionar para direita
  - ⬇️ **Invertido (180°)** - TV de cabeça para baixo
  - ⬅️ **Esquerda (270°)** - TV vertical, rotacionar para esquerda
- Clique em "Iniciar Vídeo"
- **A escolha é salva automaticamente!** Próximas vezes carrega direto

#### 2️⃣ Parâmetro de URL (Para TVs fixas)
Se você já sabe a rotação necessária, use:
- **Normal:** `https://danersc.github.io/matechique-signage/`
- **90° direita:** `https://danersc.github.io/matechique-signage/?rotate=90`
- **180° invertido:** `https://danersc.github.io/matechique-signage/?rotate=180`
- **270° esquerda:** `https://danersc.github.io/matechique-signage/?rotate=270`

#### 3️⃣ Teclas de Atalho (Durante reprodução)
- **← →** - Rotacionar vídeo com setas
- **R** - Mostrar/esconder info de rotação atual
- **F** - Fullscreen
- **H** - Esconder mensagens

## Características

✅ Vídeo em loop infinito
✅ Reprodução automática (autoplay)
✅ **Rotação ajustável (0°, 90°, 180°, 270°)**
✅ **Lembra a configuração escolhida**
✅ Otimizado para TVs
✅ Sem dependências externas
✅ Vídeo hospedado localmente (90MB)

## Como Funciona a Rotação

O sistema de rotação permite que você ajuste o vídeo para **qualquer orientação da TV**:

**Cenário 1: TV Horizontal Normal**
- Use rotação **0°** (Normal)
- Vídeo aparece vertical na tela horizontal

**Cenário 2: TV Física Vertical + Sistema Horizontal**
- TV está virada 90° fisicamente, mas sistema não sabe
- Use rotação **90°** ou **270°** dependendo do lado
- O vídeo será rotacionado para compensar

**Cenário 3: Teste no Computador**
- Abra a página, escolha rotação 90°
- Você verá o vídeo "deitado"
- Vire sua cabeça 90° → vídeo estará correto!
- Na TV real que está virada, ficará perfeito

**Memória Automática:**
- Primeira vez: escolhe a rotação
- Sistema salva no navegador (localStorage)
- Próximas vezes: carrega automaticamente na rotação salva
- Para mudar: use teclas ← → ou acesse com `?rotate=` diferente

## Como usar em uma TV

### Opção 1: Navegador Nativo (Recomendado)

A página já está otimizada para TVs. O vídeo ocupa 100% da tela automaticamente.

**Setup inicial:**
1. Abra o navegador da TV
2. Acesse: `https://danersc.github.io/matechique-signage/`
3. **Clique uma vez** na tela (usar controle remoto)
4. A mensagem desaparecerá em 8 segundos
5. O vídeo rodará em loop infinito

**Para TVs Samsung (Tizen):**
- Use o app "Internet"
- Adicione a URL aos favoritos
- Configure como página inicial se disponível

**Para TVs LG (webOS):**
- Use o navegador "Web Browser"
- Adicione aos favoritos
- Configure para iniciar automaticamente

**Para Android TV:**
- Use Google Chrome
- Instale extensão "Kiosk Mode" se disponível
- Ou use app "Fully Kiosk Browser"

### Opção 2: Modo Kiosk/Fullscreen

Alguns navegadores de TV permitem configurar:
1. Abrir URL específica ao ligar
2. Modo kiosk (sem barras de navegação)
3. Fullscreen automático
4. Desabilitar screensaver

Consulte o manual da sua TV para ativar estas opções.

### Opção 3: Dispositivo Externo

Para controle total, use:
- **Raspberry Pi** com Chromium em modo kiosk
- **Fire TV Stick** com Silk Browser
- **Chromecast** com casting permanente
- **Mini PC** com Chrome em fullscreen

## Teclas de Atalho

- **F** - Alternar tela cheia
- **H** - Esconder mensagem manualmente
- **Clique/Toque** - Ativar fullscreen

## Especificações Técnicas

**Vídeo:**
- Formato: MP4 (H.264)
- Resolução: 1080x1920 (vertical)
- Duração: 7min 36s
- Tamanho: 90MB
- Bitrate: 1.7 Mbps

**Requisitos:**
- Conexão de internet para primeira carga
- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Suporte a HTML5 video

## Troubleshooting

### O vídeo não carrega
- Verifique a conexão de internet
- Limpe o cache do navegador
- Recarregue a página (F5 ou Ctrl+R)

### Vídeo não toca automaticamente
- **Normal**: Alguns navegadores bloqueiam autoplay
- **Solução**: Clique uma vez na tela
- Em TVs, certifique-se que não há configuração bloqueando autoplay

### Mensagem não desaparece
- Pressione tecla **H** para esconder
- Ou aguarde 8 segundos após o vídeo carregar
- Clique na mensagem para esconder

### Fullscreen não ativa
- **Em TVs**: Não é necessário! O vídeo já ocupa 100% da tela
- **Em computador**: Clique na tela ou pressione **F**
- Alguns navegadores bloqueiam fullscreen automático por segurança

### Vídeo para de tocar
- A página tem proteção contra isso
- Verifica a cada 10 segundos e retoma automaticamente
- Se persistir, verifique configurações de energia da TV

## Atualizando o Vídeo

Para substituir o vídeo:

1. Comprima o vídeo para < 100MB:
   ```bash
   ffmpeg -i seu_video.mp4 -c:v libx264 -b:v 1700k -preset medium -c:a aac -b:a 128k -movflags +faststart matechique001_compressed.mp4
   ```

2. Substitua o arquivo `matechique001_compressed.mp4`

3. Faça commit e push:
   ```bash
   git add matechique001_compressed.mp4
   git commit -m "Atualiza vídeo"
   git push
   ```

4. Aguarde 2-3 minutos para o GitHub Pages atualizar

## Suporte

Para dúvidas ou problemas, abra uma issue no repositório.

## Licença

Projeto de uso livre para digital signage.
