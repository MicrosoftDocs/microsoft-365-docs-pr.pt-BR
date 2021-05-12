---
title: Atualizar listas de distribuição para grupos do Microsoft 365 no Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Saiba como atualizar uma ou muitas listas de distribuição para grupos do Microsoft 365 no Outlook e como usar o PowerShell para atualizar várias listas de distribuição simultaneamente.
ms.openlocfilehash: 8179937cafa26a2258f67baee29fcec65bd60632
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332445"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Atualizar listas de distribuição para grupos do Microsoft 365 no Outlook

Você pode atualizar listas de distribuição para grupos do Microsoft 365 no Outlook. Essa é uma ótima maneira de dar à sua organização listas de todos os recursos e funcionalidades dos Grupos do Microsoft 365. [Por que você deve atualizar suas listas de distribuição para grupos no Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Você pode atualizar DLs uma de cada vez ou várias ao mesmo tempo.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Atualizar um ou muitos grupos de lista de distribuição para grupos do Microsoft 365 no Outlook

Você deve ser um administrador global ou administrador do Exchange para atualizar um grupo de lista de distribuição. Para atualizar para grupos do Microsoft 365, o grupo de lista de distribuição deve ter um proprietário com uma caixa de correio.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Usar o novo EAC para atualizar um ou vários grupos de lista de distribuição para grupos do Microsoft 365 no Outlook

1. Vá para o novo [centro de administração do Exchange](https://admin.exchange.microsoft.com)e navegue até Grupos de **Destinatários.** \> 

2. Selecione o grupo de lista de distribuição (também chamado de grupo de distribuição **)** que você deseja atualizar para o grupo do Microsoft 365 na página **Grupos.**

3. Selecione o **grupo De atualização de distribuição** na barra de ferramentas.

4. Na caixa de diálogo **Pronto para atualizar?**, clique em **Atualizar**. O processo começa imediatamente. Dependendo do tamanho e do número de grupos de lista de distribuição que você está atualizando, o processo pode levar minutos ou horas.

> [!NOTE]
> Uma faixa na parte superior indica que a atualização, por exemplo, grupos de distribuição *foi atualizado. Levará 5 minutos para refletir as alterações. Filtrar por grupos do Microsoft 365 para ver* os grupos de destrução atualizados.

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Use o EAC clássico para atualizar um ou vários grupos de lista de distribuição para grupos do Microsoft 365 no Outlook

1. Vá para o Centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administração clássico do Exchange.</a>

2. No Centro de administração clássico do Exchange, vá para **Grupos de** \> **Destinatários.**<br/>Você verá um aviso indicando que você tem listas de distribuição (também chamadas de grupos de distribuição **)** que estão qualificadas para serem atualizadas para grupos do Microsoft 365.<br/> ![Selecione o botão Iniciar](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selecione uma ou mais listas de distribuição (também chamada de grupo **de distribuição**) na página **grupos.**<br/>![Selecionar um grupo de distribuição](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selecione o ícone de atualização.<br/>![Atualizar para o ícone grupos do Microsoft 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Na caixa de diálogo informações, selecione **Sim** para confirmar a atualização. O processo começa imediatamente. Dependendo do tamanho e do número de DLs que você está atualizando, o processo pode levar minutos ou horas.<br/>Se a lista de distribuição não puder ser atualizada, uma caixa de diálogo aparecerá dizendo isso. Veja [Quais listas de distribuição não podem ser atualizadas?](#which-distribution-lists-cant-be-upgraded).

6. Se você estiver atualizando várias listas de distribuição, use a listada para filtrar quais listas de distribuição foram atualizadas. Se a lista não estiver concluída, aguarde um pouco mais e selecione **Atualizar** para ver o que foi atualizado com êxito.<br/>Não há nenhum aviso informando quando o processo de atualização foi concluído para todas as DLs selecionadas. Você pode descobrir isso procurando ver o que está listado em Disponível para **atualização** ou **DLs atualizadas.**

7. Se você selecionou uma DL para atualização, mas ela ainda aparece na página como Disponível para atualização, então ela falhou ao atualizar. Consulte [O que fazer se a atualização não funcionar](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Se você estiver recebendo os grupos digere emails, você pode notar, na parte inferior, que às vezes ele oferecerá para permitir que você atualize quaisquer listas de distribuição qualificadas das que você é o proprietário. Confira [Ter uma conversa em grupo no Outlook para](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) obter mais informações sobre emails de digest.

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>O que fazer se a atualização não funcionar

As listas de distribuição que não conseguem atualizar permanecem inalteradas.

Se uma ou mais **listas de** distribuição qualificadas não conseguirem ser atualizadas, abra um [tíquete de Suporte](../../business-video/get-help-support.md). O problema precisará ser escalonado para a equipe de Engenharia de Grupos para que eles descubram o problema.

É possível que a lista de distribuição não tenha se atualizado devido a uma paralisação de serviço, mas improvável. Se quiser, aguarde um pouco e tente atualizar o DL novamente.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Como usar o PowerShell para atualizar várias listas de distribuição ao mesmo tempo

Se você tiver experiência em usar o PowerShell, talvez queira seguir essa rota em vez de usar a interface do usuário. Temos um conjunto de cmdlets que ajudarão você a atualizar listas de distribuição. Confira a seguir.

### <a name="upgrade-a-single-dl"></a>Atualizar um único DL

Para atualizar um único DL, execute o seguinte comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>
```

Por exemplo, se você quiser atualizar uma DLs com endereço SMTP dl1@contoso.com, execute o seguinte comando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> Você também pode atualizar uma única lista de distribuição para um grupo do Microsoft 365 usando o cmdlet [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell

### <a name="upgrade-multiple-dls-in-a-batch"></a>Atualizar várias DLs em um lote

Você também pode passar várias DLs como um lote e atualiza-las juntas:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Por exemplo, se você quiser atualizar cinco DLs com endereço SMTP e `dl1@contoso.com` , e , execute o seguinte `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Atualizar todas as DLs qualificadas

Há duas maneiras de atualizar todas as DLs qualificadas.

> [!NOTE]
> O Upgrade-DistributionGroup cmdlet não recebe dados do pipeline, por esse motivo, é necessário usar o operador "foreach-object" para ser executado com {} êxito.

1. Obter as DLs qualificadas no locatário e atualize-as usando o comando de atualização:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Obter a lista de todas as DLs e atualizar apenas as DLs qualificadas:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Perguntas frequentes sobre como atualizar listas de distribuição para grupos do Microsoft 365 no Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Quais listas de distribuição não podem ser atualizadas?

Você só pode atualizar listas de distribuição gerenciadas por nuvem, simples e não aninhadas. A tabela a seguir lista listas de distribuição que **NÃO PODEM** ser atualizadas.

|**Property**|**Qualificado?**|
|:-----|:-----|
|Lista de distribuição gerenciada local.  <br/> |Não  <br/> |
|Listas de distribuição aninhadas. A lista de distribuição tem grupos filho ou é membro de outro grupo.  <br/> |Não  <br/> |
|Listas de distribuição com **recipientTypeDetails** que não **seja UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**  <br/> |Não  <br/> |
|Lista de distribuição com mais de 100 proprietários  <br/> |Não  <br/> |
|Lista de distribuição que só tem membros, mas nenhum proprietário  <br/> |Não  <br/> |
|Lista de distribuição que tem alias contendo caracteres especiais  <br/> |Não  <br/> |
|Se a lista de distribuição estiver configurada para ser um endereço de encaminhamento para Caixa de Correio Compartilhada  <br/> |Não  <br/> |
|Se a DL faz parte da **Restrição do Remetente** em outro DL.  <br/> |Não  <br/> |
|Grupos de segurança  <br/> |Não  <br/> |
|Listas de Distribuição Dinâmica  <br/> |Não  <br/> |
|Listas de distribuição que foram convertidas em **RoomLists**  <br/> |Não  <br/> |
|Listas de distribuição **onde MemberJoinRestriction** e/ou **MemberDepartRestriction** é **Fechado**  <br/> |Não  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Verificar quais DLs estão qualificadas para atualização

Se você quiser verificar se uma DL está qualificada ou não, você pode executar o comando abaixo:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Se você quiser verificar quais DLs estão qualificadas para atualização, execute o seguinte comando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Quem pode executar os scripts de atualização?

Pessoas com direitos de administrador global ou administrador do Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Por que o cartão de visita ainda está mostrando uma lista de distribuição? O que devo fazer para impedir que uma lista de distribuição atualizada seja aparecendo na minha lista de sugestões automáticas?

- Para o Outlook: quando alguém tentar enviar um email no Outlook digitando o nome do grupo do Microsoft 365 após a migração, o destinatário será resolvido como a lista de distribuição em vez do grupo. O cartão de visita do destinatário será o cartão de visita de listas de distribuição. Isso se deve ao cache de destinatário ou cache de nome de nick no Outlook. O email será enviado com êxito para o grupo, mas pode causar confusão ao remetente.<br/>Você pode executar as etapas deste artigo, Informações sobre a lista [de Preenchimento Automático](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) do Outlook para redefinir o cache, o que corrigirá esse problema.

- Para o Outlook na Web: no caso do Outlook na Web, o destinatário da lista de distribuição ainda permanecerá no cache. Você pode seguir as etapas em [Remover nome](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) sugerido ou endereço de email da Lista De Conclusão Automática para atualizar o cache para ver o cartão de visita do grupo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Os novos membros do grupo recebem um email de boas-vindas na caixa de entrada?

Não. A configuração para habilitar mensagens de boas-vindas é definida como false por padrão. Essa configuração afeta os membros existentes e novos do grupo que podem ingressar após a conclusão da migração. Se o proprietário do grupo permitir mais tarde os usuários convidados, os usuários convidados não receberão um email de boas-vindas em sua caixa de entrada. Os membros convidados podem continuar trabalhando com o grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>E se uma ou algumas DLs não são atualizadas?

Há alguns casos em que a DL é qualificada, mas não pode ser atualizada. A DL não é atualizada e permanece como uma DL.

- Onde o administrador aplicou a Política de Endereço de **Email** de Grupo para os grupos em uma organização e eles tentam atualizar DLs que não cumprem os critérios, a DL não é atualizada

- As DLs **com MemberJoinRestriction** **ou MemberDepartRestriction definidas** como **Closed**, não puderam ser atualizadas

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>O que acontece com a DL se a atualização do EAC falhar?

A atualização só acontecerá quando a chamada for enviada para o servidor. Se a atualização falhar, suas DLs estarão intactas. Eles funcionarão como antes.
