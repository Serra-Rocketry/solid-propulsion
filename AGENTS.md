# AGENTS.md — Motor

## Visão do Projeto

Repositório de documentação técnica da equipe Serra Rocketry para motores de foguetes: desenhos CAD, especificações, dados de testes estáticos e simulações OpenMotor. Contém apenas documentação — nenhum código executável.

## Fronteira de Responsabilidade

Este repositório é a **fonte de verdade para geometria e dados brutos de motores**.

**Este repo contém:**
- CAD (.SLDPRT, .SLDASM, .SLDDRW, .STL, .STEP)
- Dados brutos de teste estático (.txt do SD card)
- Simulações OpenMotor (.ric)
- Gráficos simples de validação (thrust/pressão x tempo)
- Imagens e GIFs de testes
- Documentação técnica dos motores (.md)

**Este repo NÃO contém (vai para analysis/flight-computer/etc):**
- Análises processadas de voo
- Biblioteca de motores (app web)
- Simulações de trajetória
- Computador de bordo
- Análises estatísticas avançadas

**Se o usuário pedir para adicionar dados de análise sofisticada**, guiar para o repositório [analysis](https://github.com/Serra-Rocketry/analysis).

**Referências:**
- [analysis](https://github.com/Serra-Rocketry/analysis) — app Flask de análise e biblioteca de motores
- [flight-computer](https://github.com/Serra-Rocketry/flight-computer) — computador de bordo
- [thrust-stand](https://github.com/Serra-Rocketry/thrust-stand) — sistema de aquisição de dados

## Estrutura do Repositório

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

## Convenções de Nomes de Arquivos

- **Sem acentos:** `ã→a`, `ç→c`, `é→e`, `ó→o`, `í→i`, `ú→u`
- **Sem espaços:** usar `_` como separador
- **Sem parênteses:** remover
- **Manter maiúsculas/minúsculas** originais
- Exemplo: `Restrição_motor.SLDPRT` → `Restricao_motor.SLDPRT`

## Convenção de Nomes de Motores

Padrão: **`SR{versão}-{altura em metros}`**

| Motor | Nome | Missão | Descrição |
|---|---|---|---|
| SR1-1000 | SR 1ª versão, 1000m | SR Couto (LASC 2025) | 1º motor de 1km |
| SR2-1000 | SR 2ª versão, 1000m | Dédalo (LASC 2026) | 2º motor de 1km |
| SR2-500 | SR 2ª versão, 500m | Thonyan (LASC 2026) | 2º motor de 500m |
| SR1-500 | SR 1ª versão, 500m | Archive | Motor legado |

**Regras:**
- `SR` = prefixo Serra Rocketry (maiúsculo)
- `{versão}` = número inteiro sequencial (1, 2, 3...)
- `{altura}` = altitude alvo em metros
- Separador: hífen (`-`)
- Motores legados sem altitude clara (300M, V1, Cardboard) mantêm nome original

## Organização por Motor

Cada motor tem subpastas conforme aplicável:

| Subpasta | Conteúdo |
|---|---|
| `cad/` | `.SLDPRT` (peças), `.SLDASM` (montagens) |
| `drawings/` | `.SLDDRW` (desenhos técnicos), `.pdf` |
| `openmotor/` | `.ric` (arquivos de simulação OpenMotor) |
| `stl/` | `.STL` para impressão 3D |
| `parasolid/` | `.x_t` (formato Parasolid para interop) |
| `gcode/` | `.gcode` para impressão 3D |
| `images/` | Fotos, renderings e gráficos do motor |

## Convenções de Imagens

- Imagens ficam em `missions/{missão}/{motor ou rocket}/images/` ou `missions/{missão}/tests/{tipo}/`
- Renderings SolidWorks: nome descritivo, ex: `render_sr1-1000.jpg`
- Capturas de tela: em subpasta `capturas/`
- **Tamanho máximo: 500 KB por imagem** (regra das Boas Práticas)
- Comprimir antes de commitar: `convert input.jpg -resize 1200x -quality 80 -strip output.jpg`
- Embed no markdown: `![Descrição](./images/render.jpg)`
- Layout em docs: HTML tables para imagens lado a lado (3 por linha, 300px width), imagens isoladas em 300px

## Dados de Teste Estático

- Dados brutos do SD card: `archive/static-tests/{motor}/data.txt`
- Gráficos: `archive/static-tests/{motor}/empuxo_pressao.jpg`
- Projetos SciLab: `archive/static-tests/scilab/`
- Os dados do thrust-stand (sistema de aquisição) ficam no repo [Serra-Rocketry/thrust-stand](https://github.com/Serra-Rocketry/thrust-stand)

## O que NÃO versionar

- Pasta `drive/` (backup local do Google Drive)
- Vídeos grandes (`.MOV`, `.MP4`, `.avi`) — usar Git LFS ou hosting externo
- Binários de terceiros (`.exe`)
- Arquivos regeneráveis do SolidWorks (`.CWR`, `.dmp`, `.err`, `.LOG`, `.MFC`)
- Ver `.gitignore` completo

## Workflow

1. **Branching:** feature branches a partir de main (`feature/nome`)
2. **Commits:** mensagens em português, descritivas
3. **Arquivos CAD:** SolidWorks 2024+ (compatível com versões anteriores)
4. **Simulações OpenMotor:** arquivos `.ric` versionados diretamente
5. **Documentação:** Markdown em português

## Referências

- [Boas Práticas — Serra Rocketry](https://github.com/Serra-Rocketry/best-practices)
- [Thrust Stand — Sistema de Aquisição](https://github.com/Serra-Rocketry/thrust-stand)
- [OpenMotor — Software de Simulação](https://github.com/reilleya/openMotor)
- [MIGRATION.md](./MIGRATION.md) — histórico de migração do Drive
