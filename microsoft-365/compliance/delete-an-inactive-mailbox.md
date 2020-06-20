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
description: Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, você poderá excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817890"
---
# <a name="delete-an-inactive-mailbox"></a>Excluir uma caixa de correio inativa

Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização. Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa, você poderá excluir permanentemente a caixa de correio inativa, removendo a isenção. Além disso, é possível que várias isenções possam ser colocadas em uma caixa de correio inativa. Por exemplo, uma caixa de correio inativa pode ser colocada em retenção de litígio e em uma ou mais suspensões in-loco. Além disso, uma política de retenção (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa. Você deve remover todas as políticas de retenção e retenção de uma caixa de correio inativa para excluí-la. Após remover as políticas de retenção e retenção, a caixa de correio inativa é marcada para exclusão e excluída permanentemente após ser processada.
  
> [!IMPORTANT]
> Como continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange. Isso significa que você deve usar as políticas de retenção e retenção de litígio para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos bloqueios in-loco no Exchange Online. Mas você ainda poderá alterar a duração da retenção de um bloqueio in-loco colocado em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da retenção. Você só poderá excluir uma caixa de correio inativa removendo o bloqueio in-loco. As caixas de correio inativas existentes que estão no bloqueio in-loco ainda serão preservadas até que a retenção seja removida. Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
Consulte a seção [mais informações](#more-information) para obter uma descrição do que acontece depois que as retenções são removidas de uma caixa de correio inativa.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Antes de excluir uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para remover uma retenção de litígio de uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Você pode usar o PowerShell do Exchange Online ou o Eat para remover um bloqueio in-loco de uma caixa de correio inativa. 
    
- Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a retenção e excluir uma caixa de correio inativa. Para obter detalhes, consulte [restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md).
    
- Se você remover a política de retenção ou isenção de uma caixa de correio inativa e o período de retenção de caixa de correio de exclusão reversível da caixa de correio tiver expirado, a caixa de correio será excluída permanentemente. Depois que ele é excluído, ele não pode ser recuperado. Antes de remover a retenção, certifique-se de que você não precisa mais do conteúdo na caixa de correio. Se você quiser reativar uma caixa de correio inativa, é possível recuperá-la. Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).
    
- Para obter mais informações sobre caixas de correio inativas, consulte [inativa caixas de correio no Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Etapa 1: identificar as isenções em uma caixa de correio inativa

Conforme mencionado anteriormente, uma retenção de litígio, um bloqueio in-loco ou uma política de retenção pode ser colocada em uma caixa de correio inativa. A primeira etapa é identificar as isenções em uma caixa de correio inativa.
  
Execute o seguinte comando para exibir as informações de retenção de todas as caixas de correio inativas em sua organização.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

O valor de **true** para a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em retenção de litígio. Se um bloqueio in-loco for colocado em uma caixa de correio inativa, o GUID da retenção será exibido como o valor da propriedade **InPlaceHolds** . Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma retenção de litígio é colocada em Ana Beebe e que duas isenções in-loco são colocadas na Pilar Fernandes. 
  
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
> Se uma grande quantidade de bloqueios in-loco for colocada em uma caixa de correio inativa, nem todos os GUIDs de bloqueio in-loco serão exibidos. Você pode executar o seguinte comando para exibir todos os GUIDs de bloqueio in-loco:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Etapa 2: remover uma retenção de uma caixa de correio inativa

Depois de identificar o tipo de retenção que é colocado na caixa de correio inativa (e se há várias isenções), a próxima etapa é remover as isenções da caixa de correio. Conforme mencionado anteriormente, você deve remover todas as isenções para excluir permanentemente uma caixa de correio inativa. 
  
### <a name="remove-a-litigation-hold"></a>Remover uma retenção de litígio

Conforme mencionado anteriormente, você precisa usar o Windows PowerShell para remover uma retenção de litígio de uma caixa de correio inativa. Você não pode usar o Eat. Execute o comando a seguir para remover uma retenção de litígio.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> A melhor maneira de identificar uma caixa de correio inativa é usando seu nome distinto ou valor de GUID do Exchange. O uso de um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 
  
### <a name="remove-in-place-holds"></a>Remover bloqueios in-loco

 Há duas maneiras de remover um bloqueio in-loco de uma caixa de correio inativa: 
  
- **Excluir o objeto bloqueio in-loco** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem de um bloqueio in-loco, você pode simplesmente excluir o objeto de bloqueio in-loco. 
    
    > [!NOTE]
    > Você precisa desabilitar a retenção antes de excluir um objeto de bloqueio in-loco. Se você tentar excluir um objeto de bloqueio in-loco com a retenção habilitada, receberá uma mensagem de erro. 
  
- **Remover a caixa de correio inativa como uma caixa de correio de origem de um bloqueio in-loco** Se quiser reter outras caixas de correio de origem para um bloqueio in-loco, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto bloqueio in-loco. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Use o Eat para excluir um bloqueio in-loco

1. Se você souber o nome do bloqueio in-loco que deseja excluir, poderá ir para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco que é colocado na caixa de correio inativa que você deseja excluir permanentemente. Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. No Eat, vá para **Gerenciamento de conformidade** e \> **descoberta eletrônica in &amp; -loco**.
    
3. Selecione o bloqueio in-loco que você deseja excluir e, em seguida, clique em **Editar** ![ ícone de edição ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. Na página Propriedades **de &amp; retenção de descoberta eletrônica in-loco** , clique **em bloqueio in-loco**, desmarque a caixa **fazer o conteúdo que corresponde à consulta de pesquisa em caixas de correio selecionadas em retenção** e clique em **salvar**.
    
5. Na página ** &amp; bloqueio de descoberta eletrônica in-loco** , selecione o bloqueio in-loco novamente e clique em **excluir** ![ excluir ícone ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .
    
6. No aviso, clique em **Sim** para excluir o bloqueio in-loco. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Usar o PowerShell do Exchange Online para excluir um bloqueio in-loco

1. Crie uma variável que contenha as propriedades do bloqueio in-loco que você deseja excluir. Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Desabilite o bloqueio no bloqueio in-loco.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Exclua o bloqueio in-loco.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Use o Eat para remover uma caixa de correio inativa de um bloqueio in-loco

1. Se você souber o nome do bloqueio in-loco colocado na caixa de correio inativa, poderá ir para a próxima etapa. Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco colocado na caixa de correio. Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. No Eat, vá para **Gerenciamento de conformidade** e \> **descoberta eletrônica in &amp; -loco**.
    
3. Selecione o bloqueio in-loco que é colocado na caixa de correio inativa e, em seguida, clique em **Editar** ![ ícone de edição ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. Na página Propriedades **de &amp; retenção de descoberta eletrônica in-loco** , clique em **fontes**.
    
5. Na lista de caixas de correio de origem, clique no nome da caixa de correio inativa que você deseja remover e clique em **remover** ![ Remover ](../media/adf01106-cc79-475c-8673-065371c1897b.gif) .
    
6. Clique em **Salvar** para salvar a alteração. Uma mensagem é exibida dizendo que a operação foi concluída com êxito. 
    
7. Repita as etapas 1 a 6 para remover outros bloqueios in-loco colocados na caixa de correio inativa.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usar o PowerShell do Exchange Online para remover uma caixa de correio inativa de um bloqueio in-loco

Se o bloqueio in-loco contiver um grande número de caixas de correio de origem, é possível que a caixa de correio inativa não seja listada na página **fontes** no Eat. Até 3.000 caixas de correio são exibidas na página **fontes** quando você edita um bloqueio in-loco. Se uma caixa de correio inativa não estiver listada na página **fontes** , você poderá usar o PowerShell do Exchange Online para removê-lo do bloqueio in-loco. 
  
1. Criar uma variável que contém as propriedades do bloqueio in-loco colocado na caixa de correio inativa. Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o bloqueio in-loco. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Observação:** A propriedade *sources* do bloqueio in-loco identifica as caixas de correio de origem por suas propriedades *legacyExchangeDN* . Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *sources* do bloqueio in-loco ajuda a evitar a remoção da caixa de correio errada. Isso também ajuda a evitar problemas se duas caixas de correio tiverem o mesmo alias ou endereço SMTP. 
   
3. Remova a caixa de correio inativa da lista de caixas de correio de origem na variável. Certifique-se de usar o **legacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Por exemplo, o comando a seguir remove a caixa de correio inativa de pilar Fernandes.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem na variável.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. Modificar o bloqueio in-loco com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem para o bloqueio in-loco.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Mais informações

- **Uma caixa de correio inativa é um tipo de caixa de correio excluída por software.** No Exchange Online, uma caixa de correio excluída por software é uma caixa de correio excluída, mas pode ser recuperada dentro de um período de retenção específico. O período de retenção de caixa de correio excluída de forma reversível no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada em até 30 dias após a exclusão reversível. Após 30 dias, uma caixa de correio excluída por software é marcada para exclusão permanente e não pode ser recuperada. 
    
- **O que acontece depois que você remove o bloqueio em uma caixa de correio inativa?** A caixa de correio é tratada como outras caixas de correio excluídas por software e é marcada para exclusão permanente após o período de retenção de caixa de correio de exclusão reversível de 30 dias expirar. Esse período de retenção é iniciado na data em que a caixa de correio foi feita pela primeira vez. Essa data é conhecida como a data de exclusão reversível, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox** . A data de exclusão reversível não é a data na qual você remove a retenção. 
    
- **A caixa de correio inativa é permanentemente excluída imediatamente após a removida?** Se a data de exclusão reversível de uma caixa de correio inativa for mais antiga que 30 dias, a caixa de correio não será excluída permanentemente assim que você remover a retenção. A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez em que for processada. 
    
- **Como o período de retenção de caixa de correio de exclusão reversível afeta caixas de correio inativas?** Se a data de exclusão reversível de uma caixa de correio inativa for superior a 30 dias antes da data em que o bloqueio foi removido, a caixa de correio será marcada para exclusão permanente. Mas, se uma caixa de correio inativa tiver uma data de exclusão reversível nos últimos 30 dias e você remover a retenção, você poderá recuperar a caixa de correio até que o período de retenção de caixa de correio de exclusão reversível expire. Para obter detalhes, consulte [excluir ou restaurar caixas de correio do usuário no Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Depois que o período de retenção de caixa de correio excluída por software expirar, você seguirá os procedimentos para recuperar uma caixa de correio inativa. Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).
    
- **Como exibir informações sobre uma caixa de correio inativa depois que a retenção for removida?** Depois que uma retenção for removida e a caixa de correio inativa for revertida para uma caixa de correio excluída por software, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox** . Mas você pode exibir informações sobre a caixa de correio usando o comando **Get-Mailbox-SoftDeletedMailbox** . Por exemplo: 
    
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

  No exemplo acima, a propriedade *WhenSoftDeleted* identifica a data de exclusão reversível, que neste exemplo é 30 de outubro de 2014. Se esta caixa de correio excluída por software anteriormente era uma caixa de correio inativa para a qual a retenção foi removida, ela será excluída permanentemente 30 dias após o valor da propriedade *WhenSoftDeleted* . Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.

