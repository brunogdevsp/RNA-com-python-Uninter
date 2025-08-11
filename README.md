🧠 Projeto de Rede Neural Artificial (RNA) com Python
Curso de Inteligência Artificial — UNINTER BY - Bruno Garcia
📘 Descrição do Projeto
Este repositório apresenta um estudo aplicado de Redes Neurais Artificiais (RNA) utilizando Python e bibliotecas da stack científica, como pandas, numpy, scikit-learn e matplotlib. O projeto foi desenvolvido como parte do curso de Inteligência Artificial da UNINTER, com foco em regressão multivariada e classificação binária, empregando técnicas de pré-processamento, normalização, codificação categórica e avaliação de desempenho.

⚙️ Tecnologias Utilizadas
Python 3.11

Pandas — Manipulação de dados tabulares

NumPy — Operações matemáticas vetoriais

Scikit-learn — Modelagem com MLPRegressor, normalização com StandardScaler, e métricas de avaliação

Matplotlib — Visualização gráfica da matriz de confusão

🧪 Metodologia
1. Preparação dos Dados
Os dados foram organizados em um DataFrame contendo atributos como tipo, duração, frequência, valor e transporte.

A coluna categórica tipo foi convertida para o tipo category e codificada numericamente via cat.codes.

A matriz de entrada foi normalizada com StandardScaler, resultando em uma distribuição com média zero e desvio padrão unitário.

2. Estrutura da Rede Neural
A RNA foi implementada com a classe MLPRegressor, configurada com os seguintes hiperparâmetros:

python
MLPRegressor(
    hidden_layer_sizes=(5, 3),
    activation='logistic',
    solver='sgd',
    learning_rate='constant',
    learning_rate_init=1e-4,
    max_iter=2000,
    tol=1e-8,
    verbose=True,
    random_state=0
)
Camadas ocultas: Duas camadas com 5 e 3 neurônios, respectivamente

Função de ativação: Sigmoide logística

Algoritmo de otimização: Gradiente descendente estocástico (SGD)

Critério de parada: Tolerância mínima de erro e número máximo de iterações

3. Previsões e Inferência
A RNA foi treinada sobre os dados normalizados (x_norm) e gerou previsões multivariadas coerentes.

Também foram realizadas inferências sobre dados futuros (x_futuro), previamente escalados, com resultados compatíveis com o escopo do problema.

📊 Avaliação de Desempenho
Para avaliar a capacidade de classificação da RNA, foi utilizada uma matriz de confusão binária com os rótulos "lícito" e "fraude". As previsões contínuas foram convertidas em classes discretas com limiar de 0.5:

python
y_pred_binary = (y_pred > 0.5).astype(int)
A matriz de confusão exibiu os seguintes resultados:

Verdadeiro	Previsto	Ocorrências
lícito	lícito	1
lícito	fraude	0
fraude	lícito	0
fraude	fraude	3
A visualização foi gerada com ConfusionMatrixDisplay, utilizando coloração azul para representar a densidade de acertos.

📌 Conclusão
Este projeto demonstra a aplicação prática de Redes Neurais Artificiais em tarefas de regressão e classificação, com pipeline completo de preparação de dados, treinamento supervisionado e avaliação de desempenho. A abordagem adotada é compatível com padrões acadêmicos e profissionais, sendo uma base sólida para projetos mais avançados em Inteligência Artificial.
