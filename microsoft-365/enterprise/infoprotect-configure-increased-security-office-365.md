---
title: 'Etapa 3: Configurar a segurança aprimorada para o Microsoft 365'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: eabf0d60f3cfb61b7fffcc688a080ba99f83293e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067238"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="65c62-103">Etapa 3: Configurar a segurança aprimorada para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65c62-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="65c62-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="65c62-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: proteção de informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="65c62-106">Para garantir que seus dados e sua assinatura do Microsoft 365 comecem e continuem protegidos contra ameaças mal-intencionadas, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="65c62-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="65c62-107">Ajustar as políticas de gerenciamento de ameaças</span><span class="sxs-lookup"><span data-stu-id="65c62-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="65c62-108">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="65c62-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="65c62-109">Políticas de compartilhamento para todos os locatários no Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="65c62-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="65c62-110">Configurações do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="65c62-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="65c62-111">Após a configuração, você pode obter informações sobre seu status de segurança em:</span><span class="sxs-lookup"><span data-stu-id="65c62-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="65c62-112">Painéis e relatórios na Central de segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="65c62-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="65c62-113">Classificação de Segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="65c62-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="65c62-114">Um recurso de segurança adicional é a [Proteção Avançada contra Ameaças do Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), que ajuda sua organização a colaborar de forma mais segura ao:</span><span class="sxs-lookup"><span data-stu-id="65c62-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="65c62-115">Proteção de[links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) e [anexos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) em emails.</span><span class="sxs-lookup"><span data-stu-id="65c62-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="65c62-116">Fornecer recursos antiphishing e de inteligência contra falsificação para emails no Exchange Online e em [arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="65c62-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="65c62-117">O Office 365 ATP está disponível apenas com o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="65c62-117">Office 365 ATP is only available with Microsoft 365 E5.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="65c62-119">Guia de laboratório de teste: configurar segurança aprimorada no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65c62-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="65c62-120">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="65c62-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="65c62-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="65c62-121">Next step</span></span>


|||
|:-------|:-----|
|![Etapa 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="65c62-123">Configurar Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="65c62-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


