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
description: Use a ferramenta de adição em massa para adicionar rapidamente vários responsáveis e suas fontes de dados associadas a um caso na descoberta eletrônica avançada.
ms.openlocfilehash: ab9626be01814fa95a959141433b431df9bf7724
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024661"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="103ed-103">Adicionar os responsáveis em massa a um caso de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="103ed-103">Bulk-add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="103ed-104">Para casos de descoberta eletrônica avançada que envolvem muitos responsáveis, você pode importar vários responsáveis de uma só vez por um arquivo CSV que contém todas as informações necessárias para adicioná-los a um caso.</span><span class="sxs-lookup"><span data-stu-id="103ed-104">For Advanced eDiscovery cases that involve a lot of custodians, you can import multiple custodians at once by a CSV file that contains all the information necessary to add them to a case.</span></span>

## <a name="bulk-add-custodians"></a><span data-ttu-id="103ed-105">Adicionar responsáveis em massa</span><span class="sxs-lookup"><span data-stu-id="103ed-105">Bulk-add custodians</span></span>

1. <span data-ttu-id="103ed-106">Insira o caso e navegue até a guia **fontes** .</span><span class="sxs-lookup"><span data-stu-id="103ed-106">Enter case and navigate to the **Sources** tab.</span></span>

2. <span data-ttu-id="103ed-107">Clique em **importar responsáveis**</span><span class="sxs-lookup"><span data-stu-id="103ed-107">Click **Import custodians**</span></span>

3. <span data-ttu-id="103ed-108">Na página do menu suspenso, clique em **baixar um modelo em branco** para baixar um arquivo de modelo CSV.</span><span class="sxs-lookup"><span data-stu-id="103ed-108">On the flyout page, click **Download a blank template** to download a CSV custodian template file.</span></span>

4. <span data-ttu-id="103ed-109">Adicione as informações do custodial ao arquivo CSV e salve-o no computador local.</span><span class="sxs-lookup"><span data-stu-id="103ed-109">Add the custodial information to the CSV file and save it on your local computer.</span></span> <span data-ttu-id="103ed-110">Consulte a próxima seção para obter informações sobre as propriedades no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="103ed-110">See the next section for information about the properties in the CSV file.</span></span>

5. <span data-ttu-id="103ed-111">Na guia **fontes** , clique em **importar os responsáveis** novamente.</span><span class="sxs-lookup"><span data-stu-id="103ed-111">On the **Sources** tab, click **Import Custodians** again.</span></span>

6. <span data-ttu-id="103ed-112">Na página de submenu, clique em **procurar** e carregar o arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="103ed-112">On flyout page, click **Browse** and the upload your CSV file.</span></span>

   <span data-ttu-id="103ed-113">Após o carregamento do arquivo CSV, um trabalho do BulkAddCustodian é criado e exibido na guia **trabalhos** . O trabalho valida os responsáveis e suas fontes de dados correspondentes e os adiciona à guia **responsáveis** na página de **fontes** do caso.</span><span class="sxs-lookup"><span data-stu-id="103ed-113">After the CSV file is uploaded, a BulkAddCustodian job is created and displayed on the **Jobs** tab. The job validates the custodians and their corresponding data sources and then adds them to the **Custodians** tab on the **Sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="103ed-114">Arquivo CSV de responsáveis</span><span class="sxs-lookup"><span data-stu-id="103ed-114">Custodian CSV file</span></span>

<span data-ttu-id="103ed-115">Depois de baixar o modelo CSV, você poderá adicionar os responsáveis e sua fonte de dados em cada linha.</span><span class="sxs-lookup"><span data-stu-id="103ed-115">After you download the CSV template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="103ed-116">Certifique-se de não alterar os nomes de coluna na linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="103ed-116">Be sure not to change the column names in the header row.</span></span>

