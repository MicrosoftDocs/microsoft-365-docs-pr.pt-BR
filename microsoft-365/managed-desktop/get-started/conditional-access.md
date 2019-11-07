---
title: Ajustar o acesso condicional
description: Como excluir determinadas contas da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1b91186837ad558965d675f82d013a7081c7c7ec
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012437"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="eabdd-104">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="eabdd-104">Adjust conditional access</span></span>

<span data-ttu-id="eabdd-105">Se você usar políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) em sua organização, será necessário defini-las para excluir determinadas contas, de modo que a área de trabalho gerenciada da Microsoft possa funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="eabdd-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="eabdd-106">Para fazer isso, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="eabdd-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="eabdd-107">Consulte a seção "etapas de reversão" de [como: planejar sua implantação de acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="eabdd-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="eabdd-108">Siga as etapas para excluir o grupo de *contas de serviço de área de trabalho moderna* para todas as políticas.</span><span class="sxs-lookup"><span data-stu-id="eabdd-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="eabdd-109">Se você tiver alguma dificuldade com acesso condicional, entre em contato com o [suporte](../working-with-managed-desktop/admin-support.md)de administração.</span><span class="sxs-lookup"><span data-stu-id="eabdd-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="eabdd-110">Etapas para começar a usar a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="eabdd-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="eabdd-111">Adicionar e verificar contatos de administrador no portal de administração</span><span class="sxs-lookup"><span data-stu-id="eabdd-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="eabdd-112">Ajustar o acesso condicional (este tópico)</span><span class="sxs-lookup"><span data-stu-id="eabdd-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="eabdd-113">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="eabdd-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="eabdd-114">Implantar o portal da empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="eabdd-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="eabdd-115">Habilitar roaming de estado corporativo</span><span class="sxs-lookup"><span data-stu-id="eabdd-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="eabdd-116">Configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="eabdd-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="eabdd-117">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="eabdd-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="eabdd-118">Implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="eabdd-118">Deploy apps</span></span>](deploy-apps.md)