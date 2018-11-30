---
title: 'Etapa 3: Configurar mais segurança para o Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure mais segurança para o Office 365, incluindo o Office 365 ATP.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865205"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="b0fe8-103">Etapa 3: Configurar mais segurança para o Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fe8-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="b0fe8-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b0fe8-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b0fe8-105">Para garantir que sua assinatura do Office 365 e seus dados fiquem protegidos do início ao fim contra programas mal-intencionados, veja [Configurar seu locatário do Office 365 para aumentar a segurança](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) e configure os recursos adicionais de segurança a seguir:</span><span class="sxs-lookup"><span data-stu-id="b0fe8-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="b0fe8-106">Políticas de gerenciamento de ameaças no Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fe8-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="b0fe8-107">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b0fe8-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="b0fe8-108">Políticas de compartilhamento para todos os locatários no centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fe8-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="b0fe8-109">Configurações no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b0fe8-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="b0fe8-110">Após a configuração, você pode obter informações sobre seus status de segurança em:</span><span class="sxs-lookup"><span data-stu-id="b0fe8-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="b0fe8-111">Painéis e relatórios no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="b0fe8-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="b0fe8-112">Classificação de Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fe8-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="b0fe8-113">Para acessar essa página, você deve estar conectado como um administrador de locatários do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0fe8-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="b0fe8-114">Você também pode usar o Cloud App Security ou o Office 365 Cloud App Security para monitorar eventos de segurança e tomar medidas. Para saber mais, confira [Visão geral do Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="b0fe8-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="b0fe8-115">Um recurso de segurança adicional é a Proteção Avançada contra Ameaças do Office 365 (ou ATP), que ajuda sua organização a colaborar de forma mais segura ao:</span><span class="sxs-lookup"><span data-stu-id="b0fe8-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="b0fe8-116">Proteção de links e anexos em emails.</span><span class="sxs-lookup"><span data-stu-id="b0fe8-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="b0fe8-117">Fornecer recursos antiphishing e de inteligência de phishing para emails no Exchange Online e em arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0fe8-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="b0fe8-p101">O Office 365 ATP está incluído no Microsoft 365 Enterprise E5. Se você tiver o Microsoft 365 Enterprise E3, será possível comprar licenças individuais do ATP.</span><span class="sxs-lookup"><span data-stu-id="b0fe8-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="b0fe8-120">Para habilitar Office 365 ATP, confira [Ativar o recurso](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="b0fe8-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="b0fe8-121">Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span><span class="sxs-lookup"><span data-stu-id="b0fe8-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b0fe8-123">Guia de laboratório de teste: configurar segurança maior no Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fe8-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="b0fe8-124">Como ponto de verificação provisório, consulte os [critérios de saída](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondentes a esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b0fe8-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b0fe8-125">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b0fe8-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="b0fe8-126">Configurar gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="b0fe8-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


