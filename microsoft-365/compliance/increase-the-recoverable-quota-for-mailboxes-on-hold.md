---
title: Aumentar a cota de Itens Recuperáveis para caixas de correio em espera
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
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: Habilita a caixa de correio de arquivo morto e ative o arquivamento de expansão automática para aumentar o tamanho da pasta Itens Recuperáveis para uma caixa de correio em Microsoft 365.
ms.openlocfilehash: 47227e066f922a9e4b8bccedaa9573c001194836
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226582"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>Aumentar a cota de Itens Recuperáveis para caixas de correio em espera

A política de retenção de Exchange padrão, denominada Política *de MRM* Padrão, que é aplicada automaticamente a novas caixas de correio no Exchange Online contém uma marca de retenção chamada Itens Recuperáveis 14 dias para o arquivo morto. Essa marca de retenção move itens da pasta Itens Recuperáveis na caixa de correio principal do usuário para a pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário após o período de retenção de 14 dias expirar para um item. Para que isso aconteça, a caixa de correio de arquivo morto do usuário deve estar habilitada. Se a caixa de correio de arquivo morto não estiver habilitada, nenhuma ação será tomada, o que significa que os itens na pasta Itens Recuperáveis para uma caixa de correio em espera não são movidos para a caixa de correio de arquivo morto após o período de retenção de 14 dias expirar. Como nada é excluído de uma caixa de correio em espera, é possível que a cota de armazenamento da pasta Itens Recuperáveis possa ser excedida, especialmente se a caixa de correio de arquivo morto do usuário não estiver habilitada.

Para ajudar a reduzir a chance de exceder esse limite, a cota de armazenamento para a pasta Itens Recuperáveis é automaticamente aumentada de 30 GB para 100 GB quando uma suspensão é colocada em uma caixa de correio em Exchange Online. Se a caixa de correio de arquivo morto estiver habilitada, a cota de armazenamento da pasta Itens Recuperáveis na caixa de correio de arquivo morto também aumentará de 30 GB para 100 GB. Se o recurso de arquivamento de expansão automática no Exchange Online estiver habilitado, a cota de armazenamento da pasta Itens Recuperáveis no arquivo morto do usuário será ilimitada.

  A tabela a seguir resume a cota de armazenamento da pasta Itens Recuperáveis.

|**Local da pasta Itens Recuperáveis**|**Caixas de correio não em espera**|**Caixas de correio em espera**|
|:-----|:-----|:-----|
|Caixa de correio principal  <br/> |30 GB  <br/> |100 GB  <br/> |
|Caixa de correio de arquivo morto<sup>\*</sup> <br/> |Ilimitado  <br/> |Ilimitado  <br/> |
|**Cota de armazenamento total para a pasta Itens Recuperáveis** <br/> |Ilimitado  <br/> |Ilimitado  <br/> |

> [!NOTE]
> <sup>\*</sup>A cota de armazenamento inicial para a caixa de correio de arquivo morto é de 100 GB para usuários com uma Exchange Online (Plano 2) de usuário. No entanto, quando o arquivamento de expansão automática é ligado para caixas de correio em espera, a cota de armazenamento para a caixa de correio de arquivo morto e a pasta Itens Recuperáveis é aumentada para 110 GB. O espaço de armazenamento de arquivo morto adicional será provisionado quando necessário, o que resulta em uma quantidade ilimitada de armazenamento de arquivo morto. Para obter mais informações sobre o arquivamento de expansão automática, consulte [Overview of unlimited archiving in Office 365](unlimited-archiving.md).

Quando a cota de armazenamento da pasta Itens Recuperáveis na caixa de correio principal de uma caixa de correio em espera está quase atingindo o limite, você pode fazer o seguinte:

