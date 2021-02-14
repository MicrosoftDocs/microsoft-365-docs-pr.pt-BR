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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como verificar se as configurações de proteção de aplicativos do Microsoft 365 para empresas entrou em vigor nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403581"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validar configurações de proteção de dispositivo em computadores com Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verificar se as políticas de dispositivo Windows 10 estão definidas

Depois de [configurar as políticas de](protection-settings-for-windows-10-pcs.md)dispositivos, pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Você pode confirmar se as políticas entrou em vigor analisando várias telas de Configurações do Windows nos dispositivos dos usuários. Como os usuários não poderão modificar as configurações do Windows Update e do Windows Defender Antivírus em seus dispositivos Windows 10, muitas opções estarão es cinza.
  
1. Vá para **as opções de Reinicialização** do Windows Update de segurança de Atualização de Configurações e confirme se todas as \> **&amp;** \>  \>  configurações estão es cinzas. 
    
    ![Todas as opções de reinicialização estão es cinza.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vá para **as opções de** segurança atualização de configurações do Windows Update Advanced e \> **&amp;** \>  \>  confirme se todas as configurações estão es cinza. 
    
    ![As opções de atualizações avançadas do Windows estão es cinza.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** Choose \> **how updates are delivered**.
    
    Confirme se você pode ver a mensagem (em vermelho) de que algumas configurações estão ocultas ou gerenciadas por sua organização e se todas as opções estão es cinza.
    
    ![Escolha como as atualizações são entregues na página indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir a Central de  Segurança do Windows Defender, vá até Segurança de Atualização de Configurações do \> **&amp;** \> **Windows Defender,** clique em Abrir Proteção contra \>  \> **&amp; vírus** \> **&amp;** da Central de Segurança do Windows Defender Configurações de proteção contra ameaças contra vírus. 
    
5. Verifique se todas as opções estão es cinzas. 
    
    ![As configurações de proteção contra vírus e ameaças estão es cinzas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Documentação e recursos do Microsoft 365 para empresas](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Começar a trabalhar com o Microsoft 365 para empresas](microsoft-365-business-overview.md)
  
[Gerenciar o Microsoft 365 para empresas](manage.md)
  
[Definir configurações de dispositivo para computadores Windows 10](protection-settings-for-windows-10-pcs.md)
  

