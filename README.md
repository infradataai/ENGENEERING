# ENGENEERING

Coleção aberta de **notebooks e materiais de apoio para estudantes de Engenharia Civil**.
O objetivo é reunir, por disciplina, ferramentas de cálculo comentadas, conjuntos de dados
e roteiros que ajudem no aprendizado e na prática do dimensionamento.

> Material **didático e preliminar**. Todo cálculo gerado aqui deve ser conferido por um
> engenheiro responsável antes de qualquer uso em projeto real.

## Estrutura do repositório

```
ENGENEERING/
├── Estruturas/          # Concreto armado, dimensionamento de seções, ábacos
├── Pavimentacao/        # Dimensionamento e materiais de pavimentos
├── ProjetoGeometrico/   # Geometria de vias: curvas, perfis, superelevação
└── Geotecnia/           # Solos, fundações, empuxos e estabilidade
```

Cada subpasta tem um `README.md` próprio descrevendo o conteúdo da disciplina e os
arquivos disponíveis.

## Como executar os notebooks

Os notebooks (`.ipynb`) podem ser abertos de duas formas:

**No navegador, sem instalar nada (Google Colab):** clique no badge "Open in Colab" no
topo do notebook ou no README da disciplina. Se o notebook depender de um arquivo de dados
(`.csv`), siga as instruções da própria disciplina para carregá-lo no ambiente.

**Localmente:** clone o repositório e abra com Jupyter Notebook ou JupyterLab. Mantenha o
notebook e seus arquivos de dados na mesma pasta.

```bash
git clone https://github.com/infradataai/ENGENEERING.git
cd ENGENEERING
```

Dependências comuns aos notebooks de cálculo: `numpy`, `pandas` e `scipy`.

```bash
pip install numpy pandas scipy
```

## Contribuindo

Sugestões, correções e novos notebooks são bem-vindos. Abra uma *issue* descrevendo a
ideia ou envie um *pull request* organizando o material na disciplina correspondente.

---

> Nota: os badges e links deste repositório assumem o branch padrão `main`.
> Se o seu branch padrão for `master`, troque `main` por `master` nas URLs.
