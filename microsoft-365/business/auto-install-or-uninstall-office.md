---
title: Instalar ou desinstalar o Office em dispositivos Windows 10 automaticamente
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Instalar ou desinstalar o Office em dispositivos Windows 10 do Centro de administração do Microsoft 365 Business. '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865107"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="85aaf-103">Instalar ou desinstalar o Office em dispositivos Windows 10 automaticamente</span><span class="sxs-lookup"><span data-stu-id="85aaf-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="85aaf-104">Você pode instalar com rapidez e facilidade o Office para computadores com o Windows 10 pelo centro de administração do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="85aaf-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="85aaf-105">Para entender como isso funciona com os aplicativos do Office instalados anteriormente, leia [Preparar-se para a instalação do cliente do Office](prepare-for-office-client-deployment.md) antes de começar.</span><span class="sxs-lookup"><span data-stu-id="85aaf-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="85aaf-106">Gerenciar as implantações do Office</span><span class="sxs-lookup"><span data-stu-id="85aaf-106">Manage Office deployments</span></span>

1. <span data-ttu-id="85aaf-107">Acesse o [centro de administração](https://aka.ms/bcsportal) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="85aaf-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="85aaf-p101">No cartão de **dispositivos** , escolha **Gerenciar a implantação do Office**.    Se você não conseguir ver o cartão de **ações de dispositivo** , em que a página **inicial** do Centro de administração, clique em **Adicionar** (+) para adicioná-lo à sua casa admin.</span><span class="sxs-lookup"><span data-stu-id="85aaf-p101">On the **Devices** card, choose **Manage Office Deployment**.    If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="85aaf-111">No painel **Gerenciar a Implantação do Office** que é aberto, escolha **Adicionar um grupo** e, em seguida, selecione os grupos que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="85aaf-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="85aaf-112">Depois de ter adicionado o grupo ou os grupos que você deseja usar, no menu suspenso **Ação de Implantação**, selecione **Instalar o Office assim que possível** ou **Desinstalar o Office**.</span><span class="sxs-lookup"><span data-stu-id="85aaf-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="85aaf-114">Escolha **Próxima** \> Examinar as configurações e, em seguida, escolha **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="85aaf-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="85aaf-115">Um Office de 32 bits será automaticamente instalado ou desinstalado nos dispositivos pertencentes a usuários especificados pelo grupo ou grupos que você usou.</span><span class="sxs-lookup"><span data-stu-id="85aaf-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="85aaf-116">Para verificar, você pode abrir o Gerenciador de Tarefas em um computador que foi selecionado para uma instalação do Office e procurar o processo de Clique para Executar do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="85aaf-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


