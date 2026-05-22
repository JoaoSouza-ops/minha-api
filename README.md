# API Almoxarifado — Gestão de Patrimônios

API REST desenvolvida para o módulo de gestão de patrimônios do SGM Almoxarifado, sistema de controle de ativos da Prefeitura de Embu das Artes. Permite o cadastro, consulta, atualização e baixa de bens patrimoniais, seguindo o padrão API-First com contrato OpenAPI 3.0.

📄 **Documentação interativa:** [https://joaosouza-ops.github.io/minha-api/](https://<seu-usuario>.github.io/<seu-repositorio>)

---

## Endpoints

| Método   | Rota                    | Descrição                                     |
| -------- | ----------------------- | --------------------------------------------- |
| `GET`    | `/patrimonios`          | Lista todos os patrimônios cadastrados        |
| `POST`   | `/patrimonios`          | Cadastra um novo patrimônio                   |
| `GET`    | `/patrimonios/{codigo}` | Busca um patrimônio pelo código identificador |
| `PUT`    | `/patrimonios/{codigo}` | Atualiza os dados de um patrimônio existente  |
| `DELETE` | `/patrimonios/{codigo}` | Realiza a baixa (remoção) de um patrimônio    |

---

## Formato do Código

O campo `codigo` segue o padrão de máscara:

```
NNNNNN          → ex: 123456
AAAA-NNNNNN     → ex: MESA-123456
```

---

## Estados de Conservação

| Valor        | Descrição                         |
| ------------ | --------------------------------- |
| `BOM`        | Bem em bom estado de uso          |
| `REGULAR`    | Bem com desgaste moderado         |
| `INSERVIVEL` | Bem inutilizável ou para descarte |

---

## Pipeline CI/CD

O repositório conta com um pipeline automatizado via GitHub Actions que:

1. **Valida** o contrato OpenAPI com Spectral a cada push na branch `develop`
2. **Publica** a documentação no GitHub Pages automaticamente após validação

---

## Tecnologias

- **Especificação:** OpenAPI 3.0.3
- **Validação:** Spectral CLI
- **Documentação:** Redoc
- **CI/CD:** GitHub Actions
