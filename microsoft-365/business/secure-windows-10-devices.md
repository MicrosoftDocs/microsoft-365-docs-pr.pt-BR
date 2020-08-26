---
title: Proteger dispositivos Windows 10
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
description: Saiba mais sobre como definir as configurações da política de dispositivo padrão que qualquer dispositivo Windows 10 receberá ao entrar em sua conta corporativa ou de estudante.
ms.openlocfilehash: b586e687d6b61873b77fac8586396ab51fd90b9b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898059"
---
# <a name="secure-windows-10-devices"></a>Proteger dispositivos Windows 10

Este artigo se aplica ao Microsoft 365 Business Premium.

As configurações que você define aqui fazem parte da política de dispositivo padrão para Windows 10. Todos os usuários que conectam um dispositivo Windows 10, incluindo dispositivos móveis e computadores, ao entrar com a conta de trabalho receberão automaticamente essas configurações. Recomendamos aceitar a política padrão durante a instalação e, mais tarde, adicionar políticas destinadas a grupos de usuários específicos.
  
## <a name="settings-to-secure-windows-10-devices"></a>Configurações para proteger dispositivos Windows 10

Todas as configurações são **Ativadas** por padrão. As configurações a seguir estão disponíveis:
  
|||
|:-----|:-----|
|Setting  <br/> |Descrição  <br/> |
|Ajudar a proteger PCs contra vírus e outras ameaças usando o Windows Defender Antivirus  <br/> |Exige que o Windows Defender Antivírus esteja ativado para proteger computadores contra os riscos de estar conectado à Internet.  <br/> |
|Ajudar a proteger PCs contra ameaças baseadas na Web no Microsoft Edge  <br/> |Ativa as configurações do Microsoft Edge que ajudam a proteger os usuários contra sites e downloads mal-intencionados.  <br/> |
|Desligar a tela do dispositivo quando ele ficar ocioso durante este período  <br/> |Garante que os dados da empresa estejam protegidos se um usuário ficar ocioso. Um usuário pode estar trabalhando em um local público, como um café, e se distanciar ou distrair por um momento, deixando seu dispositivo vulnerável a olhares aleatórios. Essa configuração permite que você controle quanto tempo o usuário pode ficar ocioso antes que a tela seja desligada.  <br/> |
|Permitir que os usuários baixem aplicativos da Microsoft Store  <br/> |Permite aos usuários baixar e instalar os aplicativos da Microsoft Store. Aplicativos incluem desde jogos a ferramentas de produtividade, portanto, deixamos essa configuração **Ativada**, mas você pode desativá-la para obter mais segurança.  <br/> |
|