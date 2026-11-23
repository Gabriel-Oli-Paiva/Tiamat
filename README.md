<img src="Imagens README/Cabecalho.png"/>

**Aluno :** Gabriel de Oliveira Paiva

<h1 align="center">TIAMAT</h1>

<img src="Imagens README/Brasão com frase.jpg "/>

**Imagem gerada por I.A.**

## Resumo

Este projeto investiga se é possível identificar o gênero musical de uma faixa do Spotify com aprendizado de máquina a partir apenas de características numéricas do áudio e de sua repercussão na plataforma, como dançabilidade, energia, acústica, andamento e popularidade. O conjunto de dados traz uma grande quantidade de faixas distribuídas em muitos gêneros de forma balanceada. Na primeira parte, os modelos são otimizados com o Optuna e avaliados no problema original, com todos os gêneros. Na segunda parte, discute-se por que reduzir o número de classes pode ser vantajoso, e os gêneros são agrupados em famílias musicais, a divisão é refeita e os modelos são treinados novamente com os hiperparâmetros já encontrados, sem nova otimização, o que permite comparar os dois cenários com cuidado, já que o acerto ao acaso muda quando há menos classes.

**Modelos Utilizados:**

**Baseline (para comparação)**

**SVM**

**KNN**

**Floresta Aleatória**

**Naive Bayes**

**Regressão Logística**

## O desenvolvimento do projeto foi organizado em:

1. **Exploração dos dados:** investigação das características do conjunto de faixas do Spotify, com verificação de valores ausentes, da distribuição dos gêneros e de músicas repetidas em mais de um gênero.
2. **Definição das variáveis:** seleção dos 15 atributos numéricos de áudio e de popularidade que alimentam os modelos, excluindo nomes de artistas, álbuns e faixas, e codificação dos gêneros em rótulos numéricos.
3. **Divisão treino/teste:** separação de 80% para treino e 20% para teste com `StratifiedGroupKFold`, agrupando por `track_id` para que uma mesma música nunca apareça nos dois conjuntos.
4. **Modelo de referência (baseline):** construção de um classificador que sempre prevê a classe mais frequente, para contextualizar os resultados dos modelos mais complexos.
5. **Treinamento e otimização:** implementação do Naive Bayes, da Regressão Logística, da Floresta Aleatória, do SVM e do KNN, com busca de hiperparâmetros no Optuna, utilizando 100 trials por modelo.
6. **Validação cruzada:** utilização de `StratifiedGroupKFold` agrupado por `track_id` na otimização, para preservar a proporção dos gêneros em cada partição.
7. **Avaliação final:** comparação dos modelos no conjunto de teste independente, com análise de acurácia, precisão e revocação por gênero.
8. **Agrupamento em famílias musicais:** redução do número de classes a partir do parentesco entre os gêneros, conferido pelos artistas mais frequentes de cada rótulo, com nova divisão treino/teste.
9. **Novo treinamento:** treinamento dos mesmos modelos nas famílias com os hiperparâmetros já encontrados, sem nova otimização, e comparação com o cenário original pelo ganho sobre o baseline.
10. **Conclusão** Interpretação dos resultados obtidos

## O Dataset:

O conjunto de dados reúne 114.000 faixas reais do Spotify, coletadas diretamente da plataforma, cada uma pertencente a um de 114 gêneros musicais, com o mesmo número de faixas por gênero, o que deixa as classes perfeitamente balanceadas. Cada faixa é descrita por informações de identificação (como nome, artista e álbum), que não são usadas nos modelos, e por 15 atributos numéricos: medidas do som, como dançabilidade, energia, volume, acústica, andamento e positividade; características da estrutura musical, como tom, modo e fórmula de compasso; a duração e a indicação de conteúdo explícito; e a popularidade, que mede o sucesso da faixa na plataforma e não o som em si. Há pouquíssimos valores ausentes, restritos a campos de texto que não entram na análise. Dois pontos exigem cuidado: uma mesma música pode aparecer em mais de um gênero, o que levou a uma divisão entre treino e teste agrupada por faixa para evitar vazamento de informação, e os rótulos nem sempre correspondem ao nome do gênero, o que foi conferido pelos artistas mais frequentes antes de agrupar os gêneros em famílias musicais

ele pode ser consultado em <https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset>


## Como Navegar no Repositório:

**Pasta"Imagens README":**

Tem nomeados o Cabeçalho, Rodapé e Brasão com a frase utilizado aqui no README

**Pasta "TIAMAT":**

**dataset_musicas.csv** tem a base de dados utilizadas

**TIAMAT_musical.ipynb** é o arquivo que contém o desenvolvimento do trablaho, com os códigos, explicações e interpretações.

**optuna_generos_musicais.Db** é o arquivo que contém os registros das otimizações de Hiperparâmetros, deve estar na mesma pasta do notebook para que a otimização não tenha que ocorrer novamente

**cache_avaliacao_teste.joblib** carrega as informações dos treinamentos dos modelos com 114 classes de forma a não ser necessário treinar novamente caso esteja na mesma pasta do notebook

**cache_avaliacao_teste_20_familias.joblib** carrega as informações dos treinamentos dos modelos com 20 famílias de forma a não ser necessário treinar novamente caso esteja na mesma pasta do notebook

## Agradecimentos

Ao professor Dr. Daniel R. Cassar pelos conhecimentos transmitidos em aula e pelos materias didáticos fornecidos, aos colegas de sala e amigos Vinícius Marianno, Gustavo Colas, Matheus Mendes, Filipi Martins, Pedro Sá e Heloisa Cano pelas contribuições por meio de ideias e apoios ao longo do projeto.

## Professor

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/drcassar">
        <img src="https://avatars.githubusercontent.com/u/9871905?v=4"
             width="100px;"
             alt="Perfil de Daniel R. Cassar no GitHub"
             style="border-radius:50%;"><br>
        <b>Prof. Dr. Daniel R. Cassar</b>
      </a>
    </td>
  </tr>
</table>


<img src="Imagens README/Rodape.png"/>


