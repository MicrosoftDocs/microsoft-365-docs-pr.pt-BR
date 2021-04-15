---
title: Saiba mais sobre o painel alertas de prevenção contra perda de dados
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre alertas de prevenção contra perda de dados e o painel de alertas.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760688"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Saiba mais sobre o painel alertas de prevenção contra perda de dados

Quando os critérios em uma política de prevenção contra perda de dados (DLP) são corresponderem às ações que um usuário está fazendo em um item sensível, a política pode gerar um alerta. Isso pode resultar em um alto volume de alertas. Os alertas DLP são coletados no painel de alertas. O painel de alertas oferece um único local para você ir para executar uma investigação profunda de todos os detalhes sobre a combinação de política.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Cargas de trabalho

O painel de gerenciamento de alertas DLP , no centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com/)mostra alertas para políticas de [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)nessas cargas de trabalho:

- Exchange
- SharePoint
- OneDrive
- Teams
- Dispositivos Windows 10 

> [!TIP]
> Os clientes que usam [a DLP](endpoint-dlp-learn-about.md) do Ponto de Extremidade que estão qualificados para a DLP do Teams verão seus alertas de política de [DLP](dlp-microsoft-teams.md) de ponto de extremidade e alertas de política de DLP do Teams no painel de gerenciamento de alertas DLP.

## <a name="single-alert-and-aggregate-alert"></a>Alerta único e alerta agregado

Há dois tipos de alertas que podem ser configurados em políticas de DLP.

**Alertas de** evento único geralmente são usados em políticas que monitoram eventos altamente confidenciais que ocorrem em um volume baixo, como um único email com 10 ou mais números de cartão de crédito do cliente sendo enviados para fora da sua organização.

**Alertas de eventos agregados** são geralmente usados em políticas que monitoram eventos que ocorrem em um volume maior em um período de tempo. Por exemplo, um alerta agregado pode ser disparado quando 10 emails individuais cada um com um número de cartão de crédito do cliente é enviado para fora da sua organização por mais de 48 horas.

## <a name="types-of-events"></a>Tipos de eventos

Aqui estão alguns dos eventos associados a um alerta. Na interface do usuário, você pode escolher um evento específico para exibir seus detalhes. 

### <a name="event-details"></a>Detalhes do evento

|Nome da propriedade  |Descrição  |Tipos de eventos  |
|---------|---------|---------|
|ID |ID exclusiva associada ao evento |todos os eventos |
|Local |de carga de trabalho em que o evento foi detectado|todos os eventos |
|tempo de atividade     |tempo da atividade do usuário que corresponderam aos critérios da política DLP |

### <a name="impacted-entities"></a>Entidades impactadas

|Nome da propriedade |Descrição| Tipos de eventos|
|---------|---------|---------|
|usuário | usuário que tomou a ação que causou a combinação de política | todos os eventos|
|hostname | nome do host do computador em que ocorreu a match de política de DLP | eventos de dispositivo|
|Endereço IP | Endereço IP do computador em que ocorreu a corresponder à política de DLP | eventos de dispositivo|
|sha1 |Hash SHA-1 do arquivo | eventos de dispositivo|
|sha256 | Hash sha-256 do arquivo | eventos de dispositivo|
|ID do dispositivo MDATP | ID MDATP do dispositivo de ponto de extremidade|
|tamanho do arquivo | tamanho do arquivo| Eventos do SharePoint, do OneDrive e do dispositivo|
|caminho do arquivo | o caminho absoluto do item envolvido com a combinação de política de DLP | Eventos do SharePoint, OneDrive e dispositivos|
|destinatários de email |se um email fosse o item sensível que corresponderia à política DLP, esse campo incluiria os destinatários desse email| Eventos do Exchange|
|assunto de email |assunto do email que corresponderam à política DLP |Eventos do Exchange|
|anexos de email | nomes dos anexos no email que corresponderam à política DLP| Eventos do Exchange|
|proprietário do site |nome do proprietário do site| Eventos do SharePoint e do OneDrive|
|URL do site |cheia da URL do site do SharePoint ou do OneDrive em que ocorreu a match de política de DLP |Eventos do SharePoint e do OneDrive|
|arquivo criado |tempo de criação do arquivo que corresponderam à política DLP |Eventos do SharePoint e do OneDrive|
|arquivo modificado pela última vez | a última vez que o arquivo que correspondera à política DLP foi alterado | Eventos do SharePoint e do OneDrive|
|tamanho do arquivo | tamanho do arquivo que corresponderam à política DLP |Eventos do SharePoint e do OneDrive|
|proprietário do arquivo |proprietário do arquivo que corresponderam à política DLP |Eventos do SharePoint e do OneDrive|  

### <a name="policy-details"></a>Detalhes da política

|Nome da propriedade |Descrição |Tipos de eventos |
|---------|---------|---------|
|Política de DLP corresponder |nome da política de DLP corresponder |todos os eventos|
|rule matched |nome da regra de política de DLP corresponder |todos os eventos|
|tipos de informações confidenciais (SIT) detectados|SITs detectados como parte da combinação de política DLP |todos os eventos|
|ações tomadas |ações que foram tomadas que causaram a match de política de DLP| todos os eventos|
|violando ação | ação no dispositivo de ponto de extremidade que gerou o alerta DLP| eventos de dispositivo | 
|política de overrode do usuário |o usuário substituiu a política por meio de uma dica de política | todos os eventos|
|usar a justificativa de substituição |o texto do motivo fornecido pelo usuário para a substituição | todos os eventos|   

## <a name="see-also"></a>Confira também

- [Começar com o painel de alertas de prevenção contra perda de dados](dlp-alerts-dashboard-get-started.md)
- [Onde começar com a prevenção contra perda de dados](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)