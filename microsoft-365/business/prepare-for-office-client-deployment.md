---
title: Preparar para distribuição de cliente do Office com o Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Saiba como instalar os aplicativos do Office de 32 bits em computadores Windows 10 e mantê-los atualizados automaticamente.
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864676"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="5ec84-103">Preparar para distribuição de cliente do Office com o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5ec84-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="5ec84-104">Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes</span><span class="sxs-lookup"><span data-stu-id="5ec84-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="5ec84-105">Você pode usar o Microsoft 365 Business para instalar os aplicativos do Office de 32 bits em computadores com o Windows 10 e mantê-los atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5ec84-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="5ec84-106">Isso funciona melhor se o computador do usuário final tiver o Windows 10 Business e:</span><span class="sxs-lookup"><span data-stu-id="5ec84-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="5ec84-107">Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="5ec84-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="5ec84-108">ou</span><span class="sxs-lookup"><span data-stu-id="5ec84-108">or</span></span>
    
- <span data-ttu-id="5ec84-109">Tiver instalada uma versão Clique para Executar do Office.</span><span class="sxs-lookup"><span data-stu-id="5ec84-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="5ec84-p101">Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**). Se você vir Atualizações do Office, como é mostrado na figura a seguir, a instalação foi realizada usando o Clique para Executar.</span><span class="sxs-lookup"><span data-stu-id="5ec84-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="5ec84-113">**Quem se beneficia com esse recurso**</span><span class="sxs-lookup"><span data-stu-id="5ec84-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="5ec84-114">O usuário final cujo PC:</span><span class="sxs-lookup"><span data-stu-id="5ec84-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="5ec84-115">**Tem** uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 Business, a Atualização do Windows 10 para Criadores e ingressou no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ec84-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="5ec84-p102">**Não tem** aplicativos do Office de 64 bits (exemplo: Word, Excel, Powerpoint). Se os aplicativos do Office de 64 bits forem necessários, esse recurso não é o ideal, pois não há suporte para acionar uma versão Clique para Executar de 64 bits do Office 2016 pelo console de administração do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5ec84-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="5ec84-p103">**Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project). O Microsoft 365 Business atualiza o Office para a versão Clique para Executar do Office 2016 e ela não funciona com aplicativos autônomos do Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="5ec84-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="5ec84-120">A tabela a seguir detalha as ações que os usuários finais/administradores podem precisar tomar, dependendo do seu estado inicial, para ter uma versão Clique para Executar de 32 bits do Office pelo console de administração do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5ec84-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="5ec84-121">**Status inicial de instalação do Office**</span><span class="sxs-lookup"><span data-stu-id="5ec84-121">**Starting Office install status**</span></span>|<span data-ttu-id="5ec84-122">**Ação a ser executada antes de instalar o Office pelo Microsoft 365 Business**</span><span class="sxs-lookup"><span data-stu-id="5ec84-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="5ec84-123">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="5ec84-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ec84-124">Nenhum pacote do Office instalado</span><span class="sxs-lookup"><span data-stu-id="5ec84-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="5ec84-125">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ec84-125">None</span></span>  <br/> |<span data-ttu-id="5ec84-126">O Office 2016 de 32 bits foi instalado usando Clique para Executar</span><span class="sxs-lookup"><span data-stu-id="5ec84-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="5ec84-127">Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo</span><span class="sxs-lookup"><span data-stu-id="5ec84-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="5ec84-128">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ec84-128">None</span></span>  <br/> |<span data-ttu-id="5ec84-129">Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\***</span><span class="sxs-lookup"><span data-stu-id="5ec84-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="5ec84-130">Versão Clique para Executar de 32 bits do Office e aplicativos autônomos Clique para Executar de 32 ou 64 bits do Office (por exemplo, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="5ec84-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="5ec84-131">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ec84-131">None</span></span>  <br/> |<span data-ttu-id="5ec84-p104">Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="5ec84-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="5ec84-134">Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)</span><span class="sxs-lookup"><span data-stu-id="5ec84-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="5ec84-135">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ec84-135">None</span></span>  <br/> |<span data-ttu-id="5ec84-p105">Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="5ec84-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="5ec84-138">Qualquer versão Clique para Executar de 64 bits do Office</span><span class="sxs-lookup"><span data-stu-id="5ec84-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="5ec84-139">Desinstalar os aplicativos do Office de 64 bits, se for possível substituí-los pelos aplicativos do Office de 32 bits</span><span class="sxs-lookup"><span data-stu-id="5ec84-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="5ec84-140">Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada</span><span class="sxs-lookup"><span data-stu-id="5ec84-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="5ec84-141">Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="5ec84-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="5ec84-142">Desinstale o MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="5ec84-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="5ec84-p106">A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="5ec84-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="5ec84-145">Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office</span><span class="sxs-lookup"><span data-stu-id="5ec84-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="5ec84-146">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="5ec84-146">None</span></span>  <br/> |<span data-ttu-id="5ec84-147">A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado</span><span class="sxs-lookup"><span data-stu-id="5ec84-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="5ec84-p107">**(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido. A correção está em andamento.</span><span class="sxs-lookup"><span data-stu-id="5ec84-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


