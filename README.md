# ATM-C
# 🏧 Caixa Eletrônico (ATM) em C

Simulador de um terminal bancário (Caixa Eletrônico) desenvolvido em **Linguagem C**, focado em boas práticas de lógica de programação, validações robustas de entrada de dados e uma distribuição inteligente/balanceada de cédulas.

---

## 🚀 Funcionalidades

* **Consulta de Saldo:** O saldo inicial é fixado em **R$ 500,00** e persiste/atualiza dinamicamente a cada operação realizada.
* **Operação de Saque (Modo Balanceado):**
  * Validações completas (valores negativos, zero, saldo insuficiente e múltiplos de R$ 5[cite: 1]).
  * **Algoritmo de Distribuição Homogênea:** O caixa prioriza entregar uma variedade de notas menores em vez de esgotar o valor apenas com notas altas, utilizando um ciclo otimizado de cédulas[cite: 1].
* **Operação de Depósito:**
  * Aceita valores positivos múltiplos de R$ 5[cite: 1] e atualiza o saldo instantaneamente[cite: 1].
* **Tratamento de Erros de Entrada:** Protegido contra caracteres inválidos ou strings inseridas no terminal via `scanf`[cite: 1].

---

## ⚙️ Regras de Negócio e Lógica de Saque

O grande diferencial deste projeto está na forma como as cédulas de **R$ 100, R$ 50, R$ 20, R$ 10 e R$ 5** são distribuídas ao realizar um saque:

1. **Passo 1 (Garantia Mínima):** Para valores altos, o sistema garante a entrega proporcional de um kit completo de notas (equivalente à soma de todas as cédulas, totalizando blocos de R$ 185)[cite: 1].
2. **Passo 2 (Distribuição Cíclica):** O restante do valor é distribuído de forma iterativa priorizando notas menores e equilibrando o troco através de uma ordem cíclica de arranjo (`{50, 20, 10, 5, 100}`)[cite: 1].

---

## 💻 Compatibilidade com C89

O código foi totalmente estruturado respeitando o padrão **ANSI C (C89)**:
* Declaração de variáveis estritamente no topo dos escopos (como as variáveis auxiliares `i` e `mudou` fora dos blocos de repetição), garantindo compatibilidade com compiladores mais antigos ou rígidos[cite: 1].

---

## 🛠️ Como Executar o Projeto

### Pré-requisitos
Você precisa ter um compilador de C instalado no seu sistema (como `gcc` ou `Clang`).

### Passos para compilar e rodar via Terminal:

1. Clone o repositório:
   ```bash
   git clone [https://github.com/Guimarks08/ATM-C.git](https://github.com/Guimarks08/ATM-C.git)
