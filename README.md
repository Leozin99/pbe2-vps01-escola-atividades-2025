# ATIVIDADES ESCOLA ACME API
Situação de Aprendizagem - Back-End (Node.JS, JavaSript, VsCode, ORM Prisma, Insomnia)
## Contextualização
A ESCOLA ACME tem atuado em nossa cidade com ótimo atendimento e confiabilidade, é nossa cliente e necessita de um sistema Web para registro das atividades e notas de seus alunos.<br>O P.O. após uma visita ao cliente, elaborou o DER e UML DC(Diagrama de Classes) a seguir e elencou os requisitos funcionais.<br>
![DER e DC](./docs/der-dc.png)
## Desafio
Desenvolver as funcionalidades conforme requisitos

### Requisitos funcionais
- [RF001] O sistema deve permitir o CRUD de Alunos.
    - [RF001.1] O sistema deve permitir o CRUD de telefones, pois cada **aluno** pode possuir 0 ou vários telefones de tipos diferentes como celular, fixo ou comercial.
    - [RF001.2] A rota **read** do **aluno** deve mostrar os dados de todos os alunos e seus respectivos telefones.
    - [RF001.3] A rota **readOne** do **aluno** deve mostrar os dados de um aluno específico, seus telefones e suas **atividades**.
- [RF002] O sistema deve permitir o CRUD de Atividades.
    - [RF002.1] O sistema deve associar a atividade a um aluno.
    - [RF002.2] Ao cadastrar uma nova atividade **create** no controller, a dataInicio deve ser gerada pelo Banco de Dados @dedault(now()).
    - [RF002.3] Ao cadastrar uma nova atividade **create** no controller, a dataEntrega, a nota e a parcial podem ser nulas **"?"** pois serão preenchidas na rota **update** quando o aluno entregar e o professor corrigir.
    - [RF002.4] Se ao realizar **update** o campo **nota** for enviado o sistema deve calcular a **parcial** com a formula **"nota * peso / 10"**.

### Casos de teste (Insomnia)
- [CT001] Deve ser cadastrado pelo menos 5 alunos.
- [CT002] Deve ser cadastrado ao menos 1 telefone para cada aluno.
    - [CT002.1] Pelo menos dois alunos devem ter dois ou mais telefones cadastrados.
- [CT003] Cadastre, altere e exclua um aluno.
- [CT004] Cadastre uma atividade para cada aluno.
    - [CT004.1] Pelo menos um aluno deve ter duas ou mais atividades cadastradas.
- [CT005] Cadastre, altere e exclua uma atividade.

## Tecnologias
Node.js, Express.js, Prisma ORM, MYSQL, Insomnia, Git.


## Passo a Passo de como executar a API
1. Pré-requisitos:
Node.js: Instale o Node.js em nodejs.org.

MySQL: Instale o MySQL em mysql.com.

2. Clonar o Repositório:

git clone <URL do repositório>
cd <nome-do-diretório>
3. Instalar Dependências:

npm install
4. Configurar Banco de Dados:
Crie um banco de dados no MySQL (ex: escola_atividades).

Configure as credenciais no arquivo .env.

5. Rodar as Migrações:

npx prisma migrate dev
6. Iniciar a API:


npm start
7. Testar a API:
Use o Insomnia ou Postman para testar os endpoints da API, como POST, GET, PUT e DELETE.
