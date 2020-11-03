---
title: Personalizar os relatórios na análise de uso do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Saiba como personalizar relatórios no navegador e no Power BI desktop.
ms.openlocfilehash: 8baeb1a9f48d8f1ccdb591a60fefe863502344b6
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841418"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="f52d8-103">Personalizar os relatórios na análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f52d8-103">Customize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f52d8-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="f52d8-104">The admin center is changing.</span></span> <span data-ttu-id="f52d8-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f52d8-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f52d8-106">A análise de uso do Microsoft 365 fornece um painel no Power BI que oferece informações sobre como os usuários adotam e usam o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f52d8-106">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="f52d8-107">O painel é apenas um ponto de partida para interagir com os dados de uso.</span><span class="sxs-lookup"><span data-stu-id="f52d8-107">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="f52d8-108">Os relatórios podem ser personalizados para informações mais personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f52d8-108">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="f52d8-109">Você também pode usar a área de trabalho do Power BI para personalizar ainda mais seus relatórios conectando-os a outras fontes de dados para obter informações mais detalhadas sobre sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f52d8-109">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="f52d8-110">Personalizando relatórios no navegador</span><span class="sxs-lookup"><span data-stu-id="f52d8-110">Customizing reports in the browser</span></span>

<span data-ttu-id="f52d8-111">Os dois exemplos a seguir mostram como modificar um visual existente e como criar um novo visual.</span><span class="sxs-lookup"><span data-stu-id="f52d8-111">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="f52d8-112">Modifique um visual existente</span><span class="sxs-lookup"><span data-stu-id="f52d8-112">Modify an existing visual</span></span>

<span data-ttu-id="f52d8-113">Este exemplo mostra como modificar a guia de **ativação** dentro do relatório de **ativação/licenciamento** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-113">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="f52d8-114">No relatório de **ativação/licenciamento** , selecione a guia **ativação** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-114">Within the **Activation/Licensing** report, select the **Activation** tab.</span></span>
    
