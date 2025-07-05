# 🚀 Furby - Plataforma de Investimentos

Uma plataforma moderna de investimentos e trading com design roxo escuro, desenvolvida com HTML, CSS e JavaScript vanilla.

## 🎨 Design

- **Tema**: Roxo escuro com gradientes modernos
- **Cores principais**: #1a1a2e, #16213e, #0f3460
- **Acentos**: Verde para lucros, vermelho para perdas
- **Responsivo**: Funciona perfeitamente em desktop e mobile

## ✨ Funcionalidades

### 📊 Dashboard
- Estatísticas em tempo real
- Saldo disponível
- Rendimentos do dia
- Total de investimentos
- Growth tracking

### 👥 Sistema de Traders
- Lista de traders disponíveis
- Taxa de sucesso de cada trader
- Investimento mínimo e máximo
- Sistema de subscrição
- Filtros por categoria (Todos, Alto Retorno, Lucros Estáveis)

### 🔗 Sistema de Indicações
- Programa de referência com 3 níveis
- Nível 1: 8% de comissão
- Nível 2: 3% de comissão
- Nível 3: 1% de comissão
- Bônus especial: 10% + 2 para convites
- Link de indicação copiável
- Múltiplas formas de compartilhamento

### 🎯 Interatividade
- Notificações em tempo real
- Modais informativos
- Animações suaves
- Hover effects nos cards
- Sistema de navegação dinâmico

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura semântica e acessível
- **CSS3**: Gradientes, animações, flexbox, grid
- **JavaScript ES6+**: Interatividade e funcionalidades dinâmicas
- **Font Awesome**: Ícones modernos
- **Design Responsivo**: Mobile-first approach

## 📁 Estrutura do Projeto

```
Furby/
├── index.html          # Página principal
├── styles.css          # Estilos CSS
├── script.js           # JavaScript
├── README.md           # Documentação
├── logo/               # Pasta da logo
│   └── 34188cdd-d426-4619-90d5-7b51858fba31.jpg
└── step-by-step/       # Documentação do desenvolvimento
    └── desenvolvimento.md
```

## 🚀 Como Executar

### Opção 1: Servidor Python
```bash
cd Furby
python -m http.server 8000
```

### Opção 2: NPX Serve
```bash
cd Furby
npx serve -s . -p 8000
```

### Opção 3: Live Server (VS Code)
- Instale a extensão Live Server
- Clique com o botão direito no index.html
- Selecione "Open with Live Server"

Acesse: `http://localhost:8000`

## 🎯 Funcionalidades Principais

### 1. Dashboard Interativo
- Visualização de saldo em tempo real
- Cards de estatísticas com hover effects
- Atualizações automáticas a cada 30 segundos

### 2. Sistema de Traders
- 8 traders diferentes com perfis únicos
- Taxas de sucesso variando de 10% a 210%
- Períodos de investimento de 1 a 90 dias
- Sistema de subscrição com feedback visual

### 3. Filtros Inteligentes
- **Todos**: Mostra todos os traders
- **Alto Retorno**: Traders com taxa ≥ 100%
- **Lucros Estáveis**: Traders com taxa entre 50-100%

### 4. Sistema de Referência
- Link único de indicação
- Cópia automática para clipboard
- Múltiplas opções de compartilhamento
- Tracking de comissões

## 🎨 Características do Design

### Paleta de Cores
- **Primária**: #1a1a2e (Roxo escuro)
- **Secundária**: #16213e (Azul escuro)
- **Terciária**: #0f3460 (Azul profundo)
- **Sucesso**: #10b981 (Verde)
- **Erro**: #ef4444 (Vermelho)
- **Destaque**: #7c3aed (Roxo vibrante)

### Efeitos Visuais
- Gradientes suaves
- Backdrop blur effects
- Animações de entrada
- Transições suaves
- Sombras modernas
- Bordas arredondadas

## 📱 Responsividade

- **Desktop**: Layout em grid com múltiplas colunas
- **Tablet**: Adaptação automática do grid
- **Mobile**: Layout em coluna única
- **Navegação**: Menu inferior fixo para mobile

## 🔧 Customização

### Alterar Cores
Edite as variáveis CSS no início do arquivo `styles.css`:

```css
:root {
  --primary-color: #1a1a2e;
  --secondary-color: #16213e;
  --accent-color: #7c3aed;
  --success-color: #10b981;
  --error-color: #ef4444;
}
```

### Adicionar Novos Traders
No arquivo `index.html`, copie e modifique um card existente:

```html
<div class="trader-card">
  <!-- Conteúdo do trader -->
</div>
```

### Modificar Funcionalidades
Edite o arquivo `script.js` para adicionar novas funcionalidades ou modificar as existentes.

## 🌟 Destaques Técnicos

- **Performance**: Código otimizado e leve
- **Acessibilidade**: Estrutura semântica
- **SEO**: Meta tags apropriadas
- **Manutenibilidade**: Código bem estruturado
- **Escalabilidade**: Arquitetura modular

## 📈 Métricas

- **Tempo de carregamento**: < 2 segundos
- **Tamanho total**: < 500KB
- **Compatibilidade**: Todos os navegadores modernos
- **Responsividade**: 100% mobile-friendly

## 🔮 Futuras Melhorias

- [ ] Integração com API real de trading
- [ ] Sistema de autenticação
- [ ] Gráficos interativos
- [ ] Notificações push
- [ ] Modo escuro/claro
- [ ] Múltiplos idiomas
- [ ] PWA (Progressive Web App)

## 📞 Suporte

Para dúvidas ou sugestões, consulte a documentação em `step-by-step/desenvolvimento.md`.

---

**Desenvolvido com 💜 usando tema roxo escuro**

*Versão 1.0.0 - Janeiro 2025*