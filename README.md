# DESAFIO_Escola-ALF
## Descrição do projeto
 Neste repositório há uma API RESTful criada com o intuito de responder a um desafio de um processo seletivo.
 A API foi desenvolvida com a linguagem de programação C#, utilizando o editor de código-fonte Visual Studio Code. 
 Para a disponibilização dos dados foi utilizado o Framework ASP.NET Core.
 Para criar as requisições foi utilizada a ferramenta Postman, que tem como objetivo testar serviços de WEB APIs por meio do envio de requisições HTTP, sendo possível avaliar as respostas das requisições. 

## Critérios
 ### O Desafio

 A escola Alf aplica provas de múltipla escolha para os alunos. A nota do aluno na prova é determinada pela média ponderada das questões com os pesos de cada questão. Cada questão correta soma 1 ponto multiplicada pelo peso e cada questão errada 0. A nota final é a média aritmética das notas de todas as provas.

 ### Requisitos obrigatórios:

 Crie uma API HTTP que permita à escola: 

 - Cadastrar o gabarito de cada prova;
 - Cadastrar as respostas de cada aluno para cada prova;
 - Verificar a nota final de cada aluno;
 - Listar os alunos aprovados;

 Restrições
 - A nota total da prova é sempre maior que 0 e menor que 10.
 - A quantidade máxima de alunos é 100.
 - O peso de cada questão é sempre um inteiro maior que 0.
 - Os alunos aprovados tem média de notas maior do que 7.
 - A entrada e saída de dados deverá ser em JSON.

## Como rodar a aplicação
 Para executar a API através do Visual Studio Code, basta abrir o Terminal com a combinação de teclas `Ctrl + Shift + '`, selecionar a pasta "EscolaAlf_API" com o comando `cd` e a tecla `TAB` e digitar o seguinte comando:
 ```
 dotnet run
 ```
 ou
 ```
 dotnet watch run
 ```

## Exemplo das tabelas
 ![](IMG/TablesExample.png)

# Funcionamento da API
Este tópico tem a função de explicar como efetuar a comunicação com a API, através da apresentação dos Endpoints. Também há a demonstração dos recursos usados no código para efetuar as restrições citadas no desafio.
Toda entrada e saída de dados é em JSON.
## Endpoints
### Student
Obter todos os estudantes:
```
"name": "Get",
"request": {
    "method": "GET",
    "url": {
        "raw": "https://localhost:5001/Student"
    }
}
```

Obter o estudante pelo id:
```
"name": "GetById",
"request": {
    "method": "GET",
    "url": {
        "raw": "https://localhost:5001/Student/id=1"
    }
}
```

Postar um estudante:
```
"name": "Post",
"request": {
    "method": "POST",
    "body": {
        "mode": "raw",
        "raw": "{\r\n    \"name\": \"Eduarda\",\r\n    \"birthdate\": \"2003-09-19T00:00:00\"\r\n}"
    },
    "url": {
        "raw": "https://localhost:5001/Student/"
    }
}
```

Editar um estudante:
```
"name": "Put",
"request": {
    "method": "PUT",
    "body": {
        "mode": "raw",
        "raw": "{\r\n    \"id\": 6,\r\n    \"name\": \"Eduardo\",\r\n    \"birthdate\": \"2003-09-19T00:00:00\"\r\n}"
        }
    },
    "url": {
        "raw": "https://localhost:5001/Student/id=6"
    }
```

Remover um estudante:
```
"name": "Delete",
"request": {
    "method": "DELETE",
    },
    "url": {
        "raw": "https://localhost:5001/Student/id=6"
    }
```
### Template
```
"name": "Get",
"request": {
    "method": "GET"
    },
    "url": {
        "raw": "https://localhost:5001/Template"
    }
```
```
"name": "GetById",
"request": {
    "method": "GET"
    },
    "url": {
        "raw": "https://localhost:5001/Template/id=1"
    }
```
```
"name": "Post",
"request": {
    "method": "POST",
    "body": {
        "mode": "raw",
        "raw": "{\r\n    \"testQuestionId\": 1,\r\n    \"optionId\": 1\r\n}"
        }
    },
    "url": {
        "raw": "https://localhost:5001/Template"
    }
```
```
"name": "Put",
"request": {
    "method": "PUT",
    "body": {
        "mode": "raw",
        "raw": "{\r\n    \"id\": 3,\r\n    \"testQuestionId\": 5,\r\n    \"optionId\": 1\r\n}"
        }
    },
    "url": {
        "raw": "https://localhost:5001/Template/id=3"
    }
```
```
"name": "Delete",
"request": {
    "method": "DELETE"
    },
    "url": {
        "raw": "https://localhost:5001/Template/id=2"
    }
```

