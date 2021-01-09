---
title: Pontos de extremidade do Office 365 U.S. Government GCC High
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
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
description: Neste artigo, você encontrará pontos de extremidade acessíveis para clientes que usam planos Office 365 U.S. Government GCC High.
hideEdit: true
ms.openlocfilehash: 7a9cc33f93ac1a887ecce24689858b283f992cde
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787782"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Pontos de extremidade do Office 365 U.S. Government GCC High

 *Aplica-se a: Administrador do Office 365*

O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem estar acessíveis somente para clientes que usam planos Office 365 U.S. Government GCC High.
  
 **Pontos de extremidade do Office 365:** [global (incluindo GCC)](urls-and-ip-address-ranges.md) | [Office 365 operado pela 21 Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Alemanha](microsoft-365-germany-endpoints.md)   |  [Office 365 Governo dos E.U.A. Departamento de Defesa](microsoft-365-u-s-government-dod-endpoints.md) | *GCC High do Office 365 Governo dos E.U.A.* |
  
|||
|:-----|:-----|
|**Última atualização:** 04/01/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Alterar assinatura do Log](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** a lista completa no [formato JSON](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Comece [gerenciando pontos de extremidade do Office 365](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando esses dados. Os dados de pontos de extremidade são atualizados no início de cada mês com novos endereços IP e URLs publicados 30 dias antes de serem ativos. Isso permite que os clientes que ainda não tenham atualizações automatizadas concluam seus processos antes da nova conectividade ser necessária. Os pontos de extremidade também podem ser atualizados durante o mês, se necessário, para lidar com escalonamentos de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Os dados mostrados nesta página abaixo são todos gerados a partir dos serviços Web baseados em REST. Se você estiver usando um script ou um dispositivo de rede para acessar esses dados, acesse o [serviço Web](microsoft-365-ip-web-service.md) diretamente.

Os dados dos pontos de extremidade abaixo listam requisitos de conectividade do computador de um usuário para o Office 365. Eles não incluem conexões de rede da Microsoft com uma rede de clientes, que são algumas vezes chamadas conexões de rede híbridas ou de entrada.

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: mostra se o conjunto de pontos de extremidade é categorizado como "Otimizar", "Permitir" ou "Padrão". Leia sobre essas categorias e diretrizes para gerenciamento de todos eles em [ https://aka.ms/pnc](https://aka.ms/pnc). Esta coluna também lista quais conjuntos de ponto de extremidade são necessários para que haja conectividade de rede. Para conjuntos de ponto de extremidade que não são necessários para que haja conectividade de rede, fornecemos notas nesse campo para indicar qual funcionalidade estaria ausente se o conjunto de pontos de extremidade estiver bloqueado. Se você estiver excluindo uma área de serviço inteira, os conjuntos de pontos de extremidade listados como necessários não vão precisar de conectividade.

- **ER**: Isso é Sim **se o** conjunto de pontos de extremidade for suportado pelo Azure ExpressRoute com prefixos de rota do Office 365. A comunidade BGP que inclui os prefixos de rota mostrados se alinha com a área de serviço listada. Quando ER for **Não,** isso significa que o ExpressRoute não é suportado para este conjunto de pontos de extremidade. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**. Se você planeja usar o Azure [](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) AD Connect, leia a seção de considerações especiais para garantir que você tenha a configuração apropriada do Azure AD Connect.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.
 
- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Observações da tabela:

- O Centro de Conformidade e Segurança (SCC) fornece suporte para o Azure ExpressRoute para Office 365. O mesmo se aplica a muitos recursos expostos por meio do SCC, como Relatórios, Auditoria, DescobertaSCoberta Avançada, DLP Unificada e Governança de Dados. Dois recursos específicos, Importação de PST e Exportação de Descobertas EDiscovery, atualmente não são suportados pelo Azure ExpressRoute com apenas filtros de rota do Office 365 devido à dependência do Armazenamento de Blob do Azure. Para consumir esses recursos, você precisa de conectividade separada ao Armazenamento de Blob do Azure usando qualquer opção de conectividade do Azure com suporte, que incluem conectividade com a Internet ou Rota Expressa do Azure com filtros de rota pública do Azure. Você precisa avaliar o estabelecimento dessa conectividade para ambos os recursos. A equipe de Proteção de Informações do Office 365 está ciente dessa limitação e está trabalhando ativamente para trazer suporte para o Azure ExpressRoute para Office 365, conforme limitado aos filtros de rota do Office 365 para ambos os recursos.

- Há pontos de extremidade opcionais adicionais para o Microsoft 365 Apps para empresas que não estão listados e não são necessários para os usuários iniciarem os Aplicativos do Microsoft 365 para empresas e editarem documentos. Os pontos de extremidade opcionais são hospedados em datacenters da Microsoft e não processam, transmitem ou armazenam dados de clientes. Recomendamos que as conexões do usuário com esses pontos de extremidade sejam direcionadas para o perímetro de saída da Internet padrão.

