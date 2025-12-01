# Data Mart IDEB – Região Nordeste

Este projeto apresenta um Data Mart desenvolvido para analisar os indicadores do IDEB na Região Nordeste do Brasil. A modelagem segue a abordagem **Bottom-up** e utiliza o padrão **Star Schema**, permitindo organização clara, consultas rápidas e fácil expansão do ambiente analítico.

## 🛠️ Ferramentas Utilizadas

**PostgreSQL** | **Pentaho** | **MetaBase**

## Modelagem Dimensional

### Dimensão: Etapa de Ensino (`dim_etapa_ensino`)
**Função:** Armazena as diferentes etapas da educação básica, bem como seus anos escolares.

**Colunas principais:**
- `etapa` – Etapa da educação (ex.: Anos Iniciais)
- `anos_escolares` – Faixa de séries correspondentes

### Dimensão: Região (`dim_regiao`)
**Função:** Registra as regiões consideradas nas análises.

**Colunas principais:**
- `regiao` – Nome da região (ex.: Nordeste)

### Dimensão: Tempo (`dim_tempo`)
**Função:** Representa a dimensão temporal do modelo.

**Colunas principais:**
- `ano` – Ano da avaliação do IDEB

### Dimensão: Rede de Ensino (`dim_rede_ensino`)
**Função:** Contém as redes educacionais presentes no dataset.

**Colunas principais:**
- `rede_ensino` – Tipo da rede (pública, privada, estadual, municipal)

### Tabela Fato: IDEB (`fato_ideb`)
**Função:** Centraliza os indicadores numéricos e métricas relacionadas ao desempenho educacional.

**Colunas principais:**
- `taxa_aprovacao`
- `nota_saeb_matematica`
- `nota_saeb_lingua_portuguesa`
- `nota_saeb_media_padronizada`
- `ideb`

**Chave primária:**
- `(id_tempo, id_rede_ensino, id_etapa, id_regiao)`
