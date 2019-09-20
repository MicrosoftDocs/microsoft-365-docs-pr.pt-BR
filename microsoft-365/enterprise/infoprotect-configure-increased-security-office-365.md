---
title: 'Etapa 3: Configurar a segurança aprimorada para o Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure a segurança aprimorada para o Microsoft 365.
ms.openlocfilehash: b51cb38a386292b79fdfe264c9d8a86973aa6325
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047274"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="dadde-103">Etapa 3: Configurar a segurança aprimorada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dadde-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="dadde-104">*Esta etapa é obrigatória e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="dadde-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="dadde-105">Para garantir que seus dados e sua assinatura do Microsoft 365 comecem e continuem protegidos contra ameaças mal-intencionadas, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dadde-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="dadde-106">Ajustar as políticas de gerenciamento de ameaças</span><span class="sxs-lookup"><span data-stu-id="dadde-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="dadde-107">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dadde-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="dadde-108">Políticas de compartilhamento para todos os locatários no Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="dadde-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="dadde-109">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="dadde-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="dadde-110">Após a configuração, você pode obter informações sobre seu status de segurança em:</span><span class="sxs-lookup"><span data-stu-id="dadde-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="dadde-111">Painéis e relatórios na Central de segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="dadde-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="dadde-112">Classificação de Segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="dadde-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="dadde-113">Um recurso de segurança adicional é a [Proteção Avançada contra Ameaças do Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), que ajuda sua organização a colaborar de forma mais segura ao:</span><span class="sxs-lookup"><span data-stu-id="dadde-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="dadde-114">Proteção de[links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) e [anexos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) em emails.</span><span class="sxs-lookup"><span data-stu-id="dadde-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="dadde-115">Fornecer recursos antiphishing e de inteligência contra falsificação para emails no Exchange Online e em [arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="dadde-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="dadde-116">O ATP do Office 365 só está disponível com o Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="dadde-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="dadde-118">Guia de laboratório de teste: configurar segurança aprimorada no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dadde-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="dadde-119">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="dadde-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="dadde-120">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="dadde-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="dadde-121">Configurar Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="dadde-121">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


