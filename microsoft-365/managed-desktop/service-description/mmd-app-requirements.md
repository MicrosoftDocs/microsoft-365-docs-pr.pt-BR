---
title: Requisitos do aplicativo Microsoft Desktop gerenciados
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864663"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="ff61b-103">Requisitos do aplicativo Microsoft Desktop gerenciados</span><span class="sxs-lookup"><span data-stu-id="ff61b-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="ff61b-104">Aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciada do Microsoft devem atender aos requisitos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ff61b-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="ff61b-105">Condição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ff61b-105">Application condition</span></span>

<span data-ttu-id="ff61b-p101">É importante que os aplicativos não afetam adversamente o ambiente de área de trabalho gerenciada do Microsoft. A seguir estão os requisitos que precisa atender a um aplicativo na ordem para a Microsoft implantá-lo. Para qualquer determinado aplicativo ou driver, Microsoft talvez cancelamento qualquer requisito fornecido aqui. Microsoft poderá optar por remover qualquer aplicativo ou driver que afeta negativamente o desempenho e confiabilidade de dispositivos do Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ff61b-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="ff61b-110">Implantáveis usando tecnologias da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ff61b-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="ff61b-p102">Microsoft Desktop gerenciados usa Intune, Microsoft Store e Microsoft Store for Business para implantar aplicativos. Consequentemente, os aplicativos devem ser empacotados de maneira que poderão ser implantados pela versão atual desses serviços.</span><span class="sxs-lookup"><span data-stu-id="ff61b-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="ff61b-113">Classes de app proibido</span><span class="sxs-lookup"><span data-stu-id="ff61b-113">Prohibited app classes</span></span>

<span data-ttu-id="ff61b-114">Certos tipos de aplicativo não são permitidos em dispositivos Microsoft Desktop gerenciados:</span><span class="sxs-lookup"><span data-stu-id="ff61b-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="ff61b-115">3º antivírus de terceiros, segurança ou software de auditoria</span><span class="sxs-lookup"><span data-stu-id="ff61b-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="ff61b-116">Versões do Microsoft Office anteriores ao Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="ff61b-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="ff61b-117">Aplicativos que instalam ou agrupam os outros softwares de terceiros 3º</span><span class="sxs-lookup"><span data-stu-id="ff61b-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="ff61b-118">Comportamentos de app restritos</span><span class="sxs-lookup"><span data-stu-id="ff61b-118">Restricted app behaviors</span></span>

<span data-ttu-id="ff61b-p103">Determinados comportamentos de aplicativo podem ser ser prejudicial a experiência do usuário ou representam um risco de segurança para dispositivos Microsoft Desktop gerenciados. Aplicativos não devem apresentar os seguintes comportamentos ou características:</span><span class="sxs-lookup"><span data-stu-id="ff61b-p103">Certain application behaviors can be either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 
- <span data-ttu-id="ff61b-121">Instalar os serviços de plano de fundo ou disparar processos de plano de fundo de execução longa</span><span class="sxs-lookup"><span data-stu-id="ff61b-121">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="ff61b-122">Se adicionar ao caminho de inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="ff61b-122">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="ff61b-123">Chamar não documentado Windows ou as APIs de escritório ou assumir dependências nas estruturas de dados internas do Windows ou do Office</span><span class="sxs-lookup"><span data-stu-id="ff61b-123">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="ff61b-124">Atuar como um repositório de app ou que o Gerenciador de extensão interna</span><span class="sxs-lookup"><span data-stu-id="ff61b-124">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="ff61b-125">Eleva os privilégios do usuário final</span><span class="sxs-lookup"><span data-stu-id="ff61b-125">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="ff61b-126">Ter vulnerabilidades de segurança conhecidas</span><span class="sxs-lookup"><span data-stu-id="ff61b-126">Have known security vulnerabilities</span></span>
- <span data-ttu-id="ff61b-127">Assinados com um certificado que não acumular uma raiz confiável</span><span class="sxs-lookup"><span data-stu-id="ff61b-127">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="ff61b-128">Criptografar ou restringir o acesso aos dados do usuário final</span><span class="sxs-lookup"><span data-stu-id="ff61b-128">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="ff61b-129">Modificar o código de sistema operacional em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="ff61b-129">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="ff61b-130">Implantação do driver</span><span class="sxs-lookup"><span data-stu-id="ff61b-130">Driver deployment</span></span>

<span data-ttu-id="ff61b-131">A menos que um driver está disponível no Windows Update ou separadamente é assinado pelo laboratório de qualidade de Hardware para Windows (WHQL), Microsoft deve aprovar um driver antes que o Microsoft implantará o driver dispositivos Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ff61b-131">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>