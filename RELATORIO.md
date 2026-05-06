# Relatório de Análise Multidimensional (PCA e MDS)
## 1. Problema Investigado

O objetivo da análise foi investigar se condições climáticas influenciam o comportamento dos voos, especialmente em relação aos atrasos, utilizando técnicas de redução de dimensionalidade.

## 2. Fundamentação Teórica
🔵 PCA (Principal Component Analysis)

O PCA é uma técnica de redução de dimensionalidade que transforma variáveis originais em componentes principais ortogonais, organizados de acordo com a quantidade de variância explicada.

O primeiro componente captura a maior parte da variância
Os seguintes capturam variações residuais

Seu objetivo é reduzir o número de dimensões mantendo o máximo de informação possível.

🔴 MDS (Multidimensional Scaling)

O MDS projeta os dados em um espaço de menor dimensão preservando, tanto quanto possível, as distâncias entre as observações.

Diferente do PCA:

Não depende de variância
Pode capturar relações mais complexas

Seu foco é manter similaridades entre os dados.

## 3. Descrição do Dataset

Foi utilizado um conjunto de dados contendo informações de voos nos Estados Unidos em dezembro de 2019, incluindo:

Dados operacionais (atrasos)
Dados meteorológicos (temperatura, vento, visibilidade, precipitação)

Cada linha representa um voo individual.

## 4. Seleção das Features

As variáveis analisadas incluem:

Atraso na partida e chegada
Temperatura
Velocidade do vento
Visibilidade
Precipitação

Além disso, foi considerada a variável categórica:

Aeroporto de origem
✔ Justificativa

A seleção foi feita para combinar:

Variáveis operacionais (atrasos)
Variáveis climáticas (possíveis causas externas)
## 5. Preparação dos Dados

Os dados passaram por:

Remoção de valores ausentes
Padronização das variáveis
Remoção de outliers extremos

Essas etapas garantem que:

Nenhuma variável domine a análise por escala
Ruídos extremos não distorçam os resultados
## 6. Análise de Correlação

A análise indicou:

Forte relação entre atraso na partida e atraso na chegada
Baixa correlação entre variáveis climáticas e atrasos

 Isso já sugere que o clima, isoladamente, não explica bem os atrasos.

## 7. Aplicação do PCA

A projeção em duas dimensões mostrou:

Um gradiente contínuo de valores de atraso
Ausência de clusters bem definidos
✔ Interpretação
Os dados não se organizam em grupos distintos
Os atrasos variam de forma contínua

 Isso indica que não há separação natural entre diferentes comportamentos de voo baseada nas variáveis analisadas.

## 8. Variância Explicada

Os dois primeiros componentes principais explicam apenas parte da variância total.

✔ Interpretação
A estrutura dos dados é complexa
Duas dimensões não são suficientes para capturar toda a informação
## 9. Contribuição das Variáveis (Loadings)

A análise dos loadings mostrou que:

Variáveis de atraso possuem maior influência nos primeiros componentes
Variáveis climáticas têm contribuição menor
✔ Interpretação

 O PCA está sendo dominado por:

comportamento operacional dos voos
não pelas condições climáticas
## 10. Aplicação do MDS

A projeção via MDS apresentou:

Um grande agrupamento central
Pontos mais dispersos nas extremidades
## 11. Interpretação do MDS
Pontos próximos representam voos com características semelhantes
Pontos distantes indicam comportamentos distintos
✔ Observações
Forte sobreposição entre observações
Ausência de separação clara entre grupos
## 12. Uso da Variável Categórica

A variável categórica considerada foi o aeroporto de origem.

Ela foi utilizada na visualização para verificar se diferentes aeroportos formariam agrupamentos distintos.

✔ Resultado observado
Não houve separação clara por aeroporto
Os pontos permanecem altamente sobrepostos
✔ Interpretação

Isso indica que:

O aeroporto de origem não é um fator determinante na estrutura dos dados analisados
Outros fatores têm maior influência, especialmente os atrasos
## 13. Comparação PCA vs MDS
Aspecto	PCA	MDS
Base	Variância	Distância
Estrutura	Gradiente contínuo	Agrupamentos leves
Separação	Baixa	Baixa
✔ Conclusão

Ambos os métodos indicam:

ausência de clusters bem definidos
alta sobreposição entre observações
## 14. Padrões Identificados
Atrasos apresentam comportamento contínuo
Variáveis climáticas não geram separação clara
Existe um núcleo central de voos com características semelhantes
## 15. Outliers

Foram observados pontos mais afastados, que podem representar:

condições climáticas extremas
atrasos atípicos

Mesmo após filtragem, esses pontos ainda aparecem na projeção.

## 16. Riscos de Interpretação
Redução para 2D pode ocultar estruturas importantes
Sobreposição não significa ausência total de relação
Correlação fraca não implica ausência de influência
## 17. Redução de Features
PCA
Adequado para redução de dimensionalidade
Mantém a maior parte da variância
MDS
Mais adequado para visualização
Não é ideal para uso direto em modelos preditivos
## 18. Respostas às Perguntas
Problema: relação entre clima e atrasos
Features: atrasos + variáveis climáticas
Expectativa: clima influenciando atrasos
PCA: não revelou clusters claros
Variáveis mais influentes: atrasos
Variância: moderada
MDS: mostrou proximidade entre voos
Padrões semelhantes entre PCA e MDS: sim
Separação por categoria: não
Outliers: sim
Interpretação coerente: sim
PCA para redução: sim
MDS: visualização
Aprendizado: clima não explica atrasos isoladamente
## 19. Conclusão

A aplicação de PCA e MDS permitiu compreender melhor a estrutura dos dados e revelou que:

Os atrasos são o principal fator de variação
Variáveis climáticas têm impacto limitado quando analisadas isoladamente
Não há separação clara entre diferentes comportamentos de voo
## Conclusão Final

As técnicas utilizadas foram eficazes para:

Identificar a ausência de agrupamentos claros
Evidenciar a dominância das variáveis operacionais
Indicar que o problema é mais complexo do que inicialmente esperado

 Cancelamentos ou atrasos não podem ser explicados apenas pelo clima, sendo necessário considerar múltiplos fatores.
