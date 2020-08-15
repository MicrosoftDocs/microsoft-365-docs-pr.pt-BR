---
title: Usar o PowerShell para realizar uma migração de substituição para o Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Saiba como usar o PowerShell para mover o conteúdo de um sistema de email de origem de uma só vez executando uma migração de substituição para o Microsoft 365.
ms.openlocfilehash: bf97fef7e0e927dc901b0223978a3eef377def2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686933"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="3b38d-103">Usar o PowerShell para realizar uma migração de substituição para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b38d-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="3b38d-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3b38d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3b38d-105">Você pode migrar o conteúdo das caixas de correio de usuários de um sistema de email de origem para o Microsoft 365 todos ao mesmo tempo usando uma migração de substituição.</span><span class="sxs-lookup"><span data-stu-id="3b38d-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="3b38d-106">Este artigo apresenta as tarefas para uma migração de substituição de email usando o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b38d-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span> 
  
<span data-ttu-id="3b38d-107">Ao analisar o tópico, [o que você precisa saber sobre uma migração de substituição de email para o Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), você pode obter uma visão geral do processo de migração.</span><span class="sxs-lookup"><span data-stu-id="3b38d-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), you can get an overview of the migration process.</span></span> <span data-ttu-id="3b38d-108">Quando você estiver familiarizado com os conteúdos do artigo, use o seguinte para começar a migrar caixas de correio de um sistema de email para outro.</span><span class="sxs-lookup"><span data-stu-id="3b38d-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b38d-109">Você também pode usar o centro de administração do Exchange para realizar uma migração de substituição.</span><span class="sxs-lookup"><span data-stu-id="3b38d-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="3b38d-110">Consulte [executar uma migração de substituição de email para a Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span><span class="sxs-lookup"><span data-stu-id="3b38d-110">See [Perform a cutover migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b38d-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3b38d-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="3b38d-112">Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="3b38d-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="3b38d-113">Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível.</span><span class="sxs-lookup"><span data-stu-id="3b38d-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="3b38d-114">Para obter informações sobre outros fatores que afetam quanto tempo leva para migrar caixas de correio para a Microsoft 365, consulte [desempenho de migração](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="3b38d-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="3b38d-p105">Para executar esses procedimentos, você precisa receber permissões. Para saber quais permissões são necessárias, confira a entrada "Migração" em uma tabela no tópico [Permissões de destinatários](https://go.microsoft.com/fwlink/p/?LinkId=534105).</span><span class="sxs-lookup"><span data-stu-id="3b38d-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="3b38d-p106">Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p106">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="3b38d-119">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="3b38d-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="3b38d-120">Etapas da migração</span><span class="sxs-lookup"><span data-stu-id="3b38d-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="3b38d-121">Etapa 1: preparar para uma migração de transferência</span><span class="sxs-lookup"><span data-stu-id="3b38d-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="3b38d-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="3b38d-123">**Adicione sua organização do Exchange local como um domínio aceito de sua organização do Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="3b38d-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="3b38d-124">O serviço de migração usa o endereço SMTP de suas caixas de correio locais para criar a ID de usuário e o endereço de email do Microsoft Online Services para as novas caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="3b38d-125">A migração falhará se o seu domínio do Exchange não for um domínio aceito ou o domínio primário da sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="3b38d-126">Para obter mais informações, consulte [Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span><span class="sxs-lookup"><span data-stu-id="3b38d-126">For more information, see [Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="3b38d-p108">**Configure o Outlook em Qualquer Lugar no servidor Exchange no local** O serviço de migração de email usa o RPC sobre HTTP ou o Outlook em Qualquer Lugar para se conectar ao servidor do Exchange no local. Para saber mais sobre como configurar o Outlook em Qualquer Lugar para Exchange 2010, Exchange 2007 e Exchange 2003, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3b38d-p108">**Configure Outlook Anywhere on your on-premises Exchange server.** The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server. For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>
    
  - [<span data-ttu-id="3b38d-130">Exchange 2010: Habilitar o Outlook em Qualquer Lugar</span><span class="sxs-lookup"><span data-stu-id="3b38d-130">Exchange 2010: Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=187249)
    
  - [<span data-ttu-id="3b38d-131">Exchange 2007: Como Habilitar o Outlook em Qualquer Lugar</span><span class="sxs-lookup"><span data-stu-id="3b38d-131">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)
    
  - [<span data-ttu-id="3b38d-132">Exchange 2003: Cenários de implantação para RPC sobre HTTP</span><span class="sxs-lookup"><span data-stu-id="3b38d-132">Exchange 2003: Deployment Scenarios for RPC over HTTP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73657)
    
  - [<span data-ttu-id="3b38d-133">Como Configurar o Outlook em Qualquer Lugar com o Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="3b38d-133">How to Configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b38d-p109">Sua configuração do Outlook em Qualquer Lugar deve ser configurada com um certificado emitido por uma autoridade de certificação (AC) confiável. Ele não pode ser configurado com um certificado autoassinado. Para saber mais, confira [Como configurar o SSL para o Outlook em Qualquer Lugar](https://go.microsoft.com/fwlink/?LinkID=80875).</span><span class="sxs-lookup"><span data-stu-id="3b38d-p109">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA). It can't be configured with a self-signed certificate. For more information, see [How to Configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
- <span data-ttu-id="3b38d-p110">**Verifique se você pode se conectar à organização do Exchange usando o Outlook em Qualquer Lugar** Experimente um destes métodos para testar suas configurações de conexão:</span><span class="sxs-lookup"><span data-stu-id="3b38d-p110">**Verify that you can connect to your Exchange organization using Outlook Anywhere.** Try one of these methods to test your connection settings:</span></span>
    
  - <span data-ttu-id="3b38d-139">Use o Microsoft Outlook de fora da rede corporativa para se conectar à sua caixa de correio do Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="3b38d-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
  - <span data-ttu-id="3b38d-p111">Use o [Analisador de Conectividade Remota do Microsoft Exchange](https://www.testexchangeconnectivity.com/) para testar suas configurações de conexão. Use o Outlook em Qualquer Lugar (RPC sobre HTTP) ou testes de descoberta automática do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p111">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings. Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
  - <span data-ttu-id="3b38d-142">Execute os comandos a seguir no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b38d-142">Run the following commands in Exchange Online PowerShell.</span></span>
    
  ```
  $Credentials = Get-Credential
  ```

  ```
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="3b38d-143">**Atribua as permissões necessárias a uma conta de usuário local para acessar caixas de correio em sua organização do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="3b38d-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="3b38d-144">A conta de usuário local que você usa para se conectar à sua organização local do Exchange (também chamada de administrador de migração) deve ter as permissões necessárias para acessar as caixas de correio locais que você deseja migrar para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="3b38d-145">Essa conta de usuário é usada para criar um ponto de extremidade de migração para a sua organização local.</span><span class="sxs-lookup"><span data-stu-id="3b38d-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>
    
    <span data-ttu-id="3b38d-p113">A lista a seguir mostra os privilégios administrativos necessários para migrar caixas de correio usando uma migração de transferência. Existem três opções possíveis.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p113">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration. There are three possible options.</span></span>
    
  - <span data-ttu-id="3b38d-148">O administrador de migração deve ser membro do grupo **Administradores de Domínio** no Active Directory na organização local.</span><span class="sxs-lookup"><span data-stu-id="3b38d-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="3b38d-149">Ou</span><span class="sxs-lookup"><span data-stu-id="3b38d-149">Or</span></span>
    
  - <span data-ttu-id="3b38d-150">O administrador de migração deve ser atribuído a permissão **FullAccess** para cada caixa de correio local.</span><span class="sxs-lookup"><span data-stu-id="3b38d-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>
    
    <span data-ttu-id="3b38d-151">Ou</span><span class="sxs-lookup"><span data-stu-id="3b38d-151">Or</span></span>
    
  - <span data-ttu-id="3b38d-152">O administrador de migração deve ser atribuído a permissão **Receber como** no banco de dados da caixa de correio local que armazena as caixas de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="3b38d-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>
    
- <span data-ttu-id="3b38d-p114">**Desabilite a Unificação de Mensagens.** Se as caixas de correio locais que você está migrando estiverem habilitadas para a UM (Unificação de Mensagens), será necessário desabilitar a UM nas caixas de correio antes de migrá-las. Em seguida, você poderá habilitar a UM nas caixas de correio depois que a migração for concluída.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p114">**Disable Unified Messaging.** If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them. You can then enable UM on the mailboxes after the migration is complete.</span></span>
    
- <span data-ttu-id="3b38d-156">**Grupos de segurança e representantes** O serviço de migração de email não pode detectar se os grupos locais do Active Directory são grupos de segurança ou não, portanto, não pode provisionar nenhum grupo migrado como grupos de segurança no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="3b38d-157">Se você deseja ter grupos de segurança em seu locatário do Microsoft 365, primeiro você deve provisionar um grupo de segurança habilitado para email vazio em seu locatário do Microsoft 365 antes de iniciar a migração de substituição.</span><span class="sxs-lookup"><span data-stu-id="3b38d-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="3b38d-158">Além disso, esse método de migração só move caixas de correio, usuários de email, contatos de email e grupos habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="3b38d-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="3b38d-159">Se qualquer outro objeto do Active Directory, como o usuário que não for migrado para o Microsoft 365, for atribuído como um gerente ou representante a um objeto que está sendo migrado, ele deverá ser removido do objeto antes da migração.</span><span class="sxs-lookup"><span data-stu-id="3b38d-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>
    
### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="3b38d-160">Etapa 2: criar um ponto de extremidade de migração</span><span class="sxs-lookup"><span data-stu-id="3b38d-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="3b38d-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="3b38d-162">Para migrar emails com êxito, o Microsoft 365 precisa se conectar e se comunicar com o sistema de email de origem.</span><span class="sxs-lookup"><span data-stu-id="3b38d-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="3b38d-163">Para fazer isso, a Microsoft 365 usa um ponto de extremidade de migração.</span><span class="sxs-lookup"><span data-stu-id="3b38d-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="3b38d-164">Para criar um ponto de extremidade de migração do Outlook em qualquer lugar para migração de substituição, primeiro [Conecte-se ao Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="3b38d-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="3b38d-165">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="3b38d-165">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="3b38d-166">Execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="3b38d-166">Run the following commands in Exchange Online PowerShell:</span></span>
  
```
$Credentials = Get-Credential
```

<span data-ttu-id="3b38d-167">O exemplo usa o cmdlet [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) para obter e testar as configurações de conexão ao servidor do Exchange local e usa essas configurações de conexão para criar o ponto de extremidade de migração chamado "CutoverEndpoint".</span><span class="sxs-lookup"><span data-stu-id="3b38d-167">The example uses the [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>
  
```
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="3b38d-p117">O cmdlet **New-MigrationEndpoint** pode ser usado para especificar um banco de dados do serviço a usar, utilizando a opção **-TargetDatabase**. Caso contrário, o banco de dados é atribuído de forma aleatória do site do Serviços de Federação do Active Directory (AD FS) 2.0, no qual a caixa de correio de gerenciamento está localizada.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p117">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="3b38d-170">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="3b38d-170">Verify it worked</span></span>

<span data-ttu-id="3b38d-171">No PowerShell do Exchange Online, execute o seguinte comando para exibir informações sobre o ponto de extremidade de migração "CutoverEndpoint":</span><span class="sxs-lookup"><span data-stu-id="3b38d-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>
  
```
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="3b38d-172">Etapa 3: criar o lote de migração de transferência</span><span class="sxs-lookup"><span data-stu-id="3b38d-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="3b38d-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="3b38d-p118">Você pode usar o cmdlet **New-MigrationBatch** no PowerShell do Exchange Online para criar um lote de migração de uso em uma migração de transferência. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo manualmente mais tarde usando o cmdlet **Start-MigrationBatch**. Este exemplo cria um lote de migração chamado "CutoverBatch" e utiliza o ponto de extremidade de migração criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p118">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="3b38d-p119">Este exemplo também cria um lote de migração chamado "CutoverBatch" e utiliza o ponto de extremidade de migração criado na etapa anterior. Como o parâmetro  _AutoStart_ não está incluído, o lote de migração deve ser iniciado manualmente no painel de migração ou usando o cmdlet **Start-MigrationBatch**. Como dito anteriormente, apenas um lote de migração de transferência pode existir de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p119">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="3b38d-181">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="3b38d-181">Verify it worked</span></span>

<span data-ttu-id="3b38d-182">Para verificar se você criou com êxito um lote de migração para uma migração de substituição, execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o novo lote de migração:</span><span class="sxs-lookup"><span data-stu-id="3b38d-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>
  
```
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="3b38d-183">Etapa 4: iniciar o lote de migração de transferência</span><span class="sxs-lookup"><span data-stu-id="3b38d-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="3b38d-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="3b38d-p120">Para iniciar o lote de migração no PowerShell do Exchange Online, execute o seguinte comando. Isso criará um lote de migração chamado "CutoverBatch".</span><span class="sxs-lookup"><span data-stu-id="3b38d-p120">To start the migration batch in Exchange Online PowerShell, run the following command. This will create a migration batch called "CutoverBatch".</span></span>
  
```
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="3b38d-187">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="3b38d-187">Verify it worked</span></span>

<span data-ttu-id="3b38d-p121">Se um lote de migração for iniciado com êxito, seu status no painel de migração será especificado como Sincronizando. Para verificar se você iniciou com êxito um lote de migração usando o PowerShell do Exchange Online, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3b38d-p121">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing. To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>
  
```
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="3b38d-190">Etapa 5: encaminhar seu email para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b38d-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="3b38d-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="3b38d-192">Os sistemas de email usam um registro DNS chamado registro MX para descobrir onde entregar emails.</span><span class="sxs-lookup"><span data-stu-id="3b38d-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="3b38d-193">Durante o processo de migração de email, seu registro MX estava apontando para o sistema de email de origem.</span><span class="sxs-lookup"><span data-stu-id="3b38d-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="3b38d-194">Agora que a migração de email para o Microsoft 365 está concluída, é hora de apontar o seu registro MX no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="3b38d-195">Isso ajuda a garantir que o email seja entregue às suas caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="3b38d-196">Movendo o registro MX, você também poderá desativar seu sistema de email antigo quando estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="3b38d-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="3b38d-p123">Para muitos provedores DNS, existem instruções específicas para [alterar seu registro MX](https://go.microsoft.com/fwlink/p/?LinkId=279163). Se seu provedor DNS não estiver incluído ou se você desejar ter uma noção das instruções gerais, [instruções gerais sobre o registro MX ](https://go.microsoft.com/fwlink/?LinkId=397449) também são fornecidas.</span><span class="sxs-lookup"><span data-stu-id="3b38d-p123">For many DNS providers, there are specific instructions to [change your MX record](https://go.microsoft.com/fwlink/p/?LinkId=279163). If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="3b38d-p124">Pode levar até 72 horas para que os sistemas de email de seus clientes e parceiros reconheçam o registro MX alterado. Aguarde pelo menos 72 horas antes de prosseguir para a próxima tarefa: [Etapa 6: excluir o lote de migração de transferência](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="3b38d-p124">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span> 
  
### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="3b38d-201">Etapa 6: excluir o lote de migração de transferência</span><span class="sxs-lookup"><span data-stu-id="3b38d-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="3b38d-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="3b38d-203">Depois de alterar o registro MX e verificar se todos os emails estão sendo roteados para as caixas de correio do Microsoft 365, notifique os usuários de que seus emails estão indo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="3b38d-204">Depois disso, você pode excluir o lote de migração de substituição.</span><span class="sxs-lookup"><span data-stu-id="3b38d-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="3b38d-205">Antes de excluir o lote de migração, verifique os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="3b38d-205">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="3b38d-206">Todos os usuários estão usando caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="3b38d-207">Depois que o lote é excluído, os emails enviados para caixas de correio no servidor Exchange local não são copiados para as caixas de correio do Microsoft 365 correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3b38d-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="3b38d-208">As caixas de correio do Microsoft 365 foram sincronizadas pelo menos uma vez depois que o email começou a ser enviado diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="3b38d-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="3b38d-209">Para fazer isso, certifique-se de que o valor na caixa de hora da última sincronização do lote de migração seja mais recente do que quando o email começou a ser roteado diretamente para as caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="3b38d-210">Para excluir o lote de migração "CutoverBatch" no PowerShell do Exchange Online, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3b38d-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>
  
```
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="3b38d-211">Seção 7: atribuir licenças de usuários</span><span class="sxs-lookup"><span data-stu-id="3b38d-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="3b38d-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="3b38d-213">**Ative as contas de usuário do Microsoft 365 para as contas migradas, atribuindo licenças.**</span><span class="sxs-lookup"><span data-stu-id="3b38d-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="3b38d-214">Se você não atribuir uma licença, a caixa de correio será desabilitada quando terminar o período de carência (30 dias).</span><span class="sxs-lookup"><span data-stu-id="3b38d-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="3b38d-215">Para atribuir uma licença no centro de administração do Microsoft 365, confira [atribuir ou](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)cancelar a atribuição de licenças.</span><span class="sxs-lookup"><span data-stu-id="3b38d-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="3b38d-216">Etapa 8: concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="3b38d-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="3b38d-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="3b38d-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="3b38d-218">**Crie um registro DNS de Descoberta Automática para que os usuários possam acessar facilmente suas caixas de correio.**</span><span class="sxs-lookup"><span data-stu-id="3b38d-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="3b38d-219">Depois que todas as caixas de correio locais são migradas para o Microsoft 365, você pode configurar um registro DNS de descoberta automática para sua organização do Microsoft 365 para permitir que os usuários se conectem facilmente às novas caixas de correio do Microsoft 365 com o Outlook e clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="3b38d-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="3b38d-220">Este novo registro DNS de descoberta automática deve usar o mesmo namespace que você está usando para sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b38d-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="3b38d-221">Por exemplo, se seu namespace baseado na nuvem for cloud.contoso.com, o registro DNS de Descoberta Automática que você precisa criar será autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b38d-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="3b38d-222">Se você mantiver seu servidor Exchange, você também deve certificar-se de que o registro CNAME DNS de descoberta automática tenha que apontar para o Microsoft 365 em DNS interno e externo após a migração para que o cliente do Outlook se conecte à caixa de correio correta.</span><span class="sxs-lookup"><span data-stu-id="3b38d-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="3b38d-223">No Exchange 2007, Exchange 2010 e no Exchange 2013, você também deve definir o  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` como `Null`.</span><span class="sxs-lookup"><span data-stu-id="3b38d-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span> 
  
    <span data-ttu-id="3b38d-224">O Microsoft 365 usa um registro CNAME para implementar o serviço de descoberta automática para clientes móveis e do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b38d-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="3b38d-225">O registro CNAME de Descoberta Automática deve conter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3b38d-225">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="3b38d-226">**Alias:** descoberta automática</span><span class="sxs-lookup"><span data-stu-id="3b38d-226">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="3b38d-227">**Destino:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="3b38d-227">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="3b38d-228">Para obter mais informações, consulte [Add DNS Records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span><span class="sxs-lookup"><span data-stu-id="3b38d-228">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="3b38d-229">**Encerrar servidores locais do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="3b38d-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="3b38d-230">Depois de verificar se todos os emails estão sendo roteados diretamente para as caixas de correio do Microsoft 365, e você não precisa mais manter sua organização de email local ou não planeja implementar uma solução de logon único (SSO), é possível desinstalar o Exchange de seus servidores e remover sua organização do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="3b38d-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="3b38d-231">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3b38d-231">For more information, see the following:</span></span>
    
  - [<span data-ttu-id="3b38d-232">Modificar ou remover o Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="3b38d-232">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [<span data-ttu-id="3b38d-233">Como remover uma Organização do Exchange 2007</span><span class="sxs-lookup"><span data-stu-id="3b38d-233">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [<span data-ttu-id="3b38d-234">Como desinstalar o Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="3b38d-234">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)
    

