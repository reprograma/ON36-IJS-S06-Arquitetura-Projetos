Depois de ler o livro Hexagonal Architecture Explained por Alistair Cockburn, um dos inventores da arquitetura Hexagonal, alguns highlights:

Os quatro elementos que fazem parte do padrão de Portas e Adaptadores (Hexagonal) propriamente dito são:

1.O aplicativo ou sistema em si, que chamaremos de "app",
2.As portas,
3.Os atores externos impulsionadores e motivados,
4.Adaptadores conforme necessário em cada porta.

Para ajudar a compreender e definir esta diferença, usamos os termos driving actors (aqueles que conduzem o aplicativo)
e driven actors (eles são conduzidos pelo aplicativo).

**Portas**
As portas definem o verdadeiro limite do aplicativo.
Cada interação entre o aplicativo e o mundo exterior acontece em uma porta,
usando a linguagem de interface que o próprio aplicativo define. 
Assim, as portas são a demarcação do que está dentro do aplicativo propriamente dito e do que está fora.
Organizamos as interações entre a aplicação e os atores externos, o motivo pelo qual eles estão interagindo com o aplicativo.
Neste modelo, cada conjuntode interações com um determinado propósito ou intenção é um porto.

**driving actors - Atores Externos Condutores**
Os condutores são aqueles que iniciam a interação com o sistema. 
Eles podem ser usuários que utilizam uma interface de usuário, sistemas externos que enviam solicitações,
ou qualquer entidade que provoque uma ação no aplicativo. Esses atores são responsáveis por acionar funcionalidades do sistema,
como, por exemplo, um usuário que faz login ou um sistema de pagamento que processa uma transação.

**driven actors -Atores Externos Conduzidos**
Os conduzidos, por outro lado, são os atores que recebem respostas ou resultados das interações com o sistema.
Eles são impactados pelas ações realizadas no aplicativo e podem incluir usuários que recebem feedback ou dados processados,
ou sistemas que consomem informações geradas pelo aplicativo.
Por exemplo, um usuário que recebe uma confirmação de um pedido ou um sistema externo que recebe dados de um serviço de API.

**Configurador**
Algo tem que conectar todas as peças. Algum pedaço de código em algum lugar precisa
diga aos atores condutores como chegar ao aplicativo e diga ao aplicativo quais atores conduzidos usar.
Este é o papel do configurador.
Para fazer o seu trabalho, o configurador tem que conhecer todos os intervenientes: a aplicação, os atores ou seus adaptadores, e os atores orientados ou seus adaptadores.
A forma como você projeta o configurador não é especificada pelo padrão. 
Há muitas maneiras de projetá-lo, dependendo da sua situação. Seja como for que você organize isso,
as seguintes ações devem ocorrer:

1.Instanciar cada interator acionado (um adaptador acionado ou um ator acionado que
não precisa de adaptador).

1.Instancie o aplicativo.
2.Forneça ao aplicativo esses interatores conduzidos.
Instancie cada Interator de condução (ator ou adaptador) e passe-o para o aplicativo
usar.

Para aplicar um padrão, você precisa saber o que está dentro do escopo do padrão
em si, o que não faz parte do padrão, mas pode ser uma dica útil, e o que não faz
parte do padrão.

### O que é exigido pelo padrão

O padrão requer estas coisas:

1.O aplicativo define uma interface fornecida ou necessária para todas as inter-
ações.

1.O aplicativo define portas de condução (driving ports) para as interfaces fornecidas e portas dirigidas (driven ports)
para as interfaces dirigidas. Em linguagens que não exigem que interfaces sejam
declaradas, estes podem não ser explicitamente visíveis.

2.O aplicativo permite que os atores acionados sejam configurados em tempo de execução.

3.O aplicativo não tem dependências de código-fonte em seus atores primarios e secundários.

4.Atores externos podem interagir apenas com as portas definidas. Eles não são
tem permissão para acessar qualquer coisa dentro do hexágono diretamente.
5.As portas e interfaces são neutras em termos de tecnologia. Eles usam termos que apenas
expressar necessidades de negócios.

Dicas úteis, não exigidas pelo padrão
O padrão não exige essas coisas, mas implementá-las provavelmente
facilite sua vida:

1.O padrão não diz nada sobre como você implementa o configurador. Você
pode achar útil revisar os exemplos de configuradores fornecidos em
este livro.

1.O padrão não legisla como você nomeia suas portas. Mesmo assim, nós
recomendo a convenção de nomenclatura "Para fazer alguma coisa", pois ajuda
comunicar por que as interfaces são agrupadas.

O padrão não diz nada sobre quão granulares são as portas ou quantas
interfaces de função são agrupadas em uma porta. Na prática, preferimos menos
para mais, começando com uma porta por ator primário e uma por ator secundário,
já que correspondem às intenções das conversas.
3.O padrão não diz nada sobre como você organiza sua base de código.
Recomendamos o seguinte para facilitar a leitura do código pelas pessoas
e manter a arquitetura:

•Faça duas pastas de portas: "Driving Ports" e "Driven Ports". Coloque-os
ao lado da pasta do aplicativo, pois fazem parte do aplicativo.
•Faça duas pastas de adaptadores, "Adaptadores de Condução" e "Adaptadores Acionados".
Coloque-os em um espaço diferente da pasta do aplicativo.

1. O padrão não diz nada sobre como você organiza e projeta seu
adaptadores, incluindo se eles interagem diretamente ou não. Além de
casos de teste, os adaptadores de condução normalmente não interagem diretamente com o
adaptadores acionados. Claro, pode haver exceções que ainda não
encontrado.
2. O padrão não exclui especificamente a possibilidade de você ter um
Subsistema de Portas e Adaptadores dentro de alguns sistemas maiores de Portas e Adaptadores
tem. Se considerarmos Portas e Adaptadores como um caso especial de Estratégia de Componentes, isso implica que o componente interno de Portas e Adaptadores irá ambos
ser configurável para ter diferentes atores secundários e será completamente
testado isoladamente do resto do sistema maior de portas e adaptadores. (ver
Capítulo 6.4, O Artigo: Componente + Estratégia Generaliza Portas e Adaptadores)
Embora não seja impossível, isso nos parece improvável. Por esta razão, dizemos
que o padrão não se aninha. Veja o que acontece com hexágonos aninhados? (Capítulo
5.8).
