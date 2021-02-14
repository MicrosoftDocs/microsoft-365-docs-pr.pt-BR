---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950527"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="98a92-104">Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="98a92-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="98a92-105">O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98a92-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="98a92-106">Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="98a92-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98a92-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="98a92-107">Prerequisites</span></span>

<span data-ttu-id="98a92-108">Os administradores devem verificar se atendem a esses pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="98a92-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="98a92-109">**Quantidades de** licenças - a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="98a92-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="98a92-110">A Área de Trabalho Gerenciada da Microsoft atualmente só dá suporte a versões de 64 bits desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="98a92-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="98a92-111">**Nomes de licença** - Os nomes de licença apropriados para esses aplicativos são:</span><span class="sxs-lookup"><span data-stu-id="98a92-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="98a92-112">**Microsoft Project** - Project Online Professional ou Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="98a92-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="98a92-113">**Microsoft Visio** - Plano 2 do Visio Online</span><span class="sxs-lookup"><span data-stu-id="98a92-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="98a92-114">**Portal da** Empresa - O Portal da Empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="98a92-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="98a92-115">Se o Portal da Empresa não estiver implantado em seu locatário, consulte [o Portal da Empresa.](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="98a92-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="98a92-116">Implantar o Project e o Visio para dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="98a92-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="98a92-117">A Área de Trabalho Gerenciada da Microsoft adicionará o Microsoft Project e o Microsoft Visio como dois Aplicativos Win32 no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="98a92-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="98a92-118">Também criaremos dois grupos no Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "Disponível".</span><span class="sxs-lookup"><span data-stu-id="98a92-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="98a92-119">**Para implantar o Project e o Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98a92-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="98a92-120">Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98a92-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="98a92-121">Nome do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="98a92-121">Azure AD Group name</span></span> | <span data-ttu-id="98a92-122">Quais usuários atribuir?</span><span class="sxs-lookup"><span data-stu-id="98a92-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="98a92-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="98a92-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="98a92-124">Usuários que precisam do Project</span><span class="sxs-lookup"><span data-stu-id="98a92-124">Users needing Project</span></span>
<span data-ttu-id="98a92-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="98a92-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="98a92-126">Usuários que precisam do Visio</span><span class="sxs-lookup"><span data-stu-id="98a92-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="98a92-127">Comunicar alterações</span><span class="sxs-lookup"><span data-stu-id="98a92-127">Communicate changes</span></span>
<span data-ttu-id="98a92-128">É importante que os administradores de IT saibam aos usuários como instalar o Project e o Visio.</span><span class="sxs-lookup"><span data-stu-id="98a92-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="98a92-129">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="98a92-129">This includes:</span></span> 
- <span data-ttu-id="98a92-130">Notificar os usuários quando esses aplicativos estão disponíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="98a92-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="98a92-131">Instruções sobre como instalar esses aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98a92-131">Instructions on how to install these applications from the Company Portal.</span></span>
