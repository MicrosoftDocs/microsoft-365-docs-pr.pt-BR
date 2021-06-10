---
title: Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure
description: Saiba como configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para o Hub de Eventos.
keywords: exportação de dados brutos, API de streaming, API, Hubs de Eventos do Azure, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
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
ms.openlocfilehash: 8985a40c99ad4db9710dfbf9805d537a921f6c96
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780160"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a>Configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para seus Hubs de Eventos do Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Antes de começar

1. Crie um [hub de eventos](/azure/event-hubs/) em seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse **Assinaturas > Sua assinatura > Provedores de Recursos > Registrar em **Microsoft.insights****.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos

1. Faça logon no [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com) como administrador **global** _ ou administrador de _segurança_ _* **.

2. Vá para a [página Configurações de exportação de dados](https://securitycenter.windows.com/interoperability/dataexport) Central de Segurança do Microsoft Defender.

3. Clique em **Adicionar configurações de exportação de dados.**

4. Escolha um nome para suas novas configurações.

5. Escolha Encaminhar eventos para hubs de eventos **do Azure.**

6. Digite o **nome dos Hubs de Eventos e** a ID do recurso **hubs de eventos.**

   Para obter a ID do recurso **Hubs** de Eventos, vá para sua página namespace hubs de eventos do Azure na guia propriedades do [Azure](https://ms.portal.azure.com/) > > copiar o texto em **ID** de Recurso :

   ![Imagem da Id1 do recurso do hub de eventos](images/event-hub-resource-id.png)

7. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a>O esquema dos eventos nos Hubs de Eventos do Azure

```
{
    "records": [
                    {
                        "time": "<The time WDATP received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <WDATP Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- Cada mensagem do hub de eventos nos Hubs de Eventos do Azure contém uma lista de registros.

- Cada registro contém o nome do evento, a hora em que o Microsoft Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos de seu locatário) e o evento no formato JSON em uma propriedade chamada "**properties**".

- Para obter mais informações sobre o esquema do Microsoft Defender para eventos do Ponto de Extremidade, consulte [Visão geral de Busca Avançada](advanced-hunting-overview.md).

- Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo. Aqui todos os eventos também serão decorados com esta coluna. Confira [Grupos de Dispositivos](machine-groups.md) para obter mais informações.

## <a name="data-types-mapping"></a>Mapeamento de tipos de dados

Para obter os tipos de dados para propriedades de evento, faça o seguinte:

1. Entre [no](https://securitycenter.windows.com) Central de Segurança do Microsoft Defender e vá para a página De Busca [Avançada.](https://securitycenter.windows.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da Id2 do recurso do hub de eventos](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [API de streaming do Microsoft Defender para Ponto de Extremidade](raw-data-export.md)
- [Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de armazenamento do Azure](raw-data-export-storage.md)
- [Documentação dos Hubs de Eventos do Azure](/azure/event-hubs/)
- [Solucionar problemas de conectividade - Hubs de Eventos do Azure](/azure/event-hubs/troubleshooting-guide)