- **Habilita a caixa de correio de arquivo morto e ative o arquivamento de expansão automática.** Você pode habilitar uma capacidade de armazenamento ilimitada para a pasta Itens Recuperáveis simplesmente habilitando a caixa de correio de arquivo morto e ativando o recurso de arquivamento de expansão automática Exchange Online. Isso resulta em 110 GB para a pasta Itens Recuperáveis na caixa de correio principal e uma quantidade ilimitada de capacidade de armazenamento para a pasta Itens Recuperáveis no arquivo morto do usuário. Veja como: [Habilitar caixas de](enable-archive-mailboxes.md) correio de arquivo morto no Centro de Conformidade & Segurança e Habilitar arquivamento [ilimitado em Office 365](enable-unlimited-archiving.md).

    > [!NOTE]
    > Depois de habilitar o arquivo morto de uma caixa de correio que está perto de exceder a cota de armazenamento para a pasta Itens Recuperáveis, talvez você queira executar o Assistente de Pasta Gerenciada para disparar manualmente o assistente para processar a caixa de correio para que os itens expirados sejam movidos para a pasta Itens Recuperáveis na caixa de correio de arquivo morto. Confira as instruções na [Etapa 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings). Os demais itens na caixa de correio do usuário podem ser movidos para a nova caixa de correio de arquivo morto. Considere dizer ao usuário que isso pode acontecer depois que você habilitar a caixa de correio de arquivo morto.

- **Crie uma política de Exchange de retenção personalizada para caixas de correio em espera.** Além de habilitar a caixa de correio de arquivo morto e o arquivamento de expansão automática para caixas de correio em Retenção de Litígio ou In-Place Retenção, você também pode querer criar uma política de retenção de Exchange personalizada para caixas de correio em espera. Isso permite aplicar uma política de retenção a caixas de correio em espera diferentes da Política mrm padrão aplicada a caixas de correio que não estão em espera e permite aplicar marcas de retenção projetadas para caixas de correio em espera. Isso inclui a criação de uma nova marca de retenção para a pasta Itens Recuperáveis.

O restante deste tópico descreve os procedimentos passo a passo para criar uma política de retenção de Exchange personalizada para caixas de correio em espera.

