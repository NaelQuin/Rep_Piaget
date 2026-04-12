
#  Levantamento de Requisitos

## 1.  Introdução
O presente documento descreve o levantamento de requisitos do projeto REP (Repositório
Educativo do Piaget), uma plataforma académica desenvolvida no âmbito do Projeto
Integrador da Licenciatura em Engenharia Informática do Instituto Piaget (Almada), ano letivo
2025/2026.


## 2.  Âmbito do Sistema
A plataforma REP é uma aplicação web acessível a partir de qualquer dispositivo com
browser. O sistema abrange as seguintes áreas funcionais:

• Gestão e partilha de materiais académicos (resumos, apontamentos, exames)

• Sistema de feedback por disciplina

• Chatbot de apoio ao estudo com Inteligência Artificial

• Sistema de quizzes gerados a partir dos materiais carregados

• Autenticação e gestão de utilizadores

• Pesquisa de conteúdos na plataforma

## Identificação dos Stakeholders

Os seguintes intervenientes foram identificados no âmbito do projeto:

| Stakeholder | Papel | Interesse |
|:------------|:------|:----------|
| Autenticados | Utilizador principal | Aceder, partilhar materiais e estudar com IA |
| Administradores | Gestão da plataforma | Gerir utilizadores, disciplinas e conteúdos |
| Visitantes | Acesso limitado | Visualizar informação pública sem registo |
| Equipa de desenvolvimento | Criadores do sistema | Entregar o projeto dentro do prazo e requisitos |
| Instituto Piaget | Cliente / Orientador | Plataforma funcional e útil para os alunos |

# 3. Requisitos Funcionais

## 3.1 Autenticação e Gestão de Utilizadores

| ID | Requisito | Prioridade |
|:---|:----------|:----------:|
| RF01 | O sistema deve permitir o registo de novos utilizadores apenas com e-mail institucional e palavra-passe |  Alta |
| RF02 | O sistema deve permitir o login com e-mail e palavra-passe |  Alta |
| RF03 | O sistema deve validar a robustez da palavra-passe, exigindo o mínimo de 8 caracteres |  Média |
| RF03a | O sistema deve rejeitar sequências triviais como `12345678`, `password` ou `qwerty` |  Média |
| RF03b | O sistema não deve permitir o uso do nome de utilizador ou e-mail como parte da palavra-passe |  Média |
| RF04 | O sistema deve permitir a recuperação de palavra-passe por e-mail |  Alta |
| RF05 | O sistema deve distinguir os perfis: Utilizador Autenticado, Visitante e Admin |  Alta |
| RF06 | O administrador deve poder gerir contas (criar, suspender, eliminar) |  Alta |

## 3.2 Materiais Académicos

| ID | Requisito | Prioridade |
|:---|:----------|:----------:|
| RF07 | Os alunos devem poder fazer upload de ficheiros (PDF, DOCX, PPTX) |  Alta |
| RF08 | Os utilizadores autenticados devem poder fazer download dos materiais disponíveis |  Alta |
| RF09 | Os materiais devem estar organizados por disciplina e tipo (resumo, exame, apontamento) | Alta |
| RF10 | O sistema deve permitir a visualização de metadados do ficheiro (autor, data, disciplina) | Média |
| RF11 | O administrador deve poder remover materiais inadequados | Alta |
| RF12 | O sistema deve limitar o tamanho máximo de ficheiro por upload de no mínimo 20 mb |  Média |
| RF13 | Todos os ficheiros submetidos devem ficar em estado pendente até aprovação por um administrador | Alta |
| RF14 | O administrador deve poder aprovar ou rejeitar ficheiros submetidos | Alta |
| RF15 | Apenas ficheiros aprovados devem estar disponíveis para download | Alta |
| RF16 | Os ficheiros devem possuir um estado associado (pendente, aprovado ou rejeitado) | Baixa |
| RF17 | O utilizador deve ser notificado quando o seu ficheiro for aprovado ou rejeitado | Média |
| RF18 | O utilizador deve poder editar ou eliminar os seus ficheiros antes e depois da aprovação | Média |
| RF19 | Os utilizadores registados devem poder submeter feedback sobre as disciplinas e materiais. O feedback pode ser apresentado de forma anónima para outros utilizadores| Alta |
| RF20 | Os utilizadores autenticados devem poder votar +1 ou -1 em cada material | Baixa |
| RF21 | Cada utilizador só pode votar uma vez por material (pode alterar o voto) | Média |
| RF22 | Um material deve ser automaticamente removido ao atingir um limite de votos negativos (-5) | Média |

