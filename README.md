# 💬 Microserviço de IA em Python - SI

## 🔧 Tecnologias usadas no projeto:
- Python 3.12.1
- Docker e Docker Compose
- Ollama
- Modelo de IA: llama3.2:3b

> ⚠️ **_Não é necessário nenhum requisito e dependência de sistema além do Docker e Docker Compose_**

## ⚙️ Executando de forma local:

1) Clone o repositório para sua máquina:
    ```bash
    $ git clone https://github.com/speedlightzx/si-imobiliarias-microservico
    ```

2) Suba todos os containers do Docker Compose:
    ```bash
    $ docker compose up -d
    ```

3) Instale o modelo de IA usado pelo container do Ollama:
    ```bash
    $ docker exec ollama ollama pull llama3.2:latest
    ```

> ⚠️ **Dependendo do hardware da máquina e velocidade da internet pode levar um pouco de tempo para baixar a imagem do ollama e do modelo de IA.**


Após seguir esses passos a cima, os containers ficarão disponíveis nas seguintes URIs:

- Python FastAPI: 
    - Local: `http://localhost:8000`
    - Docker: `http://microservico-python:8000`

- Ollama:
    - Local: `http://localhost:11434`
    - Docker: `http://ollama:11434`

## 🗃️ Variáveis de ambiente:
Não é necessário nenhuma variável de ambiente.

## ❓ Como se integra com os outros serviços?
Esse microserviço de chatbot em Python se integra diretamente com o backend. Onde o backend faz uma requisição HTTP para esse microserviço com a mensagem do usuário, que é processada pela LLM e retorna para o backend que retorna para o usuário em tempo real.

## 📁 Rotas:

```http
    POST /sendMessage
```
- Recebe os seguintes campos:
    - **message**: Mensagem que será processada pelo modelo de IA
---