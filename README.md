# CashD
Expensive tracker feito em rust, insipirado por ezbookkeeping feito por "mayswind".

Em desenvolvimento...

Mas ele será feito para que você rode um servidor em uma maquina separada e então acesse os apps!



# Funcionalidades:

## Técnico
- [ ] Servidor para self-host funcional
- [ ] Interface gráfica
- [ ] Sincronização de dados bidirecional entre dispositivos (Cache offline com fila de sincronização)
- [ ] API com autenticação JWT
- [ ] Backup automático do banco
- [ ] Filtros para os gráficos

## Usuário
- [ ] Sistema de usuários 
- [ ] Sistema de contas (cartões, boletos, corrente, poupança, etc.)
- [ ] Gráfico de gastos e tendências
- [ ] Registro de gastos com categorias e subcategorias
- [ ] Planejamento financeiro (orçamento por categoria)
- [ ] Transações recorrentes
- [ ] Parcelamento de cartão (lança cobranças futuras automaticamente)
- [ ] Anexar imagem ao registrar uma transação
- [ ] Tags livres nos lançamentos 
- [ ] Câmbio automático de moedas
- [ ] Exportação CSV e outros formatos

# Tech Stack

## Servidor
> Rust · Docker

| Biblioteca | Função |
|---|---|
| `axum` | Framework HTTP |
| `tokio` | Runtime async |
| `tower-http` | Middleware: CORS, compressão, logging |
| `sqlx` | Queries async no SQLite, type-safe em compile time |
| `serde` + `serde_json` | Serialização/deserialização JSON |
| `jsonwebtoken` | Geração e validação de JWT |
| `chrono` | Datas, timezones, vencimentos |
| `uuid` | Geração de IDs únicos (uuid v4)|
| `bcrypt` | Hash de senha |
| `tokio-cron-scheduler` | Jobs periódicos (recorrentes, backup) |
| `csv` | Exportação CSV |

## App Desktop / Android:

> Flutter · Dart · Riverpod · drift

| Biblioteca | Função |
|---|---|
| `riverpod` | Gerenciamento de estado |
| `drift` | ORM sobre SQLite, queries type-safe em Dart |
| `sqflite` | SQLite local para cache offline |
| `dio` | HTTP client com interceptors e retry automático |
| `fl_chart` | Gráficos (pizza, barra, linha) |
| `connectivity_plus` | Detecta rede, aciona fila offline |
| `intl` | Formatação de moeda e datas |
| `image_picker` | Câmera/galeria para anexar imagens |
| `flutter_secure_storage` | Armazenamento seguro do JWT |
| `go_router` | Navegação entre telas |
| `freezed` | Models imutáveis, evita bugs de estado |
| `json_serializable` | Geração de código para parsing JSON |

