---
title: Adicionar os responsáveis em massa a um caso de descoberta eletrônica avançada
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432434"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a><span data-ttu-id="c3921-102">Adicionar os responsáveis em massa a um caso de descoberta eletrônica avançada (visualização)</span><span class="sxs-lookup"><span data-stu-id="c3921-102">Bulk-add custodians to an Advanced eDiscovery case (preview)</span></span>

<span data-ttu-id="c3921-103">Para casos de descoberta eletrônica avançada que envolvem muitos responsáveis, você pode importar vários responsáveis de uma só vez por um arquivo CSV que contém todas as informações necessárias para adicioná-los a um caso.</span><span class="sxs-lookup"><span data-stu-id="c3921-103">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="c3921-104">Adicionar responsáveis em massa</span><span class="sxs-lookup"><span data-stu-id="c3921-104">Bulk-add custodians</span></span>

1. <span data-ttu-id="c3921-105">Insira o caso e navegue até a guia **fontes** .</span><span class="sxs-lookup"><span data-stu-id="c3921-105">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="c3921-106">Clique em **importar responsáveis**</span><span class="sxs-lookup"><span data-stu-id="c3921-106">Click **Import custodians**</span></span>

3. <span data-ttu-id="c3921-107">Na página do menu suspenso, clique em **baixar um modelo em branco** para baixar um arquivo de modelo CSV.</span><span class="sxs-lookup"><span data-stu-id="c3921-107">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="c3921-108">Adicione as informações do custodial ao arquivo CSV e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="c3921-108">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="c3921-109">Consulte a próxima seção para obter informações sobre as propriedades no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c3921-109">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="c3921-110">Na guia **fontes** , clique em **importar os responsáveis** novamente.</span><span class="sxs-lookup"><span data-stu-id="c3921-110">On the **Sources** tab, click **Import Custodians** again.</span></span> 
6. <span data-ttu-id="c3921-111">Na página de submenu, clique em **procurar** e carregar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c3921-111">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="c3921-112">Após o carregamento do arquivo CSV, um trabalho do BulkAddCustodian é criado e exibido na guia **trabalhos** . O trabalho valida os responsáveis e suas fontes de dados correspondentes e os adiciona à guia **responsáveis** na página de **fontes** do caso.</span><span class="sxs-lookup"><span data-stu-id="c3921-112">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="c3921-113">Arquivo CSV de responsáveis</span><span class="sxs-lookup"><span data-stu-id="c3921-113">Custodian CSV file</span></span>

<span data-ttu-id="c3921-114">Depois de baixar o modelo CSV, você poderá adicionar os responsáveis e sua fonte de dados em cada linha.</span><span class="sxs-lookup"><span data-stu-id="c3921-114">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="c3921-115">Certifique-se de não alterar os nomes de coluna na linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c3921-115">Be sure not to change the column names in the the header row.</span></span>

| <span data-ttu-id="c3921-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c3921-116">Column name</span></span>|<span data-ttu-id="c3921-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="c3921-117">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="c3921-118">**ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="c3921-118">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="c3921-119">Email UPN dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-119">UPN email of custodian.</span></span> <span data-ttu-id="c3921-120">Exemplo: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3921-120">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="c3921-121">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="c3921-121">**Exchange Enabled**</span></span> | <span data-ttu-id="c3921-122">Valor TRUE/FALSE no qual adicionar a caixa de correio do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-122">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="c3921-123">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="c3921-123">**OneDrive Enabled**</span></span> | <span data-ttu-id="c3921-124">Valor verdadeiro/falso no caso de adicionar a conta do OneDrive for Business dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-124">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="c3921-125">**É onHold**</span><span class="sxs-lookup"><span data-stu-id="c3921-125">**Is OnHold**</span></span>        | <span data-ttu-id="c3921-126">Valor verdadeiro/falso se deseja colocar os responsáveis em espera.</span><span class="sxs-lookup"><span data-stu-id="c3921-126">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="c3921-127">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="c3921-127">**Workload1 Type**</span></span>         | <span data-ttu-id="c3921-128">Valor da cadeia de caracteres que indica o tipo de fonte de dados a ser associado ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="c3921-128">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="c3921-129">Os valores possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="c3921-129">Possible values include:</span></span> <br /><span data-ttu-id="c3921-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="c3921-130">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="c3921-131">**Local Workload1**</span><span class="sxs-lookup"><span data-stu-id="c3921-131">**Workload1 Location**</span></span>     | <span data-ttu-id="c3921-132">Dependendo do seu tipo de carga de trabalho, esse seria o local de dados da carga de trabalho (por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint).</span><span class="sxs-lookup"><span data-stu-id="c3921-132">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="c3921-133">Veja um exemplo de um arquivo CSV com informações sobre os responsáveis:</span><span class="sxs-lookup"><span data-stu-id="c3921-133">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="c3921-134">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="c3921-134">ContactEmail</span></span>      | <span data-ttu-id="c3921-135">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="c3921-135">Exchange Enabled</span></span> | <span data-ttu-id="c3921-136">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="c3921-136">OneDrive Enabled</span></span> | <span data-ttu-id="c3921-137">É onHold</span><span class="sxs-lookup"><span data-stu-id="c3921-137">Is OnHold</span></span> | <span data-ttu-id="c3921-138">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="c3921-138">Workload1 Type</span></span> | <span data-ttu-id="c3921-139">Local Workload1</span><span class="sxs-lookup"><span data-stu-id="c3921-139">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="c3921-140">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3921-140">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="c3921-141">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-141">TRUE</span></span>             | <span data-ttu-id="c3921-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-142">TRUE</span></span>             | <span data-ttu-id="c3921-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-143">TRUE</span></span>      | <span data-ttu-id="c3921-144">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="c3921-144">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="c3921-145">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3921-145">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="c3921-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-146">TRUE</span></span>             | <span data-ttu-id="c3921-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-147">TRUE</span></span>             | <span data-ttu-id="c3921-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="c3921-148">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="c3921-149">Validação de responsáveis e fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c3921-149">Custodian and data source validation</span></span>

