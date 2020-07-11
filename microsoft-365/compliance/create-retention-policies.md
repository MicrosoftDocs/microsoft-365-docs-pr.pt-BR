---
title: Criar e configurar políticas de retenção para reter ou excluir o conteúdo automaticamente
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Use uma política de retenção para decidir de forma proativa se deseja reter o conteúdo, excluí-lo ou ambos: reter e em seguida excluir o conteúdo; aplicar uma única política para a organização inteira ou a locais ou usuários específicos; e aplicar uma política a todo o conteúdo ou ao conteúdo que cumpra determinadas condições.'
ms.openlocfilehash: ab6a61e0cedfd91d642823f0c459a5a1699df000
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083613"
---
# <a name="create-and-configure-retention-policies"></a><span data-ttu-id="4f980-103">Criar e configurar políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="4f980-103">Create and configure retention policies</span></span>

><span data-ttu-id="4f980-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4f980-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4f980-105">Use uma política de retenção para decidir proativamente se deseja reter o conteúdo, excluí-lo ou ambos; reter e depois excluir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-105">Use a retention policy to decide proactively whether to retain content, delete content, or both - retain and then delete the content.</span></span> 

<span data-ttu-id="4f980-106">Para saber mais sobre o funcionamento das políticas de retenção, confira [Saiba mais sobre políticas de retenção](retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f980-106">For information about how retention policies work, see [Learn about retention policies](retention-policies.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4f980-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4f980-107">Before you begin</span></span>

<span data-ttu-id="4f980-108">Os membros de sua equipe de conformidade que criarão e gerenciarão políticas de retenção precisam de permissões para o [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="4f980-108">Members of your compliance team who will create and manage retention policies need permissions to the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="4f980-109">Por padrão, o administrador de locatário (administrador global) terá acesso a esse local e pode dar acesso a outras pessoas e aos responsáveis pela conformidade, sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você adicione usuários ao grupo de função de administrador **Administrador de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="4f980-109">By default, the tenant admin (global administrator) has access to this location and can give compliance officers and other people access without giving them all the permissions of a tenant admin. To grant permissions for this limited administration, we recommend that you add users to the **Compliance Administrator** admin role group.</span></span> <span data-ttu-id="4f980-110">Para obter instruções, confira [Fornecer aos usuários acesso ao Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="4f980-110">For instructions, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="4f980-111">Essas permissões são necessárias somente para criar e aplicar uma política de retenção.</span><span class="sxs-lookup"><span data-stu-id="4f980-111">These permissions are required only to create and apply a retention policy.</span></span> <span data-ttu-id="4f980-112">A pessoa que configura a política de retenção não exige acesso ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-112">The person configuring the retention policy doesn't require access to the content.</span></span>

## <a name="create-and-configure-a-retention-policy"></a><span data-ttu-id="4f980-113">Criar e configurar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="4f980-113">Create and configure a retention policy</span></span>

1. <span data-ttu-id="4f980-114">No [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/), selecione **Políticas** > **Retenção**.</span><span class="sxs-lookup"><span data-stu-id="4f980-114">From the [Microsoft 365 compliance center](https://compliance.microsoft.com/), select **Policies** > **Retention**.</span></span>

2. <span data-ttu-id="4f980-115">Selecione **Nova Política de Retenção** ou edite uma política de retenção de saída.</span><span class="sxs-lookup"><span data-stu-id="4f980-115">Select **New retention policy** or edit an exiting retention policy.</span></span>

3. <span data-ttu-id="4f980-116">Para **Configurações**, primeiro especifique as opções de configuração para manter e excluir o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-116">For **Settings**, first specify the configuration options for retaining and deleting content.</span></span> <span data-ttu-id="4f980-117">Você pode criar uma política de retenção que apenas retenha o conteúdo sem excluir, retenha e exclua após um período especificado ou apenas exclua o conteúdo após um período especificado.</span><span class="sxs-lookup"><span data-stu-id="4f980-117">You can create a retention policy that just retains content without deleting, retains and then deletes after a specified period of time, or just deletes content after a specified period of time.</span></span> <span data-ttu-id="4f980-118">Para saber mais, confira [Configurações de retenção e exclusão de conteúdo](#settings-for-retaining-and-deleting-content) nesta página:</span><span class="sxs-lookup"><span data-stu-id="4f980-118">For more information, see [Settings for retaining and deleting content](#settings-for-retaining-and-deleting-content) on this page:</span></span>
    
    <span data-ttu-id="4f980-119">Em seguida, decida se a política de retenção deve ser aplicada a todo o conteúdo ou ao conteúdo que atenda a condições específicas.</span><span class="sxs-lookup"><span data-stu-id="4f980-119">Then, decide whether the retention policy should apply to all content, or content that meets specific conditions.</span></span> <span data-ttu-id="4f980-120">Para saber mais sobre essas configurações avançadas de retenção, confira [Configurações avançadas para identificar conteúdo que atenda a condições específicas ](#advanced-settings-to-identify-content-that-meets-specific-conditions) nesta página.</span><span class="sxs-lookup"><span data-stu-id="4f980-120">For more information about these advanced retention settings, see [Advanced settings to identify content that meets specific conditions](#advanced-settings-to-identify-content-that-meets-specific-conditions) on this page.</span></span> 

4. <span data-ttu-id="4f980-121">Na página **Escolher locais**, selecione se a política de retenção deve ser aplicada a todos os locais suportados em sua organização ou se você deseja especificar os locais.</span><span class="sxs-lookup"><span data-stu-id="4f980-121">For the **Choose locations** page, select whether the retention policy should apply to all supported locations across your organization, or you want to specify the locations.</span></span> <span data-ttu-id="4f980-122">Se você optar por locais específicos, também pode especificar inclusões e exclusões.</span><span class="sxs-lookup"><span data-stu-id="4f980-122">If you choose specific locations, you can also specify includes and excludes.</span></span> 
    
    <span data-ttu-id="4f980-123">Para o Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="4f980-123">For Microsoft Teams:</span></span> 
    - <span data-ttu-id="4f980-124">Você deve selecionar a opção para escolher locais específicos, se desejar excluir ou reter as mensagens do canal do Teams ou chats do Teams.</span><span class="sxs-lookup"><span data-stu-id="4f980-124">You must select the option to choose specific locations if you want to delete or retain Teams channel messages or Team chats.</span></span> <span data-ttu-id="4f980-125">Quando você seleciona uma dessas opções como locais, os outros locais são excluídos automaticamente porque uma política de retenção que inclui esses dados do Teams não pode incluir outros locais.</span><span class="sxs-lookup"><span data-stu-id="4f980-125">When you select either of these options as locations, the other locations are automatically excluded because a retention policy that includes this Teams data can't include other locations.</span></span> 
    - <span data-ttu-id="4f980-126">Observe que, para **mensagens de canal do Teams**, estão incluídas mensagens de canais padrão, mas não de [canais privados](https://docs.microsoft.com/microsoftteams/private-channels).</span><span class="sxs-lookup"><span data-stu-id="4f980-126">Note that for **Teams channel messages**, message from standard channels but not [private channels](https://docs.microsoft.com/microsoftteams/private-channels) are included.</span></span> <span data-ttu-id="4f980-127">No momento canais privados não são suportados pelas políticas de retenção.</span><span class="sxs-lookup"><span data-stu-id="4f980-127">Currently, private channels aren't supported by retention policies.</span></span>
    
    <span data-ttu-id="4f980-128">Para obter mais informações sobre como escolher entre uma política de retenção para a organização ou para locais específicos, confira [ Aplicar uma política de retenção a uma organização inteira ou locais específicos](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) nesta página.</span><span class="sxs-lookup"><span data-stu-id="4f980-128">For more information about choosing between a retention policy for the organization or for specific locations, see [Applying a retention policy to an entire organization or specific locations](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) on this page.</span></span>
    
    <span data-ttu-id="4f980-129">Para obter informações específicas para **grupos do Office 365** e \*\*Skype for Business \*\*, consulte as seções a seguir, [Informações de configuração de grupos do Microsoft 365 ](#configuration-information-for-microsoft-365-groups) e [Informações de configuração do Skype for Business](#configuration-information-for-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="4f980-129">For information specific to **Office 365 groups** and **Skype for Business**, see the following sections, [Configuration information for Microsoft 365 groups](#configuration-information-for-microsoft-365-groups) and [Configuration information for Skype for Business](#configuration-information-for-skype-for-business).</span></span>

5. <span data-ttu-id="4f980-130">Conclua o assistente para salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="4f980-130">Complete the wizard to save your settings.</span></span>

<span data-ttu-id="4f980-131">Quando você tiver mais de uma política de retenção, confira [Os princípios de retenção ou o que tem precedência?](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="4f980-131">When you have more than one retention policy, see [The principles of retention, or what takes precedence?](retention-policies.md#the-principles-of-retention-or-what-takes-precedence)</span></span>

### <a name="configuration-information-for-microsoft-365-groups"></a><span data-ttu-id="4f980-132">Informações de configuração de grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f980-132">Configuration information for Microsoft 365 groups</span></span>

<span data-ttu-id="4f980-133">Para manter ou excluir o conteúdo de um grupo do Microsoft 365 (antigo grupo do Office 365), selecione o local **Grupos do Office 365**, ao escolher locais para sua política de retenção.</span><span class="sxs-lookup"><span data-stu-id="4f980-133">To retain or delete content for a Microsoft 365 group (formerly Office 365 group), select the **Office 365 groups** location when you choose locations for your retention policy.</span></span> <span data-ttu-id="4f980-134">Mesmo que um grupo do Microsoft 365 tenha uma caixa de correio do Exchange, uma política de retenção que inclua todo o local **E-mail do Exchange** não incluirá conteúdo nas caixas de correio de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4f980-134">Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire **Exchange email** location won't include content in Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="4f980-135">Além disso, embora o local **E-mail do Exchange** permita inicialmente especificar uma caixa de correio de grupo a ser incluída ou excluída, ao tentar salvar a política de retenção, você recebe um erro indicando que "RemoteGroupMailbox" não é uma seleção válida para o local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4f980-135">In addition, although the **Exchange email** location initially allows you to specify a group mailbox to be included or excluded, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.</span></span>

<span data-ttu-id="4f980-136">Uma política de retenção aplicada a um grupo do Microsoft 365 inclui a caixa de correio e o site do grupo.</span><span class="sxs-lookup"><span data-stu-id="4f980-136">A retention policy applied to a Microsoft 365 group includes both the group mailbox and site.</span></span> <span data-ttu-id="4f980-137">Uma política de retenção aplicada a um grupo do Microsoft 365 protege os recursos criados por um grupo do Microsoft 365, que inclui o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f980-137">A retention policy applied to a Microsoft 365 group protects the resources created by a Microsoft 365 group, which includes Microsoft Teams.</span></span>

### <a name="configuration-information-for-skype-for-business"></a><span data-ttu-id="4f980-138">Informações de configuração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4f980-138">Configuration information for Skype for Business</span></span>

<span data-ttu-id="4f980-139">Diferentemente de um email do Exchange, você não pode ativar ou desativar o status de local do Skype para incluir todos os usuários, mas pode ativar esse local e depois selecionar manualmente os usuários cujas conversas deseja manter:</span><span class="sxs-lookup"><span data-stu-id="4f980-139">Unlike Exchange email, you can't toggle the status of the Skype location on to include all users, but when you turn on that location, you then manually choose the users whose conversations you want to retain:</span></span>

![Escolha o local do Skype para políticas de retenção](../media/skype-location-retention-policies.png)
  
<span data-ttu-id="4f980-141">Ao selecionar **escolher usuários**, você pode incluir rapidamente todos os usuários, selecionando a caixa **Nome** no cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="4f980-141">When you select **Choose users**, you can quickly include all users by selecting the **Name** box in the column header.</span></span> <span data-ttu-id="4f980-142">No entanto, é importante compreender que cada usuário é como uma inclusão específica na política.</span><span class="sxs-lookup"><span data-stu-id="4f980-142">However, it's important to understand that each user counts as a specific inclusion in the policy.</span></span> <span data-ttu-id="4f980-143">Portanto, se mais de 1.000 usuários forem incluídos, os limites indicados na seção anterior serão aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="4f980-143">Therefore, if you include over 1,000 users, the limits noted in the previous section apply.</span></span> <span data-ttu-id="4f980-144">Aqui, selecionar todos os usuários do Skype não é o mesmo como se uma política no âmbito da organização fosse capaz de incluir todos os usuários do Skype por padrão.</span><span class="sxs-lookup"><span data-stu-id="4f980-144">Selecting all Skype users here is not the same as if an org-wide policy were able to include all Skype users by default.</span></span> 
  
![Página Escolher usuários do Skype](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
<span data-ttu-id="4f980-146">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span><span class="sxs-lookup"><span data-stu-id="4f980-146">Note that **Conversation History**, a folder in Outlook, is a feature that has nothing to do with Skype archiving.</span></span> <span data-ttu-id="4f980-147">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4f980-147">**Conversation History** can be turned off by the end user, but archiving for Skype is done by storing a copy of Skype conversations in a hidden folder that is inaccessible to the user but available to eDiscovery.</span></span>


## <a name="settings-for-retaining-and-deleting-content"></a><span data-ttu-id="4f980-148">Configurações de retenção e exclusão de conteúdo</span><span class="sxs-lookup"><span data-stu-id="4f980-148">Settings for retaining and deleting content</span></span>

<span data-ttu-id="4f980-149">Ao escolher as configurações de retenção e exclusão de conteúdo em sua política de retenção, sua política de retenção terá uma das seguintes configurações por um período especificado:</span><span class="sxs-lookup"><span data-stu-id="4f980-149">By choosing the settings for retaining and deleting content in your retention policy, your retention policy will have one of the following configurations for a specified period of time:</span></span>

- <span data-ttu-id="4f980-150">Somente reter</span><span class="sxs-lookup"><span data-stu-id="4f980-150">Retain-only</span></span>
- <span data-ttu-id="4f980-151">Reter e excluir</span><span class="sxs-lookup"><span data-stu-id="4f980-151">Retain and then delete</span></span>
- <span data-ttu-id="4f980-152">Somente excluir</span><span class="sxs-lookup"><span data-stu-id="4f980-152">Delete-only</span></span>

### <a name="retaining-content-for-a-specific-period-of-time"></a><span data-ttu-id="4f980-153">Reter o conteúdo por um período específico</span><span class="sxs-lookup"><span data-stu-id="4f980-153">Retaining content for a specific period of time</span></span>

<span data-ttu-id="4f980-154">Ao configurar uma política de retenção, você opta por reter o conteúdo indefinidamente ou por um número específico de dias, meses ou anos.</span><span class="sxs-lookup"><span data-stu-id="4f980-154">When you configure a retention policy, you choose to retain content indefinitely or for a specific number of days, months, or years.</span></span> <span data-ttu-id="4f980-155">A duração para retenção do conteúdo é calculada com base na idade desse conteúdo, e não do momento em que a política de retenção foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="4f980-155">The duration for how long content is retained is calculated from the age of the content, not from when the retention policy is applied.</span></span> <span data-ttu-id="4f980-156">Você pode escolher se a idade se baseia em quando o conteúdo foi criado ou (para o OneDrive e o SharePoint) em quando ele foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="4f980-156">You can choose whether the age is based on when the content was created or (for OneDrive and SharePoint) when it was last modified.</span></span>

<span data-ttu-id="4f980-157">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="4f980-157">Examples:</span></span>
  
- <span data-ttu-id="4f980-158">SharePoint: se você quiser preservar o conteúdo em um conjunto de sites por sete anos, e se um documento nesse conjunto de sites não tiver sido modificado em seis anos, o documento será retido somente por mais um ano caso não seja modificado.</span><span class="sxs-lookup"><span data-stu-id="4f980-158">SharePoint: If you want to retain content in a site collection for seven years since it was last modified, and a document in that site collection hasn't been modified in six years, the document will be retained for only another year if it's not modified.</span></span> <span data-ttu-id="4f980-159">Se o documento for editado novamente, a idade do documento será calculada a partir da última data de modificação, e ele ficará retido por mais sete anos.</span><span class="sxs-lookup"><span data-stu-id="4f980-159">If the document is edited again, the age of the document is calculated from the new last modified date, and it will be retained for another seven years.</span></span>
  
- <span data-ttu-id="4f980-160">Exchange: se você deseja reter o conteúdo em uma caixa de correio por sete anos, e uma mensagem foi enviada há seis anos, esta será retida por apenas um ano.</span><span class="sxs-lookup"><span data-stu-id="4f980-160">Exchange: If you want to retain content in a mailbox for seven years, and a message was sent six years ago, the message will be retained for only one year.</span></span> <span data-ttu-id="4f980-161">Para o conteúdo do Exchange, a idade é baseada na data de recebimento do email de entrada ou na data de envio do email de saída.</span><span class="sxs-lookup"><span data-stu-id="4f980-161">For Exchange content, the age is based on the date received for incoming email, or the date sent for outgoing email.</span></span> <span data-ttu-id="4f980-162">O processo de reter o conteúdo com base em quando ele foi modificado pela última vez é aplicável apenas ao conteúdo de sites do OneDrive e do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4f980-162">Retaining content based on when it was last modified applies only to site content in OneDrive and SharePoint.</span></span>
  
<span data-ttu-id="4f980-163">No final do período de retenção, você pode escolher se deseja que o conteúdo seja excluído permanentemente:</span><span class="sxs-lookup"><span data-stu-id="4f980-163">At the end of the retention period, you choose whether you want the content to be permanently deleted:</span></span>
  
![Página de configurações de Retenção](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a><span data-ttu-id="4f980-165">Como excluir conteúdo mais antigo que uma idade específica</span><span class="sxs-lookup"><span data-stu-id="4f980-165">Deleting content that's older than a specific age</span></span>

<span data-ttu-id="4f980-166">Uma política de retenção pode reter e excluir o conteúdo ou excluir o conteúdo antigo sem retê-lo.</span><span class="sxs-lookup"><span data-stu-id="4f980-166">A retention policy can both retain and then delete content, or delete old content without retaining it.</span></span>
  
<span data-ttu-id="4f980-167">Se sua política de retenção excluir conteúdo, será importante entender que o período de tempo especificado para uma política de retenção é calculado pelo tempo em que o documento foi criado ou modificado, e não a partir do momento em que a política foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="4f980-167">If your retention policy deletes content, it's important to understand that the time period specified for a retention policy is calculated from the time when the content was created or modified, not the time since the policy was assigned.</span></span>
  
![Configurações de exclusão](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
<span data-ttu-id="4f980-169">Por exemplo, suponha que você crie uma política de retenção que exclui o conteúdo depois de três anos e, em seguida, atribui essa política a todas as contas do OneDrive, que incluem uma grande quantidade de conteúdo criado há quatro ou cinco anos.</span><span class="sxs-lookup"><span data-stu-id="4f980-169">For example, suppose that you create a retention policy that deletes content after three years, and then assign that policy to all OneDrive accounts, which contain a lot of content that was created four or five years ago.</span></span> <span data-ttu-id="4f980-170">Nesse caso, uma boa parcela do conteúdo será excluída logo depois que a política de retenção for atribuída pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="4f980-170">In this case, a lot of content will be deleted soon after assigning the retention policy for the first time.</span></span> <span data-ttu-id="4f980-171">Por esse motivo, é importante compreender que uma política de retenção que exclui conteúdo pode ter um impacto considerável sobre o seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-171">For this reason, it's important to understand that a retention policy that deletes content can have a considerable impact on your content.</span></span> 
  
<span data-ttu-id="4f980-172">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content.</span><span class="sxs-lookup"><span data-stu-id="4f980-172">Therefore, before you assign a retention policy to a site collection for the first time, you should first consider the age of the existing content and how the policy may impact that content.</span></span> <span data-ttu-id="4f980-173">You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span><span class="sxs-lookup"><span data-stu-id="4f980-173">You may also want to communicate the new policy to your users before assigning it, to give them time to assess the possible impact.</span></span> <span data-ttu-id="4f980-174">Note this warning that appears when you review the settings for your retention policy just before creating it.</span><span class="sxs-lookup"><span data-stu-id="4f980-174">Note this warning that appears when you review the settings for your retention policy just before creating it.</span></span>
  
![Aviso sobre exclusão de conteúdo](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a><span data-ttu-id="4f980-176">Configurações avançadas para identificar conteúdo que atenda a condições específicas</span><span class="sxs-lookup"><span data-stu-id="4f980-176">Advanced settings to identify content that meets specific conditions</span></span>

<span data-ttu-id="4f980-177">Uma política de retenção pode ser aplicada a todo o conteúdo nos locais em que inclui ou você pode aplicar uma política de retenção apenas ao conteúdo que inclui palavras-chave específicas ou [tipos específicos de informações confidenciais](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="4f980-177">A retention policy can apply to all content in the locations that it includes, or you can choose to apply a retention policy only to content that contains specific keywords or [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span>
  
![Opções avançadas de retenção](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a><span data-ttu-id="4f980-179">Identificar conteúdo que inclui palavras-chave específicas</span><span class="sxs-lookup"><span data-stu-id="4f980-179">Identify content that contains specific keywords</span></span>

<span data-ttu-id="4f980-180">Você pode aplicar uma política de retenção apenas ao conteúdo que atende a condições específicas e depois realizar ações de retenção apenas nesse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-180">You can apply a retention policy only to content that meets specific conditions, and then take retention actions on just that content.</span></span> <span data-ttu-id="4f980-181">As condições disponíveis dão suporte à aplicação de uma política de retenção ao conteúdo que inclui palavras ou frases específicas.</span><span class="sxs-lookup"><span data-stu-id="4f980-181">The conditions available support applying a retention policy to content that contains specific words or phrases.</span></span> <span data-ttu-id="4f980-182">Refine a consulta usando operadores de pesquisa como AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="4f980-182">You can refine your query by using search operators like AND, OR, and NOT.</span></span> <span data-ttu-id="4f980-183">Para saber mais sobre esses operadores, confira [Consultas de palavra-chave e critérios de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="4f980-183">For more information on these operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="4f980-184">O suporte à adição de propriedades pesquisáveis (por exemplo, **assunto:**) estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="4f980-184">Support for adding searchable properties (for example, **subject:**) is coming soon.</span></span>
  
<span data-ttu-id="4f980-185">A retenção com base em consulta usa o índice de pesquisa para identificar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-185">Query-based retention uses the search index to identify content.</span></span>
  
![Editor de consultas](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a><span data-ttu-id="4f980-187">Identificar conteúdo com informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="4f980-187">Identify content that contains sensitive information</span></span>

<span data-ttu-id="4f980-188">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="4f980-188">You can also apply a retention policy only to content that contains [specific types of sensitive information](what-the-sensitive-information-types-look-for.md).</span></span> <span data-ttu-id="4f980-189">For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span><span class="sxs-lookup"><span data-stu-id="4f980-189">For example, you can choose to apply unique retention requirements only to content that contains personally identifiable information (PII) such as taxpayer identification numbers, social security numbers, or passport numbers.</span></span>
  
![Página Tipos de informações confidenciais](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
<span data-ttu-id="4f980-191">Observações:</span><span class="sxs-lookup"><span data-stu-id="4f980-191">Notes:</span></span>
  
- <span data-ttu-id="4f980-192">A retenção avançada para informações confidenciais não se aplica a pastas públicas do Exchange ou Skype for Business, pois esses locais não dão suporte a tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="4f980-192">Advanced retention for sensitive information doesn't apply to Exchange public folders or Skype for Business because those locations don't support sensitive information types.</span></span>
    
- <span data-ttu-id="4f980-193">O Exchange Online usa regras de fluxo de email (também conhecidas como regras de transporte) para identificar informações confidenciais, portanto, isso funciona apenas em mensagens em trânsito, e não em todos os itens já armazenados em uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="4f980-193">Exchange Online uses mail flow rules (also known as transport rules) to identify sensitive information, so this works only on messages in transit—not on all items already stored in a mailbox.</span></span> <span data-ttu-id="4f980-194">Para o Exchange Online, isso significa que uma política de retenção pode identificar informações confidenciais e realizar ações de retenção apenas em mensagens recebidas **após** a aplicação da política à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="4f980-194">For Exchange Online, this means that a retention policy can identify sensitive information and take retention actions only on messages that are received **after** the policy is applied to the mailbox.</span></span> <span data-ttu-id="4f980-195">A retenção com base em consulta descrita na seção anterior não apresenta essa limitação, pois ela usa o índice de pesquisa para identificar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4f980-195">Query-based retention described in the previous section doesn't have this limitation because it uses the search index to identify content.</span></span> 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a><span data-ttu-id="4f980-196">Aplicar uma política de retenção a uma organização inteira ou locais específicos</span><span class="sxs-lookup"><span data-stu-id="4f980-196">Applying a retention policy to an entire organization or specific locations</span></span>

<span data-ttu-id="4f980-197">Você pode facilmente aplicar uma política de retenção a uma organização inteira, locais inteiros ou apenas a locais ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="4f980-197">You can easily apply a retention policy to an entire organization, entire locations, or only to specific locations or users.</span></span>
  
### <a name="org-wide-policy"></a><span data-ttu-id="4f980-198">Política no âmbito da organização</span><span class="sxs-lookup"><span data-stu-id="4f980-198">Org-wide policy</span></span>

<span data-ttu-id="4f980-199">Um dos recursos mais avançados de política de retenção é que, por padrão, aplica-se aos locais no Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="4f980-199">One of the most powerful features of a retention policy is that it can apply to locations across Microsoft 365, including:</span></span>
  
- <span data-ttu-id="4f980-200">Email do Exchange</span><span class="sxs-lookup"><span data-stu-id="4f980-200">Exchange email</span></span>
    
- <span data-ttu-id="4f980-201">Conjuntos de sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4f980-201">SharePoint site collections</span></span>
    
- <span data-ttu-id="4f980-202">Contas do OneDrive</span><span class="sxs-lookup"><span data-stu-id="4f980-202">OneDrive accounts</span></span>
    
- <span data-ttu-id="4f980-203">Grupos do Microsoft 365 (aplicável ao conteúdo da caixa de correio do grupo e ao site do SharePoint associado.)</span><span class="sxs-lookup"><span data-stu-id="4f980-203">Microsoft 365 groups (applies to content in the group's mailbox and associated SharePoint site.)</span></span>
    
- <span data-ttu-id="4f980-204">Pastas públicas do Exchange</span><span class="sxs-lookup"><span data-stu-id="4f980-204">Exchange public folders</span></span>
    

![Opção Todos os locais](../media/retention-policies-all-locations.png)

<span data-ttu-id="4f980-206">Outros recursos importantes de uma política de retenção no âmbito da organização incluem:</span><span class="sxs-lookup"><span data-stu-id="4f980-206">Other important features of an org-wide retention policy include:</span></span>
  
- <span data-ttu-id="4f980-207">Não há um limite para o número de caixas de correio ou sites que essa política pode incluir.</span><span class="sxs-lookup"><span data-stu-id="4f980-207">There is no limit to the number of mailboxes or sites the policy can include.</span></span>
    
- <span data-ttu-id="4f980-208">Para o Exchange, as caixas de correio criadas após a aplicação da política herdam a política automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4f980-208">For Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>
  
### <a name="a-policy-that-applies-to-entire-locations"></a><span data-ttu-id="4f980-209">Uma política aplicável a locais inteiros</span><span class="sxs-lookup"><span data-stu-id="4f980-209">A policy that applies to entire locations</span></span>

<span data-ttu-id="4f980-210">Ao escolher locais, você pode facilmente incluir ou excluir um local inteiro, como emails do Exchange ou contas do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4f980-210">When you choose locations, you can easily include or exclude an entire location, such as Exchange email or OneDrive accounts.</span></span> <span data-ttu-id="4f980-211">Para fazer isso, ative ou desative o **Status** desse local.</span><span class="sxs-lookup"><span data-stu-id="4f980-211">To do so, toggle the **Status** of that location on or off.</span></span> 
  
<span data-ttu-id="4f980-212">Como uma política no âmbito da organização, se uma política for aplicada a qualquer combinação de locais inteiros, não haverá limite para o número de caixas de correio ou sites que ela pode incluir.</span><span class="sxs-lookup"><span data-stu-id="4f980-212">Like an org-wide policy, if a policy applies to any combination of entire locations, there is no limit to the number of mailboxes or sites the policy can include.</span></span> 

<span data-ttu-id="4f980-213">Por exemplo, se uma política incluir todos os emails do Exchange e sites do SharePoint, todos os sites e caixas de correio serão incluídos, independentemente da quantidade.</span><span class="sxs-lookup"><span data-stu-id="4f980-213">For example, if a policy includes all Exchange email and all SharePoint sites, all sites and mailboxes will be included, no matter how many.</span></span> <span data-ttu-id="4f980-214">Além disso, no caso do Exchange, todas as caixas de correio criadas após a aplicação da política herdam a política automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4f980-214">And for Exchange, any new mailbox created after the policy is applied will automatically inherit the policy.</span></span>

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a><span data-ttu-id="4f980-215">Uma política com inclusões ou exclusões específicas</span><span class="sxs-lookup"><span data-stu-id="4f980-215">A policy with specific inclusions or exclusions</span></span>

<span data-ttu-id="4f980-216">Você também pode aplicar uma política de retenção a usuários específicos, grupos específicos do Microsoft 365 ou sites específicos.</span><span class="sxs-lookup"><span data-stu-id="4f980-216">You can also apply a retention policy to specific users, specific Microsoft 365 groups, or specific sites.</span></span> <span data-ttu-id="4f980-217">Para fazer isso, ative o **Status** desse local e, em seguida, use os links para incluir ou excluir usuários específicos, grupos do Microsoft 365 ou sites.</span><span class="sxs-lookup"><span data-stu-id="4f980-217">To do so, toggle the **Status** of that location on, and then use the links to include or exclude specific users, Microsoft 365 groups, or sites.</span></span> 
  
<span data-ttu-id="4f980-218">No entanto, usando essa configuração, há alguns limites quando sua política de retenção inclui ou exclui mais de 1.000 locais específicos:</span><span class="sxs-lookup"><span data-stu-id="4f980-218">However, using this configuration, there are some limits when your retention policy includes or excludes over 1,000 specific locations:</span></span>
  
- <span data-ttu-id="4f980-219">Números máximos da política de retenção:</span><span class="sxs-lookup"><span data-stu-id="4f980-219">Maximum numbers for the retention policy:</span></span>
    - <span data-ttu-id="4f980-220">1.000 caixas de correio</span><span class="sxs-lookup"><span data-stu-id="4f980-220">1,000 mailboxes</span></span>
    - <span data-ttu-id="4f980-221">1.000 grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4f980-221">1,000 Microsoft 365 groups</span></span>
    - <span data-ttu-id="4f980-222">1.000 usuários para conversas privadas do Teams</span><span class="sxs-lookup"><span data-stu-id="4f980-222">1,000 users for Teams private chats</span></span>
    - <span data-ttu-id="4f980-223">100 sites (OneDrive ou SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4f980-223">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="4f980-224">Há um número máximo de políticas com suporte para um locatário: 10.000.</span><span class="sxs-lookup"><span data-stu-id="4f980-224">There is a maximum number of policies that are supported for a tenant: 10,000.</span></span> <span data-ttu-id="4f980-225">Esses itens incluem políticas de retenção, políticas de rótulo de retenção e políticas de retenção de aplicação automática.</span><span class="sxs-lookup"><span data-stu-id="4f980-225">These items include retention policies, retention label policies, and auto-apply retention policies.</span></span>

<span data-ttu-id="4f980-226">Se é provável que suas políticas de retenção estejam sujeitas a essas limitações, escolha as opções de configuração que se aplicam a locais inteiros ou use uma política em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="4f980-226">If your retention policies are likely to be subject to these limitations, choose the configuration options that apply to entire locations, or use an org-wide policy.</span></span>

## <a name="updating-retention-policies"></a><span data-ttu-id="4f980-227">Atualizar políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="4f980-227">Updating retention policies</span></span>

<span data-ttu-id="4f980-228">Se você editar uma política de retenção e o conteúdo já estiver sujeito às configurações originais da sua política de retenção, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo identificado recentemente.</span><span class="sxs-lookup"><span data-stu-id="4f980-228">If you edit a retention policy and content is already subject to the original settings in your retention policy, your updated settings will be automatically applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="4f980-229">Geralmente, essa atualização é bastante rápida, mas pode levar vários dias.</span><span class="sxs-lookup"><span data-stu-id="4f980-229">Usually this update is fairly quick but can take several days.</span></span> <span data-ttu-id="4f980-230">Quando a replicação da política nos locais do Microsoft 365 estiver concluída, você verá o status da política de retenção no Centro de Conformidade do Microsoft 365 mudar de **Ativado (Pendente)** para **Ativado (Sucesso)**.</span><span class="sxs-lookup"><span data-stu-id="4f980-230">When the policy replication across your Microsoft 365 locations is complete, you'll see the status of the retention policy in the Microsoft 365 compliance center change from **On (Pending)** to **On (Success)**.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a><span data-ttu-id="4f980-231">Localizar os cmdlets do PowerShell para políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="4f980-231">Find the PowerShell cmdlets for retention policies</span></span>

<span data-ttu-id="4f980-232">Para usar os cmdlets de políticas de retenção:</span><span class="sxs-lookup"><span data-stu-id="4f980-232">To use the retention policies cmdlets:</span></span>
  
1. [<span data-ttu-id="4f980-233">Conecte-se ao Centro de Segurança e Conformidade do Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f980-233">Connect to the Office 365 Security & Compliance Center PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="4f980-234">Use esses cmdlets do Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="4f980-234">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="4f980-235">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="4f980-235">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="4f980-236">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="4f980-236">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="4f980-237">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="4f980-237">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="4f980-238">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="4f980-238">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="4f980-239">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="4f980-239">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="4f980-240">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="4f980-240">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="4f980-241">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="4f980-241">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="4f980-242">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="4f980-242">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)


## <a name="lock-a-retention-policy-by-using-powershell"></a><span data-ttu-id="4f980-243">Bloquear uma política de retenção usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f980-243">Lock a retention policy by using PowerShell</span></span>

<span data-ttu-id="4f980-244">Você deve usar o Windows PowerShell se precisar usar o [Bloqueio de Preservação](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) para atender aos requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="4f980-244">You must use PowerShell if you need to use [Preservation Lock](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements) to comply with regulatory requirements.</span></span>

1. <span data-ttu-id="4f980-245">[Conecte-se ao Windows PowerShell do Centro de Segurança e Conformidade do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4f980-245">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="4f980-246">Liste suas políticas de retenção e encontre o nome da política que você quer bloquear executando `Get-RetentionCompliancePolicy`.</span><span class="sxs-lookup"><span data-stu-id="4f980-246">List your retention policies and find the name of the policy that you want to lock by running `Get-RetentionCompliancePolicy`.</span></span>
    
    ![Lista de políticas de retenção no Windows PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. <span data-ttu-id="4f980-248">Coloque um Bloqueio de Preservação em uma política de retenção, execute `Set-RetentionCompliancePolicy` com o parâmetro `RestrictiveRetention` definido como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f980-248">To place a Preservation Lock on a retention policy, run `Set-RetentionCompliancePolicy` with the `RestrictiveRetention` parameter set to true.</span></span> <span data-ttu-id="4f980-249">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4f980-249">For example:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true
   ```
   
    ![Parâmetro RestrictiveRetention no PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
    <span data-ttu-id="4f980-251">Depois de executar esse cmdlet, escolha **Sim para Todos**:</span><span class="sxs-lookup"><span data-stu-id="4f980-251">After you run that cmdlet, choose **Yes to All**:</span></span>
    
    ![Solicitar confirmação que deseja bloquear uma política de retenção no PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="4f980-253">O Bloqueio de Preservação agora está localizado na política de retenção.</span><span class="sxs-lookup"><span data-stu-id="4f980-253">A Preservation Lock is now placed on the retention policy.</span></span> <span data-ttu-id="4f980-254">Se executar `Get-RetentionCompliancePolicy`, o parâmetro `RestrictiveRetention` é definido como verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f980-254">If you run `Get-RetentionCompliancePolicy`, the `RestrictiveRetention` parameter is set to true.</span></span> <span data-ttu-id="4f980-255">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4f980-255">For example:</span></span>

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![Bloquear a política com todos os parâmetros mostrados no PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

