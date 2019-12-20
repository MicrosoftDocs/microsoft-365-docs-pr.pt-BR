---
title: Executar o módulo de processo na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: 'Saiba mais sobre as diretrizes para preparar arquivos de caso dos dados do Office 365 para análise com a descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: f96b7670a3886b2bfe01801ea76061bea4a37d14
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802904"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a>Executar o módulo de processo na descoberta eletrônica avançada do Office 365

Os arquivos de caso são carregados na descoberta eletrônica avançada durante o **processo**de **preparação** \> . 
  
> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>Diretrizes: preparando dados para descoberta eletrônica avançada

- **Qualidade**: identifique claramente o preenchimento de arquivo de caso pertinente à ocorrência.
    
- **Carrega**: carregar os arquivos em um local acessível à descoberta eletrônica avançada.
    
- **ID de arquivo**: um identificador de arquivo exclusivo na descoberta eletrônica avançada. Se nenhum identificador de arquivo for importado, a descoberta eletrônica avançada gerará automaticamente a ID. Se você mapear a ID em uma carga de processo subsequente e mapear um caminho diferente do que na carga de processo inicial, a descoberta eletrônica avançada substituirá o caminho (em vez de adicionar uma nova entrada de arquivo). A ID pode ser usada como referência no processo de exportação. O valor de ID não deve ser "-1".
    
- **MD5**: essa assinatura é usada para diferenciar entre arquivos (dois arquivos não são considerados duplicatas exatas, a menos que tenham o mesmo MD5). Por padrão, a descoberta eletrônica avançada calcula o MD5 de arquivos. Quando os arquivos carregados são arquivos de texto, é recomendável carregar e mapear o valor MD5 original, em vez de calcular a descoberta eletrônica avançada.
    
- **Nome e tipo de arquivo**:
    
  - A descoberta eletrônica avançada pode processar arquivos de vários formatos e extrair arquivos nativos carregados em um formato padrão, \*como. TXT, HTML ou. XML. O processamento de arquivos de texto é mais rápido do que os arquivos nativos. Arquivos de texto extraídos são armazenados na pasta de casos.
    
  - Não carregue arquivos que não podem ser extraídos, como arquivos do sistema ou imagens gráficas. Esses arquivos podem atrasar o processamento.
    
  - Verifique se os nomes de arquivo são nomeados de forma significativa e se os caminhos estão corretos.
    
- **Caminho do arquivo**: a descoberta eletrônica avançada pode carregar arquivos com comprimentos de caminho de até 400 caracteres.
    
- **Extração de texto**: ao extrair texto de arquivos nativos, além do texto normal, os seguintes itens também são extraídos: texto oculto (Excel e. doc), colunas ocultas (Excel), controles de acompanhamento (. doc), anotações do orador (. ppt), objetos incorporados (por exemplo, objetos do Excel em um. ppt). Eles podem ser exibidos no editor de texto.
    
- **Ignorar texto**: este recurso opcional é definido após a execução do processo e antes da análise. Ignorar texto deve ser usado com cuidado porque seu uso pode reduzir o desempenho da análise de arquivo.
    
- **Texto multilíngue**: a descoberta eletrônica avançada atualmente não lida com nomes multilíngues para marcas, responsáveis e problemas.
    
- **Metadados**: Determine se há metadados que você deseja salvar no banco de dados de caso para referência futura, como intervalo de datas, tamanho do arquivo, tipo de arquivo, responsáveis e assunto. Os metadados podem ser carregados depois que os arquivos já foram carregados sem a execução do inventário ou a adição de sobrecarga de reprocessamento. 
    
  - Se os arquivos foram originalmente carregados pelo caminho, mapeie a coluna de caminho quando importar metadados mais tarde. É possível fazer referência ao arquivo pela ID e mapear um caminho diferente. Este é um cenário útil quando os caminhos de arquivo mudam.
    
  - Se os arquivos foram originalmente carregados por ID de arquivo, mapeie a coluna de ID ao carregar metadados. Fazer referência ao arquivo por caminho (em vez de ID) causará a reinicialização de arquivos com uma ID diferente. A descoberta eletrônica avançada cria cópias dos arquivos, em vez de carregar metadados dos arquivos existentes.
    
- **Famílias**: não é possível carregar uma família sem o seu pai (chefe da família). 
    
- **Tamanho do arquivo**: não há limitação no tamanho dos arquivos carregados para a descoberta eletrônica avançada. Para análise (análise, relevância, etc.), o limite é de 5.242.880 caracteres de texto extraído. Arquivos maiores são ignorados (por exemplo, em relevância, os arquivos não participam do processo de treinamento de relevância e não recebem uma pontuação de relevância após o cálculo em lotes).
    
- **Quantidade de arquivo**: não há limite recomendado para o número de arquivos que podem ser tratados em um único caso. O desempenho depende dos recursos do seu sistema. 
    
## <a name="filtering-files"></a>Filtrando arquivos

Um rótulo definido pelo usuário pode ser associado a um conjunto de arquivos para excluí-los do processo ou de outras tarefas. Cada sessão de processo é associada a uma ID de lote. Embora a ID de lote não fique visível para o especialista em relevância, isso pode ser feito com o uso de um utilitário de pesquisa, adicionando um filtro para o lote atual e marcando todos os arquivos apropriados com um rótulo definido pelo usuário. 
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Executando o módulo de processo e carregando dados](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[Exibir resultados do módulo de processo](view-process-module-results-in-advanced-ediscovery.md)

