erDiagram
    CATEGORIAS ||--o{ VEICULOS : "tem"
    CLIENTES ||--o{ LOCACOES : "realiza"
    VEICULOS ||--o{ LOCACOES : "possui"

    CATEGORIAS {
        int id_categoria PK
        varchar nome
        decimal valor_diaria
    }
    CLIENTES {
        int id_cliente PK
        varchar nome
        varchar email
        datetime data_cadastro
    }
    VEICULOS {
        int id_veiculo PK
        varchar modelo
        varchar marca
        varchar placa
        varchar status_atual
        int id_categoria FK
    }
    LOCACOES {
        int id_locacao PK
        int id_cliente FK
        int id_veiculo FK
        datetime data_retirada
        datetime data_devolucao_prevista
        datetime data_devolucao_real
        varchar status_locacao
        decimal valor_total
    }
