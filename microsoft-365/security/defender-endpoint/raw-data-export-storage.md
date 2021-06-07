---
title: Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua Armazenamento de usuário
description: Saiba como configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua Armazenamento conta.
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
ms.custom: api
ms.openlocfilehash: 6be79e4991c9e20c46458eacd97ac0b7b7466bc8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771646"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a><span data-ttu-id="02fcb-104">Configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua Armazenamento conta</span><span class="sxs-lookup"><span data-stu-id="02fcb-104">Configure Microsoft Defender for Endpoint to stream Advanced Hunting events to your Storage account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02fcb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="02fcb-105">**Applies to:**</span></span>
- [<span data-ttu-id="02fcb-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="02fcb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="02fcb-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="02fcb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="02fcb-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="02fcb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a><span data-ttu-id="02fcb-109">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="02fcb-109">Before you begin</span></span>

1. <span data-ttu-id="02fcb-110">Crie uma [Armazenamento em](/azure/storage/common/storage-account-overview) seu locatário.</span><span class="sxs-lookup"><span data-stu-id="02fcb-110">Create a [Storage account](/azure/storage/common/storage-account-overview) in your tenant.</span></span>

2. <span data-ttu-id="02fcb-111">Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.insights**.</span><span class="sxs-lookup"><span data-stu-id="02fcb-111">Log in to your [Azure tenant](https://ms.portal.azure.com/), go to **Subscriptions > Your subscription > Resource Providers > Register to Microsoft.insights**.</span></span>

## <a name="enable-raw-data-streaming"></a><span data-ttu-id="02fcb-112">Habilitar o streaming de dados brutos</span><span class="sxs-lookup"><span data-stu-id="02fcb-112">Enable raw data streaming</span></span>

1. <span data-ttu-id="02fcb-113">Faça logon [no portal do Microsoft Defender para Ponto de Extremidade](https://securitycenter.windows.com) como um \* Administrador **Global** _ ou _\* Administrador _de Segurança_\*\*.</span><span class="sxs-lookup"><span data-stu-id="02fcb-113">Log in to [Microsoft Defender for Endpoint portal](https://securitycenter.windows.com) as a ***Global Administrator** _ or _*_Security Administrator_\*\*.</span></span>

2. <span data-ttu-id="02fcb-114">Vá para [a página Configurações de exportação de dados](https://securitycenter.windows.com/interoperability/dataexport) Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="02fcb-114">Go to [Data export settings page](https://securitycenter.windows.com/interoperability/dataexport) on Microsoft Defender Security Center.</span></span>

3. <span data-ttu-id="02fcb-115">Clique em **Adicionar configurações de exportação de dados.**</span><span class="sxs-lookup"><span data-stu-id="02fcb-115">Click on **Add data export settings**.</span></span>

4. <span data-ttu-id="02fcb-116">Escolha um nome para suas novas configurações.</span><span class="sxs-lookup"><span data-stu-id="02fcb-116">Choose a name for your new settings.</span></span>

5. <span data-ttu-id="02fcb-117">Escolha **Encaminhar eventos para o Azure Armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="02fcb-117">Choose **Forward events to Azure Storage**.</span></span>

6. <span data-ttu-id="02fcb-118">Digite sua **Armazenamento ID do Recurso da Conta.**</span><span class="sxs-lookup"><span data-stu-id="02fcb-118">Type your **Storage Account Resource ID**.</span></span> <span data-ttu-id="02fcb-119">Para obter Armazenamento **ID** do Recurso de Conta do Armazenamento, vá para Armazenamento página da sua conta no portal do [Azure](https://ms.portal.azure.com/) > guia propriedades > copie o texto sob a **ID** do recurso da conta Armazenamento :</span><span class="sxs-lookup"><span data-stu-id="02fcb-119">In order to get your **Storage Account Resource ID**, go to your Storage account page on [Azure portal](https://ms.portal.azure.com/) > properties tab > copy the text under **Storage account resource ID**:</span></span>

   ![Imagem da ID do recurso do hub de eventos1](images/storage-account-resource-id.png)

7. <span data-ttu-id="02fcb-121">Escolha os eventos que deseja transmitir e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02fcb-121">Choose the events you want to stream and click **Save**.</span></span>

## <a name="the-schema-of-the-events-in-the-storage-account"></a><span data-ttu-id="02fcb-122">O esquema dos eventos na conta Armazenamento</span><span class="sxs-lookup"><span data-stu-id="02fcb-122">The schema of the events in the Storage account</span></span>

- <span data-ttu-id="02fcb-123">Um contêiner blob será criado para cada tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="02fcb-123">A blob container will be created for each event type:</span></span> 

  ![Imagem da ID do recurso do hub de eventos2](images/storage-account-event-schema.png)

- <span data-ttu-id="02fcb-125">O esquema de cada linha em um blob é o seguinte JSON:</span><span class="sxs-lookup"><span data-stu-id="02fcb-125">The schema of each row in a blob is the following JSON:</span></span> 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- <span data-ttu-id="02fcb-126">Cada blob contém várias linhas.</span><span class="sxs-lookup"><span data-stu-id="02fcb-126">Each blob contains multiple rows.</span></span>

- <span data-ttu-id="02fcb-127">Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".</span><span class="sxs-lookup"><span data-stu-id="02fcb-127">Each row contains the event name, the time Defender for Endpoint received the event, the tenant it belongs (you will only get events from your tenant), and the event in JSON format in a property called "properties".</span></span>

- <span data-ttu-id="02fcb-128">Para obter mais informações sobre o esquema do Microsoft Defender para eventos do Ponto de Extremidade, consulte [Visão geral de Busca Avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="02fcb-128">For more information about the schema of Microsoft Defender for Endpoint events, see [Advanced Hunting overview](advanced-hunting-overview.md).</span></span>

- <span data-ttu-id="02fcb-129">Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="02fcb-129">In Advanced Hunting, the **DeviceInfo** table has a column named **MachineGroup** which contains the group of the device.</span></span> <span data-ttu-id="02fcb-130">Aqui todos os eventos também serão decorados com esta coluna.</span><span class="sxs-lookup"><span data-stu-id="02fcb-130">Here every event will be decorated with this column as well.</span></span> <span data-ttu-id="02fcb-131">Confira [Grupos de Dispositivos](machine-groups.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="02fcb-131">See [Device Groups](machine-groups.md) for more information.</span></span>

## <a name="data-types-mapping"></a><span data-ttu-id="02fcb-132">Mapeamento de tipos de dados</span><span class="sxs-lookup"><span data-stu-id="02fcb-132">Data types mapping</span></span>

<span data-ttu-id="02fcb-133">Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="02fcb-133">In order to get the data types for our events properties do the following:</span></span>

1. <span data-ttu-id="02fcb-134">Entre [no](https://securitycenter.windows.com) Central de Segurança do Microsoft Defender e vá para a página De Busca [Avançada.](https://securitycenter.windows.com/hunting-package)</span><span class="sxs-lookup"><span data-stu-id="02fcb-134">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com) and go to [Advanced Hunting page](https://securitycenter.windows.com/hunting-package).</span></span>

2. <span data-ttu-id="02fcb-135">Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:</span><span class="sxs-lookup"><span data-stu-id="02fcb-135">Run the following query to get the data types mapping for each event:</span></span> 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- <span data-ttu-id="02fcb-136">Veja um exemplo para o evento Informações do Dispositivo:</span><span class="sxs-lookup"><span data-stu-id="02fcb-136">Here is an example for Device Info event:</span></span> 

  ![Imagem da ID do recurso do hub de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a><span data-ttu-id="02fcb-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="02fcb-138">Related topics</span></span>
- [<span data-ttu-id="02fcb-139">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="02fcb-139">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="02fcb-140">API de streaming do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="02fcb-140">Microsoft Defender for Endpoint Streaming API</span></span>](raw-data-export.md)
- [<span data-ttu-id="02fcb-141">Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="02fcb-141">Stream Microsoft Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)
- [<span data-ttu-id="02fcb-142">Documentação Armazenamento conta do Azure</span><span class="sxs-lookup"><span data-stu-id="02fcb-142">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)