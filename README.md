# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS - TEMPLATE

Data: 30/05/2024
Empresa: X Segurança Trabalho
Responsável: Flávio Pedro
Arquiteto: Reginaldo Santana


# INTRODUÇÃO - DESAFIO
A empresa X procurou o arquiteto [Reginaldo Santana] para resolver seu problema com armazenamento de arquivos.
A empresa precisa manter alguns arquivos armazenados por 10 anos, mesmo não acessando-os diariemnte. Também, reportou algunos problemas.

1. Atualmente os arquivos da empresa encontra-se em um onedrive.
2. Um único e-mail é usado por 20 funcionários.
3. Os dados do Onedrive desktop na máquina de cada usuário sincronizam com os dos outros.
4. Dados pessoas se misturam com dados da empresa.
5. Um ex-funcionário, já apagou arquivos de forma intencional.
6. A empresa conta também com banco de dados em suas filias de forma descentralizadas
7. Cada filial contém servidor próprio para sistemas específico de ERP.


# ANÁLISE INICIAL

Para resolver as necessidades do cliente inicialmente foi pensando em algumas soluções:

1. Onedrive Basic
2. Google Workspace
3. AWS S3
4. AWS WorkDocs
5. AWS WorkSpace

A empresa conta com 20 usuários, atualmente usa de forma contínua a ferrament a Microsoft Word e Excel. Considerando, também
que a empresa já tem contato com o Onedrive seria uma solução mais próxima do cenário atual. O adicional seria a criaçaõ de Biblioteca
com uso de Sharepoint para acesso comum a pastas com partilhads e uso do onedrive desktop para sincronização.
O google workspace desponta de mesma características do onedrive. 

As duas ferramentas atende de forma satisfatório o usuário, no entanto a empresa deseja escalar outros serviços futuros para substituir
toda sua infraestrutura atual para um único ponto de gerencialmento de serviços de redes, além do armazenamento.


Para resolver o problema a solução ideial para o momento será o uso do AWS S3 para armazenamento de objetos, uma vez que podemos configurar classes nos objetos com regras automáticas para dimunir os custos. Exemplo, um arquivo que tem mais de 60 dias sem ser visualizado pode ser alterado de forma automizada para classe S3 Glacier. 

Para resolvermos a questão de os usuários terem acesso aos arquivos na nuvem AWS por meio de uma interface simples,  a proposta é usarmos  o AWS WordSpace para criarmos espaços compartilhados integrado ao S3 e WorkDocs.


# ESCOPO DO PROJETO

Implementar serviço de armazenamento de arquivos na nuvem AWS para garantir acesso rápido e barato a arquivos de uso diário e baixo custo a arquivos de pouco uso de forma que outros serviços possam ser implementados no futuro de forma centralizada.

# ETAPAS DO PROJETO

1. S3 - Criação de Buckets para cada Setor (Finanças, Vendas, Marketing, Operação, Administrativo)

2. Data Sync - Migração de dados das máquinas locais das filiais para o Amazon S3

3. Amazon workspace - configuração do workspace com buckets S3

4. WorkSDocs - instalaçaõ e treinamento rápidos para usuários usarem o Workdocs 


# CUSTO ESTIMADO

Workspace + S3 custo estimado para 1 TB de arquivos. 63.00 USD (workspace + workdocs)   +   10 USD

Total mês: 73 USD