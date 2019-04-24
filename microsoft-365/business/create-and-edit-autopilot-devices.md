---
title: Criar e editar os dispositivos do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277013"
---
# <a name="create-and-edit-autopilot-devices"></a>Criar e editar os dispositivos do AutoPilot

## <a name="upload-a-list-of-devices"></a>Carregar uma lista de dispositivos

Você pode usar o [Guia passo a passo](add-autopilot-devices-and-profile.md) para carregar dispositivos, mas também pode carregar na guia **Dispositivos**. 
  
Os dispositivos precisam atender a esses requisitos:
  
- Windows 10, versão 1703 ou posteriores.
    
- Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.

1. no centro de administração de negócios do 365 da Microsoft, escolha **dispositivos** \> **piloto automático** \> **adicionar**.
  
2. Na página **Preparar o Windows**, escolha a guia **Dispositivos** \> **Adicionar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. No painel **Adicionar dispositivos** , navegue até uma [lista de dispositivos CSV-arquivo](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **salvar** \> **fechar**.
    
    Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que gerará um arquivo csv. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Atribuir um perfil a um dispositivo ou a um grupo de dispositivos

1. Na página **Preparar Windows**, escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos. 
    
2. No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**. 
    
    Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções. 
    
