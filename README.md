# Miniprojeto 1 - Análise de Vendas

Este projeto automatiza a geração de dados sintéticos de vendas para realizar análises estatísticas e visualizações.

## Tecnologias Utilizadas
- Python 3.11
- Pandas e NumPy (Manipulação de dados)
- Matplotlib e Seaborn (Visualização)

## Como executar
1. Instale as dependências: `pip install -r requirements.txt`
2. Execute o script: `python projeto1.py`

## 🧠 Lógica de Geração de Dados

Para tornar o dataset mais realista e permitir análises de promoções, o script utiliza lógica condicional e geração estatística:

### 1. Simulação de Promoção (Descontos)
Implementamos uma regra de negócio onde produtos específicos de entrada/periféricos possuem preços variáveis:
- **Produtos:** `Mouse Vertical` e `Teclado Mecânico`.
- **Lógica:** Se o produto sorteado for um destes dois, o sistema aplica um multiplicador aleatório entre `0.9` e `1.0` (usando `np.random.uniform`).
- **Resultado:** Isso simula descontos de até 10%, permitindo analisar no futuro se baixos preços aumentam o volume de vendas desses itens.

### 2. Progressão Temporal
As datas dos pedidos não são puramente aleatórias:
- Utilizamos `timedelta(days = int(i/5))` para garantir que a cada 5 registros, o calendário avance um dia.
- Isso cria uma distribuição uniforme de vendas ao longo do tempo, evitando "buracos" cronológicos nos gráficos de linha.

### 3. Integridade de Dados
- **IDs Sequenciais:** Cada pedido recebe um ID único partindo de 1000.
- **Arredondamento:** Preços são tratados com `round(valor, 2)` para evitar erros de precisão decimal comuns em cálculos financeiros com Python.