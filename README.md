# Tutorial Flyway com Spring Boot

Um breve tutorial de como usar o flyway em um projeto Spring.

## Setup

- Java 17
- Maven
- Postgres


### 1. Como o Flyway funciona?

O Flayway faz o acompanhamento das migrações que já aplicamos e quando aplicamos, adicionando uma tabela especial de contabilidade ao nosso esquema. Essa tabela de metadados também rastreia soma de verificação e se as migrações foram bem sucedidas ou não.

O Flayway executa os seguintes passos para acomodar os esquemas no banco de dados:

1. Ele verifica o esquema do banco de dados para localizar a tabela com os metadados. Se essa tabela não existir, ele cria ela.
2. Ele escaneia o classpath da aplicação para uma migração disponivel.
3. Ele compara as migrations com os dados contidos na tabela especial. Se o numero da versão for menor ou igual ao da versão marcada como atual, então ele ignora.
4. Ele marca todas as migrations remanecentes como migrations pendentes. Essas são classificadas baseada na versão marcada como atual e executadas em ordem.
5. Assim que cada migration for aplicada, a nossa tabela especial é atualizada conformemente. 










Referências:

https://flywaydb.org/documentation/getstarted/why
https://www.baeldung.com/database-migrations-with-flyway
https://flywaydb.org/documentation/getstarted/how
