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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business Premium. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: f2a7f801ae471352595a36b355a874b2de653326
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627385"
---
# <a name="create-and-edit-autopilot-devices"></a>Crie e edite os dispositivos do AutoPilot

## <a name="upload-a-list-of-devices"></a>Carregar uma lista de dispositivos

Você pode usar o [guia](add-autopilot-devices-and-profile.md) passo a passo para carregar dispositivos, mas você também pode carregar dispositivos na guia **dispositivos** . 
  
Os dispositivos devem atender a estes requisitos:
  
- Windows 10, versão 1703 ou posterior
    
- Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows

1. No centro de administração do Microsoft 365, escolha **dispositivos** \> **AutoPilot**.
  
2. Na página **piloto automático** \> , escolha a guia **dispositivos** **Adicionar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. No painel **Adicionar dispositivos** , navegue até um [arquivo CSV de lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **salvar** \> **fechar**.
    
    Você pode obter essas informações do seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Atribuir um perfil a um dispositivo ou a um grupo de dispositivos

1. Na página **preparar o Windows** , escolha a guia **dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos. 
    
2. No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**. 
    
    Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções. 
    
