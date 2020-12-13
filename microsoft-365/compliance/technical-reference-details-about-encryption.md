---
title: Detalhes técnicos de referência sobre criptografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
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
description: Saiba mais sobre os vários pacotes de codificação de segurança de camada de transporte (TLS) usados para criptografia no Office 365 e no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663424"
---
# <a name="technical-reference-details-about-encryption"></a>Detalhes técnicos de referência sobre criptografia

Consulte este artigo para saber mais sobre certificados, tecnologias e pacotes de criptografia TLS usados para [criptografia no Office 365](encryption.md). Este artigo também fornece detalhes sobre as preterições planejadas.
  
- Se você estiver procurando informações gerais, confira [criptografia no Office 365](encryption.md).
- Se você estiver procurando informações de configuração, consulte [set up Encryption in Office 365 Enterprise](set-up-encryption.md).
- Para obter informações sobre os pacotes de codificação suportados por versões específicas do Windows, consulte [Cipher Suites em TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gerenciamento e propriedade de certificado do Microsoft Office 365

Você não precisa comprar ou manter certificados para o Office 365. Em vez disso, o Office 365 usa seus próprios certificados.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Padrões de criptografia atuais e preterições planejadas

Para fornecer a melhor criptografia, o Office 365 revisa regularmente os padrões de criptografia suportados. Às vezes, os padrões antigos são preteridos à medida que ficam desatualizados e menos seguros. Este artigo descreve os pacotes de codificação atualmente suportados e outros padrões e detalhes sobre as preterições planejadas.

## <a name="fips-compliance-for-office-365"></a>Conformidade com FIPS para o Office 365

Todos os pacotes de codificação compatíveis com o Office 365 usam algoritmos aceitáveis em FIPS 140-2. O Office 365 herda as validações de FIPS do Windows (por meio do Schannel). Para obter informações sobre Schannel, consulte [Cipher Suites em TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Versões do TLS com suporte do Office 365

O TLS e o SSL que vieram antes do TLS são protocolos de criptografia que protegem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. O Office 365 oferece suporte a TLS versão 1,2 (TLS 1,2).

O TLS versão 1,3 (TLS 1,3) atualmente não tem suporte.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Suporte para TLS 1,0 e 1,1

O Office 365 parou de suportar o TLS 1,0 e 1,1 em 31 de outubro de 2018. Novos problemas encontrados em clientes, dispositivos ou serviços que se conectam ao Office 365 sobre TLS 1,0 e 1,1 não serão corrigidos. A substituição oficial para ambientes GCC High e DoD começou em 15 de janeiro de 2020. A substituição de TLS 1,0 e 1,1 para ambientes de todo o mundo e GCC começou em 15 de outubro de 2020.

Para manter uma conexão segura com o Office 365 e os serviços do Microsoft 365, todas as combinações de servidor de cliente e de servidor de pesquisa usam TLS 1,2 e pacotes de codificação modernos. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor. Para obter informações sobre como essa alteração impacta você, consulte Preparando-se [para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Substituição do suporte a 3DES

Desde 31 de outubro de 2018, o Office 365 não é mais compatível com o uso de pacotes de codificação 3DES para comunicação com o Office 365. Mais especificamente, o Office 365 não suporta mais o pacote de codificação TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde 28 de fevereiro de 2019, este pacote de codificação foi desabilitado no Office 365. Os clientes e servidores que se comunicam com o Office 365 devem oferecer suporte a uma ou mais das codificações suportadas. Para obter uma lista de Codificações suportadas, consulte [pacotes de codificação TLS compatíveis com o Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Substituição do suporte de certificado SHA-1 no Office 365

Desde junho de 2016, o Office 365 não aceita mais um certificado SHA-1 para conexões de entrada ou saída. Use SHA-2 (algoritmo de hash seguro 2) ou um algoritmo de hash mais forte na cadeia de certificados.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacotes de codificação TLS compatíveis com o Office 365

O TLS usa *pacotes de codificação*, coleções de algoritmos de criptografia, para estabelecer conexões seguras. O Office 365 oferece suporte aos conjuntos de codificação listados na tabela a seguir. A tabela lista os conjuntos de codificação em ordem de intensidade, com o pacote de codificação mais forte listado primeiro.

O Office 365 responde a uma solicitação de conexão primeiro tentando se conectar usando o pacote de codificação mais seguro. Se a conexão não funcionar, o Office 365 tenta o segundo pacote de codificação mais seguro na lista e assim por diante. O serviço continua a lista para baixo até que a conexão seja aceita. Da mesma forma, quando o Office 365 solicita uma conexão, o serviço de recebimento escolhe se o TLS será usado e qual pacote de codificação usar.

> [!IMPORTANT]
> Lembre-se de que as versões do TLS estão obsoletas e que *não devem ser usadas* como versões mais recentes disponíveis. O TLS 1,3 atualmente não tem suporte. Se os serviços herdados não exigirem o TLS 1,0 ou 1,1, você deverá desabilitá-los.

| Pacote de codificação | Algoritmo/intensidade de troca de chave | Sigilo total na transferência | Codificação/força | Algoritmo de autenticação |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Sim <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Sim <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Não <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Não <br/> |AES/256 <br/>|RSA/112 <br/> |

Estes pacotes de codificação suportavam protocolos TLS 1,0 e 1,1 compatíveis até a data de substituição. Para ambientes GCC High e DoD que a data de substituição foi 15 de janeiro de 2020 e para ambientes do mundo e GCC que data foi 15 de outubro de 2020.

| Protocolos | Nome do conjunto de codificações | Algoritmo/intensidade de troca de chave | Suporte perfeito a sigilo total | Algoritmo de autenticação/intensidade | Codificação/força |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Artigos relacionados

[Pacotes de criptografia TLS no Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Criptografia no Office 365](encryption.md)
  
[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md)
  
[Implementação Schannel de TLS 1,0 na atualização de status de segurança do Windows: 24 de novembro de 2015](https://support.microsoft.com/kb/3117336)
  
[Aprimoramentos de criptografia TLS/SSL (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Preparação para o TLS 1.2 no Office 365 e no Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
