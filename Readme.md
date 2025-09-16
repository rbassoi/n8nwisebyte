# Tutorial: Instalação e Configuração da Estrutura para Agente de IA Local

---

<div align="center">
  <img src="./imagens/WAHA+n8n.png" alt="WAHA+n8n" width="200">
</div>

---

## Introdução

Este tutorial vai guiar você através do processo de instalação e configuração da nossa estrutura para criação de um Agente de IA Local, incluindo os componentes:

- **WAHA**: API de Whatsapp gratuita
- **n8n**: Plataforma de automação
- **Redis**: Banco de dados em memória para registro de chats
- **PostgreSQL** (Opcional): Banco de dados relacional para uso geral

## Pré-requisitos

- Ter o Docker Desktop instalado [Baixe aqui](https://www.docker.com/get-started/) pois para o MVP iremos utilizar localmente
- Sistema operacional Windows 10, Windows 11, Linux ou MacOs (de acordo com o docker compose)

## Passo a Passo

### 1. Faça download deste repositório:
![Baixando o repositório](./imagens/passo1.gif)



### 2. Extraia o arquivo e abra a pasta:
![Extraindo o arquivo](./imagens/passo1.2.gif)



### 3. Abra um terminal na pasta e digite o comando:
```bash
docker-compose up -d
```
*Isso irá baixar e instalar todos os programas no seu computador local.*

![Comando docker-compose](./imagens/passo2.gif)



### 4. Acessando os programas:

*Você pode acessar os programas no seu navegador clicando no link do container  através do seu aplicativo Docker Desktop.*

![Acessando os programas](./imagens/passo4.gif)



### 5. Instale os nodes do WAHA no N8N:

*Vá no painel settings > community nodes, clique em "install a community node" e digite:*
```bash
n8n-nodes-waha
```

![Instalando nodes do WAHA](./imagens/passo5.gif)



### 6. Conectando credenciais:

*Ao conectar as credenciais dos outros programas no N8N, você deve se atentar ao seguinte detalhe: **SEMPRE SUBSTITUA a palavra "localhost" por "host.docker.internal"**.*

```bash
host.docker.internal
```

*Todos os users e senhas estão configurados como "default".* 

*Exemplo:*

![Conectando credenciais](./imagens/passo6.gif)

---

## Integração do Whatsapp no N8N

### 1. Conecte seu whatsapp no WAHA através do Qr Code no dashboard:

![Conectando whatsapp](./imagens/passo7.gif)



### 2. Conecte o WAHA ao N8N:

*Deixei a variável global do Webhook configurada como:*
```bash
http://host.docker.internal:5678/webhook/webhook
```
*Então, tudo que você precisa fazer é criar um novo workflow, adicionar um webhook e configurá-lo da seguinte forma:*

![Conectando WAHA ao N8N](./imagens/passo8.png)

*Você verá os eventos que chegaram no seu painel "executions" dentro do workflow do n8n.*

*Você também pode copiar a URL de teste e colar diretamente nas configurações da sessão no dashboard do Waha:*

![Conectando WAHA ao N8N](./imagens/passo9.gif)

*Essas URLS que colamos através do dashboard somem após reiniciarmos o container, então, toda vez que quiser desenvolver, lembre-se de copiar a URL de teste e colar diretamente nas configurações da sessão no dashboard do Waha.*

![Dados dentro do N8N](./imagens/passo10.png)

---

## Conclusão

Parabéns! Você agora tem uma estrutura completa para criar seu Agente de IA de forma Local funcionando!


## Recursos Adicionais

- [Documentação do WAHA](https://waha.devlike.pro/docs/overview/introduction)

---

*Última atualização: 07/05/2025*
