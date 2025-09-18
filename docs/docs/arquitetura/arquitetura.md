#  Documento de Arquitetura – Sistema Reclame Aqui Acadêmico

## Introdução
Este documento descreve a arquitetura escolhida para o **Sistema Reclame Aqui Acadêmico**, detalhando como os componentes se organizam e interagem para formar uma aplicação web robusta, modular e escalável.  

O sistema foi desenvolvido com **Django** e **Django REST Framework (DRF)**, utilizando **PostgreSQL** como banco de dados relacional e **containerização com Docker** para facilitar a portabilidade e o deployment.  

---

## Visão Geral
O sistema adota uma **arquitetura REST baseada no padrão MTV (Model-Template-View)** do Django, adaptado para APIs através do **Django REST Framework**.  

Essa escolha garante:  
- Separação clara de responsabilidades  
- Facilidade de manutenção e testes  
- Escalabilidade horizontal  
- Portabilidade via containers Docker  

### Características Principais:
- **API REST** como interface de comunicação  
- **Padrão MTV** (Model, Template, View) adaptado para APIs  
- **Django ORM** para abstração do banco de dados  
- **DRF Serializers** para validação e transformação de dados  
- **Containerização (Docker + Docker Compose)** para deployment  

---

## Componentes Principais  

### 1. Camada de Apresentação (Views/Controllers)  
Implementada pelas **Views do DRF** (ViewSets e APIViews):  
- Recebem* requisições HTTP (GET, POST, PUT, DELETE)  
- Validam dados de entrada usando **Serializers**  
- Chamam a lógica de negócio (Services ou direto nos Models)  
- Retornam respostas HTTP em formato **JSON**  

---

### 2. Camada de Lógica de Negócio (Services/Use Cases)  
Nem sempre é explicitada no Django, mas pode ser organizada em **services.py**:  
- Implementa as regras de negócio (ex.: fluxo de cadastro de reclamação, autenticação, moderação)  
- Centraliza validações específicas do domínio  
- Facilita a testabilidade e reutilização de lógica  

---

### 3. Camada de Dados (Models e ORM)  
Gerenciada pelo **Django ORM**:  
- Definição de **Models** representando as entidades (Usuário, Empresa, Reclamação, Resposta)  
- Criação automática de tabelas no PostgreSQL via **Migrations**  
- Operações CRUD com abstração em Python (`.objects.create()`, `.filter()`, etc.)  
- Relacionamentos (OneToMany, ManyToMany, ForeignKey)  
- Proteção contra SQL Injection de forma nativa  

---

### 4. Serializers (Camada de Validação e Transformação)  
Fornecida pelo **Django Rest Framework**:  
- Validação de dados de entrada da API  
- Transformação de objetos Django (Models) em **JSON**  
- Definição de regras de serialização e deserialização  
- Suporte a **nested serializers** para entidades relacionadas  

---

## Padrão MTV Adaptado ao Django Rest Framework  

### Model  
- **Django Models** representam as tabelas do banco  
- **ORM** cuida da persistência e integridade dos dados  

### Template  
- Em projetos de API com DRF, o "Template" tradicional não é usado  
- A resposta é entregue em **JSON** ao invés de HTML  

### View  
- **DRF ViewSets/APIViews** controlam a lógica de requisição  
- **Serializers** atuam como a "camada de apresentação", validando e formatando os dados para a API  

---

## Fluxo de Requisição  
1. Cliente faz requisição HTTP para a API  
2. **Router do DRF** identifica a rota e direciona para a View correspondente  
3. **View (ViewSet/APIView)** processa a requisição  
4. **Serializer** valida/transforma os dados  
5. **Model/ORM** acessa o banco PostgreSQL  
6. Resposta é formatada em **JSON** e enviada ao cliente  

---

## Benefícios da Arquitetura  
- **Produtividade**: Django e DRF oferecem muitas funcionalidades prontas  
- **Organização**: Código dividido em Models, Views, Serializers e URLs  
- **Testabilidade**: DRF permite testes unitários e de integração de endpoints  
- **Escalabilidade**: Suporte a cache, balanceamento de carga e horizontal scaling  
- **Segurança**: Proteções nativas contra SQL Injection, CSRF e XSS  
- **Extensibilidade**: Fácil integração com bibliotecas externas (JWT, Swagger, Celery)  
