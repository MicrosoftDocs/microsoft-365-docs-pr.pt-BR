---
title: Definir a opção Ignorar texto para analisar na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Saiba como definir a regra para ignorar texto específico ao usar módulos de análise e processo na descoberta eletrônica avançada.
ms.openlocfilehash: e167cc2877ca6e1ecb2b4ac896e2000b0441be59
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285847"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>Definir a opção Ignorar texto para analisar na descoberta eletrônica avançada (clássico)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
O recurso Ignorar texto pode ser aplicado a todos os módulos de descoberta eletrônica avançados a seguir ou a qualquer um dos seguintes módulos de descoberta eletrônica avançada: analisar (próximos duplicatas, threads de email, temas) e relevância. O texto ignorado não aparecerá nos arquivos exibidos de relevância e a análise/cálculo descartará o texto ignorado.
  
Se o recurso Ignorar texto tiver sido definido anteriormente para módulos que já foram executados, a configuração de ignorar texto será agora protegida contra modificações. No entanto, o recurso Ignorar texto para o módulo de relevância ainda pode ser alterado a qualquer momento.
  
## <a name="how-ignore-text-filters-are-applied"></a>Como ignorar filtros de texto são aplicados

Vários filtros de texto ignorar são aplicados na ordem em que foram inseridos. Para alterar a ordem na qual são aplicadas, elas devem ser excluídas e reinseridas na ordem desejada.
  
Por exemplo, se o conteúdo de texto é: "DAVE BOB Ana Maria, véspera", veja a seguir exemplos de ignorar entradas de texto e os resultados que essas entradas produzem:

|**Ignorar entradas de texto** <br/> |**Resultados** <br/> |
|:-----|:-----|
|"ALICE", "BOB CAROL"  <br/> |"VÉSPERA DA DAVE"  <br/> |
|"ANA", "BOB ALICE CAROL"  <br/> |"DAVE BOB CAROL (VÉSPERA)"  <br/> |
   
A segunda entrada de texto ignorar não é implementada porque a cadeia de caracteres não é encontrada como tal após a aplicação do primeiro texto para ignorar.
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>Usar expressões regulares ao definir o texto de ignorar

As expressões regulares têm suporte para uso ao definir o texto de ignorar. A seguir estão exemplos de sintaxe e uso de expressões regulares:
  
- Para remover (ignorar) o texto de início até o final de uma linha:
    
     `Begin(.*)$`
    
    onde "Begin" é a ocorrência inicial dessa cadeia de caracteres na linha.
    
    Por exemplo, para o seguinte texto:
    
    **"Esta é a primeira frase e primeira linha**
    
    **Esta é segunda frase e segunda linha "**
    
    a expressão regular primeiro (. \* ) $ resultará em:
    
    **"Isso é**
    
    **Esta é segunda frase e segunda linha "**
    
- Para remover avisos de isenção de responsabilidade e instruções legais automaticamente inseridos no final dos threads de email:
    
     `Begin(.|\s)*End`
    
    onde "Begin" e "End" são cadeias de caracteres exclusivas no início e no final de um parágrafo com quebra de texto. 
    
    Por exemplo, a expressão regular a seguir removerá avisos de isenção de responsabilidade e declarações legais que estavam no thread de email entre as cadeias de caracteres de início e término:
    
    **Esta mensagem contém informações confidenciais (. | \s) \* se a verificação for necessária, solicite uma versão de cópia de disco**
    
- Para remover um aviso de isenção de responsabilidade (incluindo caracteres especiais): 
    
    Por exemplo, para o texto a seguir (com o aviso de isenção de responsabilidade representado aqui por x): 
    
    **/\*\ Esta mensagem contém informações confidenciais. XXXX XXXX**
    
    **XXXX XXXX XXXX XXXX XXXX XXXX XXXX**
    
    **XXXX XXXX se a verificação for necessária, solicite uma versão de cópia impressa. /\*\**
    
    a expressão regular para remover o aviso de isenção de responsabilidade acima deve ser: 
    
    **\/\\*\\ Esta mensagem contém informações confidenciais \. (. | \s) \* se a verificação for necessária, solicite uma versão \. de cópia de disco \/\\*\\**
    
- Regras de expressão regular:
    
  - Todos os caracteres que não fazem parte do alfabeto, exceto os espaços (s), "_" e "-" devem ser precedidos por " \" .
    
  - O campo normal eExpression pode ter comprimento ilimitado.
    
> [!TIP]
> Para obter uma explicação e sintaxe detalhada de expressões regulares, consulte: [linguagem de expressão regular-referência rápida](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx). 
  
## <a name="define-ignore-text-rule"></a>Definir a regra de ignorar texto

1. Na guia **Gerenciar \> \> Opções** de análise, na seção **Ignorar texto** , clique no **+** ícone para adicionar uma regra. 
    
2. Na caixa de diálogo **Adicionar ignorar texto** , no campo **nome** , digite um nome para a regra de ignorar texto. 
    
    ![Adicionar texto ignorado](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. Na caixa de **texto** , digite o texto a ser ignorado. O campo de texto permite um número ilimitado de caracteres. 
    
    > [!TIP]
    > Conforme mostrado na janela acima, clique em **lâmpada** para ver as diretrizes de sintaxe comuns da regra de ignorar texto. 
  
4. Marque a caixa de seleção diferencia **maiúsculas de minúsculas** , se desejado. 
    
5. Na lista **aplicar a** , selecione os módulos de descoberta eletrônica avançados nos quais a definição será aplicada. 
    
6. Se você quiser uma execução de teste em texto de exemplo, digite texto de exemplo na caixa de texto de **entrada** e clique em **testar**. Os resultados são exibidos na caixa de texto de **saída** . 
    
7. Clique em **OK** para salvar a regra de ignorar texto. A regra de ignorar texto definida é exibida. 
    
    ![Definir nome de texto ignorado](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre a similaridade de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuração das opções de análise](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuração analisar configurações avançadas](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Exibindo resultados de análise](view-analyze-results-in-advanced-ediscovery.md)

