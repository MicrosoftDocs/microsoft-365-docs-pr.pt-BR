---
title: Atualizar listas de distribuição para grupos do Office 365 no Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Saiba como atualizar uma ou várias listas de distribuição para grupos do Office 365 no Outlook e como usar o PowerShell para atualizar várias listas de distribuição simultaneamente.
ms.openlocfilehash: c3acf1d47a37d79d666b1b951bea704c273ccf09
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212276"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a>Atualizar listas de distribuição para grupos do Office 365 no Outlook

Você pode atualizar as listas de distribuição para grupos do Office 365 com o Outlook. Essa é uma ótima maneira de fornecer a distribuição da organização lista todos os recursos e a funcionalidade dos grupos do Office 365. [Por que você deve atualizar suas listas de distribuição para grupos no Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

Você pode atualizar uma ou várias DLs ao mesmo tempo.

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a>Atualizar uma ou várias listas de distribuição para grupos do Office 365 no Outlook

Você deve ser um administrador global do Office 365 ou um administrador do Exchange para atualizar uma lista de distribuição. Para atualizar para os grupos do Office 365, um grupo de distribuição deve ter um proprietário com uma caixa de correio. 

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.

2. No centro de administração do Exchange, vá para **grupos**de **destinatários** \> .<br/>Você verá um aviso indicando que você tem listas de distribuição (também chamadas de **grupos de distribuição** ) qualificadas para serem atualizadas para grupos do Office 365.<br/> ![Selecionar o botão introdução](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selecione uma ou mais listas de distribuição (também chamadas de **grupo de distribuição** ) na página **grupos** .<br/>![Selecionar um grupo de distribuição](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selecione o ícone upgrade.<br/>![Atualizar para o ícone de grupos do Office 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Na caixa de diálogo informações, selecione **Sim** para confirmar a atualização. O processo começa imediatamente. Dependendo do tamanho e do número de DLs que você está atualizando, o processo pode levar minutos ou horas.<br/>Se a lista de distribuição não puder ser atualizada, uma caixa de diálogo aparecerá dizendo isso. Veja [quais listas de distribuição não podem ser atualizadas?](#which-distribution-lists-cannot-be-upgraded).

6. Se você estiver atualizando várias listas de distribuição, use a lista suspensa para filtrar quais listas de distribuição foram atualizadas. Se a lista não estiver concluída, espere um pouco mais e selecione **Atualizar** para ver o que foi atualizado com êxito.<br/>Não há nenhum aviso que informa quando o processo de atualização foi concluído para todas as DLs selecionadas. Você pode descobrir isso procurando ver o que está listado em **disponível para atualização** ou **DL atualizada**.

7. Se você selecionou uma DL para atualização, mas ela ainda aparece na página como disponível para atualização, a atualização não foi possível. Veja [o que fazer se a atualização não funcionar](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Se você estiver obtendo os emails de Resumo de grupos, poderá observar na parte inferior que às vezes oferecerá para permitir que você atualize as listas de distribuição qualificadas das quais você é o proprietário. Confira [ter uma conversa de grupo no Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) para obter mais informações sobre emails de resumo.


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>O que fazer se a atualização não funcionar

As listas de distribuição que falharam ao atualizar permanecem inalteradas.

Se uma ou mais listas de distribuição **qualificadas** não puderem ser atualizadas, abra um [tíquete de suporte](../contact-support-for-business-products.md). O problema precisará ser escalonado para a equipe de engenharia de grupos para descobrir o problema.

É possível que a lista de distribuição não tenha sido atualizada por causa de uma interrupção de serviço, mas muito improvável. Se quiser, aguarde um pouco e tente atualizar novamente a DL.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Como usar o PowerShell para atualizar várias listas de distribuição ao mesmo tempo

Se você tiver experiência com o uso do PowerShell, convém ir até esta rota em vez de usar a interface do usuário. Temos um conjunto de cmdlets que ajudarão você a atualizar as listas de distribuição. Confira a seguir.

### <a name="upgrade-a-single-dl"></a>Atualizar uma única DL

Para atualizar um único DL, execute o seguinte comando:

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

Por exemplo, se você quiser atualizar uma DLs com o endereço SMTP dl1@contoso.com, execute o seguinte comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> Você também pode atualizar uma única lista de distribuição para um grupo do Office 365 usando o cmdlet [New-unificado](https://go.microsoft.com/fwlink/?LinkID=786379) do PowerShell

### <a name="upgrade-multiple-dls-in-a-batch"></a>Atualizar várias DLs em um lote

Você também pode passar várias DLs como um lote e atualizá-las juntas:

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Por exemplo, se você quiser atualizar cinco `dl1@contoso.com` DLS com endereço SMTP e `dl2@contoso.com`, `dl3@contoso.com` `dl4@contoso.com` e `dl5@contoso.com`, execute o seguinte comando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Atualizar todas as DLs qualificadas

Há duas maneiras de atualizar todas as DLs qualificadas.

> [!NOTE]
> O cmdlet Upgrade-Distribution não recebe dados da pipeline, por esse motivo, é necessário usar o operador "ForEach-Object{}" para executar com êxito.

1. Obtenha as DLs qualificadas no locatário e atualize-as usando o comando upgrade:

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Obtenha a lista de todas as DLs e atualize somente a DLs qualificada:

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a>Perguntas frequentes sobre como atualizar listas de distribuição para grupos do Office 365 no Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>Quais listas de distribuição não podem ser atualizadas?

Você só pode atualizar listas de distribuição simples, gerenciadas por nuvem, simples e não aninhadas. A tabela a seguir lista as listas de distribuição que **não podem** ser atualizadas.

|**Propriedade**|**Estará?**|
|:-----|:-----|
|Lista de distribuição gerenciada local.  <br/> |Não  <br/> |
|Listas de distribuição aninhadas. A lista de distribuição tem grupos filhos ou é membro de outro grupo.  <br/> |Não  <br/> |
|Listas de distribuição com membro **RecipientTypeDetails** diferente **de UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Não  <br/> |
|Lista de distribuição que tem mais de 100 proprietários  <br/> |Não  <br/> |
|Lista de distribuição que tem apenas membros, mas sem proprietário  <br/> |Não  <br/> |
|Lista de distribuição que tem um alias contendo caracteres especiais  <br/> |Não  <br/> |
|Se a lista de distribuição estiver configurada como um endereço de encaminhamento para a caixa de correio compartilhada  <br/> |Não  <br/> |
|Se o DL fizer parte da **restrição de remetente** em outra DL.  <br/> |Não  <br/> |
|Grupos de segurança  <br/> |Não  <br/> |
|Listas de distribuição dinâmica  <br/> |Não  <br/> |
|Listas de distribuição que foram convertidas em **RoomLists**  <br/> |Não  <br/> |
|Listas de distribuição onde o **MemberJoinRestriction** e/ou **MemberDepartRestriction** está **fechado**  <br/> |Não  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>Como verifico quais DLs estão qualificadas para atualização?

Se você quiser verificar se uma DL está qualificada ou não, execute o comando abaixo:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Se você deseja verificar quais DLs estão qualificados para atualização, basta executar o seguinte comando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Quem pode executar os scripts de atualização?

Pessoas com direitos de administrador global do Office 365 ou do Exchange.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Por que o cartão de visita ainda mostra uma lista de distribuição? O que devo fazer para impedir que uma lista de distribuição atualizada seja exibida na minha lista de sugestão automática?

- Para o Outlook: quando alguém tenta enviar um email no Outlook digitando o nome do grupo do Office 365 após a migração, o destinatário será resolvido como a lista de distribuição em vez do grupo. O cartão de visita do destinatário será o cartão de visita de listas de distribuição. Isso ocorre porque o cache de destinatários ou o cache de nomes de Nick no Outlook. O email será enviado com êxito para o grupo, mas pode causar confusão ao remetente.<br/>Você pode executar as etapas neste tópico, [informações sobre a lista de preenchimento automático do Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) para redefinir o cache, o que corrigirá esse problema.

- Para o Outlook na Web: no caso do Outlook na Web, o destinatário da lista de distribuição ainda permanecerá no cache. Você pode seguir as etapas em [remover nome sugerido ou endereço de email da lista de preenchimento automático](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) para atualizar o cache para ver o cartão de visita do grupo.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Os novos membros do grupo recebem um email de boas-vindas na caixa de entrada?

Não. A configuração para habilitar mensagens de boas-vindas é definida como false por padrão. Essa configuração afeta membros do grupo novo e existentes que podem ingressar após a conclusão da migração. Se o proprietário do grupo mais tarde permitir usuários convidados, os usuários convidados não receberão um email de boas-vindas na caixa de entrada. Membros convidados podem continuar a trabalhar com o grupo.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>E se uma ou algumas das DLs não forem atualizadas?

Há alguns casos nos quais o DL é qualificado, mas não pôde ser atualizado. O DL não é atualizado e permanece como um DL.

- Onde o administrador aplicou a **política de endereço de email do grupo** para os grupos em uma organização e tenta atualizar as DLs que não atendem aos critérios, a DL não é atualizada

- As DLs com **MemberJoinRestriction** ou **MemberDepartRestriction** definidas como **fechadas**não puderam ser atualizadas

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>O que acontece com a DL se a atualização do Eat falhar?

A atualização ocorrerá somente quando a chamada for enviada ao servidor. Se a atualização falhar, sua DLs estará intacta. Eles funcionarão da mesma forma que usavam para o.


