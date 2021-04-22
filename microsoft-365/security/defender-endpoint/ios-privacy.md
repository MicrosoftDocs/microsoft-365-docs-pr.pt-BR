---
title: Informações de privacidade - Microsoft Defender para Ponto de Extremidade no iOS
ms.reviewer: ''
description: Descreve informações de privacidade do Microsoft Defender para Ponto de Extremidade no iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, policy, overview
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 15c22a6f6b581ff68488db6628f7647d49487652
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934280"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>Informações de privacidade - Microsoft Defender para Ponto de Extremidade no iOS

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> O Defender for Endpoint no iOS usa uma VPN para fornecer o recurso de Proteção da Web. Esta não é uma VPN regular e é uma VPN local ou auto-loop que não leva tráfego fora do dispositivo. **A Microsoft ou sua organização não vê sua atividade de navegação.**

O Defender para Ponto de Extremidade no iOS coleta informações de seus dispositivos iOS configurados e as armazena no mesmo locatário em que você tem o Defender para Ponto de Extremidade. As informações são coletadas para ajudar a manter o Defender para o Ponto de Extremidade no iOS seguro, atualizado, executando conforme esperado e para dar suporte ao serviço.

Para obter mais informações sobre armazenamento de dados, consulte [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

## <a name="required-data"></a>Dados necessários 

Os dados necessários consistem em dados necessários para que o Defender for Endpoint no iOS funcione conforme o esperado. Esses dados são essenciais para a operação do serviço e podem incluir dados relacionados ao usuário final, organização, dispositivo e aplicativos. 

Aqui está uma lista dos tipos de dados que estão sendo coletados: 

### <a name="web-page-or-network-information"></a>Informações da página da Web ou rede 

- Nome de domínio do site somente quando uma conexão mal-intencionada ou página da Web é detectada. 

### <a name="device-and-account-information"></a>Informações de dispositivo e conta 

- Informações do dispositivo, como data & hora, versão do iOS, informações da CPU e identificador de dispositivo, onde o identificador de dispositivo é um dos seguintes: 

    - Wi-Fi mac adaptador 

    - Identificador global exclusivo gerado aleatoriamente (GUID) 

- Informações de locatário, dispositivo e usuário 

    - ID de Dispositivo do Azure Active Directory (AD) e ID do Usuário do Azure - Identifica exclusivamente o dispositivo, Usuário, respectivamente, no Azure Active directory. 

    - ID do locatário do Azure - GUID que identifica sua organização no Azure Active Directory. 

    - ID da organização do Microsoft Defender for Endpoint - Identificador exclusivo associado à empresa à que o dispositivo pertence. Permite que a Microsoft identifique se há problemas que afetam um conjunto selecionado de empresas e o número de empresas impactadas. 

    - Nome principal do usuário - ID de email do usuário. 

### <a name="product-and-service-usage-data"></a>Dados de uso de produtos e serviços 

As informações a seguir são coletadas apenas para o aplicativo do Microsoft Defender para Ponto de Extremidade instalado no dispositivo. 

- Informações do pacote do aplicativo, incluindo o nome, a versão e o status da atualização do aplicativo. 

- Ações realizadas no aplicativo. 

- Logs de relatório de falha gerados pelo iOS. 

- Dados de uso de memória. 

## <a name="optional-data"></a>Dados Opcionais 

Os dados opcionais incluem dados de diagnóstico e dados de feedback do cliente. Os Dados de diagnóstico opcionais são dados adicionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas. Esses dados são apenas para fins de diagnóstico e não são necessários para o próprio serviço. 

Os dados de diagnóstico opcionais incluem: 

- Uso de aplicativo, CPU e rede para o Defender para Ponto de Extremidade. 

- Recursos configurados pelo administrador do Defender para Ponto de Extremidade. 

Feedback Os dados são coletados por meio de comentários no aplicativo fornecidos pelo usuário. 

- O endereço de email do usuário, se ele optar por fornecer.

- Tipo de comentários (risos, carrancudos, ideias) e comentários enviados pelo usuário. 

Para obter mais informações, consulte [Mais sobre Privacidade](https://aka.ms/mdatpiosprivacystatement).


