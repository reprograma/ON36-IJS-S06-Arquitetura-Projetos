# Exercício de Casa 🏠 

### Objetivos de aprendizagem do desafio 🎯

- Compreender os princípios e a importância da Arquitetura Hexagonal (Ports and Adapters) no desenvolvimento de software.
- Refatorar um código existente para seguir os princípios da Arquitetura Hexagonal.
- Integrar chamadas a APIs externas.

<h2 align=center> {Reprograma}Bank </h2>
<h3>Arquitetura Hexagonal</h3>

Seu desafio é refatorar o código existente do Reprograma Bank para seguir os princípios da Arquitetura Hexagonal, além disso, você deve integrar chamadas a uma API externa.


#### Exemplos
Aqui temos algumas APIs gratuitas que vocês podem usar no projeto de vocês. Essa lista é uma sugestão de APIs, podem usar uma ou mais delas para o seu contexto de negocio, também podem usar outras que vocês desejarem. 

Você vai ver que muitos dos exemplos estão vinculadas as contas de Pessoas Juridicas, como extra deixarei alguns requisitos para quem quiser implementar a conta PJ.

**ViaCEP API**
   - **Descrição**: A API ViaCEP permite a consulta de CEPs brasileiros e retorna informações detalhadas sobre o endereço, como rua, bairro, cidade e estado.
   - **URL**: `https://viacep.com.br/ws/{CEP}/json/`
   - **Uso**: Pode ser utilizada para validar endereços e garantir que os usuários cadastrados realmente fazem parte da comunidade.

**BrasilAPI**
   - **Descrição**: A BrasilAPI oferece uma série de serviços que podem ser úteis em uma aplicação bancária, incluindo consulta de CEP, consulta de banco, consulta de CNPJ e muito mais.
   - **URL**: `https://brasilapi.com.br/docs`
   - **Uso**: Além de validar endereços, pode ser usada para validar informações de CNPJ para pequenos negócios dentro da comunidade. Também pode usar para validar Feriados Nacionais, não permitindo algumas transações. Também fornece informações de banco para otimizar as transferencias e pix.

**AwesomeAPI - Conversão de Moedas**
   - **Descrição**: API brasileira que fornece taxas de câmbio e conversão de moedas. Suporta diversas moedas, incluindo o real brasileiro (BRL).
   - **URL**: `https://docs.awesomeapi.com.br/api-de-moedas`
   - **Uso**: Pode ser utilizada para fornecer informações sobre conversão de moedas, caso a comunidade tenha interesse em trabalhar com outras moedas além do real.

**MercadoBitcoin API**
   - **Descrição**: A API do MercadoBitcoin fornece informações sobre criptomoedas, incluindo preços, ordens de compra/venda e histórico de transações.
   - **URL**: `https://www.mercadobitcoin.com.br/api-doc/`
   - **Uso**: Pode ser interessante caso a comunidade decida explorar o uso de criptomoedas como forma de investimento ou transação.

**ReceitaWS API**
   - **Descrição**: API que permite consultar informações sobre empresas através do CNPJ. Útil para verificar a legitimidade de empresas que desejam abrir contas ou fazer transações no banco comunitário.
   - **URL**: `https://developers.receitaws.com.br/#/`
   - **Uso**: Pode ser usada para validar empresas e seus dados fiscais, garantindo que elas estão em conformidade com a lei.

**IPGeolocation API**
   - **Descrição**: Essa API fornece informações de geolocalização baseadas no endereço IP do usuário, podendo verificar a localização aproximada.
   - **URL**: `https://ipgeolocation.io/documentation`
   - **Uso**: Pode ser utilizada para adicionar uma camada extra de segurança, verificando se as transações estão sendo feitas de localizações esperadas.

**Simples Nacional API**
   - **Descrição**: API para consultar informações sobre o regime de Simples Nacional de empresas brasileiras.
   - **URL**: `https://api.municipio.me/v1/docs`
   - **Uso**: Pode ser útil para verificar se micro e pequenas empresas da comunidade estão devidamente cadastradas no Simples Nacional.


#### Desafio Extra (Conta PJ)
- Regras de negocio:
    - Toda conta PJ deve ter CNPJ, endereço da empresa, area de atuação e donos/sócios
    - Uma empresa pode ter um ou mais dono/socio
    - O dono/socio precisa ser cadastrado com todos os seus dados e fazer parte da comunidade
    - O dono/socio precisa ter uma conta corrente fisica para criar a conta PJ, porém ambas as contas funcionam de formas apartadas, mesmo tendo o mesmo cliente como dono
    - Tudo que uma conta corrente faz, a conta PJ também faz.


