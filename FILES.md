# Карта файлов

| Раздел | Файлы | Назначение |
| --- | --- | --- |
| Домен | `internal/model/pet*.go`, `inventory_item.go` | Питомец, ежедневное состояние, инвентарь, события и сводка. |
| Бизнес-правила | `internal/usecase/pet_rules.go` | Расчёт состояния, XP, уровня и доменных событий. |
| Use cases | `pet_lifecycle.go`, `pet_care.go`, `pet_daily_summary.go`, `pet_contracts.go`, `pet_errors.go` | Создание профиля, использование предмета, сводка, границы зависимостей и ошибки. |
| PostgreSQL | `internal/repository/postgres/pet*.go`, `inventory_item.go` | Получение и обновление данных, блокировки и использование общей транзакции. |
| HTTP API | `internal/handler/pet*.go` | DTO, handlers, валидация и HTTP-ответы Pet API. |
| Схема данных | `migrations/000003_create_pet_core.*.sql` | Таблицы, ограничения, связи и обратимая миграция. |
| Проверки | `*_test.go`, `scripts/smoke-pet.ps1`, `.golangci.yml` | Unit-, handler-, repository-, migration- и smoke-тесты, статический анализ. |

## Что не дублируется

В исходном командном репозитории некоторые общие файлы были точечно изменены для подключения этой части: общий router, application wiring и OpenAPI-спецификация. Они не копируются сюда целиком, потому что содержат базовый код команды. В этом репозитории собраны файлы, добавленные в рамках моего pet-core-вклада.
