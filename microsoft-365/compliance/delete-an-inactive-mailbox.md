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
description: Quando você não precisar mais preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, poderá excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 0e5a56fce7f41b0c3b30e56aefbaae0593470756
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423208"
---
# <a name="delete-an-inactive-mailbox"></a>Excluir uma caixa de correio inativa

Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização. Quando você não precisa mais preservar o conteúdo de uma caixa de correio inativa, você pode excluir permanentemente a caixa de correio inativa removendo a espera. Além disso, é possível que vários retém possam ser colocados em uma caixa de correio inativa. Por exemplo, uma caixa de correio inativa pode ser colocada em Contencioso e em um ou mais In-Place Holds. Além disso, uma política de retenção (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa. Você precisa remover todas as políticas de retenção e retenção de uma caixa de correio inativa para excluí-la. Depois de remover as políticas de retenção e retenção, a caixa de correio inativa será marcada para exclusão e será excluída permanentemente depois de processada.
  
> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ress contração de In-Place no Centro de administração do Exchange. Isso significa que você deve usar as Políticas de Retenção e Retenção de Litígio para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos In-Place no Exchange Online. Mas você ainda poderá alterar a duração de espera de uma In-Place de espera colocada em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera. Você só poderá excluir uma caixa de correio inativa removendo o In-Place Hold. As caixas de correio inativas existentes que estão em In-Place de espera ainda serão preservadas até que a espera seja removida. Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)
  
