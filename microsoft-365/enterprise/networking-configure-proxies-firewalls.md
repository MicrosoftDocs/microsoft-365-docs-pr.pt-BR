---
title: 'Etapa 4: Configurar o bypass de tráfego'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure os navegadores da web e os dispositivos de borda para executar bypass de tráfego dos locais confiáveis do Office 365.
ms.openlocfilehash: 8486b5c0da9e44ed0b9ee42feb7acbfd21445010
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291584"
---
# <a name="step-4-configure-traffic-bypass"></a>Etapa 4: Configurar o bypass de tráfego

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Como o tráfego geral da Internet pode ser arriscado, as redes de organizações típicas reforçam a segurança com dispositivos de borda, como servidores proxy, interrupção e inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados. Leia sobre alguns dos problemas com dispositivos de interceptação de rede em Usar soluções ou dispositivos de rede de terceiros em tráfego do Office 365.

No entanto, os endereços IP e nomes de domínio DNS usados pelos serviços de nuvem do Microsoft 365 são conhecidos. Além disso, o tráfego e os serviços por si só são protegidos por vários recursos de segurança. Como essa proteção e segurança já está em funcionamento, os dispositivos de borda não precisam duplicá-la. Os destinos intermediários e o processamento de segurança duplicado do tráfego do Microsoft 365 podem reduzir significativamente o desempenho.

A primeira etapa para eliminar destinos intermediários e processamento de segurança duplicado é identificar o tráfego do Microsoft 365. A Microsoft definiu os seguintes intervalos de endereços IP e tipos de nomes de domínio de DNS, conhecidos como pontos de extremidade:

- **Otimizar** - necessário para a conectividade com todos os serviços do Office 365 e representa mais de 75% da largura de banda, conexões e volume de dados do Microsoft 365. Esses pontos de extremidade representam os cenários do Microsoft 365 mais importantes no desempenho, latência e disponibilidade da rede.
- **Permitir** - necessário para a conectividade com os recursos e serviços específicos do Microsoft 365, mas não são tão sensíveis ao desempenho e à latência da rede quanto os da categoria Otimizar.
 - **Padrão** - representam os serviços e dependências do Microsoft 365 que não precisam de otimização. Você pode considerar os pontos de extremidade de categoria padrão como tráfego normal da Internet.

Você pode encontrar os intervalos de endereços IP e os nomes de domínio DNS em [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).

A Microsoft recomenda que você:

- Use scripts PAC (configuração automática de Proxy) nos navegadores da Internet dos computadores no local para executar o bypass dos servidores proxy para os nomes de domínio DNS dos serviços baseados na nuvem do Microsoft 365. Para obter o script PAC mais recente do Microsoft 365, confira o script Get-Pacfile do PowerShell.
- Analise seus dispositivos de borda para determinar o processamento duplicado e configure-os para encaminhar o tráfego sem processamento para os pontos de extremidade Otimizar e Permitir, o que é conhecido como executar o bypass de tráfego. 

Os dispositivos de borda incluem firewalls, interrupção e inspeção de SSL, dispositivos de inspeção empacotados e sistemas de prevenção de perda de dados. Para configurar e atualizar as configurações de dispositivos de borda, você pode usar um script ou uma chamada REST para consumir uma lista estruturada de pontos de extremidade do serviço Web de Pontos de extremidade do Office 365. Para saber mais, confira [URL do serviço Web e endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

Observe que você está apenas ignorando o processamento normal de segurança de rede e proxy do tráfego para os pontos de extremidade da categoria Otimizar e Permitir do Microsoft 365. Todo o outro tráfego geral da Internet será intermediado por proxy e estará sujeito ao processamento existente de segurança da rede.


Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Otimizar o desempenho do serviço entre o cliente e o Office 365](networking-optimize-tcp-performance.md) |



