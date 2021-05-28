---
title: Microsoft Defender para Ponto de Extremidade para Android – Informações de privacidade
description: Controles de privacidade, como configurar configurações de política que impactam a privacidade e informações sobre os dados de diagnóstico coletados no Microsoft Defender para Ponto de Extremidade no Android.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
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
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694336"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender para Ponto de Extremidade para Android – Informações de privacidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


O Defender para Ponto de Extremidade no Android coleta informações de seus dispositivos Android configurados e o armazena no mesmo locatário onde você tem o Defender para Ponto de Extremidade. As informações são coletadas para ajudar a manter o Defender for Endpoint para Android seguro, atualizado, executando conforme o esperado e para dar suporte ao serviço.

Para obter mais informações sobre armazenamento de dados, consulte [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

As informações são coletadas para ajudar a manter o Defender for Endpoint para Android seguro, atualizado, executando conforme esperado e para dar suporte ao serviço.

Para obter mais informações sobre as perguntas de privacidade mais comuns sobre o Microsoft Defender para Ponto de Extremidade em dispositivos móveis Android e iOS, consulte Microsoft Defender for Endpoint e sua privacidade em dispositivos móveis Android e [iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)

## <a name="required-data"></a>Dados Necessários 

Os dados necessários consistem em dados necessários para que o Defender for Endpoint para Android funcione conforme esperado. Esses dados são essenciais para a operação do serviço e podem incluir dados relacionados ao usuário final, organização, dispositivo e aplicativos. Aqui está uma lista dos tipos de dados que estão sendo coletados:

### <a name="app-information"></a>Informações do aplicativo

Informações sobre **pacotes de** aplicativos Android mal-intencionados (APKs) no dispositivo, incluindo

-  Instalar origem
-  Armazenamento local (caminho do arquivo) do APK
-  Hora da instalação, tamanho do APK e permissões

### <a name="web-page--network-information"></a>Página da Web / Informações de rede

- URL completa do site somente quando uma conexão mal-intencionada ou página da Web é detectada.
- Informações de conexão
- Tipo de protocolo (como HTTP, HTTPS, etc.)


### <a name="device-and-account-information"></a>Informações de dispositivo e conta

- Informações do dispositivo, como data & hora, versão do Android, modelo OEM, informações da CPU e identificador de dispositivo
- O identificador de dispositivo é um dos abaixo:
    - Wi-Fi mac adaptador
    - [ID do Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (conforme gerado pelo Android no momento da primeira inicialização do dispositivo)
    - Identificador global exclusivo gerado aleatoriamente (GUID)

- Informações de locatário, dispositivo e usuário
    -   Azure Active Directory (AD) ID do Dispositivo e ID do Usuário do Azure: identifica exclusivamente o dispositivo, Usuário, respectivamente, no diretório do Azure Active.

    -   ID do locatário do Azure - GUID que identifica sua organização dentro Azure Active Directory

    -   ID da organização do Microsoft Defender for Endpoint - Identificador exclusivo associado à empresa à que o dispositivo pertence. Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de empresas e quantas empresas são impactadas 

    -   Nome principal do usuário – ID de email do usuário

### <a name="product-and-service-usage-data"></a>Dados de uso de produtos e serviços

As informações a seguir são coletadas apenas para o aplicativo do Microsoft Defender para Ponto de Extremidade instalado no dispositivo. 

-   Informações do pacote do aplicativo, incluindo o nome, a versão e o status da atualização do aplicativo

-   Ações executadas no aplicativo

-   Informações de detecção de ameaças, como nome da ameaça, categoria, etc.

-   Logs de relatório de falha gerados pelo Android

## <a name="optional-data"></a>Dados Opcionais

Os dados opcionais incluem dados de diagnóstico e comentários. Os Dados de diagnóstico opcionais são dados adicionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas. Os dados de diagnóstico opcionais incluem:

-   Uso de aplicativo, CPU e rede

-   Estado do dispositivo na perspectiva do aplicativo, incluindo status de verificação, tempos de verificação, permissões de aplicativo concedidas e status de atualização

-   Recursos configurados pelo administrador

-   Informações básicas sobre os navegadores no dispositivo

**Dados de feedback** são coletados por meio de comentários no aplicativo fornecidos pelo usuário

-   O endereço de email do usuário, se ele optar por fornecer

-   Tipo de comentários (risos, carrancudos, ideias) e comentários enviados pelo usuário
