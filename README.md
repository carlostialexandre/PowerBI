# PowerBI

### Visualize s aquivos em pdf, print e visuais
Documentação dos visuais do Power BI
Acesse [pelo terabox](https://www.terabox.com/main?category=all&path=%2FPowerBI)


link para [5 pilares para um dashboard de sucesso](https://www.mindmeister.com/app/map/2830078046?fullscreen=1&v=public)
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

## Resumo das Cardinalidades:

Quando falamos sobre Cardinalidade estamos nos referindo a exclusividade de valores em uma coluna.

## Os tipos de cardinalidade: 

• Um para Muitos (1:*) / Muitos para Um: (*:1):
Este é o tipo mais recomendado de relacionamento e o mais encontrado nos projetos;

• Um para Um: (1:1):
Não é comum - significa que essas tabelas poderiam ser mescladas e se tornar uma única tabela;

• Muitos para Muitos (*:*)
Significa que há dados que se repetem nas duas tabelas. Não há chave primária(única):
💡Sugestão: Criar uma tabela auxiliar com dados únicos, para que possa ser utilizada como uma "ponte" entre as duas tabelas fato.


Característica: tabelas grandes, com muitas linhas (cada linha um registro)
Dados quantitativos e com registro de datas dos eventos/fatos do negócio. Se repetem inúmeras vezes.
Nomenclatura mais encontrada: letra f minúscula na frente do nome. Assim:
fNotasFiscais, fPedidos, fEmbarques, fChamados.


## DIMENSÃO

Característica: menor quantidade de linhas, mas pode ter mais colunas (de acordo com a quantidade de atributos).
Dados mais qualitativos, que descrevem detalhes de quem, onde, quando, porquê os acontecimentos da tabela fato ocorreram. Possuem valores (chaves) únicas, sem repetição.
Nomenclatura mais encontrada: letra d minúscula. Assim:
dFornecedores, dProdutos, dFuncionários, dClientes.

## Características da modelagem de dados com boas práticas aplicadas: 

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


## Resumo de pontos destacados da aula anterior:

Levantamento das necessidades analíticas junto aos stakeholders
Mapeamento e coleta das fontes de dados
Análise da estrutura dos dados
Tratamento removendo dados indesejados e ajustando estrutura para o modelo tabular
Criação das métricas para responder as necessidades analíticas
Visualização dos dados em gráficos
Compartilhamento aos interessados e configuração de atualizações e seguranças

Resumo de pontos destacados da aula anterior:

## Tipos de Cálculos no DAX

Nova medida: cria medidas para serem inseridas em gráficos. São calculadas somente no visual.
Nova coluna: cria colunas na tabela utilizando DAX. São calculadas e mantidas na tabela/modelo. Não aparecem no Power Query.
Nova tabela: cria tabelas usando DAX. São calculadas e mantidas no modelo. Não aparecem no Power Query.

Resumo de operadores lógicos explicado na aula anterior para serem usados na Calculate, IF e outras funções.

## Argumentos Lógicos:

OR - isso 'ou' aquilo
II - isso 'ou' aquilo. Também conhecido como "Pipe"
AND - isso 'e' aquilo
&& - isso 'e' aquilo

## Principais atalhos no DAX:

// ou -- : comentário de linha
/* e */ : comentário de várias linhas
Ctrl + D : seleciona ocorrências da palavra selecionada
Ctrl + Shift + L : seleciona todas as ocorrências da palavra selecionada
Shift + Enter : Quebra de linha
Alt + Shift + Setas : Duplica linha
Alt + Setas : Reposiciona linha

## Organização dentro de Medidas: Indentação

Em todos os argumentos de função (após a vírgula), exceto aquelas que possuem apenas 1 argumento simples, é realizada uma quebra de linha.
Em toda abertura de função, após o parênteses, é realizada uma quebra de linha.
Em todo encerramento de função, após o parênteses e/ou vírgula, é realizada uma quebra de linha.

## Resumo Funções de Inteligência de Tempo

SAMEPERIODLASTYEAR: Retorna os valores do mesmo período do ano anterior.
DATEADD: Retorna os valores do mesmo período do ano, trimestre, mês ou dia anterior.
DATESINPERIOD: Cria uma lista de datas para um período específico a partir de uma data inicial.
DATESBETWEEN: Retorna uma lista de datas entre duas datas especificadas.
TOTALYTD: Calcula o total acumulado do início do ano até uma data especificada.

## Resumo da USERRELANTIONSHIP:

Múltiplas Relações: Utilize quando houver múltiplas relações entre duas tabelas e quiser alternar entre elas.
Temporariedade: A relação ativada é temporária e se aplica apenas à medida ou expressão em questão.
Relações Inativas: Só pode ativar relações que estão inativas. Tentar ativar uma já ativa resultará em erro.
Combinada com CALCULATE: Deve ser usada com CALCULATE para modificar o contexto do cálculo.
Precisa existir o relacionamento: O relacionamento entre as colunas usadas na função precisa existir, ou seja, precisa ter sido relacionada previamente.

## Compreenda o que é DataViz
Sejam muito bem-vindos e bem-vindas a mais um módulo! 🥳🎉
Essa aula é super importante para você começar com o pé direito entender exatamente qual é o conceito de DataViz. 

⚠️ Se você está aqui e pulou as aulas dos módulos anteriores: volte uma casa. Todo o conhecimento adquirido aqui só será válido se você tiver assistido o curso de forma completa e seguindo a linha linear e lógica que desenvolvemos especialmente para os #datadrivens, combinado?

Aproveite as aulas e marca a gente (@leticiasmirelli e @karinedolago) lá nos stories do Instagram enquanto estiver assistindo! Nós adoramos ver a dedicação de vocês e iremos repostar sempre que possível. Também é muito legal ver os comentários aqui abaixo das aulas na plataforma! Estamos sempre de olho nos #datadrivens com alto engajamento! 👀

## Pontos-chave - DataViz

>> Escolha dos gráficos mais adequados de acordo com a história que você quer contar.
>> Consideração dos princípios básicos do design (contraste, repetição, alinhamento e proximidade).

>> A forma segue a função (primeiro deve ser funcional e depois esteticamente bonito).
>> Elementos (cores, ícones) devem ser usados estrategicamente para dirigir a atenção do público.
>> Um bom design interfere diretamente na atenção e nível de qualidade percebido no seu projeto.
>> Menos é mais (retire tudo aquilo que ocupa espaço e não agrega valor).

## 📣 ATENÇÃO, Data Drivens!

Se o gráfico de mapa não estiver funcionando pra você (caso apareça alguma mensagem de erro no Power BI), por favor, LEIA atentamente os pontos abaixo:

1) Dentro do Power BI Desktop (baixado no seu computador), vá em Arquivo > Opções e Configurações > Opções > Segurança (fica dentro de "Global) > Confirme se as opções "ArcGIS for Power BI" e "Mapa e visuais de Mapa Preenchido" estão selecionadas. Se não estiver, selecione as duas opções, clique em OK, feche o seu Power BI Desktop e abra novamente.

2) Existe também uma configuração no Power BI Serviço (que foi explicada durante o vídeo). 

Você precisa clicar na engrenagem que fica no canto superior direito da tela (próximo a sua foto) > Portal de administração > Configurações de Locatário > Busque pelo termo "Mapa" > Deixe como "Habilitada" as duas opções

obs: em casos de contas empresariais, é possível que apenas o TI da empresa tenha acesso as configurações de locatário dentro do Power BI Serviço. Nestes casos a única forma é entrar em contato com eles para liberarem os visuais de mapa pra você (apenas caso não esteja habilitado).

## Instruções para trabalhar com imagens de forma dinâmica [Produtos]
Conforme explicado na aula, o Power BI não puxa a imagem direto de um arquivo local do seu computador - a não ser que você queira uma imagem estática, basta ir na Guia Inserir > Imagem. 

Para a imagem ficar interativa com o seu relatório e ser filtrada conforme os contextos, ela precisar estar em um link (uma URL) armazenado dentro de uma tabela. E é importante que essa tabela precisa esteja relacionada com o seu modelo de dados.



Aqui estão algumas possibilidades para esse processo:
1) URL da Web - Pública: pode ser do site da sua empresa, do Google Imagens, de redes sociais, etc. Mas lembre-se que dessa forma você fica vulnerável de quem é o dono dessa imagem e a hospedou online

