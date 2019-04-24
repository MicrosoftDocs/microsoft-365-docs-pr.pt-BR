---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288992"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="6b47b-104">Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6b47b-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="6b47b-105">O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b47b-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="6b47b-106">Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b47b-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b47b-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6b47b-107">Prerequisites</span></span>

<span data-ttu-id="6b47b-108">Os administradores devem verificar se eles atendem a estes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="6b47b-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="6b47b-109">**Quantidade de licenças** -a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6b47b-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="6b47b-110">Atualmente, a área de trabalho gerenciada da Microsoft dá suporte apenas a versões de 64 bits desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b47b-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="6b47b-111">**Nomes de licença** : os nomes de licença apropriados para esses aplicativos são:</span><span class="sxs-lookup"><span data-stu-id="6b47b-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="6b47b-112">**Microsoft Project** -Project online Professional ou Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="6b47b-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="6b47b-113">**Microsoft Visio** -Visio online plano 2</span><span class="sxs-lookup"><span data-stu-id="6b47b-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="6b47b-114">**Portal da empresa** -o portal da empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b47b-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="6b47b-115">Se o portal da empresa não estiver implantado em seu locatário, confira [portal da empresa](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="6b47b-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="6b47b-116">Implantar o Project e o Visio para dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6b47b-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="6b47b-117">Depois de enviar sua solicitação de suporte, a área de trabalho gerenciada da Microsoft criará três grupos do Azure AD e três implantações de aplicativos por meio do Microsoft Intune para implantar os aplicativos em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="6b47b-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="6b47b-118">**Para implantar o Project e o Visio**</span><span class="sxs-lookup"><span data-stu-id="6b47b-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="6b47b-119">**Arquivo uma solicitação de suporte** Os administradores de ti precisam arquivar uma solicitação de suporte para disponibilizar esses aplicativos aos usuários.</span><span class="sxs-lookup"><span data-stu-id="6b47b-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="6b47b-120">Para obter informações sobre como entrar em contato com a área de trabalho gerenciada da Microsoft, consulte [admin support for Microsoft Managed desktop](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="6b47b-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="6b47b-121">**Atribuir usuários a novos grupos do Azure ad** A área de trabalho gerenciada da Microsoft criará 3 grupos do Azure AD no locatário e 3 implantações de aplicativo correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6b47b-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="6b47b-122">Os administradores de ti precisam atribuir os usuários aos grupos apropriados.</span><span class="sxs-lookup"><span data-stu-id="6b47b-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="6b47b-123">Atribuir usuários a apenas um desses grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6b47b-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="6b47b-124">Nome do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="6b47b-124">Azure AD Group name</span></span> | <span data-ttu-id="6b47b-125">Quais usuários serão atribuídos?</span><span class="sxs-lookup"><span data-stu-id="6b47b-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="6b47b-126">Microsoft-Office-Project-install</span><span class="sxs-lookup"><span data-stu-id="6b47b-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="6b47b-127">Usuários que precisam apenas de projeto</span><span class="sxs-lookup"><span data-stu-id="6b47b-127">Users needing only Project</span></span>
<span data-ttu-id="6b47b-128">Microsoft-Office-Visio-install</span><span class="sxs-lookup"><span data-stu-id="6b47b-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="6b47b-129">Usuários que precisam apenas do Visio</span><span class="sxs-lookup"><span data-stu-id="6b47b-129">Users needing only Visio</span></span>
<span data-ttu-id="6b47b-130">Microsoft-Office-Project e Visio – instalação</span><span class="sxs-lookup"><span data-stu-id="6b47b-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="6b47b-131">Usuários que precisam do Project e do Visio</span><span class="sxs-lookup"><span data-stu-id="6b47b-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="6b47b-132">Uma vez atribuídos a esses grupos, os aplicativos estarão disponíveis no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6b47b-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="6b47b-133">Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6b47b-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="6b47b-134">Comunicar alterações</span><span class="sxs-lookup"><span data-stu-id="6b47b-134">Communicate changes</span></span>
<span data-ttu-id="6b47b-135">É importante para os administradores de ti permitir que seus usuários saibam como instalar o Project e o Visio.</span><span class="sxs-lookup"><span data-stu-id="6b47b-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="6b47b-136">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="6b47b-136">This includes:</span></span> 
- <span data-ttu-id="6b47b-137">Notificar os usuários quando esses aplicativos estiverem disponíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="6b47b-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="6b47b-138">Instruções sobre como instalar esses aplicativos do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6b47b-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="6b47b-139">Os usuários devem fechar todos os aplicativos do Office antes de instalar o Microsoft Project ou o Microsoft Visio no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6b47b-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
