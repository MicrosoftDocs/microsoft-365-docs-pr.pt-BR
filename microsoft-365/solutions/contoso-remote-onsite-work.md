---
title: Resposta COVID-19 da Contoso e suporte para trabalho remoto e local
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda como a Contoso Corporation respondeu à pandmicro de COVID-19 e projetou sua infraestrutura de instalação e atualização de software para trabalho remoto e local.
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580668"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Resposta COVID-19 da Contoso e suporte para trabalho remoto e local

A Contoso sempre havia suportado seus funcionários remotos, que acessam recursos locais por meio de um servidor VPN central na sede de Paris. A Contoso emitiu um laptop gerenciado para todos os funcionários remotos. Os funcionários locais tinham uma mistura de computadores desktop e laptops.

## <a name="contosos-response-to-covid-19"></a>Resposta da Contoso ao COVID-19

Com o início da pandmicromic COVID-19, de repente todos os funcionários, mas essenciais, eram funcionários remotos. A Contoso respondeu deslocando sua força de trabalho para trabalhar em casa e conduzir suas atividades principais por meio do acesso remoto aos recursos locais e online usando os serviços de nuvem do Microsoft 365.

A Contoso tinha servidores VPN de acesso remoto no escritório da sede de Paris para dar suporte a 25% de sua força de trabalho já remota, mas rapidamente se moveu para ampliar sua capacidade de acesso remoto para suportar 90% de sua força de trabalho. A Contoso implantou servidores VPN de acesso remoto em cada escritório satélite para que os funcionários remotos usem um ponto de entrada de fechamento regional para acessar a intranet da Contoso.

A Contoso também atualizou a configuração de clientes VPN instalados em laptops, tablets e smartphones para túnel dividido para que o tráfego para o conjunto otimizar pontos de extremidade do Office 365 ignorava a conexão VPN e era enviado diretamente pela Internet. Para saber mais, confira [Otimizar a conectividade do Office 365](../enterprise/microsoft-365-vpn-split-tunnel.md)para usuários remotos usando o túnel dividido de VPN.

Esta é a configuração resultante com dispositivos VPN instalados na sede de Paris e em cada uma das filiais. 

![Infraestrutura VPN da Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Um trabalhador remoto com o cliente VPN instalado usa o DNS para encontrar o escritório regionalmente mais próximo e se conecta ao dispositivo VPN instalado lá. Com o túnel dividido, o tráfego para os pontos de extremidade do Microsoft 365 Optimize é enviado diretamente para o local de rede do Microsoft 365 regionalmente mais próximo. Todos os outros tráfegos são enviados pela conexão VPN ao dispositivo VPN.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Suporte da Contoso para trabalho remoto e local

Depois que as alterações iniciais foram feitas para dar suporte principalmente a funcionários remotos durante bloqueios regionais, a Contoso fez alterações na infraestrutura para dar suporte ao trabalho remoto e local no qual um trabalhador poderia ser:

- Sempre remoto.
- Sempre no local.
- Uma combinação de local e remoto.

Os recursos de identidade, segurança e conformidade do Microsoft 365 foram projetados para a Confiança Zero e para funcionar independentemente da localização do usuário e do dispositivo. Para obter mais informações, consulte [Confiança Zero.](https://www.microsoft.com/security/business/zero-trust)

No entanto, o gerenciamento de novas instalações e atualizações de software depende do local do dispositivo porque o software a ser instalado pode vir de uma fonte local ou de uma fonte da Internet. Os arquitetos de TI da Contoso projetaram sua nova infraestrutura de instalação e atualização com base na localização do dispositivo, em vez do trabalhador.

Eles designam dois tipos de dispositivos: local dedicado e roaming.

### <a name="dedicated-on-premises"></a>Local dedicado

Um dispositivo local dedicado é um computador desktop ou servidor que nunca sai da intranet da Contoso e não tem um cliente VPN instalado. Esses dispositivos locais continuam a usar o Microsoft Endpoint Configuration Manager e seus pontos de distribuição para instalações e atualizações do Windows 10, do Microsoft 365 Apps para empresas e do navegador Edge.

### <a name="roaming"></a>Roaming

Um dispositivo móvel pode deixar a intranet da Contoso e inclui laptops emitidos para muitos funcionários do escritório e todos os funcionários remotos e outros dispositivos de propriedade da organização, como smartphones e tablets com o cliente VPN da Contoso instalado. 

Como esses dispositivos podem ser conectados à Internet a qualquer momento, eles usam o Intune ou outros serviços baseados em nuvem para instalar e atualizar o Windows 10, o Microsoft 365 Apps para empresas e o Edge. Eles não usam os pontos de distribuição existentes do Configuration Manager local.

Isso significa que algumas das instalações e atualizações para dispositivo móvel serão feitas pela Internet enquanto eles estão no local e conectados à intranet. Mas os arquitetos de TI da Contoso decidiram que a simplicidade da configuração era mais importante do que a otimização da largura de banda da intranet para a Internet, especialmente quando a maioria dos funcionários remotos raramente está conectada à intranet.

Esta é a infraestrutura resultante.

![Infraestrutura de atualizações e instalação da Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

O comportamento de instalação e atualização é determinado tornando as contas de computador dos dispositivos um membro de um desses grupos:

- OnPremDevices

  O cliente do Configuration Manager no dispositivo usa pontos de distribuição para instalação e atualizações.

- RoamingDevices

  O Intune e outras configurações no dispositivo especificam o uso da rede do Microsoft 365 para instalar e atualizar.

## <a name="new-onboarding-process"></a>Novo processo de integração

Para um novo dispositivo local dedicado emitido para um novo trabalhador ou para um novo servidor em um datacenter, quando o trabalhador entrar, o cliente do Configuration Manager com base na associação do dispositivo no grupo OnPremDevices baixa e instala as atualizações mais recentes para o Windows 10, o Microsoft 365 Apps para empresas e o Edge a partir dos pontos de distribuição do Configuration Manager local. Quando concluído, o dispositivo local dedicado está pronto para uso e usa esses pontos de distribuição para atualizações contínuas.

Para um novo dispositivo remoto emitido para um novo trabalhador, quando o trabalhador entrar, o dispositivo, com base em sua associação ao grupo RoamingDevices, contata o serviço de nuvem do Intune e outros serviços e baixa e instala as atualizações mais recentes para o Windows 10, o Microsoft 365 Apps para empresas e o Edge. Quando concluído, o dispositivo remoto está pronto para uso e usa o cliente VPN instalado para acessar recursos locais e a rede do Microsoft 365 para atualizações contínuas.

## <a name="next-step"></a>Próxima etapa

[Capacite os funcionários remotos](empower-people-to-work-remotely.md) em sua organização.
