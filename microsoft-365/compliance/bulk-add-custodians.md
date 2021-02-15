---
title: Importar custodiantes para uma ocorrência de Descoberta Avançada
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
description: Use a ferramenta de importação para adicionar rapidamente vários custodiantes e suas fontes de dados associadas a um caso na Descoberta Avançada.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740298"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="0fadd-103">Importar custodiantes para uma ocorrência de Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="0fadd-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="0fadd-104">Para casos de Descoberta Avançada que envolvem muitos custodiantes, você pode importar vários custodiantes de uma só vez usando um arquivo CSV que contém as informações necessárias para adicioná-los a uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0fadd-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="0fadd-105">Importar custodiantes</span><span class="sxs-lookup"><span data-stu-id="0fadd-105">Import custodians</span></span>

1. <span data-ttu-id="0fadd-106">Abra a ocorrência de Descoberta Avançada e selecione a **guia Fontes de** dados.</span><span class="sxs-lookup"><span data-stu-id="0fadd-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="0fadd-107">Clique **em Adicionar custodiantes de**  >  **importação de fonte de dados.**</span><span class="sxs-lookup"><span data-stu-id="0fadd-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="0fadd-108">Na página **importar custodiantes,** clique em **Baixar** um modelo em branco para baixar um arquivo CSV de modelo custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Baixar um modelo CSV da página importar custodiantes](../media/ImportCustodians1.png)

4. <span data-ttu-id="0fadd-110">Adicione as informações de custodiante ao arquivo CSV e salve-as no computador local.</span><span class="sxs-lookup"><span data-stu-id="0fadd-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="0fadd-111">Consulte a [seção arquivo CSV Custodian](#custodian-csv-file) para obter informações sobre as propriedades necessárias no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0fadd-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="0fadd-112">Depois de preparar o arquivo CSV com as informações  de custodiante, volte para a guia Fontes de dados e clique em Adicionar custodiantes de importação de fonte  >  **de** dados novamente.</span><span class="sxs-lookup"><span data-stu-id="0fadd-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="0fadd-113">Na página **importar custodiantes,** clique em **Procurar** e carregue o arquivo CSV que contém as informações custodiantes.</span><span class="sxs-lookup"><span data-stu-id="0fadd-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="0fadd-114">Depois que o arquivo CSV é carregado, um trabalho chamado **BulkAddCustodian** é criado e exibido na **guia** Trabalhos. O trabalho valida os custodiantes e suas fontes de  dados associadas e os adiciona à página Fontes de dados do caso.</span><span class="sxs-lookup"><span data-stu-id="0fadd-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="0fadd-115">Arquivo CSV custodiado</span><span class="sxs-lookup"><span data-stu-id="0fadd-115">Custodian CSV file</span></span>

