---
title: Integração de dispositivos que não são windows ao serviço microsoft defender para ponto de extremidade
description: Configure dispositivos que não são do Windows para que eles possam enviar dados do sensor para o serviço microsoft Defender ATP.
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
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166072"
---
# <a name="onboard-non-windows-devices"></a>Integração de dispositivos que não são windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas**
- macOS
- Linux

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para o Windows, bem como para plataformas que não são do Windows. Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Centro de Segurança do Microsoft Defender e proteger melhor a rede da sua organização. 

Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione. Para mais informações, confira:
- [Microsoft Defender for Endpoint for Linux system requirements](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Integrando dispositivos que não são windows
Você precisará seguir as etapas a seguir para a integração de dispositivos que não são windows:
1. Selecione seu método preferencial de integração:

   - Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender ATP ou por meio de uma solução de terceiros. Para obter mais informações, consulte [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).
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
- [Integração de dispositivos Windows 10](configure-endpoints.md)
- [Servidores de integração](configure-server-endpoints.md)
- [Configurar configurações de conectividade de proxy e Internet](configure-proxy-internet.md)
- [Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade](troubleshoot-onboarding.md)
