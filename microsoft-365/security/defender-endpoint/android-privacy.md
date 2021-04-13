---
title: Microsoft Defender ATP para Android - Informações de privacidade
description: Controles de privacidade, como configurar configurações de política que impactam a privacidade e informações sobre os dados de diagnóstico coletados no Microsoft Defender ATP para Android.
keywords: microsoft, defender, atp, android, privacidade, diagnóstico
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
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687956"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender para Ponto de Extremidade no Android - Informações de privacidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


O Defender for Endpoint para Android coleta informações de seus dispositivos Android configurados e as armazena no mesmo locatário onde você tem o Defender para Ponto de Extremidade.

As informações são coletadas para ajudar a manter o Defender for Endpoint para Android seguro, atualizado, executando conforme esperado e para dar suporte ao serviço.

## <a name="required-data"></a>Dados Necessários 

Os dados necessários consistem em dados necessários para que o Defender for Endpoint para Android funcione conforme esperado. Esses dados são essenciais para a operação do serviço e podem incluir dados relacionados ao usuário final, organização, dispositivo e aplicativos. Aqui está uma lista dos tipos de dados que estão sendo coletados:

### <a name="app-information"></a>Informações do aplicativo

Informações sobre pacotes de aplicativos Android (APKs) no dispositivo, incluindo

-  Instalar origem
-  Local de armazenamento (caminho do arquivo) do APK
-  Hora da instalação, tamanho do APK e permissões

### <a name="web-page--network-information"></a>Página da Web / Informações de rede

- URL completa (em navegadores com suporte), quando clicado
- Informações de conexão
- Tipo de protocolo (como HTTP, HTTPS, etc.)


### <a name="device-and-account-information"></a>Informações de dispositivo e conta

- Informações do dispositivo, como data & hora, versão do Android, modelo OEM, informações da CPU e identificador de dispositivo
- O identificador de dispositivo é um dos abaixo:
    - Wi-Fi mac adaptador
    - [ID do Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (conforme gerado pelo Android no momento da primeira inicialização do dispositivo)
    - Identificador global exclusivo gerado aleatoriamente (GUID)

- Informações de locatário, dispositivo e usuário
    -   ID do Dispositivo do Azure Active Directory (AD) e ID do Usuário do Azure: identifica exclusivamente o dispositivo, Usuário, respectivamente, no diretório do Azure Active.

    -   ID do locatário do Azure - GUID que identifica sua organização no Azure Active Directory

    -   ID da organização do Microsoft Defender ATP - Identificador exclusivo associado à empresa à que o dispositivo pertence. Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de empresas e quantas empresas são impactadas 

    -   Nome principal do usuário – ID de email do usuário

### <a name="product-and-service-usage-data"></a>Dados de uso de produtos e serviços
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
