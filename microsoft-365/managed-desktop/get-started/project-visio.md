---
title: Instalar Microsoft Project microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925534"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="7fda6-104">Instalar Microsoft Project microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos</span><span class="sxs-lookup"><span data-stu-id="7fda6-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="7fda6-105">Microsoft Project e o Microsoft Visio exigem etapas específicas para serem instaladas em Área de Trabalho Gerenciada da Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7fda6-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7fda6-106">Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7fda6-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7fda6-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7fda6-107">Prerequisites</span></span>

<span data-ttu-id="7fda6-108">Os administradores devem verificar se atendem a esses pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="7fda6-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="7fda6-109">**Quantidades de** licença - A quantidade correta de Microsoft Project e licenças do Microsoft Visio devem estar disponíveis para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7fda6-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="7fda6-110">Área de Trabalho Gerenciada da Microsoft atualmente suporta apenas versões de 64 bits desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7fda6-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="7fda6-111">**Nomes de licença** - Os nomes de licença apropriados para esses aplicativos são:</span><span class="sxs-lookup"><span data-stu-id="7fda6-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="7fda6-112">**Microsoft Project** - Project Online Professional ou Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="7fda6-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="7fda6-113">**Microsoft Visio** - Visio Plano Online 2</span><span class="sxs-lookup"><span data-stu-id="7fda6-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="7fda6-114">**Portal da Empresa** - o Portal da Empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7fda6-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="7fda6-115">Se o Portal da Empresa não for implantado em seu locatário, [consulte Portal da Empresa](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="7fda6-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="7fda6-116">Implantar Project e Visio para Área de Trabalho Gerenciada da Microsoft dispositivos</span><span class="sxs-lookup"><span data-stu-id="7fda6-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="7fda6-117">Área de Trabalho Gerenciada da Microsoft adicionará Microsoft Project microsoft Visio como dois aplicativos Win32 no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="7fda6-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="7fda6-118">Também criaremos dois grupos em Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "Disponível".</span><span class="sxs-lookup"><span data-stu-id="7fda6-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="7fda6-119">**Para implantar Project e Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="7fda6-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="7fda6-120">Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="7fda6-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="7fda6-121">Nome do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="7fda6-121">Azure AD Group name</span></span> | <span data-ttu-id="7fda6-122">Quais usuários atribuir?</span><span class="sxs-lookup"><span data-stu-id="7fda6-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="7fda6-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="7fda6-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="7fda6-124">Usuários que precisam de Project</span><span class="sxs-lookup"><span data-stu-id="7fda6-124">Users needing Project</span></span>
<span data-ttu-id="7fda6-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="7fda6-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="7fda6-126">Usuários que precisam de Visio</span><span class="sxs-lookup"><span data-stu-id="7fda6-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="7fda6-127">Comunicar alterações</span><span class="sxs-lookup"><span data-stu-id="7fda6-127">Communicate changes</span></span>
<span data-ttu-id="7fda6-128">É importante que os administradores de IT saibam aos usuários como instalar Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="7fda6-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="7fda6-129">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="7fda6-129">This includes:</span></span> 
- <span data-ttu-id="7fda6-130">Notificando os usuários quando esses aplicativos estão disponíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="7fda6-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="7fda6-131">Instruções sobre como instalar esses aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="7fda6-131">Instructions on how to install these applications from the Company Portal.</span></span>
