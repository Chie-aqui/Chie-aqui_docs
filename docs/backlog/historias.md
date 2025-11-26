# Histórias de Usuário - Plataforma Chie-Aqui  

## Introdução
Este documento apresenta as histórias de usuário do **Sistema de Reclamações**, uma plataforma que conecta **usuários consumidores** a **empresas**, permitindo registrar reclamações, responder e acompanhar resoluções.  

O sistema possui três tipos de usuários principais:  
- **Consumidores** (que registram reclamações),  
- **Empresas** (que recebem e respondem às reclamações),  
- **Administradores** (que fazem a gestão geral do sistema).  

As histórias foram priorizadas usando o método **MoSCoW**, considerando o valor para o negócio e dependências entre funcionalidades.  

---

## Histórias Priorizadas  

### Consumidor  
| ID   | História                                                                                  | Prioridade   |
|------|-------------------------------------------------------------------------------------------|--------------|
| US01 | Como consumidor, quero me cadastrar para registrar reclamações.                           | Must have    |
| US02 | Como consumidor, quero fazer login para acessar minhas reclamações.                       | Must have    |
| US03 | Como consumidor, quero registrar uma reclamação informando empresa, título e descrição.   | Must have    |
| US04 | Como consumidor, quero visualizar minhas reclamações abertas e encerradas.                | Must have    |
| US05 | Como consumidor, quero editar meu perfil (nome, email telefone).                  | Should have  |
| US06 | Como consumidor, quero avaliar a resposta da empresa como "Resolvido" ou "Não Resolvido". | Must have    |
| US07 | Como consumidor, quero anexar documentos à minha reclamação.                   | Could have   | 
| US08 | Como consumidor, quero deslogar a qualquer momento.                                       | Should have  |

---

### Empresa  
| ID   | História                                                                                  | Prioridade   |
|------|-------------------------------------------------------------------------------------------|--------------|
| US09 | Como empresa, quero me cadastrar para poder responder às reclamações.                     | Must have    |
| US10 | Como empresa, quero fazer login para acessar reclamações contra minha marca.              | Must have    |
| US11 | Como empresa, quero visualizar todas as reclamações recebidas.                            | Must have    |
| US12 | Como empresa, quero responder às reclamações dos consumidores.                            | Must have    |
| US13 | Como empresa, quero editar meu perfil (nome fantasia, email, telefone).      | Should have  |
| US14 | Como empresa, quero visualizar estatísticas de satisfação (resolvidas/não resolvidas).    | Could have   |
| US15 | Como empresa, quero deslogar a qualquer momento.                                          | Should have  |

---

###  Administrador  
| ID   | História                                                                                  | Prioridade   |
|------|-------------------------------------------------------------------------------------------|--------------|
| US16 | Como administrador, quero visualizar todos os consumidores cadastrados.                   | Must have    |
| US17 | Como administrador, quero visualizar todas as empresas cadastradas.                       | Must have    |
| US18 | Como administrador, quero remover usuários ou empresas.                                   | Must have    |
| US19 | Como administrador, quero visualizar todas as reclamações feitas no sistema.              | Must have    |
| US20 | Como administrador, quero buscar consumidores/empresas por email ou CNPJ.                 | Should have  |
---

###  Sistema e Funcionalidades Técnicas  
| ID   | História                                                                                  | Prioridade   |
|------|-------------------------------------------------------------------------------------------|--------------|
| US21 | Como usuário do sistema, quero que as reclamações tenham **status** (Aberta, Respondida, Encerrada). | Must have    |
| US22 | Como usuário do sistema, quero que reclamações tenham IDs únicos para rastreamento.       | Must have    |
| US23 | Como usuário do sistema, quero que existam filtros de reclamações por empresa e status.   | Should have  |


---

###  Legenda – Método MoSCoW  
- **Must have**: Funcionalidades essenciais e críticas para o sistema.  
- **Should have**: Funcionalidades importantes que agregam valor significativo.  
- **Could have**: Funcionalidades desejáveis que podem ser implementadas se houver tempo.  
- **Won’t have**: Funcionalidades que não serão implementadas nesta versão.  
