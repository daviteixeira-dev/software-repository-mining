# Pré-processamento de Dados

## Limpeza de dados

O primeiro passo é verificar se a base necessita de algum procedimento de limpeza de dados.

Alguns objetos podem ter informações faltantes. Uma das opções é eliminar esses objetos, reduzindo o tamanho da base; contudo, a remoção pode causar perda de informação importante.

<b>Valores ausentes</b> Um valor ausente costuma ser representado por um código de ausência, que pode ser um valor específico, um espaço em branco ou um símbolo (por exemplo, ''np.NaN''). Um valor ausente caracteriza um valor ignorado ou que não foi observado, e, nesse sentido, a substituição de valores ausentes, também conhecida como imputação, tem como objetivo estimar os valores ausentes com base nas informações disponíveis no conjunto de dados.

A imputação de valores ausentes assume que essa ausência de valor implica a perda de informação relevante de algum atributo.

Os métodos tradicionais de imputação de valores ausentes são:

- 1. <b>Ignorar o objeto</b>: consiste em remover da base (ignorar) todos aqueles objetos que possuem um ou mais valores ausentes.
- 2. <b>Imputar manualmente os valores ausentes</b>: consiste em escolher de forma empírica um valor a ser imputado para cada valor ausente.
- 3. <b>Usar uma constante global para imputar o valor ausente</b>: corresponde a substituir todos os valores ausentes de certo atributo por uma constante única.
- 4. <b>Imputação do tipo hot-deck</b>: um valor ausente é imputado usando o valor do mesmo atributo de um objeto similar aleatoriamente selecionado.
- 5. <b>Imputar de acordo com a última observação (last observation carried forward)</b>: consiste em ordenar a base de dados seguindo um ou mais de seus atributos e então busca cada valor ausente e usa aquele valor da célula imediatamente anterior para imputar o valor ausente.
- 6. <b>Usar a média ou moda de um atributo para imputar o valor ausente</b>: o método consiste em substituir os valores ausentes de cada atributo pela média (no caso de atributos numéricos) ou moda (no caso de atributos nominais) dos valores do atributo.
- 7. <b>Usar a média ou moda de todos os objetos da mesma classe para imputar o valor ausente</b>: a diferença deste método para o anterior é que a média ou moda é tomada considerando apenas os objetos da mesma classe daquele que contém o valor ausente.
- 8. <b>Usar modelos preditivos para imputar o valor ausente</b>: qualquer método preditivo pode ser usado para estimar o valor ausente.

Uma abordagem mais sistemática de tratamento de valores ausentes deve considerar quatro passos:

- investigar as razões dos dados ausentes de forma que os evite;
- investigar o impacto dos dados ausentes no resultado das análises a serem feitas em termos de confiabilidade, validade e generalização das conclusões;
- considerar os vários métodos de imputação de valores ausentes; e
- investigar o resultado da aplicação de cada um dos métodos considerados no passo anterior.

## Redução dos dados

A redução dos dados tem como um dos objetivos a construção de bases de dados menores para aumento do desempenho computacional, ao mesmo tempo que tenta manter as características originais dos dados.

O aumento do número de objetos e da dimensão do espaço (número de atributos na base) pode fazer com que os dados disponíveis se tornem esparsos e as medidas matemáticas usadas na análise tornem-se numericamente instáveis. .

Além disso, uma quantidade muito grande de objetos e atributos pode tornar o processamento dos algoritmos de mineração muito complexo.

As técnicas de redução de dados podem ser aplicadas tanto para reduzir a quantidade de objetos da base quanto para reduzir a quantidade de atributos que os descrevem (dimensionalidade),

Dentre os métodos de redução de dados destacam-se:

- <b>Seleção de atributos (ou características)</b>: efetua uma redução de dimensionalidade na qual atributos irrelevantes, pouco relevantes ou redundantes são detectados e removidos.
- <b>Compressão de atributos</b>: também efetua uma redução da dimensionalidade, mas empregando algoritmos de codificação ou transformação de dados (atributos), em vez de seleção.
- <b>Redução no número de dados</b>: neste método, os dados são removidos, substituídos ou estimados por representações menores (mais simples), como modelos paramétricos (que armazenam apenas os parâmetros do modelo em vez dos dados) e os métodos não paramétricos, como agrupamento, amostragem e histogramas.
- <b>Discretização</b>: os valores de atributos são substituídos por intervalos ou níveis conceituais mais elevados, reduzindo a quantidade final de atributos.

### Redução do número de dados

Métodos de <b>amostragem</b> tem como objetivo selecionar um subconjunto de objetos de uma base que seja representativo de toda ela para efeitos de análise ou estudo.

Os principais métodos de amostragem são:

