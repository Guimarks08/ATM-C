# ATM-C
Este projeto simula as operações fundamentais de um terminal bancário autônomo via linha de comando (CLI). O diferencial da aplicação reside no seu **algoritmo de distribuição de cédulas**, projetado para evitar a entrega excessiva de notas de alto valor (como apenas notas de R$ 100), priorizando trocos e notas menores de forma equilibrada.

O código foi rigorosamente estruturado para garantir compatibilidade com o padrão **C89** (declaração de variáveis no escopo superior) e conta com validações robustas contra entradas inválidas de usuário (`scanf`).

---

## ✨ Funcionalidades

* **Consulta de Saldo:** Visualização dinâmica do saldo atualizado em tempo real a cada transação.
* **Saque Inteligente (Modo Balanceado):**
  * Validação de saldo insuficiente e valores negativos ou zerados.
  * Restrição de múltiplos de R$ 5 (compatível com as cédulas disponíveis).
  * **Distribuição homogênea:** Garante uma proporção equilibrada entre notas de R$ 100, R$ 50, R$ 20, R$ 10 e R$ 5.
* **Depósito:**
  * Atualização imediata do saldo com validação de cédulas aceitas pelo terminal (múltiplos de 5).
* **Tratamento de Erros:** Proteção contra falhas de leitura de buffer e entradas não numéricas (`stdin`).

---

## ⚙️ Regra de Negócio do Saque (Modo Balanceado)

O algoritmo de entrega de notas opera em duas etapas principais para otimizar o troco:
1. **Passo 1 (Blocos de Cédulas):** Para valores iguais ou superiores a **R$ 185** (soma de uma unidade de cada cédula disponível: `100 + 50 + 20 + 10 + 5`), o sistema separa automaticamente um kit completo de notas.
2. **Passo 2 (Distribuição Cíclica):** O restante do valor é distribuído iterativamente utilizando uma ordem cíclica otimizada (`50, 20, 10, 5, 100`), priorizando notas menores antes de recorrer às notas máximas de R$ 100.

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
Você precisará de um compilador de C instalado em sua máquina (como `gcc`, `clang` ou MinGW).

### Passos para Compilação e Execução

1. Clone este repositório:
   ```bash
   git clone [https://github.com/Guimarks08/ATM-C.git](https://github.com/Guimarks08/ATM-C.git)
