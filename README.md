# Afro-bank
Banco(Python)

---

# 🏦 Banco Python

Bem-vindo ao **Banco Python**! Este é um projeto simples de simulação de operações bancárias, onde você pode depositar, sacar e visualizar o extrato da sua conta.

## 📋 Funcionalidades

- **Depósito**: Permite ao usuário depositar um valor na conta.
- **Saque**: Permite ao usuário sacar um valor da conta, respeitando o saldo disponível, o limite diário e o número máximo de saques.
- **Extrato**: Exibe todas as transações realizadas e o saldo atual, incluindo a data e hora de cada transação.
- **Sair**: Encerra o programa.

## 🚀 Como Usar

### Requisitos

- Python 3.x

### Executando o Programa

1. Clone este repositório para o seu ambiente local.
2. Navegue até o diretório do projeto.
3. Execute o programa:

   ```bash
   python banco.py
   ```

4. Siga as instruções no menu para realizar operações bancárias.

## 📄 Exemplo de Uso

Ao iniciar o programa, você verá o seguinte menu:

```
[D] Depositar
[S] Sacar
[E] Extrato
[Q] Sair

=> 
```

### Depósito

- Selecione a opção `D` para depositar.
- Informe o valor do depósito.

### Saque

- Selecione a opção `S` para sacar.
- Informe o valor do saque.

### Extrato

- Selecione a opção `E` para visualizar o extrato.
- Será exibido um extrato com todas as transações e o saldo atual.

### Sair

- Selecione a opção `Q` para sair do programa.

## 🛠️ Código

Aqui está uma visão geral do código:

```python
from datetime import datetime

menu = """
[D] Depositar
[S] Sacar
[E] Extrato
[Q] Sair

=> """

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

def obter_data_hora():
    agora = datetime.now()
    return agora.strftime("%d/%m/%Y %H:%M:%S")

while True:
    opcao = input(menu)

    if opcao == "D":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f} - {obter_data_hora()}\n"
        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "S":
        valor = float(input("Informe o valor do saque: "))

        excedeu_saldo = valor > saldo
        excedeu_limite = valor > limite
        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou! Você não tem saldo suficiente.")
        elif excedeu_limite:
            print("Operação falhou! O valor do saque excede o limite.")
        elif excedeu_saques:
            print("Operação falhou! Número máximo de saques excedido.")
        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f} - {obter_data_hora()}\n"
            numero_saques += 1
        else:
            print("Operação falhou! O valor informado é inválido.")

    elif opcao == "E":
        print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")

    elif opcao == "Q":
        break

    else:
        print("Operação inválida, por favor selecione novamente a operação desejada.")
```

## 📊 Exemplos de Transações

![Deposito](https://example.com/deposito.png)
![Saque](https://example.com/saque.png)
![Extrato](https://example.com/extrato.png)

## 🎨 Figurinhas Legais

Para deixar este README mais divertido, aqui estão algumas figurinhas:

- 🎉 Parabéns por completar uma transação!
- 💸 Dinheiro na conta!
- 🏦 Bem-vindo ao Banco Python!

## 🤝 Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

## 📞 Contato

Se você tiver alguma dúvida, entre em contato pelo email [tiagoalmirs@gmail.com).

---
