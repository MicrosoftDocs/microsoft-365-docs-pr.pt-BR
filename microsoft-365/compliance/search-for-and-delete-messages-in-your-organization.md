---
title: Pesquisar e excluir mensagens de email em sua organização do Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Você pode usar o recurso Pesquisar e limpar do Centro de Segurança e Conformidade do Office365 para pesquisar e excluir uma mensagem de e-mail de todas as caixas de correio da sua organização.
ms.openlocfilehash: 53ec50ddd42e1d17580f4b1581ef8d8fe02f97bf
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259969"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization"></a>Pesquisar e excluir mensagens de e-mail em sua organização do Office 365

**Este artigo é para os administradores. Você está tentando encontrar itens na sua caixa de correio que deseja excluir? Consulte [Localizar uma mensagem ou um item com a Pesquisa Instantânea](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
Você pode usar o recurso Pesquisa de Conteúdo no Office365 para pesquisar e excluir uma mensagem de email de todas as caixas de correio da sua organização. Isso pode ajudar você a encontrar e remover um email potencialmente nocivo ou de alto risco, como por exemplo:
  
- Mensagens que contenham anexos perigosos ou vírus
    
- Mensagens de phishing
    
- Mensagens que contêm dados confidenciais
    
> [!CAUTION]
> Pesquisar e limpar é um recurso poderoso que permite a qualquer pessoa com as permissões necessárias excluir mensagens de email de caixas de correio em sua organização. 
  
## <a name="before-you-begin"></a>Antes de começar

- Para criar e executar uma pesquisa de conteúdo, você precisa ser membro do grupo de funções **Gerente de Descoberta Eletrônica**ou então ter sido designado para a função de gerenciador de**Pesquisa de Conformidade**. Para excluir mensagens, você tem de ser membro do grupo de funções **Gerenciamento da Organização** ou ter sido designado para a função de gerenciamento **Pesquisar e Limpar**. Para saber mais sobre como adicionar usuários a um grupo de função, confira [Atribuir permissões de Descoberta Eletrônica no Centro de Segurança e Conformidade](assign-ediscovery-permissions.md).
    
- Você tem que usar o Centro de Segurança e Conformidade do PowerShell para excluir mensagens. Consulte a[Etapa 2](#step-2-connect-to-security--compliance-center-powershell) para obter instruções sobre como se conectar.
    
- Só é possível remover no máximo dez itens de cada vez por caixa de correio. Como o recurso de pesquisa e remoção de mensagens tem como objetivo ser uma ferramenta de resposta a incidentes, esse limite ajuda a garantir que as mensagens sejam rapidamente removidas das caixas de correio. Este recurso não tem como objetivo limpar as caixas de correio do usuário. Para excluir mais de 10 itens, você pode usar o comando **Search-Mailbox-DeleteContent** no PowerShell do Exchange Online. Consulte [Procurar e excluir mensagens](search-for-and-delete-messagesadmin-help.md).
    
- O número máximo de caixas de correio em uma pesquisa de conteúdo na qual você pode excluir itens executando uma ação de pesquisar e limpar é de 50.000. Se a pesquisa de conteúdo (que você cria na [ Etapa 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) tiver mais de 50.000 caixas de correio de origem, a ação limpar (que você vai criar na etapa 3) falhará. Confira a seção[Mais informações](#more-information) para obter uma dica de como executar uma operação Pesquisar e limpar em mais de 50.000 caixas de correio. 
    
- O procedimento neste artigo só pode ser usado para excluir itens nas caixas de correio e pastas públicas do Exchange Online. Não é possível usá-lo para excluir o conteúdo dos sites do SharePoint ou do OneDrive for Business.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Etapa 1: Criar uma Pesquisa de conteúdo para localizar a mensagem para exclusão

A primeira etapa é criar e executar uma pesquisa de conteúdo a fim de localizar a mensagem que você deseja remover das caixas de correio em sua organização. Você pode criar a pesquisa usando o Centro de Segurança e Conformidade ou executando os cmdlets **New-ComplianceSearch** e **Start-ComplianceSearch**. As mensagens que correspondem à consulta desta pesquisa serão excluídas, executando-se o comando **New-ComplianceSearchAction-Purge** na [Etapa 3](#step-3-delete-the-message). Confira informações sobre como criar uma Pesquisa de Conteúdo e como configurar consultas de pesquisa nos tópicos a seguir: 
  
- [Pesquisa de Conteúdo no Office 365](content-search.md)
    
- [Consultas de palavra-chave para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> Os locais de conteúdo pesquisados na Pesquisa de Conteúdo que você criar nesta etapa não podem incluir sites do SharePoint ou do OneDrive for Business. Em uma pesquisa de conteúdo que será usada para mensagens de email, você somente pode incluir as caixas de correio e as pastas públicas. Se a pesquisa de conteúdo incluir sites, você receberá uma mensagem de erro na Etapa 3 quando executar o cmdlet **New-ComplianceSearchAction**. 
  
### <a name="tips-for-finding-messages-to-remove"></a>Dicas para localizar mensagens para remoção

O objetivo da consulta de pesquisa é restringir os resultados da pesquisa apenas à mensagem ou mensagens que você deseja remover. Veja algumas dicas:
  
- Se você souber o texto ou a frase exata usada na linha de assunto da mensagem, use a propriedade **Subject** na consulta de pesquisa. 
    
- Se você souber a data exata (ou o intervalo de datas) da mensagem, inclua a propriedade **Received** na consulta de pesquisa. 
    
- Se você souber quem enviou a mensagem, inclua a propriedade **From** na consulta de pesquisa. 
    
- Visualize os resultados da pesquisa para verificar se a pesquisa de conteúdo retornou apenas a mensagem (ou mensagens) que você deseja excluir.
    
- Use as estatísticas de estimativa de pesquisa (exibidas no painel de detalhes da pesquisa no Centro de Segurança e Conformidade ou use o cmdlet[Get-ComplianceSearch ](https://go.microsoft.com/fwlink/p/?LinkId=517934)) para obter uma contagem do número total de resultados. 
    
Aqui estão dois exemplos de consultas para localizar mensagens de email suspeitas.
  
- Essa consulta retornará as mensagens que foram recebidas pelos usuários entre 13 de abril de 2016 e 14 de abril de 2016 e que contêm as palavras "ação" e "obrigatório" na linha de assunto.
    
    ```powershell
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```

- Essa consulta retornará as mensagens que foram enviadas por chatsuwloginsset12345@outlook.com e que contêm a frase exata "Atualizar as informações da sua conta" na linha de assunto.
    
    ```powershell
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Etapa 2: Conectar-se ao Centro de Segurança e Conformidade usando o PowerShell

A próxima etapa é conectar-se ao Centro de Segurança e Conformidade da sua organização. Para obter instruções passo a passo, confira [Conectar-se ao Centro de Segurança e Conformidade no PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Se a sua conta do Office 365 usa a MFA (autenticação multifator) ou autenticação federada, você não poderá usar as instruções do tópico anterior sobre como se conectar ao Centro de Segurança e Conformidade no PowerShell. Em vez disso, confira as instruções no tópico [ Conectar-se ao Centro de Segurança e Conformidade no PowerShell, usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Etapa 3: Excluir a mensagem

Após a criação e detalhamento de uma pesquisa de conteúdo com o objetivo de retornar a mensagem que você deseja remover e está conectada ao Centro de Segurança e Conformidade no PowerShell, a etapa final será executar o cmdlet**New-ComplianceSearchAction** para excluir a mensagem.  Você pode excluir a mensagem temporária ou permanentemente. Uma mensagem excluída temporariamente (soft- deleted) é movida para a pasta Itens Recuperáveis de um usuário e mantida até que o período de retenção de itens excluídos expire. As mensagens excluídas permanentemente (hard-deleted) serão definitivamente removidas da próxima vez que a caixa de correio for processada pelo assistente de pastas gerenciadas. Se a recuperação de um único item estiver habilitada para a caixa de correio, os itens excluídos permanentemente serão removidos definitivamente após o término do período de retenção de itens excluídos. Se uma caixa de correio for colocada em espera, as mensagens excluídas serão preservadas até que a duração de retenção do item expire ou até que o período de espera seja interrompido na caixa de correio.
  
No exemplo a seguir, o comando exclui temporariamente os resultados da pesquisa retornados por uma Pesquisa de conteúdo chamada “Remover mensagens de phishing”. 

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Para excluir permanentemente os itens retornados pela Pesquisa de conteúdo "Remover mensagens de phishing", execute este comando:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Quando você executa o comando anterior para excluir mensagens de forma temporária ou permanente, a pesquisa especificada pelo parâmetro *SearchName* é a Pesquisa de conteúdo que você criou na Etapa 1. 
  
Para obter mais informações, consulte [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).

## <a name="more-information"></a>Mais informações

- **Como obter o status da operação de pesquisa e exclusão?**

    Execute o **Get-ComplianceSearchAction** para obter o status da operação de exclusão. O objeto criado quando você executa o cmdlet **New-ComplianceSearchAction** é nomeado de acordo com este formato: `<name of Content Search>_Purge`. 
    
- **O que acontece após a exclusão de uma mensagem?**

   Uma mensagem excluída com o comando `New-ComplianceSearchAction -Purge -PurgeType HardDelete` será movida para a pasta Remoções e não poderá ser acessada pelo usuário. Uma vez na pasta Remoções, a mensagem é mantida pelo período de retenção do item excluído, se a recuperação de itens individuais estiver habilitada para a caixa de correio. (No Office 365, a recuperação de item único é habilitada por padrão quando uma nova caixa de correio é criada.) Após o período de retenção de item excluído expirar, a mensagem será marcada para exclusão permanente e será definitivamente removida do Office 365 da próxima vez que a caixa de correio for processada pelo assistente de pastas gerenciadas. 

   Se você usar o comando `New-ComplianceSearchAction -Purge -PurgeType SoftDelete`, as mensagens serão movidas para a pasta Exclusões na pasta itens recuperáveis do usuário. Ela não é removida imediatamente do Office365. O usuário pode recuperar mensagens na pasta Itens Excluídos de acordo com o período de retenção do item excluído configurado para a caixa de correio. Após esse período de retenção (ou se o usuário remover a mensagem antes do período expirar), a mensagem será movida para a pasta Remoções e não poderá mais ser acessada pelo usuário. Uma vez na pasta Remoções, a mensagem é mantida novamente durante o período de retenção do item excluído configurado para a caixa de correio, se a recuperação de itens individuais estiver habilitada para a caixa de correio. (No Office 365, a recuperação de item único é habilitada por padrão quando uma nova caixa de correio é criada.) Após o período de retenção de item excluído expirar, a mensagem será marcada para exclusão permanente e será definitivamente removida do Office 365 da próxima vez que o assistente de pastas gerenciadas processar a caixa de correio. 
    
- **E se você tiver que excluir uma mensagem de mais de 50.000 caixas de correio?**

    Conforme mencionado anteriormente, você pode executar uma operação de pesquisa e limpeza em um máximo de 50.000 caixas de correio. Se você precisar executar uma operação pesquisar e limpar em mais de 50.000 caixas de correio, considere a possibilidade de criar filtros de permissões de pesquisa temporários que reduziriam o número de caixas de correio a ser pesquisadas para menos de 50.000 caixas de correio. Por exemplo, se a sua organização tiver caixas de correio em departamentos, estados ou países diferentes, você poderá criar um filtro de permissões de pesquisa de caixa de correio com base em uma dessas propriedades de caixa de correio para pesquisar um subconjunto de caixas de correio em sua organização. Depois de criar o filtro de permissões de pesquisa, você criaria a pesquisa (descrita na etapa 1) e, em seguida, excluirá a mensagem (descrita na etapa 3). Em seguida, você pode editar o filtro para pesquisar e limpar mensagens em um conjunto diferente de caixas de correio. Para obter mais informações sobre como criar filtros de permissões, confira [Configurar a filtragem de permissões para Pesquisa de Conteúdo](permissions-filtering-for-content-search.md).
    
- **Os itens não indexados incluídos nos resultados da pesquisa serão excluídos?**

    Não, o comando New-ComplianceSearchAction-Purge não exclui itens não indexados. 
    
- **O que acontece se uma mensagem for excluída de uma caixa de correio que foi colocada no Bloqueio In-loco ou na Retenção de Litígio ou se for parte de uma política de retenção do Office 365?**

    Quando for removida e transferida para a pasta Remoções, a mensagem será mantida até que a duração da retenção expire. Se a duração de retenção for ilimitada, os itens serão mantidos até que a retenção seja removida ou a duração da espera seja alterada.
    
- **Por que o fluxo de trabalho de pesquisa e remoção é dividido entre diferentes grupos de função no centro de segurança e conformidade?**

    Conforme explicado anteriormente, uma pessoa deve ser membro do grupo de funções Gerente de Descoberta Eletrônica ou receber a função de gerenciamento de Pesquisa de Conformidade para pesquisar nas caixas de correio. Para excluir mensagens, a pessoa precisa ser membro do grupo de funções Gerenciamento da Organização ou receber a função de gerenciamento Pesquisa e Limpar. Isso possibilita o controle de quem pode pesquisar nas caixas de correio da organização e quem pode excluir mensagens. 
