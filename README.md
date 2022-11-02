# Versão inicial

Esse é um script gerador de dados com formatação para inserção em bancos de dados SQL. Feito com o intuito de ser usado para fins de estudo ou testes.

## Funcionamento:

Crie um arquivo nomeado como *atributos.txt* e coloque os atributos desejados nele, em uma única linha, separado por uma única barra de espaço. Atributos inválidos serão ignorados pelo script. Será criado um arquivo chamado *dados_formatados.txt* na mesma pasta em que está o executável do script e os dados gerados serão escritos nele. Alguns atributos requerem parâmetros adicionais que serão solicitados no prompt, caso esses atributos recebam valores *inválidos*, **valores padrão são usados**. Os valores padrão de cada atributo são especificados na próxima seção. Alguns desses parâmetros serão solicitados em forma de perguntas de *"sim ou não"*, nesses casos, deve-se responder usando **[1] para "sim"** e **[2] para "não"**, pois correspondem aos valores booleanos **True** e **False**. Todos os intervalos solicitados e padrão são fechados (ou seja, incluem ambos os valores limite do intervalo).

### Atributos suportados:

* nome --> cria um nome aleatóriamente usando uma base de dados para **prenomes** e outra para **sobrenomes**, caso o atributo "genero" também seja escolhido, usará uma base de dados para **prenomes masculinos** e outra para **prenomes femininos**. Caso sejam colocados mais de uma coluna "nome" sem colocar uma coluna "genero", nomes distintos serão gerados, podendo ser de gêneros distintos. Caso a coluna "genero" seja escolhida com mais de uma coluna "nome", os nomes gerados serão todos do mesmo gênero;

* genero --> escolhe "M" ou "F", é vinculado com o atributo "nome", caso seja colocado mais de um atributo "genero" dentro de *atributos.txt*, todos sairão com a mesma letra no arquivo de saída;

* datanasc --> gera uma data de nascimento. Caso essa coluna seja escolhida, será solicitado ao usuário o intervalo de idade desejado para esse atributo (padrão: [0, 120])

* inteiro --> gera um inteiro aleatório. Caso essa coluna seja escolhida, solicita ao usuário alguns parâmetros adicionais: intervalo de números que podem ser escolhidos (padrão: [0, 100]), se deseja que o número seja escrito como char (valor entre aspas, o padrão é 0), se sim, solicita o número total de digitos que o número deve ter (padrão: 0), no arquivo de saída, escreve zeros à esquerda caso o número de dígitos do número gerado seja menor que o especificado. Podem se adicionar várias colunas desse tipo em *atributos.txt*, serão solicitados parâmetros adicionais para cada ocorrência dessa coluna no arquivo, os parâmetros serão pedidos e aplicados para a ordem em que estão no arquivo;

* float --> gera um número com casas decimais aleatório. Parâmetros adicionais solicitados: intervalo (aceita valores inteiros e fracionários, padrão: [0, 100]), quantidade de casas decimais do número (assim como é especificado no banco, no momento da criação da tabela, padrão: 2), se deseja que o número seja escrito como char (valor entre aspas, padrão: 0), se sim, solicita o número total de dígitos do número gerado, contando com "." e as casas decimais. Podem ser geradas várias colunas desse tipo, serão solicitados parãmetros adicionais para cada ocorrência em *atributos.txt*
