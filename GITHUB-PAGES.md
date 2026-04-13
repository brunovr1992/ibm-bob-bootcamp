# 🌐 Publicando no GitHub Pages

Este guia mostra como publicar a página de apresentação do bootcamp no GitHub Pages.

## 📋 Pré-requisitos

- Repositório no GitHub
- Permissões para configurar GitHub Pages no repositório

## 🚀 Passos para Publicação

### 1. Fazer Push do Código

Certifique-se de que o arquivo `index.html` está na raiz do repositório:

```bash
git add index.html
git commit -m "Add: Página de apresentação do bootcamp com Carbon Design"
git push origin main
```

### 2. Configurar GitHub Pages

1. Acesse seu repositório no GitHub
2. Vá em **Settings** (Configurações)
3. No menu lateral, clique em **Pages**
4. Em **Source** (Fonte), selecione:
   - **Branch:** `main`
   - **Folder:** `/ (root)`
5. Clique em **Save** (Salvar)

### 3. Aguardar Deploy

- O GitHub Pages levará alguns minutos para fazer o deploy
- Você verá uma mensagem: "Your site is ready to be published at..."
- A URL será algo como: `https://seu-usuario.github.io/nome-do-repositorio/`

### 4. Acessar o Site

Após o deploy, acesse a URL fornecida pelo GitHub Pages.

## 🎨 Recursos da Página

A página criada inclui:

### ✅ Design Profissional

- **Carbon Design System** da IBM
- Layout responsivo para mobile, tablet e desktop
- Animações suaves ao scroll
- Navegação sticky

### 📱 Seções

1. **Hero Section**
   - Título principal
   - Call-to-action buttons
   - Gradiente azul IBM

2. **Sobre o Bootcamp**
   - 6 cards com features principais
   - Ícones e descrições

3. **Jornada de Modernização**
   - 5 passos numerados
   - Fluxo visual da progressão

4. **Laboratórios Práticos**
   - 4 cards de laboratórios
   - Tags de tecnologias
   - Links para guias

5. **Recursos**
   - Links para documentação
   - Pré-requisitos
   - Referências úteis

6. **Footer**
   - Links organizados
   - Informações de copyright

### 🎯 Funcionalidades

- ✅ Smooth scroll para navegação interna
- ✅ Animações ao scroll (fade in + slide up)
- ✅ Hover effects em cards e botões
- ✅ Design responsivo (mobile-first)
- ✅ Acessibilidade (semantic HTML)
- ✅ Performance otimizada (CSS inline)

## 🔧 Personalização

### Cores

As cores principais estão definidas nas variáveis CSS no topo do arquivo:

```css
:root {
  --cds-interactive-01: #0f62fe; /* Azul IBM */
  --cds-interactive-02: #393939; /* Cinza escuro */
  --cds-ui-background: #ffffff; /* Branco */
  --cds-text-01: #161616; /* Texto principal */
  --cds-text-02: #525252; /* Texto secundário */
}
```

### Conteúdo

Para alterar o conteúdo, edite o arquivo `index.html`:

- **Título:** Linha 62
- **Descrição:** Linha 63
- **Features:** Linhas 85-120
- **Laboratórios:** Linhas 200-260
- **Recursos:** Linhas 280-320

## 📊 Monitoramento

Após publicar, você pode:

1. **Ver estatísticas de acesso:**
   - GitHub > Insights > Traffic

2. **Verificar builds:**
   - GitHub > Actions (se habilitado)

3. **Atualizar conteúdo:**
   - Edite `index.html`
   - Faça commit e push
   - GitHub Pages atualiza automaticamente

## 🐛 Troubleshooting

### Página não carrega

- Verifique se o arquivo se chama exatamente `index.html`
- Confirme que está na raiz do repositório
- Aguarde alguns minutos após configurar

### CSS não aparece

- Verifique se o CDN do Carbon está acessível
- Teste em modo anônimo do navegador
- Limpe o cache do navegador

### Links quebrados

- Use caminhos relativos para arquivos do repositório
- Exemplo: `laboratorios/lab01-java8-was-base/README.md`
- GitHub Pages renderiza Markdown automaticamente

## 🔗 URLs Úteis

- **Carbon Design System:** https://carbondesignsystem.com/
- **GitHub Pages Docs:** https://docs.github.com/pages
- **Carbon Components:** https://www.carbondesignsystem.com/components/overview/

## 📝 Notas

- A página usa Carbon Design System via CDN (sem build necessário)
- Totalmente estática (HTML + CSS + JS vanilla)
- Sem dependências de Node.js ou frameworks
- Carregamento rápido e otimizado

---

**Desenvolvido com ❤️ | Powered by IBM Bob & Carbon Design System**
