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
description: Use este Guia de Laboratório de Teste para habilitar configurações de segurança adicionais do Microsoft 365 em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846995"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="822b4-103">Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="822b4-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="822b4-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="822b4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="822b4-105">Com as instruções neste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="822b4-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="822b4-107">Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="822b4-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="822b4-108">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="822b4-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="822b4-109">Se você quiser apenas configurar a segurança aumentada do Microsoft 365 de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="822b4-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="822b4-110">Se você quiser configurar maior segurança do Microsoft 365 em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="822b4-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="822b4-111">O teste de maior segurança do Microsoft 365 não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="822b4-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="822b4-112">Ele é fornecido aqui como uma opção para que você possa testar licenciamento automatizado e associação de grupo e experimentar com ele em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="822b4-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="822b4-113">Fase 2: Configurar maior segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="822b4-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="822b4-114">Nesta fase, você habilita maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="822b4-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="822b4-115">Para obter mais detalhes e configurações, consulte [Configurar seu locatário para aumentar a segurança.](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="822b4-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="822b4-116">Configurar o SharePoint Online para bloquear aplicativos que não suportam autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="822b4-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="822b4-117">Os aplicativos que não suportam a autenticação moderna não podem ter configurações de acesso de dispositivo e identidade [aplicadas](../security/office-365-security/microsoft-365-policies-configurations.md) a eles, o que é um elemento importante para proteger sua assinatura do Microsoft 365 e seus ativos digitais.</span><span class="sxs-lookup"><span data-stu-id="822b4-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="822b4-118">Vá para o Centro de administração do Microsoft 365 ( ) e entre em sua assinatura de laboratório de teste do [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="822b4-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="822b4-119">Se você estiver usando o ambiente de teste leve do Microsoft 365, entre no computador local.</span><span class="sxs-lookup"><span data-stu-id="822b4-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="822b4-120">Se você estiver usando o ambiente de teste corporativo simulado do Microsoft 365, use o portal do [Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e entre no CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="822b4-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="822b4-121">Na nova guia centro de administração do **Microsoft 365,** em **Centros** de administração no painel de navegação esquerdo, clique **em SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="822b4-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="822b4-122">Na nova guia centro **de administração do SharePoint,** clique em **Políticas > controle de acesso.**</span><span class="sxs-lookup"><span data-stu-id="822b4-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="822b4-123">Clique **em Aplicativos que não suportam autenticação moderna,** selecione **Bloquear acesso** e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="822b4-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="822b4-124">Habilitar o Defender para Office 365 para SharePoint, OneDrive for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="822b4-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="822b4-125">O Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="822b4-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="822b4-126">Vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="822b4-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="822b4-127">No painel de navegação esquerdo, em **Gerenciamento de ameaças,** clique em **Política** e em **Anexos Seguros.**</span><span class="sxs-lookup"><span data-stu-id="822b4-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="822b4-128">Em **Proteger arquivos no SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="822b4-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="822b4-129">selecione **Ativar ATP para SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="822b4-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="822b4-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="822b4-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="822b4-131">Habilitar anti-malware</span><span class="sxs-lookup"><span data-stu-id="822b4-131">Enable anti-malware</span></span>

<span data-ttu-id="822b4-132">Malware é composto por vírus e spywares.</span><span class="sxs-lookup"><span data-stu-id="822b4-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="822b4-133">Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar.</span><span class="sxs-lookup"><span data-stu-id="822b4-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="822b4-134">Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor.</span><span class="sxs-lookup"><span data-stu-id="822b4-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="822b4-135">O Microsoft 365 tem recursos integrados de filtragem de malware e spam que ajudam a proteger mensagens de entrada e de saída contra softwares mal-intencionados e ajudam a protegê-lo contra spam.</span><span class="sxs-lookup"><span data-stu-id="822b4-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="822b4-136">Para obter mais informações, [consulte Anti-spam & proteção anti-malware.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="822b4-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="822b4-137">Para garantir que o processamento anti-malware está sendo executado em arquivos com tipos de arquivo de anexo comuns:</span><span class="sxs-lookup"><span data-stu-id="822b4-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="822b4-138">Clique no botão Voltar no navegador para voltar à **página Política.**</span><span class="sxs-lookup"><span data-stu-id="822b4-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="822b4-139">Clique **em Anti-malware.**</span><span class="sxs-lookup"><span data-stu-id="822b4-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="822b4-140">Clique duas vezes na política chamada **Padrão.**</span><span class="sxs-lookup"><span data-stu-id="822b4-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="822b4-141">Na janela **política anti-malware,** clique em **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="822b4-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="822b4-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="822b4-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="822b4-143">Fase 3: Examinar o painel de segurança</span><span class="sxs-lookup"><span data-stu-id="822b4-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="822b4-144">O gerenciamento de ameaças no Microsoft 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e de saída contra software e spam mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="822b4-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="822b4-145">Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se os envios são ou não contas maliciosamente spoofing de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="822b4-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="822b4-146">Para ver o painel de segurança:</span><span class="sxs-lookup"><span data-stu-id="822b4-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="822b4-147">Se necessário, vá para o [Centro de Conformidade & segurança](https://protection.office.com) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="822b4-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="822b4-148">No painel de navegação esquerdo, em Gerenciamento **de ameaças,** clique em **Painel.**</span><span class="sxs-lookup"><span data-stu-id="822b4-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="822b4-149">Dê uma olhada em todos os cartões no painel para se familiarizar com as informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="822b4-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="822b4-150">Para obter mais informações, consulte [o Painel de Segurança.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)</span><span class="sxs-lookup"><span data-stu-id="822b4-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="822b4-151">Fase 4: Examinar o Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="822b4-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="822b4-152">O Microsoft Secure Score mostra a postura de segurança como um número, o que indica seu nível atual em relação aos recursos disponíveis em sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="822b4-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="822b4-153">Ele também fornece uma lista de ações de melhoria que você pode tomar para melhorar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="822b4-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="822b4-154">Crie uma nova guia no navegador e vá para a central de segurança do [Microsoft 365](https://security.microsoft.com/)e clique em **Classificação de segurança.**</span><span class="sxs-lookup"><span data-stu-id="822b4-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="822b4-155">Na guia **Visão geral,**  anote sua Classificação de Segurança atual e como ela se compara com a média global e as assinaturas com um número semelhante de licenças.</span><span class="sxs-lookup"><span data-stu-id="822b4-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="822b4-156">Na guia **Ações de aperfeiçoamento,** leia a lista de ações que você pode tomar para aumentar sua pontuação.</span><span class="sxs-lookup"><span data-stu-id="822b4-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="822b4-157">Para obter mais informações, consulte [o Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)</span><span class="sxs-lookup"><span data-stu-id="822b4-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="822b4-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="822b4-158">Next steps</span></span>

<span data-ttu-id="822b4-159">Explore recursos [e funcionalidades adicionais](m365-enterprise-test-lab-guides.md#information-protection) de proteção de informações em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="822b4-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="822b4-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="822b4-160">See also</span></span>

[<span data-ttu-id="822b4-161">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="822b4-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="822b4-162">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="822b4-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="822b4-163">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="822b4-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
