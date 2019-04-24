---
title: Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Microsoft 365 para o ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 54e05122dcbe5d4e24f092536897f2a8ad449e05
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283651"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aba21-103">Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aba21-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aba21-104">Com as instruções deste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança no ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aba21-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="aba21-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aba21-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="aba21-107">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aba21-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="aba21-108">Se você só quiser configurar a segurança mais 365 da Microsoft de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="aba21-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="aba21-109">Se você quiser configurar a segurança do Microsoft 365 aumentada em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="aba21-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="aba21-110">Testando o Microsoft 365 Security não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="aba21-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="aba21-111">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="aba21-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="aba21-112">Fase 2: configurar a segurança do Microsoft 365 mais elevado</span><span class="sxs-lookup"><span data-stu-id="aba21-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="aba21-113">Nesta fase, você habilitará a segurança mais 365 da Microsoft para seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="aba21-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="aba21-114">Para obter mais detalhes e configurações, consulte [Configure Your Office 365 locatário for maior segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="aba21-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="aba21-115">Configurar o SharePoint Online para bloquear aplicativos que não dão suporte à autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="aba21-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="aba21-116">Os aplicativos que não dão suporte à autenticação moderna não podem ter [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais.</span><span class="sxs-lookup"><span data-stu-id="aba21-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="aba21-117">Vá para o portal do Office[https://office.com](https://office.com)() e entre na sua assinatura de avaliação do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="aba21-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="aba21-118">Se você estiver usando o ambiente leve de teste do Microsoft 365, entre no computador local.</span><span class="sxs-lookup"><span data-stu-id="aba21-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="aba21-119">Se você estiver usando o ambiente de teste corporativo da Microsoft 365 simulado, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e, em seguida, entre no CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="aba21-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="aba21-120">Na guia **centro de administração do Microsoft 365** , clique em **administrador**.</span><span class="sxs-lookup"><span data-stu-id="aba21-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="aba21-121">Na nova guia **centro de administração do Microsoft 365** , clique em **centros de administração > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="aba21-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="aba21-122">Na nova guia **centro de administração do SharePoint** , clique em **controle de acesso**.</span><span class="sxs-lookup"><span data-stu-id="aba21-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="aba21-123">Em **aplicativos que não dão suporte à autenticação moderna**, clique em **Bloquear**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="aba21-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="aba21-124">Habilitar a proteção avançada contra ameaças para o SharePoint, o OneDrive for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aba21-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="aba21-125">A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="aba21-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="aba21-126">Vá para o [centro de conformidade do Office 365 Security &](https://protection.office.com) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="aba21-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="aba21-127">No painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política > anexos seguros**.</span><span class="sxs-lookup"><span data-stu-id="aba21-127">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="aba21-128">Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="aba21-128">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="aba21-129">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aba21-129">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="aba21-130">Habilitar Antimalware</span><span class="sxs-lookup"><span data-stu-id="aba21-130">Enable anti-malware</span></span>

<span data-ttu-id="aba21-131">Malware é composto por vírus e spywares.</span><span class="sxs-lookup"><span data-stu-id="aba21-131">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="aba21-132">Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar.</span><span class="sxs-lookup"><span data-stu-id="aba21-132">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="aba21-133">Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor.</span><span class="sxs-lookup"><span data-stu-id="aba21-133">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="aba21-134">O Office 365 tem recursos internos de filtragem de malware e spam que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e a proteger contra spam.</span><span class="sxs-lookup"><span data-stu-id="aba21-134">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="aba21-135">Para obter mais informações, consulte [anti-spam & Anti-Malware Protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="aba21-135">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="aba21-136">Para garantir que o processamento Antimalware seja executado em arquivos com tipos de arquivo de anexo comuns:</span><span class="sxs-lookup"><span data-stu-id="aba21-136">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="aba21-137">Clique no botão voltar do navegador para voltar à página **política** .</span><span class="sxs-lookup"><span data-stu-id="aba21-137">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="aba21-138">Clique em **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="aba21-138">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="aba21-139">Clique duas vezes na política denominada **padrão**.</span><span class="sxs-lookup"><span data-stu-id="aba21-139">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="aba21-140">Na janela **política de antimalware** , clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="aba21-140">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="aba21-141">Em **filtro tipos de anexo comuns**, clique **em > salvar**.</span><span class="sxs-lookup"><span data-stu-id="aba21-141">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="aba21-142">Fase 3: examinar os logs e as ferramentas de segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="aba21-142">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="aba21-143">Nesta fase, você examina os serviços internos que informam sobre eventos de segurança e medem a postura geral de segurança.</span><span class="sxs-lookup"><span data-stu-id="aba21-143">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="aba21-144">Painel de gerenciamento de ameaças</span><span class="sxs-lookup"><span data-stu-id="aba21-144">Threat management dashboard</span></span>

<span data-ttu-id="aba21-145">O gerenciamento de ameaças do Office 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra a perda de dados e ajudar a proteger mensagens de entrada e saída de software mal-intencionado e spam.</span><span class="sxs-lookup"><span data-stu-id="aba21-145">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="aba21-146">Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se ou não os remetentes estão falsificando contas de seu domínio de forma mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="aba21-146">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="aba21-147">Para obter mais informações, consulte [Threat Management na central de segurança do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="aba21-147">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>


### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="aba21-148">Painel do Office 365 Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="aba21-148">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="aba21-149">O Office 365 Cloud app Security, anteriormente conhecido como gerenciamento de segurança avançada do Office 365, permite que você crie políticas que monitoram e informam sobre atividades suspeitas em sua assinatura do Office 365, para que você possa investigar e obter possíveis ação de correção.</span><span class="sxs-lookup"><span data-stu-id="aba21-149">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action.</span></span> <span data-ttu-id="aba21-150">Para obter mais informações, consulte [Overview of Office 365 Cloud app Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="aba21-150">For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

<!--
### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="aba21-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="aba21-151">Next steps</span></span>

<span data-ttu-id="aba21-152">Consulte a etapa [Configurar maior segurança para o Microsoft 365](infoprotect-configure-increased-security-office-365.md) na fase de **proteção de informações** para obter informações e links para configurar essas definições em produção.</span><span class="sxs-lookup"><span data-stu-id="aba21-152">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="aba21-153">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="aba21-153">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="aba21-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="aba21-154">See also</span></span>

[<span data-ttu-id="aba21-155">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aba21-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="aba21-156">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aba21-156">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="aba21-157">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="aba21-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

