---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como verificar se as configurações do Microsoft 365 for Business app Protection foram efetivadas nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: b63681f040b0fe49127693e9cb7aac7ba6c41af6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635695"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar configurações de proteção do dispositivo em computadores com Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificar se as políticas de dispositivo do Windows 10 estão definidas

Depois de [configurar as políticas de dispositivos](protection-settings-for-windows-10-pcs.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Você pode confirmar que as políticas tomaram efeito examinando várias telas de configurações do Windows nos dispositivos dos usuários. Como os usuários não poderão modificar as configurações do Windows Update Antivirus e do Windows Defender em seus dispositivos Windows 10, muitas opções serão acinzentadas.
  
1. Vá para **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções de reinicialização** e confirme se todas as configurações estão acinzentadas. 
    
    ![Todas as opções de reinicialização ficam esmaecidas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vá para **configurações** \> **avançadas** de **atualização &amp; de segurança** \> do **Windows Update** \> e confirme se todas as configurações estão acinzentadas. 
    
    ![As opções avançadas do Windows estão esmaecidas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vá até **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções** \> avançadas **escolha como as atualizações são entregues**.
    
    Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estão ocultas ou gerenciadas pela sua organização, e todas as opções estão acinzentadas.
    
    ![Escolha a página como as atualizações são entregues indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir a central de segurança do Windows Defender, vá para **configurações** \> de segurança \> de ** &amp; atualização** do **Windows Defender** \> clique em **abrir a central** \> ** &amp; ** de segurança do Windows Defender proteção \> contra ** &amp; ameaças**de vírus. 
    
5. Verifique se todas as opções estão acinzentadas. 
    
    ![As configurações de proteção contra vírus e ameaças são esmaecidas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Documentação e recursos do Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introdução ao Microsoft 365 for Business](microsoft-365-business-overview.md)
  
[Gerenciar o Microsoft 365 para empresas](manage.md)
  
[Definir configurações de dispositivo para computadores Windows 10](protection-settings-for-windows-10-pcs.md)
  

