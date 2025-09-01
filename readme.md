Modelo Transformer para Tradução de Português para Inglês
Este repositório traz um modelo Transformer que traduz sentenças do português para o inglês, baseado de forma simplificada no artigo “Attention is All You Need”, de Vaswani et al.

Visão Geral
Carregamento e Pré-processamento de Dados Utiliza o dataset ted_hrlr_translate/pt_to_en do TensorFlow Datasets. A tokenização é feita usando subwords para lidar melhor com palavras desconhecidas.

Arquitetura do Modelo
Contempla um modelo Transformer configurável (número de camadas, dimensão do modelo, número de cabeças de atenção). Inclui codificação posicional, atenção multi-cabeças e redes feed-forward.

Loop de Treinamento
Implementa um loop de treinamento que calcula a perda e atualiza gradientes com o otimizador Adam. O treinamento é salvo em checkpoints periódicos para acompanhamento.

Tradução de Sentenças
Ao final, o modelo recebe sentenças em português e gera a tradução em inglês com base nos pesos treinados.

Funções de Utilidade
Inclui métodos para avaliar as traduções e manipular entradas e saídas do modelo.

Experimentos e Resultados
Treino com 10 Épocas. O modelo concluiu as 10 épocas, porém as traduções apresentaram erros significativos.

Treino com 20 Épocas Ao tentar 20 épocas, o limite de GPU foi atingido na época 18, mas, apesar dessa interrupção, houve uma melhora considerável na eficiência do treinamento por época.

Pontos Positivos
Implementação Enxuta: O modelo foi estruturado de forma a ser mais didático para quem está começando a estudar Transformers.
Aplicabilidade: Demonstra um caso prático de tradução automática, ilustrando a utilidade dos Transformers em PLN.
Pontos Negativos
Limitações de Recursos: Mesmo tentando 20 épocas, a GPU não suportou todo o processo, interrompendo na época 18.
Menos Otimizações: Recursos avançados do Transformer (presentes no artigo original) foram deixados de lado para manter o foco no essencial, o que pode restringir o desempenho em traduções mais complexas.
Avaliação Simplificada: O notebook monitora apenas a perda e não inclui métricas mais completas (como BLEU ou ROUGE).