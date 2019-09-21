---
title: Limites de pesquisa de conteúdo no centro de conformidade de & de segurança
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: 'Saiba mais sobre os limites em vigor para o recurso de pesquisa de conteúdo no centro de conformidade & segurança no Office 365, como o número máximo de pesquisas simultâneas. '
ms.openlocfilehash: 6933fcb2a7b54c3617b2c01d54fa50fa4955ead2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071814"
---
# <a name="limits-for-content-search-in-the-security--compliance-center"></a>Limites de pesquisa de conteúdo no centro de conformidade de & de segurança

> [!NOTE]
> Os limites neste tópico são diferentes dos limites atuais para descoberta eletrônica in-loco no Exchange Online e no centro de descoberta eletrônica no SharePoint Online. 
  
Vários limites são aplicados ao recurso de pesquisa de conteúdo no centro de conformidade de & de segurança. Isso inclui pesquisas executadas na página de **pesquisa de conteúdo** e pesquisas associadas a uma ocorrência de descoberta eletrônica. Esses limites ajudam a manter a integridade e a qualidade dos serviços fornecidos nas organizações do Office 365. Também há limites relacionados à indexação de mensagens de email no Exchange Online para pesquisa. Não é possível modificar os limites de pesquisa de conteúdo ou de indexação de email, mas você deve estar ciente deles para que você possa levar esses limites em consideração ao planejar, executar e solucionar problemas de pesquisa de conteúdo. 
  
## <a name="content-search-limits"></a>Limites de pesquisa de conteúdo

A tabela a seguir lista os limites de pesquisa no centro de conformidade e segurança &.
  
|**Descrição do limite**|**Limite**|
|:-----|:-----|
|O número máximo de caixas de correio ou sites que podem ser pesquisados em uma única pesquisa de conteúdo  <br/> |Sem limite  <br/> |
|O número máximo de pesquisas de conteúdo que podem ser executadas ao mesmo tempo em sua organização.  <br/> |Sem limite  <br/> |
|O número máximo de pesquisas de conteúdo que um único usuário pode iniciar ao mesmo tempo. Observe que esse limite é mais provável de hit quando o usuário tenta iniciar várias pesquisas usando o comando **Get-ComplianceSearch \| Start-ComplianceSearch** no PowerShell do centro de conformidade de segurança &.  <br/> |10   <br/> |
|O número máximo de itens por caixa de correio do usuário que são exibidos na página de visualização durante a visualização dos resultados da pesquisa de conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de usuário que são exibidas na página de visualização durante a visualização dos resultados da pesquisa de conteúdo. Os itens mais recentes são exibidos.  <br/> |1,000  <br/> |
|O número máximo de caixas de correio do usuário que podem ser visualizadas nos resultados da pesquisa. Se houver mais de 1000 caixas de correio que contenham conteúdo que corresponda à consulta de pesquisa, somente as primeiras caixas de correio de 1000 com a maioria dos resultados de pesquisa estarão disponíveis para visualização.  <br/> |1,000  <br/> |
|O número máximo de itens encontrados em sites do SharePoint e do OneDrive for Business que são exibidos na página de visualização durante a visualização dos resultados da pesquisa de conteúdo. Os itens mais recentes são exibidos.  <br/> |200  <br/> |
|O número máximo de sites (no SharePoint e no OneDrive for Business) que podem ser visualizados nos resultados da pesquisa. Se houver mais de 200 sites de total que contenham conteúdo que corresponda à consulta de pesquisa, somente os primeiros 200 sites com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |200  <br/> |
|O número máximo de itens por caixa de correio de pasta pública que são exibidos na página de visualização durante a visualização dos resultados da pesquisa de conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de pasta pública que são exibidas na página de visualização durante a visualização dos resultados da pesquisa de conteúdo.  <br/> |200  <br/> |
|O número máximo de caixas de correio públicas que podem ser visualizadas para resultados de pesquisa. Se houver mais de 500 caixas de correio de pasta pública que contenham conteúdo que corresponda à consulta de pesquisa, somente as caixas de correio de pasta pública superior 500 com a maioria dos resultados da pesquisa estarão disponíveis para visualização.  <br/> |500  <br/> |
|O número máximo de caracteres para a consulta de pesquisa (incluindo operadores e condições) para uma pesquisa de conteúdo.  <br/><br/> **Observação:** Esse limite entra em vigor depois que a consulta é expandida, o que significa que a consulta será expandida em relação a cada uma das palavras-chave. Por exemplo, se uma consulta de pesquisa tem 15 palavras-chave e parâmetros e condições adicionais, a consulta é expandida 15 vezes, cada uma com os outros parâmetros e condições na consulta. Portanto, mesmo que o número de caracteres na consulta de pesquisa possa estar abaixo do limite, é a consulta expandida que pode contribuir para exceder esse limite.  <br/> |**Caixas de correio:** 10.000  <br/> **Sites:** 4.000 ao pesquisar todos os Sites ou 2.000 ao Pesquisar até 20 sites <sup>1</sup> <br/> |
|Número máximo de variantes retornadas ao usar um caractere curinga de prefixo para pesquisar uma frase exata em uma consulta de pesquisa ou ao usar um caractere curinga de prefixo e o operador booliano **Near** ou **ONEAR** .  <br/> |10.000 <sup>2</sup> <br/> |
|O número mínimo de caracteres alfabéticos para curingas de prefixo; por exemplo, `time*` `one*`, ou `set*`.  <br/> |3D  <br/> |
|O número máximo de caixas de correio em uma pesquisa de conteúdo que você pode excluir itens em uma ação de "pesquisa e limpeza" (usando o comando **New-ComplianceSearchAction-Purge** ). Se a pesquisa de conteúdo para a qual você está fazendo uma ação de limpeza tiver mais caixas de correio de origem do que esse limite, a ação de limpeza falhará. Para obter mais informações sobre pesquisa e limpeza, confira [Pesquisar e excluir mensagens de email em sua organização do Office 365](search-for-and-delete-messages-in-your-organization.md).  <br/> |50.000  <br/> |
   
