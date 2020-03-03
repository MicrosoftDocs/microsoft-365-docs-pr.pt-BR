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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Saiba como personalizar relatórios no navegador e no Power BI desktop.
ms.openlocfilehash: 6e4bb6cf977607ca6e3b3f57240ac89dbd530e4f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355152"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="5a21f-103">Personalizar os relatórios na análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a21f-103">Customize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="5a21f-104">A análise de uso do Microsoft 365 fornece um painel no Power BI que oferece informações sobre como os usuários adotam e usam o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a21f-104">Microsoft 365 usage analytics provides a dashboard in Power BI that offers insights into how users adopt and use Microsoft 365.</span></span> <span data-ttu-id="5a21f-105">O painel é apenas um ponto de partida para interagir com os dados de uso.</span><span class="sxs-lookup"><span data-stu-id="5a21f-105">The dashboard is just a starting point to interact with the usage data.</span></span> <span data-ttu-id="5a21f-106">Os relatórios podem ser personalizados para informações mais personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5a21f-106">The reports can be customized for more personalized insights.</span></span>
  
<span data-ttu-id="5a21f-107">Você também pode usar a área de trabalho do Power BI para personalizar ainda mais seus relatórios conectando-os a outras fontes de dados para obter informações mais detalhadas sobre sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5a21f-107">You can also use the Power BI desktop to further customize your reports by connecting them to other data sources to gain richer insights about your business.</span></span>
  
## <a name="customizing-reports-in-the-browser"></a><span data-ttu-id="5a21f-108">Personalizando relatórios no navegador</span><span class="sxs-lookup"><span data-stu-id="5a21f-108">Customizing reports in the browser</span></span>

<span data-ttu-id="5a21f-109">Os dois exemplos a seguir mostram como modificar um visual existente e como criar um novo visual.</span><span class="sxs-lookup"><span data-stu-id="5a21f-109">The following two examples show how to modify an existing visual and how to create a new visual.</span></span>
  
### <a name="modify-an-existing-visual"></a><span data-ttu-id="5a21f-110">Modifique um visual existente</span><span class="sxs-lookup"><span data-stu-id="5a21f-110">Modify an existing visual</span></span>

<span data-ttu-id="5a21f-111">Este exemplo mostra como modificar a guia de **ativação** dentro do relatório de **ativação/licenciamento** .</span><span class="sxs-lookup"><span data-stu-id="5a21f-111">This example shows how to modify the **Activation** tab within the **Activation/Licensing** report.</span></span> 
  
1. <span data-ttu-id="5a21f-112">No relatório de **ativação/licenciamento** , clique na guia **ativação** .</span><span class="sxs-lookup"><span data-stu-id="5a21f-112">Within the **Activation/Licensing** report, click on the **Activation** tab.</span></span>
    
2. <span data-ttu-id="5a21f-113">Insira o modo de edição clicando no botão **Editar** na parte superior através do ![botão mais página no botão Power bi](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) .</span><span class="sxs-lookup"><span data-stu-id="5a21f-113">Enter the edit mode by clicking the **Edit** button on the top through the ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) button.</span></span> 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. <span data-ttu-id="5a21f-115">No canto superior direito, clique em **duplicar esta página**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-115">On the top right, click **Duplicate this page**.</span></span>
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. <span data-ttu-id="5a21f-117">No canto inferior direito, clique em qualquer um dos gráficos de barras mostrando a contagem de ativação de usuários com base no sistema operacional, como Android, iOS, Mac, etc.</span><span class="sxs-lookup"><span data-stu-id="5a21f-117">In the bottom right, click on any of the bar charts showing the count of users activating based on the OS such as Android, iOS, Mac, etc.</span></span>
    
