# E-commerce

<h2>Modelo EER (Extended-Entity Relationship) </h2>


![Diagrama_ecommerce_final](https://github.com/user-attachments/assets/d6a4d81e-69a7-443f-96f5-6aebbd2a1f4c)


<p>
Explicação Detalhada do Diagrama
  
Este diagrama representa um banco de dados para um sistema de e-commerce, estruturando as entidades e seus relacionamentos. Vamos detalhar cada uma das tabelas e suas conexões:

1️⃣ Entidades Principais

📦 PRODUTOS
Armazena informações sobre os produtos disponíveis no sistema.
Possui atributos como:
- IDPRODUTO: Identificador único do produto.
- CATEGORIA: Categoria do produto (Ex: Eletrônicos, Vestuário).
- DESCRICAO_PRODUTO: Descrição detalhada.
- PRECO: Valor do produto.

📋 PEDIDO
Representa as compras feitas pelos clientes.
Principais atributos:
- IDPEDIDO: Identificador do pedido.
- STATUS_PEDIDO: Status atual (Ex: Pendente, Enviado).
- DESCRICAO_PEDIDO: Informações adicionais sobre o pedido.
- CLIENTE_IDCLIENTE: Chave estrangeira ligando o pedido ao cliente que fez a compra.
- FRETE: Valor do frete.
- COD_RASTREIO: Código de rastreamento.

👤 CLIENTE
Representa os clientes cadastrados no sistema.
Atributos:
- IDCLIENTE: Identificador único.
- NOME: Nome do cliente.
- ENDERECO: Endereço cadastrado.
- IDENTIFICACAO: Chave usada para distinguir CPF e CNPJ.

🏢 FORNECEDOR
Representa as empresas que fornecem os produtos.
Atributos:
- IDFORNECEDOR: Identificador único do fornecedor.
- RAZAO_SOCIAL: Nome empresarial.
- CNPJ: Registro único da empresa.

📦 ESTOQUE
- Armazena a localização dos estoques onde os produtos estão armazenados.
- Relacionado com a tabela ESTOQUE_PRODUTOS que define a quantidade de produtos em cada estoque.

🛒 VENDEDORES PLATAFORMA
- Representa vendedores que utilizam a plataforma para comercializar produtos.
- Relacionado com PRODUTOS_POR_VENDEDOR, indicando quais produtos cada vendedor disponibiliza.

2️⃣ Relacionamentos Importantes
- FORNECE_PRODUTOS
Relaciona FORNECEDOR e PRODUTOS, indicando quais produtos cada fornecedor fornece.
- PRODUTOS_NO_PEDIDO
Relaciona PEDIDO e PRODUTOS, armazenando:
- QTD_PRODUTO: Quantidade do produto nesse pedido.
- PRODUTOS_POR_VENDEDOR
Relaciona VENDEDOR_PLATAFORMA e PRODUTOS, especificando a quantidade de um produto que cada vendedor possui.
- ESTOQUE_PRODUTOS
Relaciona ESTOQUE e PRODUTOS, indicando a quantidade disponível em cada local.
- CADASTRO_PF e CADASTRO_PJ
Permitem que clientes sejam identificados como Pessoa Física (CPF) ou Pessoa Jurídica (CNPJ).
Ambos possuem relação com a tabela EMAIL.


3️⃣ Analisando a Ligação entre PEDIDO e FORMA_PG

Agora vamos focar na relação entre PEDIDO e FORMA DE PAGAMENTO.

- FORMA_PG
Representa as diferentes formas de pagamento disponíveis.
Campos importantes:
- ID_CARTAO: Identificador do cartão.
- ID_CARTAO2: Possível segundo cartão.
- PIX: Chave PIX associada.
- BOLETO: Código do boleto.
- PROTOCOLO_PG: Identificação única da forma de pagamento.
- FORMA_PAGAMENTO_USADO
Relaciona PEDIDO e FORMA_PG, indicando qual método de pagamento foi usado em cada pedido.
Possui:
- PEDIDO_IDPEDIDO: Referência ao pedido.
- FORMA_PG_PROTOCOLO_PG: Referência à forma de pagamento utilizada.


✅ Conclusão da modelagem:

- Preserva histórico de pagamentos, garantindo que cada pedido tenha o método de pagamento registrado.
- Flexibilidade para permitir múltiplos pagamentos por pedido (se necessário no futuro).
- Evita repetição desnecessária de dados na tabela PEDIDO.
Caso você queira permitir múltiplos métodos de pagamento por pedido (Ex: parte no cartão e parte no PIX), essa modelagem já permite essa funcionalidade!
🚀
  
</p>

<h3>Contate-me: </h3>
<a href="https://www.linkedin.com/in/philype-santos/">Linkedin</a>
