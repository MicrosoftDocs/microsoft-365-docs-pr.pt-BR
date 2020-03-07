---
title: RGPD
description: Orientação técnica da Microsoft — CONJUNTO DE FERRAMENTAS DE MIGRAÇÕES FASTTRACK PARA ENVIAR SOLICITAÇÃO DE EXCLUSÃO
keywords: Migração FastTrack, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e1d5afa4e6b6ea92af39b46214397868e518e323
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557961"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="f41fa-104">Conjunto de ferramentas de migração FastTrack para envio de solicitação de exclusão</span><span class="sxs-lookup"><span data-stu-id="f41fa-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="f41fa-105">Finalidade do conjunto de ferramentas</span><span class="sxs-lookup"><span data-stu-id="f41fa-105">Toolset purpose</span></span>

<span data-ttu-id="f41fa-p101">Se você for um cliente envolvido atualmente com migrações FastTrack, a exclusão da conta de usuário do Office 365 não excluirá a cópia dos dados em posse da equipe do Microsoft FastTrack, mantida apenas para a conclusão da migração. Se, durante a migração, você quiser que a equipe do Microsoft FastTrack também exclua a cópia dos dados, envie uma solicitação por esse conjunto de ferramentas. No curso normal dos negócios, o Microsoft FastTrack excluirá todas as cópias dos dados após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="f41fa-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="f41fa-109">Plataformas compatíveis</span><span class="sxs-lookup"><span data-stu-id="f41fa-109">Supported platforms</span></span>
<span data-ttu-id="f41fa-p102">A Microsoft oferece suporte à versão inicial deste conjunto de ferramentas na plataforma do Windows e no console do PowerShell. Este conjunto de ferramentas oferece suporte às plataformas conhecidas a seguir:</span><span class="sxs-lookup"><span data-stu-id="f41fa-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="f41fa-112">***Tabela 1 - Plataformas compatíveis com este conjunto de ferramentas***</span><span class="sxs-lookup"><span data-stu-id="f41fa-112">***Table 1 — Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="f41fa-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="f41fa-113">**Windows 7**</span></span>|<span data-ttu-id="f41fa-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="f41fa-114">**Windows 8**</span></span>|<span data-ttu-id="f41fa-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="f41fa-115">**Windows 10**</span></span>|<span data-ttu-id="f41fa-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="f41fa-116">**Windows Server 2012**</span></span>|<span data-ttu-id="f41fa-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="f41fa-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="f41fa-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="f41fa-118">PS 5.0</span></span>|<span data-ttu-id="f41fa-119">Not</span><span class="sxs-lookup"><span data-stu-id="f41fa-119">Not</span></span><br/><span data-ttu-id="f41fa-120">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-120">Supported</span></span>|<span data-ttu-id="f41fa-121">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-121">Supported</span></span>|<span data-ttu-id="f41fa-122">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-122">Supported</span></span>|<span data-ttu-id="f41fa-123">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-123">Supported</span></span>|<span data-ttu-id="f41fa-124">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-124">Supported</span></span>|
|<span data-ttu-id="f41fa-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="f41fa-125">PS 5.1</span></span>|<span data-ttu-id="f41fa-126">Not</span><span class="sxs-lookup"><span data-stu-id="f41fa-126">Not</span></span><br/><span data-ttu-id="f41fa-127">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-127">Supported</span></span>|<span data-ttu-id="f41fa-128">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-128">Supported</span></span>|<span data-ttu-id="f41fa-129">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-129">Supported</span></span>|<span data-ttu-id="f41fa-130">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-130">Supported</span></span>|<span data-ttu-id="f41fa-131">Com suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="f41fa-132">Como obter o conjunto de ferramentas</span><span class="sxs-lookup"><span data-stu-id="f41fa-132">Obtaining the toolset</span></span>

<span data-ttu-id="f41fa-p103">Este conjunto de ferramentas está disponível na Galeria do PowerShell no aplicativo de console do PowerShell. Para localizar e carregar o módulo desse cmdlet, primeiro abra o PowerShell no modo de administrador para que ele tenha as permissões apropriadas para instalar o módulo. Se você nunca usou o PowerShell, acesse a Barra de Tarefas do Windows e, na caixa de pesquisa, digite "PowerShell". Selecione o aplicativo de console usando o botão direito e escolha **Executar como administrador**, depois clique em **Sim** para executar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f41fa-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - Executar como administrador](../media/fasttrack-powershell_image.png)

