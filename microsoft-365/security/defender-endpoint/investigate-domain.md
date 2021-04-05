---
title: Investigar o Microsoft Defender para domínios de ponto de extremidade
description: Use as opções de investigação para ver se dispositivos e servidores estão se comunicando com domínios mal-intencionados.
keywords: investigar domínio, domínio, domínio mal-intencionado, microsoft defender atp, alerta, URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 3d4520c805332bac41746a39bb8b668dbfb1a570
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587486"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Investigue um domínio para ver se dispositivos e servidores em sua rede corporativa estão se comunicando com um domínio mal-intencionado conhecido.

Você pode investigar um domínio usando o recurso de pesquisa ou clicando em um link de domínio da linha do tempo **do dispositivo.**

Você pode ver informações das seções a seguir no exibição url:

- Detalhes da URL, Contatos, Nameservers
- Alertas relacionados a essa URL 
- URL na organização
- Dispositivos observados mais recentes com URL

## <a name="url-worldwide"></a>URL em todo o mundo

A **seção URL Worldwide** lista a URL, um link para mais detalhes em Whois, o número de incidentes abertos relacionados e o número de alertas ativos.

## <a name="incident"></a>Incidente

O **cartão** Incident exibe um gráfico de barras de todos os alertas ativos em incidentes nos últimos 180 dias.

## <a name="prevalence"></a>Prevalência

O **Cartão de** Prevalência fornece detalhes sobre a prevalência da URL dentro da organização, por um período de tempo especificado.

Embora o período de tempo padrão seja os últimos 30 dias, você pode personalizar o intervalo selecionando a seta apontando para baixo no canto do cartão. O intervalo mais curto disponível é para prevalência no último dia, enquanto o intervalo mais longo é nos últimos 6 meses.

## <a name="alerts"></a>Alertas

A **guia Alertas** fornece uma lista de alertas associados à URL. A tabela mostrada aqui é uma versão filtrada dos alertas visíveis na tela de fila de alertas, mostrando apenas alertas associados ao domínio, sua gravidade, status, o incidente associado, classificação, estado de investigação e muito mais.

A guia Alertas pode ser ajustada para mostrar mais ou menos informações, selecionando **Personalizar colunas** no menu ação acima dos headers da coluna. O número de itens exibidos também pode ser ajustado selecionando **itens por página** no mesmo menu.

## <a name="observed-in-organization"></a>Observado na organização

A **guia Observado na organização** fornece uma exibição cronológica sobre os eventos e alertas associados que foram observados na URL. Essa guia inclui uma linha do tempo e um evento de listagem de tabela personalizável, como a hora, o dispositivo e uma breve descrição do que aconteceu. 

Você pode exibir eventos de diferentes períodos de tempo inserindo as datas nos campos de texto acima dos headers da tabela. Você também pode personalizar o intervalo de tempo selecionando diferentes áreas da linha do tempo.

**Investigar um domínio:**

1. Selecione **URL** no menu suspenso **barra de** pesquisa.
2. Insira a URL no **campo** Pesquisa.
3. Clique no ícone de pesquisa ou pressione **Enter**. Os detalhes sobre a URL são exibidos. Observação: os resultados da pesquisa só serão retornados para URLs observadas nas comunicações de dispositivos na organização.
4. Use os filtros de pesquisa para definir os critérios de pesquisa. Você também pode usar a caixa de pesquisa linha do tempo para filtrar os resultados exibidos de todos os dispositivos na organização observados se comunicando com a URL, o arquivo associado à comunicação e a última data observada.
5. Clicar em qualquer um dos nomes de dispositivo o levará ao ponto de vista desse dispositivo, onde você pode continuar a investigar alertas, comportamentos e eventos relatados.

## <a name="related-topics"></a>Tópicos relacionados
- [Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint](alerts-queue.md)
- [Gerenciar alertas do Microsoft Defender para Pontos de Extremidade](manage-alerts.md)
- [Investigar alertas do Microsoft Defender para Pontos de Extremidade](investigate-alerts.md)
- [Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices](investigate-machines.md)
- [Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-ip.md)
- [Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade](investigate-user.md)
