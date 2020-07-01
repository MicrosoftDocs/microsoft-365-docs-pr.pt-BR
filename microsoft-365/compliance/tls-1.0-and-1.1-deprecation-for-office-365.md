---
title: TLS 1,0 e 1,1 de substituição para o Office 365
description: Descreve o TLS 1,0 e o 1,1 de substituição para o Office 365.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937314"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>TLS 1,0 e 1,1 de substituição para o Office 365

A partir de 31 de outubro de 2018, os protocolos TLS (Transport Layer Security) 1,0 e 1,1 são preteridos para o serviço do Office 365. O efeito para os usuários finais deve ser mínimo. Essa alteração foi publicada por quase dois anos, com o primeiro lançamento publicado em dezembro de 2017. Este artigo destina-se apenas a abranger o cliente local do Office 365 em relação ao serviço do Office 365, mas também pode ser aplicado a problemas de TLS no local com o Office Web Apps e o servidor do Office Online.

## <a name="office-and-tls-overview"></a>Visão geral do Office e do TLS

O cliente do Office depende do serviço Web do Windows (WINHTTP) para enviar e receber tráfego sobre protocolos TLS. O cliente do Office pode usar TLS 1,2 se o serviço Web do computador local puder usar TLS 1,2. Todos os clientes do Office podem usar protocolos TLS, já que os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos para o cliente do Office.

### <a name="on-windows-8-and-later-versions"></a>No Windows 8 e nas versões posteriores

Por padrão, os protocolos TLS 1,2 e 1,1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1,2.

### <a name="on-windows-7"></a>No Windows 7

Os protocolos TLS 1,1 e 1,2 não estão disponíveis sem a atualização [KB 3140245](https://support.microsoft.com/help/3140245) . A atualização aborda esse problema e adiciona a seguinte subchave do registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Os usuários do Windows 7 que não têm essa atualização são afetados em 31 de outubro de 2018. O [KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações de WinHTTP para habilitar os protocolos TLS.

#### <a name="more-information"></a>Mais informações

O valor da chave de registro **DefaultSecureProtocols** que o artigo da base de conhecimento descreve determina quais protocolos de rede podem ser usados:

|Valor DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilitar SSL 2.0 por padrão|
|0x00000020|Habilitar SSL 3.0 por padrão|
|0x00000080|Habilitar TLS 1.0 por padrão|
|0x00000200|Habilitar TLS 1.1 por padrão|
|0x00000800|Habilitar TLS 1.2 por padrão|

## <a name="office-clients-and-tls-registry-keys"></a>Clientes do Office e chaves do registro TLS

Você pode consultar [o KB 4057306 preparando para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306). Este é um artigo geral para administradores de ti e é uma documentação oficial sobre a alteração de TLS 1,2.

A tabela a seguir mostra os valores de chave do registro apropriados nos clientes do Office 365 após 31 de outubro de 2018.

|Protocolos habilitados para o serviço do Office 365 após 31 de outubro de 2018|Valor hexadecimal|
|-|-|
|TLS 1,0 + 1,1 + 1,2|0x00000A80|
|TLS 1,1 + 1,2|0x00000A00|
|TLS 1,0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Não é recomendável usar os protocolos SSL 2,0 e 3,0, que também podem ser definidos usando a chave **DefaultSecureProtocols** . SSL 2,0 e 3,0 são considerados protocolos preteridos. A prática recomendada é encerrar o uso do SSL 2,0 e do SSL 3,0, embora a decisão de fazer isso por fim dependa do que melhor atende às necessidades do seu produto. Para obter mais informações sobre as vulnerabilidades de SSL 3,0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Você pode usar a calculadora padrão do Windows no modo Programador para configurar os mesmos valores de chave de registro de referência. Para obter mais informações, consulte [a atualização do KB 3140245 para habilitar o tls 1,1 e o tls 1,2 como protocolos de segurança padrão no WinHTTP no Windows](https://support.microsoft.com/help/3140245).

Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) ser instalada ou não, a subchave do registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um objeto de política de grupo (GPO). Ou seja, a menos que você precise Personalizar que protocolos seguros estão habilitados ou restritos, essa chave não é necessária. Você precisa apenas da atualização do Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).
