<img src="Imagens README/Cabecalho.png"/>

**Aluno** Gabriel de Oliveira Paiva

<h1 align="center">TIAMAT</h1>

<img src="Imagens README/Brasão com frase.jpg "/>

**Resumo :** Este projeto investiga se é possível identificar o gênero musical de uma faixa do Spotify com aprendizado de máquina a partir apenas de características numéricas do áudio e de sua repercussão na plataforma, como dançabilidade, energia, acústica, andamento e popularidade. O conjunto de dados traz uma grande quantidade de faixas distribuídas em muitos gêneros praticamente balanceados. Na primeira parte, os modelos são otimizados com o Optuna e avaliados no problema original, com todos os gêneros. Na segunda parte, discute-se por que reduzir o número de classes pode ser vantajoso, e os gêneros são agrupados em famílias musicais, a divisão é refeita e os modelos são treinados novamente com os hiperparâmetros já encontrados, sem nova otimização, o que permite comparar os dois cenários com cuidado, já que o acerto ao acaso muda quando há menos classes.

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
9. **Novo treinamento:** treinamento dos mesmos modelos nas famílias com os hiperparâmetros já encontrados, sem nova otimização, e comparação com o cenário original pelo ganho sobre o baseline, com acurácia balanceada e F1 macro.


## Como Navegar no Repositório:



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


