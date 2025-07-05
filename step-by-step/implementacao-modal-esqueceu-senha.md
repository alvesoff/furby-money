# Implementação do Modal "Esqueceu a Senha?"

Este documento descreve a implementação do modal que é exibido quando o usuário clica no link "Esqueceu sua senha?" na página de login.

## Alterações Realizadas

### 1. Adição de ID ao Link de Esqueceu a Senha

Adicionamos um ID ao link "Esqueceu sua senha?" para poder referenciá-lo no JavaScript:

```html
<div class="forgot-password">
    <a href="#" id="forgot-password-link">Esqueceu sua senha?</a>
</div>
```

### 2. Criação da Estrutura HTML do Modal

Adicionamos a estrutura HTML do modal no final do corpo da página, antes do script:

```html
<!-- Modal de Esqueceu a Senha -->
<div id="forgot-password-modal" class="modal">
    <div class="modal-content">
        <span class="close-modal">&times;</span>
        <h2>Recuperação de Senha</h2>
        <p>Por favor, notifique o suporte através do email:</p>
        <p class="support-email">Furby@trading.com</p>
        <div class="modal-footer">
            <button class="modal-btn" id="close-modal-btn">Fechar</button>
        </div>
    </div>
</div>
```

### 3. Adição de Estilos CSS para o Modal

Adicionamos os estilos CSS necessários para o modal, incluindo animações de entrada e saída, cores, posicionamento e responsividade:

```css
/* Estilos do Modal */
.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.7);
    backdrop-filter: blur(5px);
    animation: fadeIn 0.3s ease;
}

.modal-content {
    background: rgba(15, 23, 42, 0.95);
    margin: 10% auto;
    padding: 30px;
    border-radius: 20px;
    width: 90%;
    max-width: 500px;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
    border: 1px solid rgba(255, 255, 255, 0.1);
    position: relative;
    animation: slideDown 0.4s ease;
}

/* ... outros estilos do modal ... */
```

### 4. Implementação do JavaScript para Controlar o Modal

Adicionamos o código JavaScript para controlar a abertura e fechamento do modal:

```javascript
// Modal de Esqueceu a Senha
const modal = document.getElementById('forgot-password-modal');
const forgotPasswordLink = document.getElementById('forgot-password-link');
const closeModalBtn = document.querySelector('.close-modal');
const closeModalFooterBtn = document.getElementById('close-modal-btn');

// Abrir o modal quando clicar no link
forgotPasswordLink.addEventListener('click', (e) => {
    e.preventDefault();
    modal.style.display = 'block';
    document.body.style.overflow = 'hidden'; // Impede rolagem da página
});

// Fechar o modal quando clicar no X
closeModalBtn.addEventListener('click', () => {
    modal.style.display = 'none';
    document.body.style.overflow = 'auto'; // Permite rolagem da página novamente
});

// Fechar o modal quando clicar no botão Fechar
closeModalFooterBtn.addEventListener('click', () => {
    modal.style.display = 'none';
    document.body.style.overflow = 'auto'; // Permite rolagem da página novamente
});

// Fechar o modal quando clicar fora dele
window.addEventListener('click', (e) => {
    if (e.target === modal) {
        modal.style.display = 'none';
        document.body.style.overflow = 'auto'; // Permite rolagem da página novamente
    }
});
```

## Funcionalidade

Quando o usuário clica no link "Esqueceu sua senha?", um modal é exibido com a mensagem para notificar o suporte através do email Furby@trading.com. O modal pode ser fechado de três maneiras:

1. Clicando no botão "X" no canto superior direito
2. Clicando no botão "Fechar" na parte inferior do modal
3. Clicando fora da área do modal

O modal também impede a rolagem da página enquanto está aberto, para melhorar a experiência do usuário.

## Considerações de Design

- O modal segue o mesmo estilo visual do restante da aplicação, com cores, fontes e efeitos consistentes
- Foram adicionadas animações suaves para melhorar a experiência do usuário
- O design é responsivo e se adapta a diferentes tamanhos de tela
- O email de suporte é destacado visualmente para facilitar a visualização