---
title: Desabilitando o TLS 1.0 e 1.1 em Microsoft 365 GCC Alta e DoD
description: Discute como a Microsoft está desabilitando o suporte para TLS 1.1 e 1.0 em ambientes GCC High e DoD em Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919337"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Desabilitando o TLS 1.0 e 1.1 em Microsoft 365 GCC Alta e DoD

## <a name="summary"></a>Resumo

Para cumprir os padrões de conformidade mais recentes para o Programa Federal de Gerenciamento de Riscos e Autorizações (FedRAMP), estamos desabilitando as versões 1.1 e 1.0 do Transport Layer Security (TLS) em Microsoft 365 para ambientes High e DoD do GCC. Essa alteração foi anunciada anteriormente por meio do Suporte da Microsoft em Preparação para o uso obrigatório do [TLS 1.2 em Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

A segurança de seus dados é importante e estamos comprometidos com a transparência sobre as alterações que podem afetar seu uso do serviço.

Embora a implementação do [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, permanecemos comprometidos com os padrões de conformidade fedRAMP. Portanto, desabilitamos o TLS 1.1 e 1.0 em Microsoft 365 GCC em ambientes High e DoD em 15 de janeiro de 2020. Para obter informações sobre como remover as dependências do TLS 1.1 e 1.0, consulte o seguinte white paper:

[Solução do problema TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Mais informações

A partir de 15 de janeiro de 2020, o Microsoft 365 nos ambientes GCC High e DoD desabilitará o TLS 1.1 e 1.0.

Até 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar o TLS versão 1.2 (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas para Microsoft 365. Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores de navegador.

Para SharePoint e OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2. Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

Você deve atualizar seus computadores clientes para garantir que você mantenha o acesso ininterrupto Office 365 GCC High e DoD.

Você precisará atualizar aplicativos que chamam Microsoft 365 APIs por TLS 1.0 ou TLS 1.1 para usar o TLS 1.2. O .NET 4.5 é padrão para TLS 1.1. Para atualizar sua configuração .NET, consulte [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client). Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 em Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Sabemos que os seguintes aplicativos cliente não podem usar o TLS 1.2:

- Android 4.3 e versões anteriores
- Firefox versão 5.0 e versões anteriores
- Internet Explorer 8–10 no Windows 7 e versões anteriores
- Internet Explorer 10 no Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 e versões anteriores

Embora a análise atual das conexões com os serviços do Microsoft Online mostre que a maioria dos serviços e pontos de extremidade vê muito pouco uso do TLS 1.1 e 1.0, estamos notificação dessa alteração para que você possa atualizar todos os clientes ou servidores afetados conforme necessário antes do suporte para o TLS 1.1 e 1.0 terminar. Se você estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory (AD FS), certifique-se de que a infraestrutura possa dar suporte a conexões de entrada e de saída que usam TLS 1.2 (ou uma versão posterior).

Além das paralisações que você pode experimentar se você usar os clientes listados que não podem usar o TLS 1.2, remover o TLS 1.1 e 1.0 impedirá que você possa usar o seguinte produto da Microsoft:

- Telefone do Lync

## <a name="references"></a>Referências

Para obter orientações e referências para ajudar a garantir que seus clientes estão usando o TLS 1.2, consulte Preparando-se para o uso obrigatório do [TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)em Office 365 .