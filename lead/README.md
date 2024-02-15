# API de leads

Usada para gerenciar leads de parceiros

## Registra leads

Registra um lead de um parceiro

### POST /aberto/parceiro/{idParceiro}/lead

Registra um lead de um parceiro.

#### Parâmetros

```json
    {
		"DE_Pessoa":     "Joaquim de Teste",
		"EM_Email":      "teste@testando.com",
		"DE_Telefone":   "11999999999",
		"CO_CPF":        "00000000191",
		"DT_Nascimento": "1989-01-21",
		"SN_Autorizado": true,
    }
```

- `DE_Pessoa` (string, required) - Nome da pessoa
- `EM_Email` (string, optional) - Email da pessoa
- `DE_Telefone` (string, optional) - Telefone da pessoa
- `CO_CPF` (string, optional) - CPF da pessoa
- `DT_Nascimento` (string, optional) - Data de nascimento da pessoa
- `SN_Autorizado` (boolean, required) - Autorização para contato
- Não é permitido que email e telefone sejam nulos ao mesmo tempo

#### Respostas

- 201 - Lead registrado com sucesso
- 400 - Parâmetros inválidos