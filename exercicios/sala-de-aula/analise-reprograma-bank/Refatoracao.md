# Refatoração 

## 1. Estruturar o Projeto
Primeiro, reorganize a estrutura de diretórios do projeto para refletir a arquitetura hexagonal:

```
/src
  /adapters
    /inbound
      - client.controller.ts
      - manager.controller.ts
    /outbound
      - client.repository.ts
      - account.repository.ts
  /domain
    - client.ts
    - account.ts
    - manager.ts
  /application
    - client.service.ts
    - account.service.ts
    - manager.service.ts
```

## 2. Criar a Camada de Domínio

Arquivos a criar:
client.ts: Define a estrutura e regras de negócio para clientes.
account.ts: Define a estrutura e regras de negócio para contas.
manager.ts: Define a estrutura e regras de negócio para gerentes.
Esses arquivos devem conter apenas lógica de negócio, sem dependências de tecnologia ou infraestrutura.

## 3. Criar a Camada de Aplicação
Arquivos a criar:
client.service.ts: Contém a lógica de aplicação para gerenciar clientes (criação, atualização, etc.).
account.service.ts: Contém a lógica de aplicação para gerenciar contas.
manager.service.ts: Contém a lógica de aplicação para gerenciar gerentes.
Esses serviços devem chamar as interfaces definidas nas portas.

## 4. Criar a Camada de Adaptadores

### Adaptadores de Entrada (Inbound)
Arquivos a modificar:
client.controller.ts: Modifique para que chame os métodos do client.service.ts em vez de interagir diretamente com a lógica de negócio.
manager.controller.ts: Modifique para que chame os métodos do manager.service.ts.

### Adaptadores de Saída (Outbound)
Arquivos a criar:
client.repository.ts: Implementa a interface para persistência de dados de clientes.
account.repository.ts: Implementa a interface para persistência de dados de contas.
Esses adaptadores devem implementar as interfaces que definem como a lógica de negócio interage com a persistência.

## 5. Definir Interfaces (Portas)
Arquivos a criar:
client.repository.interface.ts: Define os métodos que o repositório de clientes deve implementar.
account.repository.interface.ts: Define os métodos que o repositório de contas deve implementar.
Essas interfaces devem ser usadas pelas classes de serviço para interagir com os repositórios.

## 6. Injeção de Dependências
Implemente um mecanismo de injeção de dependências para conectar os adaptadores às classes de serviço. Isso pode ser feito usando um contêiner de injeção de dependências ou manualmente, conforme necessário.

## 7. Testes
Arquivos a modificar:
Atualize os testes existentes para refletir a nova estrutura e lógica.
Crie novos testes para os serviços e adaptadores, garantindo que a lógica de negócio e a interação com os adaptadores estejam corretas.

## 8. Revisão e Ajustes Finais
Após a refatoração, revise o código para garantir que todas as dependências estejam corretamente desacopladas e que a lógica de negócio esteja isolada. Teste a aplicação para verificar se todas as funcionalidades ainda operam conforme esperado.