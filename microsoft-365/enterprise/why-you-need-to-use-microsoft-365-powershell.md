---
title: Por que você precisa usar o PowerShell para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 'Resumo: entenda por que você deve usar o PowerShell para gerenciar o Microsoft 365, em alguns casos com mais eficiência e em outros casos por necessidade.'
ms.openlocfilehash: 7220356cd79b03674661ace386fd1d38a7e39587
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686940"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="dd6a4-103">Por que você precisa usar o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="dd6a4-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dd6a4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd6a4-105">Com o centro de administração do Microsoft 365, você não só pode gerenciar suas licenças e contas de usuário do Microsoft 365, mas também pode gerenciar seus serviços do Microsoft 365, como o Exchange Online, o Teams e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-105">With the Microsoft 365 admin center, you can not only manage your Microsoft 365 user accounts and licenses, but you can also manage your Microsoft 365 services such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="dd6a4-106">No entanto, você também pode gerenciar esses elementos com os comandos do PowerShell, tirando proveito de um ambiente de linha de comando e de linguagem de script para velocidade, automação e capacidade adicional.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-106">However, you can also manage these elements with PowerShell commands, taking advantage of a command-line and scripting language environment for speed, automation, and additional capability.</span></span>
  
<span data-ttu-id="dd6a4-107">Neste artigo, mostraremos a você as seguintes maneiras em que você pode usar o PowerShell para gerenciar o Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-107">In this article, we'll show you these ways in which you can use PowerShell to manage Microsoft 365:</span></span>
  
- <span data-ttu-id="dd6a4-108">Revelar informações adicionais que você não consegue ver com o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-108">Reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="dd6a4-109">Configurar recursos e configurações somente para o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd6a4-109">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="dd6a4-110">Executar operações em massa</span><span class="sxs-lookup"><span data-stu-id="dd6a4-110">Perform bulk operations</span></span>
    
- <span data-ttu-id="dd6a4-111">Filtragem de dados</span><span class="sxs-lookup"><span data-stu-id="dd6a4-111">Filtering data</span></span>
    
- <span data-ttu-id="dd6a4-112">Imprimir ou salvar dados</span><span class="sxs-lookup"><span data-stu-id="dd6a4-112">Print or save data</span></span>
    
- <span data-ttu-id="dd6a4-113">Gerenciar entre serviços</span><span class="sxs-lookup"><span data-stu-id="dd6a4-113">Manage across services</span></span>
    
<span data-ttu-id="dd6a4-114">Antes de começar, entenda que o PowerShell para o Microsoft 365 é um conjunto de módulos para o Windows PowerShell, um ambiente de linha de comando para plataformas e serviços baseados no Windows.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-114">Before you begin, understand that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="dd6a4-115">Esse ambiente cria um idioma de Shell de comando que pode ser estendido com módulos adicionais e oferece uma maneira de executar comandos ou scripts simples ou complexos.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-115">This environment creates a command shell language that can be extended with additional modules and provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="dd6a4-116">Por exemplo, depois de instalar os módulos do PowerShell para o Microsoft 365 e se conectar à sua assinatura do Microsoft 365, você pode executar este comando para listar todas as caixas de correio de usuário do Microsoft Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-116">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run this command to list all of the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="dd6a4-117">A obtenção da lista de caixas de correio também pode ser feita facilmente usando o centro de administração do Microsoft 365, mas contar o número de itens em todas as listas de todos os sites de todos os seus aplicativos Web não pode ser feito facilmente.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-117">Getting the list of mailboxes can also be easily done using the Microsoft 365 admin center, but counting the number of items in all of the lists for all of the sites for all of your web apps cannot be easily done.</span></span>
  
<span data-ttu-id="dd6a4-118">Observe que o PowerShell para Microsoft 365 foi projetado para aumentar e aprimorar sua capacidade de gerenciar o Microsoft 365, não para substituir o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-118">Please note that PowerShell for Microsoft 365 is designed to augment and enhance your ability to manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="dd6a4-119">Como administrador, você deve se familiarizar com o uso do PowerShell para o Microsoft 365 porque há alguns procedimentos de configuração que só podem ser feitos com o PowerShell para os comandos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-119">As an administrator, you must become at least comfortable with using PowerShell for Microsoft 365 because there are some configuration procedures that can only be done with PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="dd6a4-120">Nesses casos, você precisará compreender como:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-120">In these cases, you will be required to understand how to:</span></span>
  
- <span data-ttu-id="dd6a4-121">Instale os módulos do PowerShell para Microsoft 365 (feito apenas uma vez para cada computador do administrador).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-121">Install the PowerShell for Microsoft 365 modules (done only once for each administrator computer).</span></span>
    
- <span data-ttu-id="dd6a4-122">Conecte-se à sua assinatura do Microsoft 365 (feita uma vez para cada sessão do PowerShell).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-122">Connect to your Microsoft 365 subscription (done once for each PowerShell session).</span></span>
    
- <span data-ttu-id="dd6a4-123">Reúna as informações necessárias para executar os comandos do PowerShell necessários para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-123">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="dd6a4-124">Execute o PowerShell para comandos do Microsoft 365 com êxito.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-124">Run the PowerShell for Microsoft 365 commands successfully.</span></span>
    
