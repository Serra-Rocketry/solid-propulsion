# Missão SR Couto — LASC 2025

## Informações Gerais

| Campo | Valor |
|---|---|
| **Missão** | SR Couto |
| **Competição** | 6th Latin American Space Challenge (LASC 2025) |
| **Foguete** | 1km |
| **Motor** | SR21000 |
| **Data** | 05-08/11/2025 |
| **Local** | Iacanga, SP |
| **Resultado** | 11º lugar, Major Damage |

## Motor SR21000

| Especificação | Valor |
|---|---|
| Empuxo | 21000 Ns |
| Propulsante | KNSU |
| Status | Concluído |

## Foguete 1km

| Especificação | Valor |
|---|---|
| Altitude alvo | 1000m |
| Material do tubo | Alumínio 6063-T5 |
| Material da tampa | Alumínio 6061 |
| Material do nozzle | Aço Inox AISI 304 |

## Teste Hidrostático

- Pressão alvo: 88 bar
- [Dados do teste](./tests/hydrostatic/TESTE_HIDROSTATICO_SR21000_88bar.xlsx)

## Estrutura

```
lasc-2025-sr-couto/
├── motor/              # SR21000
│   ├── cad/
│   ├── drawings/
│   ├── images/
│   ├── openmotor/
│   ├── parasolid/
│   ├── stl/
│   └── SR21000.md
├── rocket/             # Foguete 1km
│   ├── assembly/
│   ├── cad/
│   ├── mold/
│   ├── openmotor/
│   ├── parasolid/
│   ├── step/
│   └── documentation.md
├── tests/
│   ├── hydrostatic/
│   └── static/
└── README.md
```

## Referências

- [Notícia: Universitários de Friburgo vão lançar foguete](https://novafriburgoemfoco.com.br/universitarios-de-friburgo-vao-lancar-foguete-no-interior-paulista/)
- [Vídeo do motor](https://www.youtube.com/watch?v=OPyVqQy9fkQ)
- [LASC 2025](https://www.lasc.space/past-events/6th-lasc)
