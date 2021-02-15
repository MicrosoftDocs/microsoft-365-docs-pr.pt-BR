---
title: Desabilitando o TLS 1.0 e 1.1 no Office 365 GCC High e DoD
description: Discute como a Microsoft está desabilitando o suporte para TLS 1.1 e 1.0 em ambientes GCC High e DoD no Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233747"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Desabilitando o TLS 1.0 e 1.1 no Office 365 GCC High e DoD

## <a name="summary"></a>Resumo

Para atender aos padrões de conformidade mais recentes do FedRAMP (Federal Risk and Authorization Management Program), estamos desabilitando as versões 1.1 e 1.0 do Transport Layer Security (TLS) no Microsoft 365 para ambientes GCC High e DoD. Essa alteração foi anunciada anteriormente por meio do Suporte da Microsoft na preparação para o uso obrigatório do [TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

A segurança de seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço.

Embora a [implementação do Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, permanecemos comprometidos com os padrões de conformidade do FedRAMP. Portanto, desabilitamos o TLS 1.1 e 1.0 nos ambientes GCC High e DoD do Office 365 em 15 de janeiro de 2020. Para obter informações sobre como remover as dependências do TLS 1.1 e 1.0, consulte o seguinte white paper:

[Resolvendo o problema do TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Mais informações

A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD preterirá os TLS 1.1 e 1.0.

Até 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar o TLS versão 1.2 (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas com os serviços do Office 365. Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores do navegador.

Se você não atualizar para o TLS versão 1.2 (ou uma versão posterior) até 15 de janeiro de 2020, terá problemas ao tentar se conectar ao Office 365. Além disso, será necessário atualizar para o TLS 1.2 (ou uma versão posterior) como parte da resolução.

Você deve atualizar seus computadores clientes para garantir que mantenha acesso ininterrupto ao Office 365 GCC High e DoD.

Você precisará atualizar aplicativos que chamam as APIs do Microsoft 365 sobre TLS 1.0 ou TLS 1.1 para usar o TLS 1.2. O .NET 4.5 assume como padrão o TLS 1.1. Para atualizar sua configuração do .NET, consulte Como habilitar o [TLS (Transport Layer Security) 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client) Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Sabemos que os seguintes aplicativos cliente não podem usar o TLS 1.2:

- Android 4.3 e versões anteriores
- Firefox versão 5.0 e versões anteriores
- Internet Explorer 8–10 no Windows 7 e versões anteriores
- Internet Explorer 10 no Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 e versões anteriores

Embora a análise atual das conexões com os serviços Do Microsoft Online mostre que a maioria dos serviços e pontos de extremidade vê muito pouco uso do TLS 1.1 e 1.0, estamos fornecendo um aviso dessa alteração para que você possa atualizar todos os clientes ou servidores afetados conforme necessário antes que o suporte para TLS 1.1 e 1.0 termine. Se você estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory (AD FS), certifique-se de que a infraestrutura possa suportar conexões de entrada e saída que usam TLS 1.2 (ou uma versão posterior).

Além das paralisações que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1.2, remover o TLS 1.1 e 1.0 impedirá que você possa usar o seguinte produto da Microsoft:

- Telefone do Lync

## <a name="references"></a>Referências

O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estão usando o TLS 1.2:

[Preparando-se para o uso obrigatório do TLS 1.2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
