---
title: Limitar a exposição acidental
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Saiba como limitar a exposição acidental de informações ao compartilhar arquivos com pessoas de fora da sua organização.
ms.openlocfilehash: 952337790ce2f0418dd5ab637435f1523b27b562
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928407"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="b9fdf-103">Limitar a exposição acidental de arquivos ao compartilhar com pessoas de fora da sua organização</span><span class="sxs-lookup"><span data-stu-id="b9fdf-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="b9fdf-104">Ao compartilhar arquivos e pastas com pessoas de fora da sua organização, há uma variedade de opções para reduzir as chances de compartilhar acidentalmente informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-104">When sharing files and folders with people outside your organization, there are a variety of options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="b9fdf-105">Você pode escolher a opção apresentada neste artigo que atenda melhor às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="b9fdf-106">Usar as práticas recomendadas para links para Qualquer pessoa</span><span class="sxs-lookup"><span data-stu-id="b9fdf-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="b9fdf-107">Se as pessoas em sua organização precisarem fazer compartilhamentos não autenticados, mas você está preocupado que pessoas não autenticadas façam modificações no conteúdo, leia [Práticas recomendadas para compartilhamento não autenticado](best-practices-anonymous-sharing.md) para obter diretrizes sobre como trabalhar com o compartilhamento não autenticado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="b9fdf-108">Desativar links para Qualquer pessoa</span><span class="sxs-lookup"><span data-stu-id="b9fdf-108">Turn off Anyone links</span></span>

<span data-ttu-id="b9fdf-109">Recomenda-se deixar os links para *Qualquer pessoa* habilitados para o conteúdo apropriado porque essa é a maneira mais fácil de compartilhar, além de poder ajudar a reduzir o risco de usuários que buscam soluções diferentes e fora do controle do departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="b9fdf-110">Os links para *Qualquer pessoa* podem ser encaminhados a outras pessoas, mas o acesso aos arquivos só estará disponível para os usuários que tiverem o link.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="b9fdf-111">Caso você queira que as pessoas de fora da sua organização sempre façam a autenticação ao acessar o conteúdo no SharePoint, Grupos ou no Teams, você pode desativar o compartilhamento a *Qualquer pessoa*.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="b9fdf-112">Isso impedirá usuários de compartilharem conteúdo não autenticado.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="b9fdf-113">Mesmo desabilitando os links para *Qualquer pessoa*, os usuários continuarão podendo fazer compartilhamentos facilmente com convidados usando links para *Pessoas específicas*.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="b9fdf-114">Nesse caso, todas as pessoas de fora da sua organização precisarão se autenticar para poder acessar o conteúdo compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="b9fdf-115">Dependendo das suas necessidades, você pode desabilitar links para *Qualquer pessoa* para sites específicos ou para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="b9fdf-116">Para desativar os links para *Qualquer pessoa* da sua organização</span><span class="sxs-lookup"><span data-stu-id="b9fdf-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="b9fdf-117">No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="b9fdf-118">Defina as configurações de compartilhamento externo do SharePoint para **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![Captura de tela das configurações de compartilhamento externo do site do SharePoint no nível da organização](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="b9fdf-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-120">Click **Save**.</span></span>

<span data-ttu-id="b9fdf-121">Para desativar os links para *Qualquer pessoa* de um site</span><span class="sxs-lookup"><span data-stu-id="b9fdf-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="b9fdf-122">No centro de administração do SharePoint, na navegação à esquerda, expanda a opção **Sites** e clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="b9fdf-123">Clique no site que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="b9fdf-124">Na faixa de opções, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="b9fdf-125">Verifique se o compartilhamento está definido como **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![Captura de tela das configurações de compartilhamento externo do site do SharePoint](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="b9fdf-127">Caso tenha feito alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="b9fdf-128">Filtragem de domínios</span><span class="sxs-lookup"><span data-stu-id="b9fdf-128">Domain filtering</span></span>

