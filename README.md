
# 📚 Desafio de Projeto | DIO 
## Criando um Sistema Bancário com Python

Repositório criado para armazenar minhas entregas do Desafio de Projeto - Criando um Sistema Bancário com Pyhton do curso Dominando Python para Ciência de Dados.

Link para especificações do curso [Digital Innovation One](https://web.dio.me/track/potencia-tech-powered-ifood-ciencias-de-dados-com-python).

## 📚 Regras do Desafio 

### 1ª Regra: Do depósito
- Aceitar somente valor de depósito positivo.
- Todos os depósitos devem ser armazenados em uma variável e exibidos na operação extrato.
### 2ª Regra: Do saque
- O sistema deve permitir realizar somente 3 saques com limite máximo de R$ 500  por saque.
- Caso usuário não tenho saldo em conta, deverá exibir uma mensagem na tela informando que não é possível sacar o dinheiro por falta de saldo.
- Todos os saques devem ser armazenados em uma váriavel e exibidos na operação de extrato.
### 3ª Regra: Do extrato
- Essa operação deve listar todos os depósitos e saque realizados na conta. 
- Ao final do extrato deverá exibir o saldo atual da conta bancária.
- Se o extrato estiver em branco, exibir uma mensagem informando que não houve movimentações na conta.
- Os valores devem ser exibidos no formato: R$ xxx.xx

## 💻 Meu código entregue

```
menu = """
   --============ MENU =============--
   |                                 |   
   | [1] Depositar                   |       
   | [2] Sacar                       |   
   | [3] Extrato                     |   
   | [0] Sair                        |  
   |                                 |                                
   --===============================--
=> Digite a opção desejada: """

saldo = 0 
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)

        #OPERAÇÃO DE DEPÓSITO = LINHAS DE 22 A 30

    if opcao == "1":
        valor = float(input("Informe o valor do depósito: "))

        if valor > 0:
            saldo += valor
            extrato += f"Depósito: R$ {valor:.2f}\n"

        else:
            print("Operação falhou! O valor informado é inválido.")

        #OPERAÇÃO DE SAQUE = LINHAS DE 34 A 58

    elif opcao == "2":
        valor = float(input("Informe o valor do saque: "))

        excedeu_saldo = valor > saldo

        excedeu_limite = valor > limite

        excedeu_saques = numero_saques >= LIMITE_SAQUES

        if excedeu_saldo:
            print("Operação falhou. Você não tem saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou. O valor do saque excede o limite.")

        elif excedeu_saques:
            print("Operação falhou. O número máximo de saques excedido.")

        elif valor > 0:
            saldo -= valor
            extrato += f"Saque: R$ {valor:.2f}\n"
            numero_saques += 1

        else:
            print("Operação falhou: O valor informado é inválido")

        #OPERAÇÃO DE EXTRATO = LINHAS 62 A 66

    elif opcao == "3":
        print("\n================ EXTRATO ================")
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("=========================================")

        #FIM DO CÓDIGO CASO NÃO SEJA PREENCHIDO NENHUMA OPERAÇÃO

    elif opcao == "0":
        break

    else:
        print("Operação inválida. Por favor, selecione novamente a operação desejada.")
```


## 📸Screenshots
### Menu
![image](https://github.com/hudsonfarias/desafio-projeto/assets/138171591/393511d9-0767-4b90-9736-8caeb6cf3079)
### Depósito
![image](https://github.com/hudsonfarias/desafio-projeto/assets/138171591/a73a97e5-7606-4e67-96e1-91f870b4251c)
### Saque
![image](https://github.com/hudsonfarias/desafio-projeto/assets/138171591/dce6ee1f-4ca1-4a0e-a00b-c112ed94ca67)
### Extrato 
![image](https://github.com/hudsonfarias/desafio-projeto/assets/138171591/3b6373f6-0b62-4f83-aeb7-ee53d869a252)







Obrigado por ver meu projeto! 😀
