# Lista 04 - Deteccao de anomalias

Atividade de deteccao de acessos fora do padrao usando o algoritmo
Isolation Forest.

## Arquivos

- `lista04.ipynb`: notebook principal com a analise.
- `acessos_sistema.csv`: dataset utilizado.
- `RELATORIO.md`: interpretacao dos resultados.
- `graficos/`: graficos gerados pelo notebook.
- `resultados/`: registros classificados pelo modelo.

## Execucao

O notebook pode ser aberto no Google Colab ou no Jupyter.

No Colab:

1. Abra o arquivo `lista04.ipynb`.
2. Envie o arquivo `acessos_sistema.csv` para a mesma pasta.
3. Execute todas as celulas.

Para executar localmente:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Depois, abra `lista04.ipynb` no Jupyter ou no editor de notebooks de sua
preferencia.

## Resultado

O modelo foi configurado com `contamination=0.10` e classificou 8 dos 80
registros como anomalias. Os alertas representam acessos que merecem
investigacao, nao ataques confirmados.
