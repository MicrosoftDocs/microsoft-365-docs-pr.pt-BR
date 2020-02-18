---
title: Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/26/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Resumo: Crie sites de equipe do SharePoint Online confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste.'
ms.openlocfilehash: 6294daa943c3815b86a9e12154901ed0b58d5e8d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42088101"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a><span data-ttu-id="5d77c-103">Proteger sites do SharePoint Online em um ambiente de desenvolvimento/teste</span><span class="sxs-lookup"><span data-stu-id="5d77c-103">Secure SharePoint Online sites in a dev/test environment</span></span>

<span data-ttu-id="5d77c-104">Este artigo fornece instruções passo a passo para criar um ambiente de desenvolvimento/teste que inclui os sites confidenciais e altamente confidenciais do SharePoint para a solução de [arquivos e sites seguros do SharePoint Online](secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="5d77c-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential SharePoint sites for the [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) solution.</span></span>

![Proteção com alto nível de confidencialidade para sites de equipe do SharePoint Online.](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

<span data-ttu-id="5d77c-106">Use esse ambiente de desenvolvimento/teste para testar e ajustar as configurações de suas necessidades específicas antes de implantar esses tipos de equipes na produção.</span><span class="sxs-lookup"><span data-stu-id="5d77c-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying these types of team sites in production.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="5d77c-107">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5d77c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="5d77c-108">Se você deseja apenas testar equipes confidenciais e altamente confidenciais de uma maneira simples com os requisitos mínimos, siga as instruções em [Configuração de base leve](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="5d77c-108">If you just want to test sensitive and highly confidential team sites in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="5d77c-109">Caso pretenda testar equipes confidenciais e altamente confidenciais em uma empresa simulada, siga as instruções em [sincronização de hash de senha](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="5d77c-109">If you want to test sensitive and highly confidential team sites in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="5d77c-110">Testar as equipes confidenciais e altamente confidenciais não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5d77c-110">Testing sensitive and highly confidential team sites does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5d77c-111">Ele é fornecido aqui como uma opção para que você possa testar equipes confidenciais e altamente confidenciais e experimentá-las em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="5d77c-111">It is provided here as an option so that you can test sensitive and highly confidential team sites and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="5d77c-112">Fase 2: criar e configurar seus grupos e usuários do Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="5d77c-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="5d77c-113">Nesta fase, você cria e configura os usuários e grupos do Azure AD para sua organização fictícia.</span><span class="sxs-lookup"><span data-stu-id="5d77c-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>

<span data-ttu-id="5d77c-114">Primeiro, crie um conjunto de grupos para uma organização comum com o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="5d77c-114">First, create two groups for a typical organization with the Azure portal.</span></span>

1. <span data-ttu-id="5d77c-115">Crie uma guia separada no navegador e vá para o Portal do Azure[https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5d77c-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="5d77c-116">Se necessário, entre com as credenciais da conta de administrador global da sua assinatura paga ou de avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5d77c-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>

2. <span data-ttu-id="5d77c-117">No Portal do Azure, clique em **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="5d77c-118">Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="5d77c-119">Na folha **Grupo**:</span><span class="sxs-lookup"><span data-stu-id="5d77c-119">On the **Group** blade:</span></span>

   - <span data-ttu-id="5d77c-120">Selecione **Segurança** em **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-120">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="5d77c-121">Digite **Pacote C** em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-121">Type **C-Suite** in **Name**.</span></span>

   - <span data-ttu-id="5d77c-122">Escolha **Atribuído** em **Tipo de Associação**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-122">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="5d77c-123">Clique em **Criar** e, em seguida, feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-123">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="5d77c-124">Repita as etapas 3-5 para um novo grupo chamado **equipe de marketing**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-124">Repeat steps 3-5 for a new group named **Marketing staff**.</span></span>

<span data-ttu-id="5d77c-125">Em seguida, configure o licenciamento automático para que os membros de seus grupos recebam automaticamente a atribuição de licenças para suas assinaturas do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="5d77c-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>

1. <span data-ttu-id="5d77c-126">No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="5d77c-127">Na lista, selecione **Microsoft 365 Enterprise E5**e, em seguida, clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-127">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>

3. <span data-ttu-id="5d77c-128">Na folha **Atribuir licença**, clique em **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-128">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="5d77c-129">Na lista de grupos, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d77c-129">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="5d77c-130">Pacote C</span><span class="sxs-lookup"><span data-stu-id="5d77c-130">C-Suite</span></span>

   - <span data-ttu-id="5d77c-131">Equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="5d77c-131">Marketing staff</span></span>

5. <span data-ttu-id="5d77c-132">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-132">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="5d77c-133">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="5d77c-133">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="5d77c-134">Em seguida, conecte-se ao módulo [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5d77c-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="5d77c-135">Preencha o nome da organização, seu local e uma senha comum. Execute esses comandos no prompt de comando do PowerShell ou no ISE (Ambiente de Script Integrado) para criar contas de usuário e adicioná-las aos grupos:</span><span class="sxs-lookup"><span data-stu-id="5d77c-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="5d77c-136">O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de desenvolvimento/teste.</span><span class="sxs-lookup"><span data-stu-id="5d77c-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="5d77c-137">Obviamente, isso é recomendado para assinaturas de produção.</span><span class="sxs-lookup"><span data-stu-id="5d77c-137">Obviously, this is highly discouraged for production subscriptions.</span></span>

<span data-ttu-id="5d77c-138">Use essas etapas para verificar se o licenciamento baseado em grupo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="5d77c-138">Use these steps to verify that group-based licensing is working correctly.</span></span>

1. <span data-ttu-id="5d77c-139">Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="5d77c-140">Na nova guia **Centro de administração do Microsoft 365** do seu navegador, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="5d77c-141">Na lista de usuários, clique em **CEO**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-141">In the list of users, click **CEO**.</span></span>

4. <span data-ttu-id="5d77c-142">No painel que lista as propriedades da conta de usuário **CEO**, verifique se ele recebeu a atribuição das licenças **Microsoft 365 Enterprise E5** (em \*\* Licenças de produto\*\*).</span><span class="sxs-lookup"><span data-stu-id="5d77c-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license (in **Product licenses**).</span></span>

## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="5d77c-143">Fase 3: Criar etiquetas de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="5d77c-143">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="5d77c-144">Nesta fase, você cria os rótulos de retenção de documentos em seus sites de equipe do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5d77c-144">In this phase, you create the retention labels for documents in your SharePoint team sites.</span></span>

1. <span data-ttu-id="5d77c-145">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5d77c-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>

2. <span data-ttu-id="5d77c-146">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>

3. <span data-ttu-id="5d77c-147">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-147">Click **Retention labels > Create a label**.</span></span>

4. <span data-ttu-id="5d77c-148">No painel **Atribuir nome ao seu rótulo** digite **Confidenciais** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-148">On the **Name your label** pane, type **Sensitive** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="5d77c-149">No painel **descritores de plano de arquivo**, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-149">On the **File plan descriptors** pane, click **Next**.</span></span>

6. <span data-ttu-id="5d77c-150">No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>

7. <span data-ttu-id="5d77c-151">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-151">On the **Review your settings** pane, click **Create the label**.</span></span>

8. <span data-ttu-id="5d77c-152">Repita as etapas 3-7 para um rótulo de retenção adicional chamado **altamente confidencial**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>

9. <span data-ttu-id="5d77c-153">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>

10. <span data-ttu-id="5d77c-154">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>

11. <span data-ttu-id="5d77c-155">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="5d77c-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>

12. <span data-ttu-id="5d77c-156">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-156">Click **Done**.</span></span>

13. <span data-ttu-id="5d77c-157">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-157">On the **Choose labels to publish** pane, click **Next**.</span></span>

14. <span data-ttu-id="5d77c-158">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-158">On the **Choose locations** pane, click **Next**.</span></span>

15. <span data-ttu-id="5d77c-159">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>

16. <span data-ttu-id="5d77c-160">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

## <a name="phase-4-create-your-team-sites"></a><span data-ttu-id="5d77c-161">Fase 4: criar sites de equipes</span><span class="sxs-lookup"><span data-stu-id="5d77c-161">Phase 4: Create your team sites</span></span>

<span data-ttu-id="5d77c-162">Nesta fase, você criará e configurará equipes confidenciais e altamente confidenciais para a sua organização de exemplo.</span><span class="sxs-lookup"><span data-stu-id="5d77c-162">In this phase, you create and configure sensitive and highly confidential team sites for your example organization.</span></span>

### <a name="sensitive-team-site-for-marketing-campaigns"></a><span data-ttu-id="5d77c-163">Site de equipe confidencial para campanhas de marketing</span><span class="sxs-lookup"><span data-stu-id="5d77c-163">Sensitive team site for marketing campaigns</span></span>

<span data-ttu-id="5d77c-164">Primeiro, crie uma equipe de nível confidencial para os membros do grupo de marketing colaborarem em campanhas de marketing contínuas.</span><span class="sxs-lookup"><span data-stu-id="5d77c-164">First, create a sensitive-level team site for members of the marketing group to collaborate on ongoing marketing campaigns.</span></span>

1. <span data-ttu-id="5d77c-165">[Criar uma nova equipe privada](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) com o nome **campanhas de Marketing**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-165">[Create a new private team site](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) with the name **Marketing Campaigns**.</span></span>

2. <span data-ttu-id="5d77c-166">Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-166">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>

3. <span data-ttu-id="5d77c-167">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-167">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

4. <span data-ttu-id="5d77c-168">Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-168">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="5d77c-169">Em seguida, configure a pasta de documentos do site de equipe SharePoint campanhas de marketing para o rótulo de retenção confidencial.</span><span class="sxs-lookup"><span data-stu-id="5d77c-169">Next, configure the documents folder of the Marketing Campaigns SharePoint team site for the Sensitive retention label.</span></span>

1. <span data-ttu-id="5d77c-170">Na guia **Campanhas de marketing – Página Inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-170">In the **Marketing Campaigns-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d77c-171">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-171">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d77c-172">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-172">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d77c-173">Em **Configurações – Aplicar Rótulo**, escolha **Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-173">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>

<span data-ttu-id="5d77c-174">Em seguida, configure uma política DLP (prevenção de perda de dados) que notifique os usuários quando eles compartilham um documento com o rótulo confidencial, que inclui documentos no site campanhas de marketing, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="5d77c-174">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document with the Sensitive label, which includes documents in the Marketing Campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="5d77c-175">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5d77c-175">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>

2. <span data-ttu-id="5d77c-176">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-176">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>

3. <span data-ttu-id="5d77c-177">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-177">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>

4. <span data-ttu-id="5d77c-178">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-178">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="5d77c-179">No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-179">In the **Name your policy** pane, type **Sensitive label SharePoint sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="5d77c-180">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-180">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="5d77c-181">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-181">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="5d77c-182">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-182">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="5d77c-183">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-183">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>

10. <span data-ttu-id="5d77c-184">No painel **Rótulos de retenção**, clique em \*\* Adicionar\*\*, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-184">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="5d77c-185">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-185">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="5d77c-186">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-186">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="5d77c-187">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-187">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="5d77c-188">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-188">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="5d77c-189">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d77c-189">In the text box, type or paste in the following:</span></span>

    <span data-ttu-id="5d77c-p104">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="5d77c-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="5d77c-193">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-193">Click **OK**.</span></span>

17. <span data-ttu-id="5d77c-194">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-194">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>

18. <span data-ttu-id="5d77c-195">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-195">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="5d77c-196">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-196">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

### <a name="company-strategy-team-site"></a><span data-ttu-id="5d77c-197">Site de equipe de estratégia empresarial</span><span class="sxs-lookup"><span data-stu-id="5d77c-197">Company strategy team site</span></span>

<span data-ttu-id="5d77c-198">Primeiro, crie um site de equipe de nível altamente confidencial para que os membros da equipe de liderança sênior colabore na estratégia da empresa.</span><span class="sxs-lookup"><span data-stu-id="5d77c-198">First, create a highly confidential-level team site for the senior leadership team to collaborate on company strategy.</span></span>

1. <span data-ttu-id="5d77c-199">[Criar uma nova equipe privada](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) com o nome **Estratégia empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-199">[Create a new private team site](https://support.office.com/article/ef10c1e7-15f3-42a3-98aa-b5972711777d) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="5d77c-200">Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-200">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>

3. <span data-ttu-id="5d77c-201">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-201">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

4. <span data-ttu-id="5d77c-202">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-202">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

5. <span data-ttu-id="5d77c-203">Desative **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-203">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="5d77c-204">Em seguida, configure a pasta de documentos do site da equipe do SharePoint da estratégia da empresa para obter o rótulo altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="5d77c-204">Next, configure the documents folder of the Company Strategy SharePoint team site for the Highly Confidential label.</span></span>

1. <span data-ttu-id="5d77c-205">Na guia **Estratégia empresarial – Página Inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-205">In the **Company Strategy-Home** tab of your browser, click **Documents**.</span></span>

2. <span data-ttu-id="5d77c-206">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-206">Click the settings icon, and then click **Library settings**.</span></span>

3. <span data-ttu-id="5d77c-207">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-207">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>

4. <span data-ttu-id="5d77c-208">Em **Configurações – Aplicar Rótulo**, escolha **Altamente Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-208">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>

<span data-ttu-id="5d77c-209">Em seguida, configure uma política DLP que impede os usuários de compartilhar um documento com o rótulo altamente confidencial, que inclui documentos no site de estratégia da empresa, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="5d77c-209">Next, configure a DLP policy that blocks users when they share a document with the Highly Confidential label, which includes documents in the Company Strategy site, outside the organization.</span></span>

1. <span data-ttu-id="5d77c-210">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com seu administrador global.</span><span class="sxs-lookup"><span data-stu-id="5d77c-210">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>

2. <span data-ttu-id="5d77c-211">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-211">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>

3. <span data-ttu-id="5d77c-212">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-212">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>

4. <span data-ttu-id="5d77c-213">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-213">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>

5. <span data-ttu-id="5d77c-214">No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-214">In the **Name your policy** pane, type **Highly Confidential label SharePoint sites** in **Name**, and then click **Next**.</span></span>

6. <span data-ttu-id="5d77c-215">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-215">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>

7. <span data-ttu-id="5d77c-216">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-216">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>

8. <span data-ttu-id="5d77c-217">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-217">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>

9. <span data-ttu-id="5d77c-218">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-218">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>

10. <span data-ttu-id="5d77c-219">No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-219">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>

11. <span data-ttu-id="5d77c-220">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-220">In the **Choose the types of content to protect** pane, click **Save**.</span></span>

12. <span data-ttu-id="5d77c-221">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-221">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="5d77c-222">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-222">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>

14. <span data-ttu-id="5d77c-223">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-223">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>

15. <span data-ttu-id="5d77c-224">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5d77c-224">In the text box, type or paste in the following:</span></span>

    <span data-ttu-id="5d77c-p105">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="5d77c-p105">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>

16. <span data-ttu-id="5d77c-228">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-228">Click **OK**.</span></span>

17. <span data-ttu-id="5d77c-229">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-229">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="5d77c-230">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-230">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

19. <span data-ttu-id="5d77c-231">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5d77c-231">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="5d77c-232">Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo confidencial com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5d77c-232">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="5d77c-233">O nome do rótulo é Estratégia empresarial</span><span class="sxs-lookup"><span data-stu-id="5d77c-233">The name of the label is Company Strategy</span></span>

- <span data-ttu-id="5d77c-234">A criptografia está ativada</span><span class="sxs-lookup"><span data-stu-id="5d77c-234">Encryption is enabled</span></span>

- <span data-ttu-id="5d77c-235">O grupo de estratégia empresarial tem permissões de Coautoria.</span><span class="sxs-lookup"><span data-stu-id="5d77c-235">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="5d77c-236">Depois de criar, publique o novo rótulo.</span><span class="sxs-lookup"><span data-stu-id="5d77c-236">After creating, publish the new label.</span></span> <span data-ttu-id="5d77c-237">Se entrar como um membro do grupo de estratégias empresarial, você verá o novo rótulo na opção confidencialidade na barra de ferramentas página inicial do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="5d77c-237">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="5d77c-238">Selecione o rótulo de estratégia empresarial na opção confidencialidade para atribuir o rótulo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="5d77c-238">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="5d77c-239">Os arquivos na seção documentos da estratégia empresarial do site de equipe do SharePoint recebem o rótulo de retenção altamente confidencial e estão sujeitos à política de DLP configurada.</span><span class="sxs-lookup"><span data-stu-id="5d77c-239">Files in the documents section of the Company Strategy SharePoint team site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="5d77c-240">Os arquivos também podem ter o rótulo diferencial da estratégia empresarial atribuído.</span><span class="sxs-lookup"><span data-stu-id="5d77c-240">Files can also have the Company Strategy sensitivity label assigned.</span></span>

<span data-ttu-id="5d77c-241">Esta é a configuração resultante para as campanhas de marketing e os sites de equipe da estratégia empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d77c-241">Here is the resulting configuration for the Marketing Campaigns and Company Strategy team sites.</span></span>

![Proteção com alto nível de confidencialidade para sites de equipe do SharePoint Online.](../../media/sensitive-highly-confidential-sp-sites-dev-test.png)

## <a name="next-step"></a><span data-ttu-id="5d77c-243">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5d77c-243">Next step</span></span>

<span data-ttu-id="5d77c-244">Quando você estiver pronto para a implantação dos sites do SharePoint Online seguros na produção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md) para obter informações detalhadas e links para os artigos de implantação passo a passo.</span><span class="sxs-lookup"><span data-stu-id="5d77c-244">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) for detailed information and links to step-by-step deployment articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d77c-245">Confira também</span><span class="sxs-lookup"><span data-stu-id="5d77c-245">See Also</span></span>

[<span data-ttu-id="5d77c-246">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="5d77c-246">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)

[<span data-ttu-id="5d77c-247">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="5d77c-247">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
