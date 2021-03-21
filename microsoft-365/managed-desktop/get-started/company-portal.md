---
title: Instalar o Portal da Empresa do Intune em dispositivos
description: Informações sobre a instalação do aplicativo portal da empresa em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Portal da Empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925769"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="f103c-104">Instalar o Portal da Empresa do Intune em dispositivos</span><span class="sxs-lookup"><span data-stu-id="f103c-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="f103c-105">A Área de Trabalho Gerenciada da Microsoft exige que os administradores de IT instalem o Portal da Empresa do Intune para seus usuários com dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f103c-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f103c-106">Aqui estão alguns benefícios para sua organização:</span><span class="sxs-lookup"><span data-stu-id="f103c-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="f103c-107">Os usuários têm um local para navegar e instalar aplicativos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f103c-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="f103c-108">Os administradores de IT podem organizar aplicativos por categorias para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f103c-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="f103c-109">Alguns aplicativos (como o Microsoft Project e o Microsoft Visio) exigem que o Portal da Empresa implante com a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f103c-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="f103c-110">Os administradores de IT podem personalizar o Portal da Empresa para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f103c-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="f103c-111">Isso inclui imagens de marca, adição de contatos de suporte local e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f103c-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="f103c-112">Para obter mais informações, [consulte How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span><span class="sxs-lookup"><span data-stu-id="f103c-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="f103c-113">Este tópico documenta o processo de implantação do Portal da Empresa do Intune para seus usuários da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f103c-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f103c-114">O processo geral tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f103c-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="f103c-115">Comprar o Portal da Empresa na Microsoft Store para Empresas e sincronizar com o Intune</span><span class="sxs-lookup"><span data-stu-id="f103c-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="f103c-116">Atribuir Portal da Empresa aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="f103c-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="f103c-117">Comunicar a alteração aos usuários</span><span class="sxs-lookup"><span data-stu-id="f103c-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="f103c-118">Etapa 1 - Comprar Portal da Empresa da Microsoft Store para Empresas e sincronizar com o Intune</span><span class="sxs-lookup"><span data-stu-id="f103c-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="f103c-119">Para obter informações sobre como comprar os aplicativos e sincronizar com o Intune, consulte [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices*.</span><span class="sxs-lookup"><span data-stu-id="f103c-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="f103c-120">Este tópico fornece informações sobre como:</span><span class="sxs-lookup"><span data-stu-id="f103c-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="f103c-121">Comprar o Portal da Empresa da Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="f103c-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="f103c-122">Forçar a sincronização entre o Intune e a Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="f103c-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="f103c-123">Verificar a sincronização ativa entre o Intune e a Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="f103c-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="f103c-124">Etapa 2 - Atribuir Portal da Empresa aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="f103c-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="f103c-125">Após seu registro na Área de Trabalho Gerenciada da Microsoft, as Operações de Área de Trabalho Gerenciada da Microsoft implantarão automaticamente o Portal da Empresa em seu locatário e instalarão o aplicativo em dispositivos da Área de Trabalho Gerenciada da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f103c-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="f103c-126">Etapa 3 - Comunicar alterações aos usuários</span><span class="sxs-lookup"><span data-stu-id="f103c-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="f103c-127">Como administrador de IT da sua organização, é importante que os usuários saibam como usar o Portal da Empresa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f103c-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="f103c-128">A Área de Trabalho Gerenciada da Microsoft recomenda:</span><span class="sxs-lookup"><span data-stu-id="f103c-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="f103c-129">Etapas sobre a instalação de aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="f103c-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="f103c-130">Para obter mais informações, [consulte Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span><span class="sxs-lookup"><span data-stu-id="f103c-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="f103c-131">Como enviar solicitações aos administradores de IT para aplicativos que não estão disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="f103c-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="f103c-132">Para obter mais informações, [consulte Solicitar um aplicativo para trabalho ou escola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="f103c-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="f103c-133">Etapas para começar com a Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f103c-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="f103c-134">Adicionar e verificar contatos do administrador no portal de Administração</span><span class="sxs-lookup"><span data-stu-id="f103c-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="f103c-135">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="f103c-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="f103c-136">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="f103c-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="f103c-137">Implantar o Portal da Empresa do Intune (este tópico)</span><span class="sxs-lookup"><span data-stu-id="f103c-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="f103c-138">Habilitar Roaming de Estado da Empresa</span><span class="sxs-lookup"><span data-stu-id="f103c-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="f103c-139">Configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="f103c-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="f103c-140">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="f103c-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="f103c-141">Implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="f103c-141">Deploy apps</span></span>](deploy-apps.md)