![PowerShell - Permitir que o aplicativo faça alterações](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="f41fa-p104">Agora que o console está aberto, você precisa definir permissões para a execução do script. Digite o seguinte comando para permitir a execução dos scripts: ‘Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope:Process’</span><span class="sxs-lookup"><span data-stu-id="f41fa-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span></span>

<span data-ttu-id="f41fa-141">Você receberá uma solicitação para confirmar essa ação, pois o administrador pode alterar o escopo de acordo com seu critério.</span><span class="sxs-lookup"><span data-stu-id="f41fa-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="f41fa-142">***Definir a política de execução***</span><span class="sxs-lookup"><span data-stu-id="f41fa-142">***Set Execution Policy***</span></span>

![Definir alteração de política de execução no PowerShell](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="f41fa-144">Agora que o console está configurado para permitir o script, execute o próximo comando para instalar o módulo:</span><span class="sxs-lookup"><span data-stu-id="f41fa-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="f41fa-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="f41fa-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="f41fa-146">Pré-requisitos para o módulo</span><span class="sxs-lookup"><span data-stu-id="f41fa-146">Prerequisites for module</span></span>
<span data-ttu-id="f41fa-p105">Para executar com êxito este módulo, você precisará instalar módulos dependentes para uso, caso eles ainda não estejam instalados. Talvez seja necessário reiniciar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f41fa-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="f41fa-149">Para enviar um DSR, primeiro você deve fazer logon usando suas credenciais do Office 365 – as credenciais adequadas validarão seu status de administrador global e coletarão informações de locatário.</span><span class="sxs-lookup"><span data-stu-id="f41fa-149">In order to submit a DSR, you must first log in using your Office 365 credentials — entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="f41fa-150">**Login-FastTrackAccount -ApiKey: \<chave de API fornecida pela FastTrack MVM\>**</span><span class="sxs-lookup"><span data-stu-id="f41fa-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="f41fa-151">Após o logon bem-sucedido, as credenciais e a chave serão armazenadas para uso com os módulos do FastTrack durante o restante da sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f41fa-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="f41fa-152">Se você precisar se conectar a um ambiente de nuvem que não seja comercial, será necessário adicionar *-Environment* ao comando de *Logon* com um dos seguintes ambientes válidos:</span><span class="sxs-lookup"><span data-stu-id="f41fa-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>
- <span data-ttu-id="f41fa-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="f41fa-153">AzureCloud</span></span>
- <span data-ttu-id="f41fa-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="f41fa-154">AzureChinaCloud</span></span>
- <span data-ttu-id="f41fa-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="f41fa-155">AzureGermanCloud</span></span>
- <span data-ttu-id="f41fa-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="f41fa-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="f41fa-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <ambiente de nuvem\>**</span><span class="sxs-lookup"><span data-stu-id="f41fa-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="f41fa-158">Para enviar uma solicitação de DSR, execute o seguinte comando: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="f41fa-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="f41fa-p106">Em caso de sucesso – o cmdlet retornará um objeto com um objeto ID da Transação. Guarde a ID da Transação.</span><span class="sxs-lookup"><span data-stu-id="f41fa-p106">On success — the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="f41fa-161">Verificar o status da transação de uma solicitação</span><span class="sxs-lookup"><span data-stu-id="f41fa-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="f41fa-162">Execute a seguinte função usando a ID da Transação obtida anteriormente: FastTrackGdprDsrRequest Get - TransactionID: "SuaIDDaTransação"</span><span class="sxs-lookup"><span data-stu-id="f41fa-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="f41fa-163">Códigos de Status da Transação</span><span class="sxs-lookup"><span data-stu-id="f41fa-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="f41fa-164">**Transação**</span><span class="sxs-lookup"><span data-stu-id="f41fa-164">**Transaction**</span></span> |<span data-ttu-id="f41fa-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="f41fa-165">**Status**</span></span>|
|<span data-ttu-id="f41fa-166">**Created**</span><span class="sxs-lookup"><span data-stu-id="f41fa-166">**Created**</span></span> |<span data-ttu-id="f41fa-167">A solicitação foi criada</span><span class="sxs-lookup"><span data-stu-id="f41fa-167">Request has been created</span></span>|
|<span data-ttu-id="f41fa-168">**Falhou**</span><span class="sxs-lookup"><span data-stu-id="f41fa-168">**Failed**</span></span>|<span data-ttu-id="f41fa-169">Falha na criação da solicitação, envie de novo ou contate o suporte</span><span class="sxs-lookup"><span data-stu-id="f41fa-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="f41fa-170">**Concluída**</span><span class="sxs-lookup"><span data-stu-id="f41fa-170">**Completed**</span></span>|<span data-ttu-id="f41fa-171">Solicitação foi concluída e corrigida</span><span class="sxs-lookup"><span data-stu-id="f41fa-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="f41fa-172">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="f41fa-172">Learn more</span></span>
[<span data-ttu-id="f41fa-173">Central de Confiabilidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f41fa-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
