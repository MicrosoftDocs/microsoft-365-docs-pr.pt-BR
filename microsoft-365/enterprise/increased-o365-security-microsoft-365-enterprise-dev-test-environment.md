---
title: Segurança ampliada do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Office 365 seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864946"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="69276-103">Segurança ampliada do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69276-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="69276-104">Com as instruções deste artigo, você deve configurar as configurações adicionais do Office 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="69276-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="69276-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="69276-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="69276-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69276-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="69276-108">Se você deseja configurar maior segurança do Office 365 de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="69276-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="69276-109">Se você deseja configurar maior segurança do Office 365 em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="69276-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69276-p101">Testar maior segurança do Office 365 não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="69276-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="69276-112">Fase 2: Configurar maior segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="69276-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="69276-p102">Nesta fase, você pode habilitar maior segurança do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise. Para obter detalhes adicionais e configurações, consulte [Configure seu locatário do Office 365 para aumentar a segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="69276-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="69276-115">Configurar o SharePoint Online para bloquear os aplicativos que não há suporte para autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="69276-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="69276-116">Aplicativos que não têm suporte para autenticação moderna não podem ter a [identidade e dispositivo acessam as configurações](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais.</span><span class="sxs-lookup"><span data-stu-id="69276-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="69276-117">Vá para o portal do Office 365 ([https://portal.office.com](https://portal.office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="69276-117">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="69276-118">Se você estiver usando o ambiente de teste do Microsoft 365 leve, entre do computador local.</span><span class="sxs-lookup"><span data-stu-id="69276-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="69276-119">Se você estiver usando o ambiente de teste do enterprise simulado 365 da Microsoft, use o [portal Azure](https://portal.azure.com) para conectar a máquina virtual CLIENT1 e entrar em CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="69276-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="69276-120">A partir da guia do **Centro de administração do Microsoft 365** , clique em **Admin**.</span><span class="sxs-lookup"><span data-stu-id="69276-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="69276-121">Na guia do **Centro de administração do Microsoft 365** nova, clique em **centrais de Admin > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="69276-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="69276-122">Na guia nova **Centro de administração do SharePoint** , clique em **controle de acesso**.</span><span class="sxs-lookup"><span data-stu-id="69276-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="69276-123">Em **aplicativos que não há suporte para autenticação moderna**, clique em **bloco > Okey**.</span><span class="sxs-lookup"><span data-stu-id="69276-123">Under **Apps that don’t support modern authentication**, click **Block > OK**.</span></span>


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="69276-124">Habilitar o Advanced proteção contra ameaças (ATP) para SharePoint, OneDrive e equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="69276-124">Enable Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="69276-p103">O Office 365 avançadas ameaça proteção (ATP) é um recurso do Exchange Online Protection (EOP) que ajuda a manter o malware fora do seu email. Com ATP, criar políticas no Centro de administração do Exchange (EAC) ou a segurança & Centro de conformidade que ajudam a garantir a seus usuários acessar apenas links ou anexos em emails que são identificadas como não mal-intencionado. Para obter mais informações, consulte [proteção contra ameaças avançadas para anexos seguros e links de seguros](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="69276-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="69276-128">Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.</span><span class="sxs-lookup"><span data-stu-id="69276-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="69276-129">Na guia **segurança e conformidade** nova, clique em **gerenciamento de ameaças > política**.</span><span class="sxs-lookup"><span data-stu-id="69276-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="69276-130">Clique em **anexos de ATP seguros**.</span><span class="sxs-lookup"><span data-stu-id="69276-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="69276-131">No painel **anexos seguros** , selecione **Ativar ATP para SharePoint, OneDrive e as equipes da Microsoft**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="69276-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="69276-132">Habilitar antimalware</span><span class="sxs-lookup"><span data-stu-id="69276-132">Enable anti-malware</span></span>

<span data-ttu-id="69276-p104">Malware é composto de vírus e spyware. Os vírus infectar outros programas e dados e eles espalham em todo o seu computador procurando programas infectar. Spyware se refere ao malware que coletam suas informações pessoais, como informações de entrada e de dados pessoais e enviá-la de volta para o autor de malware.</span><span class="sxs-lookup"><span data-stu-id="69276-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="69276-p105">O Office 365 tem recursos que ajudam a proteger mensagens de entrada e saídas de software mal-intencionado e ajudam a proteger contra spam de filtragem de spam e malware interno. Para obter mais informações, consulte [proteção antispam e antimalware no Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="69276-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="69276-138">Para garantir que o processamento de antimalware estiver sendo executado no arquivos com tipos de arquivo de anexo comuns:</span><span class="sxs-lookup"><span data-stu-id="69276-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="69276-139">Clique no botão Voltar no navegador para voltar à página de **política** .</span><span class="sxs-lookup"><span data-stu-id="69276-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="69276-140">Clique em **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="69276-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="69276-141">Clique duas vezes a política de chamada **padrão**.</span><span class="sxs-lookup"><span data-stu-id="69276-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="69276-142">Na janela **política antimalware** , clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="69276-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="69276-143">Em **tipos de anexo comuns de filtro**, clique em **em > Salvar**.</span><span class="sxs-lookup"><span data-stu-id="69276-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="69276-144">Fase 3: Examinar os logs e ferramentas de segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="69276-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="69276-145">Nesta fase, você observar serviços internos que informam sobre eventos de segurança e medem sua postura geral de segurança.</span><span class="sxs-lookup"><span data-stu-id="69276-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="69276-146">Painel de gerenciamento de ameaça</span><span class="sxs-lookup"><span data-stu-id="69276-146">Threat management dashboard</span></span>

<span data-ttu-id="69276-p106">Gerenciamento de ameaça do Office 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivo móvel aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e saídas contra spam e softwares mal-intencionados. Você também pode usar threat management para proteger a reputação do seu domínio e para determinar se ou não os remetentes são falsificação de modo mal-intencionado contas do seu domínio. Para obter mais informações, consulte [gerenciamento de ameaça na segurança do Office 365 & Centro de conformidade](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="69276-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="69276-150">Use estas etapas para exibir o painel de gerenciamento do Office 365 ameaça:</span><span class="sxs-lookup"><span data-stu-id="69276-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="69276-151">Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.</span><span class="sxs-lookup"><span data-stu-id="69276-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="69276-152">Na guia **segurança e conformidade** nova, clique em **gerenciamento de ameaças > Painel**.</span><span class="sxs-lookup"><span data-stu-id="69276-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="69276-153">Na guia nova **painel** no seu navegador, observe as tendências de malware, ideias e outras seções do painel de controle.</span><span class="sxs-lookup"><span data-stu-id="69276-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="69276-154">Painel de segurança de aplicativo de nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="69276-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="69276-p107">Segurança de aplicativo do Office 365 nuvem, anteriormente conhecido como o Office 365 gerenciamento avançado de segurança, permite que você crie diretivas que monitoram e informam atividades suspeitas em sua assinatura do Office 365, para que você possa investigar e levar possíveis ação de remediação. Para obter mais informações, consulte [Visão geral do Office 365 App segurança na nuvem](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="69276-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="69276-157">Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.</span><span class="sxs-lookup"><span data-stu-id="69276-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="69276-158">Na guia **segurança e conformidade** nova, clique em **alertas > Gerenciar alertas de Avançado > Ir para segurança de aplicativo de nuvem do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="69276-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="69276-159">Na guia **Segurança de aplicativo de nuvem** nova, observe o modo de exibição do painel e a lista de políticas padrão que monitorar para várias atividades em sua assinatura do Office 365.</span><span class="sxs-lookup"><span data-stu-id="69276-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="69276-160">Clique no ícone de painel para ver um resumo das atividades de segurança de aplicativo de nuvem que estão sendo rastreadas.</span><span class="sxs-lookup"><span data-stu-id="69276-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="69276-161">Clique em **investigar** (o ícone de óculos) e, em seguida, **o log de atividade** para ver a lista de entradas recentes e outras atividades.</span><span class="sxs-lookup"><span data-stu-id="69276-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="69276-162">Pontuação de segura</span><span class="sxs-lookup"><span data-stu-id="69276-162">Secure Score</span></span>

1. <span data-ttu-id="69276-163">Criar uma nova guia no seu navegador e vá para **securescore.office.com**.</span><span class="sxs-lookup"><span data-stu-id="69276-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="69276-164">Na **Guia do painel**, observe sua pontuação de seguro atual e a lista de ações na fila para aumentar a pontuação.</span><span class="sxs-lookup"><span data-stu-id="69276-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="69276-165">Consulte a etapa [Configure maior segurança para o Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) na fase de **proteção de informações** para obter informações e links para definir essas configurações em produção.</span><span class="sxs-lookup"><span data-stu-id="69276-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="69276-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="69276-166">Next step</span></span>

<span data-ttu-id="69276-167">Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="69276-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="69276-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="69276-168">See also</span></span>

[<span data-ttu-id="69276-169">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69276-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="69276-170">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69276-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="69276-171">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="69276-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

