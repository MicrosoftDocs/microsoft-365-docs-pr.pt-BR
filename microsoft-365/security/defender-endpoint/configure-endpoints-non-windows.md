---
title: Integração de dispositivos que não são windows ao serviço microsoft defender para ponto de extremidade
description: Configure dispositivos que não são windows para que eles possam enviar dados do sensor para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: integração de dispositivos que não são windows, macos, linux, gerenciamento de dispositivos, configurar dispositivos Windows ATP, configurar o Microsoft Defender para dispositivos de ponto de extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c78779cd4a8a329864b6ac7e0debfc30ca0b3a56
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893584"
---
# <a name="onboard-non-windows-devices"></a>Dispositivos Windows não integrados

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para o Windows, bem como para plataformas que não são do Windows. Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Centro de Segurança do Microsoft Defender e proteger melhor a rede da sua organização. 

Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione. Para saber mais, confira:
- [Microsoft Defender para Ponto de Extremidade em requisitos do sistema Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender para Ponto de Extremidade em requisitos do sistema macOS.](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>Integrando dispositivos que não são windows
Você precisará seguir as etapas a seguir para a integração de dispositivos que não são windows:
1. Selecione seu método preferencial de integração:

   - Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender para Ponto de Extremidade ou por meio de uma solução de terceiros. Para obter mais informações, consulte [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).

   - Para outros dispositivos que não são do Windows, escolha **Integrar dispositivos que não são do Windows por meio da integração de terceiros.**   
    1. No painel de navegação, selecione **Parceiros de**  >  **Interoperabilidade**. Certifique-se de que a solução de terceiros está listada.
    2. Na guia **Aplicativos Parceiros,** selecione o parceiro que oferece suporte a seus dispositivos que não são windows.
    3. Selecione **Abrir página do parceiro** para abrir a página do parceiro. Siga as instruções fornecidas na página.
    4. Depois de criar uma conta ou assinar a solução de parceiro, você deve chegar a um estágio em que um administrador global de locatários em sua organização é solicitado a aceitar uma solicitação de permissão do aplicativo parceiro. Leia a solicitação de permissão cuidadosamente para garantir que ela esteja alinhada com o serviço necessário. 

        
2. Execute um teste de detecção seguindo as instruções da solução de terceiros.

## <a name="offboard-non-windows-devices"></a>Offboard de dispositivos que não são windows

1. Siga a documentação de terceiros para desconectar a solução de terceiros do Microsoft Defender para o Ponto de Extremidade.

2. Remova permissões para a solução de terceiros no locatário do Azure AD.
   1. Entre no [portal do Azure](https://portal.azure.com).
   2. Selecione Aplicativos Corporativos **do Azure Active Directory >**.
   3. Selecione o aplicativo que você gostaria de fazer offboard.
   4. Selecione o **botão Excluir.**


## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos integrados do Windows 10](configure-endpoints.md)
- [Servidores de integração](configure-server-endpoints.md)
- [Definir as configurações de proxy e conectividade com a Internet](configure-proxy-internet.md)
- [Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade](troubleshoot-onboarding.md)
