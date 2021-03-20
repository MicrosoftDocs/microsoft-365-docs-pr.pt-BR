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
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917295"
---
# <a name="restore-an-inactive-mailbox"></a>Restaurar uma caixa de correio inativa

Uma caixa de correio inativa (que é um tipo de caixa de correio excluída de forma suave) é usada para reter o email de um ex-funcionário depois que ele sair da sua organização. Se outro funcionário assumir as responsabilidades de trabalho do funcionário desacalhado ou se esse funcionário retornar à sua organização, há duas maneiras de disponibilizar o conteúdo da caixa de correio inativa para um usuário:

- **Restaurar uma caixa de correio inativa** Se outro funcionário assumir as responsabilidades de trabalho do funcionário desapurado ou se outro usuário precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Você também pode restaurar o arquivo morto de uma caixa de correio inativa. Depois de restaurada, a caixa de correio inativa é preservada e mantida como uma caixa de correio inativa. Este tópico descreve os procedimentos para restaurar uma caixa de correio inativa.

- **Recuperar uma caixa de correio inativa** Se o funcionário desacalhado retornar à sua organização ou se um novo funcionário for contratado para assumir as responsabilidades de trabalho do funcionário morto, você poderá recuperar o conteúdo da caixa de correio inativa. Esse método converte a caixa de correio inativa em uma nova caixa de correio que contém o conteúdo da caixa de correio inativa. Após sua recuperação, a caixa de correio inativa deixa de existir. Para os procedimentos passo a passo, consulte [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).

