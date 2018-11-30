---
title: Critérios de saída da infraestrutura de proteção de informações
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865207"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="9b547-103">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="9b547-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="9b547-104">Antes de concluir a infraestrutura de base, verifique se a infraestrutura de proteção de informações atende a estes requisitos.</span><span class="sxs-lookup"><span data-stu-id="9b547-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="9b547-105">Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização</span><span class="sxs-lookup"><span data-stu-id="9b547-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="9b547-p101">Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="9b547-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="9b547-108">No mínimo, você está usando três níveis de segurança:</span><span class="sxs-lookup"><span data-stu-id="9b547-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="9b547-109">Linha de base</span><span class="sxs-lookup"><span data-stu-id="9b547-109">Baseline</span></span>
- <span data-ttu-id="9b547-110">Confidencial</span><span class="sxs-lookup"><span data-stu-id="9b547-110">Sensitive</span></span>
- <span data-ttu-id="9b547-111">Altamente controlada</span><span class="sxs-lookup"><span data-stu-id="9b547-111">Highly regulated</span></span>

<span data-ttu-id="9b547-112">Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="9b547-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="9b547-113">Obrigatório: a segurança elevada está configurada no Office 365</span><span class="sxs-lookup"><span data-stu-id="9b547-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="9b547-114">Você definiu as seguintes configurações para obter uma segurança elevada, com base nas informações sobre como [configurar seu locatário do Office 365 para aumentar a segurança](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span><span class="sxs-lookup"><span data-stu-id="9b547-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="9b547-115">Políticas de gerenciamento de ameaças no Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="9b547-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="9b547-116">Configurações adicionais para todos os locatários do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9b547-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="9b547-117">Políticas de compartilhamento de todos os locatários no SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="9b547-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="9b547-118">Configurações no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9b547-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="9b547-119">Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="9b547-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="9b547-120">Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="9b547-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="9b547-121">Opcional: a classificação está configurada em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="9b547-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="9b547-122">Você e o departamento jurídico e de conformidade trabalharam em conjunto para desenvolver uma classificação apropriada e um esquema de identificação de dados em sua organização, que incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b547-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="9b547-123">tipos de dados confidenciais;</span><span class="sxs-lookup"><span data-stu-id="9b547-123">Sensitive data types</span></span>
- <span data-ttu-id="9b547-124">Rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="9b547-124">Office 365 labels</span></span>
- <span data-ttu-id="9b547-125">Rótulos da Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9b547-125">Azure Information Protection labels</span></span>

<span data-ttu-id="9b547-126">Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="9b547-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="9b547-127">Opcional: configurar o gerenciamento de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="9b547-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="9b547-p102">Você usou as informações ano tópico [Configurar o gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar o acesso privilegiado e criar uma ou mais políticas de acesso privilegiado na sua organização do Office 365. Você configurou essas políticas e o acesso Just-In-Time está habilitado para acesso a dados confidenciais ou acesso a definições de configuração crítica.</span><span class="sxs-lookup"><span data-stu-id="9b547-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="9b547-130">Se necessário, a [Etapa 4](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="9b547-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="9b547-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9b547-131">Next Step</span></span>

<span data-ttu-id="9b547-132">Agora já está tudo pronto para a implantação das [cargas de trabalho e cenários](deploy-workloads.md), como o Microsoft Teams e o Exchange Online, que são executadas acima da infraestrutura de base do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9b547-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
