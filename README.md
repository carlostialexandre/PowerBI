# PowerBI
Documentação dos visuais do Power BI

link para[5 pilares para um dashboard de sucesso](https://www.mindmeister.com/app/map/2830078046?fullscreen=1&v=public)
➡️Resumo - Análises e KPIs do Projeto

Análises necessárias

➡️ Análise de Vendas
» Total vendido por período
» Receita total
» Quantidade de itens vendidos
» Quantidade de pedidos 
» Quantidade de itens por pedido
» Ranking de melhores e piores produtos
» Análise de receita por loja, produto, UF e categoria
» Receita vs Meta por período e produto
» Simulações

➡️ Análise de Produtos
» Produtos mais vendidos
» Categorias mais vendidas
» Receita por origem de produto
» Maiores fornecedores/marcas por receita


➡️ Análise de Fluxo de Caixa
» Visão de saldo por data
» Gastos por categorias e despesas
» Gastos por departamento
» Principais gastos
» Saldo geral

➡️Etapas de um relatório/projeto no Power Bl

1. Levantamento das necessidades analíticas junto aos stakeholders

2. Mapeamento e coleta das fontes de dados

3. Análise da estrutura dos dados

4. Tratamento removendo dados indesejados e ajustando estrutura para o

modelo tabular

5. Criação das métricas para responder as necessidades analíticas

6. Visualização dos dados em gráficos

7. Compartilhamento aos interessados e configuração de atualizações e

seguranças

<<<<<<< Updated upstream
FATO
=======
Resumo das Cardinalidades:

Quando falamos sobre Cardinalidade estamos nos referindo a exclusividade de valores em uma coluna.

Os tipos de cardinalidade: 

• Um para Muitos (1:*) / Muitos para Um: (*:1):
Este é o tipo mais recomendado de relacionamento e o mais encontrado nos projetos;

• Um para Um: (1:1):
Não é comum - significa que essas tabelas poderiam ser mescladas e se tornar uma única tabela;

• Muitos para Muitos (*:*)
Significa que há dados que se repetem nas duas tabelas. Não há chave primária(única):
💡Sugestão: Criar uma tabela auxiliar com dados únicos, para que possa ser utilizada como uma "ponte" entre as duas tabelas fato.

>>>>>>> Stashed changes

Característica: tabelas grandes, com muitas linhas (cada linha um registro)
Dados quantitativos e com registro de datas dos eventos/fatos do negócio. Se repetem inúmeras vezes.
Nomenclatura mais encontrada: letra f minúscula na frente do nome. Assim:
fNotasFiscais, fPedidos, fEmbarques, fChamados.


DIMENSÃO

Característica: menor quantidade de linhas, mas pode ter mais colunas (de acordo com a quantidade de atributos).
Dados mais qualitativos, que descrevem detalhes de quem, onde, quando, porquê os acontecimentos da tabela fato ocorreram. Possuem valores (chaves) únicas, sem repetição.
Nomenclatura mais encontrada: letra d minúscula. Assim:
dFornecedores, dProdutos, dFuncionários, dClientes.

Características da modelagem de dados com boas práticas aplicadas: 

➡️ Inclui somente dados que são necessários para a análise, excluindo qualquer redundância ou informações desnecessárias ao projeto;

➡️Possui tabelas que servem para um propósito específico e bem definido, devidamente separadas por fatos e dimensões (modelo normalizado);

➡️Tabelas e colunas possuem nomes facilmente conhecidos pelo negócio (cuidado com siglas de sistemas e abreviações). Para facilitar a identificação de tabelas, você pode optar por deixar um prefixo "f" para tabela fato e "d" para dimensão (opcional). Por exemplo: fVendas; dCalendário

➡️Função Mesclar do Power Query utilizada com cautela. Usar apenas para unificar dimensões com dimensões (jamais fato + dimensão);

➡️Revisão criteriosa dos relacionamentos criados automaticamente pelo Power BI. É possível desabilitar essa opção seguindo o caminho: Arquivo > Opções e Configurações > Opções > Arquivo Atual > Carregamento de dados > Relacionamentos.

➡️Utiliza um esquema do tipo estrela (star schema) com relacionamentos de Um para Muitos (1:*);

➡️Contém relacionamentos com filtros de direção única;

➡️Não possui relacionamento direto de fato com fato. Utiliza uma tabela dimensão como ponte para vincular as duas tabelas fato. Tem uma tabela dCalendário no modelo (marcada com o tipo de dado como "Data");

➡️Componentes de Data e Hora separados em colunas diferentes;

➡️Tem uma tabela dCalendário no modelo (marcada como "Data").


Resumo de pontos destacados da aula anterior:

Levantamento das necessidades analíticas junto aos stakeholders
Mapeamento e coleta das fontes de dados
Análise da estrutura dos dados
Tratamento removendo dados indesejados e ajustando estrutura para o modelo tabular
Criação das métricas para responder as necessidades analíticas
Visualização dos dados em gráficos
Compartilhamento aos interessados e configuração de atualizações e seguranças

Resumo de pontos destacados da aula anterior:

Tipos de Cálculos no DAX

Nova medida: cria medidas para serem inseridas em gráficos. São calculadas somente no visual.
Nova coluna: cria colunas na tabela utilizando DAX. São calculadas e mantidas na tabela/modelo. Não aparecem no Power Query.
Nova tabela: cria tabelas usando DAX. São calculadas e mantidas no modelo. Não aparecem no Power Query.