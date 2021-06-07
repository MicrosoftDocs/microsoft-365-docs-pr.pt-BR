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
ms.custom: api
ms.openlocfilehash: 03b19f3af3c140729db2b5d51bb7ae11d906497b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771640"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="83f2c-104">Configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para seus Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="83f2c-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83f2c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="83f2c-105">**Applies to:**</span></span>

- [<span data-ttu-id="83f2c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="83f2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="83f2c-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="83f2c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="83f2c-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="83f2c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="83f2c-109">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="83f2c-109">Before you begin</span></span>

1. <span data-ttu-id="83f2c-110">Crie um [hub de eventos](/azure/event-hubs/) em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="83f2c-110">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="83f2c-111">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse \*\*Assinaturas > Sua assinatura > Provedores de Recursos > Registrar em \*\*Microsoft.insights\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="83f2c-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to \*\*Subscriptions > Your subscription > Resource Providers > Register to \*\*Microsoft.insights\*\*\*\*.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="83f2c-112">Habilitar o streaming de dados brutos</span><span class="sxs-lookup"><span data-stu-id="83f2c-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="83f2c-113">Faça logon no [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com) como administrador **global** _ ou administrador de _segurança_ _\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="83f2c-113">Log in to the [Microsoft Defender Security Center](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="83f2c-114">Vá para a [página Configurações de exportação de dados](https://securitycenter.windows.com/interoperability/dataexport) Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="83f2c-114">Go to the [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="83f2c-115">Clique em **Adicionar configurações de exportação de dados.**</span><span class="sxs-lookup"><span data-stu-id="83f2c-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="83f2c-116">Escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="83f2c-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="83f2c-117">Escolha Encaminhar eventos para hubs de eventos **do Azure.**</span><span class="sxs-lookup"><span data-stu-id="83f2c-117">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="83f2c-118">Digite o **nome dos Hubs de Eventos e** a ID do recurso **hubs de eventos.**</span><span class="sxs-lookup"><span data-stu-id="83f2c-118">Type your **Event Hubs name** and your **Event Hubs resource ID**.</span></span>

   <span data-ttu-id="83f2c-119">Para obter a ID do recurso **Hubs** de Eventos, vá para sua página namespace hubs de eventos do Azure na guia propriedades do [Azure](https://ms.portal.azure.com/) > > copiar o texto em **ID** de Recurso :</span><span class="sxs-lookup"><span data-stu-id="83f2c-119">In order to get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > properties tab > copy the text under **Resource ID**:</span></span>

   ![Imagem da Id1 do recurso do hub de eventos](images/event-hub-resource-id.png)

7. <span data-ttu-id="83f2c-121">Escolha os eventos que deseja transmitir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="83f2c-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="83f2c-122">O esquema dos eventos nos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="83f2c-122">The schema of the events in Azure Event Hubs</span></span>

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

- <span data-ttu-id="83f2c-123">Cada mensagem do hub de eventos nos Hubs de Eventos do Azure contém uma lista de registros.</span><span class="sxs-lookup"><span data-stu-id="83f2c-123">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="83f2c-124">Cada registro contém o nome do evento, a hora em que o Microsoft Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos de seu locatário) e o evento no formato JSON em uma propriedade chamada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="83f2c-124">Each record contains the event name, the time Microsoft Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="83f2c-125">Para obter mais informações sobre o esquema do Microsoft Defender para eventos do Ponto de Extremidade, consulte [Visão geral de Busca Avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="83f2c-125">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="83f2c-126">Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83f2c-126">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="83f2c-127">Aqui todos os eventos também serão decorados com esta coluna.</span><span class="sxs-lookup"><span data-stu-id="83f2c-127">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="83f2c-128">Confira [Grupos de Dispositivos](machine-groups.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="83f2c-128">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="83f2c-129">Mapeamento de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="83f2c-129">Data types mapping</span></span>

<span data-ttu-id="83f2c-130">Para obter os tipos de dados para propriedades de evento, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83f2c-130">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="83f2c-131">Entre [no](https://securitycenter.windows.com) Central de Segurança do Microsoft Defender e vá para a página De Busca [Avançada.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="83f2c-131">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="83f2c-132">Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="83f2c-132">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="83f2c-133">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="83f2c-133">Here is an example for Device Info event:</span></span> 

  ![Imagem da Id2 do recurso do hub de eventos](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="83f2c-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="83f2c-135">Related topics</span></span>
- [<span data-ttu-id="83f2c-136">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="83f2c-136">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="83f2c-137">API de streaming do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="83f2c-137">Microsoft Defender for Endpoint streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="83f2c-138">Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="83f2c-138">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="83f2c-139">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="83f2c-139">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="83f2c-140">Solucionar problemas de conectividade - Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="83f2c-140">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)