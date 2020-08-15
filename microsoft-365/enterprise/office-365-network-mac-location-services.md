---
title: Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/31/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)
ms.openlocfilehash: e614e719069a74ea087b07ca624ae0450790c763
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687341"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)

O centro de administração do Microsoft 365 agora mostra as **recomendações de rede e o desempenho**, que são métricas de desempenho ao vivo coletadas do seu locatário do Microsoft 365 e disponíveis para visualização apenas por usuários administrativos em seu locatário. A conectividade de rede organizacional é projetada por local do escritório por meio de um local de egresso de rede para a Internet. A conectividade do cliente Microsoft 365 usa essa rota e, em seguida, através da Internet para os servidores de porta frontal do serviço Microsoft. Identificar os locais do Office é a chave para poder mostrar esses insights de rede.

## <a name="location-in-network-measurements"></a>Local em medições de rede

O administrador de uma organização pode aceitar o local a ser incluído nas medições de rede usadas por esse recurso. Isso permite a descoberta automática da cidade onde cada escritório está localizado. As informações de local não são precisas e são ofuscadas para 300m e categorizadas por cidade. No momento em que o local é capturado em um dispositivo do Windows, ele mostrará um ícone **de local em uso** na bandeja de ferramentas e os administradores podem querer notificar os usuários sobre isso. Com esse processamento, o local é tratado como o local da organização do escritório e não o local de uma pessoa ou de um dispositivo. Os insights de rede podem ser mostrados nessas cidades de localização descoberta do Office. Se for desejado mais precisão das recomendações, um administrador poderá inserir endereços específicos do local do escritório, e os insights da rede serão agregados a eles. Os locais do Office não podem ser agregados mais de 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Local no centro de administração do Microsoft 365

No centro de administração do Microsoft 365, os controles do Bing MAP são usados para mostrar onde as localizações de escritórios da organização são e para mostrar a topologia de perímetro de rede para um local do escritório selecionado. Quando um administrador adiciona detalhes de endereço específicos para locais do Office, o Bing Maps também é usado para sugerir endereços para facilitar a entrada de dados.

## <a name="terms-of-use"></a>Termos de Uso

Qualquer conteúdo fornecido por meio do Bing Maps, incluindo geocodes, só pode ser usado dentro do produto através do qual o conteúdo é fornecido. O uso do cliente do recurso de serviços de local do centro de administração do Microsoft 365, fornecido pelo Bing Maps, é regido pelos _termos de uso do Bing Maps End User_ disponível em <https://go.microsoft.com/?linkid=9710837> e pela _declaração de privacidade da Microsoft_ disponível em <https://go.microsoft.com/fwlink/?LinkID=248686.>

Esse recurso, fornecido por meio do Bing Maps, também é suportado por **estas tecnologias**. O modo como o Bing Maps aproveita os serviços de local fornecidos por estas tecnologias é regido pelos _termos de serviço de tecnologias aqui_ disponíveis em <https://legal.here.com/en-gb/terms> .
