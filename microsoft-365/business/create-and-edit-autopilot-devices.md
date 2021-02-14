---
title: Criar e editar os dispositivos do AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o AutoPilot no Microsoft 365 Business Premium. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400985"
---
# <a name="create-and-edit-autopilot-devices"></a>Crie e edite os dispositivos do AutoPilot

## <a name="upload-a-list-of-devices"></a>Carregar uma lista de dispositivos

Você pode usar o [guia passo a passo](add-autopilot-devices-and-profile.md) para carregar dispositivos, mas também pode carregar dispositivos na guia **Dispositivos.** 
  
Os dispositivos devem atender a estes requisitos:
  
- Windows 10, versão 1703 ou posterior
    
- Novos dispositivos que não passaram pela configuração de configuração do Windows

1. No centro de administração do Microsoft 365, escolha **Dispositivos** \> **AutoPilot.**
  
2. Na página **AutoPilot,** escolha a guia **Dispositivos** \> **Adicionar dispositivos.**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. No painel **Adicionar dispositivos,** navegue até um arquivo [CSV de](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) lista de dispositivos que você \> **preparou salvar** \> **fechar.**
    
    Você pode obter essas informações do fornecedor de hardware ou usar o [script Get-WindowsAutoPilotInfo powerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Atribuir um perfil a um dispositivo ou a um grupo de dispositivos

1. Na página **Preparar o Windows,** escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos. 
    
2. No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**. 
    
    Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções. 
    