5. <span data-ttu-id="5a21f-118">Na área **visualizações** para a direita, para remover a **contagem de Mac** do Visual, clique no **X** ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="5a21f-118">In the **Visualizations** area to the right, in order to remove **Mac Count** from the visual, click on the **X** next to it.</span></span>

    ![Remover contagem de Mac](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a><span data-ttu-id="5a21f-120">Criar um novo visual</span><span class="sxs-lookup"><span data-stu-id="5a21f-120">Create a new visual</span></span>

<span data-ttu-id="5a21f-121">O exemplo a seguir mostra como criar um novo visual para rastrear novos usuários do Yammer mensalmente.</span><span class="sxs-lookup"><span data-stu-id="5a21f-121">The following example shows how to create a new visual to track new Yammer users on monthly basis.</span></span>
  
1. <span data-ttu-id="5a21f-122">Vá para o relatório de **uso do produto** usando a barra de navegação esquerda e clique na guia do **Yammer** .</span><span class="sxs-lookup"><span data-stu-id="5a21f-122">Go to the **Product Usage** report using the left nav and click on **Yammer** tab.</span></span>
    
2. <span data-ttu-id="5a21f-123">Alterne para o modo de edição clicando ![no botão mais página no Power bi](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) e **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-123">Switch to edit mode by clicking on ![The more page button in Power BI](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) and **Edit**.</span></span> 
    
3. <span data-ttu-id="5a21f-124">Na parte inferior da página, clique em</span><span class="sxs-lookup"><span data-stu-id="5a21f-124">At the bottom of the page, click on</span></span> ![O botão Adicionar página no Power BI](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) <span data-ttu-id="5a21f-126">para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="5a21f-126">to create a new page.</span></span>
  
4. <span data-ttu-id="5a21f-127">Na área **visualizações** à direita, clique no **gráfico de barras empilhadas** (linha superior, primeiro à esquerda).</span><span class="sxs-lookup"><span data-stu-id="5a21f-127">In the **Visualizations** area to the right, click the **Stacked bar chart** (top row, first from left).</span></span>

    ![Selecionar gráfico de barras](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. <span data-ttu-id="5a21f-129">Clique na parte inferior direita dessa visualização e arraste para ampliá-la.</span><span class="sxs-lookup"><span data-stu-id="5a21f-129">Click the bottom right of that visualization and drag to make it larger.</span></span>

6. <span data-ttu-id="5a21f-130">Na área **campos** à direita, expanda a tabela **calendário** .</span><span class="sxs-lookup"><span data-stu-id="5a21f-130">In the **Fields** area to the right, expand the **Calendar** table.</span></span>

7. <span data-ttu-id="5a21f-131">Arraste **MonthName** para a área de campos, diretamente abaixo do cabeçalho **Eixo** na área **Visualizações**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-131">Drag **MonthName** to the fields area, directly below the **Axis** heading in the **Visualizations** area.</span></span>
 
    ![Arrastar nome do mês](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. <span data-ttu-id="5a21f-133">Na área **Campos** à direita, expanda a tabela **TenantProductUsage**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-133">In the **Fields** area to the right, expand the **TenantProductUsage** table.</span></span>

9. <span data-ttu-id="5a21f-134">Arraste **FirstTimeUsers** para a área de campos, diretamente abaixo do cabeçalho **Valor**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-134">Drag **FirstTimeUsers** to the fields area, directly below the **Value** heading.</span></span>

10. <span data-ttu-id="5a21f-135">Arraste **Produto** para a área **Filtros**, diretamente abaixo do cabeçalho **Filtros de nível visual**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-135">Drag **Product** to the **Filters** area, directly below the **Visual level filters** heading.</span></span>

11. <span data-ttu-id="5a21f-136">Na área **Tipo de filtro** que aparece, selecione a caixa de seleção **Yammer**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-136">In the **Filter Type** area that appears, select the **Yammer** check box.</span></span>

    ![Caixa de seleção selecionar Yammer](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. <span data-ttu-id="5a21f-138">Logo abaixo da lista de visualizações, **clique no ícone Format** Icon ![Format no Power bi Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span><span class="sxs-lookup"><span data-stu-id="5a21f-138">Just below the list of visualizations, click the **Format** icon ![Format icon in Power BI Visualizaions](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png).</span></span>

13. <span data-ttu-id="5a21f-139">Expanda o título e altere o valor do **Título do Texto** para **Usuários do Yammer pela primeira vez por mês**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-139">Expand Title and change the **Title Text** value to **First-Time Yammer Users by Month**.</span></span>
    
14. <span data-ttu-id="5a21f-140">Altere o valor do **Tamanho do texto** para **12**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-140">Change the **Text Size** value to **12**.</span></span>
    
15. <span data-ttu-id="5a21f-141">Altere o título da nova página editando o nome da página no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="5a21f-141">Change the title of the new page by editing the name of the page on bottom right.</span></span>

16.  <span data-ttu-id="5a21f-142">Salve o relatório clicando em modo de **exibição de leitura** na parte superior e em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-142">Save out the report by Clicking on **Reading View** on top and then **Save**.</span></span>
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a><span data-ttu-id="5a21f-143">Personalizar os relatórios na área de trabalho do Power BI</span><span class="sxs-lookup"><span data-stu-id="5a21f-143">Customizing the reports in Power BI Desktop</span></span>

<span data-ttu-id="5a21f-p102">Para a maioria dos clientes, modificar os relatórios e os gráficos visuais na Web do Power BI será suficiente. Para alguns, porém, pode haver necessidade de juntar esses dados a outras fontes de dados para obter informações mais complexas e contextuais para seus próprios negócios, caso em que eles podem personalizar e criar relatórios adicionais usando a Área de trabalho do Power BI. Você pode baixar a [Área de trabalho do Power BI](https://go.microsoft.com/fwlink/p/?linkid=849797) gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="5a21f-p102">For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.</span></span> 
  
### <a name="use-the-reporting-apis"></a><span data-ttu-id="5a21f-147">Use as APIs de relatórios</span><span class="sxs-lookup"><span data-stu-id="5a21f-147">Use the reporting APIs</span></span>

<span data-ttu-id="5a21f-148">Você pode começar conectando-se diretamente com as APIs de relatório ODATA da Microsoft 365 que alimentam esses relatórios.</span><span class="sxs-lookup"><span data-stu-id="5a21f-148">You can start by connecting directly to the ODATA reporting APIs from Microsoft 365 that power these reports.</span></span>
  
1. <span data-ttu-id="5a21f-149">Vá até **obter dados** \> **Outros** \> **Feed ODATA** \> **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-149">Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.</span></span>
    
2. <span data-ttu-id="5a21f-150">Na janela URL, digite "https://<i></i>Reports.Office.com/PBI/v1.0/\<tenantid\>"</span><span class="sxs-lookup"><span data-stu-id="5a21f-150">In the URL window enter "https://<i></i>reports.office.com/pbi/v1.0/\<tenantid\>"</span></span>
    
    <span data-ttu-id="5a21f-151">**Observação:** As APIs de relatórios estão em visualização e estão sujeitas a alterações até que entrem em produção.</span><span class="sxs-lookup"><span data-stu-id="5a21f-151">**NOTE:** The reporting APIs are in preview and are subject to change until they go into production.</span></span> 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. <span data-ttu-id="5a21f-153">Digite suas credenciais de administrador do Microsoft 365 (organização ou escola) para se autenticar no Microsoft 365 quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="5a21f-153">Enter your Microsoft 365 (organization or school) admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
    <span data-ttu-id="5a21f-154">Consulte as [perguntas frequentes](usage-analytics.md#faq) para obter mais informações sobre quem tem permissão para acessar os relatórios de aplicativos de modelo de adoção do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a21f-154">See the [FAQ](usage-analytics.md#faq) for more information about who is allowed to access the Microsoft 365 Adoption template app reports.</span></span> 
    
4. <span data-ttu-id="5a21f-155">Uma vez que a conexão é autorizada, você verá a janela do Navegador que mostra os conjuntos de dados disponíveis para se conectar.</span><span class="sxs-lookup"><span data-stu-id="5a21f-155">Once the connection is authorized, you will see the Navigator window that shows the datasets available to connect to.</span></span>
    
    <span data-ttu-id="5a21f-156">Selecione todos e clique em **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="5a21f-156">Select all and click on **Load**.</span></span>
    
    <span data-ttu-id="5a21f-p103">Isso baixará os dados em sua Área de trabalho do Power BI. Salve este arquivo e então você poderá começar a criar os relatórios de que precisa.</span><span class="sxs-lookup"><span data-stu-id="5a21f-p103">This will download the data into your Power BI Desktop. Save this file and then you can start creating the reports you need.</span></span>
    
    ![Valores de ODATA disponíveis na API de relatórios](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a><span data-ttu-id="5a21f-160">Usar o modelo de análise de uso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a21f-160">Use the Microsoft 365 usage analytics template</span></span>

<span data-ttu-id="5a21f-161">Você também pode usar o arquivo de modelo do Power BI que corresponde aos relatórios de análise de uso do Microsoft 365 como ponto de partida para se conectar aos dados.</span><span class="sxs-lookup"><span data-stu-id="5a21f-161">You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data.</span></span> <span data-ttu-id="5a21f-162">A vantagem de usar o arquivo .pbit é que ele possui a sequência de conexão já estabelecida.</span><span class="sxs-lookup"><span data-stu-id="5a21f-162">The advantage of using the pbit file is that it has the connection string already established.</span></span> <span data-ttu-id="5a21f-163">Você também pode aproveitar todas as medidas personalizadas que são criadas, em cima dos dados que o esquema base retorna e criar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="5a21f-163">You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.</span></span>
  
<span data-ttu-id="5a21f-164">Você pode baixar o arquivo de modelo do Power BI no centro de download da Microsoft a partir do [centro de download](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span><span class="sxs-lookup"><span data-stu-id="5a21f-164">You can download the Power BI template file from the Microsoft download center from the [Download center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).</span></span> <span data-ttu-id="5a21f-165">Depois de baixar o arquivo de modelo do Power BI, siga estas etapas para começar:</span><span class="sxs-lookup"><span data-stu-id="5a21f-165">After you have downloaded the Power BI template file follow these steps to get started:</span></span>
  
1. <span data-ttu-id="5a21f-166">Abra o arquivo .pbit.</span><span class="sxs-lookup"><span data-stu-id="5a21f-166">Open the pbit file.</span></span>
    
2. <span data-ttu-id="5a21f-167">Digite o valor da ID do locatário na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5a21f-167">Enter your tenant id value in the dialog.</span></span>
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. <span data-ttu-id="5a21f-169">Digite suas credenciais de administrador para se autenticar no Microsoft 365 quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="5a21f-169">Enter your admin credentials to authenticate to Microsoft 365 when prompted.</span></span>
    
     <span data-ttu-id="5a21f-170">para obter mais informações sobre quem tem permissão para acessar os relatórios de análise de uso do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a21f-170">for more information about who is allowed to access the Microsoft 365 usage analytics reports.</span></span> 
    
    <span data-ttu-id="5a21f-171">Uma vez autorizado, os dados serão atualizados no arquivo Power BI.</span><span class="sxs-lookup"><span data-stu-id="5a21f-171">Once authorized, the data will be refreshed in the Power BI file.</span></span>
    
    <span data-ttu-id="5a21f-172">A carga de dados pode levar algum tempo, uma vez concluída, você pode salvar o arquivo como um arquivo .pbix e continuar a personalizar os relatórios ou trazer uma fonte de dados adicional para este relatório.</span><span class="sxs-lookup"><span data-stu-id="5a21f-172">Data load may take some time, once complete, you can save the file as a .pbix file and continue to customize the reports or bring an additional data source into this report.</span></span>
    
4. <span data-ttu-id="5a21f-p106">Siga a documentação [Introdução ao Power BI](https://go.microsoft.com/fwlink/?linkid=849802) para entender como criar relatórios, publicá-los no serviço do Power BI e compartilhar com sua organização. Seguir esse caminho para personalização e compartilhamento pode exigir licenças adicionais do Power BI. Confira as [diretrizes de licenciamento](https://go.microsoft.com/fwlink/p/?linkid=849803) do Power BI para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5a21f-p106">Follow [Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.</span></span> 
    

