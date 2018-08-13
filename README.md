# CNES
Repositório para o projeto de replicação da base de dados do CNES (Cadastro Nacional de Estabelecimento de Saúde), 
conforme documentação e dados públicos disponíveis em: 
http://cnes.datasus.gov.br/pages/downloads/arquivosBaseDados.jsp

Se você tem interesse em participar/ajudar de alguma forma neste projeto, favor entrar em contato.

## Idéia inicial
A idéia inicial é replicar a base de dados do CNES em um banco de dados
[PostgreSQL](https://www.postgresql.org/), da maneira mais fiel possível ao original, para possibilitar estudos e análises epidemiológicas
utilizando esses dados como fonte.

Uma cópia 100% exata não será
possível pois, por exemplo:

* Alguns campos descritos no dicionário de dados não estão
  disponíveis nos dados públicos para download.
* O CNES é disponibilizado como um sistema local no qual os dados são periodicamente enviados
  ao sistema nacional e, neste projeto, estamos interessados apenas nos dados disponíveis no
  sistema nacional.

Entretanto, a maioria absoluta dos campos e dados não disponíveis são informações de controle
interno do sistema e não afetam em nada a disponibilidade da informação realmente
importante para análises epidemiológicas.

## Tecnologia

### Banco de dados
O [PostgreSQL](https://www.postgresql.org/) foi escolhido por ser _opensource_, gratuito e disponível em diversas
plataformas (além de apresentar tipos de dados e linguagem PL/PgSQL bem similares ao
sistema original em Oracle).

O diagrama entidade relacionamento será criado com base nos metadados públicos do CNES
utilizando-se o utilitário [DbSchema](https://www.dbschema.com/).

Os dados utilizados para a validação, testes e carga no banco réplica são os de JUNHO/2018,
os últimos disponibilizados para download na página do CNES
(http://cnes.datasus.gov.br/pages/downloads/arquivosBaseDados.jsp)

### Interface de usuário
Não está prevista, no momento, o desenvolvimento de nenhuma interface amigável de acesso para
usuários finais já que o objetivo é somente ter a réplica do banco de dados para análises.

### Acesso ao banco réplica
No momento o acesso ao banco réplica está restrito. Quando toda a migração, teste e validação
terminar, avaliaremos a possibilidade de liberar o acesso público.