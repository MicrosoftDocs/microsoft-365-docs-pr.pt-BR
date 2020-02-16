---
title: Preparar para distribuição de cliente do Office com o Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Saiba como instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados.
ms.openlocfilehash: 0f8cd7df49ad627b190fad6737ec95a6d64d99d0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065088"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="0f4b7-103">Preparar para distribuição de cliente do Office com o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="0f4b7-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="0f4b7-104">Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes</span><span class="sxs-lookup"><span data-stu-id="0f4b7-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="0f4b7-105">Você pode usar o Microsoft 365 Business para instalar automaticamente os aplicativos do Office de 32 bits em computadores com Windows 10 e mantê-los atualizados com as atualizações.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="0f4b7-106">A instalação automática funciona melhor se o computador do usuário final estiver no Windows 10 Business e:</span><span class="sxs-lookup"><span data-stu-id="0f4b7-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="0f4b7-107">Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).</span><span class="sxs-lookup"><span data-stu-id="0f4b7-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="0f4b7-108">ou</span><span class="sxs-lookup"><span data-stu-id="0f4b7-108">or</span></span>
    
- <span data-ttu-id="0f4b7-109">Tiver instalada uma versão Clique para Executar do Office.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="0f4b7-110">Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**).</span><span class="sxs-lookup"><span data-stu-id="0f4b7-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="0f4b7-111">Se você vir **atualizações do Office** , conforme mostrado na figura a seguir, a instalação foi feita usando clique para executar.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="0f4b7-113">**Quem se beneficia de ter esse recurso**</span><span class="sxs-lookup"><span data-stu-id="0f4b7-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="0f4b7-114">O usuário final cujo PC:</span><span class="sxs-lookup"><span data-stu-id="0f4b7-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="0f4b7-115">**Tem** uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 Business, a Atualização do Windows 10 para Criadores e ingressou no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="0f4b7-116">**Não tem** aplicativos do Office de 64 bits (exemplo: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="0f4b7-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="0f4b7-117">Se os aplicativos do Office de 64 bits forem necessários, este recurso não é um bom ajuste porque não há suporte para o disparo de uma versão de 64 bits de 2016 clique para executar do Office a partir do console de administração de negócios do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="0f4b7-118">**Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project).</span><span class="sxs-lookup"><span data-stu-id="0f4b7-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="0f4b7-119">O Microsoft 365 Business atualiza o Office para a versão clique para executar do Office 2016 e que não funciona com o Office 2016 MSI standalone apps.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="0f4b7-120">A tabela a seguir mostra a ação que os usuários finais/administradores podem precisar executar, dependendo do seu estado inicial, para ter uma versão bem-sucedida de clique para executar de 32 bits do deployment do Office a partir do console de administração do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="0f4b7-121">**Status inicial de instalação do Office**</span><span class="sxs-lookup"><span data-stu-id="0f4b7-121">**Starting Office install status**</span></span>|<span data-ttu-id="0f4b7-122">**Ação a ser executada antes de instalar o Office pelo Microsoft 365 Business**</span><span class="sxs-lookup"><span data-stu-id="0f4b7-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="0f4b7-123">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="0f4b7-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f4b7-124">Nenhum pacote do Office instalado</span><span class="sxs-lookup"><span data-stu-id="0f4b7-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="0f4b7-125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0f4b7-125">None</span></span>  <br/> |<span data-ttu-id="0f4b7-126">O Office 2016 32-bit é instalado usando clique para executar</span><span class="sxs-lookup"><span data-stu-id="0f4b7-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="0f4b7-127">Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo</span><span class="sxs-lookup"><span data-stu-id="0f4b7-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="0f4b7-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0f4b7-128">None</span></span>  <br/> |<span data-ttu-id="0f4b7-129">Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\***</span><span class="sxs-lookup"><span data-stu-id="0f4b7-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="0f4b7-130">Versão de clique para executar de 32 bits do Office e aplicativos do Office autônomos clique para executar 32 bits ou 64 bits (por exemplo, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="0f4b7-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="0f4b7-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0f4b7-131">None</span></span>  <br/> |<span data-ttu-id="0f4b7-132">Aplicativos autônomos não são afetados.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="0f4b7-133">O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="0f4b7-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="0f4b7-134">Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)</span><span class="sxs-lookup"><span data-stu-id="0f4b7-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="0f4b7-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0f4b7-135">None</span></span>  <br/> |<span data-ttu-id="0f4b7-136">Aplicativos autônomos não são afetados.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="0f4b7-137">O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016</span><span class="sxs-lookup"><span data-stu-id="0f4b7-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="0f4b7-138">Qualquer versão Clique para Executar de 64 bits do Office</span><span class="sxs-lookup"><span data-stu-id="0f4b7-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="0f4b7-139">Desinstale os aplicativos do Office de 64 bits, se estiver tudo certo para substituí-los por aplicativos do Office de 32 bits</span><span class="sxs-lookup"><span data-stu-id="0f4b7-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="0f4b7-140">Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada</span><span class="sxs-lookup"><span data-stu-id="0f4b7-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="0f4b7-141">Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="0f4b7-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="0f4b7-142">Desinstale o MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="0f4b7-p106">A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos</span><span class="sxs-lookup"><span data-stu-id="0f4b7-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="0f4b7-145">Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office</span><span class="sxs-lookup"><span data-stu-id="0f4b7-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="0f4b7-146">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="0f4b7-146">None</span></span>  <br/> |<span data-ttu-id="0f4b7-147">A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado</span><span class="sxs-lookup"><span data-stu-id="0f4b7-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="0f4b7-148">**(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="0f4b7-149">Uma correção está em andamento.</span><span class="sxs-lookup"><span data-stu-id="0f4b7-149">A fix is in progress.</span></span> 
  
