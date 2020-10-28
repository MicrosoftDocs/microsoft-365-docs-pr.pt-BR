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
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Saiba mais sobre os vários certificados, tecnologias e pacotes de criptografia TLS usados para criptografia no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb45f325095143e6f66d9cd2bfa6f3875fb03043
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769171"
---
# <a name="technical-reference-details-about-encryption"></a>Detalhes técnicos de referência sobre criptografia

Consulte este artigo para saber mais sobre certificados, tecnologias e pacotes de criptografia TLS usados para [criptografia no Office 365](encryption.md). Este artigo também fornece detalhes sobre as preterições planejadas.

- Se você estiver procurando informações gerais, confira [criptografia no Office 365](encryption.md).
- Se você estiver procurando informações de configuração, consulte [set up Encryption in Office 365 Enterprise](set-up-encryption.md).
- Para obter informações sobre os pacotes de codificação suportados por versões específicas do Windows, consulte [Cipher Suites em TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Gerenciamento e propriedade de certificado do Microsoft Office 365

Não é necessário comprar nem manter certificados do Office 365, pois a Microsoft usa os próprios certificados.

## <a name="current-encryption-standards-and-planned-deprecations"></a>Padrões de criptografia atuais e preterições planejadas

Para continuar a fornecer a melhor criptografia para o Office 365, a Microsoft analisa regularmente os padrões de criptografia suportados. Às vezes, precisamos substituir os padrões antigos à medida que eles ficarem desatualizados e, portanto, menos seguros. Este tópico descreve os pacotes de codificação e outros padrões atualmente suportados, bem como detalhes sobre as preterições planejadas.

## <a name="fips-compliance-for-office-365"></a>Conformidade com FIPS para o Office 365

Todos os pacotes de codificação compatíveis com o Office 365 usam algoritmos aceitáveis em FIPS 140-2. O Office 365 herda as validações de FIPS do Windows (por meio do Schannel). Para obter informações sobre Schannel, consulte [Cipher Suites em TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="versions-of-tls-supported-by-office-365"></a>Versões do TLS com suporte do Office 365

O TLS e o SSL, que veio antes do TLS, são protocolos de criptografia que protegem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. O Office 365 oferece suporte a TLS versão 1,2 (TLS 1,2).

O TLS versão 1,3 (TLS 1,3) atualmente não tem suporte.

## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>Suporte para TLS 1,0 e 1,1 e o que isso significa para você

Desde 31 de outubro de 2018, o Office 365 não oferece mais suporte a TLS 1,0 e 1,1. Isso significa que a Microsoft não corrigirá novos problemas que forem encontrados em clientes, dispositivos ou serviços que se conectem ao Office 365 usando o TLS 1.0 e 1.1. A substituição oficial para ambientes GCC High e DoD começou em 15 de janeiro de 2020. A substituição de TLS 1,0 e 1,1 para ambientes de todo o mundo e GCC começa em 15 de outubro de 2020.

Você deve certificar-se de que todas as combinações de servidor de cliente e de servidor do navegador usem o TLS 1,2 e os pacotes de codificação modernos para manter uma conexão segura com o Office 365 e os serviços do Microsoft 365. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor. Para obter informações sobre como isso impacta, consulte [preparando-se para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="deprecating-support-for-3des"></a>Substituição do suporte a 3DES

Desde 31 de outubro de 2018, o Office 365 não é mais compatível com o uso de pacotes de codificação 3DES para comunicação com o Office 365. Mais especificamente, o Office 365 não suporta mais o pacote de codificação TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde 28 de fevereiro de 2019, este pacote de codificação foi desabilitado no Office 365. Os clientes e servidores que se comunicam com o Office 365 após essa data devem oferecer suporte a pelo menos uma das codificações mais seguras listadas neste tópico (consulte [TLS Cipher Suites compatíveis com o Office 365](#tls-cipher-suites-supported-by-office-365)).

## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Substituição do suporte de certificado SHA-1 no Office 365

A partir de junho de 2016, o Office 365 não aceita mais um certificado SHA-1 para conexões de entrada ou saída. Se você estiver usando um certificado com SHA-1 na cadeia de certificados, será necessário atualizar a cadeia para usar SHA-2 (algoritmo de hash seguro 2) ou um algoritmo de hash mais forte.

## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacotes de codificação TLS compatíveis com o Office 365

Um conjunto de codificações é uma coleção de algoritmos de criptografia que o TLS usa para estabelecer conexões seguras. Os conjuntos de codificações com suporte no Office 365 são apresentados na tabela a seguir em ordem de eficácia, começando pelo mais eficaz. Quando o Office 365 recebe uma solicitação de conexão, o Office 365 primeiro tenta se conectar usando o pacote de codificação mais elevado. Em seguida, se não tiver êxito, o Office 365 tentará o segundo pacote de codificação na lista e, assim, na lista. Quando o Office 365 envia uma solicitação de conexão para outro servidor, ou para um cliente, o servidor ou o cliente deve escolher o conjunto de codificações ou se o TLS será usado.

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

Estes são os conjuntos de codificação a seguir, que ainda oferecerão suporte a protocolos TLS 1,0 e 1,1 até a data de substituição. Para ambientes GCC High e DoD que a data de substituição era de 15 Jan, 2020 e para ambientes do mundo e GCC, essa data é 15 de outubro de 2020.

| Protocolos | Nome do conjunto de codificações | Algoritmo/intensidade de troca de chave | Suporte perfeito a sigilo total | Algoritmo de autenticação/intensidade | Codificação/força |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Não  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Não   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-topics"></a>Tópicos relacionados
[Pacotes de criptografia TLS no Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Criptografia no Office 365](encryption.md)

[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md)

[Riscos e proteções de criptografia](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections?view=o365-worldwide)

[Implementação Schannel de TLS 1,0 na atualização de status de segurança do Windows: 24 de novembro de 2015](https://support.microsoft.com/kb/3117336)

[Aprimoramentos de criptografia TLS/SSL (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)

[Preparação para o TLS 1.2 no Office 365 e no Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
