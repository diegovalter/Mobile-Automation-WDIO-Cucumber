# 📱 Automação Mobile - Fluxo de Compra Multi-Item (WDIO + BDD)

Este projeto foca na validação de fluxos complexos de e-commerce no aplicativo **MyDemoApp**, utilizando **WebdriverIO** e **Cucumber**. O diferencial desta automação é a validação de um carrinho com múltiplos produtos, garantindo que o sistema mantenha a integridade dos itens e realize o cálculo correto do valor total.

---

## 📋 Funcionalidades Automatizadas

### 🛒 Carrinho Dinâmico e Soma de Valores

* **Navegação de Retorno:** Simula o comportamento real do usuário utilizando `driver.back()` para retornar à vitrine e adicionar novos itens sem perder a sessão.
* **Validação Multi-Item:** Uso de seletores de array (`$$`) para validar simultaneamente diversos produtos e seus respectivos preços na tela de checkout.
* **Cálculo de Total:** Verificação do somatório final (`totalPriceTV`), garantindo que a regra de negócio de preços da aplicação está correta.

---

## 🛠️ Tecnologias Utilizadas

* **WebdriverIO (v9)** — Framework de teste ponta a ponta.
* **Appium (v3)** — Automação nativa para Android.
* **Cucumber Framework** — Escrita de testes em Gherkin (BDD).
* **W3C Actions API** — Implementação de gestos de toque (`swipe`) para navegação.

---

## 🏗️ Arquitetura e Diferenciais

* **BasePage & Herança:** Centralização do método de scroll manual para reaproveitamento em todas as telas do app.
* **POM (Page Object Model):** Separação clara entre a lógica de captura de elementos e a execução dos passos do teste.
* **Seletores Avançados:** Uso de `UiSelector` por instância e `accessibility id` para garantir a estabilidade dos testes em elementos dinâmicos.

---

## 📁 Estrutura de Pastas

```text
├── features/
│   └── fluxo_compra_multi.feature # Cenários de compra múltipla
├── step-definitions/
│   └── compra.steps.js            # Lógica de passos e asserções
├── pages/
│   ├── base.page.js               # Gestos e ações globais
│   ├── products.page.js           # Vitrine e navegação
│   ├── product_details.page.js    # Detalhes e adição ao carrinho
│   └── cart.page.js               # Validação de lista e preço total
├── config/                        # Configurações Local e Sauce Labs
└── package.json                   # Dependências do projeto

```

---

## 🚀 Como Executar

1. **Setup inicial:**
```bash
npm install

```


2. **Rodar o teste (Exemplo Local):**
```bash
npm run wdio

```



---

## 💡 Observação Técnica

O uso do método `driver.performActions` garante que o movimento de "arrastar" seja suave e respeite o tempo de resposta do emulador Android, evitando que o teste falhe por tentar interagir com elementos que ainda estão fora da área visível.
