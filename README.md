# Motor — Serra Rocketry

Desenhos CAD, especificações e dados de testes estáticos de motores de foguetes.

## Sobre

Este repositório contém a documentação técnica dos motores desenvolvidos pela equipe Serra Rocketry (IPRJ/UERJ). Aqui ficam os desenhos de peça, montagens, simulações OpenMotor e dados brutos de testes estáticos.

> **Nota:** O sistema de aquisição de dados (firmware, hardware, calibração) fica no repositório [thrust-stand](https://github.com/Serra-Rocketry/thrust-stand). Este repo armazena apenas os dados coletados e a documentação dos motores.

## Fronteira de Responsabilidade

Este repositório (`motor`) contém a **documentação da propulsão** e é a **fonte de verdade para geometria e dados brutos de motores**.

**Este repo contém:**
- Geometria do motor (CAD: .SLDPRT, .SLDASM, .SLDDRW, .STL, .STEP)
- Dados brutos de teste estático (.txt do SD card)
- Simulações OpenMotor (.ric)
- Gráficos simples de validação (thrust/pressão x tempo)
- Imagens e GIFs de testes
- Documentação técnica dos motores (.md)

**Este repo NÃO contém:**
- Análises sofisticadas de voo → [analysis](https://github.com/Serra-Rocketry/analysis)
- Biblioteca de motores (app web) → [analysis](https://github.com/Serra-Rocketry/analysis)
- Computador de bordo → [flight-computer](https://github.com/Serra-Rocketry/flight-computer)
- Simulações de trajetória → [analysis](https://github.com/Serra-Rocketry/analysis)

**Diagrama:**
```
[motor] ──dados brutos──→ [analysis] ──→ app web, biblioteca
   │                           │
   │ Propulsão                 │ Telemetria
   │ - Geometria               │ - Análise de testes
   │ - Dados SD card           │ - Simulações de voo
   │ - CAD                     │ - Visualização
   │ - OpenMotor (.ric)        │ - Biblioteca de motores
```

## Estrutura

```
missions/                          # Missões da LASC
├── lasc-2025-sr-couto/            # Missão SR Couto (LASC 2025)
│   ├── motor/                     # SR1-1000
│   ├── rocket/                    # Foguete 1km
│   ├── tests/                     # Testes (hidrostático, estático)
│   └── README.md
├── lasc-2026-thonyan/             # Missão Thonyan (LASC 2026)
│   ├── motor/                     # SR2-500
│   ├── rocket/                    # Foguete 500m
│   ├── tests/                     # Testes (hidrostático)
│   └── README.md
└── lasc-2026-dedalo/              # Missão Dédalo (LASC 2026)
    ├── motor/                     # SR2-1000
    ├── rocket/                    # Foguete 1km
    ├── tests/                     # Testes
    └── README.md

archive/                           # Arquivos legados
├── motors/                        # Motores antigos (SR1-500, 300M, V1, Cardboard)
├── rockets/                       # Foguetes legados (Commercial)
├── molds/                         # Moldes
├── nozzle-cimento/                # Nozzle de cimento
├── tools/                         # Ferramentas e gabaritos
├── static-tests/                  # Testes estáticos antigos
└── propellants/                   # Propelentes

meetings/                          # Atas de reunião
training/                          # Documentação de treinamento
```

## Competições

| Missão | Competição | Foguete | Motor | Ano | Resultado |
|---|---|---|---|---|---|
| SR Couto | [LASC 2025](https://www.lasc.space/past-events/6th-lasc) | 1km | SR1-1000 | 2025 | 11º lugar, Major Damage |
| Thonyan | [LASC 2026](https://www.lasc.space/2026-lasc/overview) | 500m | SR2-500 | 2026 | Em desenvolvimento |
| Dédalo | [LASC 2026](https://www.lasc.space/2026-lasc/overview) | 1km | SR2-1000 | 2026 | Em desenvolvimento |

## Missões

Cada missão da LASC tem sua própria pasta em `missions/` com:

- **motor/** — CAD, desenhos, simulações OpenMotor, imagens
- **rocket/** — CAD do foguete, montagens, simulações
- **tests/** — Testes hidrostáticos e estáticos
- **README.md** — Documentação da missão

### Missões Ativas

| Missão | Pasta | Status |
|---|---|---|
| [SR Couto (LASC 2025)](./missions/lasc-2025-sr-couto/) | `missions/lasc-2025-sr-couto/` | Concluída |
| [Thonyan (LASC 2026)](./missions/lasc-2026-thonyan/) | `missions/lasc-2026-thonyan/` | Em desenvolvimento |
| [Dédalo (LASC 2026)](./missions/lasc-2026-dedalo/) | `missions/lasc-2026-dedalo/` | Em desenvolvimento |

## Como Usar

### Abrir arquivos CAD

Os arquivos `.SLDPRT` e `.SLDASM` são do SolidWorks. Se não tiver SolidWorks:

- Use o [eDrawings Viewer](https://www.solidworks.com/product/edrawings-viewer) (gratuito)
- Arquivos `.STEP` abrem em qualquer CAD (FreeCAD, Fusion 360, etc.)
- Arquivos `.STL` são para impressão 3D (slicer)

### Simulações OpenMotor

Arquivos `.ric` são do [OpenMotor](https://github.com/reilleya/openMotor), software livre de simulação de motores de foguete. Para abrir:

1. Instale o OpenMotor: `pip install openmotor` ou baixe o executável
2. Abra o arquivo `.ric` correspondente ao motor
3. Execute a simulação

### Dados de Teste

Os arquivos `.txt` em `archive/static-tests/` contêm dados brutos do SD card no formato:

```
HH:MM:SS ; empuxo(kN) ; tempo(ms)
```

## Contribuindo

Este projeto segue as [Boas Práticas da Serra Rocketry](https://github.com/Serra-Rocketry/best-practices). Para contribuir:

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/nome`)
3. Commit suas mudanças
4. Abra um Pull Request

### Regras para Arquivos CAD

- Normalizar nomes: sem acentos, espaços → `_`
- SolidWorks 2024+ (compatível com versões anteriores)
- Incluir desenhos técnicos (`.SLDDRW`) quando disponível
- Exportar `.STEP` para interoperabilidade

## Links

- [Thrust Stand](https://github.com/Serra-Rocketry/thrust-stand) — Sistema de aquisição de dados
- [Ignitor](https://github.com/Serra-Rocketry/ignitor) — Sistema de ignição remota
- [Best Practices](https://github.com/Serra-Rocketry/best-practices) — Boas práticas da equipe
- [MIGRATION.md](./MIGRATION.md) — Histórico de migração do Drive
- [LASC 2025](https://www.lasc.space/past-events/6th-lasc) — 6th Latin American Space Challenge
- [LASC 2026](https://www.lasc.space/2026-lasc/overview) — 7th Latin American Space Challenge

## Issues Abertas

| Issue | Título | Status |
|---|---|---|
| [#8](https://github.com/Serra-Rocketry/motor/issues/8) | [Teste Hidrostático] Dados do teste - Thonyan - 26/06/2026 | Aguardando resposta |
| [#7](https://github.com/Serra-Rocketry/motor/issues/7) | [Teste Hidrostático] Dados do teste - Dédalo - 26/06/2026 | Aguardando resposta |
| [#23](https://github.com/Serra-Rocketry/motor/issues/23) | SR2-500: Documentar motor (CAD, especificações) | Aguardando CAD |
| [#24](https://github.com/Serra-Rocketry/motor/issues/24) | SR2-1000: Documentar motor (CAD, especificações) | Aguardando CAD |
| [#25](https://github.com/Serra-Rocketry/motor/issues/25) | Simulações 500m: Verificar se é da missão Thonyan ou arquivo legado | Aguardando resposta |

---

**Mantido por:** Equipe Serra Rocketry — IPRJ/UERJ
