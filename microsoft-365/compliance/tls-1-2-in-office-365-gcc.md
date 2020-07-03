---
title: Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD
description: Discute como a Microsoft está movendo a data para a qual o suporte do TLS 1,1 e 1,0 nos ambientes GCC High e DoD no Office 365 e se prepara para usar o TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024811"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Substituição de TLS 1,0 e 1,1 no Office 365 GCC High e DoD

> [!IMPORTANT]
> O mundo está no meio de uma pandemia, e nós da Microsoft estamos cientes do impacto para nossos clientes e parceiros. Para aliviar a carga de nossos clientes comerciais, suspendemos temporariamente qualquer imposição de preterimento do TLS 1.0 e 1.1. Uma atualização será enviada em uma linha do tempo revisada após a crise atual se estabilizar. (Este artigo é revisado para refletir a mudança.)

## <a name="summary"></a>Resumo

Para estar em conformidade com os padrões de conformidade mais recentes para o programa de gerenciamento de riscos e autorização (FedRAMP), estamos migrando para substituir as versões 1,1 e 1,0 do protocolo de segurança de camada de transporte (TLS) do Microsoft Office 365 para ambientes GCC High e DoD. Essa alteração foi anunciada anteriormente pelo suporte da Microsoft em [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Entendemos que a segurança de seus dados é importante, e estamos comprometidos com a transparência das alterações que podem afetar o uso do serviço.

Embora a [implementação do Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) não tenha vulnerabilidades de segurança conhecidas, continuamos a confirmar os padrões de conformidade do FedRAMP. Portanto, preteriremos o TLS 1,1 e 1,0 no Office 365 em ambientes GCC High e DoD, a partir de 15 de janeiro de 2020. Para obter informações sobre como remover as dependências de TLS 1,1 e 1,0, consulte o White Paper a seguir:

[Resolvendo o problema de TLS 1,0](https://www.microsoft.com/download/details.aspx?id=55266)

Ao se preparar para esta alteração para TLS 1,1 e 1,0, recomendamos que você use a versão 1,2 de TLS. Para obter mais informações, consulte [preparação para o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="more-information"></a>Mais informações

A partir de 15 de janeiro de 2020, o Office 365 nos ambientes GCC High e DoD substituirá o TLS 1,1 e 1,0.

Em 15 de janeiro de 2020, todas as combinações de servidores cliente e servidores de navegador devem usar a versão 1,2 do TLS (ou uma versão posterior) para garantir que todas as conexões possam ser feitas sem problemas para os serviços do Office 365. Isso pode exigir atualizações para determinadas combinações de servidores cliente e servidores de navegador.

Se você não atualizar para TLS versão 1,2 (ou uma versão posterior) em 15 de janeiro de 2020, você terá problemas ao tentar se conectar ao Office 365. Além disso, será necessário atualizar para o TLS 1,2 (ou uma versão posterior) como parte da resolução.

Sabemos que os seguintes clientes não podem usar o TLS 1,2:

- Android 4.3 e versões anteriores
- Firefox versão 5.0 e versões anteriores
- Internet Explorer 8 – 10 no Windows 7 e versões anteriores
- Internet Explorer 10 no Windows Phone 8,0
- Safari 6.0.4/OS X 10.8.4 e versões anteriores

Recomendamos que você atualize seus clientes para garantir que você mantenha o acesso ininterrupto ao Office 365 GCC High e o DoD.

Embora a análise atual de conexões com o Microsoft Online Services mostre que a maioria dos serviços e pontos de extremidade Confira muito pouco uso de TLS 1,1 e 1,0, estamos fornecendo notificações sobre essa alteração para que você possa atualizar quaisquer clientes ou servidores afetados, conforme o necessário, antes que o suporte para TLS 1,1 e 1,0 seja encerrado. Se você estiver usando uma infraestrutura local para cenários híbridos ou serviços de Federação do Active Directory (AD FS), verifique se a infraestrutura pode dar suporte a conexões de entrada e de saída que usam TLS 1,2 (ou uma versão posterior).

Além das interrupções que podem ocorrer se você usar os clientes listados que não podem usar o TLS 1,2, remover o TLS 1,1 e o 1,0 impedirá que você use o seguinte produto da Microsoft:

- Telefone Lync

## <a name="references"></a>Referências

O artigo de suporte a seguir descreve orientações e referências para ajudar a garantir que seus clientes estejam usando o TLS 1,2:

[Preparando o uso obrigatório do TLS 1,2 no Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
