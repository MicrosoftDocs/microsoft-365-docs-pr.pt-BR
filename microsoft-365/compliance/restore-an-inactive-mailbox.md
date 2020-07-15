---
title: Restaurar uma caixa de correio inativa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Saiba como restaurar (ou mesclar) o conteúdo de uma caixa de correio inativa para uma caixa de correio existente no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34965832c32bfd4139f4b9a54d3999313aace476
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127448"
---
# <a name="restore-an-inactive-mailbox"></a>Restaurar uma caixa de correio inativa

Uma caixa de correio inativa (que é um tipo de caixa de correio excluída por software) é usada para manter o email de um funcionário anterior, depois que ele deixa sua organização. Se outro funcionário tomar as responsabilidades do trabalho do funcionário em parte ou se esse funcionário retornar à sua organização, haverá duas maneiras de tornar o conteúdo da caixa de correio inativa disponível para um usuário:
  
- **Restaurar uma caixa de correio inativa** Se outro funcionário assumir as responsabilidades do trabalho do funcionário de parte, ou se outro usuário precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Você também pode restaurar o arquivo morto de uma caixa de correio inativa. Após a restauração, a caixa de correio inativa é preservada e é mantida como uma caixa de correio inativa. Este tópico descreve os procedimentos para restaurar uma caixa de correio inativa.

- **Recuperar uma caixa de correio inativa** Se o funcionário desparter retornar à sua organização ou se um novo funcionário for contratado para realizar as responsabilidades de trabalho do funcionário de parte, você poderá recuperar o conteúdo da caixa de correio inativa. Este método converte a caixa de correio inativa em uma nova caixa de correio que contenha o conteúdo da caixa de correio inativa. Após sua recuperação, a caixa de correio inativa deixa de existir. Para obter os procedimentos passo a passo, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).

Consulte a seção **mais informações** neste artigo para obter mais detalhes sobre as diferenças entre a restauração e a recuperação de uma caixa de correio inativa.
  
## <a name="requirements-to-restore-an-inactive-mailbox"></a>Requisitos para restaurar uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para restaurar uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).

- Execute o seguinte comando no PowerShell do Exchange Online para obter informações de identidade para as caixas de correio inativas em sua organização.

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     Use as informações retornadas por este comando para restaurar uma caixa de correio inativa específica.

