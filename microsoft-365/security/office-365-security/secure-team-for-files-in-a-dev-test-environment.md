---
title: Protege o Teams para arquivos em um ambiente de desenvolvimento/teste
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Resumo: criar equipes confidenciais e altamente confidenciais no Microsoft Teams para arquivos em um ambiente de desenvolvimento/teste.'
ms.openlocfilehash: f22b3b1fbe07af6866206034ad6c9a90ced8a268
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37929255"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a><span data-ttu-id="b8587-103">Protege o Teams para arquivos em um ambiente de desenvolvimento/teste</span><span class="sxs-lookup"><span data-stu-id="b8587-103">Secure Teams for files in a dev/test environment</span></span>

<span data-ttu-id="b8587-104">Este artigo fornece instruções passo a passo para criar um ambiente de desenvolvimento e teste que inclui as equipes contextuais e altamente confidenciais para a solução [arquivos seguros no Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b8587-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential teams for the [Secure files in Microsoft Teams](secure-files-in-teams.md) solution.</span></span>
  
![Equipes confidenciais e altamente confidenciais no Microsoft Teams para arquivos.](../media/sensitive-highly-confidential-teams-dev-test.png)
  
<span data-ttu-id="b8587-106">Use esse ambiente de desenvolvimento/teste para testar e ajustar as configurações de suas necessidades específicas antes de implantar esses tipos de equipes na produção.</span><span class="sxs-lookup"><span data-stu-id="b8587-106">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b8587-107">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b8587-107">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="b8587-108">Se você deseja apenas testar equipes confidenciais e altamente confidenciais de uma maneira simples com os requisitos mínimos, siga as instruções em [Configuração de base leve](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="b8587-108">If you just want to test sensitive and highly confidential teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="b8587-109">Caso pretenda testar equipes confidenciais e altamente confidenciais em uma empresa simulada, siga as instruções em [sincronização de hash de senha](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="b8587-109">If you want to test sensitive and highly confidential teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="b8587-110">Testar as equipes confidenciais e altamente confidenciais não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b8587-110">Testing sensitive and highly confidential teams does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b8587-111">Ele é fornecido aqui como uma opção para que você possa testar equipes confidenciais e altamente confidenciais e experimentá-las em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="b8587-111">It is provided here as an option so that you can test ATP and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="b8587-112">Fase 2: criar e configurar seus grupos e usuários do Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="b8587-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="b8587-113">Nesta fase, você cria e configura os usuários e grupos do Azure AD para sua organização fictícia.</span><span class="sxs-lookup"><span data-stu-id="b8587-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="b8587-114">Primeiro, crie um conjunto de grupos para uma organização comum com o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b8587-114">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="b8587-115">Crie uma guia separada no navegador e vá para o Portal do Azure[https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b8587-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="b8587-116">Se necessário, entre com as credenciais da conta de administrador global da sua assinatura paga ou de avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b8587-116">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="b8587-117">No Portal do Azure, clique em **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="b8587-118">Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="b8587-119">Na folha **Grupo**:</span><span class="sxs-lookup"><span data-stu-id="b8587-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="b8587-120">Selecione **Segurança** em **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-120">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="b8587-121">Digite **Pacote C** em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="b8587-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="b8587-122">Escolha **Atribuído** em **Tipo de Associação**.</span><span class="sxs-lookup"><span data-stu-id="b8587-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="b8587-123">Clique em **Criar** e, em seguida, feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-123">Click **Create**, and then close the **Group** blade.</span></span>
    
6.  <span data-ttu-id="b8587-124">Repita as etapas 3-5 para um novo grupo chamado **equipe de marketing**.</span><span class="sxs-lookup"><span data-stu-id="b8587-124">Repeat steps 3-5 for a new following group named **Marketing staff**.</span></span>
    
<span data-ttu-id="b8587-125">Em seguida, configure o licenciamento automático para que os membros de seus grupos recebam automaticamente a atribuição de licenças para suas assinaturas do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="b8587-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="b8587-126">No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="b8587-127">Na lista, selecione **Microsoft 365 Enterprise E5**e, em seguida, clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="b8587-127">In the list, select **Enterprise Mobility + Security E5 and Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="b8587-128">Na folha **Atribuir licença**, clique em **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-128">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="b8587-129">Na lista de grupos, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8587-129">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="b8587-130">Pacote C</span><span class="sxs-lookup"><span data-stu-id="b8587-130">C-Suite</span></span>
    
  - <span data-ttu-id="b8587-131">Equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="b8587-131">Marketing staff</span></span>
    
5. <span data-ttu-id="b8587-132">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="b8587-132">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="b8587-133">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="b8587-133">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="b8587-134">Em seguida, conecte-se ao módulo [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b8587-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="b8587-135">Preencha o nome da organização, seu local e uma senha comum. Execute esses comandos no prompt de comando do PowerShell ou no ISE (Ambiente de Script Integrado) para criar contas de usuário e adicioná-las aos grupos:</span><span class="sxs-lookup"><span data-stu-id="b8587-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
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
> <span data-ttu-id="b8587-136">O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de desenvolvimento/teste.</span><span class="sxs-lookup"><span data-stu-id="b8587-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="b8587-137">Obviamente, isso é recomendado para assinaturas de produção.</span><span class="sxs-lookup"><span data-stu-id="b8587-137">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="b8587-138">Use essas etapas para verificar se o licenciamento baseado em grupo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="b8587-138">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="b8587-139">Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="b8587-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="b8587-140">Na nova guia **Centro de administração do Microsoft 365** do seu navegador, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b8587-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="b8587-141">Na lista de usuários, clique em **CEO**.</span><span class="sxs-lookup"><span data-stu-id="b8587-141">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="b8587-142">No painel que lista as propriedades da conta de usuário **CEO**, verifique se ele recebeu a atribuição das licenças **Microsoft 365 Enterprise E5** (em \*\* Licenças de produto\*\*).</span><span class="sxs-lookup"><span data-stu-id="b8587-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5 and Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="b8587-143">Fase 3: Criar etiquetas de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="b8587-143">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="b8587-144">Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas de documentos do site de SharePoint subjacentes.</span><span class="sxs-lookup"><span data-stu-id="b8587-144">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>

1. <span data-ttu-id="b8587-145">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b8587-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="b8587-146">Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="b8587-147">Clique em **Rótulos de retenção > Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-147">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="b8587-148">No painel **Atribuir nome ao seu rótulo** digite **Confidenciais** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-148">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="b8587-149">No painel **descritores de plano de arquivo**, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-149">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="b8587-150">No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b8587-151">No painel **Revise suas configurações**, clique em **Criar o rótulo**.</span><span class="sxs-lookup"><span data-stu-id="b8587-151">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="b8587-152">Repita as etapas 3-7 para um rótulo de retenção adicional chamado **altamente confidencial**.</span><span class="sxs-lookup"><span data-stu-id="b8587-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>
    
9. <span data-ttu-id="b8587-153">No painel **Início > Rótulos**, clique em **Publicar rótulos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="b8587-154">No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="b8587-155">No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.</span><span class="sxs-lookup"><span data-stu-id="b8587-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="b8587-156">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b8587-156">Click **Done**.</span></span>
    
13. <span data-ttu-id="b8587-157">No painel **Escolher rótulos para publicar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-157">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="b8587-158">No painel **Escolher locais**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-158">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="b8587-159">No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="b8587-160">No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-teams"></a><span data-ttu-id="b8587-161">Fase 4: criar suas equipes</span><span class="sxs-lookup"><span data-stu-id="b8587-161">Phase 4: Create your teams</span></span>

<span data-ttu-id="b8587-162">Nesta fase, você criará e configurará equipes confidenciais e altamente confidenciais para a sua organização de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b8587-162">In this phase, you create and configure sensitive and highly confidential teams for your example organization.</span></span>

### <a name="sensitive-team-for-marketing-campaigns"></a><span data-ttu-id="b8587-163">Equipe sensível a campanhas de marketing</span><span class="sxs-lookup"><span data-stu-id="b8587-163">Sensitive team for marketing campaigns</span></span>

<span data-ttu-id="b8587-164">Para criar uma equipe de nível confidencial para os membros do grupo de marketing colaborarem em campanhas de marketing contínuas:</span><span class="sxs-lookup"><span data-stu-id="b8587-164">To create a sensitive-level team for members of the marketing group to collaborate on ongoing marketing campaigns:</span></span>

1. <span data-ttu-id="b8587-165">[Criar uma nova equipe privada](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) com o nome **campanhas de Marketing**.</span><span class="sxs-lookup"><span data-stu-id="b8587-165">[Create a new private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Marketing Campaigns**.</span></span>
2. <span data-ttu-id="b8587-166">Abra a equipe de **Campanhas de marketing**.</span><span class="sxs-lookup"><span data-stu-id="b8587-166">Open the **Marketing Campaigns** team.</span></span>
3.  <span data-ttu-id="b8587-167">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-167">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="b8587-168">Clique nas reticências e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b8587-168">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="b8587-169">Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b8587-169">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="b8587-170">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b8587-170">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="b8587-171">Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-171">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

<span data-ttu-id="b8587-172">Em seguida, configure a pasta de documentos do site de equipe Campanhas de marketing para o rótulo Confidencial.</span><span class="sxs-lookup"><span data-stu-id="b8587-172">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>

1.  <span data-ttu-id="b8587-173">Na guia **Campanhas de marketing – Página Inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-173">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="b8587-174">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b8587-174">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="b8587-175">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b8587-175">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="b8587-176">Em **Configurações – Aplicar Rótulo**, escolha **Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-176">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span> 

<span data-ttu-id="b8587-177">Em seguida, configure uma política DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do SharePoint com o rótulo Confidencial, que inclui o site de Campanhas de marketing, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="b8587-177">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="b8587-178">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b8587-178">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="b8587-179">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="b8587-179">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="b8587-180">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="b8587-180">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="b8587-181">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-181">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="b8587-182">No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-182">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b8587-183">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-183">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b8587-184">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-184">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b8587-185">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-185">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="b8587-186">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="b8587-186">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="b8587-187">No painel **Rótulos de retenção**, clique em \*\* Adicionar\*\*, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b8587-187">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="b8587-188">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-188">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="b8587-189">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="b8587-189">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="b8587-190">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="b8587-190">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="b8587-191">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="b8587-191">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="b8587-192">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8587-192">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="b8587-p104">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="b8587-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="b8587-196">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8587-196">Click **OK**.</span></span>
    
17. <span data-ttu-id="b8587-197">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-197">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="b8587-198">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-198">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="b8587-199">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-199">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="b8587-200">Esta é a configuração resultante da equipe de campanhas de marketing.</span><span class="sxs-lookup"><span data-stu-id="b8587-200">Here is the resulting configuration for the Marketing Campaigns team.</span></span>

![Configuração para equipe de campanhas de marketing.](../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="b8587-202">Site de equipe de estratégia empresarial</span><span class="sxs-lookup"><span data-stu-id="b8587-202">Company strategy team site</span></span>

<span data-ttu-id="b8587-203">Para criar uma equipe de nível altamente confidencial para que os membros da equipe de liderança sênior colabore na estratégia da empresa:</span><span class="sxs-lookup"><span data-stu-id="b8587-203">To create a highly confidential-level team for members of the senior leadership team to collaborate on company strategy:</span></span>

1. <span data-ttu-id="b8587-204">[Criar uma nova equipe privada](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) com o nome **Estratégia empresarial**.</span><span class="sxs-lookup"><span data-stu-id="b8587-204">[Create a new private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="b8587-205">Abra a equipe de **Estratégia Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="b8587-205">Open the **Company Strategy** team.</span></span>
3.  <span data-ttu-id="b8587-206">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-206">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="b8587-207">Clique nas reticências e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="b8587-207">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="b8587-208">Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b8587-208">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="b8587-209">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b8587-209">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="b8587-210">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="b8587-210">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
8.  <span data-ttu-id="b8587-211">Desative **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-211">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="b8587-212">Em seguida, configure a pasta de documentos do site subjacente do SharePoint da estratégia empresarial para o rótulo Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="b8587-212">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>

1.  <span data-ttu-id="b8587-213">Na guia **Estratégia empresarial – Página Inicial** do navegador, clique em **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="b8587-213">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="b8587-214">Clique no ícone de configurações e clique em **Configurações de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b8587-214">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="b8587-215">Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b8587-215">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="b8587-216">Em **Configurações – Aplicar Rótulo**, escolha **Altamente Confidencial** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-216">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span> 

<span data-ttu-id="b8587-217">Em seguida, configure uma política de DLP que bloqueie os usuários quando eles compartilham um documento em um site subjacente do SharePoint com o rótulo Altamente Confidencial, que inclui o site de Estratégia Empresarial, fora da organização.</span><span class="sxs-lookup"><span data-stu-id="b8587-217">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="b8587-218">Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com seu administrador global.</span><span class="sxs-lookup"><span data-stu-id="b8587-218">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="b8587-219">Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="b8587-219">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="b8587-220">No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="b8587-220">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="b8587-221">No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-221">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="b8587-222">No painel **Atribuir um nome à política**, digite **Sites do SharePoint de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-222">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="b8587-223">No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-223">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="b8587-224">Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-224">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b8587-225">No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-225">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="b8587-226">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.</span><span class="sxs-lookup"><span data-stu-id="b8587-226">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="b8587-227">No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b8587-227">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="b8587-228">No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-228">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="b8587-229">No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.</span><span class="sxs-lookup"><span data-stu-id="b8587-229">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="b8587-230">No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.</span><span class="sxs-lookup"><span data-stu-id="b8587-230">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="b8587-231">No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.</span><span class="sxs-lookup"><span data-stu-id="b8587-231">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="b8587-232">Na caixa de texto, digite ou cole o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8587-232">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="b8587-p105">Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.</span><span class="sxs-lookup"><span data-stu-id="b8587-p105">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="b8587-236">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8587-236">Click **OK**.</span></span>
    
17. <span data-ttu-id="b8587-237">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-237">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="b8587-238">No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-238">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="b8587-239">No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b8587-239">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="b8587-240">Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo confidencial com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b8587-240">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="b8587-241">O nome do rótulo é Estratégia empresarial</span><span class="sxs-lookup"><span data-stu-id="b8587-241">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="b8587-242">A criptografia está ativada</span><span class="sxs-lookup"><span data-stu-id="b8587-242">Encryption is enabled</span></span>
- <span data-ttu-id="b8587-243">O grupo de estratégia empresarial tem permissões de Coautoria.</span><span class="sxs-lookup"><span data-stu-id="b8587-243">The site group has Co-Author permissions.</span></span>

<span data-ttu-id="b8587-244">Depois de criar, publique o novo rótulo.</span><span class="sxs-lookup"><span data-stu-id="b8587-244">After creating, publish the new label.</span></span> <span data-ttu-id="b8587-245">Se entrar como um membro do grupo de estratégias empresarial, você verá o novo rótulo na opção confidencialidade na barra de ferramentas página inicial do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="b8587-245">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="b8587-246">Selecione o rótulo de estratégia empresarial na opção confidencialidade para atribuir o rótulo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b8587-246">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="b8587-247">Esta é a configuração resultante da equipe de estratégia empresarial.</span><span class="sxs-lookup"><span data-stu-id="b8587-247">Here is the resulting configuration for the Company Strategy team.</span></span>

![A configuração da equipe de Estratégia Empresarial.](../media/highlyconfidential-team-config-dev-test.png) 

<span data-ttu-id="b8587-249">Os arquivos na seção documentos do site da estratégia empresarial subjacente do SharePoint recebem o rótulo de retenção altamente confidencial e estão sujeitos à política de DLP configurada.</span><span class="sxs-lookup"><span data-stu-id="b8587-249">Files in the documents section of the underlying Company Strategy SharePoint site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="b8587-250">Os arquivos também podem ter o rótulo diferencial da estratégia empresarial atribuído.</span><span class="sxs-lookup"><span data-stu-id="b8587-250">Files can also have the Company Strategy sensitivity label assigned.</span></span>    
  
## <a name="next-step"></a><span data-ttu-id="b8587-251">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b8587-251">Next step</span></span>

<span data-ttu-id="b8587-252">Quando você estiver pronto para a implantação da produção, consulte [Arquivos seguros no Microsoft Teams](secure-files-in-teams.md) para obter informações detalhadas e links para os artigos de implantação passo a passo.</span><span class="sxs-lookup"><span data-stu-id="b8587-252">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-files-in-teams.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8587-253">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8587-253">See Also</span></span>

[<span data-ttu-id="b8587-254">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="b8587-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