<span data-ttu-id="0fadd-116">Depois de baixar o modelo custodiante CSV, você pode adicionar custodiantes e sua fonte de dados em cada linha.</span><span class="sxs-lookup"><span data-stu-id="0fadd-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="0fadd-117">Certifique-se de não alterar os nomes das colunas na linha de header.</span><span class="sxs-lookup"><span data-stu-id="0fadd-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="0fadd-118">Use o tipo de carga de trabalho e as colunas de local de carga de trabalho para associar outras fontes de dados a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="0fadd-119">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="0fadd-119">Column name</span></span>|<span data-ttu-id="0fadd-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="0fadd-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="0fadd-121">**Custodian contactEmail**</span><span class="sxs-lookup"><span data-stu-id="0fadd-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="0fadd-122">O endereço de email UPN do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="0fadd-122">The custodian's UPN email address.</span></span> <span data-ttu-id="0fadd-123">Por exemplo, sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0fadd-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="0fadd-124">**Exchange Habilitado**</span><span class="sxs-lookup"><span data-stu-id="0fadd-124">**Exchange Enabled**</span></span> | <span data-ttu-id="0fadd-125">Valor VERDADEIRO/FALSO para incluir ou não incluir a caixa de correio do custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="0fadd-126">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="0fadd-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="0fadd-127">Valor VERDADEIRO/FALSO para incluir ou não incluir a conta do OneDrive for Business do custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="0fadd-128">**Está OnHold**</span><span class="sxs-lookup"><span data-stu-id="0fadd-128">**Is OnHold**</span></span>        | <span data-ttu-id="0fadd-129">Valor VERDADEIRO/FALSO para indicar se as fontes de dados custodiante serão colocadas em espera.</span><span class="sxs-lookup"><span data-stu-id="0fadd-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span>       |
|<span data-ttu-id="0fadd-130">**Tipo workload1**</span><span class="sxs-lookup"><span data-stu-id="0fadd-130">**Workload1 Type**</span></span>         |<span data-ttu-id="0fadd-131">Valor da cadeia de caracteres indicando o tipo de fonte de dados a ser associada ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-131">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="0fadd-132">Os valores possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="0fadd-132">Possible values include:</span></span> <br/><span data-ttu-id="0fadd-133">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="0fadd-133">- ExchangeMailbox</span></span><br/> <span data-ttu-id="0fadd-134">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="0fadd-134">- SharePointSite</span></span><br/><span data-ttu-id="0fadd-135">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="0fadd-135">- TeamsMailbox</span></span><br/><span data-ttu-id="0fadd-136">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="0fadd-136">- TeamsSite</span></span><br/> <span data-ttu-id="0fadd-137">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="0fadd-137">- YammerMailbox</span></span><br/><span data-ttu-id="0fadd-138">- YammerSite</span><span class="sxs-lookup"><span data-stu-id="0fadd-138">- YammerSite</span></span> |
|<span data-ttu-id="0fadd-139">**Local workload1**</span><span class="sxs-lookup"><span data-stu-id="0fadd-139">**Workload1 Location**</span></span>     | <span data-ttu-id="0fadd-140">Dependendo do tipo de carga de trabalho, esse seria o local da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0fadd-140">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="0fadd-141">Por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0fadd-141">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

<span data-ttu-id="0fadd-142">Veja um exemplo de um arquivo CSV com informações de custodiação:</span><span class="sxs-lookup"><span data-stu-id="0fadd-142">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="0fadd-143">Custodian contactEmail</span><span class="sxs-lookup"><span data-stu-id="0fadd-143">Custodian contactEmail</span></span>      | <span data-ttu-id="0fadd-144">Exchange Habilitado</span><span class="sxs-lookup"><span data-stu-id="0fadd-144">Exchange Enabled</span></span> | <span data-ttu-id="0fadd-145">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="0fadd-145">OneDrive Enabled</span></span> | <span data-ttu-id="0fadd-146">Está OnHold</span><span class="sxs-lookup"><span data-stu-id="0fadd-146">Is OnHold</span></span> | <span data-ttu-id="0fadd-147">Tipo workload1</span><span class="sxs-lookup"><span data-stu-id="0fadd-147">Workload1 Type</span></span> | <span data-ttu-id="0fadd-148">Local workload1</span><span class="sxs-lookup"><span data-stu-id="0fadd-148">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="0fadd-149">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fadd-149">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="0fadd-150">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-150">TRUE</span></span>             | <span data-ttu-id="0fadd-151">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-151">TRUE</span></span>             | <span data-ttu-id="0fadd-152">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-152">TRUE</span></span>      | <span data-ttu-id="0fadd-153">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="0fadd-153">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="0fadd-154">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0fadd-154">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="0fadd-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-155">TRUE</span></span>             | <span data-ttu-id="0fadd-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-156">TRUE</span></span>             | <span data-ttu-id="0fadd-157">TRUE</span><span class="sxs-lookup"><span data-stu-id="0fadd-157">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="0fadd-158">Validação de custodiante e fonte de dados</span><span class="sxs-lookup"><span data-stu-id="0fadd-158">Custodian and data source validation</span></span>

<span data-ttu-id="0fadd-159">Depois de carregar o arquivo CSV custodiante, a Descoberta Avançada faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0fadd-159">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="0fadd-160">Valida os custodiantes e suas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="0fadd-160">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="0fadd-161">Indexa todas as fontes de dados para cada custodiante e coloca-as em espera (se a propriedade **Is OnHold** no arquivo CSV estiver definida como VERDADEIRO).</span><span class="sxs-lookup"><span data-stu-id="0fadd-161">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="0fadd-162">Validação custodian</span><span class="sxs-lookup"><span data-stu-id="0fadd-162">Custodian validation</span></span>

