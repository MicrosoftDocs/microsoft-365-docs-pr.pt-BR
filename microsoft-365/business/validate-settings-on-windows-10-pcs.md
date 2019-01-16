---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
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
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar configurações de proteção do aplicativo Microsoft 365 Business em dispositivos Windows 10.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864846"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar configurações de proteção de dispositivo em PCs de 10 do Windows

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificar se as políticas de dispositivo do Windows 10 estão definidas

Após você [Configurar políticas de dispositivos](protection-settings-for-windows-10-pcs.md), ele pode demorar algumas horas para a política entrem em vigor em dispositivos dos usuários. Você pode confirmar que as políticas está em vigor examinando várias telas de configurações do Windows em dispositivos dos usuários. Porque os usuários não poderão modificar as configurações do Windows Update e Windows Defender antivírus em seus dispositivos Windows 10, muitas dessas opções serão esmaecida.
  
1. Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **reiniciar as opções** e confirme que todas as configurações estão em cinza. 
    
    ![Todas as opções de reinicialização ficam cinza.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **Opções avançadas** e confirme que todas as configurações estão em cinza. 
    
    ![Opções de atualizações do Windows Advanced todos esmaecidas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vá para **configurações** \> **atualização &amp; segurança** \> **Windows Update** \> **Opções avançadas** \> **escolher como as atualizações são entregues**.
    
    Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estiverem ocultas ou gerenciadas por sua organização, e todas as opções ficam cinza.
    
    ![Escolher como as atualizações são entregues página indica as configurações estiverem ocultas ou gerenciadas por sua organização.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir a Central de segurança do Windows Defender, vá para **configurações** \> **atualização &amp; segurança** \> **Windows Defender** \> clique em **Abrir Windows Defender Security Center** \> **vírus &amp; thread proteção** \> **vírus &amp; configurações de proteção de ameaça**. 
    
5. Verifique se todas as opções são esmaecidas. 
    
    ![As configurações de proteção de vírus e ameaças ficam cinza.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Documentação e recursos do Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introdução ao Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Gerenciar o Microsoft 365 Business](manage.md)
  
[Definir configurações de dispositivo para computadores Windows 10](protection-settings-for-windows-10-pcs.md)
  

