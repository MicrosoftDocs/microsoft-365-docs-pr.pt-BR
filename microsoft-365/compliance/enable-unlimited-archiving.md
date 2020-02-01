---
title: Habilitar o arquivamento ilimitado no Office 365 — ajuda do administrador
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
description: 'Para administradores: saiba como habilitar o arquivamento de expansão automática no Office 365, que fornece aos usuários um armazenamento ilimitado para suas caixas de correio do Exchange Online. Você pode habilitar o arquivamento de expansão automática para toda a sua organização ou apenas para usuários específicos.'
ms.openlocfilehash: d37243c65770ff7bbcce4cbe4cfd593b68b7a869
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593202"
---
# <a name="enable-unlimited-archiving-in-office-365--admin-help"></a>Habilitar o arquivamento ilimitado no Office 365 — ajuda do administrador

Você pode usar o recurso de arquivamento de expansão automática do Exchange Online no Office 365 para habilitar o espaço de armazenamento ilimitado para caixas de correio de arquivo morto. Quando o arquivamento de expansão automática está ativado, o espaço de armazenamento adicional é automaticamente adicionado à caixa de correio de arquivo morto de um usuário quando se aproxima do limite de armazenamento. O resultado é a capacidade de armazenamento de caixa de correio ilimitada. Você pode ativar o arquivamento de expansão automática para todos em sua organização ou apenas para usuários específicos. Para obter mais informações sobre o arquivamento de expansão automática, consulte [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global em sua organização do Office 365 ou um membro do grupo de função gerenciamento da organização em sua organização do Exchange Online para habilitar o arquivamento de expansão automática para toda a sua organização ou para usuários específicos. Como alternativa, você precisa ser um membro de um grupo de função atribuído à função de destinatários de email para habilitar o arquivamento de expansão automática para usuários específicos.
    
- A caixa de correio de arquivo morto de um usuário deve ser habilitada para que você possa habilitar o arquivamento de expansão automática. Um usuário deve receber uma licença do Exchange Online Plan 2 para habilitar a caixa de correio de arquivo morto. Se um usuário for atribuído a uma licença do Exchange Online Plan 1, você precisará atribuí-los uma licença de arquivamento do Exchange Online separada para habilitar a caixa de correio de arquivo morto. Consulte [habilitar caixas de correio de arquivo morto no centro de conformidade de & de segurança](enable-archive-mailboxes.md).
    
- Você também pode usar o PowerShell para habilitar caixas de correio de arquivo morto. Consulte a seção [mais informações](#more-information) para obter um exemplo do comando do PowerShell que você pode usar para habilitar caixas de correio de arquivo morto para todos os usuários em sua organização. 
    
- A expansão automática do arquivamento também oferece suporte às caixas de correio compartilhadas. Para habilitar o arquivo morto para uma caixa de correio compartilhada, uma licença do Exchange Online Plan 2 ou uma licença do plano 1 do Exchange Online com uma licença de arquivamento do Exchange Online é necessária.
    
- Você não pode usar o centro de administração do Exchange ou o centro de conformidade de & de segurança para habilitar o arquivamento de expansão automática. Você precisa usar o PowerShell do Exchange Online. Para se conectar à sua organização do Exchange Online usando o PowerShell remoto, confira [conectar-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Habilitar o arquivamento de expansão automática para toda a sua organização

Você pode habilitar o arquivamento de expansão automática para toda a sua organização. Depois que você ativá-la, o arquivamento de expansão automática será habilitado para caixas de correio de usuário existentes e para novas caixas de correio de usuário criadas. Ao criar caixas de correio de usuário, certifique-se de habilitar a caixa de correio de arquivo morto principal do usuário para que o recurso de arquivamento de expansão automática funcione para a nova caixa de correio de usuário.
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Execute o seguinte comando no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para toda a sua organização.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Habilitar o arquivamento de expansão automática para usuários específicos

Em vez de habilitar o arquivamento de expansão automática para cada usuário em sua organização, você pode habilitá-lo somente para usuários específicos. Você pode fazer isso porque apenas alguns usuários podem precisar de uma grande capacidade de armazenamento de arquivo morto.
  
Quando você habilita o arquivamento de expansão automática para um usuário específico e a caixa de correio do usuário em retenção ou atribuído a uma política de retenção do Office 365, as duas alterações de configurações a seguir são feitas:
  
- A cota de armazenamento da caixa de correio de arquivo morto principal do usuário é aumentada em 10 GB (de 100 GB a 110 GB). A cota de aviso de arquivo morto também é aumentada em 10 GB (de 90 GB a 100 GB).
    
- A cota de armazenamento da pasta itens recuperáveis na caixa de correio principal do usuário é aumentada em 10 GB (também de 100 GB a 110 GB). A cota de aviso de itens recuperáveis também é aumentada em 10 GB (de 90 GB a 100 GB). Essas alterações só serão aplicáveis se a caixa de correio estiver em espera ou atribuída a uma política de retenção do Office 365.
    
Esse espaço adicional é adicionado para evitar qualquer problema de armazenamento que possa ocorrer antes de o arquivo morto de expansão automática ser provisionado. Espaço de armazenamento adicional *não é* adicionado quando você habilita o arquivamento de expansão automática para toda a sua organização, conforme descrito na seção anterior. 
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Execute o seguinte comando no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para um usuário específico. Conforme explicado anteriormente, a caixa de correio de arquivo morto do usuário (arquivo principal) deve estar habilitada para que você possa ativar o arquivamento de expansão automática para esse usuário.
    
    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> Em uma implantação híbrida do Exchange, você não pode usar o comando **Enable-Mailbox-AutoExpandingArchive** para habilitar o arquivamento de expansão automática para um usuário específico cuja caixa de correio principal esteja no local e sua caixa de correio de arquivo morto seja baseada na nuvem. Para habilitar o arquivamento de expansão automática para caixas de correio de arquivo morto baseado em nuvem em uma implantação híbrida do Exchange, você precisa executar o comando **Set-OrganizationConfig-AutoExpandingArchive** no PowerShell do Exchange Online para habilitar o arquivamento de expansão automática para toda a organização. Se as caixas de correio principais e de arquivo morto de um usuário forem baseadas em nuvem, você poderá usar o comando **Enable-Mailbox-AutoExpandingArchive** para habilitar o arquivamento de expansão automática para esse usuário específico. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Verificar se o arquivamento de expansão automática está habilitado

Para verificar se o arquivamento de expansão automática está habilitado para sua organização, execute o seguinte comando no PowerShell do Exchange Online.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Um valor `True` indica que o arquivamento de expansão automática está habilitado para a organização. 
  
Para verificar se o arquivamento de expansão automática está habilitado para um usuário específico, execute o seguinte comando no PowerShell do Exchange Online.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Um valor `True` indica que o arquivamento de expansão automática está habilitado para o usuário. 
  
Tenha em mente as seguintes coisas depois de habilitar o arquivamento de expansão automática:
  
- Se você executar o comando **Set-OrganizationConfig-AutoExpandingArchive** para habilitar o arquivamento de expansão automática para sua organização, não será necessário executar o **Enable-Mailbox-AutoExpandingArchive** em caixas de correio individuais. A execução do cmdlet **Set-OrganizationConfig** para habilitar o arquivamento de expansão automática para a sua organização não altera a propriedade *AutoExpandingArchiveEnabled* nas caixas `True`de correio do usuário.
    
- Da mesma forma, os valores das propriedades de caixa de correio *ArchiveQuota* e *ArchiveWarningQuota* não são alterados quando você habilita o arquivamento de expansão automática. Na verdade, quando você habilita o arquivamento de expansão automática para uma caixa de correio ** de usuário e a propriedade `True`AutoExpandingArchiveEnabled é definida como, as propriedades *ArchiveQuota* e *ArchiveWarningQuota* são ignoradas. Veja um exemplo dessas propriedades de caixa de correio após o arquivamento de expansão automática estar habilitado para a caixa de correio de um usuário. 
    
    ![As propriedades ArchiveQuota e ArchiveWarningQuota são ignoradas após você habilitar o arquivamento de expansão automática](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Mais informações

- Você também pode usar o PowerShell para habilitar caixas de correio de arquivo morto. Por exemplo, você pode executar o seguinte comando no PowerShell do Exchange Online para habilitar caixas de correio de arquivo morto para todos os usuários cuja caixa de correio de arquivo morto ainda não esteja habilitada.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Depois que você ativar o arquivamento de expansão automática para sua organização ou para um usuário específico, uma caixa de correio de arquivo morto será convertida em um arquivo morto de expansão automática quando a caixa de correio de arquivo morto (incluindo a pasta itens recuperáveis) atingir 90 GB. Pode levar até 30 dias para que o espaço de armazenamento adicional seja provisionado.
    
- Após ativar o arquivamento de expansão automática, não é possível desativá-la.
    
- O arquivamento de expansão automática é suportado para caixas de correio de arquivo morto baseadas em nuvem em uma implantação híbrida do Exchange para usuários que tenham uma caixa de correio primária local. No entanto, após o arquivamento de expansão automática ser habilitado para uma caixa de correio de arquivo morto baseado em nuvem, não é possível desconectar a caixa de correio de arquivo morto à organização local do Exchange. O arquivamento de expansão automática não tem suporte para caixas de correio locais no Exchange Server 2010.
    
- Para obter uma lista de clientes do Outlook que os usuários podem usar para acessar itens na área de armazenamento adicional em suas caixas de correio de arquivo morto, consulte a seção "requisitos do Outlook para acessar itens em um arquivo expandido automaticamente" em [visão geral de arquivamento ilimitado no Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).
    
- Conforme explicado anteriormente, 10 GB é adicionado à cota de armazenamento da caixa de correio de arquivo morto principal do usuário (e à pasta itens recuperáveis se a caixa de correio estiver em espera) ao executar o comando **Enable-Mailbox-AutoExpandingArchive** . Isso fornece armazenamento adicional até que o espaço de armazenamento expandido automaticamente seja provisionado (o que pode levar até 30 dias). Esse espaço de armazenamento adicional não é adicionado quando você executa o **Set-OrganizationConfig-AutoExpandingArchive** para habilitar o arquivamento de expansão automática para todas as caixas de correio em sua organização. Se você habilitou o arquivamento de expansão automática para toda a organização, mas precisa adicionar 10 GB adicionais de espaço de armazenamento para um usuário específico, é possível executar o comando **Enable-Mailbox-AutoExpandingArchive** nessa caixa de correio. Você receberá um erro informando que o arquivamento de expansão automática já foi habilitado, mas o espaço de armazenamento adicional será adicionado à caixa de correio. 

- Os administradores não podem ajustar a cota de armazenamento.

> [!IMPORTANT]
> O arquivamento de expansão automática só é suportado para caixas de correio usadas para usuários individuais ou caixas de correio compartilhadas com uma taxa de crescimento que não excede 1 GB por dia. O uso de registro no diário, regras de transporte ou regras de encaminhamento automático para copiar mensagens para uma caixa de correio de arquivo morto com a finalidade de arquivamento não é permitido. A caixa de correio de arquivo morto de um usuário destina-se somente a esse usuário. A Microsoft reserva-se o direito de negar o arquivamento ilimitado em casos em que a caixa de correio de arquivo morto de um usuário é usada para armazenar dados de arquivo para outros usuários ou em outros casos de uso inadequado.
