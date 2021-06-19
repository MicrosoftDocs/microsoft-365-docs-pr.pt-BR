---
title: Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade
f1.keywords:
- NOCSH
keywords: integre, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft Defender para Office 365 com o Microsoft Defender para Endpoint para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028866"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft Defender para Office 365](defender-for-office-365.md) pode ser configurado para trabalhar com o Microsoft Defender para Ponto de [Extremidade](/windows/security/threat-protection).

A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco. Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos que são potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para Endpoint.

A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:

![Quando o Microsoft Defender for Endpoint está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página em [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente o Central de Segurança do Microsoft Defender).

> [!TIP]
> O Microsoft 365 Defender portal substitui o Central de Segurança do Microsoft Defender. Consulte [Microsoft Defender for Endpoint no Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requirements

- Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para Ponto de Extremidade.

- Você deve ser um administrador global ou ter uma função de administrador de segurança (como Administrador de Segurança) atribuída Microsoft 365. (Consulte [Permissões no Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))

- Você deve ter acesso ao [Explorer (ou detecções em tempo real)](threat-explorer.md).

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade

A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint está configurada no Defender para Ponto de Extremidade e no Defender para Office 365.

1. Como administrador global ou administrador de segurança, acesse [https://security.microsoft.com](https://security.microsoft.com) e entre. (Isso o leva ao portal Microsoft 365 Defender.)

2. No painel de navegação, escolha **Email & colaboração** \> **Explorer**.

3. No canto superior direito da tela, clique em **MDE Configurações**.

4. Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a Conexão **para o Microsoft Defender para Ponto de Extremidade**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexão MDE":::

5. Vá para o Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) .

6. Na barra de navegação, escolha **Configurações**. Em **Geral,** escolha **Recursos avançados.**

7. Role para baixo **Office 365 conexão de Inteligência contra Ameaças** e a ligue.

   ![Office 365 de inteligência contra ameaças](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta contra ameaças Office 365](office-365-ti.md)

[Obter o Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection)
