# Screenmatch 🎬

O **Screenmatch** é uma aplicação Java backend robusta desenvolvida para o gerenciamento e exploração de séries de TV. O projeto integra o consumo de APIs externas com a persistência em bancos de dados relacionais, permitindo buscas dinâmicas e filtragens avançadas através do Spring Data JPA.

---

## 🚀 Funcionalidades

A aplicação oferece um menu interativo via console com as seguintes operações:

1.  **Busca de Séries:** Consulta dados em tempo real na API do OMDB e os persiste no banco de dados.
2.  **Gestão de Episódios:** Busca e armazena automaticamente todas as temporadas e episódios vinculados a uma série.
3.  **Consultas Inteligentes:**
    * Listagem de séries por gênero.
    * Busca de séries por nome de ator e avaliação mínima.
    * Top 5 séries com base na nota dos usuários.
    * Filtro personalizado por número de temporadas e avaliação.
    * Busca de episódios por trechos do título (uso de JPQL).
    * Filtro de episódios por data de lançamento.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Java 17
* **Framework:** Spring Boot 3
* **Persistência:** Spring Data JPA / Hibernate
* **Banco de Dados:** PostgreSQL / MySQL (Suporte via Docker)
* **Integração:** API OMDB (JSON)
* **Serialização:** Jackson Library

---

## 🔧 Como Configurar o Projeto

### 1. Pré-requisitos
* Java 17 instalado.
* Maven configurado.
* Banco de Dados (PostgreSQL/MySQL) ativo.

### 2. Variável de Ambiente
Para segurança, a chave da API do OMDB deve ser configurada como uma variável de ambiente no seu sistema (Ubuntu/Linux):

```bash
export OMDB_API_KEY="sua_chave_aqui" 
```

3. Configuração do Banco de Dados
No arquivo src/main/resources/application.properties, configure suas credenciais:


```Properties
spring.datasource.url=jdbc:postgresql://localhost:5432/nome_do_seu_banco
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update
```

📂 Estrutura de Pacotes

principal: Gerenciamento do menu e fluxo da aplicação.
model: Entidades mapeadas para o banco de dados e registros (Records) para desserialização.
repository: Interfaces que utilizam Spring Data JPA para consultas (Derived Queries e JPQL).
service: Serviços de consumo de API (HttpClient) e conversão de dados.
