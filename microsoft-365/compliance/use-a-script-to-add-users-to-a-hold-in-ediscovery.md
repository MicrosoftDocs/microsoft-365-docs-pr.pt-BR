---
title: Usar um script para adicionar usuários a uma espera em um caso de Descoberta e Principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Saiba como executar um script para adicionar caixas de correio & sites do OneDrive for Business a uma nova espera associada a um caso de Descoberta Eletrônico no centro de conformidade do Microsoft 365.
ms.openlocfilehash: 72fd9b8e7b63b36399d055e2eb710e8b53967e44
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126434"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="ed988-103">Usar um script para adicionar usuários a uma espera em um caso de Descoberta e Principal</span><span class="sxs-lookup"><span data-stu-id="ed988-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="ed988-104">O PowerShell & segurança e conformidade fornece cmdlets que permitem automatizar tarefas demoradas relacionadas à criação e gerenciamento de casos de Descoberta Eletrônica.</span><span class="sxs-lookup"><span data-stu-id="ed988-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="ed988-105">Atualmente &, o uso do caso de Descoberta Principal no Centro de Conformidade e Segurança para colocar um grande número de locais de conteúdo custodiante em espera leva tempo e preparação.</span><span class="sxs-lookup"><span data-stu-id="ed988-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="ed988-106">Por exemplo, antes de criar uma espera, você precisa coletar a URL de cada site do OneDrive for Business que deseja colocar em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="ed988-107">Em seguida, para cada usuário que você deseja colocar em espera, você precisa adicionar sua caixa de correio e seu site do OneDrive for Business à espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="ed988-108">Você pode usar o script neste artigo para automatizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="ed988-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="ed988-109">O script solicita o nome do domínio de Meu Site da sua organização (por exemplo, na URL, o nome de um caso de Descoberta Eletrônico existente, o nome da nova responsabilidade associada à ocorrência, uma lista de endereços de email dos usuários que você deseja colocar em espera e uma consulta de pesquisa a ser usada se quiser criar uma espera baseada em `contoso` https://contoso-my.sharepoint.com) consulta.</span><span class="sxs-lookup"><span data-stu-id="ed988-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="ed988-110">Em seguida, o script obtém a URL do site do OneDrive for Business para cada usuário na lista, cria a nova espera e, em seguida, adiciona a caixa de correio e o site do OneDrive for Business para cada usuário na lista à espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="ed988-111">O script também gera arquivos de log que contêm informações sobre a nova espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="ed988-112">Aqui estão as etapas para fazer isso acontecer:</span><span class="sxs-lookup"><span data-stu-id="ed988-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="ed988-113">Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ed988-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="ed988-114">Etapa 2: Gerar uma lista de usuários</span><span class="sxs-lookup"><span data-stu-id="ed988-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="ed988-115">Etapa 3: Executar o script para criar uma espera e adicionar usuários</span><span class="sxs-lookup"><span data-stu-id="ed988-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="ed988-116">Antes de adicionar usuários a uma espera</span><span class="sxs-lookup"><span data-stu-id="ed988-116">Before you add users to a hold</span></span>