- Para obter mais informações sobre caixas de correio inativas, consulte [inativa caixas de correio no Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-an-inactive-mailbox"></a>Restaurar uma caixa de correio inativa

Use o cmdlet **New-MailboxRestoreRequest** com os parâmetros _SourceMailbox_ e _TargetMailbox_ para restaurar o conteúdo de uma caixa de correio inativa para uma caixa de correio existente. Para obter mais informações sobre como usar esse cmdlet, consulte [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. Criar uma variável que contém as propriedades da caixa de correio inativa.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > No comando anterior, use o valor da propriedade **distinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa tenha o mesmo endereço SMTP principal.
  
2. Restaure o conteúdo da caixa de correio inativa para uma caixa de correio existente. O conteúdo da caixa de correio inativa (caixa de correio de origem) será mesclado nas pastas correspondentes da caixa de correio existente (caixa de correio de destino).

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Como alternativa, você pode especificar uma pasta de nível superior na caixa de correio de destino na qual restaurar o conteúdo da caixa de correio inativa. Se a pasta de destino especificada ou a estrutura de pasta de destino ainda não existir na caixa de correio de destino, ela será criada durante o processo de restauração. 

    Este exemplo copia os itens de caixa de correio e subpastas de uma caixa de correio inativa para uma pasta chamada "caixa de correio inativa" na estrutura de pastas de nível superior da caixa de correio de destino.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Restaurar o arquivo morto de uma caixa de correio inativa

Se uma caixa de correio inativa tiver uma caixa de correio de arquivo morto, você também poderá restaurá-la à caixa de correio de arquivo morto de uma caixa de correio existente. Para restaurar o arquivo morto de uma caixa de correio inativa, adicione as opções _SourceIsArchive_ e _TargetIsAchive_ ao comando usado para restaurar uma caixa de correio inativa.
  
1. Criar uma variável que contém as propriedades da caixa de correio inativa.

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > No comando anterior, use o valor da propriedade **distinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa tenha o mesmo endereço SMTP principal. 
  
2. Restaure o conteúdo do arquivo morto da caixa de correio inativa (arquivo fonte) para o arquivo morto de uma caixa de correio existente (arquivo de destino). Neste exemplo, o conteúdo do arquivo de origem é copiado para uma pasta chamada "arquivo morto de caixa de correio inativa" no arquivo morto da caixa de correio de destino.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>Mais informações

- **Qual é a principal diferença entre a recuperação e a restauração de uma caixa de correio inativa?** Ao recuperar uma caixa de correio inativa, a caixa de correio é basicamente convertida para uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e a caixa de correio é vinculada a uma nova conta de usuário. Após a recuperação, a caixa de correio inativa não existe mais e qualquer alteração feita no conteúdo da nova caixa de correio afetará o conteúdo que estava originalmente em retenção na caixa de correio inativa. Por outro lado, quando você restaura uma caixa de correio inativa, o conteúdo é simplesmente copiado para outra caixa de correio. A caixa de correio inativa é preservada e permanece como inativa. As alterações feitas no conteúdo da caixa de correio de destino não afetarão o conteúdo original mantido na caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a [ferramenta de pesquisa de conteúdo](content-search.md), seu conteúdo pode ser restaurado para outra caixa de correio ou pode ser recuperado ou excluído posteriormente.

- **Como localizar caixas de correio inativas?** Para obter uma lista das caixas de correio inativas em sua organização e exibir informações que são úteis para restaurar uma caixa de correio inativa, você pode executar este comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Use uma retenção de litígio ou uma política de retenção do Microsoft 365 para reter o conteúdo de caixa de correio inativa.** Se você deseja manter o estado de uma caixa de correio inativa após a restauração, é possível colocar a caixa de correio de destino em [retenção de litígio](https://go.microsoft.com/fwlink/?linkid=856286) ou aplicar uma política de [retenção da Microsoft 365](retention.md) antes de restaurar a caixa de correio inativa. Isso impedirá a exclusão permanente de todos os itens da caixa de correio inativa depois que eles forem restaurados para a caixa de correio de destino.

- **Habilite retenção na caixa de correio de destino antes de restaurar uma caixa de correio inativa.** Como os itens de caixa de correio de uma caixa de correio inativa podem ser antigos, você pode considerar habilitar a retenção na caixa de correio de destino antes de restaurar uma caixa de correio inativa. Quando você coloca uma caixa de correio em retenção, a política de retenção atribuída a ela não será processada até que a retenção tenha sido removida ou até que o período de retenção expire. Isso dá ao proprietário do tempo de caixa de correio de destino para gerenciar mensagens antigas da caixa de correio inativa. Caso contrário, a política de retenção poderá excluir itens antigos (ou mover itens para a caixa de correio de arquivo morto, se estiver habilitada) que expiraram com base nas configurações de retenção configuradas para a caixa de correio de destino. Para obter mais informações, consulte [colocar uma caixa de correio em retenção no Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).

- **O que a opção AllowLegacyDNMismatch faz?** Nos exemplos anteriores para restaurar uma caixa de correio inativa, a opção **AllowLegacyDNMismatch** é usada para permitir a restauração da caixa de correio inativa para uma caixa de correio de destino diferente. Em um cenário de restauração típico, o objetivo é restaurar o conteúdo em que as caixas de correio de origem e destino são a mesma caixa de correio. Portanto, por padrão, o cmdlet **New-MailboxRestoreRequest** verifica se o valor da propriedade **legacyExchangeDN** nas caixas de correio de origem e destino é o mesmo. Isso ajuda a evitar a restauração acidental de uma caixa de correio de origem na caixa de correio de destino errada. Se você tentar restaurar uma caixa de correio inativa sem usar a opção **AllowLegacyDNMismatch** , o comando poderá falhar se as caixas de correio de origem e de destino tiverem valores diferentes para a propriedade **legacyExchangeDN** .

- **Você pode usar outros parâmetros com o cmdlet New-MailboxRestoreRequest para implementar diferentes cenários de restauração para caixas de correio inativas.** Por exemplo, você pode executar este comando para restaurar o arquivo morto da caixa de correio inativa para a caixa de correio principal da caixa de correio de destino. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Você também pode restaurar a caixa de correio principal inativa no arquivo morto da caixa de correio de destino executando este comando.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **O que o parâmetro TargetRootFolder faz?** Como explicado anteriormente, você pode usar o parâmetro **TargetRootFolder** para especificar uma pasta na parte superior da estrutura de pastas (também chamada de raiz) na caixa de correio de destino na qual restaurar o conteúdo da caixa de correio inativa. Se você não usar esse parâmetro, os itens de caixa de correio da caixa de correio inativa serão mesclados nas pastas padrão correspondentes da caixa de correio de destino e as pastas personalizadas serão recriadas na raiz da caixa de correio de destino. As ilustrações a seguir destacam essas diferenças entre o uso e o uso do parâmetro **TargetRootFolder** .

    **Hierarquia de pastas na caixa de correio de destino quando o parâmetro TargetRootFolder não é usado**

    ![Captura de tela quando o parâmetro TargetRootFolder não é usado](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **Hierarquia de pastas na caixa de correio de destino quando o parâmetro TargetRootFolder é usado**

    ![Captura de tela quando o parâmetro TargetRootFolder é usado](../media/300da592-7323-48db-b8a4-07012259d113.png)
