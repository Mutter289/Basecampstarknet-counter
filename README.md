
# Starknet Counter Smart Contract

Um projeto desenvolvido em linguagem Cairo, onde é feito um Smart Contract e tem funções de visualizar saldo e aumentar saldo,


## Ferramentas necessárias
- scarb 2.6.5
- starkli 0.3.4
- starknet-devnet 0.1.2

## Váriaveis necessárias
Primeiro criamos a keystore.
```
.c-wallets/account0_keystore.json
```
Por ultimo criamos a conta.
```
.c-wallets/account0_account.json
```

## Implantação

Para implantar este projeto, primeiro você deve rodar o starknet-devnet

```bash
starknet-devnet --seed 2525635640
```
Agora vamos declarar o contrato
```bash
starkli declare target/dev/counter_CounterContract.contract_class.json --rpc http://0.0.0.0:5050 --account .c-wallets/account0_account.json --keystore .c-wallets/account0_keystore.json
```
Por fim iremos fazer a Implantação
```bash
starkli deploy --rpc http://0.0.0.0:5050 --account .c-wallets/account0_account.json --keystore .cwallets/account0_keystore.json 0x0044eb2c9de13bd3bfa49aec7339a2a6af6aa20ff2380fc2fb0c62119b4a05e5 0x12
```
## Testes

Vamos utilizar as funções para manipular o contrato, começando pela função "get_contador".
```bash
starkli call --rpc http://0.0.0.0:5050
0x025036430167a1a28d9a89b7cdba09526fcff7b3aa5cd6961904aeb232b61924 get_contador
```
Output:
```bash
"0x0000000000000000000000000000000000000000000000000000000000000012"
```
Agora vamos utilizar a nossa outra função, a "increase_contador"
```bash
starkli invoke --rpc http://0.0.0.0:5050 --account .c-wallets/account0_account.json --keystore .cwallets/account0_keystore.json
0x025036430167a1a28d9a89b7cdba09526fcff7b3aa5cd6961904aeb232b61924 increase_contador
```
Essa função adicionou 1 ao valor do contrato, logo, ao utilizar a função "get_contador" novamente é possível ver que irá aparecer:
```bash
"0x0000000000000000000000000000000000000000000000000000000000000013"
```

## Authors

- [@Mutter289](https://www.github.com/Mutter289)


## Skills

- ![Cairo](https://starkware.co/wp-content/uploads/2021/05/logoicon.svg) Cairo Language
