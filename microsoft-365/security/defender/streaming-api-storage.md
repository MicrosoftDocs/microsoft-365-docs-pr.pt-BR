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
ms.openlocfilehash: fa61e2fd0591d375a17bad6e166a76c1ca40862e
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028870"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="c49b5-104">Configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="c49b5-104">Configure Microsoft 365 Defender to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c49b5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c49b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="c49b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c49b5-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]


## <a name="before-you-begin"></a><span data-ttu-id="c49b5-107">Antes de começar:</span><span class="sxs-lookup"><span data-stu-id="c49b5-107">Before you begin:</span></span>

1. <span data-ttu-id="c49b5-108">Crie uma [conta de armazenamento](/azure/storage/common/storage-account-overview) em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c49b5-108">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="c49b5-109">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.</span><span class="sxs-lookup"><span data-stu-id="c49b5-109">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.Insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="c49b5-110">Habilitar o streaming de dados brutos:</span><span class="sxs-lookup"><span data-stu-id="c49b5-110">Enable raw data streaming:</span></span>

1. <span data-ttu-id="c49b5-111">Faça logon no Centro de segurança do [Microsoft 365 Defender](https://security.microsoft.com) como um ***Administrador Global** _ ou _* Administrador _de Segurança_\*\*.</span><span class="sxs-lookup"><span data-stu-id="c49b5-111">Log in to [Microsoft 365 Defender security center](https://security.microsoft.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="c49b5-112">Vá para [a página Configurações de exportação de dados](https://security.microsoft.com/settings/mtp_settings/raw_data_export) no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c49b5-112">Go to [Data export settings page](https://security.microsoft.com/settings/mtp_settings/raw_data_export) in Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="c49b5-113">Clique em **Adicionar configurações de exportação de dados.**</span><span class="sxs-lookup"><span data-stu-id="c49b5-113">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="c49b5-114">Escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="c49b5-114">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="c49b5-115">Escolha **Encaminhar eventos para o Armazenamento do Azure.**</span><span class="sxs-lookup"><span data-stu-id="c49b5-115">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="c49b5-116">Digite sua **ID de Recurso de Conta de Armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="c49b5-116">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="c49b5-117">Para obter sua **ID** de Recurso de Conta de Armazenamento, vá para a página Conta de Armazenamento no portal do [Azure](https://ms.portal.azure.com/) > guia propriedades > copiar o texto em **ID** de Recurso da Conta de Armazenamento :</span><span class="sxs-lookup"><span data-stu-id="c49b5-117">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage Account Resource ID**:</span></span>

   ![Imagem da ID do recurso do hub de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

7. <span data-ttu-id="c49b5-119">Escolha os eventos que deseja transmitir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c49b5-119">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="c49b5-120">O esquema dos eventos na conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="c49b5-120">The schema of the events in the Storage account:</span></span>

- <span data-ttu-id="c49b5-121">Um contêiner blob será criado para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="c49b5-121">A blob container will be created for each event type:</span></span> 

  ![Imagem da ID do recurso do hub de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- <span data-ttu-id="c49b5-123">O esquema de cada linha em um blob é o seguinte JSON:</span><span class="sxs-lookup"><span data-stu-id="c49b5-123">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="c49b5-124">Cada blob contém várias linhas.</span><span class="sxs-lookup"><span data-stu-id="c49b5-124">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="c49b5-125">Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".</span><span class="sxs-lookup"><span data-stu-id="c49b5-125">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="c49b5-126">Para obter mais informações sobre o esquema dos eventos do Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c49b5-126">For more information about the schema of Microsoft 365 Defender events, see [Advanced Hunting overview](../defender/advanced-hunting-overview.md).</span></span>


## <a name="data-types-mapping"></a><span data-ttu-id="c49b5-127">Mapeamento de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="c49b5-127">Data types mapping</span></span>

<span data-ttu-id="c49b5-128">Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c49b5-128">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="c49b5-129">Faça logoff no Centro de segurança [do Microsoft 365](https://security.microsoft.com) e vá para [a página Busca Avançada.](https://security.microsoft.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="c49b5-129">Log in to [Microsoft 365 security center](https://security.microsoft.com) and go to [Advanced Hunting page](https://security.microsoft.com/hunting-package).</span></span>

2. <span data-ttu-id="c49b5-130">Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="c49b5-130">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="c49b5-131">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c49b5-131">Here is an example for Device Info event:</span></span> 

  ![Imagem da ID do recurso do hub de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="c49b5-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c49b5-133">Related topics</span></span>
- [<span data-ttu-id="c49b5-134">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="c49b5-134">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="c49b5-135">Microsoft 365 Defender Streaming API</span><span class="sxs-lookup"><span data-stu-id="c49b5-135">Microsoft 365 Defender Streaming API</span></span>](streaming-api.md)
- [<span data-ttu-id="c49b5-136">Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="c49b5-136">Stream Microsoft 365 Defender events to your Azure storage account</span></span>](streaming-api-storage.md)
- [<span data-ttu-id="c49b5-137">Documentação da Conta de Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="c49b5-137">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
