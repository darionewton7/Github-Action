# 📦 Github-Action

Este repositório contém um pequeno projeto em Go com uma configuração de GitHub Actions para automação de testes e execução do código. O objetivo é demonstrar como configurar um workflow CI básico utilizando **GitHub Actions**.

## 🚀 Funcionalidade

O projeto implementa uma simples função de soma, com um teste automatizado para validar sua lógica.

### 📁 Estrutura dos Arquivos

```
.
├── .github/workflows/ci.yaml   # Workflow de CI com GitHub Actions
├── go.mod                      # Arquivo de dependências do Go
├── math.go                     # Função principal de soma
└── math_test.go                # Teste unitário para a função de soma
```

## 🧪 Testes

O arquivo `math_test.go` contém testes escritos com o pacote `testing` do Go para validar a função `soma`.

```go
func TestSoma(t *testing.T) {
    total := soma(15, 15)
    if total != 30 {
        t.Errorf("Resultado da soma é inválido: Resultado %d. Esperado: %d", total, 30)
    }
}
```

## ⚙️ GitHub Actions

O workflow de CI está definido no arquivo `.github/workflows/ci.yaml` e realiza as seguintes etapas:

- Faz o checkout do repositório
- Instala a versão 1.15 do Go
- Executa os testes com `go test`
- Executa a aplicação com `go run math.go`

Este workflow é acionado automaticamente em **pull requests** para a branch `develop`.

```yaml
on:
  pull_request:
    branches:
      - develop
```

## 📦 Requisitos

- Go 1.15 ou superior
- GitHub com Actions habilitadas

## 📌 Como usar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/Github-Action.git
   cd Github-Action
   ```

2. Execute o teste localmente:
   ```bash
   go test
   ```

3. Rode a aplicação:
   ```bash
   go run math.go
   ```

## 👨‍💻 Autor

Desenvolvido por [dariosilva77](https://github.com/darionewton7)
