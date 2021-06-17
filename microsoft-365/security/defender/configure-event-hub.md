---
title: Configurar seu Hub de Eventos
description: Saiba como configurar seu Hub de Eventos
keywords: hub de eventos, configurar, insights
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985515"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="ab7bf-104">Configurar seu Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="ab7bf-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab7bf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab7bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab7bf-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ab7bf-107">Saiba como configurar o Hub de Eventos para que ele possa ingerir eventos de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="ab7bf-108">Configurar o Provedor de Recursos necessário na assinatura do Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="ab7bf-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="ab7bf-109">Entre no [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ab7bf-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="ab7bf-110">Selecione Assinaturas { Selecione a assinatura que o hub de **eventos será implantado \> ***em***} \> Provedores de recursos**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="ab7bf-111">Verifique se o **Provedor Microsoft.Insights** está registrado.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="ab7bf-112">Caso contrário, registre-o.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-112">Otherwise, register it.</span></span>

![Imagem de provedores de recursos no Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="ab7bf-114">Instalação Active Directory do Azure Registro de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab7bf-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="ab7bf-115">! [OBSERVAÇÃO] Você deve ter a função administrador ou Active Directory do Azure (AAD) deve ser definida para permitir que não-administradores registrem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="ab7bf-116">Você também deve ter uma função Proprietário ou Administrador de Acesso ao Usuário para atribuir uma função à entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="ab7bf-117">Para obter mais informações, consulte [Create an Azure AD app & service principal in the portal - plataforma de identidade da Microsoft \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="ab7bf-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="ab7bf-118">Crie um novo registro (que cria inerentemente uma entidade de serviço) em Active Directory do Azure **registros do aplicativo Novo \> \> registro.**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="ab7bf-119">Preencha o formulário apenas com o Nome (nenhum URI de redirecionamento é necessário).</span><span class="sxs-lookup"><span data-stu-id="ab7bf-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Imagem do registro de um aplicativo](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Imagem das informações de visão geral](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="ab7bf-122">Crie um segredo clicando em Certificados & **segredos Novo segredo do \> cliente:**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Imagem de certificados e segredos](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="ab7bf-124">Você não poderá acessar o segredo do cliente **novamente, portanto, certifique-se de salvá-lo.**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="ab7bf-125">Namespace do Hub de Eventos de Instalação</span><span class="sxs-lookup"><span data-stu-id="ab7bf-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="ab7bf-126">Criar um Namespace do Hub de Eventos:</span><span class="sxs-lookup"><span data-stu-id="ab7bf-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="ab7bf-127">Vá **para Hubs \>** de Eventos Adicionar e selecione a camada de preços, unidades de transferência e Inflação Automática (exige preços padrão e recursos) apropriados para a carga que você está esperando.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="ab7bf-128">Para obter mais informações, consulte [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="ab7bf-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="ab7bf-129">Você pode usar um hub de eventos existente, mas a produtividade e o dimensionamento são definidos no nível do namespace, portanto, é recomendável colocar um hub de eventos em seu próprio namespace.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Imagem do espaço de nome do Hub de Eventos](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="ab7bf-131">Você também precisará da ID de Recurso deste Namespace do Hub de Eventos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="ab7bf-132">Vá para suas propriedades de namespace de hubs de eventos do \> Azure.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="ab7bf-133">Copie o texto em ID do Recurso e grave-o para uso durante a seção Configuração do M365 abaixo.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Imagem das propriedades](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="ab7bf-135">Depois que o Namespace do Hub de Eventos for criado, você precisará adicionar a Entidade de Serviço de Registro de Aplicativo como Leitor, Receptor de Dados de Hubs de Eventos do Azure e o usuário que fará logon no Microsoft 365 Defender como Colaborador (isso também pode ser feito no nível de Grupo de Recursos ou Assinatura).</span><span class="sxs-lookup"><span data-stu-id="ab7bf-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="ab7bf-136">Isso é feito no Controle de Acesso para Namespace de Hubs de Eventos **\> (IAM) \> Adicionar** e verificar em **Atribuições de função**:</span><span class="sxs-lookup"><span data-stu-id="ab7bf-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Imagem do controle de acesso](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="ab7bf-138">Hub de Eventos de Instalação</span><span class="sxs-lookup"><span data-stu-id="ab7bf-138">Setup Event Hub</span></span>


<span data-ttu-id="ab7bf-139">**Opção 1:**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-139">**Option 1:**</span></span>

<span data-ttu-id="ab7bf-140">Você pode criar um Hub de  Eventos em seu Namespace e todos os Tipos de Eventos (Tabelas) selecionados para exportar serão gravados neste **hub** de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="ab7bf-141">**Opção 2:**</span><span class="sxs-lookup"><span data-stu-id="ab7bf-141">**Option 2:**</span></span>

<span data-ttu-id="ab7bf-142">Em vez de exportar todos os Tipos de Eventos (Tabelas) para um Hub de Eventos, você pode exportar cada tabela para um Hub de Eventos diferente dentro do Namespace do Hub de Eventos (um Hub de Eventos por Tipo de Evento).</span><span class="sxs-lookup"><span data-stu-id="ab7bf-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="ab7bf-143">Nesta opção, Microsoft 365 Defender criará Hubs de Eventos para você.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="ab7bf-144">Se você estiver usando um Namespace de Hub de Eventos que não faz parte de um Cluster de Hub de Eventos, você só poderá escolher até 10 Tipos de Eventos (Tabelas) para exportar em cada Export Configurações que você definir, devido a uma limitação do Azure de 10 Hubs de Eventos por namespace do Hub de Eventos. </span><span class="sxs-lookup"><span data-stu-id="ab7bf-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="ab7bf-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ab7bf-145">For example:</span></span>

![Imagem do exemplo hub de eventos](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="ab7bf-147">Se você escolher essa opção, poderá ir para a seção Configurar Microsoft 365 Defender [para enviar tabelas de email.](#configure-microsoft-365-defender-to-send-email-tables)</span><span class="sxs-lookup"><span data-stu-id="ab7bf-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="ab7bf-148">Crie um Hub de Eventos em seu Namespace selecionando **Hubs de Eventos \> + Hub de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="ab7bf-149">A Contagem de Partição permite taxa de transferência adicional por meio do paralelismo, portanto, é recomendável aumentar esse número com base na carga que você está esperando.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="ab7bf-150">Os valores padrão de Retenção e Captura de Mensagens de 1 e Off são recomendados.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Imagem de criar Hub de Eventos](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="ab7bf-152">Para esse Hub de Eventos (não namespace), você precisará configurar uma Política de Acesso Compartilhado com Enviar, Ouvir Declarações.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="ab7bf-153">Clique em suas políticas de acesso compartilhado do Hub de Eventos **\> + \> Adicionar** e, em seguida, dê a ele um nome de Política (não usado em outro lugar) e verifique **Enviar** e **Ouvir**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Imagem das políticas de acesso compartilhado](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="ab7bf-155">Configurar Microsoft 365 Defender para enviar tabelas de email</span><span class="sxs-lookup"><span data-stu-id="ab7bf-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="ab7bf-156">Configuração Microsoft 365 Defender enviar tabelas de email para o Splunk por meio do Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="ab7bf-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="ab7bf-157">Faça logon Microsoft 365 Defender <https://security.microsoft.com> com uma conta que atenda a todos os seguintes requisitos de função:</span><span class="sxs-lookup"><span data-stu-id="ab7bf-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="ab7bf-158">Função de colaborador no nível de Recurso *de Namespace* do Hub de Eventos ou superior para o Hub de Eventos para o que você exportará.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="ab7bf-159">Sem isso, você receberá um erro de exportação ao tentar salvar as configurações.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="ab7bf-160">Função de Administrador Global ou Administrador de Segurança no locatário vinculado ao Microsoft 365 Defender e ao Azure.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Imagem do portal de segurança](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="ab7bf-162">Clique em **Exportar Dados Brutos \> +Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="ab7bf-163">Agora você usará os dados gravados acima.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="ab7bf-164">**Nome**: isso é local e deve ser o que funciona em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="ab7bf-165">**Encaminhar eventos para o hub de eventos**: Selecione essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="ab7bf-166">**ID do Recurso event-hub:** esta é a ID do Recurso de Namespace do Hub de Eventos que você gravou acima ao configurar o Hub de Eventos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="ab7bf-167">**Nome do Hub de** Evento : se você criou um Hub de Eventos dentro do namespace do Hub de Eventos, colar o nome do Hub de Eventos que você gravou acima.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="ab7bf-168">Se você optar por permitir Microsoft 365 Defender criar Hubs de Eventos por Tipos de Eventos (Tabelas) para você, deixe este campo vazio.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="ab7bf-169">**Tipos de** evento : selecione as tabelas de Busca Avançada que você deseja encaminhar para o Hub de Eventos e, em seguida, para seu aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="ab7bf-170">As tabelas de alerta são Microsoft 365 Defender, as tabelas dispositivos são do Microsoft Defender para Ponto de Extremidade (EDR) e as tabelas de email são do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ab7bf-171">Eventos de email registra todas as transações de email.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="ab7bf-172">A URL (SafeLinks), Attachment (Cofre Attachments) e Eventos de Pós-Entrega (ZAP) também são gravadas e podem ser ingressada nos Eventos de Email no campo NetworkMessageId.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Imagem das configurações da API de streaming](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="ab7bf-174">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="ab7bf-175">Verifique se os eventos estão sendo exportados para o Hub de Eventos</span><span class="sxs-lookup"><span data-stu-id="ab7bf-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="ab7bf-176">Você pode verificar se os eventos estão sendo enviados para o Hub de Eventos executando uma consulta de Busca Avançada básica.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="ab7bf-177">Selecione **Procurar Consulta de Busca \> \> Avançada** e insira a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="ab7bf-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="ab7bf-178">Isso mostrará quantos emails foram recebidos na última hora ingressados em todas as outras tabelas.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="ab7bf-179">Ele também mostrará se você estiver vendo eventos que podem ser exportados para o hub de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="ab7bf-180">Se essa contagem mostrar 0, você não verá nenhum dado saindo para o Hub de Eventos.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Imagem da busca avançada](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="ab7bf-182">Depois de verificar se há dados a exportar, você pode exibir o Hub de Eventos para verificar se as mensagens estão sendo recebidas.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="ab7bf-183">Isso pode levar até uma hora.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="ab7bf-184">No Azure, vá para Hubs de Eventos Clique nos Hubs de Eventos do **\> Namespace \> Clique no Hub \> de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="ab7bf-185">Em **Visão Geral,** role para baixo e no gráfico Mensagens, você deve ver Mensagens de Entrada.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="ab7bf-186">Se você não vir nenhum resultado, não haverá mensagens para seu aplicativo personalizado ingerir.</span><span class="sxs-lookup"><span data-stu-id="ab7bf-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Imagem da guia visão geral com mensagens](../../media/e88060e315d76e74269a3fc866df047f.png)
