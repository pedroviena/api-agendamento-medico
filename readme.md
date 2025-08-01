# Sistema de Agendamento de Consultas Médicas

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Java](https://img.shields.io/badge/Java-17%2B-blue?logo=java&logoColor=white)
![Spring](https://img.shields.io/badge/Spring_Boot-3.2.x-green?logo=spring&logoColor=white)
![Security](https://img.shields.io/badge/Security-JWT-orange)
![Tests](https://img.shields.io/badge/Tests-Testcontainers-blueviolet)

Um sistema de API REST para agendamento de consultas em uma clínica, desenvolvido com Spring Boot. O projeto inclui funcionalidades robustas como controle de horários, múltiplos perfis de acesso e uma cobertura de testes completa para garantir a qualidade e a segurança das regras de negócio.

## 📝 Visão Geral do Projeto

O objetivo deste projeto é fornecer uma API backend completa e segura para a gestão de agendamentos de uma clínica médica. A aplicação foi desenhada com uma arquitetura em camadas, seguindo as melhores práticas de desenvolvimento de software, incluindo a separação de responsabilidades, validação de dados e um sistema de autenticação e autorização baseado em tokens JWT.

Um dos grandes destaques é a suíte de testes, que utiliza **Testcontainers** para criar um ambiente de integração fiel ao de produção, garantindo que as regras de negócio complexas (como a prevenção de conflitos de horários) funcionem conforme o esperado.

## ✨ Funcionalidades Principais

-   **Cadastro de Pacientes e Médicos**: Gerenciamento completo de usuários do sistema.
-   **Autenticação Segura**: Login via API com retorno de token JWT.
-   **Controle de Acesso por Perfil**:
    -   `ADMIN`: Acesso total ao sistema.
    -   `RECEPCAO`: Permissões para agendar e cancelar consultas para qualquer paciente.
    -   `MEDICO`: Acesso apenas à sua própria agenda.
    -   `PACIENTE`: Acesso apenas aos seus próprios agendamentos.
-   **Agendamento de Consultas**: Regras de negócio para evitar duplo agendamento para o mesmo médico no mesmo horário.
-   **Cancelamento de Consultas**: Regra de negócio que exige antecedência mínima para o cancelamento.
-   **Histórico Médico**: (Funcionalidade futura) Acesso ao histórico de consultas.

## 🚀 Tecnologias Utilizadas

-   **Backend**:
    -   [Java 17](https://www.oracle.com/java/)
    -   [Spring Boot 3](https://spring.io/projects/spring-boot)
    -   [Spring Web](https://docs.spring.io/spring-framework/docs/current/reference/html/web.html)
    -   [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
    -   [Spring Security](https://spring.io/projects/spring-security)
    -   [Hibernate](https://hibernate.org/)
-   **Banco de Dados**:
    -   [PostgreSQL](https://www.postgresql.org/)
-   **Segurança**:
    -   Autenticação e autorização baseada em Token [JWT (JSON Web Token)](https://jwt.io/)
-   **Testes**:
    -   [JUnit 5](https://junit.org/junit5/)
    -   [Mockito](https://site.mockito.org/)
    -   [Testcontainers](https://www.testcontainers.org/) (para testes de integração com banco de dados real)
-   **Ferramentas**:
    -   [Maven](https://maven.apache.org/)
    -   [Lombok](https://projectlombok.org/)

## 🔧 Como Executar o Projeto

### Pré-requisitos

Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:
-   [JDK 17 ou superior](https://www.oracle.com/java/technologies/downloads/)
-   [Maven](https://maven.apache.org/download.cgi)
-   [Docker](https://www.docker.com/products/docker-desktop/) (necessário para rodar os testes com Testcontainers)
-   Um cliente de API, como [Postman](https://www.postman.com/) ou [Insomnia](https://insomnia.rest/).

### 1. Clone o repositório

```bash
git clone https://github.com/pedroviena/api-agendamento-medico.git)
cd api-agendamento-medico
