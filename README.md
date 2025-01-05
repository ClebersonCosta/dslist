# Projeto DSList
Esta API foi desenvolvida com o objetivo de demonstrar a utilização do Spring com JPA e seguindo padrão de camadas Controller, Service e Respository com o uso de DTO.

### Controller
É responsável por receber as requisições HTTP e entregar para a camada de Service.

### Service
Essa camada contém a lógica de negócios e interage com o camada Repository. Essa camada é importante para que as regras de negócios não se misture com o acesso aos dados.

### Repository
Essa camada é responsável por interagir com o banco de dados. Com o uso do JPA é possível realizar operações simples sem a necessidade de escrever código SQL.

### Entidades
As entidades representam as tabelas do banco de dados relacional.

### Tecnologias Utilizadas
- Java 17
- Spring Boot
- Spring JPA
- PostgreSQL
- Maven

## Instruções de Instalação

### Pre Requisitos
- Java 17+
- Maven

### Instalação

1. Clone o repositório
   
```bash
  git clone https://github.com/ClebersonCosta/dslist.git
  cd dslist
```

2. Instale as dependências do maven

```bash
  mvn install
```

3. Gere o JAR do projeto

```bash
  mvn clean package
```

4. Rode o JAR gerado

```bash
  java -jar target/dslist-0.0.1-SNAPSHOT.jar
```

# API Endpoints

## GET /games

**Descrição:** retorna um JSON com uma lista dos jogos e uma curta descrição
  ```bash
{
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
},
{
    "id": 2,
    "title": "Red Dead Redemption 2",
    "year": 2018,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/2.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
}
  ```

## GET /games/{id}

**Descrição:** retorna um JSON com dados detalhados do jogo
```bash
{
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "genre": "Role-playing (RPG), Shooter",
    "platforms": "XBox, Playstation, PC",
    "score": 4.8,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!",
    "longDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus dolorum illum placeat eligendi, quis maiores veniam. Incidunt dolorum, nisi deleniti dicta odit voluptatem nam provident temporibus reprehenderit blanditiis consectetur tenetur. Dignissimos blanditiis quod corporis iste, aliquid perspiciatis architecto quasi tempore ipsam voluptates ea ad distinctio, sapiente qui, amet quidem culpa."
}
```

## GET /lists

**Descrição:** retorna um JSON com a categoria dos jogos
```bash
{
    "id": 1,
    "name": "Aventura e RPG"
}
```

## GET /lists/{id}/games

**Descrição:** retorna um JSON com o jogos filtrados conforme a categoria
```bash
{
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
},
{
    "id": 2,
    "title": "Red Dead Redemption 2",
    "year": 2018,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/2.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
}
```

# Melhorias Futuras
- Integrar API com frontend
- Criar endpoint para cadastro (POST)