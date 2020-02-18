---
title: 'Etapa 4: Configurar o bypass de tráfego'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure os navegadores da web e os dispositivos de borda para executar bypass de tráfego dos locais confiáveis do Office 365.
ms.openlocfilehash: 71f62c5e245962f3514c49477e3cdeda17cb6397
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066678"
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


Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 5](../media/stepnumbers/Step5.png)|[Otimizar o desempenho do serviço entre o cliente e o Office 365](networking-optimize-tcp-performance.md) |



