---
title: Criar uma regra de notificação de remoção ou de integração
description: Receba uma notificação quando um script de integração ou de offboard local é usado.
keywords: integração, offboarding, local, script, notificação, regra
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187030"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Criar uma regra de notificação quando um script local de integração ou de offboard é usado

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Crie uma regra de notificação para que, quando um script local de integração ou de offboard for usado, você será notificado. 

## <a name="before-you-begin"></a>Antes de começar
Você precisará ter acesso a:
 - Microsoft Flow (Flow Plano 1 no mínimo). Para obter mais informações, [consulte Flow página de preços](https://flow.microsoft.com/pricing/).
 - Tabela do Azure ou SharePoint ou Biblioteca/SQL DB

## <a name="create-the-notification-flow"></a>Criar o fluxo de notificação

1. Em [flow.microsoft.com](https://flow.microsoft.com/).

2. Navegue **até Meus fluxos > Novo > Agendado - em branco**. 

    ![Imagem de fluxo](images/new-flow.png)


3. Crie um fluxo agendado.
   1. Insira um nome de fluxo.
   2. Especifique o início e a hora.
   3. Especifique a frequência. Por exemplo, a cada 5 minutos.

    ![Imagem do fluxo de notificação](images/build-flow.png)

4. Selecione o botão + para adicionar uma nova ação. A nova ação será uma solicitação HTTP para a API do Defender for Endpoint security center device(s). Você também pode substituí-lo pelo "Conector WDATP&quot; (ação: &quot;Máquinas - Obter lista de máquinas"). 

    ![Imagem de recorrência e adicionar ação](images/recurrence-add.png)


5. Insira os seguintes campos HTTP:

   - Método: "GET" como um valor para obter a lista de dispositivos.
   - URI: Insira `https://api.securitycenter.microsoft.com/api/machines` .
   - Autenticação: selecione "Active Directory OAuth".
   - Locatário: entre e navegue até https://portal.azure.com Azure Active Directory > Registros de **Aplicativos** e obter o valor da ID do Locatário.
   - Público-alvo: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - ID do cliente: entre e navegue até Azure Active Directory > https://portal.azure.com **Aplicativos** e obter o valor da ID do Cliente.
   - Tipo de credencial: selecione "Segredo".
   - Segredo: entre e navegue até https://portal.azure.com Azure Active Directory > **registros de aplicativos** e obter o valor da ID do locatário.

    ![Imagem das condições HTTP](images/http-conditions.png)


6. Adicione uma nova etapa selecionando Adicionar  **nova ação** e, em seguida, pesquise Operações de Dados e selecione **Analisar JSON**.

    ![Imagem das operações de dados](images/data-operations.png)

7. Adicionar Corpo no **campo** Conteúdo.

    ![Imagem do JSON analisado](images/parse-json.png)

8. Selecione o **link Usar carga de exemplo para gerar esquema.**

    ![Imagem do json de análise com carga](images/parse-json-schema.png)

9. Copie e colar o seguinte trecho JSON:

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  Extraia os valores da chamada JSON e verifique se os dispositivos(s) conectados (s) já estão registrados na lista de SharePoint como exemplo:
- Se sim, nenhuma notificação será disparada
- Se não, registrará os novos dispositivos SharePoint na lista de SharePoint e uma notificação será enviada ao administrador do Defender for Endpoint

    ![Imagem de aplicar a cada](images/flow-apply.png)

    ![Imagem de aplicar a cada um com obter itens](images/apply-to-each.png)

11. Em **Condição**, adicione a seguinte expressão: "length(body('Get_items')?[' value'])" e de definir a condição como igual a 0.

    ![Imagem de aplicar a cada condição](images/apply-to-each-value.png)  
    ![Imagem da condição1 ](images/conditions-2.png) 
     ![ Imagem da condição2](images/condition3.png)  
    ![Imagem do email de envio](images/send-email.png)

## <a name="alert-notification"></a>Notificação de alerta
A imagem a seguir é um exemplo de uma notificação de email.

![Imagem da notificação de email](images/alert-notification.png)


## <a name="tips"></a>Dicas 

- Você pode filtrar aqui usando somente lastSeen:
    - A cada 60 minutos:
      - Pegue todos os dispositivos vistos pela última vez nos últimos 7 dias. 

- Para cada dispositivo: 
    - Se a propriedade visto pela última vez estiver no intervalo de uma hora de [-7 dias, -7days + 60 minutos ] -> Alerta para possibilidade de offboard.
    - Se visto pela primeira vez está na última hora -> Alerta para integração.

Nesta solução, você não terá alertas duplicados: há locatários com vários dispositivos. Obter todos esses dispositivos pode ser muito caro e pode exigir paging.

Você pode dividi-lo em duas consultas: 
1.  Para o offboard, use apenas esse intervalo usando o $filter OData e notifique somente se as condições são atendidas.
2.  Pegue todos os dispositivos vistos pela última vez na última hora e verifique a propriedade vista pela primeira vez para eles (se a primeira propriedade vista está na última hora, a última vista deve estar lá também). 

