---
layout: default
title: Instalação Offline
---

# 💾 Instalação Offline do Venda Mobile Inteligente

Siga estas instruções para preparar uma instalação local do aplicativo mesmo antes do lançamento oficial.

## 1. Pré-requisitos
- Node.js 18 ou superior
- npm (instalado junto com o Node.js)
- Git
- Acesso a um terminal ou prompt de comando

## 2. Clonar o repositório principal
```bash
git clone https://github.com/renanduart3/venda-mobile.git
cd venda-mobile
```

## 3. Instalar dependências
```bash
npm install
```

Se você encontrar erros de permissão, execute o comando novamente com privilégios de administrador ou use um gerenciador como `nvm` para garantir que o Node esteja configurado corretamente.

## 4. Configurar variáveis de ambiente
Crie um arquivo `.env.local` na raiz do projeto com as chaves necessárias. Consulte o arquivo `.env.example` para verificar os campos obrigatórios.

## 5. Executar em modo de desenvolvimento
```bash
npm run dev
```

O comando acima iniciará o servidor local. Acesse o aplicativo em `http://localhost:3000`.

## 6. Empacotar para distribuição offline
Quando o lançamento estiver disponível, publicaremos scripts automatizados para gerar pacotes Android (APK) e instaladores desktop. Enquanto isso, você pode gerar builds manuais com:
```bash
npm run build
```

Os artefatos serão colocados na pasta `dist/` para que você possa distribuí-los internamente.

## 7. Receber atualizações
- Assine o [cadastro de interesse](mailto:suporte@vendamobile.app?subject=Cadastro%20de%20Interesse%20-%20Venda%20Mobile%20Inteligente) para notificações sobre novos pacotes.
- Monitore o [repositório principal](https://github.com/renanduart3/venda-mobile) para releases oficiais.

Para suporte adicional, envie uma mensagem para [suporte@vendamobile.app](mailto:suporte@vendamobile.app).
