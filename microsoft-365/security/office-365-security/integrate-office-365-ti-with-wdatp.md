---
title: Usar o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender para Ponto de Extremidade
f1.keywords:
- NOCSH
keywords: integrar, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender for Endpoint para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166082"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft Defender para Office 365](office-365-atp.md) pode ser configurado para funcionar com [o Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection)

A integração do Microsoft Defender for Office 365 com o Microsoft Defender for Endpoint pode ajudar a equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco. Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para o Ponto de Extremidade.

A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:

![Quando o Microsoft Defender para Ponto de Extremidade está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página na Central de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Saiba mais sobre a Central de Segurança do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também conhecida como portal de ponto de extremidade do Microsoft Defender).

## <a name="requirements"></a>Requisitos

- Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para o Ponto de Extremidade.

- Você deve ser um administrador global ou ter uma função de administrador de segurança (como o Administrador de Segurança) atribuída no Centro de [& Conformidade](https://protection.office.com)e Segurança. (Consulte [Permissões no Centro de Conformidade e & Segurança)](permissions-in-the-security-and-compliance-center.md)

- Você deve ter acesso ao [Explorer (ou](threat-explorer.md) detecções em tempo real) no Centro de Conformidade & segurança e na Central de Segurança do Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade

A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade é configurada usando o Centro de Conformidade e & Segurança e a Central de Segurança do Microsoft Defender.

1. Como administrador global ou administrador de segurança, acesse <https://protection.office.com> e entre. (Isso leva você ao Centro de Conformidade e Segurança & do Office 365.)

2. No painel de navegação, escolha Explorador **de gerenciamento de** \> **ameaças.**

   ![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)

3. No canto superior direito da tela, escolha Defender para Configurações de Ponto de Extremidade **(Configurações MDE).**

4. Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a ligue **Conectar-se ao Microsoft Defender para Ponto de Extremidade.**

   ![Conexão do Microsoft Defender para Ponto de Extremidade](../../media/Explorer-WDATPConnection-dialog.png)

5. Vá para a Central de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).

6. Na barra de navegação, escolha **Configurações.** Em seguida, em **Geral,** escolha **Recursos avançados.**

7. Role para baixo até a conexão de Inteligência contra Ameaças do **Office 365** e a ligue.

   ![Conexão de inteligência contra ameaças do Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta a ameaças no Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](office-365-atp.md)

[Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection)
