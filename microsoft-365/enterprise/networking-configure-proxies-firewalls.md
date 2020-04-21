---
title: 'Etapa 4: Configurar o bypass de tráfego'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure os navegadores da web e os dispositivos de borda para executar bypass de tráfego dos locais confiáveis do Office 365.
ms.openlocfilehash: 68e8f7868e0b0f7b3da80bd5f19b18f261b1b05c
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583388"
---
# <a name="step-4-configure-traffic-bypass"></a>Etapa 4: Configurar o bypass de tráfego

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Como o tráfego geral da Internet pode ser arriscado, as redes de organizações típicas reforçam a segurança com dispositivos de borda, como servidores proxy, Interrupção e Inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados. Leia sobre alguns dos problemas com dispositivos de interceptação de rede em [Usar soluções ou dispositivos de rede de terceiros em tráfego do Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

No entanto, os endereços IP e nomes de domínio DNS usados pelos serviços de nuvem do Microsoft 365 são conhecidos. Além disso, o tráfego e os serviços por si só são protegidos por vários recursos de segurança. Como essa proteção e segurança já está em funcionamento, os dispositivos de borda não precisam duplicá-la. Os destinos intermediários e o processamento de segurança duplicado do tráfego do Microsoft 365 podem reduzir significativamente o desempenho.

A primeira etapa para eliminar destinos intermediários e processamento de segurança duplicado é identificar o tráfego do Microsoft 365. A Microsoft definiu os seguintes intervalos de endereços IP e tipos de nomes de domínio de DNS, conhecidos como pontos de extremidade:

- **Otimizar** - necessário para a conectividade com todos os serviços do Office 365 e representa mais de 75% da largura de banda, conexões e volume de dados do Microsoft 365. Esses pontos de extremidade representam os cenários do Microsoft 365 mais confidenciais para o desempenho, latência e disponibilidade da rede.
- **Permitir** - necessário para a conectividade com os recursos e serviços específicos do Microsoft 365, mas não são tão sensíveis ao desempenho e à latência da rede quanto os da categoria Otimizar.
 - **Padrão** - representam os serviços e dependências do Microsoft 365 que não precisam de otimização. Você pode considerar os pontos de extremidade de categoria padrão como tráfego normal da Internet.

Você pode encontrar os intervalos de endereços IP e os nomes de domínio DNS em [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

A Microsoft recomenda que você:

- Use scripts de Configuração Automática de Proxy (PAC) nos navegadores da Internet dos computadores no local para executar o bypass dos servidores proxy para os nomes de domínio DNS dos serviços baseados na nuvem do Microsoft 365. Para obter o script PAC mais recente do Microsoft 365, confira [Script Get-Pacfile do PowerShellt](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

- Analise seus dispositivos de borda para determinar o processamento duplicado e configure-os para encaminhar o tráfego sem processamento para os pontos de extremidade Otimizar e Permitir, o que é conhecido como executar o bypass de tráfego. 

Estas são as recomendações da sua infraestrutura de rede.

![Recomendações para otimizar o tráfego local](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

Os dispositivos de borda incluem firewalls, Interrupção e Inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados. Para configurar e atualizar as configurações de dispositivos de borda, é possível usar um script ou uma chamada REST para consumir uma lista estruturada de pontos de extremidade do serviço Web de pontos de extremidade do Office 365. Para obter mais informações, confira [Serviço Web de URL e Endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

Observe que você está apenas ignorando o processamento normal de segurança de rede e proxy do tráfego para os pontos de extremidade da categoria Otimizar e Permitir do Microsoft 365. Todo o outro tráfego geral da Internet será intermediado por proxy e estará sujeito ao processamento existente de segurança da rede.

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a>Otimizando o tráfego para funcionários remotos que usam conexões VPN

As conexões VPN (rede virtual privada) são comumente usadas por funcionários remotos para acessar os recursos na intranet de uma organização. Uma conexão VPN convencional roteia todo o tráfego, incluindo o tráfego da Internet, para a intranet da organização. O tráfego de Internet é encaminhado para a rede de borda da organização e dispositivos de processamento de pacotes. Esse tráfego está sujeito a atrasos de viagens e processamentos que podem reduzir drasticamente o desempenho e afetar a produtividade dos funcionários remotos. 

O tunelamento dividido é a capacidade de uma conexão VPN para direcionar o tráfego especificado pela Internet, em vez de enviá-lo pela VPN para a sua intranet. Para obter o melhor desempenho para funcionários remotos a serviços essenciais do Microsoft 365, como Teams, SharePoint Online e Exchange Online, configure suas conexões VPN de túnel dividido para enviar o tráfego para otimizar os pontos de extremidade do Office 365 diretamente pela Internet. 

Para informações mais detalhadas, confira [Otimizar a conectividade do Office 365 para usuários remotos usando a criação de túnel dividido de VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).

Para testar o quão perto você está de um ponto de entrada da rede global da Microsoft e o quão perto você está do ponto em que a rede da sua organização se conecta ao seu ISP, use a [ferramenta de Integração de Rede do Office 365](https://connectivity.office.com/).

Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 5](../media/stepnumbers/Step5.png)|[Otimizar o desempenho do serviço entre o cliente e o Office 365](networking-optimize-tcp-performance.md) |



