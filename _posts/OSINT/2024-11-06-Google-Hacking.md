---
title: "Google Hacking"
classes: wide
header:
  teaser: /assets/images/Google-Hacking/logo.png
  overlay_image: /assets/images/Google-Hacking/logo.png
  overlay_filter: 0.5
ribbon: DarkSlateGray
excerpt: "É essencial utilizar essas práticas de maneira ética, respeitando leis e políticas de uso."
description: "É essencial utilizar essas práticas de maneira ética, respeitando leis e políticas de uso."
categories:
  - OSINT
tags:
  - OSINT
  - Google Hacking
  - Dorks
  - Webcam
  - Search
  - Hacking
  - Test
toc: true
toc_sticky: true
toc_label: "On This Blog"
toc_icon: "biohazard"
---
# Introdução
O Google Hacking, também conhecido como Google Dorking, é uma técnica que usa operadores de busca avançados do Google para encontrar informações potencialmente sensíveis ou não intencionais em sites e servidores. Essa prática é frequentemente utilizada por profissionais de segurança para identificar vulnerabilidades e dados expostos publicamente na web. Com o uso de operadores de busca específicos, é possível localizar desde arquivos confidenciais até sistemas abertos e câmeras expostas na internet.

# Principais Operadores de Busca
Para realizar buscas eficientes com Google Hacking, é fundamental conhecer e utilizar os operadores oferecidos pelo Google. Abaixo estão os operadores mais comuns:

- **site:** - Restringe a pesquisa a um domínio específico.
  - Exemplo: `site:example.com`
- **intitle:** - Procura por termos específicos no título da página.
  - Exemplo: `intitle:"index of"`
- **inurl:** - Busca por palavras específicas na URL.
  - Exemplo: `inurl:admin`
- **filetype:** - Filtra os resultados por um tipo de arquivo específico.
  - Exemplo: `filetype:pdf "confidential"`
- **cache:** - Acessa a versão em cache de uma página, o que pode revelar conteúdos que já foram removidos.
  - Exemplo: `cache:example.com`

Esses operadores podem ser combinados para refinar ainda mais os resultados, tornando a busca por informações específicas mais precisa.

![image.png](/assets/images/Vidar-Stealer-Camapign/1.png)

# Exemplos Práticos de Google Hacking
Abaixo estão alguns exemplos de como os operadores podem ser utilizados para encontrar informações sensíveis:

1. **Encontrar Painéis de Administração**
   ```plaintext
   inurl:admin
   ```
   Esse comando pesquisa URLs que contenham o termo "admin", o que pode revelar painéis de administração.

2. **Documentos Confidenciais**
   ```plaintext
   filetype:pdf "confidential"
   ```
   Esse comando busca arquivos PDF contendo a palavra "confidential", que podem conter informações sensíveis.

3. **Pastas com Índices Públicos**
   ```plaintext
   intitle:"index of" "backup"
   ```
   Esse comando localiza páginas que contêm índices de diretórios, geralmente usados para armazenar backups.

4. **Identificar Câmeras e Dispositivos de IoT**
   ```plaintext
   inurl:"/view/view.shtml"
   ```
   Esse comando ajuda a localizar câmeras públicas acessíveis via web, muitas vezes sem autenticação adequada.

# Ética e Responsabilidade
Embora o Google Hacking seja uma ferramenta poderosa para profissionais de segurança, também pode ser usado de forma mal-intencionada. É fundamental que essas práticas sejam conduzidas de maneira ética, respeitando leis e políticas de uso. Para aqueles que atuam como pentesters, é recomendável obter autorização explícita antes de coletar qualquer dado sensível.

# Lista de Dorks Comuns
Aqui estão alguns exemplos de Google Dorks populares:

- **Painéis de login**:
  - `inurl:login`
  - `intitle:"admin panel"`
  - `inurl:wp-admin`

- **Câmeras de segurança**:
  - `inurl:"/view/view.shtml"`
  - `inurl:viewerframe?mode=`
  - `inurl:axis-cgi/jpg`

- **Arquivos de backup e bancos de dados**:
  - `intitle:"index of" "backup"`
  - `filetype:sql "database"`
  - `filetype:bak "database backup"`

- **Documentos confidenciais**:
  - `filetype:pdf "confidential"`
  - `filetype:xls "password"`
  - `filetype:docx "internal use only"`

- **Informações de contato**:
  - `intext:"email" filetype:xls`
  - `intext:"telefone" filetype:txt`
  - `inurl:contatos`

Esses dorks devem ser usados com cautela e sempre respeitando as políticas de uso e a legislação aplicável.

## Conclusão
O Google Hacking é uma técnica valiosa para pesquisadores de segurança e profissionais de TI que desejam identificar informações potencialmente expostas. Com o uso adequado e ético dessas ferramentas, é possível aumentar a segurança cibernética, evitando que dados sensíveis sejam acessados por pessoas não autorizadas. A prática responsável e o respeito às leis são fundamentais para que o uso de Google Dorks se mantenha ético e contribua para a proteção de dados online.

# References
- [Exploit Database - Google Hacking Database](https://exploit-db.com/google-hacking-database)
- [OWASP](https://owasp.org)
- [Google Advanced Search Help](https://support.google.com)

