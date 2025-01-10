# Mineração de Dados

## Dados, informação e conhecimento

### Conceitos básicos

Dado, informação e conhecimento:

- O <b>dado</b> é um fato, um valor documentado ou um resultado de medição.
- Quando um significado é atribuído aos dados, gera-se uma <b>informação</b>.
- Quando um agente se torna consciente destes significados e torna-se capaz de tomar decisões a partir destes, temos o <b>conhecimento</b>.

<b>Dados não-estruturados</b>: dado não estruturado é aquele que não possui um modelo de dados, que não está organizado de uma maneira predefinida ou que não reside em locais definidos.

A Mineração de Dados surgiu como área de pesquisa e aplicação independente em meados da década de 1990, mas suas origens na matemática, estatística e computação são muito anteriores a esse período. A área também ganhou evidência nos últimos anos após ser cunhado o termo Big Data e com a publicação do relatório intitulado: Big Data: The Next Frontier for Innovation, Competition, and Productivity? pelo McKinsey Global Institute em meados de 2011.

<b>Dados semi-estruturados</b>: o dado semiestruturado é um tipo de dado que não possui a estrutura completa de um modelo de dados, mas também não é totalmente desestruturado.

<b>Dados estruturados</b>: dados descritos em campos fixos - por exemplo, uma tabela, uma planilha ou um banco de dados - de acordo com um modelo de dados, isto é, a descrição dos objetos juntamente com suas propriedades e relações.

Cada <b>linha</b> da tabela de dados geralmente corresponde a um <b>objeto</b>, uma <b>instância</b>, um exemplo, um registro, um vetor de entradas ou padrão (de entrada ou treinamento).

Cada <b>coluna</b>, por sua vez, corresponde a um <b>atributo</b>, uma <b>característica</b> (features) ou uma variável.

- Atributo dependente vs. atributo independente
- Atributo numérico vs. atributo categórico

Níveis de medida de atributos:

- <b>Binário</b>: pode assumir apenas dois valores possíveis, por exemplo 0 ou 1;
- <b>Nominal</b>: pode possuir símbolos ou rótulos distintos, por exemplo "estado civil" pode assumir os valores "solteiro", "casado", etc;
- <b>Ordinal</b>: permite ordenar suas categorias, embora não necessariamente haja uma noção explícita de distância entre as categorias. Por exemplo: o atributo "nível educacional" pode assumir os valores "fundamental", "médio", "graduação", "mestrado", etc;
- <b>Razão</b>: quantidades para as quais o método de medida define o ponto zero, por exemplo a distância entre dois objetos, salário, etc.


### Problemas nos dados

O objetivo das técnicas de pré-processamento de dados é preparar os dados brutos para serem analisados de modo mais eficiente.

Para a maioria das bases de dados reais, a etapa de pré-processamento demandam bastante trabalho e consomem muito tempo, mas o sucesso da mineração depende fortemente do cuidado dedicado a essa etapa.

Tipos de problemas nos dados:

<b>Incompletude</b>: em uma base de dados pode faltar valores de um dado atributo ("célula"), pode faltar um atributo de interesse ("coluna") ou pode faltar um objeto de interesse ("linha").

<b>Inconsistência</b>: um dado inconsistente normalmente é aquele cujo valor está fora do domínio do atributo ou apresenta uma grande discrepância em relação aos outros dados.

<b>Ruído</b>: Um dado ruidoso é aquele que apresenta alguma variação em relação ao seu valor sem ruído e, portanto, podem levar a inconsistências na base de dados.

Conhecer e preparar de forma adequada os dados para análise é uma etapa chamada de pré-processamento de dados e que pode tornar todo o processo de mineração muito mais eficiente e eficaz.

Para fazer uso efetivo da mineração, é preciso pensar em algumas questões importantes antes de iniciar a análise:

- Existem dados ausentes, inconsistentes ou ruidosos? Como tratá-los?
- Quais são os tipos de atributos da base? É preciso padronizá-los?
- É possível resumir a base de dados?
- Há atributos naturalmente inter-relacionados?
- Existem atributos que são mais relevantes que outros?
- Existem atributos irrelevantes?

### Processo de preparação da base de dados

1. <b>Limpeza de dados</b>

O primeiro passo é verificar se a base necessita de algum procedimento de limpeza de dados.

Alguns objetos podem ter informações faltantes. Uma das opções é eliminar esses objetos, reduzindo o tamanho da base; contudo, a remoção pode causar perda de informação importante.

2. <b>Redução dos dados</b>

A redução dos dados tem como um dos objetivos a construção de bases de dados menores para aumento do desempenho computacional, ao mesmo tempo que tenta manter as características originais dos dados.

3. <b>Transformação</b>

Os métodos de transformação de dados visam modificar ou consolidar os dados em formas apropriadas aos processos de mineração.

Por exemplo, pode haver valores de um mesmo atributo escritos em maiúsculo e outros em minúsculo, e os formatos e as unidades podem ser diferentes.

Problemas dessa natureza são resolvidos padronizando ou normalizando os dados.

4. <b>Discretização</b>

Muitos algoritmos em mineração de dados não trabalham com dados mistos, ou seja, bases de dados com atributos categóricos e contínuos.

Nesses casos, atributos numéricos podem ser discretizados, dividindo o domínio do atributo em intervalos e ampliando a quantidade de métodos de análise disponíveis para aplicação.
