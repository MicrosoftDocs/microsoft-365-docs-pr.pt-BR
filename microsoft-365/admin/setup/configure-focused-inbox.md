---
title: Configurar a Caixa de Entrada Destaques para todos em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.openlocfilehash: eaf2c7623c81b24670a7b512c6311f0af036b255
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644598"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurar a Caixa de Entrada Destaques para todos na sua organização

  Se você é responsável por configurar como o e-mail funciona para TODOS em uma empresa, este artigo é para você!  Ele explica como personalizá-lo ou desativá-lo para a sua empresa e responde a perguntas sobre [Perguntas frequentes](#faq-for-focused-inbox).  <br/> Se você quiser desligar a Caixa de Entrada Destaques por si mesmo, confira [Desativar a Caixa de Entrada Destaques](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
Se quiser garantir que seus usuários recebam mensagens de email específicas de negócios, por exemplo, do RH ou da folha de pagamentos, você pode configurar a Caixa de Entrada Destaques para que essas mensagens alcancem o modo de exibição Destaques. Você também pode controlar se os usuários da sua organização veem a Caixa de Entrada Destaques nas caixas de correio deles.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Ativar ou desativar a Caixa de Entrada Destaques na sua organização

Usar o PowerShell para ativar ou desativar a Caixa de Entrada Destaques para todos da sua organização. Você quer fazer isso no centro de administração do Office 365? Informe nossa equipe de engenharia. **[Vote aqui!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Para desativar a Caixa de Entrada Destaques:**
  
O exemplo a seguir do PowerShell **desativa** a Caixa de Entrada Destaques na organização. No entanto, ele não bloqueia a disponibilidade do recurso para os usuários; ou seja, eles ainda poderão reativar a Caixa de Entrada Destaques em cada um dos respectivos clientes. 
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Você deve ter permissões para poder realizar esses procedimentos. Para ver quais são as permissões necessárias, confira a entrada "Regras de transporte" no artigo [Permissões de política e conformidade de mensagens](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
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

Os usuários verão o modo de exibição Destaques somente após fechar e reiniciar o Outlook. Depois disso, eles verão uma dica na interface do usuário do programa mostrando a opção de usar a nova Caixa de Entrada Destaques.
  
![Uma imagem da aparência da Caixa de Entrada Destaques quando um usuário abre pela primeira vez o Outlook na Web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Se estiver migrando do Email secundário para a Caixa de Entrada Destaques, eles poderão decidir habilitá-la ("Experimente") ou ignorar o recurso. Se o usuário tiver vários clientes (compatíveis), eles poderão ativar/desativar a Caixa de Entrada Destaques individualmente em cada um deles. A dica tem esta aparência:
  
![Imagem mostrando a aparência da Caixa de Entrada Destaques quando ela é implantada para os usuários e o Outlook é reaberto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Quando um usuário decide começar a usar a Caixa de Entrada Destaques, o Email secundário é desabilitado automaticamente. A pasta Email secundário é convertida em uma pasta padrão, que permite ao usuário renomeá-la ou excluí-la.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Ative ou desative a Caixa de Entrada Destaques para determinados usuários

Este exemplo **desativa** a Caixa de Entrada Destaques para Henrique Cunha na organização Contoso. No entanto, ele não bloqueia a disponibilidade do recurso para ele. Se ele quiser, ainda poderá reativar a Caixa de Entrada Destaques em cada um dos próprios clientes. 
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Você precisa ter permissões antes de executar estes procedimentos. Para ver quais permissões são necessárias, confira a entrada "Regras de transporte" no tópico Permissões de política e conformidade de mensagens.
    
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
    
2. Você deve ter permissões para poder realizar esses procedimentos. Para ver quais são as permissões necessárias, confira a entrada "Regras de transporte" no artigo [Permissões de política e conformidade de mensagens](https://go.microsoft.com/fwlink/p/?LinkId=829796).

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
 
Recebemos relatórios informando que o Email secundário subitamente parou de funcionar para alguns usuários. Se isso acontecer, será possível habilitá-lo novamente para usuários específicos. Veja [Configuração do Email secundário para sua organização](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Perguntas frequentes sobre a Caixa de Entrada Destaques

Aqui estão respostas para Perguntas frequentes sobre a Caixa de Entrada Destaques. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Posso controlar como distribuir a Caixa de Entrada Destaque na minha organização?

Sim. Você pode ativar ou desativar a Caixa de Entrada Destaques para toda a sua organização ou para usuários específicos. Veja acima.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>O recurso Caixa de Entrada Destaques está disponível APENAS para clientes do Office 2016?

Sim, somente usuários com o Office 2016 são afetados. O recurso não será disponibilizado para o Outlook 2013 e versões anteriores.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Quanto tempo leva para as alterações da Caixa de Entrada Destaques serem feitas no Outlook?

Depois que você ativar ou desativar a Caixa de Entrada Destaques, as configurações serão efetivadas quando os usuários fecharem e reiniciarem o Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>O que acontece com o Email Secundário depois que eu ativar a Caixa de Entrada Destaques?

Após a mudança, você deixará de receber emails menos importantes na pasta Email secundário. Em vez disso, os emails serão divididos entre as guias Destaques e Outros na Caixa de Entrada. O mesmo algoritmo que movia itens para a pasta de Email secundário agora habilita a Caixa de Entrada Destaques. Isso significa que todos os emails que foram definidos para serem movidos para a pasta de Email secundário agora serão movidos para a pasta Outros. As mensagens que já estão na pasta de Email secundário permanecerão nesse local até que você decida excluí-las ou movê-las.
  
Confira esta postagem de [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP da Microsoft: [Como a Caixa de Entrada Destaques substituirá o Email Secundário no Office 365](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Posso manter os usuários no Clutter? O que a Microsoft recomenda sobre o uso do Email Secundário e da Caixa de Entrada Destaques?

Sim, você pode manter os usuários no Email secundário e desabilitar a Caixa de Entrada Destaques; no entanto, futuramente o Email Secundário será totalmente substituído pela Caixa de Entrada Destaques, portanto, a Microsoft recomenda migrar para a Caixa de Entrada Destaques agora. Para saber mais sobre quando usar a pasta Email secundário no Exchange Online, confira a seguinte postagem de blog: [Atualização sobre a Caixa de Entrada Destaques e nossos planos para o Email secundário](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Devo desabilitar o Clutter dos meus usuários finais se migrarmos para a Caixa de Entrada Destaques?

Não. É possível desabilitar o Email Secundário para uma caixa de correio explicitamente executando o Set-Clutter. No entanto, se fizer isso, o proprietário da caixa de correio verá que mensagens que anteriormente foram redirecionadas para a pasta Email Secundário permanecerão na Caixa de Entrada e será necessário processar essas mensagens até que o cliente seja atualizado para uma versão ofereça suporte para a Caixa de Entrada Destaques. Portanto, é melhor não desabilitar o Email Secundário até que os clientes atualizados estejam disponíveis.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Por que há dois cmdlets diferentes para gerenciar a Caixa de Entrada Destaques?

Há dois estados associados à Caixa de Entrada Destaques.
  
- **Nível da Organização**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado. 
    
- **Nível da Caixa de Correio**: estado da Caixa de Entrada Destaques e um carimbo de data/hora de última atualização associado. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Como o Outlook decide mostrar a experiência da Caixa de Entrada Destaques com esses dois estados?

O Outlook decide mostrar a experiência escolhendo cmdlet que tem o carimbo de data/hora mais recente. Por padrão, ambos os carimbos são "nulos" e, nesse caso, o recurso é habilitado.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Por que o cmdlet Get-FocusedInbox retorna "true" quando eu desativo a Caixa de Entrada Destaques na minha organização?

Há dois cmdlets para controlar a Caixa de Entrada Destaques. Quando você executa Get-FocusedInbox para uma caixa de correio, ele retorna o estado do nível da caixa de correio do recurso. A experiência do Outlook é escolhida com base em qual estado de cmdlet foi modificado pela última vez.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Posso executar um script para ver quem ativou a Caixa de Entrada Destaques?

Não, e isso é o padrão. A ativação da Caixa de Entrada Destaques é uma configuração do lado do cliente, portanto, tudo o que o cmdlet pode fazer é informar se a caixa de correio do usuário está qualificada para a experiência do cliente. É possível que ela esteja ativada simultaneamente em alguns clientes e desativada em outros, por exemplo, ativada no aplicativo Outlook e no Outlook Mobile, mas desativada no Outlook na Web.
