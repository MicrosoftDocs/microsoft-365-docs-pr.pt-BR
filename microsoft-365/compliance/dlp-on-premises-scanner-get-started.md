---
title: Obter o scanner local de prevenção contra perda de dados do Microsoft 365 (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configurar o scanner local de prevenção contra perda de dados do Microsoft 365
ms.openlocfilehash: deae5dfa803b002174583ae67412af9fc028fcb9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538094"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="dbdc1-103">Obter o scanner local de prevenção contra perda de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="dbdc1-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="dbdc1-104">Este artigo apresenta os pré-requisitos e a configuração do scanner local de prevenção de perda de dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dbdc1-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dbdc1-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="dbdc1-106">Licenciamento SKU/assinaturas</span><span class="sxs-lookup"><span data-stu-id="dbdc1-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="dbdc1-107">Antes de obter o scanner DLP local, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="dbdc1-108">Para participar da visualização, a conta de administrador que configura as regras de DLP deve atribuir uma das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="dbdc1-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbdc1-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="dbdc1-110">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dbdc1-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="dbdc1-111">Microsoft 365 E5 Proteção da Informação & Governança</span><span class="sxs-lookup"><span data-stu-id="dbdc1-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="dbdc1-112">Para obter os detalhes completos do licenciamento, consulte: [Orientação de licenciamento do Microsoft 365 para segurança & conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="dbdc1-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="dbdc1-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="dbdc1-113">Permissions</span></span>


<span data-ttu-id="dbdc1-114">Os dados do scanner DLP local podem ser visualizados no [Explorador de atividades](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="dbdc1-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="dbdc1-115">Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="dbdc1-116">Administrador global</span><span class="sxs-lookup"><span data-stu-id="dbdc1-116">Global administrator</span></span>
- <span data-ttu-id="dbdc1-117">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="dbdc1-117">Compliance administrator</span></span>
- <span data-ttu-id="dbdc1-118">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="dbdc1-118">Security administrator</span></span>
- <span data-ttu-id="dbdc1-119">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="dbdc1-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="dbdc1-120">Pré-requisitos do scanner DLP local</span><span class="sxs-lookup"><span data-stu-id="dbdc1-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="dbdc1-p103">O scanner de Proteção de Informações do Azure (AIP) implementa a correspondência de políticas DLP e a aplicação de políticas. O scanner é instalado como parte do cliente AIP, portanto sua instalação deve atender a todos os pré-requisitos para AIP, o cliente AIP e o scanner de rotulagem unificado AIP.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="dbdc1-123">Implantar o cliente e scanner AIP.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="dbdc1-124">Para mais informações [Instalar o cliente de rotulagem unificada AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) e [], consulte [Configurando e instalando o scanner de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install).</span><span class="sxs-lookup"><span data-stu-id="dbdc1-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="dbdc1-125">Deve haver pelo menos um rótulo e uma política publicados no locatário, mesmo se todas as suas regras de detecção forem baseadas apenas em tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="dbdc1-126">Implantar o scanner DLP local</span><span class="sxs-lookup"><span data-stu-id="dbdc1-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="dbdc1-127">Seguir os procedimentos em [Instalar o cliente de rotulagem unificada AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span><span class="sxs-lookup"><span data-stu-id="dbdc1-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="dbdc1-128">Segui os procedimentos em [Configurando e instalando o scanner de rotulagem unificada do Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install) para concluir a instalação do scanner.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="dbdc1-129">Configuração dos trabalhos de descoberta de rede é uma etapa opcional.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="dbdc1-130">Você pode ignorá-lo e definir repositórios específicos a serem verificados em seu trabalho de exame de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="dbdc1-131">Você deve criar um trabalho de exame de conteúdo e especificar os repositórios que hospedam arquivos que precisam ser avaliados pelo mecanismo DLP.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="dbdc1-132">Habilitar as regras de DLP no trabalho de exame de conteúdo criado e defina a opção **Aplicar** como **Desligado**, a menos que você queira prosseguir diretamente para o estágio de aplicação de DLP.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="dbdc1-p106">Verificar se o trabalho de exame de conteúdo foi atribuído ao cluster correto. Se você ainda não criou um trabalho de exame de conteúdo, crie um novo e atribua-o ao cluster que contém os nós de scanner que executam a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="dbdc1-135">Conecte-se à extensão [Proteção de Informações do Azure no portal do Azure](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) e adicione seus repositórios ao trabalho de exame de conteúdo que executará a verificação.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="dbdc1-136">Siga um destes procedimentos para executar seu exame:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="dbdc1-137">conjunto o programação do scanner</span><span class="sxs-lookup"><span data-stu-id="dbdc1-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="dbdc1-138">use a opção manual **Digitalizar Agora** no portal</span><span class="sxs-lookup"><span data-stu-id="dbdc1-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="dbdc1-139">ou execute **Iniciar-AIPScan** Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="dbdc1-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="dbdc1-140">Lembre-se de que o scanner executa uma varredura delta do repositório por padrão e os arquivos que já foram varridos no ciclo de exame anterior serão ignorados, a menos que o arquivo seja alterado ou você inicie uma nova varredura completa.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="dbdc1-141">A nova verificação completa pode ser iniciada usando a opção **Verificar novamente todos os arquivos** na IU ou executando **Iniciar-AIPScan-Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="dbdc1-142">Abra a [Página de prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies) no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="dbdc1-143">Escolher **Criar política** e criar uma política DLP de teste.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="dbdc1-144">Consulte [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md) se precisar de ajuda para criar uma política.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="dbdc1-145">Certifique-se de executá-lo em teste até que você se sinta confortável com este recurso.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="dbdc1-146">Usar estes parâmetros para sua política:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="dbdc1-147">Defina o escopo da regra de varredura local do DLP para locais específicos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="dbdc1-148">Se você definir o escopo **loalização** para **Todos**, todos os arquivos verificados pelo scanner estarão sujeitos à correspondência e aplicação da regra DLP.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="dbdc1-149">Ao especificar os locais, você pode usar a lista de exclusão ou inclusão.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="dbdc1-150">Durante a visualização pública, você não pode definir os dois conjuntos.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="dbdc1-151">Você pode definir que a regra é relevante apenas para caminhos que correspondem a um dos padrões listados na lista de inclusão ou, todos os arquivos, exceto os arquivos que correspondem ao padrão listado na lista de inclusão.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="dbdc1-152">Nenhum caminho local é suportado.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-152">No local paths are supported.</span></span> <span data-ttu-id="dbdc1-153">Aqui estão alguns exemplos de caminhos válidos:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="dbdc1-154">\\\\servidor\compartilhamento</span><span class="sxs-lookup"><span data-stu-id="dbdc1-154">\\\server\share</span></span>
      - <span data-ttu-id="dbdc1-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="dbdc1-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="dbdc1-156">\*\\pasta1</span><span class="sxs-lookup"><span data-stu-id="dbdc1-156">\*\\folder1</span></span>
      - <span data-ttu-id="dbdc1-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="dbdc1-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="dbdc1-158">\*Secreta\*.\*</span><span class="sxs-lookup"><span data-stu-id="dbdc1-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="dbdc1-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="dbdc1-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="dbdc1-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="dbdc1-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="dbdc1-161">Aqui estão alguns exemplos de uso de valores inaceitáveis:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="dbdc1-162">\*\\a.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-162">\*\\a</span></span>
      - <span data-ttu-id="dbdc1-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="dbdc1-163">Aaa</span></span>
      - <span data-ttu-id="dbdc1-164">c:</span><span class="sxs-lookup"><span data-stu-id="dbdc1-164">c:</span></span>\
      - <span data-ttu-id="dbdc1-165">C:\teste</span><span class="sxs-lookup"><span data-stu-id="dbdc1-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbdc1-166">A lista de exclusão tem precedência sobre a lista de inclusões.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="dbdc1-167">Visualização de alertas de scanner locais de DLP no painel de gerenciamento de Alertas de DLP</span><span class="sxs-lookup"><span data-stu-id="dbdc1-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="dbdc1-168">Abra a [Página de prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies) no Centro de Conformidade do Microsoft 365 e selecione **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="dbdc1-169">Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do Ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="dbdc1-170">Visualização do scanner DLP local no explorador de atividades e registro de auditoria</span><span class="sxs-lookup"><span data-stu-id="dbdc1-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="dbdc1-171">O verificador local requer que a auditoria esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="dbdc1-172">No Microsoft 365, a auditoria é habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="dbdc1-173">Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) para seu domínio no Centro de Conformidade do Microsoft 365 e selecione explorador de Atividades.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="dbdc1-174">Consulte os procedimentos em [Introdução ao explorador de Atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados para os locais do scanner local.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="dbdc1-175">Abra o [Registro de Auditoria no centro de Conformidade](https://security.microsoft.com/auditlogsearch).</span><span class="sxs-lookup"><span data-stu-id="dbdc1-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="dbdc1-176">Durante a visualização pública, as correspondências de regras de DLP estão disponíveis na IU do log de Auditoria ou acessíveis por [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbdc1-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="dbdc1-177">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dbdc1-177">Next steps</span></span>
<span data-ttu-id="dbdc1-178">Agora que implantou uma política de teste para locais DLP locais e pode visualizar os dados de atividade no Explorador de atividades, você está pronto para passar para a próxima etapa, onde criará políticas DLP que protegem seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="dbdc1-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="dbdc1-179">Usando DLP local (visualização)</span><span class="sxs-lookup"><span data-stu-id="dbdc1-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="dbdc1-180">Confira também</span><span class="sxs-lookup"><span data-stu-id="dbdc1-180">See also</span></span>

- [<span data-ttu-id="dbdc1-181">Saiba mais sobre o scanner local DLP (visualização)</span><span class="sxs-lookup"><span data-stu-id="dbdc1-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="dbdc1-182">Use o scanner local DLP (visualização)</span><span class="sxs-lookup"><span data-stu-id="dbdc1-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="dbdc1-183">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="dbdc1-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="dbdc1-184">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="dbdc1-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dbdc1-185">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="dbdc1-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dbdc1-186">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dbdc1-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)