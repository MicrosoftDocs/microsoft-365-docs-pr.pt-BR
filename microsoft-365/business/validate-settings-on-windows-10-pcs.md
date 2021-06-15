---
title: Validar configurações de proteção de aplicativo para Windows 10 PCs
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Saiba como verificar se as configurações Microsoft 365 de proteção de aplicativos comerciais entrou em vigor nos dispositivos Windows 10 dos usuários.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925250"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Validar configurações de proteção de dispositivo para Windows 10 PCs

## <a name="verify-that-windows-10-device-policies-are-set"></a>Verifique se as Windows 10 de dispositivo estão definidas

Depois de [configurar políticas de](protection-settings-for-windows-10-pcs.md)dispositivos, pode levar até algumas horas para que a política entre em vigor nos dispositivos dos usuários. Você pode confirmar se as políticas foram efetivadas analisando várias Windows Configurações nos dispositivos dos usuários. Como os usuários não poderão modificar as configurações Windows Update e Windows Defender Antivírus em seus dispositivos Windows 10, muitas opções serão acinzentados.
  
1. Vá para **Configurações** Atualizar Windows Opções de Reinicialização de Atualização e confirme se todas as \> **&amp;** \>  \>  configurações estão acinzenadas. 
    
    ![Todas as opções reiniciar estão acinzenadas.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Vá para **Configurações** Atualizar Windows Atualizar Opções Avançadas e confirme se todas as \> **&amp;** \>  \>  configurações estão acinzenadas. 
    
    ![Windows As opções de atualizações avançadas estão todas acinzenadas.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Vá para **Configurações** Atualizar \> **&amp; Windows** \> **Opções** Avançadas De atualização Escolha como \>  \> **as atualizações são entregues.**
    
    Confirme se você pode ver a mensagem (em vermelho) de que algumas configurações estão ocultas ou gerenciadas por sua organização, e todas as opções estão acinzenadas.
    
    ![Escolha como as atualizações são entregues página indica que as configurações estão ocultas ou gerenciadas pela sua organização.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Para abrir Windows Defender Central de Segurança, vá Configurações Atualização de segurança Windows Defender clique em  \> **&amp;** \>  \> **Abrir** \> **&amp;** \> **&amp;** Windows Defender Proteção contra vírus do Centro de Segurança. 
    
5. Verifique se todas as opções estão acinzenadas. 
    
    ![As configurações de proteção contra vírus e ameaças estão acinzenadas.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Microsoft 365 para recursos e documentação de negócios](./index.yml)
  
[Começar com o Microsoft 365 para empresas](microsoft-365-business-overview.md)
  
[Gerenciar Microsoft 365 para empresas](manage.md)
  
[Definir configurações de dispositivo para computadores Windows 10](protection-settings-for-windows-10-pcs.md)
