---
title: Excluir uma caixa de correio inativa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Quando não precisar mais preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, você poderá excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817890"
---
# <a name="delete-an-inactive-mailbox"></a>Excluir uma caixa de correio inativa

Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização. Quando você não precisar mais preservar o conteúdo de uma caixa de correio inativa, poderá excluir permanentemente a caixa de correio inativa removendo a espera. Além disso, é possível que várias retém sejam colocadas em uma caixa de correio inativa. Por exemplo, uma caixa de correio inativa pode ser colocada em Litígio e em um ou mais In-Place Retém. Além disso, uma política de retenção (criada no centro de conformidade e segurança no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa. Você precisa remover todas as retenções e políticas de retenção de uma caixa de correio inativa para excluí-la. Depois de remover as retenções e as políticas de retenção, a caixa de correio inativa é marcada para exclusão e é excluída permanentemente depois de processada.
  
> [!IMPORTANT]
> À medida que continuamos investindo em maneiras diferentes de preservar o conteúdo da caixa de correio, anunciamos a ressarção do In-Place retém no Centro de administração do Exchange. Isso significa que você deve usar Retenções de Litígio e políticas de retenção para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos In-Place retém no Exchange Online. Mas você ainda poderá alterar a duração da espera de uma In-Place colocada em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera. Você só poderá excluir uma caixa de correio inativa removendo o In-Place Remoção. Caixas de correio inativas existentes que estão In-Place remoção ainda serão preservadas até que a iseção seja removida. Para obter mais informações sobre a baixa In-Place, consulte a Baixa das ferramentas de [Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
Consulte a [seção Mais informações](#more-information) para obter uma descrição do que acontece após remoção de uma caixa de correio inativa.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Antes de excluir uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para remover uma Moção de Litígio de uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Você pode usar o PowerShell do Exchange Online ou o EAC para remover um In-Place de uma caixa de correio inativa. 
    
- Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a espera e excluir uma caixa de correio inativa. Para obter detalhes, [consulte Restaurar uma caixa de correio inativa no Office 365.](restore-an-inactive-mailbox.md)
    
- Se você remover a política de retenção ou retenção de uma caixa de correio inativa e o período de retenção de caixa de correio excluída de forma flexível da caixa de correio tiver expirado, a caixa de correio será excluída permanentemente. Depois que ele é excluído, ele não pode ser recuperado. Antes de remover a espera, certifique-se de não precisar mais do conteúdo na caixa de correio. Se você quiser reativar uma caixa de correio inativa, poderá recuperá-la. Para obter detalhes, [consulte Recuperar uma caixa de correio inativa no Office 365.](recover-an-inactive-mailbox.md)
    
- Para saber mais sobre caixas de correio inativas, confira Caixas de correio [inativas no Office 365.](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Etapa 1: Identificar os retém em uma caixa de correio inativa

Conforme mencionado anteriormente, uma retenção de litígio, In-Place retenção ou política de retenção pode ser colocada em uma caixa de correio inativa. A primeira etapa é identificar os retém em uma caixa de correio inativa.
  
Execute o seguinte comando para exibir as informações de espera para todas as caixas de correio inativas em sua organização.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

O valor True **para** a **propriedade LitigationHoldEnabled** indica que a caixa de correio inativa está em Litígio. Se um In-Place De espera for colocado em uma caixa de correio inativa, o GUID da iseção será exibido como o valor da **propriedade InPlaceHolds.** Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma Responsabilidade de Litígio é colocada em Ann Beebe e que dois In-Place Reter são colocados em Pilar Pinilla. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Se muitos In-Place retém são colocados em uma caixa de correio inativa, nem todos os GUIDs de In-Place de espera serão exibidos. Você pode executar o seguinte comando para exibir todos os GUIDs de In-Place de espera:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Etapa 2: Remover uma espera de uma caixa de correio inativa

Depois de identificar que tipo de espera é colocada na caixa de correio inativa (e se há várias retém), a próxima etapa é remover os retém na caixa de correio. Conforme mencionado anteriormente, você precisa remover todas as retém para excluir permanentemente uma caixa de correio inativa. 
  
### <a name="remove-a-litigation-hold"></a>Remover uma moção de litígio

Conforme mencionado anteriormente, você precisa usar o Windows PowerShell para remover uma Moção de Litígio de uma caixa de correio inativa. Você não pode usar o EAC. Execute o seguinte comando para remover uma Moção de Litígio.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> A melhor maneira de identificar uma caixa de correio inativa é usando o nome diferenciado ou o valor guid do Exchange. Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 
  
### <a name="remove-in-place-holds"></a>Remover Retenções Locais

 Há duas maneiras de remover um In-Place de uma caixa de correio inativa: 
  
- **Excluir o In-Place objeto Hold** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem para um In-Place, você pode apenas excluir o objeto In-Place De espera. 
    
    > [!NOTE]
    > Você precisa desabilitar a espera antes de excluir um objeto In-Place Hold. Se você tentar excluir um objeto In-Place Hold que tenha a espera habilitada, você receberá uma mensagem de erro. 
  
- **Remover a caixa de correio inativa como uma caixa de correio de origem de um In-Place Espera** Se quiser reter outras caixas de correio de origem para um In-Place, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto In-Place Retenção. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Usar o EAC para excluir uma In-Place Segura

1. Se você sabe o nome do In-Place que deseja excluir, vá para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do In-Place Que é colocado na caixa de correio inativa que você deseja excluir permanentemente. Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. No EAC, vá para **Gerenciamento de Conformidade** \> **eDiscovery Hold in-loco. &amp;**
    
3. Selecione o In-Place que você deseja excluir e clique em **Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ícone.
    
4. Na página de propriedades do **In-Place eDiscovery &amp; Hold,**  clique em **In-Place Hold**, desmarque o conteúdo Local correspondente à consulta de pesquisa em caixas de correio selecionadas em espera e clique em **Salvar**.
    
5. Na página **In-Place eDiscovery &amp; Hold,** selecione o In-Place Recluso e clique em **Excluir** ![ ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ícone.
    
6. No aviso, clique em **Sim** para excluir a In-Place Segura. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Usar o PowerShell do Exchange Online para excluir uma In-Place Segura

1. Crie uma variável que contenha as propriedades do In-Place Hold que você deseja excluir. Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Desabilite a espera no In-Place Desem espera.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Exclua a In-Place Segura.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usar o EAC para remover uma caixa de correio inativa de um In-Place Espera

1. Se você sabe o nome do In-Place que é colocado na caixa de correio inativa, você pode ir para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do In-Place De espera colocado na caixa de correio. Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. No EAC, vá para **Gerenciamento de Conformidade** \> **eDiscovery Hold in-loco. &amp;**
    
3. Selecione o In-Place Que é colocado na caixa de correio inativa e clique em **Editar** ![ ícone ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. Na página **de propriedades do In-Place eDiscovery &amp; Hold,** clique em **Fontes**.
    
5. Na lista de caixas de correio de origem, clique no nome da caixa de correio inativa que você deseja remover e clique no ícone ![ Remover. ](../media/adf01106-cc79-475c-8673-065371c1897b.gif)
    
6. Clique em **Salvar** para salvar a alteração. Uma mensagem é exibida dizendo que a operação foi concluída com êxito. 
    
7. Repita as etapas 1 a 6 para remover In-Place Retém colocadas na caixa de correio inativa.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usar o PowerShell do Exchange Online para remover uma caixa de correio inativa de um In-Place Espera

Se o In-Place de correio contiver um grande número de caixas de correio de origem, é possível que a caixa de correio inativa não seja listada na página Fontes do EAC.  Até 3.000 caixas de correio  são exibidas na página Fontes quando você edita um In-Place Espera. Se uma caixa de correio inativa  não estiver listada na página Fontes, você poderá usar o PowerShell do Exchange Online para removê-la do In-Place Espera. 
  
1. Crie uma variável que contenha as propriedades do In-Place colocado na caixa de correio inativa. Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o In-Place Espera. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Observação:** A *propriedade Sources* do In-Place Hold identifica as caixas de correio de origem por suas propriedades *LegacyExchangeDN.* Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *Sources* do In-Place Hold ajuda a evitar a remoção da caixa de correio errada. Isso também ajuda a evitar problemas se duas caixas de correio têm o mesmo alias ou endereço SMTP. 
   
3. Remova a caixa de correio inativa da lista de caixas de correio de origem na variável. Certifique-se de usar **o LegacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Por exemplo, o comando a seguir remove a caixa de correio inativa de Pilar Pinilla.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem na variável.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. Modifique o In-Place Com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem do In-Place Espera.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Mais informações

- **Uma caixa de correio inativa é um tipo de caixa de correio excluída de forma flexível.** No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada dentro de um período de retenção específico. O período de retenção de caixa de correio excluída de forma suave no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada dentro de 30 dias após a exclusão suave. Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada. 
    
- **O que acontece depois que você remove a espera em uma caixa de correio inativa?** A caixa de correio é tratada como outras caixas de correio excluídas de forma suave e é marcada para exclusão permanente após o período de retenção de caixa de correio excluída por 30 dias. Esse período de retenção começa na data em que a caixa de correio foi inativa pela primeira vez. Essa data é conhecida como a data de exclusão suave, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox.** A data de exclusão suave não é a data em que você remove a espera. 
    
- **Uma caixa de correio inativa é excluída permanentemente imediatamente após a remoção da espera?** Se a data de exclusão flexível de uma caixa de correio inativa tiver mais de 30 dias, ela não será excluída permanentemente assim que você remover a espera. A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez que for processada. 
    
- **Como o período de retenção de caixa de correio excluída de forma flexível afeta as caixas de correio inativas?** Se a data de exclusão flexível de uma caixa de correio inativa for superior a 30 dias antes da data em que o espera foi removido, a caixa de correio será marcada para exclusão permanente. Mas se uma caixa de correio inativa tiver uma data de exclusão flexível nos últimos 30 dias e você remover a retenção, poderá recuperar a caixa de correio até que o período de retenção da caixa de correio excluída de forma flexível expire. Para obter detalhes, consulte [Excluir ou restaurar caixas de correio do usuário no Exchange Online.](https://go.microsoft.com/fwlink/?linkid=856835) Depois que o período de retenção de caixa de correio excluída de forma flexível expirar, você seguirá os procedimentos para recuperar uma caixa de correio inativa. Para obter detalhes, [consulte Recuperar uma caixa de correio inativa no Office 365.](recover-an-inactive-mailbox.md)
    
- **Como exibir informações sobre uma caixa de correio inativa após a remoção da espera?** Depois que uma espera é removida e a caixa de correio inativa é revertida de volta para uma caixa de correio excluída de forma reversida, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox.** Mas você pode exibir informações sobre a caixa de correio usando o **comando Get-Mailbox -SoftDeletedMailbox.** Por exemplo: 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  No exemplo acima, a propriedade *WhenSoftDeleted* identifica a data de exclusão suave, que neste exemplo é 30 de outubro de 2014. Se essa caixa de correio excluída por software anteriormente era uma caixa de correio inativa para a qual a espera foi removida, ela será excluída permanentemente 30 dias após o valor da propriedade *WhenSoftDeleted.* Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.

