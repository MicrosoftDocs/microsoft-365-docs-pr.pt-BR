---
title: Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento.
keywords: exportação de dados brutos, API de streaming, API, Hubs de Eventos, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
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
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029652"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="497f7-104">Configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="497f7-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="497f7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="497f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="497f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="497f7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="497f7-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="497f7-107">Before you begin</span></span>

1. <span data-ttu-id="497f7-108">Crie uma [conta de armazenamento](/azure/storage/common/storage-account-overview) em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="497f7-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="497f7-109">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="497f7-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="497f7-110">Habilitar o streaming de dados brutos</span><span class="sxs-lookup"><span data-stu-id="497f7-110">Enable raw data streaming</span></span>

1. <span data-ttu-id="497f7-111">Faça logon no portal do Microsoft 365 Defender ( ) como <https://security.microsoft.com> um \* Administrador **Global** _ ou _\* Administrador _de Segurança_\*\*.</span><span class="sxs-lookup"><span data-stu-id="497f7-111">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="497f7-112">Vá para **Configurações** da API de Streaming do \> **Microsoft 365** \> Defender.</span><span class="sxs-lookup"><span data-stu-id="497f7-112">Go to **Settings** \> **Microsoft 365 Defender** \> **Streaming API**.</span></span> <span data-ttu-id="497f7-113">Para ir diretamente para a página **api de streaming,** use <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .</span><span class="sxs-lookup"><span data-stu-id="497f7-113">To go directly to the **Streaming API** page, use <https://security.microsoft.com/settings/mtp_settings/raw_data_export>.</span></span>

3. <span data-ttu-id="497f7-114">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="497f7-114">Click **Add**.</span></span>

4. <span data-ttu-id="497f7-115">No **flyout Adicionar novas configurações de API de Streaming exibidas,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="497f7-115">In the **Add new Streaming API settings** flyout that appears, configure the following settings:</span></span>
   1. <span data-ttu-id="497f7-116">**Nome**: escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="497f7-116">**Name**: Choose a name for your new settings.</span></span>
   2. <span data-ttu-id="497f7-117">Selecione **Encaminhar eventos para o Armazenamento do Azure.**</span><span class="sxs-lookup"><span data-stu-id="497f7-117">Select **Forward events to Azure Storage**.</span></span>
   3. <span data-ttu-id="497f7-118">Na caixa **ID do Recurso** de Conta de Armazenamento exibida, digite sua **ID** de Recurso de Conta de Armazenamento .</span><span class="sxs-lookup"><span data-stu-id="497f7-118">In the **Storage Account Resource ID** box that appears, type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="497f7-119">Para obter sua **ID** de Recurso de Conta de Armazenamento, abra o portal do Azure em , clique em Contas de armazenamento vá para a guia Propriedades copiar o texto em <https://portal.azure.com>  \> \> **ID** de Recurso da Conta de Armazenamento .</span><span class="sxs-lookup"><span data-stu-id="497f7-119">To get your **Storage Account Resource ID**, open the Azure portal at <https://portal.azure.com>, click **Storage accounts** \> go to the properties tab \> copy the text under **Storage Account Resource ID**.</span></span>

      ![Imagem da ID do recurso do hub de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

   4. <span data-ttu-id="497f7-121">De volta ao **flyout Adicionar novas configurações de API de Streaming,** escolha **os tipos de** evento que você deseja transmitir.</span><span class="sxs-lookup"><span data-stu-id="497f7-121">Back on the **Add new Streaming API settings** flyout, choose the **Event types** that you want to stream.</span></span>

   <span data-ttu-id="497f7-122">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="497f7-122">When you're finished, click **Submit**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="497f7-123">O esquema dos eventos na conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="497f7-123">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="497f7-124">Um contêiner blob será criado para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="497f7-124">A blob container will be created for each event type:</span></span>

  ![Imagem da ID do recurso do hub de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="497f7-126">O esquema de cada linha em um blob é o seguinte JSON:</span><span class="sxs-lookup"><span data-stu-id="497f7-126">The schema of each row in a blob is the following JSON:</span></span>

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- <span data-ttu-id="497f7-127">Cada blob contém várias linhas.</span><span class="sxs-lookup"><span data-stu-id="497f7-127">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="497f7-128">Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".</span><span class="sxs-lookup"><span data-stu-id="497f7-128">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="497f7-129">Para obter mais informações sobre o esquema dos eventos do Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="497f7-129">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="497f7-130">Mapeamento de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="497f7-130">Data types mapping</span></span>

<span data-ttu-id="497f7-131">Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="497f7-131">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="497f7-132">Faça logoff no portal do Microsoft 365 Defender ( ) e <https://security.microsoft.com> vá para **Hunting** \> **Advanced hunting**.</span><span class="sxs-lookup"><span data-stu-id="497f7-132">Log in to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Hunting** \> **Advanced hunting**.</span></span> <span data-ttu-id="497f7-133">Para ir diretamente para a **página De busca** avançada, use <security.microsoft.com/advanced-hunting>.</span><span class="sxs-lookup"><span data-stu-id="497f7-133">To go directly to the **Advanced hunting** page, use <security.microsoft.com/advanced-hunting>.</span></span>

2. <span data-ttu-id="497f7-134">Na **guia Consulta,** execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="497f7-134">On the **Query** tab, run the following query to get the data types mapping for each event:</span></span>

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- <span data-ttu-id="497f7-135">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="497f7-135">Here is an example for Device Info event:</span></span>

  ![Imagem da ID do recurso do hub de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="497f7-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="497f7-137">Related topics</span></span>

- [<span data-ttu-id="497f7-138">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="497f7-138">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="497f7-139">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="497f7-139">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="497f7-140">Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="497f7-140">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="497f7-141">Documentação da Conta de Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="497f7-141">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
