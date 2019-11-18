---
title: Detalhes de referências técnicas sobre a criptografia no Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Veja detalhes técnicos sobre o encyption no Office 365.
ms.openlocfilehash: b21409007b82490730aa48f403c30e542ead0316
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38684817"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>Detalhes de referências técnicas sobre a criptografia no Office 365

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

O TLS e o SSL, que veio antes do TLS, são protocolos de criptografia que protegem a comunicação em uma rede usando certificados de segurança para criptografar uma conexão entre computadores. O Office 365 é compatível com várias versões do TLS, entre elas:
  
- TLS versão 1.2 (TLS 1.2)
    
- TLS versão 1.1 (TLS 1.1)
    
- TLS versão 1.0 (TLS 1.0)
    
 O suporte a TLS 1,0 e TLS 1,1 será substituído em 31 de outubro de 2018. Consulte [preterindo o suporte para TLS 1,0 e 1,1 e o que isso significa](technical-reference-details-about-encryption.md#TLS11and12deprecation) para obter mais informações. 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Substituição do suporte para TLS 1,0 e 1,1 e o que isso significa para você
<a name="TLS11and12deprecation"> </a>

Desde 31 de outubro de 2018, o Office 365 não oferece mais suporte a TLS 1,0 e 1,1. Isso significa que a Microsoft não corrigirá novos problemas que forem encontrados em clientes, dispositivos ou serviços que se conectem ao Office 365 usando o TLS 1.0 e 1.1.

Observação isso não significa que o Office 365 bloqueará as conexões TLS 1,0 e 1,1. 

O TLS 1,0 e o TLS 1,1 serão oficialmente preteridos nas datas abaixo:
- 1º de junho de 2020 para clientes nos ambientes de todo o mundo e GCC.
- 15 de janeiro de 2020 para clientes nos ambientes GCC High e DoD soberana. 

Você deve certificar-se de que todas as combinações de servidor de cliente e navegador de servidor usem TLS 1,2 (ou uma versão posterior) para manter a conexão com os serviços do Office 365. Talvez seja necessário atualizar determinadas combinações de servidor de cliente e de servidor. Para obter informações sobre como isso impacta, consulte [preparando-se para o uso obrigatório de TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Substituição do suporte a 3DES
<a name="TLS11and12deprecation"> </a>

Desde 31 de outubro de 2018, o Office 365 não é mais compatível com o uso de pacotes de codificação 3DES para comunicação com o Office 365. Mais especificamente, o Office 365 não suporta mais o pacote de codificação TLS_RSA_WITH_3DES_EDE_CBC_SHA. Desde 28 de fevereiro de 2019, este pacote de codificação está sendo desabilitado no Office 365. Os clientes e servidores que se comunicam com o O365 após esta data devem oferecer suporte a pelo menos uma das codificações mais seguras listadas neste tópico (consulte [TLS Cipher Suites compatíveis com o Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Substituição do suporte de certificado SHA-1 no Office 365
<a name="TLS11and12deprecation"> </a>

A partir de junho de 2016, o Office 365 não aceita mais um certificado SHA-1 para conexões de entrada ou saída. Se você estiver usando um certificado com SHA-1 na cadeia de certificados, será necessário atualizar a cadeia para usar SHA-2 (algoritmo de hash seguro 2) ou um algoritmo de hash mais forte.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Pacotes de codificação TLS compatíveis com o Office 365
<a name="TLSCipherSuites"> </a>

Um conjunto de codificações é uma coleção de algoritmos de criptografia que o TLS usa para estabelecer conexões seguras. Os pacotes de codificação com suporte do Office 365 estão listados na tabela a seguir em ordem de força com o pacote de codificação mais forte listado primeiro. Quando o Office 365 recebe uma solicitação de conexão, primeiro ele tenta se conectar usando o conjunto de codificações de nível superior e, caso não consiga, tenta o segundo conjunto da lista e assim por diante até o final da lista. Quando o Office 365 envia uma solicitação de conexão para outro servidor, ou para um cliente, o servidor ou o cliente deve escolher o conjunto de codificações ou se o TLS será usado.

> [!IMPORTANT]
> Lembre-se de que as versões do TLS estão obsoletas e que *não devem ser usadas* como versões mais recentes disponíveis. Em outras palavras, em qualquer lugar em que estejam listadas que o TLS 1,0, 1,1 e 1,2 têm suporte, escolha a versão *mais recente* (TLS 1,2).
  
|**Protocolos**|**Nome do conjunto de codificações**|**Algoritmo/intensidade de troca de chave**|**Suporte perfeito a sigilo total**|**Algoritmo de autenticação/intensidade**|**Codificação/força**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Sim  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Sim  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |Não  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |Não  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |Não  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |Não  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados
[Pacotes de criptografia TLS no Windows 10 v1607](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Criptografia no Office 365](encryption.md)
  
[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md)
  
[Implementação Schannel de TLS 1,0 na atualização de status de segurança do Windows: 24 de novembro de 2015](https://support.microsoft.com/kb/3117336)
  
[Aprimoramentos de criptografia TLS/SSL (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  

