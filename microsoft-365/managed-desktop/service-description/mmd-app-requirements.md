---
title: Requisitos do aplicativo Microsoft Desktop gerenciados
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864663"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="66971-103">Requisitos do aplicativo Microsoft Desktop gerenciados</span><span class="sxs-lookup"><span data-stu-id="66971-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="66971-104">Aplicativos de linha de negócios que você deseja implantar para os dispositivos de área de trabalho gerenciada do Microsoft devem atender aos requisitos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66971-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="66971-105">Condição de aplicativo</span><span class="sxs-lookup"><span data-stu-id="66971-105">Application condition</span></span>

<span data-ttu-id="66971-p101">É importante que os aplicativos não afetam adversamente o ambiente de área de trabalho gerenciada do Microsoft. A seguir estão os requisitos que precisa atender a um aplicativo na ordem para a Microsoft implantá-lo. Para qualquer determinado aplicativo ou driver, Microsoft talvez cancelamento qualquer requisito fornecido aqui. Microsoft poderá optar por remover qualquer aplicativo ou driver que afeta negativamente o desempenho e confiabilidade de dispositivos do Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="66971-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="66971-110">Implantáveis usando tecnologias da Microsoft</span><span class="sxs-lookup"><span data-stu-id="66971-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="66971-p102">Microsoft Desktop gerenciados usa Intune, Microsoft Store e Microsoft Store for Business para implantar aplicativos. Consequentemente, os aplicativos devem ser empacotados de maneira que poderão ser implantados pela versão atual desses serviços.</span><span class="sxs-lookup"><span data-stu-id="66971-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="66971-113">Classes de app proibido</span><span class="sxs-lookup"><span data-stu-id="66971-113">Prohibited app classes</span></span>

<span data-ttu-id="66971-114">Certos tipos de aplicativo não são permitidos em dispositivos Microsoft Desktop gerenciados:</span><span class="sxs-lookup"><span data-stu-id="66971-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="66971-115">3º antivírus de terceiros, segurança ou software de auditoria</span><span class="sxs-lookup"><span data-stu-id="66971-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="66971-116">3º navegadores da web de terceiros</span><span class="sxs-lookup"><span data-stu-id="66971-116">3rd party web browsers</span></span>
- <span data-ttu-id="66971-117">Versões do Microsoft Office anteriores ao Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="66971-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="66971-118">Aplicativos que instalam ou agrupam os outros softwares de terceiros 3º</span><span class="sxs-lookup"><span data-stu-id="66971-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="66971-119">Comportamentos de app restritos</span><span class="sxs-lookup"><span data-stu-id="66971-119">Restricted app behaviors</span></span>

<span data-ttu-id="66971-p103">Determinados comportamentos de aplicativo podem ser prejudicial a experiência do usuário ou representar um risco de segurança para dispositivos Microsoft Desktop gerenciados. Aplicativos não devem apresentar os seguintes comportamentos ou características:</span><span class="sxs-lookup"><span data-stu-id="66971-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="66971-122">Experiência do usuário:</span><span class="sxs-lookup"><span data-stu-id="66971-122">User Experience:</span></span>
- <span data-ttu-id="66971-123">Instalar os serviços de plano de fundo ou disparar processos de plano de fundo de execução longa</span><span class="sxs-lookup"><span data-stu-id="66971-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="66971-124">Se adicionar ao caminho de inicialização do Windows</span><span class="sxs-lookup"><span data-stu-id="66971-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="66971-125">Segurança:</span><span class="sxs-lookup"><span data-stu-id="66971-125">Security:</span></span>
- <span data-ttu-id="66971-126">Chamar não documentado Windows ou as APIs de escritório ou assumir dependências nas estruturas de dados internas do Windows ou do Office</span><span class="sxs-lookup"><span data-stu-id="66971-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="66971-127">Atuar como um repositório de app ou que o Gerenciador de extensão interna</span><span class="sxs-lookup"><span data-stu-id="66971-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="66971-128">Eleva os privilégios do usuário final</span><span class="sxs-lookup"><span data-stu-id="66971-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="66971-129">Ter vulnerabilidades de segurança conhecidas</span><span class="sxs-lookup"><span data-stu-id="66971-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="66971-130">Assinados com um certificado que não acumular uma raiz confiável</span><span class="sxs-lookup"><span data-stu-id="66971-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="66971-131">Criptografar ou restringir o acesso aos dados do usuário final</span><span class="sxs-lookup"><span data-stu-id="66971-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="66971-132">Modificar o código de sistema operacional em tempo de execução</span><span class="sxs-lookup"><span data-stu-id="66971-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="66971-133">Implantação do driver</span><span class="sxs-lookup"><span data-stu-id="66971-133">Driver deployment</span></span>

<span data-ttu-id="66971-134">A menos que um driver está disponível no Windows Update ou separadamente é assinado pelo laboratório de qualidade de Hardware para Windows (WHQL), Microsoft deve aprovar um driver antes que o Microsoft implantará o driver dispositivos Microsoft Desktop gerenciados.</span><span class="sxs-lookup"><span data-stu-id="66971-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
