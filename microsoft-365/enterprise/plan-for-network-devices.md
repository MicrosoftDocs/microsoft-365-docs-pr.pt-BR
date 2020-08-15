---
title: Plano para dispositivos de rede que se conectam aos serviços do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 'Resumo: descreve as considerações de capacidade de rede, aceleradores de WAN e dispositivos de balanceamento de carga usados para se conectar ao Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687169"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Plano para dispositivos de rede que se conectam aos serviços do Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*
  
Alguns hardwares de rede podem ter limitações quanto ao número de sessões simultâneas suportadas. Para organizações com mais de 2.000 usuários, recomendamos que eles monitorem seus dispositivos de rede para garantir que eles sejam capazes de lidar com o tráfego de serviço adicional do Office 365. O software de monitoramento do protocolo SNMP pode ajudá-lo a fazer isso.

Este artigo faz parte do [planejamento de rede e do ajuste de desempenho do Office 365](https://aka.ms/tune).

As configurações de proxy da Internet de saída local também afetam a conectividade com os serviços do Office 365 para seus aplicativos cliente. Você também deve configurar seus dispositivos de proxy de rede para permitir conexões para aplicativos e URLs de serviços de nuvem da Microsoft. Cada organização é diferente. Para ter uma ideia de como a Microsoft gerencia esse processo e a quantidade de largura de banda que fazemos, [Leia o estudo de caso](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).
  
Os seguintes artigos da ajuda do Skype for Business têm mais informações sobre as configurações do Skype for Business:
  
- [Solucionando problemas de erros de entrada do Skype for Business online para administradores](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Você não pode se conectar ao Skype for Business ou determinados recursos não funcionam porque um firewall local bloqueia a conexão](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Embora muitas dessas configurações sejam específicas do Skype for Business, a orientação geral sobre a configuração de rede é útil para todos os serviços do Office 365.
  
## <a name="determining-network-capacity"></a>Determinando a capacidade da rede

Todos os dispositivos de rede que existem em uma conexão têm seu limite de capacidade. Esses dispositivos incluem adaptadores de rede de cliente e de servidor, roteadores, comutadores e hubs que os interconectam. A capacidade de rede adequada significa que nenhuma delas é saturada. O monitoramento da atividade de rede é essencial para ajudar a garantir que as cargas reais em todos os dispositivos de rede sejam menores do que sua capacidade máxima. A capacidade de rede afeta o desempenho do dispositivo de proxy.
  
Na maioria das situações, a largura de banda de conexão com a Internet define o limite para o volume de tráfego. O desempenho fraco durante as horas de tráfego de pico provavelmente é causado pelo uso excessivo do link da Internet. Essa situação também se aplica a um cenário de filial, onde os computadores do servidor proxy de filial do escritório estão conectados ao dispositivo proxy na matriz da filial através de um link de rede de longa distância (WAN) lento.
  
Para testar a capacidade da rede, monitore a atividade de rede na interface de rede de proxy. Se for mais de 75% da largura de banda máxima de qualquer interface de rede, considere aumentar a largura de banda da infraestrutura de rede inadequada. Ou, considere usar recursos avançados, como a compactação HTTP.
  
## <a name="wan-accelerators"></a>Aceleradores de WAN

Se sua organização usa dispositivos proxy de aceleração de rede de longa distância (WAN), você pode encontrar problemas ao acessar os serviços do Office 365. Talvez seja necessário otimizar o dispositivo ou dispositivos de rede para garantir que os usuários tenham uma experiência consistente ao acessar o Office 365. Por exemplo, os serviços do Office 365 criptografam alguns conteúdos do Office 365 e o cabeçalho TCP. O dispositivo pode não ser capaz de lidar com esse tipo de tráfego.
  
Leia nossa declaração de suporte sobre o [uso do controlador de otimização WAN ou dispositivos de tráfego/inspeção com o Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivos de balanceamento de carga de hardware e software

Sua organização precisa usar um balanceador de carga de hardware (HLB) ou uma solução de balanceamento de carga de rede (NLB) para distribuir solicitações aos seus servidores de serviços de Federação do Active Directory (AD FS) e/ou seus servidores híbridos do Exchange. Os dispositivos de balanceamento de carga controlam o tráfego de rede para os servidores locais. Esses servidores são cruciais para ajudar a garantir a disponibilidade de logon único e a implantação híbrida do Exchange.
  
Fornecemos uma solução NLB baseada em software incorporada ao Windows Server. O Office 365 suporta esta solução para alcançar um balanceamento de carga.
  
## <a name="firewalls-and-proxies"></a>Firewalls e proxies

Para obter mais detalhes sobre a configuração de firewalls e proxies para se conectar ao Office 365, leia [Gerenciamento do office 365 pontos de extremidade](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [avaliação da conectividade de rede do Office 365](assessing-network-connectivity.md)e [perguntas frequentes sobre os pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) para saber mais sobre dispositivos e seleção de circuitos.
  
## <a name="see-also"></a>Confira também

[Guias de configuração para os serviços do Office 365](setup-guides-for-microsoft-365.md)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
