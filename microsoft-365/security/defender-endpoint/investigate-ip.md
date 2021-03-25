---
title: Investigar um endereço IP associado a um alerta
description: Use as opções de investigação para examinar a possível comunicação entre dispositivos e endereços IP externos.
keywords: investigar, investigação, endereço IP, alerta, microsoft defender atp, IP externo
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 003abd854e34bb5a9a05f675313ba6c4f6ce1d71
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186036"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Examine a possível comunicação entre seus dispositivos e endereços IP (protocolo IP) externos.

Identificar todos os dispositivos na organização que se comunicaram com um endereço IP suspeito ou conhecido mal-intencionado, como servidores de Comando e Controle (C2), ajuda a determinar o escopo potencial de violação, arquivos associados e dispositivos infectados.

Você pode encontrar informações das seguintes seções no exibição de endereço IP:

- IP em todo o mundo
- Nomes DNS reverso
- Alertas relacionados a esse IP
- IP na organização
- Prevalência

## <a name="ip-worldwide-and-reverse-dns-names"></a>Nomes DNS de IP em todo o mundo e dns reverso

A seção Detalhes do endereço IP mostra atributos do endereço IP, como seu ASN e seus nomes DNS reverso.

## <a name="alerts-related-to-this-ip"></a>Alertas relacionados a esse IP

A **seção Alertas relacionados** a esse IP fornece uma lista de alertas associados ao IP.

## <a name="ip-in-organization"></a>IP na organização

A **seção IP na organização** fornece detalhes sobre a prevalência do endereço IP na organização.

## <a name="prevalence"></a>Prevalência

A **seção Prevalência** exibe quantos dispositivos se conectaram a esse endereço IP e quando o IP foi visto pela primeira e última vez. Você pode filtrar os resultados desta seção por período de tempo; o período padrão é de 30 dias.

## <a name="most-recent-observed-devices-with-ip"></a>Dispositivos observados mais recentes com IP

A **seção Dispositivos observados mais** recentes com IP fornece uma exibição cronológica sobre os eventos e alertas associados que foram observados no endereço IP.

**Investigar um IP externo:**

1. Selecione **IP** no menu suspenso **da barra** de pesquisa.
2. Insira o endereço IP no **campo** Pesquisa.
3. Clique no ícone de pesquisa ou pressione **Enter**.

Detalhes sobre o endereço IP são exibidos, incluindo: detalhes do registro (se disponível), IPs reversos (por exemplo, domínios), prevalência de dispositivos na organização que se comunicaram com esse Endereço IP (durante o período selecionável) e os dispositivos na organização que foram observados se comunicando com esse endereço IP.

> [!NOTE]
> Os resultados da pesquisa só serão retornados para endereços IP observados na comunicação com dispositivos na organização.

Use os filtros de pesquisa para definir os critérios de pesquisa. Você também pode usar a caixa de pesquisa linha do tempo para filtrar os resultados exibidos de todos os dispositivos na organização observados se comunicando com o endereço IP, o arquivo associado à comunicação e a última data observada.

Clicar em qualquer um dos nomes de dispositivo o levará ao ponto de vista desse dispositivo, onde você pode continuar a investigar alertas, comportamentos e eventos relatados.

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint](alerts-queue.md)
- [Gerenciar alertas do Microsoft Defender para Pontos de Extremidade](manage-alerts.md)
- [Investigar alertas do Microsoft Defender para Pontos de Extremidade](investigate-alerts.md)
- [Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices](investigate-machines.md)
- [Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-domain.md)
- [Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade](investigate-user.md)
