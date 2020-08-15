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

Anteriormente, as diretrizes sugeriam que o número máximo de clientes do Exchange que você deve usar por endereço IP para se conectar ao Office 365 foi de cerca de 2.000 clientes por porta de rede.
  
## <a name="why-use-nat"></a>Por que usar o NAT?

Usando o NAT, milhares de pessoas em uma rede corporativa podem "compartilhar" alguns endereços IP roteáveis publicamente.
  
A maioria das redes corporativas usa o espaço de endereço IP privado (RFC1918). O espaço de endereçamento privado é alocado pela autoridade de números atribuídos da Internet (IANA) e destinado exclusivamente a redes que não roteiam diretamente para e da Internet global.
  
Para fornecer acesso à Internet para dispositivos em um espaço de endereço IP privado, as organizações usam tecnologias de gateway como firewalls e proxies que fornecem NAT (conversão de endereço de rede) ou serviços PAT (conversão de endereço de porta). Esses gateways fazem com que o tráfego de dispositivos internos para a Internet (incluindo o Office 365) pareça estar vindo de um ou mais endereços IP roteáveis publicamente. Cada conexão de saída de um dispositivo interno é traduzida para uma porta TCP de origem diferente no endereço IP público. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Por que você precisa ter tantas conexões abertas para o Office 365 ao mesmo tempo?

O Outlook pode abrir oito ou mais conexões (em situações em que há suplementos, calendários compartilhados, caixas de correio, etc.). Como há um máximo de 64.000 portas disponíveis em um dispositivo NAT baseado no Windows, pode haver no máximo 8.000 usuários atrás de um endereço IP antes que as portas sejam esgotadas. Observe que, se os clientes estiverem usando dispositivos baseados no sistema operacional não Windows para NAT, o total de portas disponíveis dependerá do tipo de dispositivo ou software NAT que está sendo usado. Neste cenário, o número máximo de portas pode ser menor que 64.000. A disponibilidade de portas também é afetada por outros fatores, como o Windows, restringindo 4.000 portas para seu próprio uso, o que reduz o número total de portas disponíveis para 60.000. Pode haver outros aplicativos, como o Internet Explorer, que podem se conectar ao mesmo tempo, exigindo portas adicionais.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Calculando o máximo de dispositivos suportados por trás de um único endereço IP público com o Office 365

Para determinar o número máximo de dispositivos por trás de um único endereço IP público, você deve monitorar o tráfego de rede para determinar o consumo de porta de pico por cliente. Além disso, um fator de pico deve ser usado para o uso da porta (mínimo 4). 
  
 **Use a seguinte fórmula para calcular o número de dispositivos com suporte por endereço IP:**
  
Máximo de dispositivos suportados por trás de um único endereço IP público = (portas restritas de 64.000)/(consumo de porta de pico + fator de pico)
  
 **Por exemplo, se o seguinte foi verdadeiro:**
  
- **Portas restritas:** 4.000 para o sistema operacional

- **Consumo de porta de pico:** 6 por dispositivo

- **Fator de pico:** 4

Em seguida, o máximo de dispositivos suportados por trás de um único endereço IP público = (64.000-4000)/(6 + 4) = 6.000
  
Com o lançamento do pacote de hospedagem do Office 365, incluído nas atualizações de setembro de 2011 para o Microsoft Office Outlook 2007 ou de novembro de 2011 para o Microsoft Outlook 2010, ou uma atualização posterior, o número de conexões do Outlook (tanto do Office Outlook 2007 com o Service Pack 2 e o Outlook 2010) para o Exchange pode ser apenas 2. Você precisará fatorar os diferentes sistemas operacionais, comportamentos de usuário e assim por diante para determinar o número mínimo e máximo de portas que sua rede precisará em pico.
  
Se você quiser dar suporte a mais dispositivos por trás de um único endereço IP público, siga as etapas descritas para avaliar o número máximo de dispositivos que podem ser suportados:
  
Monitorar o tráfego de rede para determinar o consumo de porta de pico por cliente. Você deve coletar estes dados:
  
- De vários locais
    
- De vários dispositivos
    
- Em vários momentos
    
Use a fórmula anterior para calcular o número máximo de usuários por endereço IP que podem ser suportados em seu ambiente.
  
Há vários métodos para distribuir a carga do cliente entre endereços IP públicos adicionais. As estratégias disponíveis dependem dos recursos da solução de gateway corporativo. A solução mais simples é segmentar o espaço de endereço do usuário e "atribuir" estaticamente um número de endereços IP a cada gateway. Outra alternativa que muitos dispositivos de gateway oferecem é a capacidade de usar um pool de endereços IP. O benefício do pool de endereços é que ele é muito mais dinâmico e é menos provável de exigir ajuste à medida que a sua base de usuários cresce.
  
## <a name="see-also"></a>Confira também

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
