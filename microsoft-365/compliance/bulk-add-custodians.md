---
title: Importar os responsáveis para uma ocorrência de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use o dto Tool de importação para adicionar rapidamente vários responsáveis e suas fontes de dados associadas a um caso na descoberta eletrônica avançada.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740298"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="c8c47-103">Importar os responsáveis para uma ocorrência de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="c8c47-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="c8c47-104">Para casos de descoberta eletrônica avançada que envolvem muitos responsáveis, você pode importar vários responsáveis de uma só vez usando um arquivo CSV que contenha as informações necessárias para adicioná-los a um caso.</span><span class="sxs-lookup"><span data-stu-id="c8c47-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="c8c47-105">Importar os responsáveis</span><span class="sxs-lookup"><span data-stu-id="c8c47-105">Import custodians</span></span>

1. <span data-ttu-id="c8c47-106">Abra o caso de descoberta eletrônica avançada e selecione a guia **fontes de dados** .</span><span class="sxs-lookup"><span data-stu-id="c8c47-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="c8c47-107">Clique em **adicionar os**  >  **responsáveis de importação** de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c8c47-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="c8c47-108">Na página **importar** o submenu responsáveis, clique em **baixar um modelo em branco** para baixar um arquivo CSV de modelo de responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Baixar um modelo CSV da página de submenu importar responsáveis](../media/ImportCustodians1.png)

4. <span data-ttu-id="c8c47-110">Adicione as informações do custodial ao arquivo CSV e salve-o em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="c8c47-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="c8c47-111">Consulte a seção [arquivo CSV de responsáveis](#custodian-csv-file) para obter informações sobre as propriedades necessárias no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c8c47-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="c8c47-112">Depois de preparar o arquivo CSV com as informações dos responsáveis, volte para a guia **fontes de dados** e clique em **Adicionar fonte de dados**  >  **importar os responsáveis** novamente.</span><span class="sxs-lookup"><span data-stu-id="c8c47-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="c8c47-113">Na página do submenu **importar responsáveis** , clique em **procurar** e carregue o arquivo CSV que contém as informações dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="c8c47-114">Após o carregamento do arquivo CSV, um trabalho chamado **BulkAddCustodian** é criado e exibido na guia **trabalhos** . O trabalho valida os responsáveis e suas fontes de dados associadas e os adiciona à página de **fontes de dados** do caso.</span><span class="sxs-lookup"><span data-stu-id="c8c47-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="c8c47-115">Arquivo CSV de responsáveis</span><span class="sxs-lookup"><span data-stu-id="c8c47-115">Custodian CSV file</span></span>

<span data-ttu-id="c8c47-116">Depois de baixar o modelo de responsáveis por CSV, você pode adicionar os responsáveis e a fonte de dados em cada linha.</span><span class="sxs-lookup"><span data-stu-id="c8c47-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="c8c47-117">Certifique-se de não alterar os nomes de coluna na linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c8c47-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="c8c47-118">Use as colunas tipo de carga de trabalho e local de carga de trabalho para associar outras fontes de dados a um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8c47-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="c8c47-119">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c8c47-119">Column name</span></span>|<span data-ttu-id="c8c47-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8c47-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="c8c47-121">**ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="c8c47-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="c8c47-122">O endereço de email UPN do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-122">The custodian's UPN email address.</span></span> <span data-ttu-id="c8c47-123">Por exemplo, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="c8c47-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="c8c47-124">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="c8c47-124">**Exchange Enabled**</span></span> | <span data-ttu-id="c8c47-125">Valor verdadeiro/falso para incluir ou não a caixa de correio do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="c8c47-126">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="c8c47-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="c8c47-127">Valor verdadeiro/falso para incluir ou não a conta do OneDrive for Business do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="c8c47-128">**É onHold**</span><span class="sxs-lookup"><span data-stu-id="c8c47-128">**Is OnHold**</span></span>        | <span data-ttu-id="c8c47-129">Valor verdadeiro/falso para indicar se deve colocar as fontes de dados dos responsáveis em espera.</span><span class="sxs-lookup"><span data-stu-id="c8c47-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="c8c47-130">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="c8c47-130">**Workload1 Type**</span></span>         |<span data-ttu-id="c8c47-131">Valor da cadeia de caracteres que indica o tipo de fonte de dados a ser associado ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="c8c47-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="c8c47-132">Os valores possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="c8c47-132">Possible values include:</span></span> <br/><span data-ttu-id="c8c47-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="c8c47-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="c8c47-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="c8c47-134">- SharePointSite</span></span><br/><span data-ttu-id="c8c47-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="c8c47-135">- TeamsMailbox</span></span><br/><span data-ttu-id="c8c47-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="c8c47-136">- TeamsSite</span></span><br/> <span data-ttu-id="c8c47-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="c8c47-137">- YammerMailbox</span></span><br/><span data-ttu-id="c8c47-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="c8c47-138">- YammerSite</span></span> |
|<span data-ttu-id="c8c47-139">**Local Workload1**</span><span class="sxs-lookup"><span data-stu-id="c8c47-139">**Workload1 Location**</span></span>     | <span data-ttu-id="c8c47-140">Dependendo do seu tipo de carga de trabalho, esse seria o local da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c8c47-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="c8c47-141">Por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c8c47-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="c8c47-142">Veja um exemplo de um arquivo CSV com informações sobre os responsáveis:</span><span class="sxs-lookup"><span data-stu-id="c8c47-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="c8c47-143">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="c8c47-143">Custodian contactEmail</span></span>      | <span data-ttu-id="c8c47-144">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="c8c47-144">Exchange Enabled</span></span> | <span data-ttu-id="c8c47-145">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="c8c47-145">OneDrive Enabled</span></span> | <span data-ttu-id="c8c47-146">É onHold</span><span class="sxs-lookup"><span data-stu-id="c8c47-146">Is OnHold</span></span> | <span data-ttu-id="c8c47-147">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="c8c47-147">Workload1 Type</span></span> | <span data-ttu-id="c8c47-148">Local Workload1</span><span class="sxs-lookup"><span data-stu-id="c8c47-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="c8c47-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8c47-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="c8c47-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-150">TRUE</span></span>             | <span data-ttu-id="c8c47-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-151">TRUE</span></span>             | <span data-ttu-id="c8c47-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-152">TRUE</span></span>      | <span data-ttu-id="c8c47-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="c8c47-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="c8c47-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c8c47-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="c8c47-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-155">TRUE</span></span>             | <span data-ttu-id="c8c47-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-156">TRUE</span></span>             | <span data-ttu-id="c8c47-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="c8c47-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="c8c47-158">Validação de responsáveis e fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c8c47-158">Custodian and data source validation</span></span>

