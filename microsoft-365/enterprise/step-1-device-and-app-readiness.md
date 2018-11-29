---
title: 'Etapa 1: preparação de dispositivos e aplicativos'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Aprenda a avaliar a preparação de dispositivos e aplicativos no ambiente.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865327"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="8265e-103">Etapa 1: preparação de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="8265e-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="8265e-104">Comece seu projeto de implantação da área de trabalho com um inventário dos seus dispositivos e aplicativos, priorize o que você deseja avançar, teste os aplicativos e dispositivos priorizados e corrija o que for preciso para se preparar para a implantação.</span><span class="sxs-lookup"><span data-stu-id="8265e-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="8265e-105"><strong>Etapa 1: preparação de dispositivos e aplicativos</strong></span><span class="sxs-lookup"><span data-stu-id="8265e-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="8265e-106">Comece seu projeto de implantação da área de trabalho com um inventário dos seus dispositivos e aplicativos, priorize o que você deseja avançar, teste os aplicativos e dispositivos priorizados e corrija o que for preciso para se preparar para a implantação.</span><span class="sxs-lookup"><span data-stu-id="8265e-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="8265e-p101">A Preparação de Dispositivos e Aplicativos é a primeira etapa na nossa roda de processos de implantação recomendados, cobrindo os aspectos abrangentes da compatibilidade de aplicativos e hardware. Para ver o processo de implantação completo da área de trabalho, acesse o [Centro de implantação do Computador Moderno](https://aka.ms/HowToShift).</span><span class="sxs-lookup"><span data-stu-id="8265e-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="8265e-p102">No passado, um grande desafio para a atualização de computadores dos usuários era a compatibilidade entre aplicativos e hardware. A boa notícia ao planejar sua migração para o Windows 10 e Office 365 ProPlus é que qualquer aplicativo escrito nos últimos 10 anos funciona no Windows 10, e todos os suplementos e macros do VBA que sua organização usou em versões do Office desde o Office 2010 continuam a funcionar em versões mais recentes do Office, sem precisar de modificações.</span><span class="sxs-lookup"><span data-stu-id="8265e-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="8265e-111">Dito isto, dependendo do tamanho e da idade da sua organização, verificar a compatibilidade entre aplicativos e hardware provavelmente ainda é uma etapa inicial essencial no nosso processo de implantação recomendado de fase de 8.</span><span class="sxs-lookup"><span data-stu-id="8265e-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="8265e-112">Neste artigo, fornecemos orientações sobre esta primeira fase – Preparação de Dispositivos e Aplicativos – usando a nova ferramenta Windows Analytics Upgrade Readiness, uma solução inteligente baseada na nuvem disponível com sua licença do Windows.</span><span class="sxs-lookup"><span data-stu-id="8265e-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="8265e-113">Se você atualmente não tem o Windows Analytics configurado para seu ambiente, ou deseja inscrever-se para uma avaliação, acesse a [Página do Windows Analytics](http://www.aka.ms/windowsanalytics) e comece a usar.</span><span class="sxs-lookup"><span data-stu-id="8265e-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="8265e-114">Ferramenta recomendada: Windows Analytics Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="8265e-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="8265e-p103">O Windows Analytics Upgrade Readiness oferece muitas vantagens em relação a sistemas de gerenciamento de área de trabalho tradicionais, e é a nossa ferramenta recomendada. Funciona sem agentes, fornece orientações sobre o que precisa ser feito e utiliza informações de compatibilidade entre aplicativos e drivers, obtidas por meio da atualização de centenas de milhões de PCs de consumidores, para fornecer uma análise detalhada que identifica problemas de compatibilidade que podem impedir sua atualização, com links para correções sugeridas de conhecimento da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8265e-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="8265e-p104">Para configurar o Window Analytics Upgrade Readiness, primeiro será preciso configurar uma assinatura do Azure e incluir um espaço de trabalho do Azure Log Analytics para fazer isso. Depois que o serviço Windows Analytics Upgrade Readiness estiver em execução, você poderá inscrever qualquer dispositivo com Windows 7 SP1 ou mais recente conectado à Internet por meio das configurações de Política de Grupo. É simples assim. Não existem agentes para implantar, e o fluxo de trabalho visual do Windows Analytics Upgrade Readiness orienta você desde o teste piloto até à implantação para produção. Se desejar, você pode exportar dados do Windows Analytics Upgrade Readiness para ferramentas de implantação de software como o System Center Configuration Manager, para direcionar a PCs individualmente e criar conjuntos assim que eles estejam prontos para implantação.</span><span class="sxs-lookup"><span data-stu-id="8265e-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="8265e-122">Preparação de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="8265e-122">Device and App Readiness Process</span></span>

