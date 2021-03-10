---
title: Pontos de extremidade high GCC do Office 365 Government GCC
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/28/2021
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
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: Neste artigo, você encontrará pontos de extremidade acessíveis para clientes que usam planos do Office 365 GCC High do Governo dos EUA.
hideEdit: true
ms.openlocfilehash: 4f7e1f8e6a0cc631e5df8302694ed96663a20c53
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596927"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Pontos de extremidade high GCC do Office 365 Government GCC

 *Aplica-se a: Administrador do Office 365*

O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis apenas para clientes que usam planos do Office 365 GCC High do Governo dos EUA.
  
 **Pontos de extremidade do Office 365:** [global (incluindo GCC)](urls-and-ip-address-ranges.md) | [Office 365 operado pela 21 Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Alemanha](microsoft-365-germany-endpoints.md)   |  [Office 365 Governo dos E.U.A. Departamento de Defesa](microsoft-365-u-s-government-dod-endpoints.md) | *GCC High do Office 365 Governo dos E.U.A.* |
  
|||
|:-----|:-----|
|**Última atualização:** 28/01/2021 - Assinatura do Log de Alterações ![ ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [do](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) RSS <br/> |**Baixar:** a lista completa no [formato JSON](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Comece com o Gerenciamento de pontos de extremidade do [Office 365](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando esses dados. Os dados de pontos de extremidade são atualizados conforme necessário no início de cada mês com novos Endereços IP e URLs publicadas 30 dias antes de estarem ativos. Isso permite que os clientes que ainda não tenham atualizações automatizadas concluam seus processos antes que a nova conectividade seja necessária. Os pontos de extremidade também podem ser atualizados durante o mês, se necessário para lidar com escalonamentos de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Os dados mostrados nesta página abaixo são todos gerados a partir dos serviços Web baseados em REST. Se você estiver usando um script ou um dispositivo de rede para acessar esses dados, acesse o [serviço Web diretamente.](microsoft-365-ip-web-service.md)

Os dados dos pontos de extremidade abaixo listam requisitos de conectividade do computador de um usuário para o Office 365. Eles não incluem conexões de rede da Microsoft com uma rede de clientes, que são algumas vezes chamadas conexões de rede híbridas ou de entrada.

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: mostra se o conjunto de pontos de extremidade é categorizado como "Otimizar", "Permitir" ou "Padrão". Leia sobre essas categorias e diretrizes para gerenciamento de todos eles em [ https://aka.ms/pnc](https://aka.ms/pnc). Esta coluna também lista quais conjuntos de ponto de extremidade são necessários para que haja conectividade de rede. Para conjuntos de ponto de extremidade que não são necessários para que haja conectividade de rede, fornecemos notas nesse campo para indicar qual funcionalidade estaria ausente se o conjunto de pontos de extremidade estiver bloqueado. Se você estiver excluindo uma área de serviço inteira, os conjuntos de pontos de extremidade listados como necessários não vão precisar de conectividade.

- **ER**: Isso é **Sim se** o conjunto de pontos de extremidade for suportado sobre o Azure ExpressRoute com prefixos de rota do Office 365. A comunidade BGP que inclui os prefixos de rota mostrados se alinha à área de serviço listada. Quando ER é **Não**, isso significa que o ExpressRoute não tem suporte para esse conjunto de pontos de extremidade. No entanto, não deve ser presumido que nenhuma rota seja anunciada para um conjunto de pontos de extremidade onde ER é **Não**. Se você planeja usar o Azure AD Connect, leia a seção considerações [especiais](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) para garantir que você tenha a configuração apropriada do Azure AD Connect.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.
 
- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Observações da tabela:

- O Centro de Segurança e Conformidade (SCC) fornece suporte para o Azure ExpressRoute para o Office 365. O mesmo se aplica a muitos recursos expostos por meio do SCC, como Relatórios, Auditoria, Descoberta Externa Avançada, DLP Unificada e Governança de Dados. Dois recursos específicos, PST Import e eDiscovery Export, atualmente não suportam o Azure ExpressRoute com apenas filtros de rota do Office 365 devido à dependência do Armazenamento de Blob do Azure. Para consumir esses recursos, você precisa de conectividade separada com o Armazenamento de Blob do Azure usando todas as opções de conectividade do Azure com suporte, que incluem conectividade com a Internet ou Azure ExpressRoute com filtros de rota pública do Azure. Você precisa avaliar o estabelecimento dessa conectividade para ambos os recursos. A equipe de Proteção de Informações do Office 365 está ciente dessa limitação e está trabalhando ativamente para trazer suporte para o Azure ExpressRoute para Office 365 como limitado aos filtros de rota do Office 365 para ambos os recursos.

- Há pontos de extremidade opcionais adicionais para Aplicativos do Microsoft 365 para empresas que não estão listados e não são necessários para os usuários iniciarem o Microsoft 365 Apps para aplicativos corporativos e editar documentos. Os pontos de extremidade opcionais são hospedados em datacenters da Microsoft e não processam, transmitem ou armazenam dados do cliente. Recomendamos que as conexões do usuário com esses pontos de extremidade sejam direcionadas ao perímetro padrão de saída da Internet.

