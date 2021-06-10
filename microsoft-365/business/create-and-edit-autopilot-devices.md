---
title: Criar e editar os dispositivos do AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Saiba como carregar dispositivos usando o AutoPilot Microsoft 365 Business Premium. Você pode atribuir um perfil a um dispositivo ou a um grupo de dispositivos.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578478"
---
# <a name="create-and-edit-autopilot-devices"></a>Crie e edite os dispositivos do AutoPilot

## <a name="upload-a-list-of-devices"></a>Carregar uma lista de dispositivos

Você pode usar o [guia Passo a](add-autopilot-devices-and-profile.md) passo para carregar dispositivos, mas também pode carregar dispositivos na guia **Dispositivos.** 
  
Os dispositivos devem atender a esses requisitos:
  
- Windows 10, versão 1703 ou posterior
    
- Novos dispositivos que não passaram por Windows experiência completa

1. No centro Microsoft 365 de administração, escolha **Dispositivos** \> **AutoPilot**.
  
2. Na página **Piloto Automático,** escolha a guia **Dispositivos** \> **Adicionar dispositivos**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. No painel **Adicionar dispositivos,** navegue até um arquivo [CSV](../admin/misc/device-list.md) da lista de dispositivos que você preparou \> **Salvar** \> **Fechar**.
    
    Você pode obter essas informações do fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Atribuir um perfil a um dispositivo ou a um grupo de dispositivos

1. Na página **Preparar Windows,** escolha a guia **Dispositivos** e marque a caixa de seleção ao lado de um ou mais dispositivos. 
    
2. No painel **Dispositivo**, selecione um perfil do menu suspenso **Perfil atribuído**. 
    
    Se você ainda não tem perfis, confira [Criar e editar perfis do AutoPilot](create-and-edit-autopilot-profiles.md) para obter instruções. 