Consulte a [seção Mais informações](#more-information) para obter uma descrição do que acontece após a remoção de retém de uma caixa de correio inativa.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Antes de excluir uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para remover uma Moção de Litígio de uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a espera e excluir uma caixa de correio inativa. Para obter detalhes, [consulte Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).

- Se você remover a política de retenção ou retenção de uma caixa de correio inativa e o período de retenção de caixa de correio excluída pela caixa de correio tiver expirado, a caixa de correio será excluída permanentemente. Depois que ele é excluído, ele não pode ser recuperado. Antes de remover a espera, certifique-se de não precisar mais do conteúdo na caixa de correio. Se você quiser reativar uma caixa de correio inativa, poderá recuperá-la. Para obter detalhes, [consulte Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- Para obter mais informações sobre caixas de correio inativas, consulte Caixas de correio [inativas no Office 365](inactive-mailboxes-in-office-365.md).

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Etapa 1: identificar os retém em uma caixa de correio inativa

Como mencionado anteriormente, uma retenção de litígio, In-Place retenção ou política de retenção pode ser colocada em uma caixa de correio inativa. A primeira etapa é identificar os retém em uma caixa de correio inativa.
  
Execute o seguinte comando para exibir as informações de espera de todas as caixas de correio inativas em sua organização.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

O valor **true para** a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em Contencioso. Se um In-Place de espera for colocado em uma caixa de correio inativa, o GUID da responsabilidade será exibido como o valor da **propriedade InPlaceHolds.** Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma Retenção de Litígio é colocada em Ann Beebe e que uma política de retenção e retenção de In-Place é colocada em Pilar Pinilla.
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Se muitas In-Place de retenção ou retenção são colocadas em uma caixa de correio inativa, nem todos os GUIDs de retenção In-Place serão exibidos. Você pode executar o seguinte comando para exibir todos os GUIDs na propriedade InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Para obter mais informações sobre como identificar retém, consulte Como identificar o tipo [de espera colocada em uma caixa de correio](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Etapa 2: Remover uma espera de uma caixa de correio inativa

Depois de identificar qual tipo de espera é colocada na caixa de correio inativa (e se há várias restituições), a próxima etapa é remover as resituções na caixa de correio. Conforme mencionado anteriormente, você precisa remover todas as resvases para excluir permanentemente uma caixa de correio inativa.
  
### <a name="remove-a-litigation-hold"></a>Remover uma moção de litígio

Como mencionado anteriormente, você precisa usar Windows PowerShell remover uma Moção de Litígio de uma caixa de correio inativa. Não é possível usar o EAC. Execute o seguinte comando para remover uma Moção de Litígio.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> A melhor maneira de identificar uma caixa de correio inativa é usando seu valor Distinguished Name ou GUID do Exchange. Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Remover uma caixa de correio inativa de uma política de retenção

O procedimento para remover uma caixa de correio inativa de uma política de retenção do Microsoft 365 depende se a política de retenção atribuída à caixa de correio inativa é de toda a organização ou explícita. no tipo de política de retenção atribuída à caixa de correio inativa.

- Políticas de retenção em toda a organização atribuídas a todas as caixas de correio na organização. Use o cmdlet **Get-OrganizationConfig** no PowerShell do Exchange Online para obter informações sobre políticas de retenção em toda a organização.

- Políticas de retenção de localização específicas atribuídas a caixas de correio específicas. São políticas atribuídas aos locais de conteúdo de usuários específicos. Use o cmdlet **Get-Mailbox -IncludeInactiveMailbox** no PowerShell do Exchange Online para obter informações sobre políticas de retenção atribuídas a caixas de correio inativas específicas.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Remover uma caixa de correio inativa de uma política de retenção em toda a organização

Execute o seguinte comando no PowerShell do Exchange Online para excluir uma caixa de correio inativa de uma política de retenção em toda a organização.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Para obter mais informações que identifiquem políticas de retenção em toda a organização aplicadas a uma caixa de correio inativa e obtenham o GUID de uma política de retenção, consulte [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)seção "Get-OrganizationConfig" em Como identificar o tipo de retenção colocado em uma caixa de correio .

Como alternativa, você pode executar o seguinte comando para remover a caixa de correio inativa de todas as políticas de toda a organização:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Remover uma caixa de correio inativa de uma política de retenção de local específica

Execute o seguinte comando no Centro de Conformidade & Segurança do [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) para remover uma caixa de correio inativa de uma política de retenção explícita.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

Para obter mais informações sobre como identificar políticas de retenção de local específicas aplicadas a uma caixa de correio inativa e obter o GUID de uma política de retenção, consulte [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)seção "Get-Mailbox" em Como identificar o tipo de retenção colocada em uma caixa de correio .

### <a name="remove-in-place-holds"></a>Remover Retenções Locais

 Há duas maneiras de remover um In-Place de uma caixa de correio inativa: 
  
- **Excluir o objeto In-Place Hold** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem para um In-Place de espera, você pode apenas excluir o objeto In-Place Hold. 

    > [!NOTE]
    > Você precisa desabilitar a espera antes de poder excluir um objeto In-Place Hold. Se você tentar excluir um objeto In-Place Hold que tenha a espera habilitada, receberá uma mensagem de erro. 
  
- **Remover a caixa de correio inativa como uma caixa de** correio de origem de um In-Place Hold Se você quiser reter outras caixas de correio de origem para um In-Place, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto In-Place Hold.

#### <a name="delete-an-in-place-hold"></a>Excluir um In-Place de espera

1. Crie uma variável que contenha as propriedades do In-Place que você deseja excluir. Use o GUID In-Place de espera que você obteve na [Etapa 1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identificar os retém em uma caixa de correio inativa .

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Desabilite a espera no In-Place Hold.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Exclua o In-Place de espera.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Remover uma caixa de correio inativa de um In-Place Hold

Se o In-Place hold contiver um grande número de caixas de correio de origem,  é possível que a caixa de correio inativa não seja listada na página Fontes no EAC. Até 3.000 caixas de correio  são exibidas na página Fontes quando você edita um In-Place Hold. Se uma caixa de correio inativa  não estiver listada na página Fontes, você poderá usar o PowerShell do Exchange Online para removê-la do In-Place Hold. 
  
1. Crie uma variável que contenha as propriedades do In-Place hold colocado na caixa de correio inativa. Use o GUID In-Place de espera que você obteve na [Etapa 1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identificar os retém em uma caixa de correio inativa .

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o In-Place Hold. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > A *propriedade Sources* do In-Place Hold identifica as caixas de correio de origem por suas propriedades *LegacyExchangeDN.* Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *Sources* do In-Place Hold ajuda a evitar a remoção da caixa de correio errada. Isso também ajuda a evitar problemas se duas caixas de correio têm o mesmo alias ou endereço SMTP. 

3. Remova a caixa de correio inativa da lista de caixas de correio de origem na variável. Use o **LegacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior. 

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

5. Modifique o In-Place com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem do In-Place Hold.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Mais informações

- **Uma caixa de correio inativa é um tipo de caixa de correio excluída de forma suave.** No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada em um período de retenção específico. O período de retenção de caixa de correio excluído no Exchange Online é de 30 dias. Isso significa que a caixa de correio pode ser recuperada dentro de 30 dias após a exclusão suave. Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada.

- **O que acontece depois de remover a espera em uma caixa de correio inativa?** A caixa de correio é tratada como outras caixas de correio excluídas de forma suave e é marcada para exclusão permanente após o período de retenção de caixa de correio excluído por 30 dias. Esse período de retenção começa na data em que a caixa de correio foi inativa pela primeira vez. Essa data é conhecida como a data excluída de forma suave, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox.** A data excluída de forma suave não é a data em que você remove a espera.

- **Uma caixa de correio inativa será excluída permanentemente imediatamente após a remoção da moção?** Se a data de exclusão suave de uma caixa de correio inativa tiver mais de 30 dias, a caixa de correio não será excluída permanentemente assim que você remover a responsabilidade. A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez que for processada.

- **Como o período de retenção de caixa de correio excluído suave afeta caixas de correio inativas?** Se a data de exclusão suave de uma caixa de correio inativa for superior a 30 dias antes da data em que a remoção foi removida, a caixa de correio será marcada para exclusão permanente. Porém, se uma caixa de correio inativa tiver uma data excluída nos últimos 30 dias e você remover a retenção, poderá recuperar a caixa de correio até que o período de retenção de caixa de correio excluído de forma suave expire. Para obter detalhes, consulte [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes). Depois que o período de retenção de caixa de correio excluído de forma suave expirar, siga os procedimentos para recuperar uma caixa de correio inativa. Para obter detalhes, [consulte Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

- **Como você exibe informações sobre uma caixa de correio inativa após a remoção da moção?** Depois que uma espera é removida e a caixa de correio inativa é revertida de volta para uma caixa de correio excluída de forma suave, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox.** Mas você pode exibir informações sobre a caixa de correio usando o **comando Get-Mailbox -SoftDeletedMailbox.** Por exemplo:

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

  No exemplo acima, a *propriedade WhenSoftDeleted* identifica a data excluída de forma suave, que neste exemplo é 30 de outubro de 2014. Se essa caixa de correio excluída suave anteriormente fosse uma caixa de correio inativa para a qual a responsabilidade foi removida, ela será excluída permanentemente 30 dias após o valor da *propriedade WhenSoftDeleted.* Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.
