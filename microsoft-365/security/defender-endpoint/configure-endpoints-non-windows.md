---
title: Integração de dispositivos que não Windows para o serviço do Microsoft Defender para Ponto de Extremidade
description: Configure dispositivos não Windows para que eles possam enviar dados do sensor para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: integração de dispositivos Windows, macos, linux, gerenciamento de dispositivos, configurar o Microsoft Defender para dispositivos de ponto de extremidade
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
ms.openlocfilehash: 265a7e9093638caa2111c7d1d82e51c8c2437d12
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845451"
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

O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para Windows, bem como plataformas que não Windows. Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Central de Segurança do Microsoft Defender e proteger melhor a rede da sua organização. 

Você precisará saber as versões exatas do Linux e macOS compatíveis com o Defender para o Ponto de Extremidade para que a integração funcione. Para saber mais, confira:
- [Microsoft Defender para Ponto de Extremidade em requisitos do sistema Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender para Ponto de Extremidade em requisitos do sistema macOS.](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>Integrando dispositivos que não Windows de segurança
Você precisará seguir as seguintes etapas para a integração de dispositivos que não Windows:
1. Selecione seu método preferencial de integração:

   - Para dispositivos macOS, você pode optar por integração por meio do Microsoft Defender para Ponto de Extremidade ou por meio de uma solução de terceiros. Para obter mais informações, consulte [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).

   - Para outros dispositivos que não Windows escolha Integrar dispositivos que não Windows por meio da **integração de terceiros.**   
    1. No painel de navegação, selecione **Parceiros de**  >  **Interoperabilidade**. Certifique-se de que a solução de terceiros está listada.
    2. Na guia **Aplicativos parceiros,** selecione o parceiro que oferece suporte aos dispositivos que não Windows.
    3. Selecione **Abrir página do parceiro** para abrir a página do parceiro. Siga as instruções fornecidas na página.
    4. Depois de criar uma conta ou assinar a solução de parceiro, você deve chegar a um estágio em que um administrador global de locatários em sua organização é solicitado a aceitar uma solicitação de permissão do aplicativo parceiro. Leia a solicitação de permissão cuidadosamente para garantir que ela esteja alinhada com o serviço necessário. 

        
2. Execute um teste de detecção seguindo as instruções da solução de terceiros.

## <a name="offboard-non-windows-devices"></a>Dispositivos que não Windows offboard

1. Siga a documentação de terceiros para desconectar a solução de terceiros do Microsoft Defender para o Ponto de Extremidade.

2. Remova permissões para a solução de terceiros no locatário do Azure AD.
   1. Entre no [portal do Azure](https://portal.azure.com).
   2. Selecione **Azure Active Directory > Enterprise Aplicativos**.
   3. Selecione o aplicativo que você gostaria de fazer offboard.
   4. Selecione o **botão Excluir.**


## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos integrados do Windows 10](configure-endpoints.md)
- [Servidores de integração](configure-server-endpoints.md)
- [Definir as configurações de proxy e conectividade com a Internet](configure-proxy-internet.md)
- [Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade](troubleshoot-onboarding.md)
