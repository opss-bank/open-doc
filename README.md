# open-doc
Documentação das API OpssBank

## Lista de API

- [Produtos](produto/README.md)


## Fluxo de venda

O primeiro passo é listar os produtos disponíveis para o parceiro. Para isso, é necessário fazer requisição `GET /aberto/parceiro/{idParceiro}/produtos`. O retorno será uma lista de produtos, com os dados necessários para a venda.

Em seguida, é necessário fazer uma requisição `GET /aberto/produto/{idProduto}/campos` para listar os campos que devem ser preenchidos para o produto escolhido. O retorno será uma lista de campos, com os metadados dos campos que devem ser preenchidos.

Por fim, é necessário fazer uma requisição `POST /aberto/produto/{idProduto}/venda` para efetuar a venda. 