---
title: Proteger dispositivos Windows 10
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Saiba mais sobre como configurar as configurações da política de dispositivo padrão que qualquer dispositivo Windows 10 receberá ao entrar em sua conta de trabalho ou de estudante.
ms.openlocfilehash: 86db1c152f9f6ac1fe6093b4a55a74b69fbd8b0f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579965"
---
# <a name="secure-windows-10-devices"></a>Proteger dispositivos Windows 10

Este artigo se aplica a Microsoft 365 Business Premium.

As configurações que você define aqui fazem parte da política de dispositivo padrão para Windows 10. Todos os usuários que conectam um Windows 10, incluindo dispositivos móveis e PCs, ao entrar com sua conta de trabalho receberão automaticamente essas configurações. Recomendamos aceitar a política padrão durante a instalação e, mais tarde, adicionar políticas destinadas a grupos de usuários específicos.
  
## <a name="settings-to-secure-windows-10-devices"></a>Configurações para proteger dispositivos Windows 10

Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis:
  
|||
|:-----|:-----|
|Configuração  <br/> |Descrição  <br/> |
|Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus  <br/> |Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.  <br/> |
|Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge  <br/> |Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.  <br/> |
|Ajudar a proteger os arquivos e pastas em computadores contra acesso não autorizado com o BitLocker  <br/> |O BitLocker protege os dados por meio da criptografia das unidades de disco do computador e da proteção contra exposição de dados caso um computador seja perdido ou roubado. Para obter mais informações, consulte [Perguntas frequentes do Bitlocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Desligar a tela do dispositivo quando ele ficar ocioso durante este período  <br/> |Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.  <br/> |
|