<span data-ttu-id="b9fdf-129">Você pode usar as listas permitir ou negar domínio para determinar os domínios que seus usuários podem compartilhar com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="b9fdf-130">Com uma lista de permissões, você pode especificar uma lista de domínios que os usuários de sua organização podem compartilhar com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="b9fdf-131">O compartilhamento com outros domínios está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-131">Sharing with to other domains is blocked.</span></span> <span data-ttu-id="b9fdf-132">Se sua organização só colabora com as pessoas presentes em uma lista de domínios específicos, você pode usar esse recurso para impedir o compartilhamento com outros domínios.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="b9fdf-133">Com uma lista de negações, você pode especificar uma lista de domínios que os usuários da organização não podem compartilhar com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="b9fdf-134">O compartilhamento com os domínios listados está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="b9fdf-135">Isso poderá ser útil se você tiver concorrentes, por exemplo, que deseja impedir de acessar o conteúdo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="b9fdf-136">As listas de permissão e negação afetam apenas o compartilhamento com convidados.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="b9fdf-137">Os usuários continuarão podendo fazer compartilhamentos com pessoas de domínios proibidos usando links para *Qualquer pessoa* caso você ainda não os tenha desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="b9fdf-138">Para obter os melhores resultados com listas de permissão e negação de domínio, cogite desabilitar os links para *Qualquer pessoa* conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="b9fdf-139">Para configurar uma lista de permissão ou negação de domínio</span><span class="sxs-lookup"><span data-stu-id="b9fdf-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="b9fdf-140">No centro de administração do SharePoint, na navegação à esquerda, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="b9fdf-141">Em **Configurações avançadas para compartilhamento externo**, marque a caixa de seleção **Limitar compartilhamento externo por domínio**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="b9fdf-142">Clique em **Adicionar domínios**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="b9fdf-143">Selecione se deseja bloquear domínios, digite os domínios e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="b9fdf-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![Captura de tela das configurações de limite de compartilhamento externo por domínio do SharePoint](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="b9fdf-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-145">Click **Save**.</span></span>

<span data-ttu-id="b9fdf-146">Caso deseje limitar o compartilhamento por domínio em um nível superior ao SharePoint e ao OneDrive, você pode [permitir ou bloquear convites para usuários B2B de organizações específicas](/azure/active-directory/b2b/allow-deny-list) no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="b9fdf-147">(Você deve configurar a [integração do SharePoint e do OneDrive com a versão prévia do B2B do Azure AD](/sharepoint/sharepoint-azureb2b-integration-preview) para que essas configurações se apliquem ao SharePoint e ao OneDrive).</span><span class="sxs-lookup"><span data-stu-id="b9fdf-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="b9fdf-148">Limitar o compartilhamento de arquivos, pastas e sites com pessoas de fora da sua organização com grupos de segurança especificados</span><span class="sxs-lookup"><span data-stu-id="b9fdf-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="b9fdf-149">Você pode restringir o compartilhamento de arquivos, pastas e sites com pessoas de fora da sua organização com os membros de um grupo de segurança específico.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="b9fdf-150">Isso será útil caso você queira habilitar o compartilhamento externo, mas com um fluxo de trabalho de aprovação ou processo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="b9fdf-151">Como alternativa, você pode exigir que os usuários concluam um curso de treinamento antes que eles sejam adicionados ao grupo de segurança e possam compartilhar externamente.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="b9fdf-152">Limitar o compartilhamento externo com membros de um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b9fdf-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="b9fdf-153">No [centro de administração do SharePoint](https://admin.microsoft.com/sharepoint), na navegação à esquerda, em **Políticas** clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="b9fdf-154">Em **Compartilhamento externo**, expanda **Mais configurações de compartilhamento externo**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="b9fdf-155">Selecione **Permitir que somente os usuários em grupos de segurança específicos compartilhem externamente** e, em seguida, selecione **Gerenciar grupos de segurança**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![Captura de tela do Painel gerenciar grupos de segurança](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="b9fdf-157">Na caixa **Adicionar um grupo de segurança**, digite um nome para o grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="b9fdf-158">A caixa de grupo de segurança é exibida.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-158">The security group box appears.</span></span>

5. <span data-ttu-id="b9fdf-159">Ao lado do nome do grupo de segurança, na lista suspensa **Pode compartilhar com**, escolha:</span><span class="sxs-lookup"><span data-stu-id="b9fdf-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="b9fdf-160">**Somente convidados autenticados** (padrão)</span><span class="sxs-lookup"><span data-stu-id="b9fdf-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="b9fdf-161">**Qualquer pessoa**</span><span class="sxs-lookup"><span data-stu-id="b9fdf-161">**Anyone**</span></span>

6. <span data-ttu-id="b9fdf-162">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-162">Select **Save**.</span></span>

<span data-ttu-id="b9fdf-163">Observe que isso afeta arquivos, pastas e sites, mas não os grupos do Microsoft 365 ou Teams.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="b9fdf-164">Quando os membros convidarem pessoas para um grupo privado do Microsoft 365 ou uma equipe privada no Microsoft Teams, o convite é enviado ao proprietário do grupo ou equipe para aprovação.</span><span class="sxs-lookup"><span data-stu-id="b9fdf-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9fdf-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9fdf-165">See Also</span></span>

[<span data-ttu-id="b9fdf-166">Criar um ambiente seguro de compartilhamento de convidados</span><span class="sxs-lookup"><span data-stu-id="b9fdf-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="b9fdf-167">Práticas recomendadas para compartilhar arquivos e pastas com usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="b9fdf-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)