<span data-ttu-id="8265e-p105">A Preparação de Dispositivos e Aplicativos é composta por quatro etapas: 1. Inventário, 2. Priorizar, 3. Testar, 4. Corrigir. Vamos examiná-las uma de cada vez.</span><span class="sxs-lookup"><span data-stu-id="8265e-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="8265e-p106">1\. Inventário</span><span class="sxs-lookup"><span data-stu-id="8265e-p106">1\. Inventory</span></span>

<span data-ttu-id="8265e-131">O serviço do Windows Analytics Upgrade Readiness usa um processo sem agentes para inventariar os computadores, aplicativos e suplementos do Office no seu conjunto de computadores.</span><span class="sxs-lookup"><span data-stu-id="8265e-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="8265e-132">Ele também fornece relatórios sobre sites da Internet, aplicativos e locais da intranet altamente visitados, para ajudá-lo a realizar testes de compatibilidade posteriormente.</span><span class="sxs-lookup"><span data-stu-id="8265e-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="8265e-p107">2\. Priorizar</span><span class="sxs-lookup"><span data-stu-id="8265e-p107">2\. Prioritize</span></span>

<span data-ttu-id="8265e-135">Com o inventário realizado, o Windows Analytics Upgrade Readiness ajuda a identificar e priorizar os aplicativos e hardware mais comumente usados na sua organização, e no que se concentrar para desbloquear o máximo de computadores possível para implantação,</span><span class="sxs-lookup"><span data-stu-id="8265e-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="8265e-136">também fornecendo orientações para ajudá-lo a avaliar as atualizações necessárias para resolver problemas durante a próxima etapa: o teste.</span><span class="sxs-lookup"><span data-stu-id="8265e-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="8265e-p108">3\. Testar</span><span class="sxs-lookup"><span data-stu-id="8265e-p108">3\. Testing</span></span>

<span data-ttu-id="8265e-p109">Você descobrirá que a maioria dos suplementos, aplicativos e drivers inventariados funcionarão sem precisar de alterações. Para os itens que o Windows Analytics Upgrade Readiness avalie como tendo problemas, ele oferece informações conhecidas, incluindo onde encontrar atualizações de versão para resolver problemas de compatibilidade. Em vez de dedicar tempo e recursos para solucionar problemas complexos em aplicativos não essenciais pouco implantados e dispositivos antigos, você pode optar por trabalhar com os usuários para desativar e substituir esses itens.</span><span class="sxs-lookup"><span data-stu-id="8265e-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="8265e-p110">Você também pode usar o Windows Analytics Upgrade Readiness para avaliar problemas de compatibilidade baseados no navegador, identificar os aplicativos Web e sites acessados por usuários que ainda estão usando controles ActiveX, Objetos de Ajuda do Navegador, VBScript ou outras tecnologias herdadas sem suporte no navegador Microsoft Edge. Seus usuários ainda precisarão usar o Internet Explorer 11 para esses sites, e você pode adicioná-los à [lista de sites do modo Empresarial](https://docs.microsoft.com/pt-BR/microsoft-edge/deploy/emie-to-improve-compatibility) usando o Enterprise Mode Site List Manager.</span><span class="sxs-lookup"><span data-stu-id="8265e-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/pt-BR/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="8265e-144">Além disso, para ajudar na mudança para o Office 365 ProPlus, você pode usar o [Readiness Toolkit for Office](https://docs.microsoft.com/pt-BR/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) para testar a compatibilidade dos seus suplementos e macros do Microsoft Visual Basic for Applications (VBA).</span><span class="sxs-lookup"><span data-stu-id="8265e-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/pt-BR/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="8265e-p111">4\. Corrigir</span><span class="sxs-lookup"><span data-stu-id="8265e-p111">4\. Remediation</span></span>

<span data-ttu-id="8265e-p112">Como a fase final da preparação de dispositivos e aplicativos é "corrigir", aqui o seu objetivo será coletar os pacotes de driver ou softwares necessários, que serão usados para substituir ou atualizar as versões mais antigas como parte do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="8265e-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="8265e-p113">Conforme remedia problemas da lista, você verá que mais e mais PCs ficam "Prontos para implantação". Isso significa que os drivers e os aplicativos nos computadores estão listados como compatíveis com a versão de destino para implantação do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8265e-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="8265e-151">Uso contínuo de ferramentas de telemetria</span><span class="sxs-lookup"><span data-stu-id="8265e-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="8265e-p114">O Windows Analytics Upgrade Readiness não é apenas uma ferramenta para ajudá-lo a mudar para o Windows 10 e Office 365 ProPlus. Quando tiver computadores executando o Windows 10 e o Office 365, você poderá usar esta ferramenta para ajudar na manutenção da sua implantação e para gerenciar as Atualizações de Recursos semestrais e manter-se atualizado.</span><span class="sxs-lookup"><span data-stu-id="8265e-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="8265e-154">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8265e-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="8265e-155">Etapa 2: diretório e preparação de rede</span><span class="sxs-lookup"><span data-stu-id="8265e-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)