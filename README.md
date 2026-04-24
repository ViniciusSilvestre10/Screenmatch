
Screenmatch 🎬
O Screenmatch é uma aplicação Java backend desenvolvida durante o curso de Java e Spring Boot da Alura. A aplicação permite buscar informações sobre séries de TV através da API do OMDB, armazenar esses dados em um banco de dados relacional e realizar diversas consultas avançadas utilizando Spring Data JPA.

🚀 Funcionalidades
O projeto conta com um menu interativo via console que permite:

Busca Web: Busca séries pelo título diretamente na API do OMDB.

Persistência: Salva as séries e seus respectivos episódios no banco de dados.

Consultas Avançadas:

Listar todas as séries buscadas.

Buscar séries por título ou por ator.

Filtrar o Top 5 séries com melhor avaliação.

Buscar séries por categoria (Gênero).

Filtrar séries por quantidade de temporadas e avaliação mínima.

Buscar episódios por trecho do título.

Consultar o Top 5 episódios de uma série específica.

Buscar episódios lançados a partir de um determinado ano.


🛠️ Tecnologias Utilizadas
Java 17

Spring Boot 3

Spring Data JPA

PostgreSQL (ou MySQL, conforme sua configuração no Docker)

Hibernate (ORM)

Jackson (Desserialização de JSON)

API OMDB

🔧 Configuração e Execução

1. Variáveis de Ambiente
Para manter a segurança, a chave da API do OMDB não está fixada no código. Você precisa configurar uma variável de ambiente no seu sistema (Ubuntu):

Bash
export OMDB_API_KEY="sua_chave_aqui"

2. Banco de Dados
Certifique-se de que o seu banco de dados está rodando (via Docker ou local). Ajuste as credenciais no arquivo src/main/resources/application.properties:

Properties
spring.datasource.url=jdbc:postgresql://localhost:5432/screenmatch
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha

3. Executando
Você pode rodar a aplicação diretamente pelo IntelliJ IDEA ou via terminal:

Bash
mvn spring-boot:run

📂 Estrutura do Código
model: Classes de entidade (Serie, Episodio) e DTOs (DadosSerie).

repository: Interface SerieRepository que estende JpaRepository.

service: Lógica de consumo de API e conversão de dados.

principal: Classe Principal que gerencia o fluxo do menu e interação com o usuário.
