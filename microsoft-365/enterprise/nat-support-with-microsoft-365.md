---
title: Suporte NAT com o Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: Este artigo fornece detalhes sobre como aproximar o número de clientes que você pode usar por endereço IP em sua organização usando NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686914"
---
# <a name="nat-support-with-office-365"></a>Suporte NAT com o Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Anteriormente, as diretrizes sugeriam que o número máximo de clientes Exchange você deve usar por endereço IP para se conectar ao Office 365 era de cerca de 2.000 clientes por porta de rede.
  
## <a name="why-use-nat"></a>Por que usar NAT?

Usando o NAT, milhares de pessoas em uma rede corporativa podem "compartilhar" alguns endereços IP publicamente routable.
  
A maioria das redes corporativas usa espaço de endereço IP privado (RFC1918). O espaço de endereço privado é alocado pela Autoridade de Números Atribuídos à Internet (IANA) e destinado exclusivamente a redes que não são roteadas diretamente para e para a Internet global.
  
Para fornecer acesso à Internet a dispositivos em um espaço de endereço IP privado, as organizações usam tecnologias de gateway, como firewalls e proxies que fornecem serviços nat (conversão de endereço de rede) ou serviços de conversão de endereço de porta (PAT). Esses gateways fazem com que o tráfego de dispositivos internos para a Internet (incluindo Office 365) pareça estar vindo de um ou mais endereços IP publicamente routable. Cada conexão de saída de um dispositivo interno é traduzida para uma porta TCP de origem diferente no endereço IP público. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Por que você precisa ter tantas conexões abertas Office 365 ao mesmo tempo?

Outlook pode abrir oito ou mais conexões (em situações em que há complementos, calendários compartilhados, caixas de correio etc.). Como há no máximo 64.000 portas disponíveis em um dispositivo NAT baseado em Windows, pode haver no máximo 8.000 usuários atrás de um endereço IP antes que as portas sejam esgotadas. Observe que, se os clientes estão usando dispositivos não baseados em Windows so para NAT, o total de portas disponíveis dependerá do dispositivo NAT ou software que está sendo usado. Nesse cenário, o número máximo de portas pode ser menor que 64.000. A disponibilidade de portas também é afetada por outros fatores, como Windows restrição de 4.000 portas para uso próprio, o que reduz o número total de portas disponíveis para 60.000. Pode haver outros aplicativos, como o Internet Explorer, que podem se conectar ao mesmo tempo, exigindo portas adicionais.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Calculando os dispositivos com suporte máximo por trás de um único endereço IP público com Office 365

Para determinar o número máximo de dispositivos atrás de um único endereço IP público, você deve monitorar o tráfego de rede para determinar o pico de consumo de porta por cliente. Além disso, um fator de pico deve ser usado para o uso da porta (mínimo 4). 
  
 **Use a seguinte fórmula para calcular o número de dispositivos com suporte por endereço IP:**
  
Máximo de dispositivos com suporte atrás de um único endereço IP público = (64.000 - portas restritas)/(Consumo de porta de pico + fator de pico)
  
 **Por exemplo, se o seguinte fosse verdadeiro:**
  
- **Portas restritas:** 4.000 para o sistema operacional

- **Pico de consumo de porta:** 6 por dispositivo

- **Fator de pico:** 4

Em seguida, os dispositivos com suporte máximo atrás de um único endereço IP público = (64.000 - 4.000)/(6 + 4) = 6.000
  
Com o lançamento do pacote de hospedagem do Office 365, incluído nas atualizações de setembro de 2011 para o Microsoft Office Outlook 2007 ou novembro de 2011 para Microsoft Outlook 2010, ou uma atualização posterior, o número de conexões do Outlook (Office Outlook 2007 com Service Pack 2 e Outlook 2010) para Exchange pode ser tão poucos quanto 2. Você precisará fatorar os diferentes sistemas operacionais, comportamentos do usuário e assim por diante para determinar o número mínimo e máximo de portas que sua rede exigirá no pico.
  
Se você deseja dar suporte a mais dispositivos atrás de um único endereço IP público, siga as etapas descritas para avaliar o número máximo de dispositivos que podem ser suportados:
  
Monitore o tráfego de rede para determinar o pico de consumo de porta por cliente. Você deve coletar esses dados:
  
- De vários locais
    
- De vários dispositivos
    
- Em várias vezes
    
Use a fórmula anterior para calcular o máximo de usuários por endereço IP que podem ser suportados em seu ambiente.
  
Há vários métodos para distribuir a carga do cliente em endereços IP públicos adicionais. As estratégias disponíveis dependem dos recursos da solução de gateway corporativo. A solução mais simples é segmentar o espaço de endereço do usuário e "atribuir" estáticamente um número de endereços IP a cada gateway. Outra alternativa que muitos dispositivos gateway oferecem é a capacidade de usar um pool de endereços IP. O benefício do pool de endereços é que ele é muito mais dinâmico e menos provável de exigir ajuste à medida que sua base de usuários aumenta.
  
## <a name="see-also"></a>Confira também

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
