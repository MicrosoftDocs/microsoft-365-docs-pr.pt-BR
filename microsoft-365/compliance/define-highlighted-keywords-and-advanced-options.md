---
title: Definir palavras-chave realçadas e opções avançadas na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: 'Saiba como adicionar palavras-chave definidas pelo usuário à relevância para ajudar a identificar arquivos relevantes durante a marcação na descoberta eletrônica avançada do Office 365 e especificar os parâmetros de custo.  '
ms.openlocfilehash: 967258c152c12692cc5eb51f6553317161efa695
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806124"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a>Definir palavras-chave realçadas e opções avançadas na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, é possível adicionar palavras-chave definidas pelo usuário à relevância para ajudá-lo a identificar arquivos relevantes durante a marcação. As palavras-chave serão exibidas na marca cores especificadas em **relevância \> **. 
  
Conforme descrito abaixo, as listas de palavras-chave podem ser adicionadas e as cores atribuídas à lista de palavras-chave e aos problemas relacionados. Uma dica de ferramenta exibe a descrição da palavra-chave, se houver uma, conforme indicado por um sublinhado duplo.
  
> [!IMPORTANT]
> O realce de ocorrências em relevância e exibição de ocorrências de palavras-chave em documentos durante a marcação de relevância não funciona para os conjuntos de caracteres de byte duplo japonês, chinês e coreano. 
  
## <a name="adding-highlighted-keywords"></a>Adicionando palavras-chave realçadas

1. Na guia **configuração \> de relevância de relevância** , selecione **palavras-chave realçadas**.
    
2. Clique no **+** ícone para adicionar palavras-chave. A caixa de diálogo **adicionar novas palavras-chave** é exibida. 
    
3. Em **palavras-chave**, digite a lista palavras-chave, separando palavras-chave com vírgulas. 
    
4. Na lista **cor** , selecione a cor para realçar a lista de palavras-chave inserida. 
    
5. Na lista **selecionar problema** , selecione se deseja aplicar a lista de palavras-chave a "todos os problemas" ou a problemas selecionados. 
    
6. Em **Descrição**, digite a lista de palavras-chave (opcional).
    
    ![Adicionar novas palavras-chave](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. Clique em **OK** quando terminar. A lista criada é adicionada à tabela lista de palavras-chave e pode ser editada ou excluída. 
    
    ![Lista de palavras-chave de configuração de relevância](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
As palavras-chave definidas pelo usuário serão exibidas, na marca cores especificadas em relevância \> . 
  
## <a name="specifying-relevance-setup-advanced-settings"></a>Especificar configurações avançadas da configuração de relevância

Essas configurações afetam a faixa e decidem os gráficos de relevância.
  
1. Na guia **configuração \> de relevância de relevância** , selecione **Configurações avançadas**.
    
2. Na caixa de diálogo **parâmetros de custo** , faça as seguintes seleções: 
    
1. Na lista **análise de custo por hora ($)** , selecione o valor em dólares ou aceite o padrão. 
    
2. Na lista **número de arquivos revisados por hora** , selecione o valor ou aceite o padrão. 
    
    ![Parâmetros de custo de instalação de relevância](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. Clique em **Salvar**. As configurações selecionadas são salvas.
    
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Como definir problemas e atribuir usuários](define-issues-and-assign-users.md)
  
[Como configurar carregamentos para adicionar os arquivos importados](set-up-loads-to-add-imported-files.md)

