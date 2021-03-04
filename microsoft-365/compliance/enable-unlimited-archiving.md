---
title: Habilitar arquivamento ilimitado - Ajuda do administrador
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Para administradores: saiba como habilitar o arquivamento de expansão automática, que fornece aos usuários armazenamento ilimitado para suas caixas de correio do Exchange Online. Você pode habilitar o arquivamento de expansão automática para toda a sua organização ou apenas para usuários específicos.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 967b623b8ac1898567b5e6e779e8e557404b5242
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423652"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Habilitar arquivamento ilimitado - Ajuda do administrador

Você pode usar o recurso de arquivamento de expansão automática do Exchange Online para habilitar espaço de armazenamento ilimitado para caixas de correio de arquivo morto. Quando o arquivamento de expansão automática é ativado, o espaço de armazenamento adicional é adicionado automaticamente à caixa de correio de arquivo morto de um usuário quando ele se aproxima do limite de armazenamento. O resultado é a capacidade de armazenamento de caixa de correio ilimitada. Você pode ativar o arquivamento de expansão automática para todos em sua organização ou apenas para usuários específicos. Para obter mais informações sobre o arquivamento de expansão automática, consulte [Overview of unlimited archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Antes de habilitar o arquivamento de expansão automática

- Você precisa ser um administrador global em sua organização ou membro do grupo de função Gerenciamento da Organização em sua organização do Exchange Online para habilitar o arquivamento de expansão automática para toda a sua organização ou para usuários específicos. Como alternativa, você precisa ser membro de um grupo de funções atribuído à função Destinatários de Email para habilitar o arquivamento de expansão automática para usuários específicos.

- A caixa de correio de arquivo morto de um usuário precisa ser habilitada para que você possa habilitar o arquivamento de expansão automática. Um usuário deve receber uma licença do Plano 2 do Exchange Online para habilitar a caixa de correio de arquivo morto. Se um usuário receber uma licença do Plano 1 do Exchange Online, você terá que atribuir uma licença Arquivamento do Exchange Online separada para habilitar sua caixa de correio de arquivo morto. Consulte [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md).

- Você também pode usar o PowerShell para habilitar caixas de correio de arquivo morto. Consulte a [seção Mais informações](#more-information) para obter um exemplo do comando do PowerShell que você pode usar para habilitar caixas de correio de arquivo morto para todos os usuários em sua organização.

- A expansão automática do arquivamento também oferece suporte às caixas de correio compartilhadas. Para habilitar o arquivo morto para uma caixa de correio compartilhada, uma licença do Plano 2 do Exchange Online ou uma licença do Plano 1 do Exchange Online com uma Arquivamento do Exchange Online é necessária.

- O arquivamento de expansão automática impede que você recupere ou restaurá uma [caixa de correio inativa.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) Isso significa que, se você habilitar o arquivamento de expansão automática para uma caixa de [](recover-an-inactive-mailbox.md) correio e a caixa de correio for inativa em uma data posterior, não será possível recuperar a caixa de correio inativa (convertendo-a em uma caixa de correio ativa) ou restaurá-la [(mesclando](restore-an-inactive-mailbox.md) o conteúdo a uma caixa de correio existente). Se o arquivamento de expansão automática estiver habilitado em uma caixa de correio inativa, a única maneira de recuperar dados é usando a ferramenta de pesquisa de conteúdo no centro de conformidade do Microsoft 365 para exportar os dados da caixa de correio e importar para outra caixa de correio. Para obter mais informações, consulte a seção "Caixas de correio inativas e arquivos de expansão automática" em [Overview of inactive mailboxes](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).

- Não é possível usar o Centro de administração do Exchange ou o Centro de Conformidade & segurança para habilitar o arquivamento de expansão automática. Você precisa usar o PowerShell do Exchange Online. Para se conectar à sua organização do Exchange Online usando o PowerShell remoto, consulte [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitar o arquivamento de expansão automática para toda a sua organização

Você pode habilitar o arquivamento de expansão automática para toda a sua organização. Depois de ativá-lo, o arquivamento de expansão automática será habilitado para caixas de correio de usuário existentes e para novas caixas de correio de usuário criadas. Ao criar caixas de correio de usuário, certifique-se de habilitar a caixa de correio de arquivo morto principal do usuário para que o recurso de arquivamento de expansão automática funcione para a nova caixa de correio do usuário.
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para toda a sua organização.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitar o arquivamento de expansão automática para usuários específicos

Em vez de habilitar o arquivamento de expansão automática para cada usuário em sua organização, você pode habilita-lo somente para usuários específicos. Você pode fazer isso porque apenas alguns usuários podem ter uma necessidade de uma grande capacidade de armazenamento de arquivo morto.
  
Quando você habilita o arquivamento de expansão automática para um usuário específico e a caixa de correio do usuário em espera ou atribuída a uma política de retenção, as duas configurações a seguir são feitas:
  
- A cota de armazenamento da caixa de correio de arquivo morto principal do usuário é aumentada em 10 GB (de 100 GB para 110 GB). A cota de aviso de arquivo morto também é aumentada em 10 GB (de 90 GB para 100 GB).

- A cota de armazenamento para a pasta Itens Recuperáveis na caixa de correio principal do usuário é aumentada em 10 GB (também de 100 GB para 110 GB). A cota de aviso de Itens Recuperáveis também é aumentada em 10 GB (de 90 GB para 100 GB). Essas alterações só serão aplicáveis se a caixa de correio em espera ou atribuída a uma política de retenção.

Esse espaço adicional é adicionado para evitar quaisquer problemas de armazenamento que possam ocorrer antes que o arquivo morto de expansão automática seja provisionado. O espaço de  *armazenamento adicional não é*  adicionado quando você habilita o arquivamento de expansão automática para toda a sua organização, conforme descrito na seção anterior.
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para um usuário específico. Conforme explicado anteriormente, a caixa de correio de arquivo morto do usuário (arquivo morto principal) deve ser habilitada para que você possa ativar o arquivamento de expansão automática para esse usuário.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> Em uma implantação híbrida do Exchange, você não pode usar o comando **Enable-Mailbox -AutoExpandingArchive** para habilitar o arquivamento de expansão automática para um usuário específico cuja caixa de correio principal é local e cuja caixa de correio de arquivo morto é baseada em nuvem. Para habilitar o arquivamento de expansão automática para caixas de correio de arquivo morto baseadas em nuvem em uma implantação híbrida do Exchange, você precisa executar o comando **Set-OrganizationConfig -AutoExpandingArchive** no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para toda a organização. Se as caixas de correio primárias e de arquivo morto de um usuário são baseadas em nuvem, você pode usar o comando **Enable-Mailbox -AutoExpandingArchive** para habilitar o arquivamento de expansão automática para esse usuário específico.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Verifique se o arquivamento de expansão automática está habilitado

Para verificar se o arquivamento de expansão automática está habilitado para sua organização, execute o seguinte comando no PowerShell do Exchange Online.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Um valor de indica que o arquivamento de expansão  `True` automática está habilitado para a organização. 
  
Para verificar se o arquivamento de expansão automática está habilitado para um usuário específico, execute o seguinte comando no PowerShell do Exchange Online.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Um valor de indica que o arquivamento de expansão  `True` automática está habilitado para o usuário.
  
Para determinar se o arquivamento de expansão automática está habilitado para caixas de correio inativas, execute o seguinte comando no PowerShell do Exchange Online.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Um valor de indica que o arquivamento de expansão automática está habilitado para a  `True` caixa de correio inativa. Um valor de indica que o arquivamento de expansão `False` automática não está habilitado.

Lembre-se das seguintes coisas depois de habilitar o arquivamento de expansão automática:
  
- Se você executar o comando **Set-OrganizationConfig -AutoExpandingArchive** para habilitar o arquivamento de expansão automática para sua organização, não será preciso executar **Enable-Mailbox -AutoExpandingArchive** em caixas de correio individuais. Executar o cmdlet **Set-OrganizationConfig** para habilitar o arquivamento de expansão automática para sua organização não altera a propriedade  *AutoExpandingArchiveEnabled*  em caixas de correio de usuário para `True` .

- Da mesma forma, os valores das propriedades de caixa de correio  *ArchiveQuota*  e  *ArchiveWarningQuota*  não são alterados quando você habilita o arquivamento de expansão automática. Na verdade, quando você habilita o arquivamento de expansão automática para uma caixa de correio de usuário e a  *propriedade AutoExpandingArchiveEnabled*  é definida como , as propriedades  `True`  *ArchiveQuota*  e  *ArchiveWarningQuota*  são ignoradas. Veja um exemplo dessas propriedades de caixa de correio após o arquivamento de expansão automática ser habilitado para a caixa de correio de um usuário. 

    ![As propriedades ArchiveQuota e ArchiveWarningQuota são ignoradas depois que você habilita o arquivamento de expansão automática](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Mais informações

- Você também pode usar o PowerShell para habilitar caixas de correio de arquivo morto. Por exemplo, você pode executar o seguinte comando no PowerShell do Exchange Online para habilitar caixas de correio de arquivo morto para todos os usuários cuja caixa de correio de arquivo morto ainda não está habilitada.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Depois de ativar o arquivamento de expansão automática para sua organização ou para um usuário específico, uma caixa de correio de arquivo morto é convertida em um arquivo morto em expansão automática quando a caixa de correio de arquivo morto (incluindo a pasta Itens Recuperáveis) atinge 90 GB. Pode levar até 30 dias para que o espaço de armazenamento adicional seja provisionado.

- Depois de ativar o arquivamento de expansão automática, ele não poderá ser desligado. Além disso, os administradores não podem ajustar a cota de armazenamento para arquivamento de expansão automática.

- O arquivamento de expansão automática é suportado para caixas de correio de arquivo morto baseadas em nuvem em uma implantação híbrida do Exchange para usuários que têm uma caixa de correio primária local. No entanto, depois que o arquivamento de expansão automática for habilitado para uma caixa de correio de arquivo morto baseada em nuvem, você não poderá desembucar essa caixa de correio de arquivo morto de volta para a organização local do Exchange. O arquivamento de expansão automática não é suportado para caixas de correio locais em nenhuma versão do Exchange Server.

- Para obter uma lista de clientes do Outlook que os usuários podem usar para acessar itens na área de armazenamento adicional em sua caixa de correio de arquivo morto, consulte a seção "Requisitos do Outlook para acessar itens em um arquivo morto expandido automaticamente" em [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).

- Conforme explicado anteriormente, 10 GB é adicionado à cota de armazenamento da caixa de correio de arquivo morto principal do usuário (e à pasta Itens Recuperáveis se a caixa de correio estiver em espera) ao executar o comando **Enable-Mailbox -AutoExpandingArchive.** Isso fornece armazenamento adicional até que o espaço de armazenamento expandido automaticamente seja provisionado (o que pode levar até 30 dias). Esse espaço de armazenamento adicional não é adicionado quando você executar **o Set-OrganizationConfig -AutoExpandingArchive** para habilitar o arquivamento de expansão automática para todas as caixas de correio em sua organização. Se você habilitar o arquivamento de expansão automática para toda a organização, mas precisar adicionar os 10 GB adicionais de espaço de armazenamento para um usuário específico, você poderá executar o comando **Enable-Mailbox -AutoExpandingArchive** nessa caixa de correio. Você receberá um erro dizendo que o arquivamento de expansão automática já foi habilitado, mas o espaço de armazenamento adicional será adicionado à caixa de correio.

> [!IMPORTANT]
> O arquivamento de expansão automática só é suportado para caixas de correio usadas para usuários individuais ou caixas de correio compartilhadas com uma taxa de crescimento que não exceda 1 GB por dia. O uso de regras de arquivamento no diário, regras de transporte ou encaminhamento automático para copiar mensagens para uma caixa de correio de arquivo morto para fins de arquivamento não é permitido. A caixa de correio de arquivo morto de um usuário destina-se somente a esse usuário. A Microsoft reserva o direito de negar o arquivamento ilimitado em situações onde a caixa de correio de arquivo morto do usuário é usada para armazenar dados de arquivo morto de outros usuários.
