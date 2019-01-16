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
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865107"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Instalar ou desinstalar o Office em dispositivos Windows 10 automaticamente

Você pode instalar com rapidez e facilidade o Office para computadores com o Windows 10 pelo centro de administração do Microsoft 365 Business.
  
Para entender como isso funciona com os aplicativos do Office instalados anteriormente, leia [Preparar-se para a instalação do cliente do Office](prepare-for-office-client-deployment.md) antes de começar. 
  
## <a name="manage-office-deployments"></a>Gerenciar as implantações do Office

1. Acesse o [centro de administração](https://aka.ms/bcsportal) com credenciais de administrador global. 
    
2. No cartão de **dispositivos** , escolha **Gerenciar a implantação do Office**.    Se você não conseguir ver o cartão de **ações de dispositivo** , em que a página **inicial** do Centro de administração, clique em **Adicionar** (+) para adicioná-lo à sua casa admin.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. No painel **Gerenciar a Implantação do Office** que é aberto, escolha **Adicionar um grupo** e, em seguida, selecione os grupos que você deseja usar.
    
4. Depois de ter adicionado o grupo ou os grupos que você deseja usar, no menu suspenso **Ação de Implantação**, selecione **Instalar o Office assim que possível** ou **Desinstalar o Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Escolha **Próxima** \> Examinar as configurações e, em seguida, escolha **Confirmar**.
    
Um Office de 32 bits será automaticamente instalado ou desinstalado nos dispositivos pertencentes a usuários especificados pelo grupo ou grupos que você usou.
  
Para verificar, você pode abrir o Gerenciador de Tarefas em um computador que foi selecionado para uma instalação do Office e procurar o processo de Clique para Executar do Microsoft Office.
  


