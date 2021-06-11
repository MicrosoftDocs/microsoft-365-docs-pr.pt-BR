---
title: Desabilitando o TLS 1.0 e 1.1 para Microsoft 365
description: Descreve a depreciação e a desabilitação do TLS 1.0 e 1.1 para Microsoft 365.
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
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332673"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Desabilitando o TLS 1.0 e 1.1 para Microsoft 365

> [!IMPORTANT]
> Interrompemos temporariamente a desabilitação do TLS 1.0 e 1.1 para clientes comerciais devido ao COVID-19. À medida que as cadeias de fornecimento foram ajustadas e determinados países abriram o back-up, reiniciamos a aplicação de TLS 1.2 em 15 de outubro de 2020. A adoção continuará durante as semanas e meses seguintes.

A partir de 31 de outubro de 2018, os protocolos TLS (Transport Layer Security) 1.0 e 1.1 são preterido para o serviço Microsoft 365 transporte. O efeito para usuários finais é mínimo. Essa alteração foi divulgada por mais de dois anos, com o primeiro comunicado público feito em dezembro de 2017. Este artigo destina-se apenas a abranger o cliente local Office 365 em relação ao serviço Office 365, mas também pode se aplicar a problemas TLS locais com Office e Servidor do Office Online/Office Web Apps.

Para SharePoint e OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2. Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="office-365-and-tls-overview"></a>Office 365 e visão geral do TLS

O Office cliente depende do serviço web Windows (WINHTTP) para enviar e receber tráfego por meio de protocolos TLS. O Office cliente poderá usar o TLS 1.2 se o serviço Web do computador local puder usar o TLS 1.2. Todos Office clientes podem usar protocolos TLS, pois os protocolos TLS e SSL fazem parte do sistema operacional e não são específicos do cliente Office.

### <a name="on-windows-8-and-later-versions"></a>Em Windows 8 e versões posteriores

Por padrão, os protocolos TLS 1.2 e 1.1 estão disponíveis se nenhum dispositivo de rede estiver configurado para rejeitar o tráfego TLS 1.2.

### <a name="on-windows-7"></a>No Windows 7

Os protocolos TLS 1.1 e 1.2 não estão disponíveis sem a atualização [KB 3140245.](https://support.microsoft.com/help/3140245) A atualização resolve esse problema e adiciona a seguinte sub-chave do Registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 usuários que não têm essa atualização são afetados a partir de 31 de outubro de 2018. [O KB 3140245](https://support.microsoft.com/help/3140245) tem detalhes sobre como alterar as configurações WINHTTP para habilitar protocolos TLS.

#### <a name="more-information"></a>Mais informações

O valor da chave de registro **DefaultSecureProtocols** que o artigo KB descreve determina quais protocolos de rede podem ser usados:

|Valor DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilitar SSL 2.0 por padrão|
|0x00000020|Habilitar SSL 3.0 por padrão|
|0x00000080|Habilitar TLS 1.0 por padrão|
|0x00000200|Habilitar TLS 1.1 por padrão|
|0x00000800|Habilitar TLS 1.2 por padrão|

## <a name="office-clients-and-tls-registry-keys"></a>Office clientes e chaves de registro TLS

Você pode se referir [ao KB 4057306 Preparando-se](https://support.microsoft.com/help/4057306)para o uso obrigatório do TLS 1.2 em Office 365 . Este é um artigo geral para administradores de IT e é a documentação oficial sobre a alteração do TLS 1.2.

A tabela a seguir mostra os valores de chave do Registro apropriados Office 365 clientes após 31 de outubro de 2018.

|Protocolos habilitados para Office 365 serviço após 31 de outubro de 2018|Valor hexadecimal|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> Não use os protocolos SSL 2.0 e 3.0, que também podem ser definidos usando a **chave DefaultSecureProtocols.** SSL 2.0 e 3.0 são considerados protocolos desatualizados e inseguros. A prática ideal é encerrar o uso do SSL 2.0 e do SSL 3.0, embora a decisão de fazer isso, em última análise, dependa do que melhor atende às necessidades do produto. Para obter mais informações sobre vulnerabilidades SSL 3.0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Você pode usar a calculadora Windows padrão no modo Programador para configurar os mesmos valores de chave de registro de referência. Para obter mais informações, consulte [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Independentemente de a atualização do Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) estar instalada ou não, a sub-chave do Registro DefaultSecureProtocols não está presente e deve ser adicionada manualmente ou por meio de um objeto de política de grupo (GPO). Ou seja, a menos que você tenha que personalizar quais protocolos seguros estão habilitados ou restritos, essa chave não é necessária. Você só precisa da atualização Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Atualizar e configurar o .NET Framework para dar suporte ao TLS 1.2

Você precisará atualizar aplicativos que chamam Microsoft 365 APIs por TLS 1.0 ou TLS 1.1 para usar o TLS 1.2. O .NET 4.5 é padrão para TLS 1.1. Para atualizar sua configuração .NET, consulte [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="more-information"></a>Mais informações

Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 em Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="references"></a>Referências

Os recursos a seguir fornecem orientações para ajudar a garantir que seus clientes estão usando o TLS 1.2 ou uma versão posterior e para desabilitar o TLS 1.0 e 1.1:

- Caso tenha clientes Windows 7 conectados ao Office 365, verifique se o TLS 1.2 é o protocolo seguro padrão do WinHTTP no Windows. Para obter mais informações, consulte [KB 3140245 - Atualização para habilitar o TLS 1.1 e o TLS 1.2](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)como protocolos seguros padrão no WinHTTP em Windows .
- Para resolver o uso de TLS fraco removendo as dependências TLS 1.0 e 1.1, consulte [Suporte ao TLS 1.2 na Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- A [nova funcionalidade de IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) facilita a descoberta de clientes no [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) e no [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) que se conectam ao serviço usando protocolos de segurança fracos.
- Obter mais informações sobre como [resolver o problema TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).
- Para obter informações gerais sobre nossa abordagem de segurança, acesse a [Central de Confiabilidade do Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparação para o preterimento do TLS 1.0/1.1 — Skype for Business do Office 365](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Diretrizes do Exchange Server TLS, parte 1: Preparação para o TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Diretrizes do Exchange Server TLS Parte 2: Habilitando o TLS 1.2 e identificando clientes que não o utilizam](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Diretrizes do Exchange Server TLS Parte 3: Desativando o TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Habilitar o suporte para TLS 1.1 e TLS 1.2 no Servidor do Office Online](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

