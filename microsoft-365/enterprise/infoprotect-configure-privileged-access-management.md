---
title: 'Etapa 7: configurar o gerenciamento de acesso privilegiado'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636983"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="abd8b-103">Etapa 7: configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="abd8b-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="abd8b-104">*Esta etapa é opcional e se aplica apenas às versões E5 e Advanced Compliance do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="abd8b-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Proteção de Informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="abd8b-106">O gerenciamento de acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time para atividades com base em tarefas em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="abd8b-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="abd8b-107">Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso à dados confidenciais ou acesso a definições de configuração crítica.</span><span class="sxs-lookup"><span data-stu-id="abd8b-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="abd8b-108">Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer aprovação explícita para acessar e alterar as configurações de caixa de correio de organização em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="abd8b-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="abd8b-109">Nesta etapa, você habilitará o gerenciamento de acesso privilegiado no locatário e configurará políticas de acesso privilegiado que forneçam segurança adicional para acesso baseado em tarefa a dados e definições de configuração para sua organização.</span><span class="sxs-lookup"><span data-stu-id="abd8b-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="abd8b-110">Há três etapas básicas para começar a usar o acesso privilegiado em sua organização:</span><span class="sxs-lookup"><span data-stu-id="abd8b-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="abd8b-111">Criar um grupo de aprovadores</span><span class="sxs-lookup"><span data-stu-id="abd8b-111">Creating an approver's group</span></span>
- <span data-ttu-id="abd8b-112">Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="abd8b-112">Enabling privileged access</span></span>
- <span data-ttu-id="abd8b-113">Criar políticas de aprovação</span><span class="sxs-lookup"><span data-stu-id="abd8b-113">Creating approval policies</span></span>

<span data-ttu-id="abd8b-p103">Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.</span><span class="sxs-lookup"><span data-stu-id="abd8b-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="abd8b-117">Para habilitar o gerenciamento de acesso privilegiado, consulte o tópico [Configurar gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .</span><span class="sxs-lookup"><span data-stu-id="abd8b-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="abd8b-118">Para obter mais informações, consulte o tópico [Gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .</span><span class="sxs-lookup"><span data-stu-id="abd8b-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="abd8b-120">Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="abd8b-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="abd8b-121">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step7) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="abd8b-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="abd8b-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="abd8b-122">Next Step</span></span>

[<span data-ttu-id="abd8b-123">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="abd8b-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