> [!NOTE]
> <sup>1</sup> ao pesquisar os locais do SharePoint e do onedrive for Business, os caracteres nas URLs dos sites que estão sendo pesquisados são contados em relação a esse limite. <br/> <sup>2</sup> para consultas de não-frase (um valor de palavra-chave que não usa aspas duplas) usamos um índice de prefixo especial. Isso nos diz que uma palavra ocorre em um documento, mas não onde ele ocorre no documento. Para fazer uma consulta de frase (um valor de palavra-chave com aspas duplas), precisamos comparar a posição dentro do documento para as palavras da frase. Isso significa que não é possível usar o índice de prefixo para consultas de frase. Nesse caso, expandimos internamente a consulta com todas as palavras possíveis às quais o prefixo se expande; por exemplo, `"time*"` pode expandir para `"time OR timer OR times OR timex OR timeboxed OR …"`. 10.000 é o número máximo de variantes à qual a palavra pode ser expandida, e não o número de documentos que correspondem à consulta. Não há um limite superior para termos de não frase. 
  
## <a name="indexing-limits-for-email-messages"></a>Limites de indexação para mensagens de email

A tabela a seguir descreve os limites de indexação que podem resultar em uma mensagem de email sendo retornada como um item não indexado ou um item parcialmente indexado nos resultados de uma pesquisa de conteúdo.
  
