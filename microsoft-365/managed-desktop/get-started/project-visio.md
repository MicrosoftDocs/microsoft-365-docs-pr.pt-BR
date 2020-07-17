---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126822"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="f6b0c-104">Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f6b0c-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="f6b0c-105">O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f6b0c-106">Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6b0c-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6b0c-107">Prerequisites</span></span>

<span data-ttu-id="f6b0c-108">Os administradores devem verificar se eles atendem a estes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="f6b0c-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="f6b0c-109">**Quantidade de licenças** -a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="f6b0c-110">Atualmente, a área de trabalho gerenciada da Microsoft dá suporte apenas a versões de 64 bits desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="f6b0c-111">**Nomes de licença** : os nomes de licença apropriados para esses aplicativos são:</span><span class="sxs-lookup"><span data-stu-id="f6b0c-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="f6b0c-112">**Microsoft Project** -Project online Professional ou Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="f6b0c-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="f6b0c-113">**Microsoft Visio** -Visio online plano 2</span><span class="sxs-lookup"><span data-stu-id="f6b0c-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="f6b0c-114">**Portal da empresa** -o portal da empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="f6b0c-115">Se o portal da empresa não estiver implantado em seu locatário, confira [portal da empresa](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="f6b0c-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="f6b0c-116">Implantar o Project e o Visio para dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f6b0c-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="f6b0c-117">A área de trabalho gerenciada da Microsoft adicionará o Microsoft Project e o Microsoft Visio como dois aplicativos Win32 no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="f6b0c-118">Também criaremos dois grupos no Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "disponível".</span><span class="sxs-lookup"><span data-stu-id="f6b0c-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="f6b0c-119">**Para implantar o Project e o Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="f6b0c-120">Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="f6b0c-121">Nome do grupo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f6b0c-121">Azure AD Group name</span></span> | <span data-ttu-id="f6b0c-122">Quais usuários serão atribuídos?</span><span class="sxs-lookup"><span data-stu-id="f6b0c-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="f6b0c-123">Área de trabalho moderna-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="f6b0c-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="f6b0c-124">Usuários que precisam de projeto</span><span class="sxs-lookup"><span data-stu-id="f6b0c-124">Users needing Project</span></span>
<span data-ttu-id="f6b0c-125">Área de trabalho moderna-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="f6b0c-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="f6b0c-126">Usuários que precisam do Visio</span><span class="sxs-lookup"><span data-stu-id="f6b0c-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="f6b0c-127">Comunicar alterações</span><span class="sxs-lookup"><span data-stu-id="f6b0c-127">Communicate changes</span></span>
<span data-ttu-id="f6b0c-128">É importante para os administradores de ti permitir que seus usuários saibam como instalar o Project e o Visio.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="f6b0c-129">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="f6b0c-129">This includes:</span></span> 
- <span data-ttu-id="f6b0c-130">Notificar os usuários quando esses aplicativos estiverem disponíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="f6b0c-131">Instruções sobre como instalar esses aplicativos do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="f6b0c-131">Instructions on how to install these applications from the Company Portal.</span></span>
