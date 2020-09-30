---
title: Usar o Microsoft defender para Office 365 junto com o Microsoft defender para ponto de extremidade
f1.keywords:
- NOCSH
keywords: integrar, Microsoft defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft defender para Office 365 junto com a proteção avançada contra ameaças do Microsoft defender para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309232"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a>Usar o Microsoft defender para Office 365 junto com a proteção avançada contra ameaças do Microsoft defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) pode ser configurado para trabalhar com [o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection).

A integração do Microsoft defender para Office 365 com o Microsoft defender para o ponto de extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estiverem em risco. Por exemplo, depois que a integração estiver habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft defender para ponto de extremidade. 

A imagem a seguir mostra a aparência da guia **dispositivos** para que a integração do Microsoft defender para ponto de extremidade seja habilitada:
  
![Quando o Microsoft defender para ponto de extremidade estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
Neste exemplo, você pode ver que os destinatários da mensagem de email detectado têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página no centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Saiba mais sobre o centro de segurança do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também mencionado como o portal ATP do Microsoft defender).
  
## <a name="requirements"></a>Requisitos

- Sua organização deve ter o Microsoft defender para Office 365 (ou o Office 365 E5) e o Microsoft defender para ponto de extremidade.
    
- Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com). (Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))
    
- Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar o Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade

A integração do Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade é configurada usando o centro de segurança & conformidade e a central de segurança do Microsoft defender.
  
1. Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre. (Isso leva você para o centro de conformidade & segurança do Office 365.)
    
2. No painel de navegação, escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer**.<br>![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. No canto superior direito da tela, escolha configurações de **WDATP**.
    
4. Na caixa de diálogo conexão do Microsoft defender para ponto de extremidade, ative **conectar ao Windows ATP**.<br>![Conexão de ponto de extremidade do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Vá para o centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Na barra de navegação, escolha **configurações**. Em seguida, em **geral**, escolha **recursos avançados**.

7. Role para baixo até a **conexão do Office 365 Threat Intelligence**e ative a conexão.<br/>![Conexão do Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta contra ameaças no Office 365](office-365-ti.md)
  
[Microsoft defender para Office 365](office-365-atp.md)
  
[Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection)