|**Limite de indexação**|**Observações**|**Descrição**|
|:-----|:-----|:-----|
|Tamanho máximo do anexo (excluindo arquivos do Excel)  <br/> |150 MB  <br/> |O tamanho máximo de um anexo de email que será analisado para indexação. Qualquer anexo maior do que esse limite não será analisado para indexação, e a mensagem com o anexo será marcada como parcialmente indexada.  <br/> <br/>**Observação:** A análise é o processo em que o serviço de indexação extrai texto do anexo, remove caracteres desnecessários, como pontuação e espaços, e divide o texto em palavras (em um processo chamado geração de tokens), que são armazenados no índice.           |
|Tamanho máximo de arquivos do Excel  <br/> |4 MB  <br/> |O tamanho máximo de um arquivo do Excel localizado em um site ou anexado a uma mensagem de email que será analisada para indexação. Qualquer arquivo do Excel que seja maior do que esse limite não será analisado e o arquivo ou o email que a mensagem com o anexo de arquivo será marcado como não indexado.  <br/> |
|Número máximo de anexos  <br/> |250  <br/> |O número máximo de arquivos anexados a uma mensagem de email que será analisado para indexação. Se uma mensagem tiver mais de 250 anexos, os primeiros 250 anexos serão analisados e indexados, e a mensagem será marcada como parcialmente indexada porque tinha anexos adicionais que não foram analisados.  <br/> |
|Profundidade máxima do anexo  <br/> |até  <br/> |O número máximo de anexos aninhados que são analisados. Por exemplo, se uma mensagem de email tiver outra mensagem anexada a ela e a mensagem anexada tiver um documento do Word anexado, o documento do Word e a mensagem anexada serão indexados. Esse comportamento vai continuar até 30 anexos aninhados.  <br/> |
|Número máximo de imagens anexadas  <br/> |,0  <br/> |Uma imagem anexada a uma mensagem de email é ignorada pelo analisador e não é indexado.  <br/> |
|Tempo máximo gasto na análise de um item  <br/> |30 segundos  <br/> |Um máximo de 30 segundos é gasto em análise de um item para indexação. Se o tempo de análise exceder 30 segundos, o item será marcado como parcialmente indexado.  <br/> |
|Saída de análise máxima  <br/> |2 milhões de caracteres  <br/> |A quantidade máxima de saída de texto do analisador indexado. Por exemplo, se o analisador extrair 8 milhões caracteres de um documento, somente os primeiros 2 milhões de caracteres serão indexados.  <br/> |
|Tokens de anotação máximo  <br/> |2 milhões  <br/> |Quando uma mensagem de email é indexada, cada palavra é anotada com instruções de processamento diferentes que especificam como essa palavra deve ser indexada. Cada conjunto de instruções de processamento é chamado de token de anotação. Para manter a qualidade do serviço no Office 365, há um limite de 2 milhões tokens de anotação para uma mensagem de email.  <br/> |
|Tamanho máximo do corpo no índice  <br/> |67 milhões caracteres  <br/> |O número total de caracteres no corpo de uma mensagem de email e todos os seus anexos. Quando uma mensagem de email é indexada, todo o texto no corpo da mensagem e em todos os anexos é concatenado em uma única cadeia de caracteres. O tamanho máximo dessa cadeia de caracteres indexada é de 67 milhões caracteres.  <br/> |
|Máximo de tokens exclusivos no corpo  <br/> |1 milhão  <br/> |Como explicado anteriormente, os tokens são o resultado da extração de texto do conteúdo, da remoção de Pontuação e de espaços e da divisão em palavras (chamados Tokens) que são armazenadas no índice. Por exemplo, a frase `"cat, mouse, bird, dog, dog"` contém 5 tokens. Mas apenas 4 desses tokens são exclusivos. Há um limite de 1 milhão tokens exclusivos por mensagem de email, o que ajuda a evitar que o índice fique muito grande com tokens aleatórios.  <br/> |
  
## <a name="more-information"></a>Mais informações

Há limites adicionais relacionados a diferentes aspectos da pesquisa de conteúdo, como exportar resultados de pesquisa e indexação de conteúdo. Para obter uma descrição desses limites, consulte os seguintes tópicos:
  
- [Exportar os resultados da Pesquisa de Conteúdo](export-search-results.md#export-limits)
    
- [Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)
    
- [Investigar itens parcialmente indexados na Descoberta Eletrônica do Office 365](investigating-partially-indexed-items-in-ediscovery.md)
    
- [Limites de pesquisa para o SharePoint Online](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
Para obter informações sobre pesquisas de conteúdo, consulte:
  
- [Pesquisa de conteúdo no Office 365](content-search.md)
    
- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