2. <span data-ttu-id="f52d8-115">Insira o modo de edição escolhendo o botão **Editar** na parte superior através do ![ botão mais página no botão Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) .</span><span class="sxs-lookup"><span data-stu-id="f52d8-115">Enter the edit mode by choosing the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="f52d8-117">No canto superior direito, escolha **duplicar esta página** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-117">On the top right, choose **Duplicate this page** .</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="f52d8-119">No canto inferior direito, escolha qualquer um dos gráficos de barras que mostram a contagem de ativação de usuários com base no sistema operacional, como Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="f52d8-119">In the bottom right, choose any of the bar-charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="f52d8-120">Na área **visualizações** para a direita, para remover a **contagem de Mac** do Visual, selecione o **X** ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="f52d8-120">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, select the **X** next to it.</span></span>

    ![Remover contagem de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="f52d8-122">Criar um novo visual</span><span class="sxs-lookup"><span data-stu-id="f52d8-122">Create a new visual</span></span>

<span data-ttu-id="f52d8-123">O exemplo a seguir mostra como criar um novo visual para rastrear novos usuários do Yammer mensalmente.</span><span class="sxs-lookup"><span data-stu-id="f52d8-123">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="f52d8-124">Vá para o relatório de **uso do produto** usando a navegação esquerda e selecione a guia **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-124">Go to the **Product Usage** report using the left nav and select the **Yammer** tab.</span></span>
    
2. <span data-ttu-id="f52d8-125">Alterne para o modo de edição escolhendo ![ o botão mais páginas no Power bi ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-125">Switch to edit mode by choosing ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit** .</span></span> 
    
3. <span data-ttu-id="f52d8-126">Na parte inferior da página, selecione o botão</span><span class="sxs-lookup"><span data-stu-id="f52d8-126">At the bottom of the page, select the</span></span> ![O botão Adicionar página no Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="f52d8-128">para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="f52d8-128">to create a new page.</span></span>
  
4. <span data-ttu-id="f52d8-129">Na área **visualizações** à direita, escolha o **gráfico de barras empilhadas** (linha superior, primeiro à esquerda).</span><span class="sxs-lookup"><span data-stu-id="f52d8-129">In the **Visualizations** area to the right, choose the **Stacked bar chart** (top row, first from left).</span></span>

    ![Selecionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="f52d8-131">Selecione o canto inferior direito dessa visualização e arraste para aumentá-lo.</span><span class="sxs-lookup"><span data-stu-id="f52d8-131">Select the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="f52d8-132">Na área **campos** à direita, expanda a tabela **calendário** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-132">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="f52d8-133">Arraste **MonthName** para a área de campos, diretamente abaixo do cabeçalho **Eixo** na área **Visualizações** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-133">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Arrastar nome do mês](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="f52d8-135">Na área **Campos** à direita, expanda a tabela **TenantProductUsage** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-135">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="f52d8-136">Arraste **FirstTimeUsers** para a área de campos, diretamente abaixo do cabeçalho **Valor** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-136">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="f52d8-137">Arraste **Produto** para a área **Filtros** , diretamente abaixo do cabeçalho **Filtros de nível visual** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-137">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="f52d8-138">Na área **Tipo de filtro** que aparece, selecione a caixa de seleção **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-138">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Caixa de seleção selecionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="f52d8-140">Logo abaixo da lista de visualizações, escolha o ícone **Format** Icon ![ Format no Power bi Visualizaions ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) .</span><span class="sxs-lookup"><span data-stu-id="f52d8-140">Just below the list of visualizations, choose the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="f52d8-141">Expanda o título e altere o valor do **Título do Texto** para **Usuários do Yammer pela primeira vez por mês** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-141">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month** .</span></span>
    
14. <span data-ttu-id="f52d8-142">Altere o valor do **Tamanho do texto** para **12** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-142">Change the **Text Size** value to **12** .</span></span>
    
15. <span data-ttu-id="f52d8-143">Altere o título da nova página editando o nome da página no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="f52d8-143">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="f52d8-144">Salve o relatório clicando em modo de **exibição de leitura** na parte superior e em **salvar** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-144">Save out the report by Clicking on **Reading View** on top and then **Save** .</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="f52d8-145">Personalizar os relatórios na área de trabalho do Power BI</span><span class="sxs-lookup"><span data-stu-id="f52d8-145">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="f52d8-p103">Para a maioria dos clientes, modificar os relatórios e os gráficos visuais na Web do Power BI será suficiente. Para alguns, porém, pode haver necessidade de juntar esses dados a outras fontes de dados para obter informações mais complexas e contextuais para seus próprios negócios, caso em que eles podem personalizar e criar relatórios adicionais usando a Área de trabalho do Power BI. Você pode baixar a [Área de trabalho do Power BI](https://go.microsoft.com/fwlink/p/?linkid=849797) gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="f52d8-p103">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="f52d8-149">Use as APIs de relatórios</span><span class="sxs-lookup"><span data-stu-id="f52d8-149">Use the reporting APIs</span></span>

<span data-ttu-id="f52d8-150">Você pode começar conectando-se diretamente com as APIs de relatório ODATA da Microsoft 365 que alimentam esses relatórios.</span><span class="sxs-lookup"><span data-stu-id="f52d8-150">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="f52d8-151">Vá até **obter dados** \> **Outros** \> **Feed ODATA** \> **Conectar** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-151">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect** .</span></span>
    
2. <span data-ttu-id="f52d8-152">Na janela URL, digite "https:// <i></i> reports.Office.com/PBI/v1.0/ \<tenantid\> "</span><span class="sxs-lookup"><span data-stu-id="f52d8-152">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="f52d8-153">**Observação:** As APIs de relatórios estão em visualização e estão sujeitas a alterações até que entrem em produção.</span><span class="sxs-lookup"><span data-stu-id="f52d8-153">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="f52d8-155">Digite suas credenciais de administrador do Microsoft 365 (organização ou escola) para se autenticar no Microsoft 365 quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="f52d8-155">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="f52d8-156">Consulte as [perguntas frequentes](usage-analytics.md#faq) para obter mais informações sobre quem tem permissão para acessar os relatórios de aplicativos de modelo de adoção do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f52d8-156">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="f52d8-157">Uma vez que a conexão é autorizada, você verá a janela do Navegador que mostra os conjuntos de dados disponíveis para se conectar.</span><span class="sxs-lookup"><span data-stu-id="f52d8-157">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="f52d8-158">Selecione tudo e escolha **carregar** .</span><span class="sxs-lookup"><span data-stu-id="f52d8-158">Select all and choose **Load** .</span></span>
    
    <span data-ttu-id="f52d8-159">Isso baixará os dados em sua Área de trabalho do Power BI.</span><span class="sxs-lookup"><span data-stu-id="f52d8-159">This will download the data into your Power BI Desktop.</span></span> <span data-ttu-id="f52d8-160">Salve este arquivo e então você poderá começar a criar os relatórios de que precisa.</span><span class="sxs-lookup"><span data-stu-id="f52d8-160">Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valores de ODATA disponíveis na API de relatórios](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="f52d8-162">Usar o modelo de análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f52d8-162">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="f52d8-163">Você também pode usar o arquivo de modelo do Power BI que corresponde aos relatórios de análise de uso do Microsoft 365 como ponto de partida para se conectar aos dados.</span><span class="sxs-lookup"><span data-stu-id="f52d8-163">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="f52d8-164">A vantagem de usar o arquivo .pbit é que ele possui a sequência de conexão já estabelecida.</span><span class="sxs-lookup"><span data-stu-id="f52d8-164">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="f52d8-165">Você também pode aproveitar todas as medidas personalizadas que são criadas, em cima dos dados que o esquema base retorna e criar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="f52d8-165">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="f52d8-166">Você pode baixar o arquivo de modelo do Power BI no centro de download da Microsoft a partir do [centro de download](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="f52d8-166">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="f52d8-167">Depois de baixar o arquivo de modelo do Power BI, siga estas etapas para começar:</span><span class="sxs-lookup"><span data-stu-id="f52d8-167">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="f52d8-168">Abra o arquivo .pbit.</span><span class="sxs-lookup"><span data-stu-id="f52d8-168">Open the pbit file.</span></span>
    
2. <span data-ttu-id="f52d8-169">Digite o valor da ID do locatário na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f52d8-169">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="f52d8-171">Digite suas credenciais de administrador para se autenticar no Microsoft 365 quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="f52d8-171">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="f52d8-172">para obter mais informações sobre quem tem permissão para acessar os relatórios de análise de uso do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f52d8-172">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="f52d8-173">Uma vez autorizado, os dados serão atualizados no arquivo Power BI.</span><span class="sxs-lookup"><span data-stu-id="f52d8-173">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="f52d8-174">A carga de dados pode levar algum tempo, uma vez concluída, você pode salvar o arquivo como um arquivo .pbix e continuar a personalizar os relatórios ou trazer uma fonte de dados adicional para este relatório.</span><span class="sxs-lookup"><span data-stu-id="f52d8-174">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="f52d8-p107">Siga a documentação [Introdução ao Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para entender como criar relatórios, publicá-los no serviço do Power BI e compartilhar com sua organização. Seguir esse caminho para personalização e compartilhamento pode exigir licenças adicionais do Power BI. Confira as [diretrizes de licenciamento](https://go.microsoft.com/fwlink/p/?linkid=849803) do Power BI para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f52d8-p107">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

