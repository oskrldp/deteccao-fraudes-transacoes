# Detecção de Fraudes em Transações

Este projeto aplica análise de dados e machine learning a transações de cartão de crédito. O objetivo é identificar a classe rara (`Class = 1`), que representa fraude, sem ser enganado pela acurácia elevada causada pelo forte desbalanceamento dos dados.

## Se você nunca usou o Google Colab

1. Abra https://colab.research.google.com/ no navegador.
2. Entre na sua conta Google, se necessário.
3. Clique em **Arquivo > Fazer upload de notebook**.
4. Escolha o arquivo `notebooks/deteccao_fraudes_completo.ipynb` deste projeto.
5. Quando o notebook abrir, clique na primeira célula.
6. Execute a célula pelo botão de reprodução à esquerda ou com `Shift + Enter`.
7. Espere aparecer o resultado antes de executar a célula seguinte.
8. Continue de cima para baixo, sem pular células.
9. Se o Colab perguntar se você confia no notebook, confirme, pois o código está visível e comentado.

O notebook contém instruções antes de cada bloco. Você não precisa decidir onde colocar os códigos: cada trecho já está em sua própria célula.

## O que o projeto faz

- baixa o dataset público utilizado na aula;
- verifica estrutura, valores ausentes e duplicatas;
- mostra o forte desbalanceamento entre transações normais e fraudes;
- cria a variável `Amount_log`;
- separa treino, validação e teste de forma estratificada;
- treina Regressão Logística, Random Forest, modelo com SMOTE e XGBoost;
- avalia precision, recall, F1-score, matriz de confusão e Average Precision;
- escolhe um limiar de decisão usando a validação;
- compara todos os modelos;
- mostra importância das variáveis e explicações com SHAP;
- salva o melhor modelo para uso posterior.

## Estrutura

```text
projeto_deteccao_fraudes/
├── README.md
├── requirements.txt
└── deteccao_fraudes_completo.ipynb
```

## Conceitos mais importantes

- `Class = 0`: transação normal.
- `Class = 1`: fraude.
- **Recall da fraude**: porcentagem das fraudes reais que o modelo encontrou.
- **Precision da fraude**: entre os alertas emitidos, quantos realmente eram fraude.
- **F1-score**: equilíbrio entre precision e recall.
- **Falso negativo**: fraude que o modelo deixou passar.
- **Falso positivo**: transação normal enviada para investigação.

A acurácia não deve ser usada sozinha porque aproximadamente 99,83% dos registros pertencem à classe normal.

## Fonte dos dados

O notebook baixa os dados deste endereço público:

```text
https://storage.googleapis.com/download.tensorflow.org/data/creditcard.csv
```

## Entrega sugerida

1. Execute todas as células do notebook.
2. Confira se os gráficos e relatórios apareceram.
3. Preencha a seção **Conclusão pessoal** no final do notebook usando os seus resultados.
4. No Colab, clique em **Arquivo > Salvar uma cópia no Drive**.
5. Depois clique em **Arquivo > Fazer download > Fazer download do .ipynb**.
6. Crie um repositório público no GitHub.
7. Envie este `README.md`, o `requirements.txt` e o notebook executado.
8. Copie o endereço do repositório e cole na área **Entregar Projeto** da plataforma.

Não copie números do vídeo para a conclusão. Use os resultados que aparecerem quando você executar o notebook.

## Execução local opcional

Quem quiser executar no próprio computador pode instalar as dependências com:

```bash
pip install -r requirements.txt
```
