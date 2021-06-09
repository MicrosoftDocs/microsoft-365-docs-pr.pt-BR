---
title: Preparação para o TLS 1.2 no Office 365 e no Office 365 GCC
description: Como se preparar para usar o TLS 1.2 para todas as combinações de servidor-cliente e servidor-navegador no Office 365 e Office 365 GCC após o suporte para TLS 1.0 e 1.1 ser desabilitado.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 708e5dc68b777db42696c6791124b2a8dd1d3b87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927947"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Preparação para o TLS 1.2 no Office 365 e no Office 365 GCC

## <a name="summary"></a>Resumo

Para oferecer a melhor criptografia disponível para nossos clientes, a Microsoft planeja preterir as versões 1.0 e 1.1 do protocolo TLS no Office 365 e no Office 365 GCC. Entendemos que a segurança dos seus dados é importante, e estamos comprometidos com a transparência sobre as alterações que podem afetar o uso do serviço TLS.

A [implementação do Microsoft TLS 1.0](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) não tem vulnerabilidades de segurança conhecidas. Porém, devido ao potencial de futuros ataques de downgrade do protocolo e de outras vulnerabilidades do TLS, estamos interrompendo o suporte para o TLS 1.0 e 1.1 no Microsoft Office 365 e no Office 365 GCC.

Para obter mais informações sobre como remover as dependências do TLS 1.0 e 1.1, consulte o seguinte white paper: [Resolvendo o problema do TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Mais informações

Já iniciamos o preterimento do TLS 1.0 e 1.1 a partir de janeiro de 2020. Quaisquer clientes, dispositivos ou serviços que se conectam ao Office 365 por meio do TLS 1.0 ou 1.1 em nossas instâncias DoD ou GCC High não têm suporte. Para nossos clientes comerciais do Office 365, a depreciação do TLS 1.0 e 1.1 começará em 15 de outubro de 2020 e a adoção continuará durante as semanas e meses seguintes. 

Recomendamos que todas as combinações de cliente-servidor e navegador-servidor usem o TLS 1.2 (ou uma versão posterior) para manter a conexão com os serviços do Office 365. Você poderá ter que atualizar certas combinações de cliente-servidor e navegador-servidor.

Você precisará atualizar aplicativos que chamam Microsoft 365 APIs por TLS 1.0 ou TLS 1.1 para usar o TLS 1.2. O .NET 4.5 é padrão para TLS 1.1. Para atualizar sua configuração .NET, consulte [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

Os seguintes clientes não podem usar o TLS 1.2. Atualize esses clientes para garantir o acesso sem interrupções ao serviço.

- Android 4.3 e versões anteriores
- Firefox versão 5.0 e versões anteriores
- Internet Explorer 8-10 no Windows 7 e versões anteriores
- Internet Explorer 10 no Windows Phone 8
- Safari 6.0.4/OS X10.8.4 e versões anteriores

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 para Salas do Microsoft Teams e Surface Hub

As Salas do Microsoft Teams (anteriormente conhecidas como Sistema de Salas Skype V2 SRS V2) têm suporte ao TLS 1.2 desde dezembro de 2018. Recomendamos que os dispositivos de Salas tenham o aplicativo Salas do Microsoft Teams versão 4.0.64.0 ou posterior instalado. Para obter mais informações, consulte as [Notas de versão](/microsoftteams/room-systems/srs2-release-note). As mudanças são compatíveis com versões anteriores e posteriores.

O Surface Hub lançou o suporte ao TLS 1.2 em maio de 2019.

O suporte ao TLS 1.2 para os produtos Salas do Microsoft Team e Surface Hub também requer as seguintes alterações de código do lado do servidor:

- As alterações no servidor do Skype for Business Online foram ativadas em abril de 2019. Agora, o Skype for Business Online dá suporte à conexão com as Salas do Microsoft Teams e dispositivos Surface Hub usando o TLS 1.2.
- Os clientes do Skype for Business Server devem instalar uma CU (atualização cumulativa) para usar o TLS 1.2 para Sistemas de Salas do Teams e Surface Hub.

  - Para o Skype for Business Server 2015, a CU9 já foi lançada em maio de 2019.
  - Para o Skype for Business Server 2019, a CU1 estava planejada para abril de 2019, mas foi adiada para junho de 2019.

  > [!NOTE]
  > Os clientes do Skype for Business no local não devem desabilitar o TLS 1.0/1.1 antes de instalar CUs específicas para o Skype for Business Server.

Se estiver usando qualquer infraestrutura local para cenários híbridos ou Serviços de Federação do Active Directory, verifique se a infraestrutura pode oferecer suporte para as conexões de entrada e saída que usam TLS 1.2.

## <a name="references"></a>Referências

Os seguintes recursos fornecem instruções para ajudar a verificar se seus clientes estão usando TLS 1.2, ou uma versão posterior, e como desabilitar o TLS 1.0 e 1.1.

- Caso tenha clientes Windows 7 conectados ao Office 365, verifique se o TLS 1.2 é o protocolo seguro padrão do WinHTTP no Windows. Para obter mais informações, consulte [KB 3140245 – Atualização para habilitar o TLS 1.1 e TLS 1.2 como protocolos seguros padrão no WinHTTP no Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- Para começar a solucionar problemas de pouco uso de TLS ao remover a dependência do TLS 1.0 e 1.1, consulte [Suporte para TLS 1.2 na Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- A [nova funcionalidade de IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) facilita a descoberta de clientes no [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) e no [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) que se conectam ao serviço usando protocolos de segurança fracos.
- Obter mais informações sobre como [resolver o problema TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).
- Para obter informações gerais sobre nossa abordagem de segurança, acesse a [Central de Confiabilidade do Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparação para o preterimento do TLS 1.0/1.1 — Skype for Business do Office 365](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Diretrizes do Exchange Server TLS, parte 1: Preparação para o TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Diretrizes do Exchange Server TLS Parte 2: Habilitando o TLS 1.2 e identificando clientes que não o utilizam](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Diretrizes do Exchange Server TLS Parte 3: Desativando o TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Habilitar o suporte para TLS 1.1 e TLS 1.2 no Servidor do Office Online](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)