---
title: Aplicativos conectados no Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Exibir aplicativos parceiros conectados que usam o protocolo OAuth 2.0 padrão para autenticar e fornecer tokens para uso com o Microsoft Defender para APIs de Ponto de Extremidade.
keywords: parceiros, aplicativos, terceiros, conexões, sentinelone, mirante, bitdefender, corrata, morphisec, paloalto, ziften, melhor móvel
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893492"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Aplicativos conectados no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Aplicativos conectados se integram à plataforma Defender para Ponto de Extremidade usando APIs. 

Os aplicativos usam o protocolo OAuth 2.0 padrão para autenticar e fornecer tokens para uso com o Microsoft Defender para APIs de Ponto de Extremidade.  Além disso, os aplicativos do Azure Active Directory (Azure AD) permitem que os administradores de locatários deem um controle explícito sobre quais APIs podem ser acessadas usando o aplicativo correspondente.
 
Você precisará seguir estas etapas [para](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) usar as APIs com o aplicativo conectado.
 
## <a name="access-the-connected-application-page"></a>Acessar a página de aplicativo conectado
No menu de navegação esquerdo, selecione **Parceiros & APIs**  >  **aplicativos AAD conectados.**

 
## <a name="view-connected-application-details"></a>Exibir detalhes do aplicativo conectado
A página Aplicativos Conectados fornece informações sobre os aplicativos do Azure AD conectados ao Microsoft Defender para Ponto de Extremidade em sua organização. Você pode revisar o uso dos aplicativos conectados: visto pela última vez, número de solicitações nas últimas 24 horas e solicitar tendências nos últimos 30 dias.

![Imagem de aplicativos conectados](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Editar, reconfigurar ou excluir um aplicativo conectado
O **link Abrir configurações do** aplicativo abre a página de gerenciamento de aplicativos do Azure AD correspondente no portal do Azure. No portal do Azure, você pode gerenciar permissões, reconfigurar ou excluir os aplicativos conectados.
