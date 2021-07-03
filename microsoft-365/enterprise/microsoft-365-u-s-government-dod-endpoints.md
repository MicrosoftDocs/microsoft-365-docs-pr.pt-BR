---
title: Office 365 Pontos de extremidade do DOD do Governo dos EUA
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis para clientes que usam Office 365 apenas planos do DoD do Governo dos EUA.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 32a760843453a4d243ee65802325852323402140
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286424"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 Pontos de extremidade do DoD do governo dos EUA

*Aplica-se a: Office 365 Admin*

O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis para clientes que usam Office 365 apenas planos do DoD do Governo dos EUA.
  
Office 365 pontos de **extremidade:** em todo o mundo [(incluindo GCC)](urls-and-ip-address-ranges.md) Office 365 operado pela \| [21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Alemanha](microsoft-365-germany-endpoints.md) Office 365 \| *DoD* \| [](microsoft-365-u-s-government-gcc-high-endpoints.md) do Governo dos EUA Office 365 GCC Alta

<br>

****

|Observações|Baixar|
|---|---|
|**Última atualização:** 28/05/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Alterar assinatura do Log](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Baixar:** a lista completa no [formato JSON](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

Comece com [Gerenciando pontos de extremidade do Office 365 ](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando esses dados. Os dados dos terminais são atualizados conforme necessário no início de cada mês com novos endereços IP e URLs publicados 30 dias antes de serem ativados. Isso permite que os clientes que ainda não tenham atualizações automatizadas concluam seus processos antes que a nova conectividade seja necessária. Os endpoints também podem ser atualizados durante o mês, se necessário, para lidar com escalações de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Os dados mostrados nesta página a seguir são todos gerados a partir dos serviços da web baseados em REST. Se estiver usando um script ou um dispositivo de rede para acessar esses dados, você deve ir para o [serviço da Web ](microsoft-365-ip-web-service.md) diretamente.

Os dados do ponto de extremidade abaixo listam os requisitos de conectividade do computador de um usuário para Office 365. Ele não inclui conexões de rede da Microsoft em uma rede do cliente, às vezes chamadas de conexões de rede híbridas ou de entrada. Para obter mais informações, consulte [Pontos de extremidade adicionais não incluídos no serviço Web](additional-office365-ip-addresses-and-urls.md).

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: Mostra se o conjunto de terminais está classificado como "Otimizar", "Permitir" ou "Padrão". Você pode ler sobre essas categorias e orientações para o gerenciamento delas em [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Esta coluna também lista quais conjuntos de terminais são necessários para se ter conectividade de rede. Quanto aos conjuntos de terminais que não precisam ter conectividade de rede, fornecemos notas neste campo para indicar qual funcionalidade faltaria se o conjunto de terminais estivesse bloqueado. Se você excluir uma área de serviço inteira, os conjuntos de terminais listados conforme necessário não exigirão conectividade.

- **ER**: Isso é **Sim se** o conjunto de pontos de extremidade for suportado no Azure ExpressRoute com prefixos Office 365 de rota. A comunidade BGP que inclui os prefixos de rota mostrados se alinha à área de serviço listada. Quando ER é **Não**, isso significa que o ExpressRoute não tem suporte para esse conjunto de pontos de extremidade. No entanto, não deve ser presumido que nenhuma rota seja anunciada para um conjunto de pontos de extremidade onde ER é **Não**. Se você planeja usar o Azure AD [](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) Conexão, leia a seção considerações especiais para garantir que você tenha a configuração apropriada do Azure AD Conexão configuração.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.

- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Observações da tabela:

- O Centro de Conformidade e Segurança (SCC) fornece suporte para o Azure ExpressRoute para Office 365. O mesmo se aplica a muitos recursos expostos por meio do SCC, como Relatórios, Auditoria, Advanced eDiscovery, DLP Unificada e Governança de Dados. Dois recursos específicos, PST Import e eDiscovery Export, atualmente não suportam o Azure ExpressRoute com apenas filtros de rota Office 365 devido à sua dependência do Azure Blob Armazenamento. Para consumir esses recursos, você precisa de conectividade separada com o Azure Blob Armazenamento usando todas as opções de conectividade do Azure com suporte, que incluem conectividade com a Internet ou O Azure ExpressRoute com filtros de rota pública do Azure. Você precisa avaliar o estabelecimento dessa conectividade para ambos os recursos. A equipe Office 365 proteção de informações está ciente dessa limitação e está trabalhando ativamente para trazer suporte para o Azure ExpressRoute para Office 365 como limitado Office 365 filtros de rota para ambos os recursos.

- Há pontos de extremidade opcionais adicionais para Microsoft 365 Apps para Grandes Empresas que não estão listados e não são necessários para os usuários iniciarem Microsoft 365 Apps para Grandes Empresas aplicativos e editar documentos. Os pontos de extremidade opcionais são hospedados em datacenters da Microsoft e não processam, transmitem ou armazenam dados do cliente. Recomendamos que as conexões do usuário com esses pontos de extremidade sejam direcionadas ao perímetro padrão de saída da Internet.