| <span data-ttu-id="103ed-117">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="103ed-117">Column name</span></span>|<span data-ttu-id="103ed-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="103ed-118">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="103ed-119">**ContactEmail**</span><span class="sxs-lookup"><span data-stu-id="103ed-119">**Custodian ContactEmail**</span></span>     | <span data-ttu-id="103ed-120">Email UPN dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-120">UPN email of custodian.</span></span> <span data-ttu-id="103ed-121">Exemplo: sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="103ed-121">Example: sarad@onmicrosoft.contoso.com</span></span>           |
|<span data-ttu-id="103ed-122">**Exchange habilitado**</span><span class="sxs-lookup"><span data-stu-id="103ed-122">**Exchange Enabled**</span></span> | <span data-ttu-id="103ed-123">Valor TRUE/FALSE no qual adicionar a caixa de correio do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-123">TRUE/FALSE value on whether to add custodian's mailbox.</span></span>      |
|<span data-ttu-id="103ed-124">**OneDrive habilitado**</span><span class="sxs-lookup"><span data-stu-id="103ed-124">**OneDrive Enabled**</span></span> | <span data-ttu-id="103ed-125">Valor verdadeiro/falso no caso de adicionar a conta do OneDrive for Business dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-125">TRUE/FALSE value on whether to add custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="103ed-126">**É onHold**</span><span class="sxs-lookup"><span data-stu-id="103ed-126">**Is OnHold**</span></span>        | <span data-ttu-id="103ed-127">Valor verdadeiro/falso se deseja colocar os responsáveis em espera.</span><span class="sxs-lookup"><span data-stu-id="103ed-127">TRUE/FALSE value on whether to place custodian on hold.</span></span>       |
|<span data-ttu-id="103ed-128">**Tipo Workload1**</span><span class="sxs-lookup"><span data-stu-id="103ed-128">**Workload1 Type**</span></span>         | <span data-ttu-id="103ed-129">Valor da cadeia de caracteres que indica o tipo de fonte de dados a ser associado ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="103ed-129">String value indicating the type of data source to associate with the custodian.</span></span> <br /><span data-ttu-id="103ed-130">Os valores possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="103ed-130">Possible values include:</span></span> <br /><span data-ttu-id="103ed-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span><span class="sxs-lookup"><span data-stu-id="103ed-131">ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite</span></span> |
|<span data-ttu-id="103ed-132">**Local Workload1**</span><span class="sxs-lookup"><span data-stu-id="103ed-132">**Workload1 Location**</span></span>     | <span data-ttu-id="103ed-133">Dependendo do seu tipo de carga de trabalho, esse seria o local de dados da carga de trabalho (por exemplo, o endereço de email de uma caixa de correio do Exchange ou a URL de um site do SharePoint).</span><span class="sxs-lookup"><span data-stu-id="103ed-133">Depending on your workload type, this would be the data location of your workload (for example, the email address of an Exchange mailbox or the URL for a SharePoint site).</span></span> |
|||

<span data-ttu-id="103ed-134">Veja um exemplo de um arquivo CSV com informações sobre os responsáveis:</span><span class="sxs-lookup"><span data-stu-id="103ed-134">Here's an example of a CSV file with custodian information:</span></span>  

| <span data-ttu-id="103ed-135">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="103ed-135">ContactEmail</span></span>      | <span data-ttu-id="103ed-136">Exchange habilitado</span><span class="sxs-lookup"><span data-stu-id="103ed-136">Exchange Enabled</span></span> | <span data-ttu-id="103ed-137">OneDrive habilitado</span><span class="sxs-lookup"><span data-stu-id="103ed-137">OneDrive Enabled</span></span> | <span data-ttu-id="103ed-138">É onHold</span><span class="sxs-lookup"><span data-stu-id="103ed-138">Is OnHold</span></span> | <span data-ttu-id="103ed-139">Tipo Workload1</span><span class="sxs-lookup"><span data-stu-id="103ed-139">Workload1 Type</span></span> | <span data-ttu-id="103ed-140">Local Workload1</span><span class="sxs-lookup"><span data-stu-id="103ed-140">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="103ed-141">sarad@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="103ed-141">sarad@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="103ed-142">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-142">TRUE</span></span>             | <span data-ttu-id="103ed-143">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-143">TRUE</span></span>             | <span data-ttu-id="103ed-144">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-144">TRUE</span></span>      | <span data-ttu-id="103ed-145">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="103ed-145">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="103ed-146">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="103ed-146">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="103ed-147">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-147">TRUE</span></span>             | <span data-ttu-id="103ed-148">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-148">TRUE</span></span>             | <span data-ttu-id="103ed-149">TRUE</span><span class="sxs-lookup"><span data-stu-id="103ed-149">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="103ed-150">Validação de responsáveis e fonte de dados</span><span class="sxs-lookup"><span data-stu-id="103ed-150">Custodian and data source validation</span></span>

<span data-ttu-id="103ed-151">Quando você carrega o arquivo CSV do Object, a descoberta eletrônica avançada realiza as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="103ed-151">When you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="103ed-152">Valida os responsáveis e suas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="103ed-152">Validates the custodians and their data sources.</span></span> 

