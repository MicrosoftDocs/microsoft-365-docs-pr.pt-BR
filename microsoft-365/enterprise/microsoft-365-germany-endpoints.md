---
title: Pontos de extremidade do Office 365 para Alemanha
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: Neste artigo, você encontrará pontos de extremidade acessíveis para clientes que usam o Office 365 na Alemanha.
hideEdit: true
ms.openlocfilehash: deabb590376a46580a2cd9d4a5dc498aacc3c5ef
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597041"
---
# <a name="office-365-germany-endpoints"></a>Pontos de extremidade do Office 365 Alemanha

 *Aplica-se a: Administrador do Office 365*

O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis somente para clientes que usam planos do **Office 365 Germany.**
  
 **Pontos de extremidade do Office 365:** [global (incluindo GCC)](urls-and-ip-address-ranges.md)  | [Office 365 operado pela 21 Vianet](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 Alemanha*  |  [Office 365 Governo dos E.U.A. Departamento de Defesa](microsoft-365-u-s-government-dod-endpoints.md) | [GCC High do Office 365 Governo dos E.U.A.](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Última atualização:** 12/01/2020 - Assinatura do Log de Alterações ![ ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [do](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) RSS |**Baixar:** todos os destinos obrigatórios e opcionais em uma lista [no formato em JSON](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Comece com o Gerenciamento de pontos de extremidade do [Office 365](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando esses dados. Os dados de pontos de extremidade são atualizados conforme necessário no início de cada mês com novos Endereços IP e URLs publicadas 30 dias antes de estarem ativos. Isso permite que os clientes que ainda não tenham atualizações automatizadas concluam seus processos antes que a nova conectividade seja necessária. Os pontos de extremidade também podem ser atualizados durante o mês, se necessário para lidar com escalonamentos de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Você sempre pode se referir à assinatura [de log de alterações.](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

Os dados mostrados nesta página abaixo são todos gerados a partir dos serviços Web baseados em REST. Se você estiver usando um script ou um dispositivo de rede para acessar esses dados, acesse o [serviço Web diretamente.](microsoft-365-ip-web-service.md)

Os dados do ponto de extremidade abaixo listam os requisitos de conectividade do computador de um usuário para o Office 365. Ele não inclui conexões de rede da Microsoft em uma rede do cliente, às vezes chamadas de conexões de rede híbridas ou de entrada.

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: Mostra se o conjunto de terminais está classificado como "Otimizar", "Permitir" ou "Padrão". Você pode ler sobre essas categorias e orientações para o gerenciamento delas em [https://aka.ms/pnc](https://aka.ms/pnc). Esta coluna também lista quais conjuntos de terminais são necessários para se ter conectividade de rede. Quanto aos conjuntos de terminais que não precisam ter conectividade de rede, fornecemos notas neste campo para indicar qual funcionalidade faltaria se o conjunto de terminais estivesse bloqueado. Se você excluir uma área de serviço inteira, os conjuntos de terminais listados conforme necessário não exigirão conectividade.

- **ER**: Aqui, você verá um **Sim** se o conjunto de pontos de extremidade tem suporte no Azure ExpressRoute com prefixos de rota do Office 365. A comunidade do BGP que inclui os prefixos de rota mostrados se alinha com a área do serviço listada. Quando o ER estiver marcado como **Não**, isso significa que o ExpressRoute não é suportado para esse conjunto de pontos de extremidade. No entanto, não devemos presumir que não existem rotas anunciadas para um conjunto de ponto de extremidade onde ER está marcado como **Não**.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.
 
- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

