<h1 align="center">
  <img src="assets/reprograma-fundos-claros.png" alt="logo reprograma" width="500">
</h1>

# Arquitetura Hexagonal

Turma Online S04 - Imersão JavaScript | Semana 06 | 2024 | Professora Jessica Felix

### Objetivo
Compreender e aplicar arquitetura hexagonal

### Resumo
O que veremos na aula de hoje?
- [Arquitetura Hexagonal](#arquitetura-hexagonal)
    - [Instruções](#instruções)
    - [Objetivo](#objetivo)
    - [Resumo](#resumo)

- [Conceitos](#conceitos)

  - [Arquitetura Hexagonal Aplicada](#arquitetura-hexagonal-aplicada)
    - [O que são e para que servem ](#o-que-são-e-para-que-servem)
    - [Benefícios](#benefícios)
    - [Abordagens](#abordagens)
    - [Implementação](#implementação)
  
  - [Conteúdo Extra](#conteúdo-extra)
    - [Camada ACL](#camada-acl)

  - [Exercícios](#exercícios)
  - [Material da aula](#material-da-aula)
  - [Links Úteis](#links-úteis)

# Conceitos

## Arquitetura Hexagonal Aplicada
  #### O que são e para que servem
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