[Etapa 1: criar uma marca de retenção personalizada para a pasta Itens Recuperáveis](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[Etapa 2: criar uma nova Exchange de retenção para caixas de correio em espera](#step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold)

[Etapa 3: aplicar a nova Exchange de retenção a caixas de correio em espera](#step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold)

[(Opcional) Etapa 4: executar o Assistente de Pasta Gerenciada para aplicar as novas configurações de retenção](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)

## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>Etapa 1: Criar uma marca de retenção personalizada para a pasta Itens Recuperáveis

A primeira etapa é criar uma marca de retenção personalizada (chamada de marca de política de retenção ou RPT) para a pasta Itens Recuperáveis. Como explicado anteriormente, essa RPT move itens da pasta Itens Recuperáveis na caixa de correio principal do usuário para a pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário. Você precisa usar o PowerShell para criar um RPT para a pasta Itens Recuperáveis. Você não pode usar o Centro de Administração do Exchange (EAC).

1. [Conectar-se ao Exchange Online usando o PowerShell Remoto](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando para criar um novo relatório para a pasta Itens Recuperáveis: 

    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    Por exemplo, o comando a seguir cria um RPT para a pasta Itens Recuperáveis chamado "Itens Recuperáveis 30 dias para caixas de correio em espera", com um período de retenção de 30 dias. Isso significa que depois que um item estiver na pasta Itens Recuperáveis por 30 dias, ele será movido para a pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário.

    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > Recomendamos que o período de retenção (definido pelo parâmetro  _AgeLimitForRetention)_ para o RPT de Itens Recuperáveis seja igual ao período de retenção de item excluído para as caixas de correio às que o RPT será aplicado. Isso proporciona a um usuário todo o período de retenção de itens excluídos para recuperar itens excluídos antes que eles sejam movidos para a caixa de correio de arquivo morto. No exemplo anterior, o período de retenção foi configurado para 30 dias com base na suposição de que o período de retenção de itens excluídos para caixas de correio também é de 30 dias. Uma caixa de correio do Exchange Online é configurada, por padrão, para manter itens excluídos por 14 dias. Porém, você pode alterar essa configuração para até 30 dias. Para obter mais informações, [consulte Change the deleted item retention period for a mailbox in Exchange Online](https://www.microsoft.com/?ref=go).

## <a name="step-2-create-a-new-exchange-retention-policy-for-mailboxes-on-hold"></a>Etapa 2: criar uma nova Exchange de retenção para caixas de correio em espera

A próxima etapa é criar uma nova política de retenção e adicionar marcas de retenção a ela, inclusive o RPT de Itens Recuperáveis que você criou na Etapa 1. Essa nova política será aplicada às caixas de correio em espera na próxima etapa. 

Antes de criar a nova política de retenção, determine as marcas de retenção adicionais que você deseja adicionar. Confira a lista das marcas de retenção adicionadas à política MRM Padrão e informações sobre como criar novas marcas de retenção em:

- [Política de Retenção Padrão no Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- [Pastas padrão que suportam marcas de política de retenção](/exchange/security-and-compliance/messaging-records-management/default-folders)

- A seção "Criar uma marca de retenção" no [tópico Criar uma Política de](/exchange/security-and-compliance/messaging-records-management/create-a-retention-policy) Retenção.

Você pode usar o EAC ou Exchange Online PowerShell para criar uma política de retenção.

### <a name="use-the-eac-to-create-a-retention-policy"></a>Usar o EAC para criar uma política de retenção

1. No EAC, vá para Políticas de retenção de **gerenciamento** de conformidade e clique em \>  **Adicionar** ![ ícone ](../media/ITPro-EAC-AddIcon.gif) .

2. Na página **Nova política de retenção**, em **Nome**, digite um nome que descreva o propósito da política de retenção, por exemplo, **MRM Policy for Mailboxes on Hold**. 

3. Em **Marcas de retenção,** clique **em Adicionar** Ícone ![ ](../media/ITPro-EAC-AddIcon.gif) .

4. Na lista de marcas de retenção, selecione o relatório de itens recuperáveis que você criou na Etapa 1 e clique em **Adicionar**.

    ![Selecione a marca de retenção personalizada Itens Recuperáveis](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)

5. Selecione marcas de retenção adicionais para adicionar à política de retenção. Por exemplo, convém adicionar as mesmas marcas que são incluídas na Política de MRM Padrão.

6. Quando terminar de adicionar marcas de retenção, clique em **OK**.

7. Clique em **Salvar** para criar a nova política de retenção. 

    Observe que as marcas de retenção vinculadas à política de retenção são exibidas no painel de detalhes.

    ![Marcas de retenção vinculadas à política de retenção são exibidas no painel de detalhes](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)

### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Usar Exchange Online PowerShell para criar uma política de retenção

Execute o comando a seguir para criar a nova política de retenção para caixas de correio em espera. 

```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

Por exemplo, o comando a seguir cria a política de retenção e as marcas de retenção vinculadas exibidas na ilustração anterior.

```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-exchange-retention-policy-to-mailboxes-on-hold"></a>Etapa 3: aplicar a nova Exchange de retenção a caixas de correio em espera

A última etapa é aplicar a nova política de retenção que você criou na Etapa 2 a caixas de correio em espera na sua organização. Você pode usar o EAC ou Exchange Online PowerShell para aplicar a política de retenção a uma única caixa de correio ou a várias caixas de correio.

### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>Usar o EAC para aplicar a nova política de retenção

1. Vá para **Caixas de** Correio  >  **de Destinatários.**

2. No modo de exibição de lista, selecione a caixa de correio à que você deseja aplicar a política de retenção e clique em **Editar** ![ ícone ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) editar.

3. Na página **Caixa de Correio do Usuário**, clique em **Recursos de caixa de correio**.

4. Em **Política de retenção**, selecione a política de retenção que você criou na Etapa 2 e clique em **Salvar**.

Você também pode usar o EAC para aplicar a política de retenção a várias caixas de correio.

1. Vá para **Caixas de** Correio  >  **de Destinatários.**

2. No modo de exibição de lista, use as teclas Shift ou Ctrl, para selecionar várias caixas de correio.

3. No painel de detalhes, clique em **Mais opções**.

4. Em **Política de Retenção**, clique em **Atualizar**.

5. Na página **Atribuir em massa uma política de retenção**, selecione a política de retenção que você criou na Etapa 2 e clique em **Salvar**. 

### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Use Exchange Online PowerShell para aplicar a nova política de retenção

Você pode usar Exchange Online PowerShell para aplicar uma nova política de retenção a uma única caixa de correio. Mas o poder real do PowerShell é que você pode usá-lo para identificar rapidamente todas as caixas de correio em sua organização que estão em Retenção de Litígio ou In-Place Retenção e, em seguida, aplicar a nova política de retenção a todas as caixas de correio em espera em um único comando. Aqui estão alguns exemplos de uso Exchange PowerShell para aplicar uma política de retenção a uma ou mais caixas de correio. Todos os exemplos aplicam a política de retenção que foi criada na Etapa 2.

Este exemplo aplica a nova política de retenção à caixa de correio de Clara Barbosa.

```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Este exemplo aplica a nova política de retenção a todas as caixas de correio na organização que estão em Retenção de Litígio.

```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Este exemplo aplica a nova política de retenção a todas as caixas de correio na organização que estão em Bloqueio In-loco.

```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

Você pode usar o cmdlet **Get-Mailbox** para verificar se a nova política de retenção foi aplicada.

Aqui estão alguns exemplos para verificar se os comandos nos exemplos anteriores aplicaram a "Política MRM a caixas de correio em espera" em caixas de correio em Retenção de Litígio e caixas de correio em Bloqueio In-loco.

```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(Opcional) Etapa 4: Executar o Assistente de Pasta Gerenciada para aplicar as novas configurações de retenção

Depois de aplicar Exchange nova política de retenção a caixas de correio em espera, pode levar até 7 dias em Exchange Online para o Assistente de Pasta Gerenciada processar essas caixas de correio usando as configurações da nova política de retenção. Em vez de esperar pela execução do Assistente de Pasta Gerenciada, você pode usar o cmdlet **Start-ManagedFolderAssistant** para disparar manualmente o assistente para processar as caixas de correio às quais você aplicou a nova política de retenção.

Execute o comando a seguir para iniciar o Assistente de Pasta Gerenciada para caixa de correio de Clara Barbosa.

```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

Execute os comandos a seguir para iniciar o Assistente de Pasta Gerenciada para todas as caixas de correio em espera.

```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>Mais informações

- Após habilitar a caixa de correio de arquivo morto de um usuário, considere informar ao usuário que outros itens da sua caixa de correio (não apenas itens na pasta Itens Recuperáveis) podem ser movidos para a caixa de correio de arquivo morto. Isso porque a Política mrm padrão atribuída a caixas de correio Exchange Online contém uma marca de retenção (chamada Padrão de 2 anos de movimentação para arquivo morto) que move itens para a caixa de correio de arquivo morto dois anos após a data em que o item foi entregue à caixa de correio ou criado pelo usuário. Para obter mais informações, consulte [Política de Retenção Padrão no Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

- Após habilitar a caixa de correio de arquivo morto de um usuário, você também pode informar ao usuário que ele pode recuperar itens excluídos na pasta Itens Recuperáveis na caixa de correio de arquivo morto. Eles podem fazer isso em Outlook selecionando a pasta **Itens** Excluídos na caixa de correio de arquivo morto e, em seguida, clicando em **Recuperar Itens Excluídos** do Servidor na guia Início.  Para obter mais informações sobre como recuperar itens excluídos, consulte [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).
