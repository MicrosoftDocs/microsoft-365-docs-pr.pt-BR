---
title: Defina grupos e usuários - Ambiente de desenvolvimento/teste de uma campanha política
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Resumo: Crie assinaturas de teste do Office 365 e Enterprise Mobility + Security (EMS) com usuários e grupos para um ambiente de desenvolvimento/teste de campanha política.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e21cdfb0aabbdb10397d6d16c879756449a498e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202911"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="896cb-103">Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política</span><span class="sxs-lookup"><span data-stu-id="896cb-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="896cb-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="896cb-104">**Applies to**</span></span>
- [<span data-ttu-id="896cb-105">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="896cb-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

 <span data-ttu-id="896cb-106">**Resumo:** Crie assinaturas de teste do Office 365 e Enterprise Mobility + Security (EMS) com usuários e grupos para um ambiente de desenvolvimento/teste de campanha política.</span><span class="sxs-lookup"><span data-stu-id="896cb-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="896cb-107">Use as instruções deste artigo para criar um ambiente de desenvolvimento/de teste que inclui grupos e contas de usuário simplificadas para a solução [Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="896cb-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="896cb-108">Fase 1: Criar seu ambiente de desenvolvimento/teste do Office 365</span><span class="sxs-lookup"><span data-stu-id="896cb-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="896cb-109">Nesta fase, você deve obter assinaturas de avaliação do Office 365 E5 e do Enterprise Mobility + Security (EMS) E5 para uma organização fictícia que representa uma campanha política.</span><span class="sxs-lookup"><span data-stu-id="896cb-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="896cb-110">Primeiro, siga as instruções em **Fase 2** de [A configuração de base leve](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="896cb-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="896cb-111">Em seguida, inscreva-se para a assinatura de avaliação do EMS E5 e adicione-o à mesma organização da assinatura de avaliação da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="896cb-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="896cb-112">Se necessário, entre no centro de administração com as credenciais da conta do administrador global da sua assinatura de avaliação.</span><span class="sxs-lookup"><span data-stu-id="896cb-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="896cb-113">Para obter ajuda, confira [Onde acessar](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="896cb-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="896cb-114">Clique no bloco de **Administração**.</span><span class="sxs-lookup"><span data-stu-id="896cb-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="896cb-115">Na guia **centro de administração do Microsoft 365** em seu navegador, na navegação à esquerda, clique em **Cobrança > Comprar serviços**.</span><span class="sxs-lookup"><span data-stu-id="896cb-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="896cb-p102">Na página **Comprar serviços**, encontre o item **Enterprise Mobility + Security E5**. Passe o ponteiro do mouse sobre ele e clique em **Iniciar avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="896cb-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="896cb-118">Na página **Confirmar seu pedido**, clique em **Experimentar agora**.</span><span class="sxs-lookup"><span data-stu-id="896cb-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="896cb-119">Na página **Recibo do pedido**, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="896cb-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="896cb-120">Em seguida, habilite a licença do EMS E5 para a sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="896cb-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="896cb-121">Na guia **centro de administração do Microsoft 365** no navegador, na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="896cb-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="896cb-122">Clique em sua conta de administrador global e, em seguida, clique em **Editar** para **Licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="896cb-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="896cb-123">No painel **Licenças de produto**, mude a licença de produto de **Enterprise Mobility + Security E5** para **Ativada**, clique em **Salvar** e clique em **Fechar** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="896cb-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="896cb-124">Fase 2: Criar e configurar seus grupos do Azure Active Directory (AD) (Active Directory)</span><span class="sxs-lookup"><span data-stu-id="896cb-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="896cb-125">Nesta fase, você cria e configura os grupos do Azure AD para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="896cb-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="896cb-126">Primeiro, crie um conjunto de grupos para uma campanha política com o Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="896cb-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="896cb-127">Em uma guia separada em seu navegador, vá para o portal do Microsoft Azure em <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="896cb-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="896cb-128">Se necessário, entre com as credenciais da conta de administrador global da sua assinatura de avaliação do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="896cb-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="896cb-129">No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="896cb-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="896cb-130">Siga as seguintes etapas para cada nome do grupo nesta lista:</span><span class="sxs-lookup"><span data-stu-id="896cb-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="896cb-131">Equipe estratégica e sênior</span><span class="sxs-lookup"><span data-stu-id="896cb-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="896cb-132">Equipe de TI</span><span class="sxs-lookup"><span data-stu-id="896cb-132">IT staff</span></span>

   - <span data-ttu-id="896cb-133">Equipe de análise</span><span class="sxs-lookup"><span data-stu-id="896cb-133">Analytics staff</span></span>

   - <span data-ttu-id="896cb-134">Equipe principal regular</span><span class="sxs-lookup"><span data-stu-id="896cb-134">Regular core staff</span></span>

   - <span data-ttu-id="896cb-135">Equipe de operações</span><span class="sxs-lookup"><span data-stu-id="896cb-135">Operations staff</span></span>

   - <span data-ttu-id="896cb-136">Equipe de campo</span><span class="sxs-lookup"><span data-stu-id="896cb-136">Field staff</span></span>

1. <span data-ttu-id="896cb-137">Na folha **Todos os grupos**, clique em **+ Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="896cb-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="896cb-138">Digite o nome do grupo na lista em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="896cb-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="896cb-139">Selecione **Usuário dinâmico** em **Associação**.</span><span class="sxs-lookup"><span data-stu-id="896cb-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="896cb-140">Selecione **Sim** para **Habilitar recursos do Office**.</span><span class="sxs-lookup"><span data-stu-id="896cb-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="896cb-141">Clique em **Adicionar consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="896cb-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="896cb-142">Em **Adicionar usuários onde**, selecione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="896cb-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="896cb-143">No campo seguinte, selecione **Igual a**.</span><span class="sxs-lookup"><span data-stu-id="896cb-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="896cb-144">No campo seguinte, digite o nome do grupo na lista.</span><span class="sxs-lookup"><span data-stu-id="896cb-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="896cb-145">Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="896cb-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="896cb-146">Clique em **Usuários e grupos – Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="896cb-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="896cb-147">Em seguida, configure os grupos para que os membros tenham licenças do Office 365 E5 e EMS E5 atribuídas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="896cb-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="896cb-148">No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="896cb-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="896cb-149">Na lista, selecione **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir+**.</span><span class="sxs-lookup"><span data-stu-id="896cb-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="896cb-150">Na folha **Atribuir licença**, clique em **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="896cb-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="896cb-151">Na lista de grupos, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="896cb-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="896cb-152">Equipe de análise</span><span class="sxs-lookup"><span data-stu-id="896cb-152">Analytics staff</span></span>

   - <span data-ttu-id="896cb-153">Equipe de campo</span><span class="sxs-lookup"><span data-stu-id="896cb-153">Field staff</span></span>

   - <span data-ttu-id="896cb-154">Equipe de TI</span><span class="sxs-lookup"><span data-stu-id="896cb-154">IT staff</span></span>

   - <span data-ttu-id="896cb-155">Equipe de operações</span><span class="sxs-lookup"><span data-stu-id="896cb-155">Operations staff</span></span>

   - <span data-ttu-id="896cb-156">Equipe principal regular</span><span class="sxs-lookup"><span data-stu-id="896cb-156">Regular core staff</span></span>

   - <span data-ttu-id="896cb-157">Equipe estratégica e sênior</span><span class="sxs-lookup"><span data-stu-id="896cb-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="896cb-158">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="896cb-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="896cb-159">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="896cb-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="896cb-160">Fase 3: Adicionar as suas conta de usuário</span><span class="sxs-lookup"><span data-stu-id="896cb-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="896cb-161">Nesta fase, adicione exemplos de contas de usuário para a sua campanha política.</span><span class="sxs-lookup"><span data-stu-id="896cb-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="896cb-162">Primeiro, conecte-se ao módulo [PowerShell do Azure Active Directory para Graph](../../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="896cb-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="896cb-163">Em seguida, preencha o nome de sua organização, o local e uma senha comum e, em seguida, execute esses comandos desde o prompt de comando do PowerShell ou Ambiente de Script Integrado (ISE):</span><span class="sxs-lookup"><span data-stu-id="896cb-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="896cb-p104">O uso de uma senha comum aqui serve para a automação e a facilidade da configuração para um ambiente de desenvolvimento/de teste. Isso não é recomendável para assinaturas de produção. Ao entrar com cada uma dessas novas contas de usuário, você deverá alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="896cb-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="896cb-167">Use estas etapas para verificar se a associação de grupo dinâmico e o licenciamento com base em grupo estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="896cb-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="896cb-168">Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.</span><span class="sxs-lookup"><span data-stu-id="896cb-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="896cb-169">Na nova guia **Centro de administração do Microsoft 365** do seu navegador, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="896cb-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="896cb-170">Na lista de usuários, clique em **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="896cb-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="896cb-171">No painel que lista as propriedades da conta de usuário **Candidato**, verifique se:</span><span class="sxs-lookup"><span data-stu-id="896cb-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="896cb-172">É um membro do grupo **Equipe estratégica e sênior** (em **Associações de grupo**).</span><span class="sxs-lookup"><span data-stu-id="896cb-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="896cb-173">Foram-lhe atribuídas as licenças do **Enterprise Mobility + Security E5** e do **Office 365 Enterprise E5** (nas **Licenças de produto**).</span><span class="sxs-lookup"><span data-stu-id="896cb-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="896cb-174">Feche o painel da conta de usuário do **Candidato**.</span><span class="sxs-lookup"><span data-stu-id="896cb-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="896cb-175">Valores de registro para referência futura</span><span class="sxs-lookup"><span data-stu-id="896cb-175">Record values for future reference</span></span>

<span data-ttu-id="896cb-176">Grave esses valores para trabalhar com as assinaturas de avaliação do Office 365 e do EMS para o ambiente de desenvolvimento/de teste:</span><span class="sxs-lookup"><span data-stu-id="896cb-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="896cb-177">Nome da sua organização de assinatura de avaliação: </span><span class="sxs-lookup"><span data-stu-id="896cb-177">Your trial subscription organization name:</span></span> ![Sublinhado](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="896cb-179">Por exemplo, para o nome de domínio de assinatura de avaliação contoso.onmicrosoft.com, o nome da organização é "contoso".</span><span class="sxs-lookup"><span data-stu-id="896cb-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="896cb-180">Nome do administrador global:</span><span class="sxs-lookup"><span data-stu-id="896cb-180">The global administrator name:</span></span> ![Sublinhado](../../media/Common-Images/TableLine.png)<span data-ttu-id="896cb-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="896cb-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="896cb-183">Grave a senha dessa conta e a senha inicial comum das outras contas de usuário em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="896cb-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="896cb-184">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="896cb-184">Next step</span></span>

<span data-ttu-id="896cb-185">Criar os quatro diferentes tipos de sites de equipe do SharePoint Online neste ambiente de desenvolvimento/de teste com [Criar sites de equipe em um ambiente de desenvolvimento/de teste de campanha política](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="896cb-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="896cb-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="896cb-186">See also</span></span>

[<span data-ttu-id="896cb-187">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile</span><span class="sxs-lookup"><span data-stu-id="896cb-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="896cb-188">Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política</span><span class="sxs-lookup"><span data-stu-id="896cb-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="896cb-189">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="896cb-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="896cb-190">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="896cb-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)