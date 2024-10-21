# Sistema Bancário em Python

Este projeto implementa um sistema bancário simples utilizando Python. O objetivo é simular operações bancárias básicas como **Depósito**, **Saque** e **Extrato**, com algumas regras de negócio específicas. O sistema foi desenvolvido para um banco que busca modernizar suas operações e limitar saques diários para controle de segurança.

## Regras de Negócio

As regras do sistema bancário são as seguintes:

1. **Depósito**:
   - O sistema permite apenas **depósitos de valores positivos**.
   - Todos os depósitos realizados são armazenados e exibidos na operação de **extrato**.

2. **Saque**:
   - O usuário pode realizar até **3 saques por dia**.
   - Cada saque tem um **limite máximo de R$ 500,00**.
   - Se o saldo do usuário for insuficiente para o valor solicitado, o saque será negado.
   - Todos os saques realizados são armazenados e exibidos na operação de **extrato**.

3. **Extrato**:
   - O extrato lista todos os depósitos e saques realizados pelo usuário.
   - Ao final da listagem, o **saldo atual** da conta é exibido.
   - Caso o extrato não possua movimentações, o sistema exibe a mensagem: **"Não foram realizadas movimentações."**
   - Todos os valores são exibidos no formato monetário (por exemplo, `1500.45` será exibido como **R$ 1500,45**).

## Funcionalidades

O sistema possui as seguintes funcionalidades:

- **Depósito**: O usuário pode adicionar dinheiro à sua conta, desde que o valor seja válido (positivo).
- **Saque**: O usuário pode sacar dinheiro da conta com as seguintes regras:
  - Limite de **3 saques diários**.
  - O valor de cada saque não pode exceder **R$ 500,00**.
  - Se o saldo for insuficiente ou o número de saques for excedido, a operação será negada.
- **Extrato**: Exibe todas as movimentações realizadas (depósitos e saques) e o saldo atual.
- **Sair**: O usuário pode encerrar o sistema a qualquer momento.

## Explicação do Código
O sistema bancário foi implementado com as seguintes funções:

- **`exibir_menu()`**: Exibe o menu de opções para o usuário.
- **`depositar(saldo, extrato, valor)`**: Função que realiza a operação de depósito, garantindo que o valor seja positivo.
- **`sacar(saldo, extrato, valor, limite, numero_saques, limite_saques)`**: Função que gerencia a operação de saque, verificando as regras de limite diário de saques e saldo disponível.
- **`exibir_extrato(saldo, extrato)`**: Exibe o extrato com todas as movimentações (depósitos e saques) e o saldo atual.
- **`sistema_bancario()`**: Função principal que mantém o sistema rodando, gerenciando o loop de operações.

### Detalhes Adicionais

- **Controle de Limite de Saques**:
  - A função `sacar()` verifica se o número de saques diários atingiu o limite de 3 saques ou se o valor solicitado excede R$ 500,00.

- **Formatação de Valores**:
  - Todos os valores monetários são formatados no padrão brasileiro (R$ xxx,xx), utilizando a formatação `f"R$ {valor:.2f}"`.

- **Mensagens de Erro**:
  - O sistema exibe mensagens claras quando o saque falha devido à falta de saldo, excedência de limite de saque ou número máximo de saques atingido.

## Melhorias Futuras

Este sistema bancário básico pode ser expandido para incluir:

- **Autenticação de Usuários**: Garantir que apenas usuários autenticados possam acessar o sistema.
- **Persistência de Dados**: Armazenar os dados em um banco de dados ou arquivos para manter as informações entre diferentes execuções.
- **Interface Gráfica**: Implementar uma interface gráfica para melhorar a experiência do usuário.
- **Taxas de Serviço**: Adicionar taxas para operações de saque ou depósito, para monetizar o sistema.

## Contribuição

Contribuições são bem-vindas! Se você tiver sugestões ou melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request.
