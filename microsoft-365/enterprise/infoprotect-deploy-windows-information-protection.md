---
title: 'Etapa 4: configurar a Proteção de Informações do Windows'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e implantar a Proteção de Informações do Windows no Microsoft 365.
ms.openlocfilehash: e32b09c20e86ff927748f7aedd8b8d769e07916e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073552"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="45f3c-103">Etapa 4: configurar a Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="45f3c-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="45f3c-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="45f3c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="45f3c-105">Com mais dispositivos pessoais sendo usados para o trabalho, há um risco maior de aplicativos e dispositivos vazarem dados da organização privada.</span><span class="sxs-lookup"><span data-stu-id="45f3c-105">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="45f3c-106">Por exemplo, um funcionário inadvertidamente envia uma imagem de um plano de marketing para um produto futuro para um site de mídia social ou salva um arquivo contendo informações altamente confidenciais em seu armazenamento em nuvem pública.</span><span class="sxs-lookup"><span data-stu-id="45f3c-106">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="45f3c-107">A Proteção de Informações do Windows (WIP) ajuda a proteger contra esses tipos de vazamento de dados em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="45f3c-107">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="45f3c-108">Para obter mais informações, confira [Proteger seus dados corporativos usando o WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="45f3c-108">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="45f3c-109">No Microsoft 365 Enterprise, o WIP é uma combinação do Windows 10 Enterprise e do Microsoft Intune, incluído no Enterprise Mobility + Security (EMS) na sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="45f3c-109">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with Enterprise Mobility + Security (EMS) in your subscription.</span></span> 

<span data-ttu-id="45f3c-110">Para implantar o WIP na sua organização com o Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="45f3c-110">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="45f3c-111">Inscreva seus dispositivos do Windows no Intune.</span><span class="sxs-lookup"><span data-stu-id="45f3c-111">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="45f3c-112">Você deveria ter feito isso na [Fase 5: Gerenciamento de Dispositivos Móveis](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="45f3c-112">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="45f3c-113">Crie uma [política do Intune para WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="45f3c-113">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="45f3c-114">Certifique-se de que você tenha preenchido sua lista de aplicativos protegidos.</span><span class="sxs-lookup"><span data-stu-id="45f3c-114">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="45f3c-115">Escolha o seu nível de proteção WIP.</span><span class="sxs-lookup"><span data-stu-id="45f3c-115">Choose your WIP protection level.</span></span>

<span data-ttu-id="45f3c-116">Você também pode usar o WIP com o [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="45f3c-116">You can also use WIP with [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="45f3c-117">Veja [Práticas recomendadas de WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="45f3c-117">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="45f3c-118">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="45f3c-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="45f3c-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="45f3c-119">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="45f3c-120">Configurar a Prevenção de Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="45f3c-120">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


