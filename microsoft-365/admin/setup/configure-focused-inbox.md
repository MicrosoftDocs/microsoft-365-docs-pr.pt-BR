---
title: Configurar a Caixa de Entrada Destaques para todos em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Aprenda a configurar a Caixa de Entrada Destaques para todos ou usuários específicos da sua organização. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779924"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurar a Caixa de Entrada Destaques para todos na sua organização

  Se você é responsável por configurar como o e-mail funciona para TODOS em uma empresa, este artigo é para você!  Ele explica como personalizá-lo ou desativá-lo para a sua empresa e responde a perguntas sobre [Perguntas frequentes](#faq-for-focused-inbox).  <br/> Se você quiser desligar a Caixa de Entrada Destaques por si mesmo, confira [Desativar a Caixa de Entrada Destaques](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Ativar ou desativar a Caixa de Entrada Destaques na sua organização

Usar o PowerShell para ativar ou desativar a Caixa de Entrada Destaques para todos da sua organização. Você quer fazer isso no centro de administração do Office 365? Informe nossa equipe de engenharia. **[Vote aqui!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Para desativar a Caixa de Entrada Destaques:**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. Execute o cmdlet **Get-OrganizationConfig**. 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. Procure **FocusedInboxOn** para ver a configuração atual: 
    
    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Execute o cmdlet **Get-OrganizationConfig** novamente e você verá que FocusedInboxOn está definido como $false, o que significa que ele está desativado. 
    
 **Para ativar a Caixa de Entrada Destaques:**
  
- Na Etapa 5 acima, execute o cmdlet a seguir para ativar a Caixa de Entrada Destaques.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>O que os usuários veem depois que ativo a Caixa de Entrada Destaques? 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![Uma imagem da aparência da Caixa de Entrada Destaques quando um usuário abre pela primeira vez o Outlook na Web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![Imagem mostrando a aparência da Caixa de Entrada Destaques quando ela é implantada para os usuários e o Outlook é reaberto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Ative ou desative a Caixa de Entrada Destaques para determinados usuários

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. Execute o cmdlet **Get-FocusedInbox**, por exemplo: 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Procure FocusedInboxOn para ver a configuração atual:
    
    ![Resposta do PowerShell no estado da Caixa de Entrada Destaques.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Execute o cmdlet a seguir para desativar a Caixa de Entrada Destaques.
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. OU, execute o cmdlet a seguir para ativá-la:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Use a interface do usuário para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
    
2. Navegue até **Regras de** \> **fluxo de mensagens**. Clique em ![Ícone Adicionar EAC](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e clique em **Criar uma nova regra...**. 
    
3. Quando concluir a criação da nova regra, clique em **Salvar** para iniciá-la. 
    
    A imagem a seguir mostra um exemplo em que todas as mensagens com o assunto "Departamento da Folha de Pagamento" são entregues na Caixa de Entrada Destaques.
    
    ![folha de pagamento focusedinbox](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Use o PowerShell para criar uma regra de transporte para direcionar mensagens de e-mail ao modo de exibição Destaques para todos os usuários

1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. Execute o comando a seguir para permitir que todas as mensagens do "Departamento da Folha de Pagamento", por exemplo, sejam entregues na Caixa de Entrada Destaques.
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> Neste exemplo, tanto "X-MS-Exchange-Organization-BypassFocusedInbox" quanto "true" diferenciam maiúsculas de minúsculas.
> Além disso, a Caixa de Entrada Destaques respeitará o cabeçalho X que ignora o Clutter, portanto, se você usar essa configuração no Clutter, ela será usada na Caixa de Entrada Destaques. Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Você pode verificar os cabeçalhos das mensagens de email para conferir se elas estão chegando na Caixa de Entrada por ignorar a regra de transporte da Caixa de Entrada Destaques. Escolha uma mensagem de email de uma caixa de correio na sua organização que tenha a regra de transporte da Caixa de Entrada Destaques aplicada. Examine os cabeçalhos marcados na mensagem e você verá o cabeçalho **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Isso significa que a regra está sendo ignorada. Confira o artigo [Exibir as informações de cabeçalho de Internet por uma mensagem de e-mail](https://go.microsoft.com/fwlink/p/?LinkId=822530) para obter mais informações sobre como encontrar as informações de cabeçalho. 
 
## <a name="turn-onoff-clutter"></a>Ativar/desativar o Clutter
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Perguntas frequentes sobre a Caixa de Entrada Destaques

Aqui estão respostas para Perguntas frequentes sobre a Caixa de Entrada Destaques. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Posso controlar como distribuir a Caixa de Entrada Destaque na minha organização?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>O recurso Caixa de Entrada Destaques está disponível APENAS para clientes do Office 2016?

Sim, somente usuários com o Office 2016 são afetados. O recurso não será disponibilizado para o Outlook 2013 e versões anteriores.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Quanto tempo leva para as alterações da Caixa de Entrada Destaques serem feitas no Outlook?

Depois que você ativar ou desativar a Caixa de Entrada Destaques, as configurações serão efetivadas quando os usuários fecharem e reiniciarem o Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>O que acontece com o Email Secundário depois que eu ativar a Caixa de Entrada Destaques?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Confira esta postagem de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP da Microsoft: [Como a Caixa de Entrada Destaques substituirá o Email Secundário no Office 365](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Posso manter os usuários no Clutter? O que a Microsoft recomenda sobre o uso do Email Secundário e da Caixa de Entrada Destaques?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Devo desabilitar o Clutter dos meus usuários finais se migrarmos para a Caixa de Entrada Destaques?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Por que há dois cmdlets diferentes para gerenciar a Caixa de Entrada Destaques?

Há dois estados associados à Caixa de Entrada Destaques.
  
- **Nível da Organização**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado. 
    
- **Nível da Caixa de Correio**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Como o Outlook decide mostrar a experiência da Caixa de Entrada Destaques com esses dois estados?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Por que o cmdlet Get-FocusedInbox retorna "true" quando eu desativo a Caixa de Entrada Destaques na minha organização?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Posso executar um script para ver quem ativou a Caixa de Entrada Destaques?

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
