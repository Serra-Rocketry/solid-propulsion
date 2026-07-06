# Missão Dédalo — LASC 2026

## Informações Gerais

| Campo | Valor |
|---|---|
| **Missão** | Dédalo |
| **Competição** | 7th Latin American Space Challenge (LASC 2026) |
| **Foguete** | 1km |
| **Motor** | SR1000M |
| **Data do teste** | 26/06/2026 |
| **Local** | Laboratório de Adesão e Aderência |
| **Responsáveis** | Caio, Ítalo e Steffany |

## Teste Hidrostático

### Parâmetros

| Parâmetro | Valor |
|---|---|
| Pressão alvo | 90 bar |
| Pressão máxima atingida | 91 bar |
| Tempo de prova | 6 min |
| Fluido utilizado | Água |

### Resultados

| Critério | Resultado |
|---|---|
| **Resultado geral** | Aprovado |
| Vazamentos observados | Não |
| Deformações visíveis | Não |
| Observações de segurança | Nenhuma |

## Estrutura

```
lasc-2026-dedalo/
├── motor/              # SR1000M (aguardando CAD, issue #24)
│   ├── cad/
│   ├── drawings/
│   ├── images/
│   ├── openmotor/
│   ├── parasolid/
│   └── stl/
├── rocket/             # Foguete 1km
│   ├── assembly/
│   ├── cad/
│   ├── mold/
│   ├── openmotor/
│   ├── parasolid/
│   └── step/
├── tests/
└── README.md
```

## Issues Relacionadas

- [Issue #7: Dados do teste hidrostático - Dédalo](https://github.com/Serra-Rocketry/motor/issues/7)
- [Issue #24: SR1000M - Documentar motor](https://github.com/Serra-Rocketry/motor/issues/24)
