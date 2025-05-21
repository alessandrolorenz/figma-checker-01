# figma-checker-01# Figma Style Checker com GPT-4o

Este projeto compara visualmente um design do Figma com um site real, usando screenshots, análise de similaridade (SSIM) e análise de diferenças com o GPT-4o Vision.

---

## Instalação

1. **Clone o repositório**
   ```sh
   git clone <url-do-repo>
   cd <pasta-do-projeto>

Crie um ambiente virtual (opcional, mas recomendado)

python -m venv venv
venv\Scripts\activate   # Windows
# ou
source venv/bin/activate  # Linux/Mac

Instale as dependências

pip install -r requirements.txt

Se não houver requirements.txt, instale manualmente:
pip install pillow requests python-dotenv opencv-python scikit-image openai

## Configuração
Crie um arquivo .env na raiz do projeto com:

FIGMA_TOKEN=seu_token_figma
SCREENSHOT_API_KEY=sua_api_key_de_screenshot
OPENAI_API_KEY=sua_api_key_openai

O FIGMA_TOKEN você gera em Figma > Settings > Personal Access Tokens.
O SCREENSHOT_API_KEY pode ser do apiflash.com ou outro serviço similar.
O OPENAI_API_KEY você gera em OpenAI Platform.

## Como rodar
No terminal, execute:

python figma_langchain/figma_lang.py
O sistema irá pedir:

Figma File Key: (ex: GNKzYCRdDzTnfJG8tyiSNT)
Figma Node Key: (ex: 0-2&t=nkr3dH1oCs86bAd3-0)
URL do site: (ex: https://www.seusite.com)

Esses dados você pega na URL do Figma:

https://www.figma.com/design/GNKzYCRdDzTnfJG8tyiSNT/NOME?node-id=0-2&t=nkr3dH1oCs86bAd3-0
File Key: GNKzYCRdDzTnfJG8tyiSNT
Node Key: 0-2&t=nkr3dH1oCs86bAd3-0

Como funciona
Busca estilos do Figma via API.
Tira screenshot do design do Figma e do site real.
Compara as imagens usando SSIM (similaridade estrutural).
Gera uma imagem de diferença (diff_output.png).
Envia ambas as imagens para o GPT-4o Vision e recebe um feedback textual sobre as diferenças visuais.
Resultados
Imagem de diferença salva como diff_output.png.
Feedback do GPT-4o impresso no terminal.
Observações
O serviço de screenshot pode ter limitações de uso gratuito.
O GPT-4o Vision consome créditos da OpenAI.
Para projetos grandes no Figma, use sempre o file_key e node_id corretos para evitar erros de "Request too large".
Licença
MIT
