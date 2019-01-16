---
title: Criar e editar os dispositivos do AutoPilot
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
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Saiba como carregar dispositivos usando o piloto automático no Microsoft 365 Business. Você pode atribuir um perfil para um dispositivo ou um grupo de dispositivos.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864928"
---
# <a name="create-and-edit-autopilot-devices"></a>Criar e editar os dispositivos do AutoPilot

## <a name="upload-a-list-of-devices"></a>Carregar uma lista de dispositivos

Você pode usar o [Guia passo a passo](add-autopilot-devices-and-profile.md) para carregar dispositivos, mas também pode carregar na guia **Dispositivos**. 
  
Os dispositivos precisam atender a esses requisitos:
  
- Windows 10, versão 1703 ou posteriores.
    
- Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.
    
1. No Centro de administração do Microsoft 365 Business, escolha **Implantar o Windows com o AutoPilot** no cartão **Ações do dispositivo**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Na página **Preparar o Windows**, escolha a guia **Dispositivos** \> **Adicionar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. No painel **Adicionar dispositivos** , navegue até uma [lista de dispositivos arquivo CSV](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) que você preparou \> **Salvar** \> **Close**.
    
    Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que gerará um arquivo csv. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Atribuir um perfil a um dispositivo ou a um grupo de dispositivos

1. Na página **Preparar Windows**, escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos. 
    
2. No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**. 
    
    Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções. 
    
