---
title: Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este Guia de Laboratório de Teste para habilitar configurações de segurança adicionais do Microsoft 365 no ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 928deae34dc16c70776eb512188d1a36ae169da5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909781"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5ed08-103">Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5ed08-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5ed08-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="5ed08-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5ed08-105">Com as instruções neste artigo, você configura configurações adicionais do Microsoft 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5ed08-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5ed08-107">Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5ed08-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5ed08-108">Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5ed08-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5ed08-109">Se você deseja apenas configurar a segurança aumentada do Microsoft 365 de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5ed08-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5ed08-110">Se você quiser configurar a maior segurança do Microsoft 365 em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5ed08-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ed08-111">Testar a segurança aumentada do Microsoft 365 não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5ed08-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5ed08-112">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="5ed08-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="5ed08-113">Fase 2: Configurar maior segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ed08-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="5ed08-114">Nesta fase, você habilita maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5ed08-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="5ed08-115">Para obter detalhes e configurações adicionais, consulte [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="5ed08-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="5ed08-116">Configurar o SharePoint Online para bloquear aplicativos que não suportam autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="5ed08-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="5ed08-117">Os aplicativos que não suportam a autenticação moderna não podem ter configurações de identidade e acesso a [dispositivos aplicadas](../security/office-365-security/microsoft-365-policies-configurations.md) a eles, o que é um elemento importante para proteger sua assinatura do Microsoft 365 e seus ativos digitais.</span><span class="sxs-lookup"><span data-stu-id="5ed08-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="5ed08-118">Vá para o Centro de administração do Microsoft 365 ( ) e entre na assinatura do laboratório de teste do [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5ed08-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="5ed08-119">Se você estiver usando o ambiente de teste leve do Microsoft 365, entre no computador local.</span><span class="sxs-lookup"><span data-stu-id="5ed08-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="5ed08-120">Se você estiver usando o ambiente de teste do Microsoft 365 empresarial simulado, use o portal do [Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e entre no CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="5ed08-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="5ed08-121">Na nova guia Centro de administração do **Microsoft 365,** em **Centros de administração** no painel de navegação esquerdo, clique em **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="5ed08-122">Na nova guia Centro de **administração do SharePoint,** clique em **Políticas > Controle de Acesso.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="5ed08-123">Clique **em Aplicativos que não suportam autenticação moderna,** selecione **Bloquear** acesso e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="5ed08-124">Habilitar o Defender para Office 365 para SharePoint, OneDrive for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ed08-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="5ed08-125">O Defender for Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="5ed08-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="5ed08-126">Vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5ed08-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5ed08-127">No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Política** e em **Anexos Seguros.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="5ed08-128">Em **Proteger arquivos no SharePoint, no OneDrive e no Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="5ed08-129">selecione **Ativar a ATP para SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="5ed08-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="5ed08-131">Habilitar anti-malware</span><span class="sxs-lookup"><span data-stu-id="5ed08-131">Enable anti-malware</span></span>

<span data-ttu-id="5ed08-132">Malware é composto por vírus e spywares.</span><span class="sxs-lookup"><span data-stu-id="5ed08-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="5ed08-133">Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar.</span><span class="sxs-lookup"><span data-stu-id="5ed08-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="5ed08-134">Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor.</span><span class="sxs-lookup"><span data-stu-id="5ed08-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="5ed08-135">O Microsoft 365 tem recursos de filtragem de malware e spam integrados que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e ajudam a proteger você contra spam.</span><span class="sxs-lookup"><span data-stu-id="5ed08-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="5ed08-136">Para obter mais informações, consulte [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="5ed08-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="5ed08-137">Para garantir que o processamento anti-malware está sendo executado em arquivos com tipos de arquivo de anexo comuns:</span><span class="sxs-lookup"><span data-stu-id="5ed08-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="5ed08-138">Clique no botão voltar no navegador para voltar à **página Política.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="5ed08-139">Clique **em Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="5ed08-140">Clique duas vezes na política chamada **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="5ed08-141">Na janela **Política anti-malware,** clique **em Configurações**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="5ed08-142">Em **Filtro Tipos de Anexo Comuns,** selecione **Em** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="5ed08-143">Fase 3: Examinar o painel de segurança</span><span class="sxs-lookup"><span data-stu-id="5ed08-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="5ed08-144">O gerenciamento de ameaças no Microsoft 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivo móvel aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e saída contra software mal-intencionado e spam.</span><span class="sxs-lookup"><span data-stu-id="5ed08-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="5ed08-145">Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se os enviadores são ou não mal-intencionados a spoofing de contas do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5ed08-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="5ed08-146">Para ver o painel de segurança:</span><span class="sxs-lookup"><span data-stu-id="5ed08-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="5ed08-147">Se necessário, vá para o Centro de [Conformidade](https://protection.office.com) & segurança e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5ed08-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5ed08-148">No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Painel**.</span><span class="sxs-lookup"><span data-stu-id="5ed08-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="5ed08-149">Dê uma olhada de perto em todos os cartões no painel para se familiarizar com as informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="5ed08-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="5ed08-150">Para obter mais informações, consulte [Painel de Segurança](../security/office-365-security/security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="5ed08-150">For more information, see [Security Dashboard](../security/office-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="5ed08-151">Fase 4: Examinar a Pontuação Segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5ed08-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="5ed08-152">A Pontuação Segura da Microsoft mostra sua postura de segurança como um número, o que indica seu nível atual em relação aos recursos disponíveis em sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="5ed08-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="5ed08-153">Ele também oferece uma lista de ações de melhoria que você pode tomar para melhorar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="5ed08-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="5ed08-154">Crie uma nova guia no navegador e vá para o Centro de Segurança do [Microsoft 365](https://security.microsoft.com/)e clique em **Pontuação segura.**</span><span class="sxs-lookup"><span data-stu-id="5ed08-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="5ed08-155">Na guia **Visão**  geral, observe sua Pontuação Segura atual e como ela se compara com a média global e assinaturas com um número semelhante de licenças.</span><span class="sxs-lookup"><span data-stu-id="5ed08-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="5ed08-156">Na guia **Ações de melhoria,** leia a lista de ações que você pode tomar para aumentar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="5ed08-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="5ed08-157">Para obter mais informações, consulte [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="5ed08-157">For more information, see [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ed08-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5ed08-158">Next steps</span></span>

<span data-ttu-id="5ed08-159">Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="5ed08-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed08-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ed08-160">See also</span></span>

[<span data-ttu-id="5ed08-161">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5ed08-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5ed08-162">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5ed08-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5ed08-163">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5ed08-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)