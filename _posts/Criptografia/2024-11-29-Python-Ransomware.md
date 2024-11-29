---
title: "Ransomware em Python"
classes: wide
header:
  teaser: /assets/images/Ransomware/th.jpg
  overlay_image: /assets/images/Ransomware/th.jpg
  overlay_filter: 0.5
ribbon: DarkSlateGray
excerpt: "Vou te mostrar como funciona um ransomware na prática!"
description: "Vou te mostrar como funciona um ransomware na prática!"
categories:
  - Encryption 
tags:
  - Encryption
  - Base64
  - Ransomware
  - Python
  - Project
  - Hacking
  - Test
toc: true
toc_sticky: true
toc_label: "On This Blog"
toc_icon: "biohazard"
---
# Exemplo de Ransomware Simples em Python 🐍💻

Você já se perguntou como funciona o processo de criptografar e descriptografar arquivos? 🤔 Hoje, vou compartilhar com vocês um exemplo simples de **ransomware** feito em Python! Antes que você pense em algo malicioso, vou deixar claro: o objetivo deste código é **educacional**. Ele foi feito para te ajudar a entender conceitos básicos de criptografia e como os ransomware podem operar de forma simplificada. Vamos dar uma olhada no que o código faz e como você pode usá-lo!

## O que o código faz?

Este script em Python tem como objetivo simular um **ransomware simples**, que criptografa um arquivo em Base64. A ideia é mostrar como a criptografia pode ser aplicada em arquivos de maneira simples, sem entrar em detalhes complexos de algoritmos avançados.

### Funcionalidades do código:
- O script oferece um **menu interativo** com opções:
  - **Criptografar um arquivo**: O script vai pegar um arquivo de texto (`archive.txt`) e transformá-lo em uma sequência codificada de Base64.
  - **Descriptografar um arquivo**: A sequência codificada de Base64 será revertida ao formato original do arquivo.
  - **Sair do programa**: Para encerrar a execução do script.

### Como funciona a criptografia?
O código utiliza a codificação **Base64** para criptografar e descriptografar arquivos. A codificação Base64 transforma dados binários (como o conteúdo de um arquivo) em uma string de texto ASCII. Isso é o que você vê quando o arquivo é "criptografado" — ele se torna uma longa sequência de caracteres que não pode ser lida facilmente.

**Exemplo visual do processo**:  
![base64.png](/assets/images/Ransomware/base64.png)

## Como funciona o código? 🧑‍💻

Agora vamos dar uma olhada no código e entender como ele funciona:

### 1. **Função `colorir`**

Essa função é responsável por adicionar cores ao texto exibido no terminal. As cores são definidas por códigos ANSI, o que permite que o texto se destaque. Quando o código exibe algo como "**ARQUIVO CRIPTOGRAFADO COM SUCESSO!**", ele é colorido em verde para chamar atenção.

**Exemplo visual do terminal colorido**:  
![colorido.png](/assets/images/Ransomware/colorido.png)

```python
def colorir(texto, cor):
    cores = {
        "vermelho": "[91m",
        "amarelo": "[93m",
        "verde": "[92m",
        "azul": "[94m",
        "reset": "[0m",
    }
    return f"{cores.get(cor, '')}{texto}{cores['reset']}"
```

### 2. **Função `criptografar_arquivo`**

Esta função abre o arquivo no modo binário (`'rb'`), lê o conteúdo e o criptografa utilizando a codificação Base64. Após a criptografia, o arquivo é sobrescrito com a versão criptografada.


```python
def criptografar_arquivo(caminho_arquivo):
    with open(caminho_arquivo, 'rb') as file:
        conteudo = file.read()

    arquivo_criptografado = base64.b64encode(conteudo)

    with open(caminho_arquivo, 'wb') as file:
        file.write(arquivo_criptografado)
```

### 3. **Função `descriptografar_arquivo`**

Aqui, o processo é revertido: o arquivo criptografado é lido, e a codificação Base64 é decodificada para restaurar o conteúdo original.

**Exemplo da transformação do conteúdo do arquivo teste**:
![exemplo.png](/assets/images/Ransomware/exemplo.png)

```python
def descriptografar_arquivo(caminho_arquivo):
    with open(caminho_arquivo, 'rb') as file:
        arquivo_criptografado = file.read()

    arquivo_descriptografado = base64.b64decode(arquivo_criptografado)
    
    with open(caminho_arquivo, 'wb') as file:
        file.write(arquivo_descriptografado)
```

### 4. **Função `exibir_menu`**

Este é o menu interativo que permite ao usuário escolher entre as opções de criptografar, descriptografar ou sair. Ele exibe um menu colorido e solicita a entrada do usuário.

```python
def exibir_menu():
    print(colorir("+-----------------------------+", "vermelho"))
    print(colorir("|       LOCK-TEST MENU       |", "vermelho"))
    print(colorir("+-----------------------------+", "vermelho"))
    print(colorir("| [1] Criptografar arquivo   |", "amarelo"))
    print(colorir("| [2] Descriptografar arquivo|", "amarelo"))
    print(colorir("| [0] Sair                   |", "amarelo"))
    print(colorir("+-----------------------------+", "vermelho"))
    return input(colorir("Escolha uma opção: ", "verde"))
```

## Como usar o script? 🛠️

1. **Prepare o ambiente**: 
   Certifique-se de ter o **Python** instalado no seu sistema.
   
2. **Baixe ou clone o repositório**:
   O código está disponível para download ou clonagem diretamente no [GitHub](https://github.com/CH40S-BR/Lock-Test-Ransomware).

3. **Crie um arquivo para testar**:
   No mesmo diretório onde o script está localizado, crie um arquivo chamado `archive.txt`. Esse será o arquivo criptografado e descriptografado.

4. **Execute o script**:
   No terminal, execute o seguinte comando para rodar o script:
   ```bash
   python ransomware.py
   ```

5. **Escolha uma opção**:
   O programa vai te mostrar um menu com as seguintes opções:
   - **1** para criptografar o arquivo.
   - **2** para descriptografar o arquivo.
   - **0** para sair do programa.

Após escolher uma opção, o script realizará a ação de criptografar ou descriptografar o arquivo `archive.txt` automaticamente.

## Por que isso é útil? 🤔

O objetivo principal desse código é ajudar a entender como a criptografia funciona de forma básica. Ao entender esse processo simples, você pode aprender como proteger dados e começar a explorar tópicos mais avançados de **segurança cibernética**.

## ⚠️ Atenção

Embora este código simule o comportamento de um ransomware, **não é um ransomware real**. Ele foi feito **somente para fins educacionais**. Não recomendamos o uso desse código em ambientes de produção ou para qualquer tipo de uso malicioso. 

A ética em programação e segurança é extremamente importante, e sempre deve ser levada em conta ao desenvolver qualquer tipo de software relacionado à segurança digital.

Fique à vontade para estudar, modificar e melhorar o código, mas lembre-se de sempre utilizar seus conhecimentos de forma responsável! 🌐🔒