- <b>Amostragem aleatória sem substituição</b>: uma amostra com <b>n</b> objetos distintos <b>(n < N)</b> é retirada aleatoriamente da base de dados.
- <b>Amostragem aleatória com substituição</b>: similar ao caso anterior, mas cada objeto retirado da base é armazenado e devolvido à base, de forma que ele possa ser selecionado novamente.
- <b>Amostragem sistemática</b>: consiste em organizar a base de dados seguindo algum critério, por exemplo, do menor ao maior valor de algum atributo do objeto ou do objeto mais antigo ao mais novo, e selecionar objetos de forma sistemática, como por exemplo, os objetos cujos índices são pares ou apenas os objetos gerados no ano atual.
- <b>Amostragem por grupo</b>: se uma base de dados está agrupada em M grupos disjuntos, então <b>m</b> grupos <b>(m < M)</b> podem ser escolhidos aleatoriamente.
- <b>Amostragem estratificada</b>: se a base de dados está dividida em grupos ou classes, então na amostragem estratificada a proporção de dados de cada classe é mantida.

Uma vantagem da amostragem é que seu custo computacional é proporcional ao tamanho da amostra a ser retirada da base e, portanto, é sublinear em relação ao tamanho original da base.

A principal desvantagem do método é o possível erro do processo de mineração por causa da amostragem.

### Compressão de atributos

As técnicas de compressão aplicam uma codificação ou transformação para que uma representação compacta dos dados ou atributos originais seja obtida. Se os dados originais puderem ser reconstruídos a partir dos dados comprimidos sem perda de informação, então dizemos que o método de compressão é sem perda (lossless); senão, dizemos que é com perda (lossy).

A <b>análise de componentes principais</b> (Principal Component Analysis – PCA), um dos métodos mais úteis e eficazes na compressão de dados, é um procedimento estatístico que converte um conjunto de objetos com atributos possivelmente correlacionados em um conjunto de objetos com atributos linearmente descorrelacionados, chamados de componentes principais.

A análise de componentes principais é a principal técnica linear para a redução de dimensionalidade dos dados. Ela realiza um mapeamento linear (também chamado de projeção) dos dados em um espaço de dimensão menor, a fim de que a variância dos dados nesse espaço seja maximizada.

### Modelos de aproximação

Os modelos de aproximação de dados operam de forma completamente diferente dos métodos amostrais, e seu objetivo é representar ou ajustar os dados usando algum modelo que pode ser definido ou não por um conjunto de parâmetros.

## Transformação de dados

### Transformação

Os métodos de transformação de dados visam modificar ou consolidar os dados em formas apropriadas aos processos de mineração. Por exemplo, pode haver valores de um mesmo atributo escritos em maiúsculo e outros em minúsculo, e os formatos e as unidades podem ser diferentes. Problemas dessa natureza são resolvidos padronizando ou normalizando os dados.

### Padronização

O objetivo principal da padronização é resolver as diferenças de unidades e escalas dos dados.

Exemplos de transformação:

- <b>Capitalização</b>: dados nominais podem aparecer em minúsculo, maiúsculo ou ambos. Para evitar inconsistências com ferramentas sensíveis a letras maiúsculas ou minúsculas, é usual padronizar as fontes, normalmente para maiúsculo.
- <b>Caracteres especiais</b>: algumas ferramentas de mineração de dados podem ser sensíveis ao conjunto de caracteres utilizado em determinado idioma. Por exemplo, ferramentas projetadas para bases de dados na língua inglesa podem apresentar problemas decorrentes da acentuação utilizada na língua portuguesa. Uma simples troca de letras em valores nominais pode evitar eventuais problemas.
- <b>Padronização de formatos</b>: o uso de alguns tipos de atributos, como datas e números de documentos, permite diferentes formatos. Por exemplo, datas podem ser apresentadas DDMMAAAA ou MMDDAAAA (dependendo do país de origem), um número de CPF pode ser apresentado como XXX.XXX.XXX-XX ou como XXXXXXXXXXX. Para evitar esses problemas, é preciso observar e padronizar o formato de cada atributo da base, principalmente quando diferentes bases precisam ser integradas.
- <b>Conversão de unidades</b>: outro problema comum nas bases brutas é o uso de diferentes unidades de medida – por exemplo, centímetros ou metros, quilômetros por hora ou milhas por hora etc. Nesse caso, vale o mesmo princípio discutido anteriormente: todos os dados devem ser convertidos e padronizados em uma mesma unidade de medida.

$`
  x' = \frac{x - x_{\text{min}}}{x_{\text{max}} - x_{\text{min}}}
`$

```math
a' = \frac{a - a_{\text{min}}}{a_{\text{max}} - a_{\text{min}}}(a_{\text{novo_max}} - a_{\text{novo_min}}) + a_{\text{novo_min}}
```

teste
