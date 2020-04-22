---
title: Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender para ver informações mais detalhadas sobre o gerenciamento de ameaças.
ms.openlocfilehash: e416d70baf7498b0163d5bd8aa8e923585a5e5a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633804"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender

Se você fizer parte da equipe de segurança da sua organização, poderá integrar a [proteção avançada contra ameaças do Office 365](office-365-atp.md) e os recursos de investigação e resposta relacionados à [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). Isso pode ajudá-lo a entender rapidamente se as máquinas dos usuários estão em risco quando você está investigando ameaças no Office 365. Por exemplo, depois que a integração estiver habilitada, você poderá ver uma lista de máquinas que são usadas pelos destinatários de uma mensagem de email detectada, bem como os alertas recentes que essas máquinas têm na proteção avançada contra ameaças do Microsoft defender.
  
A imagem a seguir mostra a guia **dispositivos** que você verá quando tiver a integração do Microsoft defender ATP habilitada:
  
![Quando o Microsoft defender ATP estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
Neste exemplo, você pode ver que os destinatários da mensagem de email têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página na central de segurança do Microsoft defender.
  
## <a name="requirements"></a>Requirements

- Sua organização deve ter o Office 365 ATP Plan 2 (ou o Office 365 E5) e o Microsoft defender ATP.
    
- Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com). (Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))
    
- Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Para integrar o Office 365 ATP com o Microsoft defender ATP

A integração do Office 365 ATP com o Microsoft defender ATP é configurada usando o centro de conformidade & segurança e o centro de segurança do Microsoft defender.
  
1. Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.
    
2. Escolha **Threat management** \> **Gerenciador**de gerenciamento de ameaças.<br>![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. No canto superior direito da tela, escolha configurações de **WDATP**.
    
4. Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.<br>![Conexão ATP do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Habilite a conexão no centro de segurança do Microsoft[https://securitycenter.windows.com](https://securitycenter.windows.com)defender ().

## <a name="related-topics"></a>Tópicos relacionados

[Recursos de investigação e resposta contra ameaças no Office 365](office-365-ti.md)
  
[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
  

