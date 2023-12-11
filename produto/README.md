# API de Produtos

Usada para venda de produtos por parceiros.

## Lista de Produtos

### GET /aberto/parceiro/{idParceiro}/produtos

Retorna a lista de produtos de um parceiro.

#### Retorno

```json
{
	"data": [
		{
			"DE_Produto": "OPSS Care 80",
			"ID_Opcao": 0,
			"NU_CamposObrigatorios": 34815,
			"NU_CamposOpcionais": 997376,
			"ProdutoID": "6ba0efe7-0a71-428d-bd1b-ba9e0cda0e4d",
			"SN_Adicional": false,
			"SN_VendaUnica": true,
			"TX_Descricao": "Pacote de Benefícios conta com uma série de vantagens para que você e sua família possam usufruir em vida de uma série de benefícios e assistências que trarão para vocês mais tranquilidade no dia a dia e na hora de sua falta, promovendo segurança e tranquilidade para você e seus familiares!",
			"VL_Seguro": 8000000,
			"VL_Valor": 5690,
			"VL_Valor2": 0,
			"VL_Valor3": 0,
			"informacoes": [
				{
					"DE_Titulo": "Morte Acidental (MA)",
					"DE_Valor": "80.000,00"
				},
				{
					"DE_Titulo": "Invalidez Permanente Total ou Parcial por Acidente (IPA)",
					"DE_Valor": "80.000,00"
				},
				{
					"DE_Titulo": "Seguro Assistência Funeral Familiar Superluxo",
					"DE_Valor": "7.000,00"
				},
				{
					"DE_Titulo": "Personal Care",
					"DE_Valor": "Contratado"
				},
				{
					"DE_Titulo": "Serviço de Desconto em Consultas, Exames e Laboratórios",
					"DE_Valor": "Contratado"
				},
				{
					"DE_Titulo": "Consultoria de Planejamento Financeiro Familiar (ConsultFin)",
					"DE_Valor": "Contratado"
				}
			]
		},
		{
			"DE_Produto": "OPSS Care 100",
			"ID_Opcao": 0,
			"NU_CamposObrigatorios": 34815,
			"NU_CamposOpcionais": 997376,
			"ProdutoID": "df33885a-667d-4212-b1b0-cfa1fcbe6783",
			"SN_Adicional": false,
			"SN_VendaUnica": true,
			"TX_Descricao": "Pacote de Benefícios conta com uma série de vantagens para que você e sua família possam usufruir em vida de uma série de benefícios e assistências que trarão para vocês mais tranquilidade no dia a dia e na hora de sua falta, promovendo segurança e tranquilidade para você e seus familiares!",
			"VL_Seguro": 10000000,
			"VL_Valor": 6490,
			"VL_Valor2": 0,
			"VL_Valor3": 0,
			"informacoes": [
				{
					"DE_Titulo": "Morte Acidental (MA)",
					"DE_Valor": "100.000,00"
				},
				{
					"DE_Titulo": "Invalidez Permanente Total ou Parcial por Acidente (IPA)",
					"DE_Valor": "100.000,00"
				},
				{
					"DE_Titulo": "Seguro Assistência Funeral Familiar Superluxo",
					"DE_Valor": "7.000,00"
				},
				{
					"DE_Titulo": "Personal Care",
					"DE_Valor": "Contratado"
				},
				{
					"DE_Titulo": "Serviço de Desconto em Consultas, Exames e Laboratórios",
					"DE_Valor": "Contratado"
				},
				{
					"DE_Titulo": "Consultoria de Planejamento Financeiro Familiar (ConsultFin)",
					"DE_Valor": "Contratado"
				}
			]
		}
	]
}
```

Para diferenciar se um campo é obrigatório ou opcional, basta verificar se o bit correspondente está ligado no campo `NU_CamposObrigatorios` ou `NU_CamposOpcionais`.

Essa verificação pode ser feita com a seguinte expressão:

```javascript
var campo = 1; // Campo CPF
var obrigatorio = (produto.NU_CamposObrigatorios & campo) == campo;
var opcional = (produto.NU_CamposOpcionais & campo) == campo;
```


### GET /aberto/produto/{idProduto}/campos

Lista metadados de campos possíveis de serem preenchidos para um produto.

#### Retorno