## 3.3 Feedback de Disciplinas

| ID | Requisito | Prioridade |
|:---|:----------|:----------:|
| RF23 | Os alunos devem poder submeter feedback anónimo sobre as disciplinas |  Baixa |
| RF24 | O sistema deve permitir a consulta do feedback agregado por disciplina | Baixa |
| RF25 | O feedback deve incluir classificação numérica e comentário textual |  Média |
| RF26 | O sistema deve impedir a submissão de múltiplos feedbacks pelo mesmo utilizador na mesma disciplina |  Baixa |

##  3.4 Chatbot de Apoio ao Estudo (IA)

| ID | Requisito | Prioridade |
|:---|:----------|:----------:|
| RF27 | O sistema deve disponibilizar um chatbot integrado por disciplina | Média |
| RF28 | O chatbot deve responder a perguntas com base nos materiais carregados na disciplina | Média |
| RF29 | O utilizador deve poder iniciar, continuar e terminar sessões de estudo com o chatbot | Baixa |
| RF30 | O chatbot deve gerar quizzes automáticos com base nos materiais da disciplina | Baixa |
| RF31 | O sistema deve guardar o histórico de conversas por utilizador | Baixa |
| RF32 | O chatbot deve indicar a fonte (material) de onde retirou a resposta |Baixa |
| RF33 | O sistema deve impor um limite diário de mensagens por utilizador no chatbot | Baixa |
| RF34 | O utilizador deve poder inserir a sua própria chave de API OpenAI para remover o limite diário | Baixa |
| RF35 | O sistema deve permitir que o utilizador avalie a utilidade da resposta da IA (voto positivo/negativo) para melhoria do sistema| Baixa |
| RF36 | O utilizador deve poder escolher o contexto do chatbot: toda a Unidade Curricular ou apenas um ficheiro específico | Baixa |


## 3.5 Pesquisa de Conteúdos

| ID | Requisito | Prioridade |
|:---|:----------|:----------:|
| RF37 | O sistema deve permitir a pesquisa de materiais por nome e disciplina | Alta |
| RF38 | Os resultados de pesquisa devem ser filtráveis e ordenáveis |Média |
| RF39 | A pesquisa deve retornar resultados em tempo real (à medida que o utilizador escreve) | Baixa |
| RF40 | O utilizador deve poder marcar e desmarcar qualquer material como favorito para acesso mais rápido | Baixa |


# 4. Requisitos Não Funcionais

