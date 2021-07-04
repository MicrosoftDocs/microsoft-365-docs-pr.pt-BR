---
title: Criar alerta a partir da API de evento
description: Saiba como usar a API Criar alerta para criar um novo Alerta em cima do Evento no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, alerta, informações, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7f8d3b10cee0b3c4a561dfd1f7567fa9818e7686
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289458"
---
# <a name="create-alert-api"></a>Criar API de alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API

Cria um [novo Alerta](alerts.md) em cima do **evento**.

- **O Evento Do Microsoft Defender para Ponto** de Extremidade é necessário para a criação do alerta.
- Você precisará fornecer 3 parâmetros do Evento na solicitação: Hora do Evento, **ID do** Computador e **ID do Relatório.** Veja o exemplo a seguir.
- Você pode usar um evento encontrado na API de Busca Avançada ou portal.
- Se houver um alerta aberto no mesmo Dispositivo com o mesmo Título, o novo alerta criado será mesclado com ele.
- Uma investigação automática é iniciada automaticamente em alertas criados por meio da API.

## <a name="limitations"></a>Limitações

1. Limitações de taxa para essa API são 15 chamadas por minuto.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
:---|:---|:---
Aplicativo | Alerts.ReadWrite.All | 'Ler e gravar todos os alertas'
Delegado (conta corporativa ou de estudante) | Alert.ReadWrite | 'Alertas de leitura e gravação'

> [!NOTE]
> Ao obter um token usando credenciais de usuário:
>
> - O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)
> - O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | String | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, fornece os seguintes valores (todos são necessários):

Propriedade | Tipo | Descrição
:---|:---|:---
eventTime | DateTime(UTC) | O tempo preciso do evento como cadeia de caracteres, conforme obtido da busca avançada. por exemplo, ```2018-08-03T16:45:21.7115183Z``` **obrigatório.**
reportId | String | O reportId do evento, conforme obtido da busca avançada. **Obrigatório**.
machineId | String | ID do dispositivo no qual o evento foi identificado. **Obrigatório**.
severity | String | Gravidade do alerta. Os valores da propriedade são: 'Low', 'Medium' e 'High'. **Obrigatório**.
title | String | Título do alerta. **Obrigatório**.
description | String | Descrição do alerta. **Obrigatório**.
recommendedAction| String | Ação recomendada pelo agente de segurança ao analisar o alerta. **Obrigatório**.
category| String | Categoria do alerta. Os valores da propriedade são: "Geral", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltração", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistência", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 OK e um novo objeto [de](alerts.md) alerta no corpo da resposta. Se o evento com as propriedades especificadas (_reportId,_ _eventTime_ e _machineId_) não for encontrado - 404 Não Encontrado.

## <a name="example"></a>Exemplo

### <a name="request"></a>Solicitação

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
