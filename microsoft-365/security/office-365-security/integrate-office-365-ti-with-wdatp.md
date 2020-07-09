---
title: Integrar o ATP do Office 365 com o ATP do Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086700"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender

A [proteção avançada contra ameaças do office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) pode ser configurada para funcionar com a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft defender ATP).

Integrar o Office 365 ATP com o Microsoft defender ATP pode ajudar sua equipe de operações de segurança a monitorar e tomar ações rapidamente se os dispositivos dos usuários estiverem em risco. Por exemplo, depois que a integração estiver habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes esses dispositivos têm no Microsoft defender ATP. 

A imagem a seguir representa a aparência da guia **dispositivos** como a integração do Microsoft defender ATP está habilitada:
  
![Quando o Microsoft defender ATP estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
Neste exemplo, você pode ver que os destinatários da mensagem de email detectado têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página no centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Saiba mais sobre o centro de segurança do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também mencionado como o portal ATP do Microsoft defender).
  
## <a name="requirements"></a>Requirements

- Sua organização deve ter o Office 365 ATP Plan 2 (ou o Office 365 E5) e o Microsoft defender ATP.
    
- Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com). (Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))
    
- Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Para integrar o Office 365 ATP com o Microsoft defender ATP

A integração do Office 365 ATP com o Microsoft defender ATP é configurada usando o centro de conformidade & segurança e o centro de segurança do Microsoft defender.
  
1. Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre. (Isso leva você para o centro de conformidade & segurança do Office 365.)
    
2. No painel de navegação, escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer**.<br>![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. No canto superior direito da tela, escolha configurações de **WDATP**.
    
4. Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.<br>![Conexão ATP do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Vá para o centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Na barra de navegação, escolha **configurações**. Em seguida, em **geral**, escolha **recursos avançados**.

7. Role para baixo até a **conexão do Office 365 Threat Intelligence**e ative a conexão.<br/>![Conexão do Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta contra ameaças no Office 365](office-365-ti.md)
  
[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
  
[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection)
