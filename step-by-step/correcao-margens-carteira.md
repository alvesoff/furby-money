# Correção de Margens da Página da Carteira

## Problema Identificado
A página `carteira.html` estava sem bordas horizontais, fazendo com que o conteúdo ficasse colado nas margens da tela, prejudicando a experiência visual e a legibilidade.

## Solução Implementada

### 1. Correção do Main Content
Adicionado CSS para o elemento `.main-content` com as seguintes propriedades:

```css
.main-content {
    max-width: 1200px;
    margin: 0 auto;
    padding: 30px 20px 100px;
}
```

### 2. Correção do Header
Modificado CSS para o elemento `.header .container` adicionando:

```css
.header .container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}
```

### Detalhes da Solução:
- **max-width: 1200px**: Define uma largura máxima para o conteúdo
- **margin: 0 auto**: Centraliza o conteúdo horizontalmente
- **padding**: Adiciona espaçamento interno (20px nas laterais)

## Arquivos Modificados
- `styles.css`: Adicionado estilo para `.main-content` e modificado `.header .container`

## Resultado
Agora a página da carteira possui margens horizontais adequadas, evitando que o conteúdo fique colado nas bordas da tela e melhorando a experiência visual do usuário.

## Data da Implementação
25 de dezembro de 2024