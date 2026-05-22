# Estruturas

Materiais de apoio para **dimensionamento de elementos de concreto armado** e análise
estrutural. Esta disciplina reúne notebooks de cálculo, conjuntos de dados validados e
referências em PDF usados como base teórica.

> Conteúdo **didático e preliminar**. Os resultados servem para estudo e pré-dimensionamento
> e devem sempre ser conferidos por um engenheiro responsável.

## Conteúdo atual

### Ábacos de Venturini — Flexão Composta Reta

Roteiro completo para o **dimensionamento preliminar de seções retangulares de concreto
armado submetidas à flexão composta reta** (esforço normal + momento em uma direção),
usando a lógica dos ábacos de Venturini com armadura simétrica nas duas faces.

O notebook automatiza a sequência: entrada de dados → cálculo dos parâmetros adimensionais
`ν` e `μ` → leitura de um dataset validado dos ábacos → obtenção de `ω` por interpolação em
duas etapas (interpolação 2D em `(ν, μ)` dentro de cada ábaco e interpolação linear entre
ábacos vizinhos em função de `d'/h`) → cálculo da área de aço `As` → verificações básicas →
sugestão de detalhamento → memorial de cálculo em Markdown.

| Arquivo | Descrição |
|---|---|
| `abacos_venturini_flexao_composta_reta_interpolacao_csv.ipynb` | Notebook de cálculo comentado |
| `dataset_venturini_final_sem_extremos_duplicados.csv` | Pontos digitalizados e validados dos ábacos A-1 a A-5 (`d'/h` de 0,05 a 0,25), 3.655 pontos |
| `abaco_venturini_flexao_composta_reta.pdf` | Material de referência dos ábacos |

**Abrir no Colab:**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/infradataai/ENGENEERING/blob/main/Estruturas/abacos_venturini_flexao_composta_reta_interpolacao_csv.ipynb)

No Colab, o notebook usa o modo `csv_interpolado` e procura o dataset em `/content/`.
Para carregá-lo automaticamente, rode esta célula antes do cálculo:

```python
!wget -q https://raw.githubusercontent.com/infradataai/ENGENEERING/main/Estruturas/dataset_venturini_final_sem_extremos_duplicados.csv -O /content/dataset_venturini_final_sem_extremos_duplicados.csv
```

Alternativamente, faça upload manual do `.csv` pelo painel de arquivos do Colab, ou use o
modo `manual` informando o `ω` lido diretamente no ábaco.

**Executar localmente:** mantenha o notebook e o `.csv` na mesma pasta e instale as
dependências:

```bash
pip install numpy pandas scipy
```

### Convenções adotadas no notebook

- `Nd` positivo indica compressão;
- `Md` informado em módulo, em `kNm` (convertido internamente para `kN·cm`);
- dimensões em `cm` e tensões em `kN/cm²`;
- seção retangular com armadura simétrica nas duas faces, aço CA-50;
- parâmetros adimensionais: `ν = Nd / (Ac·fcd)` e `μ = Md / (Ac·h·fcd)`;
- área de aço: `As = ω·Ac·fcd / fyd`.
