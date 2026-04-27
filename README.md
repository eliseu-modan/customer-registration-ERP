# Customer Registration ERP

Interface web em React para validar os fluxos principais de um ERP conectado a uma API backend. O projeto funciona como um painel de testes para autenticacao, clientes, pedidos, dashboard administrativo e integracao com ViaCEP.

## Visao geral

Este repositorio contem o frontend da aplicacao, construido com React e Vite. A API backend e consumida por HTTP via a variavel de ambiente `VITE_API_URL`.

Fluxos disponiveis:

- Login com JWT
- Dashboard para perfil `Admin`
- Cadastro e edicao de clientes
- Busca automatica de endereco por CEP
- Criacao de pedidos com calculo visual do total
- Atualizacao de status dos pedidos
- Consulta manual da integracao ViaCEP

## Stack

- React 19
- Vite 7
- JavaScript
- CSS

## Estrutura do projeto

```text
Customer-registration-ERP/
|- frontend/
|  |- src/
|  |- .env
|  |- package.json
|  `- vite.config.js
`- README.md
```

## Requisitos

- Node.js 20 ou superior
- npm
- API backend disponivel localmente ou em ambiente publicado

## Como rodar localmente

1. Entre na pasta do frontend:

```bash
cd frontend
```

2. Instale as dependencias:

```bash
npm install
```

3. Crie o arquivo de ambiente com base no exemplo:

```bash
cp .env.example .env
```

No Windows PowerShell, voce pode usar:

```powershell
Copy-Item .env.example .env
```

4. Ajuste a URL da API no arquivo `.env`:

```env
VITE_API_URL=http://localhost:5111
```

5. Inicie o servidor de desenvolvimento:

```bash
npm run dev
```

6. Abra a aplicacao no navegador:

```text
http://localhost:5173
```

## Scripts disponiveis

Dentro de `frontend/`:

- `npm run dev`: inicia o ambiente de desenvolvimento com Vite
- `npm run build`: gera a versao de producao
- `npm run preview`: publica localmente o build gerado para validacao

## Credenciais de teste

- `admin / admin123`
- `funcionario / func123`

## Integracao com a API

O frontend monta as requisicoes a partir da variavel `VITE_API_URL`, por exemplo:

```text
${VITE_API_URL}/api/auth/login
```

Se a API estiver publicada no Railway, o valor pode ser algo como:

```env
VITE_API_URL=https://customer-registration-erp-api-production.up.railway.app
```

## Problemas comuns

### `Failed to fetch`

Esse erro normalmente esta relacionado a um destes cenarios:

- API offline ou com falha no deploy
- CORS bloqueando a origem do frontend
- URL da API ausente ou incorreta no `.env`
- erro interno no backend retornando `500`

Checklist rapido:

- confirme se `VITE_API_URL` esta correta
- valide se a API responde fora do navegador
- verifique se o backend libera a origem do frontend no CORS
- confira os logs do Railway ao testar o login

## Observacoes

- Este repositorio contem apenas o frontend.
- O backend precisa estar disponivel para que login, dashboard, clientes, pedidos e ViaCEP funcionem corretamente.