- <span data-ttu-id="ed988-117">Você precisa ser membro do grupo de funções Gerente de Descobertas EDiscovery no Centro de Conformidade & Segurança e um administrador do SharePoint Online para executar o script na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ed988-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="ed988-118">Para saber mais, confira Atribuir permissões de Descoberta e no Centro de Conformidade e Segurança [& do Office 365.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="ed988-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="ed988-119">No máximo 1.000 caixas de correio e 100 sites podem ser adicionados a uma espera associada a um caso de & Descoberta Eletrônico no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="ed988-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="ed988-120">Supondo que cada usuário que você deseja colocar em espera tenha um site do OneDrive for Business, você pode adicionar no máximo 100 usuários a uma espera usando o script neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ed988-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="ed988-121">Salve a lista de usuários que você criou na Etapa 2 e o script na Etapa 3 na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="ed988-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="ed988-122">Isso facilitará a executar o script.</span><span class="sxs-lookup"><span data-stu-id="ed988-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="ed988-123">O script adiciona a lista de usuários a uma nova isenta que está associada a um caso existente.</span><span class="sxs-lookup"><span data-stu-id="ed988-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="ed988-124">Certifique-se de que o caso ao que você deseja associar a iseção foi criado antes de executar o script.</span><span class="sxs-lookup"><span data-stu-id="ed988-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="ed988-125">O script neste artigo oferece suporte à autenticação moderna & ao se conectar ao PowerShell do Centro de Conformidade e Segurança e Ao Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ed988-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="ed988-126">Você pode usar o script como está se você for uma organização do Microsoft 365 ou microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="ed988-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="ed988-127">Se você for uma organização do Office 365 Germany, uma organização do Microsoft 365 GCC High ou uma organização do Microsoft 365 DoD, terá que editar o script para executar com êxito.</span><span class="sxs-lookup"><span data-stu-id="ed988-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="ed988-128">Especificamente, você precisa editar a linha e usar os `Connect-IPPSSession` parâmetros *ConnectionUri* e *AzureADAuthorizationEndpointUri* (e os valores apropriados para seu tipo de organização &) para se conectar ao PowerShell do Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="ed988-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ed988-129">Para obter mais informações, consulte os exemplos no Centro de Conformidade e Segurança [& PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="ed988-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="ed988-130">O script se desconecta automaticamente do PowerShell do Centro de Conformidade & Segurança e do Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ed988-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="ed988-131">O script inclui tratamento mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="ed988-131">The script includes minimal error handling.</span></span> <span data-ttu-id="ed988-132">Sua principal finalidade é colocar a caixa de correio e o site do OneDrive for Business de forma rápida e fácil de cada usuário em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="ed988-p109">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="ed988-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="ed988-138">Etapa 1: Instalar o Shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ed988-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="ed988-139">A primeira etapa é instalar o Shell de Gerenciamento do SharePoint Online se ele ainda não estiver instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="ed988-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="ed988-140">Você não precisa usar o shell neste procedimento, mas precisa instalá-lo porque ele contém os pré-requisitos exigidos pelo script executado na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ed988-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="ed988-141">Esses pré-requisitos permitem que o script se comunique com o SharePoint Online para obter as URLs dos sites do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="ed988-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="ed988-142">Vá para Configurar o ambiente Do Windows PowerShell do Shell de Gerenciamento do [SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) e execute a Etapa 1 e a Etapa 2 para instalar o Shell de Gerenciamento do SharePoint Online no computador local.</span><span class="sxs-lookup"><span data-stu-id="ed988-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="ed988-143">Etapa 2: Gerar uma lista de usuários</span><span class="sxs-lookup"><span data-stu-id="ed988-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="ed988-144">O script na Etapa 3 criará uma espera associada a um caso de Descoberta Eletrônico e adicionará as caixas de correio e os sites do OneDrive for Business de uma lista de usuários à espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="ed988-145">Você pode apenas digitar os endereços de email em um arquivo de texto ou pode executar um comando no Windows PowerShell para obter uma lista de endereços de email e salvá-los em um arquivo (localizado na mesma pasta em que você salvará o script na Etapa 3).</span><span class="sxs-lookup"><span data-stu-id="ed988-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="ed988-146">Aqui está um comando do PowerShell (executado usando o PowerShell remoto conectado à sua organização do Exchange Online) para obter uma lista de endereços de email para todos os usuários em sua organização e salvá-lo em um arquivo de texto chamado HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="ed988-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="ed988-147">Depois de executar esse comando, abra o arquivo de texto e remova o header que contém o nome da  `PrimarySmtpAddress` propriedade.</span><span class="sxs-lookup"><span data-stu-id="ed988-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="ed988-148">Em seguida, remova todos os endereços de email, exceto os dos usuários que você deseja adicionar à espera que você criará na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ed988-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="ed988-149">Certifique-se de que não haja linhas em branco antes ou depois da lista de endereços de email.</span><span class="sxs-lookup"><span data-stu-id="ed988-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="ed988-150">Etapa 3: Executar o script para criar uma espera e adicionar usuários</span><span class="sxs-lookup"><span data-stu-id="ed988-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="ed988-151">Quando você executar o script nesta etapa, ele solicitará as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="ed988-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="ed988-152">Certifique-se de ter essas informações prontas antes de executar o script.</span><span class="sxs-lookup"><span data-stu-id="ed988-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="ed988-153">**Suas credenciais de usuário:** O script usará suas credenciais para se conectar ao Centro de Conformidade & segurança com o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="ed988-153">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="ed988-154">Ele também usará essas credenciais para acessar o SharePoint Online e obter as URLs do OneDrive for Business para a lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="ed988-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="ed988-155">**Nome do seu domínio de Meu Site:** O domínio de Meu Site é o domínio que contém todos os sites do OneDrive for Business em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ed988-155">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="ed988-156">Por exemplo, se a URL do seu domínio de Meu Site for, você digitará quando o script solicitar o nome do seu domínio **https://contoso-my.sharepoint.com**  `contoso` de Meu Site.</span><span class="sxs-lookup"><span data-stu-id="ed988-156">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="ed988-157">**Nome da ocorrência:** O nome de uma ocorrência existente.</span><span class="sxs-lookup"><span data-stu-id="ed988-157">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="ed988-158">O script criará uma nova iseção associada a esse caso.</span><span class="sxs-lookup"><span data-stu-id="ed988-158">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="ed988-159">**Nome da espera:** O nome da espera que o script criará e associará ao caso especificado.</span><span class="sxs-lookup"><span data-stu-id="ed988-159">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="ed988-160">**Consulta de pesquisa para uma espera baseada em consulta:** Você pode criar uma isenção baseada em consulta para que somente o conteúdo que atenda aos critérios de pesquisa especificados seja colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-160">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="ed988-161">Para colocar todo o conteúdo em espera, pressione **Enter** quando for solicitado a fazer uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ed988-161">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="ed988-162">**A ligar a espera ou não:** Você pode fazer o script ativar a espera depois que ele é criado ou fazer com que o script crie a espera sem habilita-lo.</span><span class="sxs-lookup"><span data-stu-id="ed988-162">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="ed988-163">Se você não tiver o script para ativar a espera &, poderá a turn-lo posteriormente no Centro de Conformidade e Segurança ou executando os seguintes comandos do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ed988-163">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="ed988-164">**Nome do arquivo de texto** com a lista de usuários - O nome do arquivo de texto da Etapa 2 que contém a lista de usuários a adicionar à espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-164">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="ed988-165">Se esse arquivo estiver localizado na mesma pasta do script, basta digitar o nome do arquivo (por exemplo, HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="ed988-165">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="ed988-166">Se o arquivo de texto estiver em outra pasta, digite o nome de caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ed988-166">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="ed988-167">Depois de coletar as informações que o script solicitará, a etapa final é executar o script para criar a nova iseção e adicionar usuários a ela.</span><span class="sxs-lookup"><span data-stu-id="ed988-167">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="ed988-168">Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo de `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="ed988-168">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="ed988-169">Por exemplo, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="ed988-169">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="ed988-170">No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="ed988-170">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="ed988-171">Execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ed988-171">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="ed988-172">Insira as informações que o script solicita.</span><span class="sxs-lookup"><span data-stu-id="ed988-172">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="ed988-173">O & script se conecta ao PowerShell do Centro de Conformidade e Segurança e, em seguida, cria a nova espera no caso de Descoberta Eletrônico e adiciona as caixas de correio e o OneDrive for Business para os usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="ed988-173">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="ed988-174">Você pode ir para o caso na página descoberta de **eDiscovery** no Centro de conformidade & segurança para exibir a nova espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-174">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="ed988-175">Após a execução do script, ele cria os arquivos de log a seguir e os salva na pasta onde o script está localizado.</span><span class="sxs-lookup"><span data-stu-id="ed988-175">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="ed988-176">**LocationsOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script colocou com êxito em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-176">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="ed988-177">**LocationsNotOnHold.txt:** Contém uma lista de caixas de correio e sites do OneDrive for Business que o script não colocar em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-177">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="ed988-178">Se um usuário tiver uma caixa de correio, mas não um site do OneDrive for Business, ele será incluído na lista de sites do OneDrive for Business que não foram colocados em espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-178">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="ed988-179">**GetCaseHoldPolicy.txt:** Contém a saída do cmdlet **Get-CaseHoldPolicy** para a nova espera, que o script criou após criar a nova espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-179">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="ed988-180">As informações retornadas por esse cmdlet incluem uma lista de usuários cujas caixas de correio e sites do OneDrive for Business foram colocados em espera e se a espera está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="ed988-180">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="ed988-181">**GetCaseHoldRule.txt:** Contém a saída do cmdlet **Get-CaseHoldRule** para a nova espera, que o script foi aplicável após a criação da nova espera.</span><span class="sxs-lookup"><span data-stu-id="ed988-181">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="ed988-182">As informações retornadas por esse cmdlet incluirão a consulta de pesquisa se você tiver usado o script para criar uma espera baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="ed988-182">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
