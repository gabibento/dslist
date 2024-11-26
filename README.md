# DSList

DSList é um projeto desenvolvido durante o **Intensivão Java Spring** da [DevSuperior](https://devsuperior.com.br/), ministrado pelo professor Nelio Alves. O objetivo foi construir uma API REST para gerenciar uma lista de jogos, com foco em boas práticas de desenvolvimento, organização em camadas, e utilização de tecnologias modernas como Java e Spring Boot.  

## 🖥️ Sobre o projeto  

A **DSList** é uma aplicação que permite listar e organizar jogos em diferentes listas, associando cada jogo a uma posição específica em uma lista personalizada. A API segue padrões de mercado, com código limpo e organização estruturada, ideal para aprendizado e aplicações reais.  

### Modelo de Domínio  

O modelo de domínio do projeto é composto por três entidades principais:  

- **Game**: Representa um jogo com informações como título, ano, gênero, plataformas, pontuação, imagens e descrições.  
- **GameList**: Representa uma lista de jogos.  
- **Belonging**: Classe de associação que conecta jogos a listas, permitindo definir a posição de cada jogo em uma lista específica.  

#### Diagrama de Domínio  

![image](https://github.com/user-attachments/assets/0d5006de-2a95-4e3d-bddc-9b470e880651)


## 🚀 Tecnologias utilizadas  

- **Java 17**  
- **Spring Boot 3**  
- **JPA / Hibernate**  
- **Banco de Dados H2** 
- **Maven**  

## 🔧 Funcionalidades principais  

- Listar todos os jogos cadastrados.  
- Consultar detalhes de um jogo específico.  
- Listar todas as listas de jogos criadas.  
- Associar jogos a listas específicas com posições personalizadas.  

## 🗂️ Estrutura do Projeto  

O projeto segue a estrutura padrão de um projeto Spring Boot, organizado em camadas:  

- **entities**: Contém as entidades. 
- **repositories**: Interfaces responsáveis pelo acesso ao banco de dados.  
- **services**: Contém a lógica de negócios.  
- **controllers**: Controladores REST que expõem os endpoints.  
- **dtos**: Classes para transferência de dados (Data Transfer Objects).  

## 📋 Endpoints da API  

Aqui estão os endpoints disponíveis na API:  

### Jogos  
- **`GET /games`**: Retorna uma lista com todos os jogos cadastrados, contendo informações resumidas.
**Retorno:**
```json
  [
  {
    "id": 1,
    "title": "The Legend of Zelda",
    "platforms": "Switch",
    "score": 95.0
  },
]
```
- **`GET /games/{id}`**: Retorna os detalhes completos de um jogo específico, identificado pelo seu ID.
**Retorno:**
``` json
  {
  "id": 1,
  "title": "The Legend of Zelda",
  "year": 2017,
  "genre": "Action-Adventure",
  "platforms": "Switch",
  "score": 95.0,
  "imgUrl": "https://...",
  "shortDescription": "Explore a vast open world...",
  "longDescription": "The Legend of Zelda: Breath of the Wild reinvents the series with its vast open-world gameplay."
}
```
### Listas de Jogos  
- **`GET /lists`**: Retorna uma lista de todas as listas de jogos criadas.
**Retorno:**
``` json
[
  {
    "id": 1,
    "name": "Favoritos"
  },
  {
    "id": 2,
    "name": "Aventuras"
  }
]
```
- **`GET /lists/{listId}/games`**: Retorna todos os jogos associados a uma lista específica, identificada pelo ID da lista.
**Retorno:**
```json
[
  {
    "id": 1,
    "title": "The Legend of Zelda",
    "platforms": "Switch",
    "score": 95.0
  },
]
```
  
### Associação de Jogos a Listas
- **`POST /lists/{listId}/replacement`**: Atualiza a posição de um jogo em uma lista específica.
**Request Body:**
```json
{
  "sourceIndex": 1,
  "destinationIndex": 3
}
```
## 🗂️ Como executar o projeto  

### Pré-requisitos  

- [Git](https://git-scm.com) instalado.  
- [Java 17+](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html) instalado.  
- [Maven](https://maven.apache.org/) instalado.  

### Passo a passo  

1. Clone este repositório:  
   ```bash  
   git clone https://github.com/seu-usuario/dslist.git  
   cd dslist  
   ```  

2. Execute o projeto:  
   ```bash  
   ./mvnw spring-boot:run  
   ```  

3. Acesse a aplicação no navegador:  
   ```
   http://localhost:8080  
   ```  

### Console do H2  

Para acessar o console do banco de dados H2, utilize o link:  
```
http://localhost:8080/h2-console  
```  
As configurações de acesso estão no arquivo `application.properties`.  

## 🌟 Autor  

Projeto desenvolvido por **[Gabriella Maurea Bento](https://www.linkedin.com/in/gabriella-maurea-bento)** durante o Intensivão Java Spring da [DevSuperior](https://devsuperior.com.br/).  