| ID | Categoria | Requisito |
|:---|:----------:|:----------|
| RNF01 | Desempenho | As páginas devem carregar em menos de 3 segundos|
| RNF02 | Segurança | Todas as comunicações devem usar HTTPS |
| RNF03 | Segurança | As palavras-passe devem ser armazenadas com hashing seguro (gerido pelo Supabase Auth) |
| RNF04 | Segurança | O acesso à API OpenAI deve ser feito exclusivamente pelo backend, nunca expondo a chave no frontend |
| RNF05 | Usabilidade | A interface deve ser responsiva e utilizável em dispositivos móveis e desktop |
| RNF06 | Usabilidade | A interface deve seguir princípios de acessibilidade (WCAG 2.1 nível AA) |
| RNF07 | Disponibilidade | A plataforma deve ter disponibilidade mínima de 99% em horário letivo |
| RNF08 | Escalabilidade | A arquitetura deve suportar crescimento do número de utilizadores e ficheiros sem refatorização |
| RNF09 | Manutenibilidade | O código deve seguir boas práticas de desenvolvimento (TypeScript, comentários, estrutura modular) |
| RNF10 | Privacidade | Os dados dos utilizadores devem ser tratados em conformidade com o RGPD |
| RNF11 | Segurança | O sistema deve validar os ficheiros submetidos antes do upload, garantindo o cumprimento das restrições definidas (tipo e tamanho) |
| RNF12 | Segurança | O sistema deve implementar controlo de acessos baseado em perfis (visitante, utilizador, administrador) |
| RNF13 | Auditoria| O sistema deve registar logs das ações de administradores (aprovação, rejeição, eliminação) |
| RNF14 | Auditoria| Os logs devem incluir ID do administrador, ação realizada, data/hora e recurso afetado |
| RNF15 | Auditoria| Os logs devem ser apenas acessíveis a administradores e não devem poder ser alterados |
| RNF16 | Integridade de Dados| O sistema deve garantir que todos os ficheiros estão associados a uma disciplina e a um utilizador válido |
| RNF17 | Robustez | O sistema deve apresentar mensagens de erro compreensíveis ao utilizador, indicando a causa do erro e, sempre que aplicável, a ação necessária para o corrigir |
| RNF18 | Armazenamento| O sistema deve armazenar os ficheiros com metadados associados, incluindo pelo menos o nome, tipo, utilizador que efetuou o upload, disciplina e estado de aprovação |

# 5. Casos de Uso Principais / Use Cases

Os diagramas de casos de uso serão desenvolvidos em detalhe na documentação UML. A seguir apresentam-se os casos de uso de alto nível identificados.

| ID | Caso de Uso | Ator(es) | Pré-condição |
|:---|:------------|:---------|:-------------|
| UC01 | Registar conta | Visitante | Nenhuma |
| UC02 | Autenticar na plataforma | Utilizador, Admin | Conta registada |
| UC03 | Fazer upload de material | Utilizador | Autenticado, disciplina existente |
| UC04 | Fazer download de material | Utilizador | Autenticado, ficheiro aprovado |
| UC05 | Submeter feedback | Utilizador | Autenticado, disciplina existente |
| UC06 | Consultar feedback | Utilizador, Admin | Autenticado |
| UC07 | Interagir com chatbot | Utilizador | Autenticado, materiais carregados |
| UC08 | Gerar quiz | Utilizador | Autenticado, materiais carregados |
| UC09 | Pesquisar conteúdos | Visitante, Utilizador | Nenhuma |
| UC10 | Gerir utilizadores | Admin | Autenticado como Admin |
| UC11 | Gerir disciplinas | Admin | Autenticado como Admin |
| UC12 | Aprovar/Rejeitar ficheiros | Admin | Autenticado como Admin, ficheiros pendentes |
| UC13 | Consultar logs do sistema | Admin | Autenticado como Admin |
| UC14 | Eliminar ficheiro próprio | Utilizador | Autenticado, ficheiro pertencente a utilizador |


# 6. Restrições e Pressupostos

##  6.1 Restrições Técnicas
• O sistema será desenvolvido em Next.js com TypeScript e Tailwind CSS

• A base de dados e autenticação serão geridas pelo Supabase (PostgreSQL)

• O chatbot utilizará a API da OpenAI (modelo GPT)

• O deployment será feito na plataforma Vercel

## 6.2 Restrições de Negócio
• O acesso a materiais, AI e escrever feedback requer autenticação

• O projeto deve estar concluído no final do ano letivo 2025/2026


## 6.3 Pressupostos
• Os utilizadores têm acesso a um browser moderno e ligação à internet

• Os dados das disciplinas e cursos serão recolhidos manualmente pela equipa de desenvolvimento a partir da informação publicamente disponível no site do Instituto Piaget 

• A equipa terá acesso às APIs necessárias (Supabase, OpenAI) durante o
desenvolvimento