```json
{
	"data": [
		{
			"id": 1,
			"label": "CPF",
			"mandatory": true,
			"name": "CO_CPF",
			"regex": "[0-9]{11}"
		},
		{
			"id": 2,
			"label": "Nome",
			"mandatory": true,
			"name": "DE_Pessoa",
			"regex": ""
		},
		{
			"id": 4,
			"label": "Nascimento",
			"mandatory": true,
			"name": "DT_Nascimento",
			"regex": "[0-9]{8}|[0-9]{2}-[0-9]{2}-[0-9]{4}"
		},
		{
			"id": 8,
			"label": "Cep",
			"mandatory": true,
			"name": "CO_Cep",
			"regex": "[0-9]{8}|[0-9]{5}-[0-9]{3}"
		},
		{
			"id": 16,
			"label": "Endereço",
			"mandatory": true,
			"name": "DE_Endereco",
			"regex": ""
		},
		{
			"id": 32,
			"label": "Número",
			"mandatory": true,
			"name": "DE_Numero",
			"regex": ""
		},
		{
			"id": 64,
			"label": "Bairro",
			"mandatory": true,
			"name": "DE_Bairro",
			"regex": ""
		},
		{
			"id": 128,
			"label": "Cidade",
			"mandatory": true,
			"name": "DE_Cidade",
			"regex": ""
		},
		{
			"id": 256,
			"label": "Estado",
			"mandatory": true,
			"name": "SG_Estado",
			"regex": "[a-zA-Z]{2}"
		},
		{
			"id": 512,
			"label": "Complemento",
			"mandatory": true,
			"name": "DE_Complemento",
			"regex": ""
		},
		{
			"id": 1024,
			"label": "Telefone",
			"mandatory": true,
			"name": "DE_Telefone",
			"regex": "[0-9]{10,11}"
		},
		{
			"id": 2048,
			"label": "Email",
			"mandatory": false,
			"name": "EM_Email",
			"regex": ""
		},
		{
			"id": 4096,
			"label": "Identidade",
			"mandatory": false,
			"name": "CO_Identidade",
			"regex": ""
		},
		{
			"id": 8192,
			"label": "Órgão",
			"mandatory": false,
			"name": "SG_OrgaoExpedidor",
			"regex": ""
		},
		{
			"id": 32768,
			"label": "Sexo",
			"mandatory": true,
			"name": "CO_Sexo",
			"regex": ""
		},
		{
			"id": 65536,
			"label": "Expedição",
			"mandatory": false,
			"name": "DT_Expedicao",
			"regex": "[0-9]{8}|[0-9]{2}-[0-9]{2}-[0-9]{4}"
		},
		{
			"id": 131072,
			"label": "Telefone Fixo",
			"mandatory": false,
			"name": "DE_TelefoneFixo",
			"regex": ""
		},
		{
			"id": 262144,
			"label": "Profissão",
			"mandatory": false,
			"name": "DE_Profissao",
			"regex": ""
		},
		{
			"id": 524288,
			"label": "Estado Civil",
			"mandatory": false,
			"name": "ID_EstadoCivil",
			"regex": ""
		}
	]
}
```

### POST /aberto/parceiro/{idParceiro}/venda

Registra uma venda de um produto, feita por um parceiro.

#### Parâmetros

```json
	{
		"venda":[
			{
				"produto":
				{
					"ProdutoID":"e929814e-8909-4e97-9871-1b820ea6e94e",
					"ID_Opcao":1
				},
				"beneficiado":{
					"DE_Pessoa":"Joaquim de Teste",
					"CO_CPF":"00000000191",
					"DT_Nascimento":"1962-04-27",
					"CO_DDD":"",
					"CO_Telefone":"",
					"EM_Email":"teste@email.com"
				}
			},
			{
				"produto":
				{
					"ProdutoID":"76b22ecc-9e08-437d-b733-3a5c10feffc5",
					"ID_Opcao":2
				},
				"beneficiado":
				{
					"DE_Pessoa":"Joaquim de Teste",
					"CO_CPF":"00000000191",
					"DT_Nascimento":"1962-04-28",
					"CO_Identidade":"1111",
					"SG_OrgaoExpedidor":"ssp",
					"DT_Expedicao":"09092009",
					"SG_EstadoExpedidor":"mg",
					"CO_Sexo":"F",
					"CO_Cep":"35702700",
					"DE_Endereco":"Rua José de Alencar",
					"DE_Bairro":"Residencial Sete Lagoas",
					"DE_Numero":"46",
					"DE_Complemento":"casa",
					"DE_Cidade":"Sete Lagoas",
					"SG_Estado":"MG",
					"CO_DDD":"31",
					"CO_Telefone":"978643214",
					"CO_DDD1":"",
					"CO_Telefone1":"",
					"EM_Email":"teste@email.com",
					"ID_Profissao":2336,
					"ID_EstadoCivil":2549
				},
				"beneficiarios":[
					{
						"DE_Pessoa":"JOÃO DA SILVA",
						"ID_Parentesco":1,
						"VL_Proporcao":50
					}
				]
			}
		]
	}
```

### GET /aberto/produto/{id}/pdf

Gera PDF com detalhes de um produto.
