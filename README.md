# Matechique Digital Signage

Página web para exibir vídeo em loop e tela cheia, ideal para TVs e displays digitais.

## Como configurar o vídeo no Google Drive

### Passo 1: Upload do vídeo

1. Acesse [Google Drive](https://drive.google.com)
2. Faça login com sua conta Google
3. Clique em **"Novo"** > **"Upload de arquivo"**
4. Selecione o vídeo `matechique001.mp4`
5. Aguarde o upload completar

### Passo 2: Tornar o vídeo público

1. Clique com botão direito no vídeo que você fez upload
2. Selecione **"Compartilhar"**
3. Clique em **"Alterar para qualquer pessoa com o link"**
4. Certifique-se que está marcado como **"Visualizador"**
5. Clique em **"Concluído"**

### Passo 3: Obter o ID do arquivo

1. Clique com botão direito no vídeo novamente
2. Selecione **"Obter link"**
3. Você verá um link como este:
   ```
   https://drive.google.com/file/d/1a2b3c4d5e6f7g8h9i0j/view?usp=sharing
   ```
4. Copie apenas a parte que está entre `/d/` e `/view` (exemplo: `1a2b3c4d5e6f7g8h9i0j`)

### Passo 4: Atualizar o código

1. Abra o arquivo `index.html`
2. Encontre a linha (aproximadamente linha 65):
   ```javascript
   player.src = 'https://drive.google.com/uc?export=download&id=COLOQUE_SEU_ID_AQUI';
   ```
3. Substitua `COLOQUE_SEU_ID_AQUI` pelo ID que você copiou
4. Exemplo final:
   ```javascript
   player.src = 'https://drive.google.com/uc?export=download&id=1a2b3c4d5e6f7g8h9i0j';
   ```
5. Salve o arquivo

### Passo 5: Fazer commit e push

```bash
git add index.html
git commit -m "Atualiza link do vídeo do Google Drive"
git push
```

## Alternativa: Usar outro serviço

Se preferir usar outro serviço de hospedagem:

### Dropbox
1. Faça upload do vídeo
2. Gere link compartilhável
3. **Importante:** Troque `dl=0` por `dl=1` no final da URL
4. Use este link no `player.src`

### Cloudinary (recomendado para vídeos)
1. Crie conta gratuita em [cloudinary.com](https://cloudinary.com)
2. Faça upload do vídeo
3. Copie a URL direta do vídeo
4. Use no `player.src`

## Como usar

1. Acesse a página pelo GitHub Pages
2. Clique na tela para entrar em tela cheia
3. Ou pressione a tecla `F` para fullscreen
4. O vídeo tocará automaticamente em loop

## Teclas de atalho

- `F` - Alternar tela cheia
- Clique - Entrar em tela cheia

## Troubleshooting

### O vídeo não carrega
- Verifique se o link do Google Drive está correto
- Certifique-se que o vídeo está público
- Teste o link diretamente no navegador

### Vídeo não toca automaticamente
- Alguns navegadores bloqueiam autoplay
- Clique na tela para iniciar a reprodução
- Em TVs, certifique-se que o navegador permite autoplay

### Para TVs Samsung/LG
- Use o navegador nativo da TV
- Configure a página como página inicial
- Ative o modo quiosque se disponível
