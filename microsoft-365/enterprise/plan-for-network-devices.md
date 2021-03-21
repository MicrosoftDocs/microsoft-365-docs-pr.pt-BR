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
description: 'Resumo: descreve considerações sobre capacidade de rede, aceleradores WAN e dispositivos de balanceamento de carga usados para se conectar ao Office 365.'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927495"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>Plano para dispositivos de rede que se conectam aos serviços do Office 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*
  
Alguns hardwares de rede podem ter limitações no número de sessões simultâneas com suporte. Para organizações com mais de 2.000 usuários, recomendamos que elas monitorem seus dispositivos de rede para garantir que sejam capazes de lidar com o tráfego de serviço adicional do Office 365. O software de monitoramento SNMP (Simple Network Management Protocol) pode ajudá-lo a fazer isso.

Este artigo faz parte do [planejamento de rede e ajuste de desempenho do Office 365](./network-planning-and-performance.md).

As configurações de proxy de Internet de saída local também afetam a conectividade com os serviços do Office 365 para seus aplicativos cliente. Você também deve configurar seus dispositivos proxy de rede para permitir conexões para URLs e aplicativos de serviços de nuvem da Microsoft. Cada organização é diferente. Para ter uma ideia de como a Microsoft gerencia esse processo e a quantidade de largura de banda que provisionarmos, [leia o estudo de caso.](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)
  
Os seguintes artigos da Ajuda do Skype for Business têm mais informações sobre as configurações do Skype for Business:
  
- [Solução de problemas de erros de login do Skype for Business Online para administradores](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [Você não pode se conectar ao Skype for Business ou determinados recursos não funcionam, pois um firewall local bloqueia a conexão](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> Embora muitas dessas configurações sejam específicas do Skype for Business, as orientações gerais sobre a configuração de rede são úteis para todos os serviços do Office 365.
  
## <a name="determining-network-capacity"></a>Determinando a capacidade da rede

Cada dispositivo de rede que existe em uma conexão tem seu limite de capacidade. Esses dispositivos incluem adaptadores de rede de cliente e servidor, roteadores, comutadores e hubs que os interconectam. A capacidade de rede adequada significa que nenhum deles está saturado. O monitoramento da atividade de rede é essencial para ajudar a garantir que as cargas reais em todos os dispositivos de rede sejam menores do que a capacidade máxima. A capacidade da rede afeta o desempenho do dispositivo proxy.
  
Na maioria das situações, a largura de banda de conexão com a Internet define o limite para a quantidade de tráfego. O desempenho fraco durante o horário de pico provavelmente é causado pelo uso excessivo do link da Internet. Essa situação também se aplica a um cenário de filial, onde os computadores do servidor proxy de filial estão conectados ao dispositivo proxy na sede da filial por meio de um link WAN (Rede de Área Ampla) lento.
  
Para testar a capacidade da rede, monitore a atividade de rede na interface de rede proxy. Se for mais de 75% da largura de banda máxima de qualquer interface de rede, considere aumentar a largura de banda da infraestrutura de rede inadequada. Ou, considere o uso de recursos avançados, como compactação HTTP.
  
## <a name="wan-accelerators"></a>Aceleradores de WAN

Se sua organização usar dispositivos proxy de aceleração de rede de ampla área (WAN), você poderá encontrar problemas ao acessar os serviços do Office 365. Talvez seja necessário otimizar seu dispositivo de rede ou dispositivos para garantir que seus usuários tenham uma experiência consistente ao acessar o Office 365. Por exemplo, os serviços do Office 365 criptografam algum conteúdo do Office 365 e o header TCP. Seu dispositivo pode não ser capaz de lidar com esse tipo de tráfego.
  
Leia nossa instrução de suporte [sobre como usar o controlador de otimização wan ou dispositivos de tráfego/inspeção com o Office 365](https://support.microsoft.com/kb/2690045).
  
## <a name="hardware-and-software-load-balancing-devices"></a>Dispositivos de balanceamento de carga de hardware e software

Sua organização precisa usar um balanceador de carga de hardware (HLB) ou uma solução de Balanceamento de Carga de Rede (NLB) para distribuir solicitações para seus servidores do AD FS (Serviços de Federação do Active Directory) e/ou seus servidores híbridos do Exchange. Os dispositivos de balanceamento de carga controlam o tráfego de rede para os servidores locais. Esses servidores são cruciais para ajudar a garantir a disponibilidade de um único login e da implantação híbrida do Exchange.
  
Fornecemos uma solução NLB baseada em software integrada ao Windows Server. O Office 365 suporta esta solução para alcançar um balanceamento de carga.
  
## <a name="firewalls-and-proxies"></a>Firewalls e proxies

Para obter mais detalhes sobre como configurar firewalls e proxies para se conectar ao Office 365, leia [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Assessing Office 365 network connectivity](assessing-network-connectivity.md), and [Office 365 endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) to learn more about devices and circuit selection.
  
## <a name="see-also"></a>Confira também

[Guias de instalação para serviços do Office 365](setup-guides-for-microsoft-365.md)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)