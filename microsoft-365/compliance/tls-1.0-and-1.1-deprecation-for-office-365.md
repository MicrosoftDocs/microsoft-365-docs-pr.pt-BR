---
title: Desabilitando o TLS 1.0 e 1.1 para o Microsoft 365
description: Descreve a preteração e desabilitação do TLS 1.0 e 1.1 para o Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233093"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Desabilitando o TLS 1.0 e 1.1 para o Microsoft 365

> [!IMPORTANT]
> Interrompemos temporariamente a desabilitação do TLS 1.0 e 1.1 para clientes comerciais devido ao COVID-19. Como as cadeias de fornecimento foram ajustadas e determinados países abriram o back up, reiniciamos a rollout de imposição do TLS 1.2 em 15 de outubro de 2020. A rollout continuará nas seguintes semanas e meses.

A partir de 31 de outubro de 2018, os protocolos TLS 1.0 e 1.1 foram preterido para o serviço do Microsoft 365. O efeito para os usuários finais é mínimo. Essa alteração foi divulgada há mais de dois anos, com o primeiro comunicado público feito em dezembro de 2017. Este artigo destina-se apenas a abranger o cliente local do Office 365 em relação ao serviço do Office 365, mas também pode se aplicar a problemas de TLS locais com o Office e o Servidor do Office Online/Office Web Apps.

Para o SharePoint e o OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2. Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Visão geral do Office 365 e do TLS

O cliente do Office depende do winHTTP (serviço Web do Windows) para enviar e receber tráfego por protocolos TLS. O cliente do Office poderá usar o TLS 1.2 se o serviço Web do computador local puder usar o TLS 1.2. Todos os clientes do Office podem usar protocolos TLS, pois os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos do cliente do Office.

### <a name="on-windows-8-and-later-versions"></a>No Windows 8 e versões posteriores

Por padrão, os protocolos TLS 1.2 e 1.1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1.2.

### <a name="on-windows-7"></a>No Windows 7

Os protocolos TLS 1.1 e 1.2 não estão disponíveis sem a atualização [KB 3140245.](https://support.microsoft.com/help/3140245) A atualização resolve esse problema e adiciona a seguinte sub-chave do Registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Os usuários do Windows 7 que não têm essa atualização são afetados a partir de 31 de outubro de 2018. [O KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações WINHTTP para habilitar protocolos TLS.

#### <a name="more-information"></a>Mais informações

O valor da chave do Registro **DefaultSecureProtocols** que o artigo da KB descreve determina quais protocolos de rede podem ser usados:

|Valor de DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilitar SSL 2.0 por padrão|
|0x00000020|Habilitar SSL 3.0 por padrão|
|0x00000080|Habilitar TLS 1.0 por padrão|
|0x00000200|Habilitar TLS 1.1 por padrão|
|0x00000800|Habilitar TLS 1.2 por padrão|

## <a name="office-clients-and-tls-registry-keys"></a>Clientes do Office e chaves do Registro TLS

Você pode consultar a KB 4057306 Preparando-se para o uso obrigatório do [TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306) Este é um artigo geral para administradores de IT e sua documentação oficial sobre a alteração do TLS 1.2.

A tabela a seguir mostra os valores de chave do Registro apropriados nos clientes do Office 365 após 31 de outubro de 2018.

|Protocolos habilitados para o serviço do Office 365 após 31 de outubro de 2018|Valor hexadecimal|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Não use os protocolos SSL 2.0 e 3.0, que também podem ser definidos usando a **chave DefaultSecureProtocols.** O SSL 2.0 e 3.0 são considerados protocolos desatualizados e inseguros. A prática ideal é encerrar o uso de SSL 2.0 e SSL 3.0, embora a decisão de fazer isso em última análise dependa do que melhor atende às necessidades do seu produto. Para obter mais informações sobre vulnerabilidades do SSL 3.0, consulte [kb 3009008](https://support.microsoft.com/help/3009008).

Você pode usar a Calculadora do Windows padrão no modo Programador para configurar os mesmos valores de chave de registro de referência. Para obter mais informações, consulte a Atualização [KB 3140245 para habilitar o TLS 1.1 e o TLS 1.2](https://support.microsoft.com/help/3140245)como protocolos seguros padrão no WinHTTP no Windows.

Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) estar instalada ou não, a sub-chave do Registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um OBJETO de política de grupo (GPO). Ou seja, a menos que você tenha que personalizar quais protocolos seguros estão habilitados ou restritos, essa chave não é necessária. Você só precisa da atualização do Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Atualizar e configurar o .NET Framework para dar suporte a TLS 1.2

Você precisará atualizar aplicativos que chamam as APIs do Microsoft 365 sobre TLS 1.0 ou TLS 1.1 para usar o TLS 1.2. O .NET 4.5 assume como padrão o TLS 1.1. Para atualizar sua configuração do .NET, consulte Como habilitar o [TLS (Transport Layer Security) 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Mais informações

Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
