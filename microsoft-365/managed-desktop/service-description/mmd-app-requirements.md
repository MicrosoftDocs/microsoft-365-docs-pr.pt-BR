---
title: Requisitos do aplicativo da área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278331"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="3c454-103">Requisitos do aplicativo da área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c454-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="3c454-104">Os aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciado da Microsoft devem atender aos requisitos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3c454-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="3c454-105">Condição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3c454-105">Application condition</span></span>

<span data-ttu-id="3c454-106">É importante que os aplicativos não afetem negativamente o ambiente de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c454-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="3c454-107">A seguir estão os requisitos que um aplicativo deve atender para que a Microsoft o implante.</span><span class="sxs-lookup"><span data-stu-id="3c454-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="3c454-108">Para qualquer aplicativo ou driver específico, a Microsoft pode renunciar a qualquer requisito fornecido aqui.</span><span class="sxs-lookup"><span data-stu-id="3c454-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="3c454-109">A Microsoft pode decidir remover qualquer aplicativo ou driver que impacta negativamente o desempenho e a confiabilidade dos dispositivos de área de trabalho gerenciado da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c454-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="3c454-110">ImPlantável usando tecnologias Microsoft</span><span class="sxs-lookup"><span data-stu-id="3c454-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="3c454-111">O Microsoft Managed desktop usa o Intune, a Microsoft Store e a Microsoft Store para empresas para implantar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3c454-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="3c454-112">Consequentemente, os aplicativos devem ser empacotados de uma maneira que possa ser implantado pela versão atual desses serviços.</span><span class="sxs-lookup"><span data-stu-id="3c454-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="3c454-113">Classes de aplicativo proibidas</span><span class="sxs-lookup"><span data-stu-id="3c454-113">Prohibited app classes</span></span>

<span data-ttu-id="3c454-114">Determinados tipos de aplicativos não são permitidos em dispositivos de área de trabalho gerenciada da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3c454-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="3c454-115">software antivírus, de segurança ou de auditoria de terceiros</span><span class="sxs-lookup"><span data-stu-id="3c454-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="3c454-116">navegadores da Web de terceiros</span><span class="sxs-lookup"><span data-stu-id="3c454-116">3rd party web browsers</span></span>
- <span data-ttu-id="3c454-117">Versões do Microsoft Office anteriores ao Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="3c454-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="3c454-118">Aplicativos que instalam ou agrupam outros softwares de terceiros</span><span class="sxs-lookup"><span data-stu-id="3c454-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="3c454-119">Comportamentos de aplicativo restritos</span><span class="sxs-lookup"><span data-stu-id="3c454-119">Restricted app behaviors</span></span>

<span data-ttu-id="3c454-120">Determinados comportamentos de aplicativos podem ser prejudiciais à experiência do usuário ou apresentar um risco de segurança para os dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c454-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3c454-121">Os aplicativos não devem apresentar os seguintes comportamentos ou características:</span><span class="sxs-lookup"><span data-stu-id="3c454-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="3c454-122">Experiência do usuário:</span><span class="sxs-lookup"><span data-stu-id="3c454-122">User Experience:</span></span>
- <span data-ttu-id="3c454-123">Instalar os serviços em segundo plano ou gerar processos em segundo plano de execução longa</span><span class="sxs-lookup"><span data-stu-id="3c454-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="3c454-124">Adicione a si próprio ao caminho de inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="3c454-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="3c454-125">Segurança:</span><span class="sxs-lookup"><span data-stu-id="3c454-125">Security:</span></span>
- <span data-ttu-id="3c454-126">Chamar as APIs não documentadas do Windows ou do Office ou assumir dependências em estruturas de dados internas do Windows ou do Office</span><span class="sxs-lookup"><span data-stu-id="3c454-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="3c454-127">Atuar como uma loja de aplicativos ou ter um Gerenciador de extensões interno</span><span class="sxs-lookup"><span data-stu-id="3c454-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="3c454-128">Elevar os privilégios do usuário final</span><span class="sxs-lookup"><span data-stu-id="3c454-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="3c454-129">Ter vulnerabilidades de segurança conhecidas</span><span class="sxs-lookup"><span data-stu-id="3c454-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="3c454-130">Assinado usando um certificado que não se acumula em uma raiz confiável</span><span class="sxs-lookup"><span data-stu-id="3c454-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="3c454-131">Criptografar ou restringir o acesso aos dados do usuário final</span><span class="sxs-lookup"><span data-stu-id="3c454-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="3c454-132">Modificar o código do sistema operacional no tempo de execução</span><span class="sxs-lookup"><span data-stu-id="3c454-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="3c454-133">Implantação de driver</span><span class="sxs-lookup"><span data-stu-id="3c454-133">Driver deployment</span></span>

<span data-ttu-id="3c454-134">A menos que um driver esteja disponível no Windows Update ou tenha sido assinado separadamente pelo Windows Hardware Quality Lab (WHQL), a Microsoft deve aprovar um driver antes que a Microsoft implante o driver nos dispositivos da área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c454-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
