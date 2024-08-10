<h1 align="center">
  <img src="assets/reprograma-fundos-claros.png" alt="logo reprograma" width="500">
</h1>

# Arquitetura de Projetos

Turma Online S04 - Imersão JavaScript | Semana 06 | 2024 | Professora Jessica Felix

### Objetivo
Compreender e aplicar arquitetura hexagonal

### Resumo
O que veremos na aula de hoje?
- [Arquitetura de projetos](#arquitetura-de-projetos)
    - [Instruções](#instruções)
    - [Objetivo](#objetivo)
    - [Resumo](#resumo)

- [Conceitos](#conceitos)

  - [Arquitetura de Projetos](#arquitetura-de-projetos)
    - [O que é e para que serve ](#o-que-é-e-para-que-serve)
    - [Benefícios](#benefícios)
    - [Abordagens](#abordagens)
    - [Implementação](#implementação)
      
  - [Arquitetura Hexagonal Aplicada](#arquitetura-hexagonal-aplicada)
    - [O que é e para que serve ](#o-que-é-e-para-que-serve)
    - [Benefícios](#benefícios)
    - [Abordagens](#abordagens)
    - [Implementação](#implementação)
  
  - [Conteúdo Extra](#conteúdo-extra)
    - [Camada ACL](#camada-acl)

  - [Exercícios](#exercícios)
  - [Material da aula](#material-da-aula)
  - [Links Úteis](#links-úteis)

# Conceitos

## Arquitetura de Projetos

### O que é e para que serve
Arquitetura de projetos em software refere-se à estruturação e organização de um sistema de software, onde são definidos os componentes, suas interações e a forma como eles se comunicam. Essa arquitetura é crucial para garantir que o sistema atenda aos requisitos funcionais e não funcionais, como desempenho, escalabilidade e manutenibilidade.

A arquitetura de software estabelece a base sobre a qual o software será construído, funcionando como um guia para os desenvolvedores. Ela não apenas define a estrutura do sistema, mas também orienta sobre como os diferentes componentes devem interagir, o que é essencial para o desenvolvimento de sistemas complexos.

**Principais Aspectos da Arquitetura de Projetos**

**Componentes e Interações**: A arquitetura detalha quais são os componentes do sistema (como módulos, classes, serviços) e como eles se comunicam entre si. Isso ajuda a visualizar a estrutura do software e facilita a identificação de dependências e interações.

**Estilos Arquiteturais**: Existem diversos estilos arquiteturais, como arquitetura em camadas, microserviços, e cliente-servidor. A escolha do estilo adequado é fundamental para atender às necessidades específicas do projeto e garantir a escalabilidade e a eficiência do sistema.

**Documentação**: A documentação da arquitetura é essencial para a comunicação entre as partes interessadas e para a manutenção do sistema ao longo do tempo. Ela registra decisões de design e permite o reuso de componentes em projetos futuros.

**Qualidade do Sistema**: A arquitetura impacta diretamente atributos de qualidade do software, como confiabilidade, desempenho e portabilidade. Um bom design arquitetural pode minimizar riscos e facilitar a evolução do sistema

**Arquitetura Alvo**
O que é? A arquitetura alvo é como um plano ou um modelo do que queremos que nosso software se torne no futuro.
Por que é importante? Ela nos ajuda a decidir como organizar o software para que ele funcione bem, seja fácil de manter e atenda às necessidades do negócio.
Exemplo: Imagine que você quer construir uma casa. A arquitetura alvo seria o projeto da casa que você deseja, com todos os detalhes de como ela deve ser.

**Degradação de Arquitetura**
O que é? A degradação de arquitetura acontece quando o software que foi construído não segue o plano original. Isso significa que ele pode ter problemas de qualidade ou não funcionar como esperado.
Por que acontece? Isso pode ocorrer por várias razões, como pressa para entregar o projeto, mudanças nas necessidades ou decisões ruins durante o desenvolvimento.
Exemplo: Voltando à casa, a degradação seria se, durante a construção, você mudasse o projeto e acabasse com uma casa que não tem a estrutura que você queria, como um quarto a menos ou sem janelas.
Resumindo
Arquitetura Alvo: É o plano ideal para o software.
Degradação de Arquitetura: É quando o software construído não segue esse plano e pode ter problemas.

#### Benefícios
Implementar uma arquitetura de software bem definida traz diversos benefícios, incluindo:
Facilidade de Manutenção: Sistemas bem arquitetados são mais fáceis de manter e atualizar, pois suas estruturas são claras e organizadas.
Escalabilidade: Uma boa arquitetura permite que o sistema cresça e se adapte a novas demandas sem comprometer seu desempenho.
Redução de Riscos: Ao identificar e documentar componentes e suas interações, a arquitetura ajuda a mitigar riscos associados a falhas e problemas de integração.

Em resumo, a arquitetura de projetos em software é um elemento vital que determina como um sistema será construído e operado, influenciando sua eficácia e adaptabilidade ao longo do tempo.

#### Abordagens
Existem várias abordagens de arquitetura de projetos em software, cada uma com características e adequações específicas para diferentes tipos de sistemas e necessidades. Abaixo estão algumas das principais abordagens, incluindo a arquitetura hexagonal.

**1. Arquitetura Hexagonal**
A arquitetura hexagonal, também conhecida como Ports and Adapters, foi proposta por Alistair Cockburn. Essa abordagem visa desacoplar o núcleo da aplicação de suas interações externas, como interfaces de usuário, bancos de dados e serviços externos. O objetivo é permitir que a lógica de negócio permaneça independente de detalhes de implementação, facilitando testes e adaptações a novas tecnologias.

**2. Arquitetura Monolítica**
Na arquitetura monolítica, todo o sistema é construído como um único componente. Todas as funcionalidades estão integradas em uma única base de código, o que simplifica o desenvolvimento e a implantação. No entanto, essa abordagem pode apresentar desafios em relação à escalabilidade e manutenção, especialmente em sistemas grandes e complexos.

**3. Arquitetura em Camadas**
A arquitetura em camadas organiza o sistema em diferentes níveis, onde cada camada tem responsabilidades específicas. Normalmente, as camadas incluem apresentação, lógica de negócio e acesso a dados. Essa abordagem facilita a manutenção e a evolução do sistema, pois as alterações em uma camada não afetam diretamente as outras.

**4. Arquitetura Orientada a Serviços (SOA)**
A arquitetura orientada a serviços (SOA) é uma abordagem que estrutura o sistema como um conjunto de serviços independentes que se comunicam entre si através de interfaces bem definidas. Essa abordagem promove a reutilização de serviços e facilita a integração com outros sistemas, sendo especialmente útil em ambientes corporativos complexos.

**5. Arquitetura de Microserviços**
Similar à SOA, a arquitetura de microserviços divide o sistema em pequenos serviços independentes, cada um responsável por uma funcionalidade específica. Essa abordagem permite que equipes diferentes trabalhem em serviços distintos de forma autônoma, melhorando a escalabilidade e a flexibilidade do sistema.

**6. Arquitetura Client-Server**
Na arquitetura client-server, o sistema é dividido em duas partes: o cliente, que solicita serviços, e o servidor, que os fornece. Essa abordagem é comum em aplicações web e móveis, onde o cliente interage com o servidor para acessar dados e funcionalidades.

A escolha da abordagem arquitetural deve ser baseada em uma análise cuidadosa das necessidades do projeto, considerando fatores como escalabilidade, manutenibilidade e requisitos específicos do negócio. Cada abordagem tem suas vantagens e desvantagens, e a decisão deve refletir uma compreensão profunda do contexto em que o sistema será implementado

#### Implementação
O processo de implementação de uma abordagem arquitetural envolve diversas etapas e considerações importantes para garantir o sucesso do projeto. Aqui estão algumas das principais etapas desse processo:

**1. Análise dos Requisitos**
A primeira etapa é realizar uma análise detalhada dos requisitos funcionais e não funcionais do sistema. Isso inclui entender as necessidades do negócio, as restrições técnicas e os atributos de qualidade desejados, como desempenho, escalabilidade e segurança.

**3. Escolha da Abordagem Arquitetural**
Com base na análise dos requisitos, é feita a escolha da abordagem arquitetural mais adequada para o projeto. Algumas das principais abordagens incluem:
Arquitetura Monolítica
Arquitetura em Camadas
Arquitetura Orientada a Serviços (SOA)
Arquitetura de Microserviços
Arquitetura Cliente-Servidor
A escolha deve considerar fatores como complexidade do sistema, escalabilidade, manutenibilidade e alinhamento com as estratégias da empresa.

**3. Definição da Estrutura de Componentes**
Após escolher a abordagem, a próxima etapa é definir a estrutura de componentes do sistema, incluindo seus relacionamentos e interfaces. Isso envolve a identificação dos componentes de negócio, utilitários e de infraestrutura necessários.

**4. Definição de Tecnologias e Padrões**
São definidas as tecnologias, frameworks e padrões de projeto que serão utilizados na implementação. Essa escolha deve considerar fatores como experiência da equipe, disponibilidade de recursos e alinhamento com os requisitos.

**6. Prototipação e Validação**
Antes de partir para a implementação completa, é comum criar protótipos e validá-los com as partes interessadas. Isso permite identificar problemas e validar decisões arquiteturais de forma antecipada.

**7. Implementação e Testes**
Com a arquitetura definida, parte-se para a implementação do sistema, seguindo as melhores práticas de desenvolvimento. Testes em diferentes níveis (unitário, integração, sistema) são realizados para garantir a qualidade.

**8. Implantação e Monitoramento**
Após os testes, o sistema é implantado no ambiente de produção. Métricas de monitoramento são definidas para acompanhar o desempenho e identificar possíveis problemas.

**9. Manutenção e Evolução**
O sistema entra em um ciclo de manutenção e evolução, onde novos requisitos são implementados e problemas são resolvidos. Nessa etapa, a documentação da arquitetura é essencial para facilitar futuras alterações.
Em resumo, implementar uma abordagem arquitetural envolve um processo iterativo de análise, design, implementação, testes e monitoramento, sempre alinhado com os requisitos do sistema e as melhores práticas da engenharia de software.

## Arquitetura Hexagonal Aplicada
### O que é e para que serve
A arquitetura hexagonal, também conhecida como arquitetura de portas e adaptadores, é um padrão de arquitetura de software que visa desacoplar a aplicação do seu ambiente externo. Ela divide a aplicação em duas partes principais:

**Domínio**: Contém as regras de negócio da aplicação, independente de qualquer tecnologia ou ambiente externo.

**Adaptadores**: Responsáveis pela comunicação com o ambiente externo, como banco de dados, APIs, interfaces de usuário, etc. Eles se adaptam às portas definidas pelo domínio.

A comunicação entre o domínio e os adaptadores é feita através de portas, que são interfaces genéricas definidas pelo domínio e implementadas pelos adaptadores.

#### Benefícios
- Desacoplamento: O domínio é isolado do ambiente externo, facilitando a manutenção e evolução da aplicação.
- Flexibilidade: Novos adaptadores podem ser adicionados facilmente, permitindo integração com diferentes tecnologias.
- Testabilidade: O domínio pode ser testado independentemente, pois não depende de adaptadores específicos.

#### Abordagens
- Definição do Domínio: Comece identificando o núcleo da aplicação, que contém a lógica de negócios e regras essenciais. Este núcleo deve ser independente de qualquer tecnologia externa.
    
- Criação de Portas: Estabeleça interfaces (portas) que definem como o domínio interage com o mundo externo. Essas portas permitem que diferentes adaptadores se conectem ao núcleo.

- Implementação de Adaptadores: Desenvolva adaptadores que implementem as interfaces definidas pelas portas. Esses adaptadores podem incluir controladores, serviços de banco de dados, APIs externas, entre outros.
  
- Organização Modular: Estruture sua aplicação em módulos claros, facilitando a manutenção e a evolução do sistema. Cada módulo deve conter seu próprio domínio e adaptadores.

- Testabilidade: Utilize a separação entre domínio e adaptadores para criar testes unitários e de integração, garantindo que a lógica de negócios possa ser testada independentemente.

#### Implementação
1. Definir o Domínio:
Identifique as regras de negócio essenciais do seu sistema.
Crie módulos separados para cada entidade de negócio (ex: usuários, pedidos, produtos).
Cada módulo deve conter suas próprias classes de entidade, serviços e casos de uso.

2. Criar Portas:
Defina interfaces (portas) que descrevem como o domínio se comunica com o mundo externo.
As portas devem ser definidas no módulo de domínio.
Exemplos de portas: repositórios para acesso a dados, serviços externos, etc.

3. Implementar Adaptadores:
Crie adaptadores que implementam as portas definidas no domínio.
Os adaptadores ficam fora do domínio, em módulos separados.
Exemplos de adaptadores: controladores HTTP, serviços de banco de dados, integrações com APIs externas.

4. Organizar a Estrutura de Pastas:
Organize os módulos por domínio, não por camada técnica.
Cada módulo deve conter seu próprio domínio, portas e adaptadores.
Exemplo de estrutura:

```
src/
 modules/
   users/
     domain/
     ports/
     adapters/
   orders/
     domain/
     ports/
     adapters/
```

6. Injeção de Dependências:
Use a injeção de dependências do NestJS para conectar os adaptadores às portas.
Registre os adaptadores como provedores nos módulos apropriados.
Injete as dependências necessárias nos construtores das classes.

7. Testes:
Teste o domínio isoladamente, usando doubles (stubs, mocks) para os adaptadores.
Teste os adaptadores separadamente, usando doubles para o domínio.
Certifique-se de ter uma boa cobertura de testes unitários e de integração

O foco está em separar claramente as responsabilidades, manter o domínio isolado e facilitar a testabilidade e manutenção do código.

## Conteúdo extra
   #### Camada ACL
A camada ACL, ou Camada de Anti-Corrupção, é uma camada de tradução em software que facilita a comunicação entre sistemas, prevenindo inconsistências. Ela atua como um intermediário, permitindo que diferentes sistemas interajam sem que mudanças em um deles afetem diretamente o outro. 

Essa abordagem é especialmente útil ao integrar serviços de terceiros ou sistemas legados, pois centraliza as adaptações necessárias, minimizando o impacto nas partes que consomem esses serviços.

A camada ACL não é uma parte intrínseca da arquitetura hexagonal, mas pode ser integrada como um adaptador ou uma porta que gerencia a autorização e autenticação dentro da aplicação. 

Na arquitetura hexagonal, o foco está na separação entre o domínio e as tecnologias externas, permitindo que a lógica de negócios permaneça independente de detalhes de implementação, como controle de acesso. 

Portanto, a ACL pode ser implementada como um adaptador que se comunica com o domínio através de interfaces definidas, respeitando os princípios da arquitetura hexagonal.

***
### Exercícios 
* [Exercicio para sala](/exercicios/para-sala/)

Refatorar a aplicação vista em sala de aula anteriormente para arquitetura hexagonal

* [Exercicio para casa](/exercicios/para-casa/)

**NÃO OBRIGATORIO**
Criar uma prova de conceito (Poc) de Arquitetura Hexagonal

### Material da aula 

https://github.com/reprograma/ON36-IJS-S05-reprograma-bank

### Links Úteis

[https://engsoftmoderna.info/artigos/arquitetura-hexagonal.html]

[https://dev.to/pmafra/arquitetura-hexagonal-explicada-como-transformar-seu-desenvolvimento-de-software-43d9]

[https://www.santanderopenacademy.com/pt_br/blog/arquitectura-hexagonal.html]

[https://netflixtechblog.com/ready-for-changes-with-hexagonal-architecture-b315ec967749]

[https://youtu.be/on9FiB18A6Q?si=cu4eFTLl7IJrHpOP]

<p align="center">
Desenvolvido com :purple_heart:  
</p>

