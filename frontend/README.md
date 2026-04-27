# Frontend

Aplicacao React usada para validar os fluxos da API do ERP.

## Requisitos

- Node.js 20 ou superior
- npm
- API backend disponivel

## Configuracao

Crie um arquivo `.env` com a URL base da API:

```env
VITE_API_URL=http://localhost:5111
```

Voce tambem pode copiar o arquivo de exemplo:

```powershell
Copy-Item .env.example .env
```

## Execucao

```bash
npm install
npm run dev
```

## Scripts

- `npm run dev`
- `npm run build`
- `npm run preview`

## Credenciais seed

- `admin / admin123`
- `funcionario / func123`

## Fluxos disponiveis

- Login JWT
- Dashboard para `Admin`
- Cadastro e edicao de clientes
- Busca automatica de endereco por CEP
- Criacao de pedidos com calculo visual do total
- Atualizacao de status dos pedidos
- Consulta manual da integracao ViaCEP

## Mais detalhes

Consulte o README da raiz do projeto para instrucoes completas.
