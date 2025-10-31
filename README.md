# 📱 Venda Mobile Inteligente

Repositório público do aplicativo Venda Mobile Inteligente - Documentação, Termos e Políticas

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Active-success)](https://renanduart3.github.io/venda-mobile-inteligente/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🌐 Sobre este Repositório

Este é o repositório público do **Venda Mobile Inteligente**, contendo:

- 📚 **Documentação Completa**: Site Jekyll com docs organizadas
- 🏠 **Landing Page**: Página inicial do aplicativo
- 📋 **Termos de Serviço**: Termos de uso do aplicativo
- 🔒 **Política de Privacidade**: Como tratamos seus dados
- 💎 **Informações Premium**: Planos, preços e funcionalidades
- 🖼️ **Assets Públicos**: Imagens, logos e recursos visuais
- 🔧 **GitHub Actions**: Workflow automático de publicação

Este repositório utiliza **GitHub Pages** com **Jekyll** (tema Cayman) para hospedar toda a documentação.

## 🔗 Links Importantes

- **Site Oficial**: [https://renanduart3.github.io/venda-mobile-inteligente/](https://renanduart3.github.io/venda-mobile-inteligente/)
- **Documentação**: [https://renanduart3.github.io/venda-mobile-inteligente/](https://renanduart3.github.io/venda-mobile-inteligente/)
- **Código Fonte Original**: [github.com/renanduart3/venda-mobile](https://github.com/renanduart3/venda-mobile)

## 📂 Estrutura do Repositório

```
venda-mobile-inteligente/
├── docs/                        # Site de documentação (Jekyll)
│   ├── _config.yml             # Configuração Jekyll
│   ├── index.md                # Landing page
│   ├── privacy.md              # Política de privacidade
│   ├── support.md              # Suporte e ajuda
│   ├── faq.md                  # Perguntas frequentes
│   ├── pricing.md              # Planos e preços
│   ├── data-safety.md          # Segurança de dados
│   ├── iap-testing.md          # Guia de testes IAP
│   ├── changelog.md            # Histórico de versões
│   ├── features.md             # Lista de funcionalidades
│   └── assets/                 # Assets da documentação
│       ├── screenshots/        # Screenshots do app
│       └── branding/           # Logos e branding
├── .github/
│   ├── workflows/
│   │   └── pages.yml           # Workflow GitHub Pages
│   └── ISSUE_TEMPLATE/         # Templates de issues
│       ├── bug_report.md
│       └── feature_request.md
├── index.html                  # Página inicial (legacy)
├── terms-of-service.html       # Termos de serviço
├── privacy-policy.html         # Política de privacidade (legacy)
├── _config.yml                 # Configuração Jekyll (root)
├── LICENSE                     # MIT License
├── SECURITY.md                 # Política de segurança
├── CODE_OF_CONDUCT.md          # Código de conduta
└── README.md                   # Este arquivo
```

## 🎯 Sobre o Venda Mobile Inteligente

O Venda Mobile Inteligente é um aplicativo completo para gerenciamento de vendas mobile, desenvolvido para facilitar o trabalho de vendedores e empresas que precisam de mobilidade e eficiência no processo de vendas.

### Principais Funcionalidades

- 🛒 **Gestão de Vendas**: Registre e acompanhe todas as suas vendas
- 👥 **Cadastro de Clientes**: Mantenha um cadastro completo dos seus clientes
- 📦 **Controle de Produtos**: Gerencie seu catálogo de produtos
- 📊 **Relatórios**: Visualize relatórios e estatísticas de vendas
- 🔄 **Sincronização**: Sincronize seus dados em tempo real
- 📱 **Interface Intuitiva**: Design moderno e fácil de usar
- 💎 **Plano Premium**: Recursos avançados para profissionais

[Ver lista completa de funcionalidades →](docs/features.md)

## 📚 Documentação

A documentação completa está disponível no diretório `docs/` e publicada via GitHub Pages:

- [🏠 Home](docs/index.md) - Landing page do aplicativo
- [📋 Funcionalidades](docs/features.md) - Lista detalhada de todas as funcionalidades
- [🔒 Política de Privacidade](docs/privacy.md) - Como protegemos seus dados
- [🆘 Suporte](docs/support.md) - Como obter ajuda
- [❓ FAQ](docs/faq.md) - Perguntas frequentes
- [💎 Planos e Preços](docs/pricing.md) - Informações sobre o Premium
- [🔒 Data Safety](docs/data-safety.md) - Resumo de segurança de dados
- [🧪 Guia de Testes IAP](docs/iap-testing.md) - Testes de In-App Purchases
- [📝 Changelog](docs/changelog.md) - Histórico de versões

## 🚀 Publicação do Site (GitHub Pages)

Este repositório está configurado para publicação automática via GitHub Actions.

### Configuração Inicial

1. **Habilitar GitHub Pages:**
   - Vá em: **Settings** → **Pages**
   - Source: **GitHub Actions**
   - O workflow `.github/workflows/pages.yml` fará o deploy automaticamente

2. **Verificar Deployment:**
   - Acesse: **Actions** → **Deploy GitHub Pages**
   - O site estará disponível em: `https://renanduart3.github.io/venda-mobile-inteligente/`

### Workflow Automático

O workflow de publicação é acionado:
- ✅ A cada push na branch `main`
- ✅ Manualmente via workflow_dispatch

O workflow:
1. Faz checkout do código
2. Configura o GitHub Pages
3. Compila o site Jekyll do diretório `docs/`
4. Faz upload do artifact
5. Publica no GitHub Pages

### Desenvolvimento Local

Para testar o site localmente:

```bash
# Instalar Jekyll (se não tiver)
gem install bundler jekyll

# Navegar para o diretório docs
cd docs/

# Servir o site localmente
jekyll serve

# Acessar em http://localhost:4000
```

### Adicionar Conteúdo

Para adicionar novo conteúdo ao site:

1. Edite ou crie arquivos `.md` em `docs/`
2. Use o formato front matter do Jekyll:
   ```yaml
   ---
   layout: default
   title: Título da Página
   ---
   ```
3. Commit e push para `main`
4. O site será atualizado automaticamente

### Adicionar Imagens

**⚠️ IMPORTANTE:** As imagens não estão incluídas neste commit inicial.

Para adicionar imagens:

1. **Screenshots do aplicativo:**
   - Coloque em: `docs/assets/screenshots/telefone/`
   - Formatos recomendados: PNG, JPG
   - Tamanho recomendado: 1080x1920px (mobile)

2. **Branding (logos, ícones):**
   - Coloque em: `docs/assets/branding/`
   - Use PNG com transparência quando apropriado

3. **Atualizar referências:**
   - Edite `docs/index.md` e outros arquivos que referenciam imagens
   - Use caminhos relativos: `assets/screenshots/telefone/screenshot.png`

4. **Commit as imagens:**
   ```bash
   git add docs/assets/
   git commit -m "Add app screenshots and branding assets"
   git push
   ```

## 📝 Nota sobre o Código Fonte

Este repositório contém **apenas arquivos públicos** (documentação, termos, políticas e assets).

O código fonte completo do aplicativo está disponível no repositório privado/separado:
[github.com/renanduart3/venda-mobile](https://github.com/renanduart3/venda-mobile)

## 🤝 Contribuindo

Este repositório contém a documentação pública do aplicativo. Contribuições são bem-vindas!

### Como Contribuir

1. **Reportar Bugs ou Problemas:**
   - Use os [Issue Templates](.github/ISSUE_TEMPLATE/)
   - [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md)
   - [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md)

2. **Melhorar a Documentação:**
   - Fork este repositório
   - Crie uma branch: `git checkout -b docs/minha-melhoria`
   - Faça suas alterações nos arquivos em `docs/`
   - Commit: `git commit -m 'docs: improve documentation'`
   - Push: `git push origin docs/minha-melhoria`
   - Abra um Pull Request

3. **Código de Conduta:**
   - Leia nosso [Código de Conduta](CODE_OF_CONDUCT.md)
   - Seja respeitoso e construtivo

## 🔒 Segurança

Para reportar vulnerabilidades de segurança, consulte nosso [Security Policy](SECURITY.md).

**Não reporte vulnerabilidades através de issues públicas!**

Email para segurança: suporte@vendamobile.app

## 📄 Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 📧 Contato

Para questões, suporte ou sugestões:

- **Email:** [suporte@vendamobile.app](mailto:suporte@vendamobile.app)
- **Issues:** [GitHub Issues](https://github.com/renanduart3/venda-mobile-inteligente/issues)
- **Documentação:** [https://renanduart3.github.io/venda-mobile-inteligente/](https://renanduart3.github.io/venda-mobile-inteligente/)

## 🎯 Roadmap

Veja nosso [Changelog](docs/changelog.md) para:
- Histórico de versões
- Próximas funcionalidades planejadas
- Atualizações recentes

## ⚠️ Revisão Necessária

**IMPORTANTE:** Antes de fazer merge deste PR:

1. **Revisar Conteúdo:**
   - [ ] Política de privacidade (`docs/privacy.md`)
   - [ ] Termos de serviço (arquivos HTML existentes)
   - [ ] Informações de contato (suporte@vendamobile.app)
   - [ ] Planos e preços (`docs/pricing.md`)
   - [ ] Licença (LICENSE)

2. **Adicionar Assets:**
   - [ ] Screenshots do app em `docs/assets/screenshots/telefone/`
   - [ ] Logos e branding em `docs/assets/branding/`
   - [ ] Atualizar referências de imagens em `docs/index.md`

3. **Verificar Links:**
   - [ ] Todos os links internos funcionam
   - [ ] Email de suporte está correto
   - [ ] Links para Play Store (quando disponível)

4. **Configurar GitHub Pages:**
   - [ ] Habilitar Pages em Settings → Pages
   - [ ] Source: GitHub Actions
   - [ ] Verificar primeiro deploy

---

**Desenvolvido com ❤️ para facilitar suas vendas mobile**
