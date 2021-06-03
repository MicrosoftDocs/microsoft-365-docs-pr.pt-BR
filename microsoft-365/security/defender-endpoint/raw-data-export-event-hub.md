---
title: Transmitir Microsoft 365 eventos do Defender para hubs de eventos do Azure
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para o Hub de Eventos.
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
ms.openlocfilehash: e2ede14d6b93a61bc232d42b5926c6adb7c9585f
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736319"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-azure-event-hubs"></a><span data-ttu-id="b0b97-104">Configurar Microsoft 365 Defender para transmitir eventos de Busca Avançada para seus Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="b0b97-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Azure Event Hubs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b0b97-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b0b97-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0b97-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0b97-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="b0b97-107">Antes de começar:</span><span class="sxs-lookup"><span data-stu-id="b0b97-107">Before you begin:</span></span>

1. <span data-ttu-id="b0b97-108">Crie um [hub de eventos](/azure/event-hubs/) em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b0b97-108">Create an [event hub](/azure/event-hubs/) in your tenant.</span></span>

2. <span data-ttu-id="b0b97-109">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="b0b97-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

3. <span data-ttu-id="b0b97-110">Crie um Namespace do Hub de Eventos, vá para **Hubs** de Eventos > Adicionar e selecione a camada de preços, as unidades de transferência e a Inflação Automática apropriada para a carga esperada.</span><span class="sxs-lookup"><span data-stu-id="b0b97-110">Create an Event Hub Namespace, go to **Event Hubs > Add** and select the pricing tier, throughput units and Auto-Inflate appropriate for expected load.</span></span> <span data-ttu-id="b0b97-111">Para obter mais informações, consulte [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span><span class="sxs-lookup"><span data-stu-id="b0b97-111">For more information, see [Pricing - Event Hubs | Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/).</span></span>  

4. <span data-ttu-id="b0b97-112">Depois que o namespace do hub de eventos for criado, você precisará adicionar a Entidade de Serviço de Registro de Aplicativo como Leitor, Receptor de Dados de Hubs de Eventos do Azure e o usuário que fará logon no Microsoft 365 Defender como Colaborador (isso também pode ser feito no nível de Grupo de Recursos ou Assinatura).</span><span class="sxs-lookup"><span data-stu-id="b0b97-112">Once the event hub namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span> <span data-ttu-id="b0b97-113">Vá para Namespace de hubs de eventos > Controle de acesso **(IAM)** > Adicionar e verificar em **Atribuir funções**.</span><span class="sxs-lookup"><span data-stu-id="b0b97-113">Go to **Event hubs namespace > Access control (IAM) > Add** and verify under **Role assignements**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="b0b97-114">Habilitar o streaming de dados brutos:</span><span class="sxs-lookup"><span data-stu-id="b0b97-114">Enable raw data streaming:</span></span>

1. <span data-ttu-id="b0b97-115">Faça logon no [Microsoft 365 de](https://security.microsoft.com) segurança do Defender como um ***Administrador Global** _ ou _* Administrador _de Segurança_\*\*.</span><span class="sxs-lookup"><span data-stu-id="b0b97-115">Log in to the [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="b0b97-116">Vá para a página [Configurações de exportação de dados.](https://security.microsoft.com/settings/mtp_settings/raw_data_export)</span><span class="sxs-lookup"><span data-stu-id="b0b97-116">Go to the [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export).</span></span>

3. <span data-ttu-id="b0b97-117">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b0b97-117">Click on **Add**.</span></span>

4. <span data-ttu-id="b0b97-118">Escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="b0b97-118">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="b0b97-119">Escolha Encaminhar eventos para hubs de eventos **do Azure.**</span><span class="sxs-lookup"><span data-stu-id="b0b97-119">Choose **Forward events to Azure Event Hubs**.</span></span>

6. <span data-ttu-id="b0b97-120">Você pode selecionar se deseja exportar os dados do evento para um único hub de eventos ou exportar cada tabela de eventos para um hub diferente no namespace do hub de eventos.</span><span class="sxs-lookup"><span data-stu-id="b0b97-120">You can select if you want to export the event data to a single event hub, or to export each event table to a different even hub in your event hub namespace.</span></span> 

7. <span data-ttu-id="b0b97-121">Para exportar os dados de evento para um único hub de eventos, insira o nome do Hub de **Eventos** e sua ID de recurso **do Hub de Eventos.**</span><span class="sxs-lookup"><span data-stu-id="b0b97-121">To export the event data to a single event hub, Enter your **Event Hub name** and your **Event Hub resource ID**.</span></span>

   <span data-ttu-id="b0b97-122">Para obter sua ID de recurso de **Hubs** de Eventos, vá para sua página namespace hubs de eventos do Azure na guia Propriedades do [Azure](https://ms.portal.azure.com/)> copiar o texto em  >   **ID** de Recurso :</span><span class="sxs-lookup"><span data-stu-id="b0b97-122">To get your **Event Hubs resource ID**, go to your Azure Event Hubs namespace page on [Azure](https://ms.portal.azure.com/) > **Properties** tab > copy the text under **Resource ID**:</span></span>

   ![Imagem da Id1 do recurso do hub de eventos](images/event-hub-resource-id.png)

8. <span data-ttu-id="b0b97-124">Escolha os eventos que deseja transmitir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b0b97-124">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-azure-event-hubs"></a><span data-ttu-id="b0b97-125">O esquema dos eventos nos Hubs de Eventos do Azure:</span><span class="sxs-lookup"><span data-stu-id="b0b97-125">The schema of the events in Azure Event Hubs:</span></span>

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

- <span data-ttu-id="b0b97-126">Cada mensagem do hub de eventos nos Hubs de Eventos do Azure contém uma lista de registros.</span><span class="sxs-lookup"><span data-stu-id="b0b97-126">Each event hub message in Azure Event Hubs contains list of records.</span></span>

- <span data-ttu-id="b0b97-127">Cada registro contém o nome do evento Microsoft 365, a hora em que o Defender recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "**properties**".</span><span class="sxs-lookup"><span data-stu-id="b0b97-127">Each record contains the event name, the time Microsoft 365 Defender received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "**properties**".</span></span>

- <span data-ttu-id="b0b97-128">Para obter mais informações sobre o esquema de eventos Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b0b97-128">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="b0b97-129">Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0b97-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="b0b97-130">Aqui todos os eventos também serão decorados com esta coluna.</span><span class="sxs-lookup"><span data-stu-id="b0b97-130">Here every event will be decorated with this column as well.</span></span> 

9. <span data-ttu-id="b0b97-131">Para exportar cada tabela de eventos para um hub de eventos diferente, basta deixar o nome do **hub** de eventos vazio e Microsoft 365 Defender fará o restante.</span><span class="sxs-lookup"><span data-stu-id="b0b97-131">To export each event table to a different event hub, simply leave the **Event hub name** empty, and Microsoft 365 Defender will do the rest.</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="b0b97-132">Mapeamento de tipos de dados:</span><span class="sxs-lookup"><span data-stu-id="b0b97-132">Data types mapping:</span></span>

<span data-ttu-id="b0b97-133">Para obter os tipos de dados para propriedades de evento, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b0b97-133">To get the data types for event properties do the following:</span></span>

1. <span data-ttu-id="b0b97-134">Entre no centro [Microsoft 365 segurança e](https://security.microsoft.com) vá para a página De Busca [Avançada.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="b0b97-134">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="b0b97-135">Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="b0b97-135">Run the following query to get the data types mapping for each event:</span></span>
 
   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="b0b97-136">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b0b97-136">Here is an example for Device Info event:</span></span> 

  ![Imagem da Id2 do recurso do hub de eventos](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="b0b97-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b0b97-138">Related topics</span></span>
- [<span data-ttu-id="b0b97-139">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="b0b97-139">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="b0b97-140">Microsoft 365 Defender streaming API</span><span class="sxs-lookup"><span data-stu-id="b0b97-140">Microsoft 365 Defender streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="b0b97-141">Transmitir Microsoft 365 eventos do Defender para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="b0b97-141">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="b0b97-142">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="b0b97-142">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="b0b97-143">Solucionar problemas de conectividade - Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="b0b97-143">Troubleshoot connectivity issues - Azure Event Hubs</span></span>](/azure/event-hubs/troubleshooting-guide)
