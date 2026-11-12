# Painel de Cotações — Projeto 4

Projeto Django que consulta a cotação USD/BRL na AwesomeAPI, salva cada consulta no banco SQLite e exibe o histórico usando `fetch()`.

## Requisitos
- Python 3.10 ou superior
- VS Code (recomendado)
- Conexão com a internet para consultar a AwesomeAPI

## Como executar no Windows (PowerShell)

Abra esta pasta no VS Code e, no terminal, execute:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Acesse:
- Painel: http://127.0.0.1:8000/consultar/
- API de histórico: http://127.0.0.1:8000/api/historico/
- Admin: http://127.0.0.1:8000/admin/

Se o PowerShell bloquear a ativação do ambiente virtual, execute:
```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\venv\Scripts\Activate.ps1
```

## Criar usuário administrador
Em outro terminal com o ambiente virtual ativado:
```powershell
python manage.py createsuperuser
```

## Testes automatizados
```powershell
python manage.py test
```

## Variável de ambiente (opcional)
A URL padrão já está configurada. Para testar falha da API no PowerShell:
```powershell
$env:COTACAO_URL="https://economia.awesomeapi.com.br/json/last/XXX-YYY"
python manage.py runserver
```
Para voltar ao padrão, feche o terminal e abra outro.

## Estrutura
- `painel/`: aplicação, model, views, serializer, rotas e testes.
- `painelapi/`: configurações e rotas principais.
- `db.sqlite3`: criado automaticamente após `migrate` (não enviar ao GitHub).

## Publicar no GitHub
Antes de publicar, confira se `venv/`, `db.sqlite3` e `.env` não estão no repositório. Preencha seu nome no campo Autor, se desejar.
