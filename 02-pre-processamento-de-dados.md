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


### Normalização

A normalização é um processo de transformação dos dados que objetiva torná-los mais apropriados à aplicação de algum algoritmo de mineração, como redes neurais artificiais ou métodos baseados em distância. A necessidade de normalização pode ser consequência de diversos fatores, como evitar a saturação dos neurônios em uma rede neural artificial de múltiplas camadas e fazer com que cada atributo dos dados de entrada tenha o mesmo domínio.

#### Normalização Max-Min

A normalização Max-Min realiza uma transformação linear nos dados originais. Assuma que <b>max_a</b> e <b>min_a</b> são, respectivamente, os valores máximo e mínimo de determinado atributo <b>a</b>. A normalização max-min mapeia um valor a em um valor no domínio , de acordo com seguinte equação:

a' = ((a - min_a) / (max_a - min_a)) * (novo_max_a - novo_min_a) + novo_min_a

A aplicação mais frequente dessa normalização é colocar todos os atributos de uma base de dados sob um mesmo intervalo de valores, por exemplo no intervalo [0, 1].

#### Normalização pelo z-score

Também conhecida por normalização de média zero, os valores de um atributo <b>a</b> são normalizados tendo como base a média e o desvio padrão de <b>a</b>,

a' = (a - ã) / a°

onde <b>ã</b> é a média e <b>a°</b> o desvio padrão de <b>a</b>.

#### Normalização pelo escalonamento decimal

A normalização pelo escalonamento decimal move a casa decimal dos valores do atributo <b>a</b>. O número de casas decimais movidas depende do valor máximo absoluto do atributo <b>a</b>.

a' = a / 10^j

onde <b>j</b> é o menor inteiro tal que |a'| < 1.

#### Normalização pelo interquartil

A normalização interquartil toma cada valor do atributo, subtrai a mediana e divide pelo intervalo interquartil (IQR, do inglês interquartile range).

Os quartis de um atributo ordenado são os três pontos que dividem o domínio do atributo em quatro grupos de cardinalidades iguais, cada qual composto por um quarto da quantidade total de dados.

- O primeiro quartil, <b>Q1</b> é definido como o ponto central entre o menor valor e a mediana;
- O segundo quartil, <b>Q2</b>, é a mediana, que divide o conjunto de dados ordenados em dois subconjuntos, cada um contendo metade da quantidade total dos dados;
- O terceiro quartil, <b>Q3</b>, é o valor do meio entre a mediana e o maior valor do atributo.

A normalização interquartil opera de acordo com a seguinte equação:

a' = a - Q2 / Q3 - Q1


## Discretização

Muitos algoritmos em mineração de dados não trabalham com dados mistos, ou seja, bases de dados com atributos categóricos e contínuos.

Nesses casos, atributos numéricos podem ser discretizados, dividindo o domínio do atributo em intervalos e ampliando a quantidade de métodos de análise disponíveis para aplicação.

Além disso, a discretização reduz a quantidade de valores de um dado atributo contínuo, facilitando, em muitos casos, o processo de mineração.

A maneira mais óbvia de discretizar um certo atributo é dividindo seu domínio em um número predeterminado de intervalos iguais, o que normalmente é feito no momento da coleta dos dados.

#### Encaixotamento (binning)

Atributos podem ser discretizados distribuindo-se seus valores em intervalos (bins) e substituindo-se o valor de cada intervalo pela média ou mediana.

Há dois tipos de métodos de encaixotamento: de mesma largura (o intervalo de cada caixa tem o mesmo tamanho) e de mesma frequência (a quantidade de objetos em cada caixa é a mesma).

Em ambos os casos, o método de encaixotamento funciona da seguinte maneira: (1) ordene os valores do atributo, (2) defina a quantidade de caixas, (3) escolha um ou mais valores representativos daquela caixa e (4) substi-tua todos os valores da caixa por esses valores.

O valor representativo pode ser calculado de diferentes maneiras, por exemplo, pela média ou moda da caixa, ou pelos valores extremos da caixa, sendo que, neste último, cada valor dentro da caixa é substituído pelo extremo mais próximo.

#### Histogramas

Similar à discretização por encaixotamento, a discretização por histogramas utiliza faixas para definir os intervalos de valores do atributo. Após a definição do histograma, os valores do atributo são substituídos de acordo com a faixa na qual estes se encontram; com isso, a quantidade de valores discretos dependerá da quantidade de faixas escolhidas.

#### Agrupamentos

Algoritmos de agrupamento são utilizados para particionar o atributo em grupos de valores seguindo um critério preestabelecido. Cada grupo de valores é representado por um protótipo que é utilizado em substituição aos valores que pertencem ao grupo, e diferentes métodos de agrupamento podem ser utilizados para realização dessa tarefa.