<span data-ttu-id="c3921-150">Quando você carrega o arquivo CSV do Object, a descoberta eletrônica avançada realiza as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c3921-150">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="c3921-151">Valida os responsáveis e suas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="c3921-151">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="c3921-152">Indexa todas as fontes de dados de cada responsáveis e as coloca em espera (se a propriedade is onHold estiver definida como TRUE).</span><span class="sxs-lookup"><span data-stu-id="c3921-152">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="c3921-153">Validação de responsáveis</span><span class="sxs-lookup"><span data-stu-id="c3921-153">Custodian validation</span></span>

<span data-ttu-id="c3921-154">No momento, só damos suporte à importação de responsáveis que estão no Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="c3921-154">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="c3921-155">Validamos e localizaram os responsáveis usando o valor UPN na coluna **email de contato** no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c3921-155">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="c3921-156">Os responsáveis que são validados são automaticamente adicionados ao caso e listados na guia **responsáveis** na página de **fontes** do caso.</span><span class="sxs-lookup"><span data-stu-id="c3921-156">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="c3921-157">Se não for possível validar os responsáveis, eles serão listados no log de erros para o trabalho do BulkAddCustodian listado na guia **trabalhos** no caso.</span><span class="sxs-lookup"><span data-stu-id="c3921-157">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="c3921-158">Os responsáveis não validados não são adicionados ao caso.</span><span class="sxs-lookup"><span data-stu-id="c3921-158">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="c3921-159">Validação da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c3921-159">Data source validation</span></span>

<span data-ttu-id="c3921-160">Após os responsáveis serem validados e adicionados ao caso, cada fonte de dados associada a um responsáveis será validada.</span><span class="sxs-lookup"><span data-stu-id="c3921-160">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="c3921-161">Se qualquer fonte de dados para um Objectnão puder ser encontrada, o valor **não validado** será exibido na coluna **validada** na guia **responsáveis** por esses responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-161">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="c3921-162">Solucionando fontes de dados não validadas</span><span class="sxs-lookup"><span data-stu-id="c3921-162">Remediating unvalidated data sources</span></span>

<span data-ttu-id="c3921-163">Para corrigir os responsáveis por fontes de dados não validadas:</span><span class="sxs-lookup"><span data-stu-id="c3921-163">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="c3921-164">Na guia **responsáveis** , selecione um funcionário que não é validado.</span><span class="sxs-lookup"><span data-stu-id="c3921-164">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="c3921-165">Na página do submenu de responsáveis, role até a seção **fontes de dados** para exibir as fontes de dados associadas aos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-165">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="c3921-166">As fontes de dados validadas e não validadas são listadas.</span><span class="sxs-lookup"><span data-stu-id="c3921-166">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="c3921-167">Na seção **fontes de dados** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3921-167">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="c3921-168">Na página **escolher locais de custodial** , remova uma fonte de dados não validada.</span><span class="sxs-lookup"><span data-stu-id="c3921-168">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="c3921-169">Na página **selecionar locais adicionais** , clique em **Atualizar** para adicionar outras fontes de dados para um responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c3921-169">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
