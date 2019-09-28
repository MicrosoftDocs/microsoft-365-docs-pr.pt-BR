---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar as configurações de proteção do Microsoft 365 Business app em dispositivos Windows 10.
ms.openlocfilehash: 66e83df19e44419b37bcc1c5678ab13317162dbc
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288586"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar configurações de proteção do dispositivo em computadores com Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificar se as políticas de dispositivo do Windows 10 estão definidas

Depois de [configurar as políticas de dispositivos](protection-settings-for-windows-10-pcs.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Você pode confirmar que as políticas tomaram efeito examinando várias telas de configurações do Windows nos dispositivos dos usuários. Como os usuários não poderão modificar as configurações de Windows Update e antivírus do Windows Defender em seus dispositivos Windows 10, muitas dessas opções ficarão acinzentadas.
  
1. Vá para **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções de reinicialização** e confirme se todas as configurações estão acinzentadas. 
    
    ![Todas as opções de reinicialização ficam acinzentadas.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vá para **configurações** \> **avançadas** de **atualização &amp; de segurança** \> do **Windows Update** \> e confirme se todas as configurações estão acinzentadas. 
    
    ![As opções avançadas do Windows estão esmaecidas.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vá até **configurações** \> **atualização &amp; de segurança** \> do **Windows Update** \> **Opções** \> avançadas **escolha como as atualizações são entregues**.
    
    Confirme que você pode ver a mensagem (em vermelho) que algumas configurações estão ocultas ou gerenciadas pela sua organização, e todas as opções estão acinzentadas.
    
    ![Escolha a página como as atualizações são entregues indica que as configurações estão ocultas ou gerenciadas pela sua organização.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir a central de segurança do Windows Defender, acesse **configurações** \> de **atualização &amp; de segurança** **** \> \> Windows Defender clique em abrir o thread de \> vírus **** ** &amp; da central de segurança do Windows Defender ** \> **configurações de &amp; proteção contra ameaças de vírus**de proteção. 
    
5. Verifique se todas as opções estão acinzentadas. 
    
    ![As configurações de proteção contra vírus e ameaças estão acinzentadas.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Documentação e recursos do Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Introdução ao Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Gerenciar o Microsoft 365 Business](manage.md)
  
[Definir configurações de dispositivo para computadores Windows 10](protection-settings-for-windows-10-pcs.md)
  

