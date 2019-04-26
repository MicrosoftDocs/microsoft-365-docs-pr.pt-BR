---
title: 'Etapa 6: configurar o gerenciamento de acesso privilegiado para o Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado do Office 365.
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304151"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="822e3-103">Etapa 6: configurar o gerenciamento de acesso privilegiado para o Office 365</span><span class="sxs-lookup"><span data-stu-id="822e3-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="822e3-104">*Esta etapa é opcional e se aplica apenas às versões E5 e Advanced Compliance do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="822e3-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="822e3-p101">O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time a atividades baseadas em tarefas em seu locatário do Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="822e3-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="822e3-p102">Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário do Office 365 e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso baseado em tarefas nos dados e definições de configuração do Office 365 em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização do Office 365:</span><span class="sxs-lookup"><span data-stu-id="822e3-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="822e3-110">Criar um grupo de aprovadores</span><span class="sxs-lookup"><span data-stu-id="822e3-110">Creating an approver's group</span></span>
- <span data-ttu-id="822e3-111">Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="822e3-111">Enabling privileged access</span></span>
- <span data-ttu-id="822e3-112">Criar políticas de aprovação</span><span class="sxs-lookup"><span data-stu-id="822e3-112">Creating approval policies</span></span>

<span data-ttu-id="822e3-p103">Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.</span><span class="sxs-lookup"><span data-stu-id="822e3-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="822e3-116">Para habilitar o gerenciamento do acesso privilegiado no Office 365, confira o tópico [Configurar o gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="822e3-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="822e3-117">Para saber mais, confira o tópico [Gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="822e3-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="822e3-118">Resultados</span><span class="sxs-lookup"><span data-stu-id="822e3-118">Results</span></span>

<span data-ttu-id="822e3-119">O resultado esta etapa é que você aumentou a segurança do Office 365, habilitando o controle de acesso just-in-time para dados-chave e as definições de configuração para sua organização.</span><span class="sxs-lookup"><span data-stu-id="822e3-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="822e3-120">Como um ponto de verificação provisório, confira os [Critérios de saída](infoprotect-exit-criteria.md#crit-infoprotect-step6) correspondentes desta etapa.</span><span class="sxs-lookup"><span data-stu-id="822e3-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="822e3-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="822e3-121">Next Step</span></span>

[<span data-ttu-id="822e3-122">Critérios de saída da infraestrutura de proteção de informações</span><span class="sxs-lookup"><span data-stu-id="822e3-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)