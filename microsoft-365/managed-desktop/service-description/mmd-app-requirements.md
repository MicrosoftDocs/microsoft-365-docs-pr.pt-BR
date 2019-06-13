---
title: Requisitos do aplicativo da área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ded8bcfd87a6b430dfc4be055a582b482872b104
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913012"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="cf503-103">Requisitos do aplicativo da área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cf503-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="cf503-104">Para garantir o desempenho, a confiabilidade e a manutenção dos dispositivos de área de trabalho gerenciada da Microsoft, os aplicativos de linha de negócios do cliente não precisam afetar seriamente a experiência do usuário final ou modificar a postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="cf503-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="cf503-105">Consequentemente, os aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciada da Microsoft devem atender aos requisitos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cf503-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="cf503-106">Condição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="cf503-106">Application condition</span></span>

<span data-ttu-id="cf503-107">É importante que os aplicativos não afetem negativamente o ambiente de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="cf503-108">A seguir estão os requisitos que um aplicativo deve atender para um aplicativo a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="cf503-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="cf503-109">Para qualquer aplicativo ou driver específico, a Microsoft pode renunciar a qualquer requisito fornecido aqui.</span><span class="sxs-lookup"><span data-stu-id="cf503-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="cf503-110">A Microsoft pode decidir remover qualquer aplicativo ou driver que impacta negativamente o desempenho e a confiabilidade dos dispositivos de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="cf503-111">Aplicativos gerenciados de forma centralizada</span><span class="sxs-lookup"><span data-stu-id="cf503-111">Centrally managed apps</span></span>

<span data-ttu-id="cf503-112">Todos os aplicativos e drivers instalados em dispositivos gerenciados pela Microsoft devem ser implantados por meio do Microsoft Intune, da Microsoft Store ou da Microsoft Store para empresas; Se estiver disponível, os drivers também serão implantados por meio do serviço Windows Update.</span><span class="sxs-lookup"><span data-stu-id="cf503-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="cf503-113">Classes de aplicativo proibidas</span><span class="sxs-lookup"><span data-stu-id="cf503-113">Prohibited app classes</span></span>

<span data-ttu-id="cf503-114">Determinados tipos de aplicativos não são permitidos em dispositivos de área de trabalho gerenciada da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="cf503-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="cf503-115">software antivírus, de segurança ou de auditoria de terceiros</span><span class="sxs-lookup"><span data-stu-id="cf503-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="cf503-116">Versões do Microsoft Office anteriores ao Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="cf503-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="cf503-117">Aplicativos que instalam ou agrupam outros softwares de terceiros</span><span class="sxs-lookup"><span data-stu-id="cf503-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="cf503-118">Comportamentos de aplicativo restritos</span><span class="sxs-lookup"><span data-stu-id="cf503-118">Restricted app behaviors</span></span>

<span data-ttu-id="cf503-119">Determinados comportamentos de aplicativo podem afetar negativamente a experiência do usuário ou podem representar um risco de segurança para os dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="cf503-120">Os aplicativos com os seguintes comportamentos não podem ser executados no ambiente de área de trabalho gerenciada da Microsoft sem uma isenção específica da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="cf503-121">Experiência do usuário:</span><span class="sxs-lookup"><span data-stu-id="cf503-121">User Experience:</span></span>
- <span data-ttu-id="cf503-122">Instalar serviços em segundo plano</span><span class="sxs-lookup"><span data-stu-id="cf503-122">Install background services</span></span>
- <span data-ttu-id="cf503-123">Adicione a si próprio ao caminho de inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="cf503-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="cf503-124">Aplicativos dependentes de drivers</span><span class="sxs-lookup"><span data-stu-id="cf503-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="cf503-125">navegadores da Web de terceiros</span><span class="sxs-lookup"><span data-stu-id="cf503-125">3rd party web browsers</span></span>

<span data-ttu-id="cf503-126">Segurança:</span><span class="sxs-lookup"><span data-stu-id="cf503-126">Security:</span></span>
- <span data-ttu-id="cf503-127">Elevar os privilégios do usuário final</span><span class="sxs-lookup"><span data-stu-id="cf503-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="cf503-128">Atuar como uma loja de aplicativos ou ter um Gerenciador de extensões interno</span><span class="sxs-lookup"><span data-stu-id="cf503-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="cf503-129">Ter vulnerabilidades de segurança conhecidas</span><span class="sxs-lookup"><span data-stu-id="cf503-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="cf503-130">Criptografar ou restringir o acesso aos dados do usuário final</span><span class="sxs-lookup"><span data-stu-id="cf503-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="cf503-131">Não está assinado ou assinado usando um certificado que não se acumula em uma raiz confiável</span><span class="sxs-lookup"><span data-stu-id="cf503-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="cf503-132">Implantação de driver</span><span class="sxs-lookup"><span data-stu-id="cf503-132">Driver deployment</span></span>

<span data-ttu-id="cf503-133">A área de trabalho gerenciada da Microsoft suporta apenas drivers de dispositivos que estão disponíveis por meio do Windows Update ou da caixa de entrada instalada com o dispositivo gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="cf503-134">Se um aplicativo exigir que um ou mais drivers específicos sejam executados, será considerado um aplicativo restrito e exigirá a implantação da isenção na área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf503-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