2) Link do One Drive: que não exija entrada - teste em uma guia anônima do seu navegador para ver se consegue visualizar a imagem

3) Sites gratuitos que hospedam imagens online e geram links compartilháveis, como: https://pt-br.imgbb.com/  (não sei exatamente qual é o prazo de expiração)

4) Criar uma função personalizada no Editor Avançado do Power Query que converte binário pra texto em Base 64 - teremos uma aula sobre isso no modulo de Linguagem M 🧙

## ✍️ Resumo - Tipo de Dado vs. Categoria de Dado
🧙 Em resumo: o Tipo de Dado é uma propriedade fundamental de uma coluna que afeta como os dados são tratados em todo o modelo de dados (definido dentro do Power Query Editor), enquanto a Categoria de Dados é uma propriedade mais específica que controla como os dados são apresentados em visualizações (gráficos) individuais (configurada em Ferramentas da Coluna, na Guia Modo de Exibição de Tabela do Power BI).

Configurar a Categoria de Dados é extremamente importante para trabalhar de forma efetiva e sem estresse com gráficos de mapa, URLs (links) e também com imagens no Power BI. Percebo que muitos "erros" e dificuldades em trabalhar com esses tipos de visualização na verdade acontecem pois os usuários se esquecem dessa etapa (que é um detalhe, mas detalhes importam). 

Depois dessa, você, data driven, não vai esquecer! 👊