<span data-ttu-id="0fadd-163">Atualmente, só damos suporte à importação de custodiantes incluídos no Azure Active Directory (Azure AD) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0fadd-163">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="0fadd-164">A ferramenta de importação custodiada localiza e valida custodiantes usando o valor UPN na coluna **Custodian contactEmail** no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="0fadd-164">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="0fadd-165">Custodiantes validados são adicionados automaticamente à ocorrência e listados na guia **Fontes de** dados do caso.</span><span class="sxs-lookup"><span data-stu-id="0fadd-165">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="0fadd-166">Se um custodiante não puder ser validado, eles serão listados no log de erros  do trabalho BulkAddCustodian listado na guia Trabalhos no caso.</span><span class="sxs-lookup"><span data-stu-id="0fadd-166">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="0fadd-167">Os custodiantes nãovalidados não são adicionados à ocorrência ou listados na **guia Fontes de** dados.</span><span class="sxs-lookup"><span data-stu-id="0fadd-167">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="0fadd-168">Validação da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="0fadd-168">Data source validation</span></span>

<span data-ttu-id="0fadd-169">Depois que os responsáveis são validados e adicionados à ocorrência, cada caixa de correio principal e a conta do OneDrive associada a um custodiante são adicionadas.</span><span class="sxs-lookup"><span data-stu-id="0fadd-169">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="0fadd-170">No entanto, se qualquer uma das outras fontes de dados (como sites do SharePoint, Microsoft Teams, Grupos do Microsoft 365 ou grupos do Yammer) associadas a um custodiante não puder  ser encontrada, nenhuma delas será atribuída ao custodiante e o valor Não validado será exibido na coluna **Status** ao lado do custodiante na guia Fontes de dados. </span><span class="sxs-lookup"><span data-stu-id="0fadd-170">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="0fadd-171">Para adicionar fontes de dados validadas para um custodiante:</span><span class="sxs-lookup"><span data-stu-id="0fadd-171">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="0fadd-172">Na guia **Fontes de dados,** selecione um custodiante que contenha fontes de dados não validadas.</span><span class="sxs-lookup"><span data-stu-id="0fadd-172">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="0fadd-173">Na página do flyout custodiante, role até a seção Locais custodiais para exibir fontes de dados validadas e nãovalidadas associadas ao custodiante. </span><span class="sxs-lookup"><span data-stu-id="0fadd-173">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="0fadd-174">Clique **em Editar** na parte superior da página do flyout para remover fontes de dados inválidas ou adicionar novas.</span><span class="sxs-lookup"><span data-stu-id="0fadd-174">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="0fadd-175">Depois de remover fontes de dados nãovalidadas ou adicionar uma nova, o valor **Ativo** será exibido na coluna **Status** do custodiante na guia Fontes **de** dados. Para adicionar fontes que anteriormente aparentam ser inválidas, siga as etapas de correção abaixo para adicioná-las manualmente a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-175">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="0fadd-176">Correção de fontes de dados inválidas</span><span class="sxs-lookup"><span data-stu-id="0fadd-176">Remediating invalid data sources</span></span>

<span data-ttu-id="0fadd-177">Para adicionar e associar manualmente uma fonte de dados que anteriormente era inválida:</span><span class="sxs-lookup"><span data-stu-id="0fadd-177">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="0fadd-178">Na guia **Fontes de dados,** selecione um custodiante para adicionar e associar manualmente uma fonte de dados anteriormente inválida.</span><span class="sxs-lookup"><span data-stu-id="0fadd-178">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="0fadd-179">Clique **em Editar** na parte superior da página do flyout para associar caixas de correio, sites, equipes ou grupos do Yammer ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="0fadd-179">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="0fadd-180">Faça isso clicando em **Editar** ao lado do tipo de local de dados apropriado.</span><span class="sxs-lookup"><span data-stu-id="0fadd-180">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="0fadd-181">Clique **em Próximo** para exibir a página de **configurações de** Espera e definir a configuração de espera para as fontes de dados que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="0fadd-181">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="0fadd-182">Clique **em Próximo** para exibir a página Revisar **custodiantes** e clique **em Enviar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="0fadd-182">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
