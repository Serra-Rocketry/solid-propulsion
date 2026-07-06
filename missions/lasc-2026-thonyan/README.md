# Missão Thonyan — LASC 2026

## Informações Gerais

| Campo | Valor |
|---|---|
| **Missão** | Thonyan |
| **Competição** | 7th Latin American Space Challenge (LASC 2026) |
| **Foguete** | 500m |
| **Motor** | SR500M |
| **Data do teste** | 11/06/2026 |
| **Local** | Laboratório de Adesão e Aderência |
| **Responsáveis** | Caio, Joana e Steffany |

## Motor SR500M

| Especificação | Valor |
|---|---|
| Empuxo | [aguardando issue #23] |
| Propulsante | [a definir] |
| Status | Aguardando CAD |

## Foguete 500m

| Especificação | Valor |
|---|---|
| Altitude alvo | 500m |
| Material do tubo | Alumínio 6063-T5 |
| Material da tampa | Alumínio 6061 |
| Material do nozzle | Aço Inox AISI 304 |

## Teste Hidrostático

### Parâmetros

| Parâmetro | Valor |
|---|---|
| Pressão alvo | 62 bar |
| Pressão máxima atingida | 64 bar |
| Tempo de prova | 10 min |
| Fluido utilizado | Água |

### Resultados

| Critério | Resultado |
|---|---|
| **Resultado geral** | Aprovado |
| Vazamentos observados | Não |
| Deformações visíveis | Não |
| Observações de segurança | Nenhuma |

### Evidências

![Teste hidrostático 1](./tests/hydrostatic/teste_hidrostatico_1.jpg)
![Teste hidrostático 2](./tests/hydrostatic/teste_hidrostatico_2.jpg)
![Teste hidrostático 3](./tests/hydrostatic/teste_hidrostatico_3.jpg)
![Teste hidrostático 4](./tests/hydrostatic/teste_hidrostatico_4.jpg)
![Teste hidrostático 5](./tests/hydrostatic/teste_hidrostatico_5.jpg)
![Teste hidrostático 6](./tests/hydrostatic/teste_hidrostatico_6.jpg)

### Gráfico

![Pressão × Tempo — Teste Hidrostático](./tests/hydrostatic/pressao_tempo.png)

### Dados

- [Planilha de dados — pressão × tempo (.xls)](./tests/hydrostatic/TESTE_HIDROSTATICO_500m_62bar.xls)
- [Dados exportados — pressão × tempo (.csv)](./tests/hydrostatic/teste_hidrostatico_dados.csv)

### Vídeo

- [Vídeo do teste (Google Drive)](https://drive.google.com/file/d/1uUkc7NuGaZSWjlcIh_S-NmDpeM9jrFmb/view?usp=sharing)

## Estrutura

```
lasc-2026-thonyan/
├── motor/              # SR500M (aguardando CAD, issue #23)
│   ├── cad/
│   ├── drawings/
│   ├── images/
│   ├── openmotor/
│   ├── parasolid/
│   └── stl/
├── rocket/             # Foguete 500m
│   ├── assembly/
│   ├── cad/
│   ├── openmotor/
│   ├── simulation/
│   └── documentation.md
├── tests/
│   └── hydrostatic/    # Teste hidrostático (11/06/2026)
└── README.md
```

## Issues Relacionadas

- [Issue #8: Dados do teste hidrostático - Thonyan](https://github.com/Serra-Rocketry/motor/issues/8)
- [Issue #23: SR500M - Documentar motor](https://github.com/Serra-Rocketry/motor/issues/23)
- [Issue #25: Simulações 500m - Verificar origem](https://github.com/Serra-Rocketry/motor/issues/25)
- [Issue #26: Corrigir formatação de rocket/documentation.md](https://github.com/Serra-Rocketry/motor/issues/26)

## Referências

- [7th Latin American Space Challenge (LASC 2026)](https://www.lasc.space)
- [Relatório técnico de propulsão](./rocket/documentation.md)
