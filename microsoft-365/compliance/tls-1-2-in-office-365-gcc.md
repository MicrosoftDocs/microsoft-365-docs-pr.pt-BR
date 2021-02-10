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
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166436"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Desabilitando o TLS 1.0 e 1.1 no Office 365 GCC High e DoD

## <a name="summary"></a>Resumo

Para atender aos padrões de conformidade mais recentes do FedRAMP (Federal Risk and Authorization Management Program), estamos desabilitando as versões 1.1 e 1.0 do Transport Layer Security (TLS) no Microsoft 365 para ambientes GCC High e DoD. Essa alteração foi anunciada anteriormente por meio do Suporte da Microsoft na preparação para o uso obrigatório do [TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

A segurança de seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço.

Embora a [implementação do Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, permanecemos comprometidos com os padrões de conformidade do FedRAMP. Portanto, desabilitamos o TLS 1.1 e 1.0 nos ambientes GCC High e DoD do Office 365 em 15 de janeiro de 2020. Para obter informações sobre como remover as dependências do TLS 1.1 e 1.0, consulte o seguinte white paper:

[Resolvendo o problema do TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

Você deve usar o TLS versão 1.2. Para obter mais informações, consulte Preparando-se para o uso obrigatório [do TLS 1.2 no Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Para o SharePoint e o OneDrive, você precisará atualizar e configurar o .NET para dar suporte ao TLS 1.2. Para obter informações, [consulte Como habilitar o TLS 1.2 em clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Mais Informações

A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD preterirá as TLS 1.1 e 1.0.

Até 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar o TLS versão 1.2 (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas com os serviços do Office 365. Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores do navegador.

Se você não atualizar para o TLS versão 1.2 (ou uma versão posterior) até 15 de janeiro de 2020, terá problemas ao tentar se conectar ao Office 365. Além disso, será necessário atualizar para o TLS 1.2 (ou uma versão posterior) como parte da resolução.

Sabemos que os seguintes clientes não podem usar o TLS 1.2:

- Android 4.3 e versões anteriores
- Firefox versão 5.0 e versões anteriores
- Internet Explorer 8–10 no Windows 7 e versões anteriores
- Internet Explorer 10 no Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 e versões anteriores

Recomendamos que você atualize seus clientes para garantir que mantenha acesso ininterrupto ao Office 365 GCC High e DoD.

Embora a análise atual das conexões com os serviços Do Microsoft Online mostre que a maioria dos serviços e pontos de extremidade vê muito pouco uso do TLS 1.1 e 1.0, estamos fornecendo aviso dessa alteração para que você possa atualizar todos os clientes ou servidores afetados conforme necessário antes que o suporte para TLS 1.1 e 1.0 termine. Se você estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory (AD FS), certifique-se de que a infraestrutura possa suportar conexões de entrada e saída que usam TLS 1.2 (ou uma versão posterior).

Além das paralisações que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1.2, remover o TLS 1.1 e 1.0 impedirá que você possa usar o seguinte produto da Microsoft:

- Telefone do Lync

## <a name="references"></a>Referências

O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estão usando o TLS 1.2:

[Preparando-se para o uso obrigatório do TLS 1.2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
