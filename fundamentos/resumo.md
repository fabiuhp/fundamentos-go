# Fundamentos do Go

## Package

Em Go, **todos os arquivos** devem começar com a declaração de um package. A única exceção a essa regra são os comentários, que podem vir antes da declaração do package.

No momento de importar outros pacotes, é possível criar **alias** para esses pacotes. Alias são utilizados para facilitar a referência a pacotes dentro do código.

![Estrutura básica de um arquivo Go](../imagens/image.png)

### Importando Pacotes

Pacotes da **standard library** (biblioteca padrão do Go) **não recebem alias** por uma questão de padronização. Isso torna o código mais legível e facilita a compreensão de quais pacotes estão sendo utilizados.

#### Dot Import

Se você encontrar um import com um alias sendo um **"."**, isso significa que é um **dot import**. Com esse tipo de import, todas as funções, variáveis e tipos do pacote importado são inseridos diretamente no escopo atual, como se fossem parte do pacote onde estão sendo usados.

> **Atenção:** *Dot import não é uma prática recomendada!* Ele pode tornar o código confuso, dificultando a identificação de onde as funções e tipos foram definidos.

#### Underscore Import

Outro tipo de import é o com um alias **"_"**. Esse tipo de import é conhecido como **blank import**. O blank import **não traz** diretamente os elementos do pacote para o escopo atual. Ele é usado para executar o `init()` do pacote ou para registrar drivers, sem realmente utilizar as funções ou variáveis do pacote.

### Retrocompatibilidade

Uma das promessas do Go é a **retrocompatibilidade eterna**. Isso significa que futuras versões da linguagem não quebrarão o código escrito em versões anteriores, garantindo que o código seja durável e estável ao longo do tempo.
