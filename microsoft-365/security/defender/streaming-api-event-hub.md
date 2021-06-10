---
title: Transmitir Microsoft 365 eventos do Defender para o Hub de Eventos do Azure
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para o Hub de Eventos.
keywords: exportação de dados brutos, API de streaming, API, Hub de Eventos do Azure, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
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
ms.openlocfilehash: c62f175fc8227f64b9f18de78a2a793b2201691c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782364"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hub"></a><span data-ttu-id="aaf06-104">Configurar Microsoft 365 Defender para transmitir eventos de Busca Avançada para o Hub de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="aaf06-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aaf06-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="aaf06-105">**Applies to:**</span></span>
- [<span data-ttu-id="aaf06-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aaf06-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="aaf06-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="aaf06-107">Before you begin</span></span>

1. <span data-ttu-id="aaf06-108">Crie um [hub de eventos](/azure/event-hubs/) em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="aaf06-108">Create an [Event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="aaf06-109">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="aaf06-110">Crie um Namespace do Hub de Eventos, vá até **Event Hub > Adicionar** e selecione a camada de preços, as unidades de transferência e a Inflação Automática apropriada para a carga esperada.</span><span class="sxs-lookup"><span data-stu-id="aaf06-110">Create an Event Hub Namespace, go to **Event Hub > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="aaf06-111">Para obter mais informações, consulte [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="aaf06-111">For more information, see [Pricing - Event Hub | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

### <a name="add-contributor-permissions"></a><span data-ttu-id="aaf06-112">Adicionar permissões de colaborador</span><span class="sxs-lookup"><span data-stu-id="aaf06-112">Add contributor permissions</span></span> 
<span data-ttu-id="aaf06-113">Depois que o namespace do Hub de Eventos for criado, você precisará adicionar a Entidade de Serviço de Registro de Aplicativo como Leitor, Receptor de Dados do Hub de Eventos do Azure e o usuário que fará logon no Microsoft 365 Defender como Colaborador (isso também pode ser feito no nível de Grupo de Recursos ou Assinatura).</span><span class="sxs-lookup"><span data-stu-id="aaf06-113">Once the Event Hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hub Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> 

<span data-ttu-id="aaf06-114">Vá para Namespace de hubs de eventos > Controle de acesso **(IAM)** > Adicionar e verificar em **Atribuições de função**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-114">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignments**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="aaf06-115">Habilitar o streaming de dados brutos</span><span class="sxs-lookup"><span data-stu-id="aaf06-115">Enable raw data streaming</span></span>

1. <span data-ttu-id="aaf06-116">Faça logon no [Microsoft 365 de](https://security.microsoft.com) segurança do Defender como um ***Administrador Global** _ ou _* Administrador _de Segurança_\*\*.</span><span class="sxs-lookup"><span data-stu-id="aaf06-116">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="aaf06-117">Vá para a [página Configurações da API de Streaming.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="aaf06-117">Go to the [Streaming API settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="aaf06-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-118">Click on **Add**.</span></span>

4. <span data-ttu-id="aaf06-119">Escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="aaf06-119">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="aaf06-120">Escolha **Encaminhar eventos para o Hub de Eventos do Azure.**</span><span class="sxs-lookup"><span data-stu-id="aaf06-120">Choose **Forward events to Azure Event Hub**.</span></span>

6. <span data-ttu-id="aaf06-121">Você pode selecionar se deseja exportar os dados do evento para um único Hub de Eventos ou exportar cada tabela de eventos para um hub de eventos diferente no namespace do Hub de Eventos.</span><span class="sxs-lookup"><span data-stu-id="aaf06-121">You can select if you want to export the event data to a single Event Hub, or to export each event table to a different event hub in your Event Hub namespace.</span></span> 

7. <span data-ttu-id="aaf06-122">Para exportar os dados de evento para um único Hub de Eventos, insira o nome do **Hub** de Eventos e sua ID de recurso **do Hub de Eventos.**</span><span class="sxs-lookup"><span data-stu-id="aaf06-122">To export the event data to a single Event Hub, enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="aaf06-123">Para obter sua **ID** de recurso do Hub de Eventos, vá para sua página de namespace do Hub de Eventos do Azure na guia Propriedades do [Azure](https://ms.portal.azure.com/)> copiar o texto em  >   **ID** de Recurso :</span><span class="sxs-lookup"><span data-stu-id="aaf06-123">To get your **Event Hub resource ID**, go to your Azure Event Hub namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Imagem da Id1 do recurso hub de eventos](../defender-endpoint/images/event-hub-resource-id.png)

8. <span data-ttu-id="aaf06-125">Escolha os eventos que deseja transmitir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aaf06-125">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hub"></a><span data-ttu-id="aaf06-126">O esquema dos eventos no Hub de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="aaf06-126">The schema of the events in Azure Event Hub</span></span>

```
{
    "records": [
                    {
                        "time": "<The time Microsoft 365 Defender received the event>"
                        "tenantId": "<The Id of the tenant that the event belongs to>"
                        "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
                        "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
                    }
                    ...
                ]
}
```

- <span data-ttu-id="aaf06-127">Cada mensagem do Hub de Eventos no Hub de Eventos do Azure contém uma lista de registros.</span><span class="sxs-lookup"><span data-stu-id="aaf06-127">Each Event Hub message in Azure Event Hub contains list of records.</span></span>

- <span data-ttu-id="aaf06-128">Cada registro contém o nome do evento Microsoft 365, a hora em que o Defender recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="aaf06-128">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="aaf06-129">Para obter mais informações sobre o esquema de eventos Microsoft 365 Defender, consulte [Advanced Hunting overview](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aaf06-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="aaf06-130">Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aaf06-130">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="aaf06-131">Aqui todos os eventos também serão decorados com esta coluna.</span><span class="sxs-lookup"><span data-stu-id="aaf06-131">Here every event will be decorated with this column as well.</span></span> 




## <a name="data-types-mapping"></a><span data-ttu-id="aaf06-132">Mapeamento de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="aaf06-132">Data types mapping</span></span>

<span data-ttu-id="aaf06-133">Para obter os tipos de dados para propriedades de evento, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aaf06-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="aaf06-134">Entre no centro [Microsoft 365 segurança e](https://security.microsoft.com) vá para a página De Busca [Avançada.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="aaf06-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="aaf06-135">Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="aaf06-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="aaf06-136">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="aaf06-136">Here is an example for Device Info event:</span></span> 

  ![Imagem da Id do recurso hub de eventos2](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="aaf06-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aaf06-138">Related topics</span></span>
- [<span data-ttu-id="aaf06-139">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="aaf06-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aaf06-140">Microsoft 365 Defender streaming API</span><span class="sxs-lookup"><span data-stu-id="aaf06-140">Microsoft 365 Defender streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="aaf06-141">Transmitir Microsoft 365 eventos do Defender para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="aaf06-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="aaf06-142">Documentação do Hub de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="aaf06-142">Azure Event Hub documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="aaf06-143">Solucionar problemas de conectividade - Hub de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="aaf06-143">Troubleshoot connectivity issues - Azure Event Hub</span></span>](/azure/event-hubs/troubleshooting-guide)
