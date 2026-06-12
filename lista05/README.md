# Lista 05 - Market Basket Analysis

Atividade de analise de cestas de supermercado com o algoritmo Apriori e
regras de associacao.

## Arquivos

- `lista05.ipynb`: notebook principal com a analise completa.
- `basket_supermercado_1000.csv`: dataset com 1.000 transacoes.
- `RELATORIO.md`: interpretacao gerencial e respostas das questoes propostas.
- `graficos/`: visualizacoes geradas pelo notebook.
- `resultados/`: conjuntos frequentes, regras e resumos exportados.

## Metodologia

O notebook utiliza:

- suporte minimo de 5%;
- confianca minima de 50% para gerar regras;
- itemsets com no maximo quatro produtos;
- lift minimo de 1,20 para destacar regras gerencialmente relevantes;
- antecedente e consequente unitarios na selecao principal, facilitando a
  interpretacao.

O suporte minimo de 5% exige que uma combinacao apareca em pelo menos 50 das
1.000 transacoes. Isso reduz o risco de destacar coincidencias baseadas em
poucos registros.

## Execucao

O notebook pode ser aberto no Google Colab ou no Jupyter.

No Colab:

1. Abra o arquivo `lista05.ipynb`.
2. Envie `basket_supermercado_1000.csv` para a mesma pasta.
3. Instale as dependencias, caso necessario.
4. Execute todas as celulas.

Para executar localmente:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook lista05.ipynb
```

## Principais resultados

As associacoes mais importantes foram:

- pao e leite: suporte de 62,4% e lift de 1,56;
- arroz e feijao: suporte de 50,3% e lift de 1,89;
- cafe e acucar: suporte de 37,3% e lift de 2,43;
- refrigerante e cerveja: suporte de 19,1% e lift de 2,69;
- doces para cerveja: confianca de 87,8% e lift de 2,60;
- carne ou frango para arroz e feijao: confiancas acima de 93%.

Os resultados devem apoiar testes de layout e promocoes, nao substituir
avaliacoes de margem, estoque, sazonalidade e perfil de cliente.