<span data-ttu-id="dd6a4-125">Depois de aprender essas habilidades básicas, não é necessário listar os usuários de caixa de correio com o comando **Get-Mailbox**, também não é preciso entender como criar um novo comando como o anterior para contar todos os itens nas listas de todos os sites para todos os seus aplicativos da Web.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-125">After learning these basic skills, you are not required to list your mailbox users with **Get-Mailbox** command, nor are you required to understand how to create a new command like the previous one to count all the items in all the lists for all of the sites for all of your web apps.</span></span> <span data-ttu-id="dd6a4-126">A Microsoft e a comunidade de administradores podem ajudá-lo com isso conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-126">Microsoft and the community of administrators can help you with that as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-additional-information-that-you-cannot-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="dd6a4-127">O PowerShell para Microsoft 365 pode revelar informações adicionais que você não consegue ver com o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-127">PowerShell for Microsoft 365 can reveal additional information that you cannot see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="dd6a4-128">O centro de administração 365 da Microsoft exibe muitas informações úteis, mas isso não significa que ela exibe todas as informações possíveis que a Microsoft 365 armazena em usuários, licenças, caixas de correio e sites.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-128">The Microsoft 365 admin center displays a lot of useful information, but that doesn't mean that it displays all the possible information that Microsoft 365 stores on users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="dd6a4-129">Veja um exemplo de **usuários e grupos** no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-129">Here is an example for **users and groups** in the Microsoft 365 admin center:</span></span>
  
