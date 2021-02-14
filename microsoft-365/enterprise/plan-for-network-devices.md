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
description: 'Resumo: Descreve considerações sobre capacidade de rede, aceleradores de WAN e dispositivos de balanceamento de carga usados para se conectar ao Office 365.'
ms.openlocfilehash: a4ea75eb294d74004125be4d258dbe86d7d89810
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687169"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Plano para dispositivos de rede que se conectam aos serviços do Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*
  
Alguns hardwares de rede podem ter limitações no número de sessões simultâneas com suporte. Para organizações com mais de 2.000 usuários, recomendamos que monitorem seus dispositivos de rede para garantir que sejam capazes de lidar com o tráfego de serviço adicional do Office 365. O software de monitoramento SNMP (Simple Network Management Protocol) pode ajudá-lo a fazer isso.

Este artigo faz parte do [planejamento de rede e do ajuste de desempenho do Office 365.](https://aka.ms/tune)

As configurações de proxy de Internet de saída locais também afetam a conectividade com os serviços do Office 365 para seus aplicativos cliente. Você também deve configurar seus dispositivos de proxy de rede para permitir conexões para APLICATIVOs e URLs de serviços de nuvem da Microsoft. Cada organização é diferente. Para ter uma ideia de como a Microsoft gerencia esse processo e a quantidade de largura de banda que provisionarmos, [leia o estudo de caso.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
Os seguintes artigos da Ajuda do Skype for Business têm mais informações sobre as configurações do Skype for Business:
  
- [Solução de problemas de erros de login do Skype for Business Online para administradores](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Você não pode se conectar ao Skype for Business ou determinados recursos não funcionam, porque um firewall local bloqueia a conexão](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Embora muitas dessas configurações sejam específicas do Skype for Business, a orientação geral sobre a configuração de rede é útil para todos os serviços do Office 365.
  
## <a name="determining-network-capacity"></a>Determinando a capacidade da rede

Cada dispositivo de rede existente em uma conexão tem seu limite de capacidade. Esses dispositivos incluem os adaptadores de rede do cliente e do servidor, roteadores, comutadores e hubs que os interconectam. Capacidade de rede adequada significa que nenhuma delas está saturada. O monitoramento da atividade de rede é essencial para ajudar a garantir que as cargas reais em todos os dispositivos de rede sejam menores do que sua capacidade máxima. A capacidade da rede afeta o desempenho do dispositivo proxy.
  
Na maioria das situações, a largura de banda da conexão com a Internet define o limite para a quantidade de tráfego. O desempenho fraco durante os horários de pico de tráfego provavelmente é causado pelo uso excessivo do link da Internet. Essa situação também se aplica a um cenário de filial, em que os computadores do servidor proxy de filial estão conectados ao dispositivo proxy na sede da filial por um link lento de Rede de Área Ampla (WAN).
  
Para testar a capacidade da rede, monitore a atividade de rede na interface de rede proxy. Se for mais de 75% da largura de banda máxima de qualquer interface de rede, considere aumentar a largura de banda da infraestrutura de rede inadequada. Ou considere o uso de recursos avançados, como compactação HTTP.
  
## <a name="wan-accelerators"></a>Aceleradores de WAN

Se sua organização usa dispositivos de proxy de aceleração wan, você pode encontrar problemas ao acessar os serviços do Office 365. Talvez seja necessário otimizar seus dispositivos ou dispositivos de rede para garantir que seus usuários tenham uma experiência consistente ao acessar o Office 365. Por exemplo, os serviços do Office 365 criptografam parte do conteúdo do Office 365 e o header TCP. Seu dispositivo pode não ser capaz de lidar com esse tipo de tráfego.
  
Leia nossa declaração de suporte sobre como usar [o controlador de otimização de WAN ou dispositivos de tráfego/inspeção com o Office 365.](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivos de balanceamento de carga de hardware e software

Sua organização precisa usar um balanceador de carga de hardware (HLB) ou uma solução de Balanceamento de Carga de Rede (NLB) para distribuir solicitações aos servidores dos Serviços de Federação do Active Directory (AD FS) e/ou servidores híbridos do Exchange. Os dispositivos de balanceamento de carga controlam o tráfego de rede para os servidores locais. Esses servidores são cruciais para ajudar a garantir a disponibilidade do single sign-on e da implantação híbrida do Exchange.
  
Fornecemos uma solução NLB baseada em software integrada ao Windows Server. O Office 365 suporta esta solução para alcançar um balanceamento de carga.
  
## <a name="firewalls-and-proxies"></a>Firewalls e proxies

Para obter mais detalhes sobre como configurar firewalls e proxies para se conectar ao Office 365, leia Gerenciar pontos de extremidade do [Office 365,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)avaliar a conectividade de rede do [Office 365](assessing-network-connectivity.md)e perguntas frequentes sobre pontos de extremidade do [Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) para saber mais sobre dispositivos e seleção de circuitos.
  
## <a name="see-also"></a>Confira também

[Guias de configuração para serviços do Office 365](setup-guides-for-microsoft-365.md)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
