---
title: Solucionar problemas de integração de ferramentas SIEM no Microsoft Defender ATP
description: Solucionar problemas que podem surgir ao usar ferramentas SIEM com o Microsoft Defender ATP.
keywords: solução de problemas, siem, segredo do cliente, segredo
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053543"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>Solucionar problemas de integração de ferramentas SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Talvez seja necessário solucionar problemas ao puxar detecções em suas ferramentas SIEM.

Esta página fornece etapas detalhadas para solucionar problemas que você pode encontrar.


## <a name="learn-how-to-get-a-new-client-secret"></a>Saiba como obter um novo segredo do cliente
Se o segredo do cliente expirar ou se você tiver perdido a cópia fornecida quando estava habilitando o aplicativo de ferramenta SIEM, você precisará obter um novo segredo.

1. Faça logon no [portal de gerenciamento do Azure.](https://portal.azure.com)

2. Selecione **Azure Active Directory**.

3. Selecione seu locatário.

4. Clique **em Registros de aplicativo.** Em seguida, na lista aplicativos, selecione o aplicativo.

5. Selecione **a seção** Chaves e forneça uma descrição de chave e especifique a duração da validade da chave.

6. Clique em **Salvar**. O valor da chave é exibido.

7. Copie o valor e salve-o em um local seguro.


## <a name="error-when-getting-a-refresh-access-token"></a>Erro ao obter um token de acesso de atualização
Se você encontrar um erro ao tentar obter um token de atualização ao usar a API de inteligência de ameaça ou as ferramentas SIEM, você precisará adicionar a URL de resposta para o aplicativo relevante no Azure Active Directory.

1. Faça logon no [portal de gerenciamento do Azure.](https://ms.portal.azure.com)

2. Selecione **Azure Active Directory**.

3. Selecione seu locatário.

4. Clique **em Registros de Aplicativos**. Em seguida, na lista aplicativos, selecione o aplicativo.

5. Adicione a seguinte URL:
   - Para a União Europeia: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - Para o Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - Para os Estados Unidos:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .
 
6. Clique em **Salvar**.

## <a name="error-while-enabling-the-siem-connector-application"></a>Erro ao habiltar o aplicativo de conector SIEM
Se você encontrar um erro ao tentar habilitar o aplicativo de conector SIEM, verifique as configurações do bloqueador pop-up do navegador. Ele pode estar bloqueando a nova janela que está sendo aberta quando você habilita o recurso.




>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>Tópicos relacionados
- [Habilitar a integração do SIEM no Microsoft Defender para Endpoint](enable-siem-integration.md)
- [Configurar ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade](configure-arcsight.md)
- [Pull detections to your SIEM tools](configure-siem.md)
- [Campos de Detecção de Ponto de Extremidade do Microsoft Defender](api-portal-mapping.md)
- [Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST](pull-alerts-using-rest-api.md)
