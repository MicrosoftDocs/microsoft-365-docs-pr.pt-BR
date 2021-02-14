---
title: Preparar-se para a implantação do cliente do Office pelo Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Saiba como instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470938"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="6c147-103">Preparar-se para a implantação do cliente do Office pelo Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6c147-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="6c147-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6c147-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="6c147-105">Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes</span><span class="sxs-lookup"><span data-stu-id="6c147-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="6c147-106">Você pode usar o Microsoft 365 Business Premium para instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados.</span><span class="sxs-lookup"><span data-stu-id="6c147-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="6c147-107">A instalação automática funciona melhor se o computador do usuário final estiver no Windows 10 Business e:</span><span class="sxs-lookup"><span data-stu-id="6c147-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="6c147-108">Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="6c147-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="6c147-109">ou</span><span class="sxs-lookup"><span data-stu-id="6c147-109">or</span></span>
    
- <span data-ttu-id="6c147-110">Tiver instalada uma versão Clique para Executar do Office.</span><span class="sxs-lookup"><span data-stu-id="6c147-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="6c147-111">Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**).</span><span class="sxs-lookup"><span data-stu-id="6c147-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="6c147-112">Se você vir **as Atualizações do Office** conforme mostrado na figura a seguir, a instalação foi feita usando o Clique para Executar.</span><span class="sxs-lookup"><span data-stu-id="6c147-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="6c147-114">**Quem se beneficia de ter esse recurso**</span><span class="sxs-lookup"><span data-stu-id="6c147-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="6c147-115">O usuário final cujo PC:</span><span class="sxs-lookup"><span data-stu-id="6c147-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="6c147-116">**Tem**  uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 para empresas, a Atualização do Windows 10 para Criadores e está ingressada no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c147-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="6c147-117">**Não tem aplicativos** do Office de 64 bits (exemplo: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="6c147-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="6c147-118">Se os aplicativos do Office de 64 bits são necessários, esse recurso não é uma boa ideia porque não há suporte para acionar uma versão Clique para Executar de 64 bits do Office de 2016 a partir do console de administração do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="6c147-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="6c147-119">**Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project).</span><span class="sxs-lookup"><span data-stu-id="6c147-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="6c147-120">O Microsoft 365 para empresas atualiza o Office para a versão Clique para Executar do Office 2016 e isso não funciona com aplicativos autônomos MSI do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="6c147-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="6c147-121">A tabela a seguir mostra qual ação os usuários finais/administradores podem precisar tomar, dependendo do estado inicial, para ter uma versão Clique para Executar de 32 bits bem-sucedida da implantação do Office no console de administração do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="6c147-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="6c147-122">**Status inicial de instalação do Office**</span><span class="sxs-lookup"><span data-stu-id="6c147-122">**Starting Office install status**</span></span>|<span data-ttu-id="6c147-123">**Ação a ser tomada antes da instalação do Microsoft 365 para empresas do Office**</span><span class="sxs-lookup"><span data-stu-id="6c147-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="6c147-124">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="6c147-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c147-125">Nenhum pacote do Office instalado</span><span class="sxs-lookup"><span data-stu-id="6c147-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="6c147-126">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="6c147-126">None</span></span>  <br/> |<span data-ttu-id="6c147-127">O Office 2016 de 32 bits é instalado usando Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="6c147-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="6c147-128">Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo</span><span class="sxs-lookup"><span data-stu-id="6c147-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="6c147-129">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="6c147-129">None</span></span>  <br/> |<span data-ttu-id="6c147-130">Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\***</span><span class="sxs-lookup"><span data-stu-id="6c147-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="6c147-131">Versão Clique para Executar de 32 bits do Office e aplicativos autônomos clique para executar de 32 bits ou 64 bits do Office (por exemplo, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="6c147-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="6c147-132">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6c147-132">None</span></span>  <br/> |<span data-ttu-id="6c147-133">Aplicativos autônomos não são afetados.</span><span class="sxs-lookup"><span data-stu-id="6c147-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="6c147-134">O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="6c147-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="6c147-135">Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)</span><span class="sxs-lookup"><span data-stu-id="6c147-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="6c147-136">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="6c147-136">None</span></span>  <br/> |<span data-ttu-id="6c147-137">Aplicativos autônomos não são afetados.</span><span class="sxs-lookup"><span data-stu-id="6c147-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="6c147-138">O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="6c147-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="6c147-139">Qualquer versão Clique para Executar de 64 bits do Office</span><span class="sxs-lookup"><span data-stu-id="6c147-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="6c147-140">Desinstalar os aplicativos do Office de 64 bits, se não for problema substituí-los por aplicativos do Office de 32 bits</span><span class="sxs-lookup"><span data-stu-id="6c147-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="6c147-141">Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada</span><span class="sxs-lookup"><span data-stu-id="6c147-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="6c147-142">Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="6c147-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="6c147-143">Desinstale o MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="6c147-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="6c147-p106">A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="6c147-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="6c147-146">Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office</span><span class="sxs-lookup"><span data-stu-id="6c147-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="6c147-147">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="6c147-147">None</span></span>  <br/> |<span data-ttu-id="6c147-148">A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado</span><span class="sxs-lookup"><span data-stu-id="6c147-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="6c147-149">**(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido.</span><span class="sxs-lookup"><span data-stu-id="6c147-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="6c147-150">Uma correção está em andamento.</span><span class="sxs-lookup"><span data-stu-id="6c147-150">A fix is in progress.</span></span> 
  
