# enco6a-tdd

Exercício prático de **Test-Driven Development (TDD)** aplicado a uma calculadora de descontos, com refatoração utilizando o padrão de projeto **Strategy**.

## Descrição

Implementação de uma calculadora de descontos que suporta três políticas:

- **Sem desconto** — retorna o valor original.
- **Desconto percentual** — aplica um percentual fixo (ex.: 10%).
- **Desconto por cupom** — subtrai um valor fixo (ex.: R$ 20,00), nunca resultando em valor negativo.

## Ciclos TDD

O desenvolvimento segue os três ciclos clássicos do TDD:

### 🔴 Red
Testes unitários escritos antes de qualquer implementação. Os testes falham intencionalmente nesta etapa.

```
git commit -m "red: testes iniciais"
```

### 🟢 Green
Implementação mínima para fazer todos os testes passarem, sem preocupação com elegância ou estrutura.

```
git commit -m "green: implementação mínima"
```

### 🔵 Refactor
Aplicação do padrão **Strategy** para separar cada política de desconto em sua própria classe, mantendo a interface pública inalterada e todos os testes passando.

```
git commit -m "refactor: padrão Strategy aplicado"
```

## Padrão de Projeto

Após a refatoração, a arquitetura segue o padrão **Strategy**:

```
DiscountStrategy (ABC)
├── NoDiscount
├── PercentageDiscount
└── CouponDiscount

DiscountCalculator (Contexto)
```

Cada estratégia implementa o método `calculate(value)` definido na interface abstrata `DiscountStrategy`.

> Referência: [Refactoring Guru — Strategy Pattern](https://refactoring.guru/design-patterns/strategy)

## Estrutura do Repositório

```
enco6a-tdd/
├── enco6a_tdd.py       # Código-fonte com os três ciclos TDD
├── enco6a_tdd.ipynb    # Notebook Google Colab com o desenvolvimento
└── LICENSE             # GPL-3.0
```

## Execução

O notebook foi desenvolvido no Google Colab. Para rodar localmente:

```bash
python enco6a_tdd.py
```

Ou abra o arquivo `.ipynb` no Jupyter ou Google Colab.

## Requisitos

- Python 3.x
- Biblioteca padrão `unittest` (sem dependências externas)

## Licença

Distribuído sob a licença [GPL-3.0](LICENSE).