2. <span data-ttu-id="103ed-153">Indexa todas as fontes de dados de cada responsáveis e as coloca em espera (se a propriedade is onHold estiver definida como TRUE).</span><span class="sxs-lookup"><span data-stu-id="103ed-153">Indexes all data sources for each custodian and places them on hold (if the Is OnHold property is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="103ed-154">Validação de responsáveis</span><span class="sxs-lookup"><span data-stu-id="103ed-154">Custodian validation</span></span>

<span data-ttu-id="103ed-155">No momento, só damos suporte à importação de responsáveis que estão no Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="103ed-155">Currently, we only support importing custodians that are in Azure Active Directory (AAD).</span></span>

<span data-ttu-id="103ed-156">Validamos e localizaram os responsáveis usando o valor UPN na coluna **email de contato** no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="103ed-156">We validate and find custodians using the UPN value in the **Contact Email** column in the CSV file.</span></span> <span data-ttu-id="103ed-157">Os responsáveis que são validados são automaticamente adicionados ao caso e listados na guia **responsáveis** na página de **fontes** do caso.</span><span class="sxs-lookup"><span data-stu-id="103ed-157">Custodians that are validated are automatically added to the case and listed on the **Custodian** tab on the **Sources** page of the case.</span></span> <span data-ttu-id="103ed-158">Se não for possível validar os responsáveis, eles serão listados no log de erros para o trabalho do BulkAddCustodian listado na guia **trabalhos** no caso.</span><span class="sxs-lookup"><span data-stu-id="103ed-158">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="103ed-159">Os responsáveis não validados não são adicionados ao caso.</span><span class="sxs-lookup"><span data-stu-id="103ed-159">Unvalidated custodians are not added to the case.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="103ed-160">Validação da fonte de dados</span><span class="sxs-lookup"><span data-stu-id="103ed-160">Data source validation</span></span>

<span data-ttu-id="103ed-161">Após os responsáveis serem validados e adicionados ao caso, cada fonte de dados associada a um responsáveis será validada.</span><span class="sxs-lookup"><span data-stu-id="103ed-161">After custodians are validated and added to the case, each data source that's associated with a custodian is validated.</span></span> <span data-ttu-id="103ed-162">Se qualquer fonte de dados para um Objectnão puder ser encontrada, o valor **não validado** será exibido na coluna **validada** na guia **responsáveis** por esses responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-162">If any data source for a custodian can't be found, the value **Not validated** would be displayed in the **Validated** column on the **Custodian** tab for that custodian.</span></span>

### <a name="remediating-unvalidated-data-sources"></a><span data-ttu-id="103ed-163">Solucionando fontes de dados não validadas</span><span class="sxs-lookup"><span data-stu-id="103ed-163">Remediating unvalidated data sources</span></span>

<span data-ttu-id="103ed-164">Para corrigir os responsáveis por fontes de dados não validadas:</span><span class="sxs-lookup"><span data-stu-id="103ed-164">To remediate custodians with unvalidated data sources:</span></span> 

1. <span data-ttu-id="103ed-165">Na guia **responsáveis** , selecione um funcionário que não é validado.</span><span class="sxs-lookup"><span data-stu-id="103ed-165">On the **Custodian** tab, select a custodian who isn't validated.</span></span>

2. <span data-ttu-id="103ed-166">Na página do submenu de responsáveis, role até a seção **fontes de dados** para exibir as fontes de dados associadas aos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-166">On the custodian flyout page, scroll to the **Data sources** section to view the data sources that are associated with custodian.</span></span> <span data-ttu-id="103ed-167">As fontes de dados validadas e não validadas são listadas.</span><span class="sxs-lookup"><span data-stu-id="103ed-167">Both validated and unvalidated data sources are listed.</span></span>

3. <span data-ttu-id="103ed-168">Na seção **fontes de dados** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="103ed-168">In the **Data sources** section, click **Edit**.</span></span>

4. <span data-ttu-id="103ed-169">Na página **escolher locais de custodial** , remova uma fonte de dados não validada.</span><span class="sxs-lookup"><span data-stu-id="103ed-169">On the **Choose custodial locations** page, remove an unvalidated data source.</span></span>

5. <span data-ttu-id="103ed-170">Na página **selecionar locais adicionais** , clique em **Atualizar** para adicionar outras fontes de dados para um responsáveis.</span><span class="sxs-lookup"><span data-stu-id="103ed-170">On the **Select additional locations** page, click **Update** to add additional data sources for a custodian.</span></span>
