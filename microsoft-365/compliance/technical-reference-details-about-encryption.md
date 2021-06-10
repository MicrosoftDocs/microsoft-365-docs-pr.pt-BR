---
title: Detalhes de referência técnica sobre criptografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Saiba mais sobre os vários certificados, tecnologias e pacote de codificação TLS (Transport Layer Security) usados para criptografia em Office 365 e Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919347"
---
# <a name="technical-reference-details-about-encryption"></a>Detalhes de referência técnica sobre criptografia

Consulte este artigo para saber mais sobre certificados, tecnologias e pacote de codificação TLS usados para criptografia [em Office 365](encryption.md). Este artigo também fornece detalhes sobre deprecações planejadas.
  
- Se você estiver procurando informações de visão geral, consulte [Encryption in Office 365](encryption.md).
- Se você estiver procurando informações de instalação, consulte [Configurar criptografia em Office 365 Enterprise](set-up-encryption.md).
- Para obter informações sobre os suites de codificação suportados por versões específicas do Windows, consulte [Cipher Suites in TLS/SSL (SSP Schannel)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gerenciamento e propriedade de certificado do Microsoft Office 365

Você não precisa comprar ou manter certificados para Office 365. Em vez disso, Office 365 usa seus próprios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Padrões de criptografia atuais e deprecações planejadas

Para fornecer a melhor criptografia na classe, Office 365 regularmente revisa os padrões de criptografia com suporte. Às vezes, os padrões antigos são preterido à medida que se tornam desaparados e menos seguros. Este artigo descreve atualmente os suites de codificação com suporte e outros padrões e detalhes sobre deprecações planejadas.

## <a name="fips-compliance-for-office-365"></a>Conformidade FIPS para Office 365

Todos os pacote de codificação suportados por Office 365 usam algoritmos aceitáveis em FIPS 140-2. Office 365 herda validações FIPS de Windows (por meio do Schannel). Para obter informações sobre schannel, consulte [Cipher Suites in TLS/SSL (SSP Schannel)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versões do TLS com suporte do Office 365

TLS e SSL que vieram antes do TLS são protocolos criptográficos que garantem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. Office 365 dá suporte ao TLS versão 1.2 (TLS 1.2).

No momento, não há suporte para TLS versão 1.3 (TLS 1.3).
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Suporte para depreciação TLS 1.0 e 1.1

Office 365 parou de dar suporte a TLS 1.0 e 1.1 em 31 de outubro de 2018. Concluímos a desabilitação do TLS 1.0 e 1.1 em GCC ambientes High e DoD. Começamos a desabilitar o TLS 1.0 e 1.1 para ambientes em todo o mundo e GCC a partir de 15 de outubro de 2020 e continuaremos com a roll-out nas próximas semanas e meses.

Para manter uma conexão segura com serviços Office 365 e Microsoft 365, todas as combinações cliente-servidor e navegador-servidor usam TLS 1.2 e modernos pacote de codificação. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor. Para obter informações sobre como essa alteração afeta você, consulte Preparando-se para o uso obrigatório do [TLS 1.2 em Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Preterindo o suporte para o 3DES

Desde 31 de outubro de 2018, o Office 365 não suporta mais o uso de suites de codificação 3DES para comunicação com Office 365. Mais especificamente, Office 365 dá suporte ao pacote TLS_RSA_WITH_3DES_EDE_CBC_SHA de codificação. Desde 28 de fevereiro de 2019, esse pacote de codificação foi desabilitado Office 365. Clientes e servidores que se comunicam com Office 365 devem dar suporte a uma ou mais das codificações com suporte. Para ver uma lista de codificações com suporte, consulte [TLS cipher suites com suporte Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Substituição do suporte de certificado SHA-1 no Office 365

Desde junho de 2016, Office 365 aceita mais um certificado SHA-1 para conexões de saída ou de entrada. Use SHA-2 (Algoritmo de Hash Seguro 2) ou um algoritmo de hash mais forte na cadeia de certificados.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacote de codificação TLS com suporte Office 365

O TLS usa *pacote de codificação*, coleções de algoritmos de criptografia, para estabelecer conexões seguras. Office 365 dá suporte aos suites de codificação listados na tabela a seguir. A tabela lista os pacote de codificação em ordem de força, com o pacote de codificação mais forte listado primeiro.

Office 365 responde a uma solicitação de conexão primeiro tentando se conectar usando o pacote de codificação mais seguro. Se a conexão não funcionar, Office 365 o segundo pacote de codificação mais seguro da lista e assim por diante. O serviço continua na lista até que a conexão seja aceita. Da mesma forma, quando Office 365 solicita uma conexão, o serviço de recebimento escolhe se o TLS será usado e qual pacote de codificação usar.

> [!IMPORTANT]
> Esteja ciente de que as versões TLS são  preteridas e que as versões preteridas não devem ser usadas onde as versões mais recentes estão disponíveis. No momento, o TLS 1.3 não tem suporte. Se seus serviços herdado não exigirem TLS 1.0 ou 1.1, você deverá desabilitá-los.

| Pacote de codificação | Algoritmo/força de troca de chaves | Encaminhar Segredo | Codificação/força | Algoritmo de autenticação |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Não <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Não <br/> |AES/256 <br/>|RSA/112 <br/> |

Esses pacote de codificação suportam protocolos TLS 1.0 e 1.1 até a data de deprecação. Para GCC ambientes High e DoD que deprecation datam de 15 de janeiro de 2020 e para ambientes de nível mundial e GCC data de 15 de outubro de 2020.

| Protocolos | Nome do conjunto de codificações | Algoritmo/força de troca de chaves | Suporte ao Encaminhamento de Segredo | Algoritmo/força de autenticação | Cipher/Strength |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Artigos relacionados

[TLS Cipher Suites no Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Criptografia no Office 365](encryption.md)
  
[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md)
  
[Implementação do Schannel do TLS 1.0 na atualização de status de segurança Windows: 24 de novembro de 2015](https://support.microsoft.com/kb/3117336)
  
[Aprimoramentos criptográficos TLS/SSL (Windows Centro de IT)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Preparação para o TLS 1.2 no Office 365 e no Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)