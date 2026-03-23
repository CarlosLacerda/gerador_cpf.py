# 🪪 Gerador de CPF

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat&logo=python&logoColor=white)
![Status](https://img.shields.io/badge/status-concluído-brightgreen)
![Licença](https://img.shields.io/badge/licença-MIT-blue)

> 🎲 Gera CPFs matematicamente válidos de forma aleatória — sem bibliotecas externas, puro Python.

---

## 🧮 Como funciona

O script gera 9 dígitos aleatórios e aplica o algoritmo oficial de cálculo dos **dígitos verificadores** do CPF, produzindo um número 100% válido a cada iteração.

### 🔢 Cálculo do 1º dígito
Multiplica os 9 dígitos gerados por uma contagem regressiva de 10 até 2, soma tudo, multiplica por 10 e tira o resto da divisão por 11.

### 🔢 Cálculo do 2º dígito
Repete o processo com os 10 dígitos (incluindo o 1º verificador), usando contagem regressiva de 11 até 2.

> ⚠️ Se o resultado for maior que 9, o dígito é `0`.

---

## 🗂️ Estrutura do cálculo

```
9 dígitos aleatórios:  7  4  6  8  2  4  8  9  0
                      ×10 ×9 ×8 ×7 ×6 ×5 ×4 ×3 ×2
                       70  36 48 56 12 20 32 27  0
                                       soma = 301
                                    301 × 10 = 3010
                                   3010 % 11 = 9  → 1º dígito = 9

10 dígitos:  7  4  6  8  2  4  8  9  0  9
            ×11×10 ×9 ×8 ×7 ×6 ×5 ×4 ×3 ×2
             ...          → 2º dígito calculado ✅
```

---

## ▶️ Como usar

```bash
python gerador_cpf.py
```

```
74682489097
31290547863
...
```

Por padrão gera **100 CPFs** válidos a cada execução. Para mudar a quantidade, altere o valor no `range()`:

```python
for _ in range(100):  # ← altere aqui
```

---

## ⚙️ Requisitos

- 🐍 Python 3.x
- 📦 Sem dependências externas (`random` e `sys` já vêm no Python)

---

## ⚠️ Aviso

> Este gerador é destinado **exclusivamente para fins educacionais e de teste**.
> CPFs gerados **não pertencem a nenhuma pessoa real**.
> O uso indevido de CPFs de terceiros é crime previsto em lei. 🚫

---

## 📚 Autor

Desenvolvido como exercício da **aula 64** do curso **Python 101 - Udemy**.