Consulte a [seção Mais informações](#more-information) neste artigo para obter mais detalhes sobre as diferenças entre restaurar e recuperar uma caixa de correio inativa.

> [!NOTE]
> Não é possível recuperar ou restaurar uma caixa de correio inativa configurada com um arquivo morto de expansão automática. Se você precisar recuperar dados de uma caixa de correio inativa com um arquivo morto em expansão automática, use a pesquisa de conteúdo para exportar os dados da caixa de correio e importe para outra caixa de correio. Para obter instruções, consulte os seguintes tópicos:
>
> - [Pesquisa de conteúdo](content-search.md)
> - [Exportar resultados da pesquisa de conteúdo](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>Requisitos para restaurar uma caixa de correio inativa

- Você precisa usar o PowerShell do Exchange Online para restaurar uma caixa de correio inativa. Você não pode usar o Centro de Administração do Exchange (EAC). Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Execute o seguinte comando no PowerShell do Exchange Online para obter informações de identidade para as caixas de correio inativas em sua organização.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Use as informações retornadas por este comando para restaurar uma caixa de correio inativa específica.

- Para obter mais informações sobre caixas de correio inativas, consulte Caixas de correio [inativas no Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-inactive-mailboxes"></a>Restaurar caixas de correio inativas

Use o cmdlet **New-MailboxRestoreRequest** com os parâmetros  _SourceMailbox_ e  _TargetMailbox_ para restaurar o conteúdo de uma caixa de correio inativa para uma caixa de correio existente. Para obter mais informações sobre como usar esse cmdlet, consulte [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).

1. Crie uma variável que contenha as propriedades da caixa de correio inativa.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa possa ter o mesmo endereço SMTP principal.

2. Restaure o conteúdo da caixa de correio inativa para uma caixa de correio existente. O conteúdo da caixa de correio inativa (caixa de correio de origem) será mesclado nas pastas correspondentes na caixa de correio existente (caixa de correio de destino).

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   Como alternativa, você pode especificar uma pasta de nível superior na caixa de correio de destino na qual restaurar o conteúdo da caixa de correio inativa. Se a pasta de destino especificada ou a estrutura da pasta de destino ainda não existir na caixa de correio de destino, ela será criada durante o processo de restauração.

   Este exemplo copia itens de caixa de correio e subpastas de uma caixa de correio inativa para uma pasta chamada "Caixa de Correio Inativa" na estrutura de pasta de nível superior da caixa de correio de destino.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Restaurar o arquivo morto de uma caixa de correio inativa

Se uma caixa de correio inativa tiver uma caixa de correio de arquivo morto, você também poderá restaurá-la para a caixa de correio de arquivo morto de uma caixa de correio existente. Para restaurar o arquivo morto de uma caixa de correio inativa, você precisa adicionar as opções _SourceIsArchive_ e _TargetIsArchive_ ao comando usado para restaurar uma caixa de correio inativa.

1. Crie uma variável que contenha as propriedades da caixa de correio inativa.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGUID** para identificar a caixa de correio inativa. Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e inativa possa ter o mesmo endereço SMTP principal.

2. Restaure o conteúdo do arquivo morto da caixa de correio inativa (arquivo morto de origem) para o arquivo morto de uma caixa de correio existente (arquivo morto de destino). Neste exemplo, o conteúdo do arquivo morto de origem é copiado para uma pasta chamada "Arquivo morto de caixa de correio inativa" no arquivo morto da caixa de correio de destino.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>Mais informações

- **Qual é a principal diferença entre recuperar e restaurar uma caixa de correio inativa?** Quando você recupera uma caixa de correio inativa, a caixa de correio é basicamente convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e a caixa de correio é vinculada a uma nova conta de usuário. Depois de recuperada, a caixa de correio inativa não existe mais, e quaisquer alterações feitas no conteúdo na nova caixa de correio afetarão o conteúdo que estava originalmente em espera na caixa de correio inativa. Por outro lado, quando você restaura uma caixa de correio inativa, o conteúdo é simplesmente copiado para outra caixa de correio. A caixa de correio inativa é preservada e permanece como inativa. Quaisquer alterações feitas no conteúdo na caixa de correio de destino não afetarão o conteúdo original mantido na caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando a ferramenta Pesquisa de Conteúdo [,](content-search.md)seu conteúdo pode ser restaurado para outra caixa de correio, ou pode ser recuperado ou excluído em uma data posterior.

- **Como você encontra caixas de correio inativas?** Para obter uma lista das caixas de correio inativas em sua organização e exibir informações úteis para restaurar uma caixa de correio inativa, você pode executar esse comando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Use uma retenção de litígio ou uma política de retenção do Microsoft 365 para reter o conteúdo inativo da caixa de correio.** Se você quiser manter o estado de uma caixa de correio inativa depois [](create-a-litigation-hold.md) de restaurada, coloque a caixa de correio de destino em Retenção de Litígio ou aplique uma política de retenção do [Microsoft 365](retention.md) antes de restaurar a caixa de correio inativa. Isso impedirá a exclusão permanente de todos os itens da caixa de correio inativa depois que eles são restaurados para a caixa de correio de destino.

- **Habilita a retenção na caixa de correio de destino antes de restaurar uma caixa de correio inativa.** Como os itens de caixa de correio de uma caixa de correio inativa podem ser antigos, você pode considerar habilenciar a retenção na caixa de correio de destino antes de restaurar uma caixa de correio inativa. Quando você coloca uma caixa de correio em retenção, a política de retenção atribuída a ela não será processada até que a retenção seja removida ou até que o período de retenção expire. Isso dá ao proprietário do tempo de caixa de correio de destino para gerenciar mensagens antigas da caixa de correio inativa. Caso contrário, a política de retenção poderá excluir itens antigos (ou mover itens para a caixa de correio de arquivo morto, se estiver habilitada) que tenham expirado com base nas configurações de retenção configuradas para a caixa de correio de destino. Para obter mais informações, [consulte Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **O que a opção AllowLegacyDNMismatch faz?** Nos exemplos anteriores para restaurar uma caixa de correio inativa, a opção **AllowLegacyDNMismatch** é usada para permitir a restauração da caixa de correio inativa para uma caixa de correio de destino diferente. Em um cenário de restauração típico, o objetivo é restaurar o conteúdo onde as caixas de correio de origem e de destino são a mesma caixa de correio. Portanto, por padrão, o cmdlet **New-MailboxRestoreRequest** verifica se o valor da propriedade **LegacyExchangeDN** nas caixas de correio de origem e de destino é o mesmo. Isso ajuda a impedir que você restaurá acidentalmente uma caixa de correio de origem na caixa de correio de destino errada. Se você tentar restaurar uma caixa de correio inativa sem usar a opção **AllowLegacyDNMismatch,** o comando poderá falhar se as caixas de correio de origem e de destino têm valores diferentes para a propriedade **LegacyExchangeDN.**

- **Você pode usar outros parâmetros com o cmdlet New-MailboxRestoreRequest para implementar diferentes cenários de restauração para caixas de correio inativas.** Por exemplo, você pode executar esse comando para restaurar o arquivo morto da caixa de correio inativa para a caixa de correio principal da caixa de correio de destino.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Você também pode restaurar a caixa de correio primária inativa no arquivo morto da caixa de correio de destino executando este comando.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **O que o parâmetro TargetRootFolder faz?** Conforme explicado anteriormente, você pode usar o parâmetro **TargetRootFolder** para especificar uma pasta na parte superior da estrutura de pastas (também chamada de raiz) na caixa de correio de destino na qual restaurar o conteúdo da caixa de correio inativa. Se você não usar esse parâmetro, os itens de caixa de correio da caixa de correio inativa serão mesclados nas pastas padrão correspondentes da caixa de correio de destino e pastas personalizadas serão re-criadas na raiz da caixa de correio de destino. As ilustrações a seguir realçam essas diferenças entre não usar e usar o **parâmetro TargetRootFolder.**

  **Hierarquia de pastas na caixa de correio de destino quando o parâmetro TargetRootFolder não é usado**

  ![Captura de tela quando o parâmetro TargetRootFolder não é usado](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **Hierarquia de pastas na caixa de correio de destino quando o parâmetro TargetRootFolder é usado**

  ![Captura de tela quando o parâmetro TargetRootFolder é usado](../media/300da592-7323-48db-b8a4-07012259d113.png)