![Exemplo de exibição de usuários e grupos no centro de administração do Microsoft 365.](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="dd6a4-131">Para muitas finalidades, isso exibe as informações que você precisa saber.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-131">For many purposes, this displays the information you need to know.</span></span> <span data-ttu-id="dd6a4-132">No entanto, há ocasiões em que você precisa de mais.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-132">However, there are times when you need more.</span></span> <span data-ttu-id="dd6a4-133">Por exemplo, o licenciamento da Microsoft 365 (e os recursos do Microsoft 365 disponíveis para um usuário) dependem parte da localização geográfica desse usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-133">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depend in part on that user's geographic location.</span></span> <span data-ttu-id="dd6a4-134">As políticas e os recursos que você pode estender para um usuário que reside nos Estados Unidos podem não ser os mesmos que as políticas e os recursos que você pode estender para um usuário que mora na Índia ou na Bélgica.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-134">The policies and features you can extend to a user who lives in the United States might not be the same as the policies and features you can extend to a user who lives in India or in Belgium.</span></span> <span data-ttu-id="dd6a4-135">Você pode usar o centro de administração do Microsoft 365 para determinar a localização geográfica de um usuário com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-135">You can use the Microsoft 365 admin center to determine a user's geographic location with these steps:</span></span>
  
1. <span data-ttu-id="dd6a4-136">Clique duas vezes no **Nome de exibição** do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-136">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="dd6a4-137">No painel de exibição de propriedades do usuário, clique em **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-137">In the user properties display pane, click **details**.</span></span>
    
3. <span data-ttu-id="dd6a4-138">Na exibição detalhes, clique em **detalhes adicionais**.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-138">In the details display, click **additional details**.</span></span>
    
4. <span data-ttu-id="dd6a4-139">Role para baixo até ver o cabeçalho **País ou região**:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-139">Scroll down until you see the heading **Country or region**:</span></span>
    
     ![Exemplo das informações de região de um usuário no centro de administração do Microsoft 365.](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="dd6a4-141">Escreva o nome de exibição e localização do usuário em um pedaço de papel ou copie e cole no Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-141">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span> 
    
<span data-ttu-id="dd6a4-142">Você deve repetir este procedimento para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-142">You must repeat this procedure for each user.</span></span> <span data-ttu-id="dd6a4-143">Quando há muitos usuários, isso pode ser uma tarefa entediante.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-143">For many users, this can be a tedious task.</span></span> <span data-ttu-id="dd6a4-144">Com o PowerShell para Microsoft 365, você pode exibir essas informações para todos os seus usuários com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-144">With PowerShell for Microsoft 365, you can display this information for all of your users with the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="dd6a4-145">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="dd6a4-146">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="dd6a4-147">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-147">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

> [!TIP]
>  <span data-ttu-id="dd6a4-148">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 ( **Get-AzureADUser** ), mas apenas exibir o nome e o local para cada usuário ( **selecione DisplayName, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-148">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription ( **Get-AzureADUser** ), but only display the name and location for each user ( **Select DisplayName, UsageLocation** ).</span></span>
  
<span data-ttu-id="dd6a4-149">Como o PowerShell para Microsoft 365 oferece suporte a um idioma de Shell de comando, você pode manipular ainda mais as informações obtidas do comando **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="dd6a4-149">Because PowerShell for Microsoft 365 supports a command shell language, you can further manipulate the information obtained from the **Get-AzureADUser** command.</span></span> <span data-ttu-id="dd6a4-150">Por exemplo, talvez você queira classificar esses usuários pelo local, agrupar todos os usuários brasileiros juntos, todos os usuários do Brasil, etc. Este é o comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-150">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, etc. Here is the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="dd6a4-151">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-151">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

> [!TIP]
>  <span data-ttu-id="dd6a4-152">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, mas apenas exibir o nome e o local de cada usuário e classificá-los primeiro pelo local e, em seguida, os nomes ( **classificar UsageLocation, DisplayName** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location, and then their names ( **Sort UsageLocation, DisplayName** ).</span></span>
  
<span data-ttu-id="dd6a4-p110">Você também pode usar a filtragem adicional. Por exemplo, se você quiser ver informações sobre usuários baseados no Brasil, use este comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p110">You can also employ additional filtering. For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="dd6a4-155">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-155">Here is an example of the display:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

> [!TIP]
>  <span data-ttu-id="dd6a4-156">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, cujo local é Brasil ( **onde {$ \_ . UsageLocation-EQ "BR"}** ) e, em seguida, exibe o nome e o local para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-156">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription whose location is Brazil ( **Where {$\_.UsageLocation -eq "BR"}** ), then display the name and location for each user.</span></span>
  
 <span data-ttu-id="dd6a4-157">**Uma rápida observação sobre domínios maiores**</span><span class="sxs-lookup"><span data-stu-id="dd6a4-157">**A Quick Note Regarding Larger Domains**</span></span>
  
<span data-ttu-id="dd6a4-158">Se você tiver um domínio muito grande com dezenas de milhares de usuários, tentar alguns dos exemplos mostrados neste artigo pode levar a "limitação".</span><span class="sxs-lookup"><span data-stu-id="dd6a4-158">If you have a very large domain with tens of thousands of users, trying some of the examples we show in this article could lead to "throttling."</span></span> <span data-ttu-id="dd6a4-159">Isso significa que, com base em itens como energia de computação e largura de banda de rede disponível, você está tentando fazer um pequeno demais ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-159">That means that, based on things like computing power and available network bandwidth, you're trying to do a little too much at one time.</span></span> <span data-ttu-id="dd6a4-160">Por isso, as organizações maiores podem querer dividir alguns desses comandos do PowerShell para Microsoft 365 em dois comandos.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-160">Because of that, larger organizations might want to split some of these PowerShell for Microsoft 365 commands into two commands.</span></span> <span data-ttu-id="dd6a4-161">Por exemplo, este comando retorna todas as contas de usuário e mostra o nome e o local de cada usuário:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-161">For example, this one command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="dd6a4-p112">Isso funciona bem com domínios menores. Em uma grande organização, no entanto, talvez você precise dividi-lo em dois comandos: um comando para armazenar as informações da conta do usuário em uma variável e outro comando para exibir as informações necessárias. Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p112">That works great for smaller domains. In a large organization, however, you might need to split that into two commands: one command to store the user account information in a variable and another command to display the needed information. Here is an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="dd6a4-165">A interpretação deste conjunto de comandos do PowerShell é:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-165">The interpretation of this set of PowerShell commands is:</span></span>
- <span data-ttu-id="dd6a4-166">Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-166">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="dd6a4-167">Exibir o conteúdo da variável $x, mas incluir apenas o nome e o local para cada usuário (**$x | Select DisplayName, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-167">Display the contents of the variable $x, but only include the name and location for each user ( **$x | Select DisplayName, UsageLocation** ).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="dd6a4-168">A Microsoft 365 tem recursos que você só pode configurar com o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-168">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="dd6a4-169">O centro de administração do Microsoft 365 destina-se a fornecer acesso às tarefas administrativas mais comuns ou significativas que se aplicam à maioria das pessoas.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-169">The Microsoft 365 admin center is intended to provide access to the most common or meaningful administrative tasks that apply to most people.</span></span> <span data-ttu-id="dd6a4-170">Em outras palavras, o centro de administração do Microsoft 365 foi projetado para que o administrador típico pudesse usar a ferramenta para realizar as tarefas de gerenciamento mais comuns.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-170">In other words, the Microsoft 365 admin center was designed so that the typical administrator could use the tool to carry out the most common management tasks.</span></span> <span data-ttu-id="dd6a4-171">Por essa definição, isso significa que há algumas tarefas que não podem ser concluídas usando o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-171">By this definition, that means that there are some tasks that can't be completed by using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="dd6a4-172">Por exemplo, o Centro de administração Skype for Business online fornece algumas opções para criar convites personalizados para reunião:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-172">For example, the Skype for Business Online Admin center provides a few options for creating custom meeting invitations:</span></span>
  
![Exemplo da exibição de convites de reunião personalizados no Centro de administração do Skype for Business Online.](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="dd6a4-p114">Com essas configurações, você pode adicionar um toque de personalização e profissionalismo a convites de reunião. No entanto, há muito mais configurações de reunião do que simplesmente criar convites personalizados de reunião. Por exemplo, por padrão, as reuniões permitem:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p114">With these settings, you can add a touch of personalization and professionalism to meeting invitations. However, there's more to meeting configuration settings than simply creating custom meeting invitations. For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="dd6a4-177">Usuários anônimos obterem entrada automática para cada reunião.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-177">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="dd6a4-178">Participantes gravem a reunião.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-178">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="dd6a4-179">Todos os usuários da sua organização serem designado como apresentadores quando eles entrarem na reunião.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-179">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="dd6a4-180">Essas configurações não estão disponíveis no centro de administração do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-180">These settings are not available from the Skype for Business Online Admin center.</span></span> <span data-ttu-id="dd6a4-181">No entanto, você pode controlá-los do PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-181">However, you can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="dd6a4-182">Veja um comando que desabilita essas três configurações:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-182">Here is a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="dd6a4-183">Este comando requer que você instale o [Módulo do PowerShell Skype for Business Online ](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-183">This command requires that you install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="dd6a4-184">A interpretação deste comando do PowerShell é: para as configurações para novas reuniões do Skype for Business online ( **set-CsMeetingConfiguration** ), desabilitar a permissão de usuários anônimos para obter a entrada automática de reuniões ( **-AdmitAnonymousUsersByDefault $false** ), desabilitar a capacidade dos participantes de registrarem reuniões (- **AllowConferenceRecording $false** ) e não designar todos os usuários da organização como apresentadores (- **DesignateAsPresenter "nenhum"** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-184">The interpretation of this PowerShell command is: For the settings for new Skype for Business Online meetings ( **Set-CsMeetingConfiguration** ), disable allowing anonymous users to gain automatic entrance to meetings ( **-AdmitAnonymousUsersByDefault $False** ), disable the ability for attendees to record meetings ( **-AllowConferenceRecording $False** ), and do not designate all users from your organization as presenters ( **-DesignateAsPresenter "None"** ).</span></span>
  
<span data-ttu-id="dd6a4-185">Se você mudar de ideia e desejar restaurar essas configurações padrão (todas são ativadas), execute este comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-185">If you change your mind and want to restore these default settings (all of them enabled), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="dd6a4-186">Isso é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-186">This is just one example.</span></span> <span data-ttu-id="dd6a4-187">Há outros, por isso, você, como administrador, precisa se familiarizar com a execução de comandos do PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-187">There are others, which is why you, as an administrator, need to be comfortable with running PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-carrying-out-bulk-operations"></a><span data-ttu-id="dd6a4-188">O PowerShell para Microsoft 365 é ótimo para realizar operações em massa</span><span class="sxs-lookup"><span data-stu-id="dd6a4-188">PowerShell for Microsoft 365 is great at carrying out bulk operations</span></span>

<span data-ttu-id="dd6a4-189">Historicamente, interfaces visuais como o centro de administração do Microsoft 365 são mais valiosas quando você tem uma única operação a ser executada.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-189">Historically, visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to perform.</span></span> <span data-ttu-id="dd6a4-190">Por exemplo, se for necessário desabilitar uma conta de usuário, você poderá usar o centro de administração do Microsoft 365 para localizar e desmarcar rapidamente uma caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-190">For example, if you need to disable one user account, you can use the Microsoft 365 admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="dd6a4-191">Isso pode ser mais simples do que executar uma operação semelhante no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-191">This can be simpler than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="dd6a4-192">Mas se você precisar alterar muitas coisas ou algumas coisas selecionadas dentro de um grande conjunto de outras coisas, o centro de administração do Microsoft 365 pode não ser o melhor uso do tempo.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-192">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best use of your time.</span></span> <span data-ttu-id="dd6a4-193">Por exemplo, se você tivesse que alterar o prefixo em milhares de números de telefone ou você precisava remover um usuário específico, Ken Myer, de todos os seus sites do SharePoint Online, como faria isso no centro de administração do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="dd6a4-193">For example, if you had to change the prefix on thousands of phone numbers or you needed to remove a specific user, Ken Myer, from all of your SharePoint Online sites, how would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="dd6a4-194">Para o último exemplo, você tem centenas de sites do SharePoint Online e não sabe nem mesmo saber quais são os que Ken Araújo é membro.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-194">For the latter example, you have several hundred SharePoint Online sites and you don't know even know which ones of which Ken Meyer is a member.</span></span> <span data-ttu-id="dd6a4-195">Isso significa que você terá que começar no centro de administração do Microsoft 365 e, em seguida, executar este procedimento para cada site:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-195">That means you'll have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="dd6a4-196">Clicar na **URL** do site.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-196">Click the **URL** of the site.</span></span>
    
2. <span data-ttu-id="dd6a4-197">Na caixa **Propriedades da coleção de sites**, clicar no link **Endereço de Site da Web** para abrir o site.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-197">In the **site collection properties** box, click the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="dd6a4-198">No site, clicar em **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-198">On the site, click **Share**.</span></span>
    
4. <span data-ttu-id="dd6a4-199">Na caixa de diálogo **Compartilhar** clicar no link que mostra a você todos os usuários que têm permissão para o site:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-199">In the **Share** dialog box click the link that shows you all the users who have permissions to the site:</span></span>
    
     ![Exemplo de como exibir os membros de um site do SharePoint Online no Centro de administração do SharePoint Online.](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="dd6a4-201">Na caixa de diálogo **Compartilhado com** clicar em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-201">In the **Shared With** dialog box, click **Advanced**.</span></span>
    
6. <span data-ttu-id="dd6a4-202">Rolar pela lista de usuários, encontrar e selecionar Paulo Araújo (supondo que ele tem permissões para o site) e então clicar em **Remover Permissões do Usuário**.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-202">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then click **Remove User Permissions**.</span></span>
    
<span data-ttu-id="dd6a4-203">Pode demorar muito tempo para você fazer isso em uma centena de sites.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-203">This can take a long time for several hundred sites.</span></span>
  
<span data-ttu-id="dd6a4-204">A alternativa é usar o PowerShell para o Microsoft 365 e o seguinte comando para remover Ken Myer de todos os sites:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-204">The alternative is to use PowerShell for Microsoft 365 and the following command to remove Ken Myer from all of your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="dd6a4-205">Este comando requer que você instale o [módulo do PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-205">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
> [!TIP]
>  <span data-ttu-id="dd6a4-206">A interpretação deste comando do PowerShell é: obter todos os sites do SharePoint na assinatura atual do Microsoft 365 ( **Get-SPOSite** ) e para cada site, remover Ken Araújo da lista de usuários que podem acessá-lo ( **foreach {remove-marido-site $ \_ . URL-LoginName "kenmyer@litwareinc.com"}** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-206">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription ( **Get-SPOSite** ) and for each site, remove Ken Meyer from the list of users who can access it ( **ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer@litwareinc.com"}** ).</span></span>
  
<span data-ttu-id="dd6a4-207">Como estamos dizendo para a Microsoft 365 para remover Ken Araújo de todos os sites, incluindo aqueles nos quais ele não tem acesso, a exibição desse comando mostrará erros para aqueles sites nos quais ele não tem acesso no momento.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-207">Because we are telling Microsoft 365 to remove Ken Meyer from every site, including those in which he does not have access, the display of this command will show errors for those sites in which he does not currently have access.</span></span> <span data-ttu-id="dd6a4-208">Podemos usar uma condição adicional nesse comando para remover Paulo Araújo somente de sites com ele esteja na lista de login, mas os erros listados não provocam danos aos sites.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-208">We can use an additional condition on this command to remove Key Meyer only from the sites that have him in their login list, but the listed errors cause no harm to the sites themselves.</span></span> <span data-ttu-id="dd6a4-209">Este comando pode levar alguns minutos para ser executado em centenas de sites, em vez de horas de trabalho por meio do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-209">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="dd6a4-p121">Este é outro exemplo de operação em massa. Use este comando para adicionar Mila Moraes, uma nova administradora do SharePoint, para todos os sites na organização:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p121">Here is another bulk operation example. Use this command to add Bonnie Kearney, a new SharePoint administrator, to all of the sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

> [!TIP]
>  <span data-ttu-id="dd6a4-212">A interpretação deste comando do PowerShell é: obter todos os sites do SharePoint na assinatura atual do Microsoft 365 e para cada site, permitir o acesso Kearney do Bonnie adicionando seu nome de logon ao grupo de membros do site ( **foreach {Add-marido-site $ \_ . URL-LoginName "bkearney@litwareinc.com"-Group "Members"}** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-212">The interpretation of this PowerShell command is:  Get all of the SharePoint sites in the current Microsoft 365 subscription and for each site, allow Bonnie Kearney access by adding her login name to the Members group of the site ( **ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}** ).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="dd6a4-213">O PowerShell para Microsoft 365 é ótimo para filtrar dados</span><span class="sxs-lookup"><span data-stu-id="dd6a4-213">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="dd6a4-214">O centro de administração do Microsoft 365 fornece várias maneiras diferentes de filtrar seus dados para localizar de forma rápida e fácil um subconjunto de informações direcionado.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-214">The Microsoft 365 admin center provides several different ways to filter your data to quickly and easily locate a targeted subset of information.</span></span> <span data-ttu-id="dd6a4-215">Por exemplo, o Exchange facilita a filtragem de praticamente qualquer propriedade da caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-215">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="dd6a4-216">Por exemplo, esta é uma lista de caixas de correio para todos os usuários que moram em Belo Horizonte:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-216">For example, here is the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![Exemplo de uma pesquisa avançada no centro de administração do Microsoft 365 para a lista de caixas de correio para todos os usuários que moram na cidade do belo horizonte.](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="dd6a4-p123">O Centro de administração do Exchange também permite que você combine critérios de filtro. Por exemplo, você pode encontrar as caixas de correio para todas as pessoas que moram em Belo Horizonte e que trabalham no departamento financeiro.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p123">The Exchange Admin center also lets you combine filter criteria. For example, you can find the mailboxes for all the people who live in Bloomington and who work in the Finance department.</span></span> 
  
<span data-ttu-id="dd6a4-p124">No entanto, existem limitações no que você pode fazer no Centro de administração do Exchange. Por exemplo, talvez você queira localizar caixas de correio de quem mora em Belo Horizonte ou Curitiba ou caixas de correio para todas as pessoas que não moram em Belo Horizonte.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p124">However, there are limitations to what you can do in the Exchange Admin center. For example, maybe you'd like to find the mailboxes of people who live in Bloomington or San Diego, or the mailboxes for all the people who don't live in Bloomington.</span></span> 
  
<span data-ttu-id="dd6a4-222">Com o PowerShell para Microsoft 365, você pode obter uma lista de caixas de correio para todas as pessoas que vivem nas cidades de Belo Horizonte ou San Diego com este comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-222">With PowerShell for Microsoft 365, you can get a list of mailboxes for all the people who live in the cities of Bloomington or San Diego with this command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="dd6a4-223">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-223">Here is an example of the display:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

> [!TIP]
>  <span data-ttu-id="dd6a4-224">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 que tenha uma caixa de correio nas cidades de San Diego ou Belo Horizonte ( **onde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e ($ \_ . City-eq "San Diego"-ou $ \_ . City-eq "Belo Horizonte")}** ), em seguida, exibe o nome e a cidade para cada ( **selecione DisplayName, City** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-224">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox in the cities of either San Diego or Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}** ), then display the name and city for each ( **Select DisplayName, City** ).</span></span>
  
<span data-ttu-id="dd6a4-225">Este é o comando para listar todas as caixas de correio de quem mora em qualquer lugar, exceto Belo Horizonte:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-225">To list all the mailboxes for people who live anywhere except Bloomington, here is the command:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="dd6a4-226">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-226">Here is an example of the display:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

> [!TIP]
>  <span data-ttu-id="dd6a4-227">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365 que possua uma caixa de correio não localizada na cidade de Belo Horizonte ( **onde {$ \_ . RecipientTypeDetails-EQ "UserMailbox"-e $ \_ . City-NE "Belo Horizonte"}** ) e, em seguida, exiba o nome e a cidade de cada um.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-227">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington ( **Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}** ), then display the name and city for each.</span></span>
  
<span data-ttu-id="dd6a4-228">Você também pode usar caracteres curinga em seus filtros do PowerShell para corresponder a parte de um nome.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-228">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="dd6a4-229">Por exemplo, suponha que você esteja procurando uma conta de usuário, e tudo o que você pode lembrar é que seu sobrenome era Anderson, ou talvez Gonçalves, ou talvez seja Gomes.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-229">For example, suppose you're looking for a user account, and all you can remember is that their last name was Anderson, or maybe Henderson, or maybe it was Jorgenson.</span></span>
  
<span data-ttu-id="dd6a4-230">Você pode rastrear esse usuário no centro de administração do Microsoft 365 usando a ferramenta de pesquisa e executando três pesquisas diferentes:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-230">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="dd6a4-231">Uma para  *Mendes*</span><span class="sxs-lookup"><span data-stu-id="dd6a4-231">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="dd6a4-232">Uma para  *Gonçalves*</span><span class="sxs-lookup"><span data-stu-id="dd6a4-232">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="dd6a4-233">Uma para  *Gomes*</span><span class="sxs-lookup"><span data-stu-id="dd6a4-233">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="dd6a4-234">Como todos os três desses nomes terminam em "Son", você pode dizer ao PowerShell para exibir todos os usuários cujo nome termina em "Son".</span><span class="sxs-lookup"><span data-stu-id="dd6a4-234">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="dd6a4-235">Este é o comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-235">Here is the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

> [!TIP]
>  <span data-ttu-id="dd6a4-236">A interpretação deste comando do PowerShell é: obter todos os usuários na assinatura atual do Microsoft 365, mas usar um filtro que liste apenas os usuários cujos sobrenomes terminam em "Son" ( **-Filter ' {LastName-like " \* Son"} '** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-236">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" ( **-Filter '{LastName -like "\*son"}'** ).</span></span> <span data-ttu-id="dd6a4-237">O \* significa um conjunto de caracteres, que são letras no caso do sobrenome do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-237">The \* stands for any set of characters, which are letters in the case of the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="dd6a4-238">O PowerShell para Microsoft 365 facilita a impressão ou a gravação de dados</span><span class="sxs-lookup"><span data-stu-id="dd6a4-238">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="dd6a4-239">O centro de administração 365 da Microsoft permite exibir listas de dados.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-239">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="dd6a4-240">Veja um exemplo do centro de administração do Skype for Business online que exibe uma lista de usuários que foram habilitados para o Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-240">Here is an example of the Skype for Business Online Admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![Exemplo do Centro de administração do Skype for Business Online exibindo uma lista de usuários que foram habilitados para o Skype for Business Online.](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="dd6a4-242">Para salvar essas informações em um arquivo, você deve copiá-lo e colá-lo em um documento ou no Excel.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-242">To save that information to a file, you must copy and paste it into a document or Excel.</span></span> <span data-ttu-id="dd6a4-243">Em ambos os casos, a cópia pode exigir uma formatação adicional.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-243">In either case, the copy might require additional formatting.</span></span> <span data-ttu-id="dd6a4-244">Além disso, o centro de administração do Microsoft 365 não oferece uma maneira de imprimir diretamente a lista exibida.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-244">Additionally, the Microsoft 365 admin center does not provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="dd6a4-245">Felizmente, você pode usar o PowerShell para não apenas exibir a lista, mas salvá-la em um arquivo que pode ser facilmente importado para o Excel.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-245">Fortunately, you can use PowerShell to not only display the list, but save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="dd6a4-246">Veja a seguir um exemplo de comando para salvar dados de usuário do Skype for Business online em um arquivo de valores separados por vírgula (CSV), um arquivo que pode ser importado facilmente como uma tabela em uma planilha do Excel:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-246">Here is an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, a file that can be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="dd6a4-247">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-247">Here is an example of the display:</span></span>
  
![Exemplo de uma tabela importada para uma planilha do Excel para os dados do usuário do Skype for Business Online que foram salvos em um arquivo de valores separados por vírgula (CSV).](../media/o365-powershell-data-in-excel.png)
  
> [!TIP]
>  <span data-ttu-id="dd6a4-249">A interpretação deste comando do PowerShell é: obter todos os usuários do Skype for Business online na assinatura atual do Microsoft 365 ( **Get-CsOnlineUser** ), obter apenas o nome de usuário, o UPN e o local ( **selecione DisplayName, userPrincipalName, UsageLocation** ) e, em seguida, salve essas informações no arquivo CSV denominado c: logs \\ \\SfBUsers.csv ( **Export-CSV-Path "C: \\ logs \\SfBUsers.csv"-NoTypeInformation**</span><span class="sxs-lookup"><span data-stu-id="dd6a4-249">The interpretation of this PowerShell command is: Get all of the Skype for Business Online users in the current Microsoft 365 subscription ( **Get-CsOnlineUser** ), obtain only the user name, UPN, and location ( **Select DisplayName, UserPrincipalName, UsageLocation** ), and then save that information in CSV file named C:\\Logs\\SfBUsers.csv ( **Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation** ).</span></span>
  
<span data-ttu-id="dd6a4-p131">Você também pode usar opções para salvar a lista como um arquivo XML ou como uma página HTML. Na verdade, com os comandos adicionais do PowerShell, você poderia salvá-la diretamente como um arquivo do Excel, com qualquer formatação personalizada desejada.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p131">You can also use options to save this list as an XML file or as an HTML page. In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you desire.</span></span> 
  
<span data-ttu-id="dd6a4-252">Você também pode enviar a saída de um comando do PowerShell que exibe uma lista diretamente para a impressora padrão no Windows.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-252">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="dd6a4-253">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-253">Here is an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="dd6a4-254">O seu documento impresso ficará assim:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-254">Here's what your printed document will look like:</span></span>
  
![Exemplo de um documento impresso que foi a saída de um comando do PowerShell listado diretamente para a impressora padrão no Windows.](../media/o365-powershell-printed-data.png)
  
> [!TIP]
>  <span data-ttu-id="dd6a4-256">A interpretação deste comando do PowerShell é: obter todos os usuários do Skype for Business online na assinatura atual do Microsoft 365, obter apenas o nome de usuário, o UPN e o local e enviá-las para a impressora padrão do Windows ( **Out-Printer** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-256">The interpretation of this PowerShell command is:  Get all of the Skype for Business Online users in the current Microsoft 365 subscription, obtain only the user name, UPN, and location, and then send that information to the default Windows printer ( **Out-Printer** ).</span></span>
  
<span data-ttu-id="dd6a4-257">O documento impresso tem a mesma formatação simples que a exibição na janela de comando do PowerShell, mas depois que você tiver criado um comando do PowerShell para listar o que precisa, basta adicionar **| Out-Printer** para o final do comando para obter uma cópia impressa para trabalhar.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-257">The printed document has the same simple formatting as the display within the PowerShell command window, but once you have created a PowerShell command to list what you need, you just add **| Out-Printer** to the end of the command to get a hard copy to work from.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="dd6a4-258">O PowerShell para Microsoft 365 permite que você gerencie nos produtos de servidor</span><span class="sxs-lookup"><span data-stu-id="dd6a4-258">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="dd6a4-259">Os diferentes componentes que compõem o Microsoft 365 são projetados para funcionar juntos.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-259">The different components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="dd6a4-260">Por exemplo, suponha que você adicione um novo usuário ao Microsoft 365 e, quando fizer isso, especifique informações como o departamento e o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-260">For example, suppose you add a new user to Microsoft 365 and, when you do, you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="dd6a4-261">Essas informações estarão disponíveis se você acessar as informações do usuário usando qualquer um dos serviços do Microsoft 365: Skype for Business Online, Exchange ou SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-261">That information will then be available if you access the user's information using any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint Online.</span></span>
  
<span data-ttu-id="dd6a4-p134">Mas isso se trata de informações genéricas que existem em todo o conjunto de produtos. Informações específicas do produto, por exemplo, as informações sobre uma caixa de correio do Exchange do usuário, geralmente não estão disponíveis em todo o pacote. Por exemplo, se você deseja saber se a caixa de correio do usuário está habilitada ou não, essas informações estão disponíveis somente no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-p134">But that's for common information that spans the suite of products. Product-specific information-for example, information about a user's Exchange mailbox-is typically not available across the suite. For example, if you want to know if a user's mailbox is enabled or not, that information is available only in the Exchange Admin center.</span></span> 
  
<span data-ttu-id="dd6a4-265">Suponha que você queira fazer um relatório que mostre as seguintes informações sobre todos os seus usuários:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-265">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="dd6a4-266">O nome de exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="dd6a4-266">The user's display name</span></span>
    
- <span data-ttu-id="dd6a4-267">Se o usuário está licenciado para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-267">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="dd6a4-268">Se a caixa de correio do Exchange do usuário está habilitada</span><span class="sxs-lookup"><span data-stu-id="dd6a4-268">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="dd6a4-269">Se o usuário está habilitado para o Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="dd6a4-269">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="dd6a4-270">No momento, você não pode usar o centro de administração do Microsoft 365 para produzir um relatório desse tipo com facilidade.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-270">You currently cannot use the Microsoft 365 admin center to easily produce such a report.</span></span> <span data-ttu-id="dd6a4-271">Em vez disso, você precisará criar um documento separado para armazenar as informações, como uma planilha do Excel, e obter todos os nomes de usuário e informações de licenciamento do centro de administração do Microsoft 365, obter informações de caixa de correio do centro de administração do Exchange, obter informações do Skype for Business Online do centro de administração do Skype for Business Online e agrupar e combinar essas informações.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-271">Instead, you'll have to create a separate document to store the information, like an Excel worksheet, and get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then collate and combine that information.</span></span>
  
<span data-ttu-id="dd6a4-272">A alternativa é usar um script do PowerShell para compilar esse relatório para você.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-272">The alternative is to use a PowerShell script to compile that report for you.</span></span>
  
<span data-ttu-id="dd6a4-273">O script de exemplo a seguir é mais complicado do que os comandos que vimos até agora neste artigo.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-273">The following example script is more complicated than the commands you have seen so far in this article.</span></span> <span data-ttu-id="dd6a4-274">No entanto, ele mostra o potencial de usar o PowerShell para criar modos de exibição de informações que são muito difíceis de fazer caso contrário.</span><span class="sxs-lookup"><span data-stu-id="dd6a4-274">But, it shows the potential of using PowerShell to create views of information that are very difficult to do otherwise.</span></span> <span data-ttu-id="dd6a4-275">Aqui está o script que pode compilar e exibir a lista necessária:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-275">Here is the script that can compile and display the needed list:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="dd6a4-276">Este é um exemplo de exibição:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-276">Here is an example of the display:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="dd6a4-277">A interpretação deste script do PowerShell é:</span><span class="sxs-lookup"><span data-stu-id="dd6a4-277">The interpretation of this PowerShell script is:</span></span>  

- <span data-ttu-id="dd6a4-278">Obter todos os usuários na assinatura atual do Microsoft 365 e armazenar as informações em uma variável chamada $x ( **$x = Get-AzureADUser** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-278">Get all of the users in the current Microsoft 365 subscription and store the information in a variable named $x ( **$x = Get-AzureADUser** ).</span></span>
- <span data-ttu-id="dd6a4-279">Iniciar um loop que é executado em todos os usuários na variável denominada $x (**foreach ($i in $x)**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-279">Start a loop that runs over all the users in the variable named $x ( **foreach ($i in $x)** ).</span></span>  
- <span data-ttu-id="dd6a4-280">Definir uma variável chamada $y e armazenar as informações da caixa de correio do usuário nela (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-280">Define a variable named $y and store the user's mailbox information in it ( **$y = Get-Mailbox -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="dd6a4-281">Adicionar uma nova propriedade à informação do usuário chamada IsMailBoxEnabled e configurá-la para o valor da propriedade IsMailBoxEnabled da caixa de correio do usuário (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-281">Add a new property to the user information named IsMailBoxEnabled and set it to the value of the IsMailBoxEnabled property of the user's mailbox ( **$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled** ).</span></span>
- <span data-ttu-id="dd6a4-282">Definir uma variável chamada $y e armazenar as informações do usuário do Skype for Business Online nela (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-282">Define a variable named $y and store the user's Skype for Business Online information in it ( **$y = Get-CsOnlineUser -Identity $i.UserPrincipalName** ).</span></span>
- <span data-ttu-id="dd6a4-283">Adicionar uma nova propriedade à informação do usuário chamada EnabledForSfB e configurá-la para o valor da propriedade Habilitada das informações do usuário do Skype for Business Online (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-283">Add a new property to the user information named EnabledForSfB and set it to the value of the Enabled property of the user's Skype for Business Online information ( **$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled** ).</span></span>
- <span data-ttu-id="dd6a4-284">Exibir a lista de usuários, mas incluir apenas os nomes, informar se eles estão licenciados e incluir as duas novas propriedades que indicam se as caixas de correio deles estão ativadas e se elas estão habilitadas para o Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span><span class="sxs-lookup"><span data-stu-id="dd6a4-284">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online ( **$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB** ).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd6a4-285">Veja também</span><span class="sxs-lookup"><span data-stu-id="dd6a4-285">See also</span></span>

[<span data-ttu-id="dd6a4-286">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-286">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dd6a4-287">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd6a4-287">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="dd6a4-288">Usar o PowerShell do Windows para criar relatórios no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd6a4-288">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)

