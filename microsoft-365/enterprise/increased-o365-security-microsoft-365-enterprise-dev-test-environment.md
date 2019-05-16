---
title: Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Microsoft 365 para o ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: d51f9ada68969823eadbb4fad55392358a6ddee8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072131"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1e582-103">Maior segurança do Microsoft 365 para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e582-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1e582-104">Com as instruções deste artigo, você define configurações adicionais do Microsoft 365 para aumentar a segurança no ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1e582-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1e582-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1e582-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1e582-107">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e582-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1e582-108">Se você só quiser configurar a segurança mais 365 da Microsoft de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1e582-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1e582-109">Se você quiser configurar a segurança do Microsoft 365 aumentada em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1e582-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e582-110">Testando o Microsoft 365 Security não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1e582-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1e582-111">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="1e582-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="1e582-112">Fase 2: configurar a segurança do Microsoft 365 mais elevado</span><span class="sxs-lookup"><span data-stu-id="1e582-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="1e582-113">Nesta fase, você habilitará a segurança mais 365 da Microsoft para seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1e582-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="1e582-114">Para obter mais detalhes e configurações, consulte [Configure Your Office 365 locatário for maior segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="1e582-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="1e582-115">Configurar o SharePoint Online para bloquear aplicativos que não dão suporte à autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="1e582-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="1e582-116">Os aplicativos que não dão suporte à autenticação moderna não podem ter [configurações de acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais.</span><span class="sxs-lookup"><span data-stu-id="1e582-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="1e582-117">Vá para o centro de administração do Microsoft[https://portal.microsoft.com](https://portal.microsoft.com)365 () e entre na sua assinatura de laboratório de teste do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1e582-117">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="1e582-118">Se você estiver usando o ambiente leve de teste do Microsoft 365, entre no computador local.</span><span class="sxs-lookup"><span data-stu-id="1e582-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="1e582-119">Se você estiver usando o ambiente de teste corporativo da Microsoft 365 simulado, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual CLIENT1 e, em seguida, entre no CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="1e582-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="1e582-120">Na nova guia **centro de administração do Microsoft 365** , clique em **centros de administração > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1e582-120">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="1e582-121">Na nova guia **centro de administração do SharePoint** , clique em **controle de acesso**.</span><span class="sxs-lookup"><span data-stu-id="1e582-121">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="1e582-122">Em **aplicativos que não dão suporte à autenticação moderna**, clique em **Bloquear**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e582-122">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="1e582-123">Habilitar a proteção avançada contra ameaças para o SharePoint, o OneDrive for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e582-123">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="1e582-124">A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="1e582-124">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="1e582-125">Vá para o [centro de conformidade do Office 365 Security &](https://protection.office.com) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1e582-125">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1e582-126">No painel de navegação esquerdo, em **Gerenciamento de ameaças**, escolha **política > anexos seguros**.</span><span class="sxs-lookup"><span data-stu-id="1e582-126">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="1e582-127">Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="1e582-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="1e582-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e582-128">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="1e582-129">Habilitar Antimalware</span><span class="sxs-lookup"><span data-stu-id="1e582-129">Enable anti-malware</span></span>

<span data-ttu-id="1e582-130">Malware é composto por vírus e spywares.</span><span class="sxs-lookup"><span data-stu-id="1e582-130">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="1e582-131">Os vírus infectam outros programas e dados e se espalham em todo o computador em busca de programas para infectar.</span><span class="sxs-lookup"><span data-stu-id="1e582-131">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="1e582-132">Spyware é um tipo de malware que coleta suas informações pessoais, como informações de logon e dados pessoais, e as envia de volta ao seu autor.</span><span class="sxs-lookup"><span data-stu-id="1e582-132">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="1e582-133">O Office 365 tem recursos internos de filtragem de malware e spam que ajudam a proteger mensagens de entrada e saída de software mal-intencionado e a proteger contra spam.</span><span class="sxs-lookup"><span data-stu-id="1e582-133">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="1e582-134">Para obter mais informações, consulte [anti-spam & Anti-Malware Protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="1e582-134">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="1e582-135">Para garantir que o processamento Antimalware seja executado em arquivos com tipos de arquivo de anexo comuns:</span><span class="sxs-lookup"><span data-stu-id="1e582-135">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="1e582-136">Clique no botão voltar do navegador para voltar à página **política** .</span><span class="sxs-lookup"><span data-stu-id="1e582-136">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="1e582-137">Clique em **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="1e582-137">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="1e582-138">Clique duas vezes na política denominada **padrão**.</span><span class="sxs-lookup"><span data-stu-id="1e582-138">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="1e582-139">Na janela **política de antimalware** , clique em **configurações**.</span><span class="sxs-lookup"><span data-stu-id="1e582-139">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="1e582-140">Em **filtro tipos de anexo comuns**, clique **em > salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e582-140">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="1e582-141">Fase 3: examinar o painel de gerenciamento de ameaças</span><span class="sxs-lookup"><span data-stu-id="1e582-141">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="1e582-142">O gerenciamento de ameaças do Office 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivos móveis aos dados da sua organização, ajudar a proteger sua organização contra a perda de dados e ajudar a proteger mensagens de entrada e saída de software mal-intencionado e spam.</span><span class="sxs-lookup"><span data-stu-id="1e582-142">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="1e582-143">Você também usa o gerenciamento de ameaças para proteger a reputação do seu domínio e para determinar se ou não os remetentes estão falsificando contas de seu domínio de forma mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="1e582-143">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="1e582-144">Para obter mais informações, consulte [Threat Management na central de segurança do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="1e582-144">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="1e582-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1e582-145">Next steps</span></span>

<span data-ttu-id="1e582-146">Consulte a etapa [Configurar maior segurança para o Microsoft 365](infoprotect-configure-increased-security-office-365.md) na fase de **proteção de informações** para obter informações e links para configurar essas definições em produção.</span><span class="sxs-lookup"><span data-stu-id="1e582-146">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="1e582-147">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="1e582-147">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e582-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e582-148">See also</span></span>

[<span data-ttu-id="1e582-149">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e582-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1e582-150">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e582-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1e582-151">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e582-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

