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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083374"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft Defender para Office 365](defender-for-office-365.md) pode ser configurado para trabalhar com o Microsoft Defender para Ponto de [Extremidade](/windows/security/threat-protection).

A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco. Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos que são potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para Endpoint.

A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:

![Quando o Microsoft Defender for Endpoint está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página no [portal Microsoft 365 Defender (anteriormente](../defender-endpoint/microsoft-defender-security-center.md) o Centro de segurança do Microsoft Defender).

> [!TIP]
> O Microsoft 365 Defender portal substitui o Central de Segurança do Microsoft Defender. Consulte [Microsoft Defender for Endpoint no Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requirements

- Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para Ponto de Extremidade.

- Você deve ser um administrador global ou ter uma função de administrador de segurança (como Administrador de Segurança) atribuída Microsoft 365. Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Você deve ter acesso ao [Explorer (ou detecções em tempo real)](threat-explorer.md).

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade

A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint está configurada no Defender para Ponto de Extremidade e no Defender para Office 365.

1. Como administrador global ou administrador de segurança, abra o portal Microsoft 365 Defender ( ) e acesse <https://security.microsoft.com> **Email & collaboration** \> **Explorer**. Para ir diretamente para a página **Explorer,** use <https://security.microsoft.com/threatexplorer> .

2. Na página **Explorer,** no canto superior direito da tela, clique em **MDE Configurações**.

3. No **flyout** de conexão do Microsoft Defender para Ponto de Extremidade que aparece, a Conexão para **o Microsoft Defender para** Ponto de Extremidade ( Ativar ) e clique em Fechar ícone ![ ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Fechar**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexão MDE":::

4. De volta ao painel de navegação, escolha **Configurações**. Na página **Configurações,** escolha **Pontos de Extremidade**

5. Na página **Pontos de Extremidade que é** aberta, escolha Recursos **avançados**.

6. Role para baixo **Office 365 conexão de Inteligência de Ameaças** e a a ligue ( Ativar ![ ](../../media/scc-toggle-on.png) ).

   Quando terminar, clique em **Salvar preferências.**

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta contra ameaças Office 365](office-365-ti.md)

[Obter o Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection)