<span data-ttu-id="c8c47-159">Depois que você carregar o arquivo CSV de responsáveis, a descoberta eletrônica avançada fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c8c47-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="c8c47-160">Valida os responsáveis e suas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="c8c47-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="c8c47-161">Indexa todas as fontes de dados de cada responsáveis e as coloca em espera (se a propriedade **is onHold** no arquivo CSV estiver definida como true).</span><span class="sxs-lookup"><span data-stu-id="c8c47-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="c8c47-162">Validação de responsáveis</span><span class="sxs-lookup"><span data-stu-id="c8c47-162">Custodian validation</span></span>

<span data-ttu-id="c8c47-163">No momento, só há suporte para importar os responsáveis que estão incluídos no Azure Active Directory (Azure AD) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8c47-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c8c47-164">A ferramenta de importação de responsáveis localiza e valida os responsáveis usando o valor UPN na coluna **contactEmail** do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c8c47-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="c8c47-165">Os responsáveis que são validados são automaticamente adicionados ao caso e listados na guia **fontes de dados** do caso.</span><span class="sxs-lookup"><span data-stu-id="c8c47-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="c8c47-166">Se não for possível validar os responsáveis, eles serão listados no log de erros para o trabalho do BulkAddCustodian listado na guia **trabalhos** no caso.</span><span class="sxs-lookup"><span data-stu-id="c8c47-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="c8c47-167">Os responsáveis não validados não são adicionados ao caso ou listados na guia **fontes de dados** .</span><span class="sxs-lookup"><span data-stu-id="c8c47-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="c8c47-168">Validação da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c8c47-168">Data source validation</span></span>

<span data-ttu-id="c8c47-169">Após os responsáveis serem validados e adicionados ao caso, cada caixa de correio principal e conta do OneDrive associada a um objectserá adicionado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="c8c47-170">No entanto, se qualquer uma das outras fontes de dados (como sites do SharePoint, Microsoft Teams, Microsoft 365 groups ou Yammer groups) associada a um solicitante não puder ser encontrada, nenhuma delas será atribuída aos responsáveis e o valor **não validado** será exibido na coluna **status** ao lado dos responsáveis na guia **fontes de dados** .</span><span class="sxs-lookup"><span data-stu-id="c8c47-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="c8c47-171">Para adicionar fontes de dados validadas para um responsáveis:</span><span class="sxs-lookup"><span data-stu-id="c8c47-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="c8c47-172">Na guia **fontes de dados** , selecione um responsáveis que contenha fontes de dados que não são validadas.</span><span class="sxs-lookup"><span data-stu-id="c8c47-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="c8c47-173">Na página do submenu de responsáveis, role até a seção **locais do custodial** para ver as fontes de dados validadas e não validadas que estão associadas aos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="c8c47-174">Clique em **Editar** na parte superior da página de menu suspenso para remover fontes de dados inválidas ou adicionar novas.</span><span class="sxs-lookup"><span data-stu-id="c8c47-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="c8c47-175">Após a remoção de fontes de dados não validadas ou a adição de uma nova, o valor **ativo** será exibido na coluna **status** para os responsáveis na guia **fontes de dados** . Para adicionar fontes que anteriormente apareciam como inválidas, siga as etapas de correção abaixo para adicioná-las manualmente a um solicitante.</span><span class="sxs-lookup"><span data-stu-id="c8c47-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="c8c47-176">Correção de fontes de dados inválidas</span><span class="sxs-lookup"><span data-stu-id="c8c47-176">Remediating invalid data sources</span></span>

<span data-ttu-id="c8c47-177">Para adicionar e associar manualmente uma fonte de dados que era previamente inválida:</span><span class="sxs-lookup"><span data-stu-id="c8c47-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="c8c47-178">Na guia **fontes de dados** , selecione um funcionário para adicionar e associar manualmente uma fonte de dados que antes era inválida.</span><span class="sxs-lookup"><span data-stu-id="c8c47-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="c8c47-179">Clique em **Editar** na parte superior da página de menu para associar caixas de correio, sites, equipes ou grupos do Yammer aos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c8c47-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="c8c47-180">Para isso, clique em **Editar** ao lado do tipo de local de dados apropriado.</span><span class="sxs-lookup"><span data-stu-id="c8c47-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="c8c47-181">Clique em **Avançar** para exibir a página **configurações de retenção** e definir a configuração de retenção para as fontes de dados que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="c8c47-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="c8c47-182">Clique em **Avançar** para exibir a página **revisar responsáveis** e, em seguida, clique em **Enviar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c8c47-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
