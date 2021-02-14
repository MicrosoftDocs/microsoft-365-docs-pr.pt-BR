---
title: Usar o PowerShell para executar uma migração em etapas para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Saiba como usar o PowerShell para mover conteúdo de um sistema de email de origem ao longo do tempo usando uma migração em estágios para o Microsoft 365.
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687069"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a><span data-ttu-id="12ac2-103">Usar o PowerShell para executar uma migração em etapas para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12ac2-103">Use PowerShell to perform a staged migration to Microsoft 365</span></span>

<span data-ttu-id="12ac2-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="12ac2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="12ac2-105">Você pode migrar o conteúdo das caixas de correio do usuário de um sistema de email de origem para o Microsoft 365 ao longo do tempo usando uma migração em estágios.</span><span class="sxs-lookup"><span data-stu-id="12ac2-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 over time using a staged migration.</span></span>
  
<span data-ttu-id="12ac2-106">Este artigo o orienta ao longo das tarefas envolvidas para uma migração em estágios de email usando o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="12ac2-106">This article walks you through the tasks involved with for a staged email migration using Exchange Online PowerShell.</span></span> <span data-ttu-id="12ac2-107">O tópico, [o que você precisa saber sobre uma migração](https://go.microsoft.com/fwlink/p/?LinkId=536487)de email em estágios, fornece uma visão geral do processo de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-107">The topic, [What you need to know about a staged email migration](https://go.microsoft.com/fwlink/p/?LinkId=536487), gives you an overview of the migration process.</span></span> <span data-ttu-id="12ac2-108">Quando você estiver familiarizado com os conteúdos do artigo, use o seguinte para começar a migrar caixas de correio de um sistema de email para outro.</span><span class="sxs-lookup"><span data-stu-id="12ac2-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12ac2-109">Você também pode usar o Centro de administração do Exchange para executar a migração em estágios.</span><span class="sxs-lookup"><span data-stu-id="12ac2-109">You can also use the Exchange admin center to perform staged migration.</span></span> <span data-ttu-id="12ac2-110">Confira [Executar uma migração em estágios de email para o Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=536687)</span><span class="sxs-lookup"><span data-stu-id="12ac2-110">See [Perform a staged migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12ac2-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="12ac2-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="12ac2-112">Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="12ac2-113">Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível.</span><span class="sxs-lookup"><span data-stu-id="12ac2-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="12ac2-114">Para obter informações sobre outros fatores que afetam o tempo necessário para migrar caixas de correio para o Microsoft 365, consulte Desempenho da [Migração.](https://go.microsoft.com/fwlink/p/?LinkId=275079)</span><span class="sxs-lookup"><span data-stu-id="12ac2-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="12ac2-p104">Para executar esses procedimentos, você precisa receber permissões. Para ver quais são as permissões necessárias, confira a entrada "Migração" no tópico [Permissões de destinatários](https://go.microsoft.com/fwlink/p/?LinkId=534105).</span><span class="sxs-lookup"><span data-stu-id="12ac2-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="12ac2-p105">Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="12ac2-119">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="12ac2-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="12ac2-120">Etapas da migração</span><span class="sxs-lookup"><span data-stu-id="12ac2-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-staged-migration"></a><span data-ttu-id="12ac2-121">Etapa 1: preparar para uma migração em estágios</span><span class="sxs-lookup"><span data-stu-id="12ac2-121">Step 1: Prepare for a staged migration</span></span>

<span data-ttu-id="12ac2-122">Antes de migrar caixas de correio para o Microsoft 365 usando uma migração em estágios, há algumas alterações que você deve fazer em seu ambiente do Exchange.</span><span class="sxs-lookup"><span data-stu-id="12ac2-122">Before you migrate mailboxes to Microsoft 365 by using a staged migration, there are a few changes you must make to your Exchange environment.</span></span>
  
 <span data-ttu-id="12ac2-p106">**Configurar o Outlook em Qualquer Lugar em seu Exchange Server** local O serviço de migração de email usa o Outlook em Qualquer Lugar (também conhecido como RPC sobre HTTP) para se conectar a seu Exchange Server local. Para saber mais sobre como configurar o Outlook em Qualquer Lugar para o Exchange Server 2007 e para o Exchange 2003, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12ac2-p106">**Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server. For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:</span></span>
  
- [<span data-ttu-id="12ac2-125">Exchange 2007: Como Habilitar o Outlook em Qualquer Lugar</span><span class="sxs-lookup"><span data-stu-id="12ac2-125">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [<span data-ttu-id="12ac2-126">Como configurar o Outlook em Qualquer Lugar com o Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="12ac2-126">How to configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> <span data-ttu-id="12ac2-p107">Você deve usar um certificado emitido por uma AC (autoridade de certificação) confiável com sua configuração do Outlook em Qualquer Lugar. O Outlook em Qualquer Lugar não pode ser configurado com um certificado autoassinado. Para saber mais, confira [Como configurar o SSL para o Outlook em Qualquer Lugar](https://go.microsoft.com/fwlink/?LinkID=80875)</span><span class="sxs-lookup"><span data-stu-id="12ac2-p107">You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
 <span data-ttu-id="12ac2-130">**Opcional: Verifique se você pode se conectar à sua organização do Exchange usando o Outlook em Qualquer Lugar** Tente um dos métodos a seguir para testar as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="12ac2-130">**Optional: Verify that you can connect to your Exchange organization using Outlook Anywhere** Try one of the following methods to test your connection settings.</span></span>
  
- <span data-ttu-id="12ac2-131">Use o Outlook fora de sua rede corporativa para se conectar a sua caixa de correio local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="12ac2-131">Use Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
- <span data-ttu-id="12ac2-132">Use o [Analisador de Conectividade Remota da Microsoft](https://https://testconnectivity.microsoft.com/) para testar as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="12ac2-132">Use the [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) to test your connection settings.</span></span> <span data-ttu-id="12ac2-133">Use o Outlook em Qualquer Lugar (RPC sobre HTTP) ou os testes de Descoberta Automática do Outlook.</span><span class="sxs-lookup"><span data-stu-id="12ac2-133">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
- <span data-ttu-id="12ac2-134">Execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="12ac2-134">Run the following commands in Exchange Online PowerShell:</span></span>
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 <span data-ttu-id="12ac2-135">**Definir permissões** A conta de usuário local que você usa para se conectar à sua organização local do Exchange (também chamada de administrador de migração) deve ter as permissões necessárias para acessar as caixas de correio locais que você deseja migrar para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-135">**Set permissions** The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="12ac2-136">Essa conta de usuário é usada quando você se conecta ao seu sistema de email criando um ponto de extremidade de migração posteriormente neste procedimento ( Etapa 3: Criar um ponto de extremidade[de migração).](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint)</span><span class="sxs-lookup"><span data-stu-id="12ac2-136">This user account is used when you connect to your email system by creating a migration endpoint later in this procedure ([Step 3: Create a migration endpoint](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).</span></span>
  
<span data-ttu-id="12ac2-137">Para migrar as caixas de correio, o administrador deve ter um dos seguintes conjuntos de permissão:</span><span class="sxs-lookup"><span data-stu-id="12ac2-137">To migrate the mailboxes, the admin must have one of the following permission sets:</span></span>
  
- <span data-ttu-id="12ac2-138">Ser membro do grupo **Administradores de Domínio** no Active Directory na organização local.</span><span class="sxs-lookup"><span data-stu-id="12ac2-138">Be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="12ac2-139">ou</span><span class="sxs-lookup"><span data-stu-id="12ac2-139">or</span></span>
    
- <span data-ttu-id="12ac2-140">Ter a permissão **FullAccess** para cada caixa de correio local e a permissão **WriteProperty** para modificar a propriedade **TargetAddress** nas contas de usuário locais.</span><span class="sxs-lookup"><span data-stu-id="12ac2-140">Be assigned the **FullAccess** permission for each on-premises mailbox and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
    <span data-ttu-id="12ac2-141">ou</span><span class="sxs-lookup"><span data-stu-id="12ac2-141">or</span></span>
    
- <span data-ttu-id="12ac2-142">Ter a permissão **Receive As** no banco de dados de caixa de correio local que armazena as caixas de correio do usuário e a permissão **WriteProperty** para modificar a propriedade **TargetAddress** nas contas de usuário locais.</span><span class="sxs-lookup"><span data-stu-id="12ac2-142">Be assigned the **Receive As** permission on the on-premises mailbox database that stores user mailboxes and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
<span data-ttu-id="12ac2-143">Para obter instruções sobre como definir essas permissões, confira Atribuir permissões para migrar caixas de correio [para o Microsoft 365.](https://go.microsoft.com/fwlink/?LinkId=521656)</span><span class="sxs-lookup"><span data-stu-id="12ac2-143">For instructions about how to set these permissions, see [Assign permissions to migrate mailboxes to Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).</span></span>
  
 <span data-ttu-id="12ac2-p110">**Desabilitar a UM (Unificação de Mensagens)** Se a UM estiver habilitada para as caixas de correio locais que você está migrando, desabilite a UM antes da migração. Habilite a UM para as caixas de correio após a conclusão da migração. Para obter instruções, confira [desabilitar a unificação de mensagens](https://go.microsoft.com/fwlink/?LinkId=521891).</span><span class="sxs-lookup"><span data-stu-id="12ac2-p110">**Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration. Turn on UM for the mailboxes after migration is complete. For how-to steps, see[disable unified messaging](https://go.microsoft.com/fwlink/?LinkId=521891).</span></span>
  
 <span data-ttu-id="12ac2-147">**Use a sincronização de diretórios para criar novos usuários no Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="12ac2-147">**Use directory synchronization to create new users in Microsoft 365.**</span></span> <span data-ttu-id="12ac2-148">Use a sincronização de diretórios para criar todos os usuários locais em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-148">You use directory synchronization to create all the on-premises users in your Microsoft 365 organization.</span></span>
  
<span data-ttu-id="12ac2-p112">Você precisa licenciar os usuários depois que eles são criados. O prazo é de 30 dias para adicionar licenças depois que os usuários são criados. Para obter as etapas para adicionar licenças, confira [Etapa 8: concluir tarefas pós-migração](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span><span class="sxs-lookup"><span data-stu-id="12ac2-p112">You need to license the users after they're created. You have 30 days to add licenses after the users are created. For steps to add licenses, see [Step 8: Complete post-migration tasks](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span></span>
  
 <span data-ttu-id="12ac2-152">Você pode usar a Ferramenta de Sincronização do Microsoft Azure Active Directory (Azure AD) ou os Serviços de Sincronização do Microsoft Azure AD para sincronizar e criar seus usuários locais no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-152">You can use either the Microsoft Azure Active Directory (Azure AD) Synchronization Tool or the Microsoft Azure AD Sync Services  to synchronize and create your on-premises users in Microsoft 365.</span></span> <span data-ttu-id="12ac2-153">Depois que as caixas de correio são migradas para o Microsoft 365, você gerencia contas de usuário em sua organização local e elas são sincronizadas com sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-153">After mailboxes are migrated to Microsoft 365, you manage user accounts in your on-premises organization, and they're synchronized with your Microsoft 365 organization.</span></span> <span data-ttu-id="12ac2-154">Para obter mais informações, consulte[Integração de diretórios.](https://go.microsoft.com/fwlink/?LinkId=521788)</span><span class="sxs-lookup"><span data-stu-id="12ac2-154">For more information, see[Directory Integration](https://go.microsoft.com/fwlink/?LinkId=521788) .</span></span>
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a><span data-ttu-id="12ac2-155">Etapa 2: criar um arquivo CSV para um lote de migração em estágios</span><span class="sxs-lookup"><span data-stu-id="12ac2-155">Step 2: Create a CSV file for a staged migration batch</span></span>

<span data-ttu-id="12ac2-156">Depois de identificar os usuários cujas caixas de correio locais você deseja migrar para o Microsoft 365, use um arquivo de valores separados por vírgula (CSV) para criar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-156">After you identify the users whose on-premises mailboxes you want to migrate to Microsoft 365, you use a comma separated value (CSV ) file to create a migration batch.</span></span> <span data-ttu-id="12ac2-157">Cada linha no arquivo CSV, usado pelo Microsoft 365 para executar a migração, contém informações sobre uma caixa de correio local.</span><span class="sxs-lookup"><span data-stu-id="12ac2-157">Each row in the CSV file—used by Microsoft 365 to run the migration—contains information about an on-premises mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="12ac2-158">Não há um limite para o número de caixas de correio que você pode migrar para o Microsoft 365 usando uma migração em estágios.</span><span class="sxs-lookup"><span data-stu-id="12ac2-158">There isn't a limit for the number of mailboxes that you can migrate to Microsoft 365 using a staged migration.</span></span> <span data-ttu-id="12ac2-159">O arquivo CSV para um lote de migração pode conter um máximo de 2.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="12ac2-159">The CSV file for a migration batch can contain a maximum of 2,000 rows.</span></span> <span data-ttu-id="12ac2-160">Para migrar mais de 2.000 caixas de correio, crie arquivos CSV adicionais e use cada arquivo para criar um novo lote de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-160">To migrate more than 2,000 mailboxes, create additional CSV files and use each file to create a new migration batch.</span></span> 
  
 <span data-ttu-id="12ac2-161">**Atributos com suporte**</span><span class="sxs-lookup"><span data-stu-id="12ac2-161">**Supported attributes**</span></span>
  
<span data-ttu-id="12ac2-p116">O arquivo CSV para uma migração em estágios dá suporte aos três atributos a seguir. Cada linha no arquivo CSV corresponde a uma caixa de correio e deve conter um valor para cada um desses atributos.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p116">The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.</span></span>
  
|<span data-ttu-id="12ac2-164">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="12ac2-164">**Attribute**</span></span>|<span data-ttu-id="12ac2-165">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="12ac2-165">**Description**</span></span>|<span data-ttu-id="12ac2-166">**Obrigatório?**</span><span class="sxs-lookup"><span data-stu-id="12ac2-166">**Required?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12ac2-167">EmailAddress</span><span class="sxs-lookup"><span data-stu-id="12ac2-167">EmailAddress</span></span>  <br/> |<span data-ttu-id="12ac2-168">Especifica o endereço de email SMTP principal, por exemplo, laurac@contoso.com, para caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="12ac2-168">Specifies the primary SMTP email address, for example, pilarp@contoso.com, for on-premises mailboxes.</span></span>  <br/> <span data-ttu-id="12ac2-169">Use o endereço SMTP principal para caixas de correio locais e não IDs de usuário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-169">Use the primary SMTP address for on-premises mailboxes and not user IDs from the Microsoft 365.</span></span> <span data-ttu-id="12ac2-170">Por exemplo, se o domínio local se chamar contoso.com mas o domínio de email do Microsoft 365 for chamado service.contoso.com, você usará o nome de domínio contoso.com para endereços de email no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="12ac2-170">For example, if the on-premises domain is named contoso.com but the Microsoft 365 email domain is named service.contoso.com, you would use the contoso.com domain name for email addresses in the CSV file.</span></span>  <br/> |<span data-ttu-id="12ac2-171">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="12ac2-171">Required</span></span>  <br/> |
|<span data-ttu-id="12ac2-172">Senha</span><span class="sxs-lookup"><span data-stu-id="12ac2-172">Password</span></span>  <br/> |<span data-ttu-id="12ac2-173">A senha a ser definida para a nova caixa de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-173">The password to be set for the new Microsoft 365 mailbox.</span></span> <span data-ttu-id="12ac2-174">Todas as restrições de senha aplicadas à sua organização do Microsoft 365 também se aplicam às senhas incluídas no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="12ac2-174">Any password restrictions that are applied to your Microsoft 365 organization also apply to the passwords included in the CSV file.</span></span>  <br/> |<span data-ttu-id="12ac2-175">Opcional</span><span class="sxs-lookup"><span data-stu-id="12ac2-175">Optional</span></span>  <br/> |
|<span data-ttu-id="12ac2-176">ForceChangePassword</span><span class="sxs-lookup"><span data-stu-id="12ac2-176">ForceChangePassword</span></span>  <br/> |<span data-ttu-id="12ac2-177">Especifica se um usuário deve alterar a senha na primeira vez que entrar em sua nova caixa de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-177">Specifies whether a user must change the password the first time they sign in to their new Microsoft 365 mailbox.</span></span> <span data-ttu-id="12ac2-178">Use **True** ou **False** para o valor deste parâmetro.</span><span class="sxs-lookup"><span data-stu-id="12ac2-178">Use **True** or **False** for the value of this parameter.</span></span> <br/> <span data-ttu-id="12ac2-179">> [!NOTE]> Se você implementou uma solução de SSO (Logon Único) com a implantação do AD FS (Serviços de Federação do Active Directory) em sua organização local, deve usar **False** para o valor do atributo **ForceChangePassword**.</span><span class="sxs-lookup"><span data-stu-id="12ac2-179">> [!NOTE]> If you've implemented a single sign-on (SSO) solution by deploying Active Directory Federation Services (AD FS) or greater in your on-premises organization, you must use **False** for the value of the **ForceChangePassword** attribute.</span></span>          |<span data-ttu-id="12ac2-180">Opcional</span><span class="sxs-lookup"><span data-stu-id="12ac2-180">Optional</span></span>  <br/> |
   
 <span data-ttu-id="12ac2-181">**Formato de arquivo CSV**</span><span class="sxs-lookup"><span data-stu-id="12ac2-181">**CSV file format**</span></span>
  
<span data-ttu-id="12ac2-182">Veja a seguir um exemplo do formato do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="12ac2-182">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="12ac2-183">Neste exemplo, três caixas de correio locais são migradas para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-183">In this example, three on-premises mailboxes are migrated to Microsoft 365.</span></span>
  
<span data-ttu-id="12ac2-p121">A primeira linha, ou linha de cabeçalho, do arquivo CSV lista os nomes dos atributos ou campos especificados nas linhas a seguir. Cada nome de atributo é separado por uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p121">The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.</span></span>
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

<span data-ttu-id="12ac2-p122">Cada linha embaixo da linha de cabeçalho representa um usuário e fornece as informações que serão utilizadas para migrar a caixa de correio dele. Os valores de atributo em cada linha devem estar na mesma ordem que os nomes dos atributos na linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p122">Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.</span></span> 
  
<span data-ttu-id="12ac2-p123">Use qualquer editor de texto ou um aplicativo como o Excel para criar o arquivo CSV. Salve-o como um arquivo .csv ou .txt.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p123">Use any text editor, or an application like Excel , to create the CSV file. Save the file as a .csv or .txt file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="12ac2-p124">Se o arquivo CSV contiver caracteres não-ASCII ou especiais, salve-o com UTF-8 ou outra codificação Unicode. Dependendo do aplicativo, salvar o arquivo CSV com UTF-8 ou outra codificação Unicode pode ser mais fácil quando a localidade do sistema do computador corresponde ao idioma usado no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p124">If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding. Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.</span></span> 
  
### <a name="step-3-create-a-migration-endpoint"></a><span data-ttu-id="12ac2-192">Etapa 3: criar um ponto de extremidade de migração</span><span class="sxs-lookup"><span data-stu-id="12ac2-192">Step 3: Create a migration endpoint</span></span>
<span data-ttu-id="12ac2-193"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-193"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="12ac2-194">Para migrar emails com êxito, o Microsoft 365 precisa se conectar e se comunicar com o sistema de email de origem.</span><span class="sxs-lookup"><span data-stu-id="12ac2-194">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="12ac2-195">Para fazer isso, o Microsoft 365 usa um ponto de extremidade de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-195">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="12ac2-196">Para criar um ponto de extremidade de migração do Outlook em Qualquer Lugar usando o PowerShell, para migração em estágios, [conecte-se primeiro ao Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=534121)</span><span class="sxs-lookup"><span data-stu-id="12ac2-196">To create an Outlook Anywhere migration endpoint by using PowerShell, for staged migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="12ac2-197">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="12ac2-197">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="12ac2-198">Para criar um ponto de extremidade de migração do Outlook em Qualquer Lugar chamado "StagedEndpoint" no PowerShell do Exchange Online, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="12ac2-198">To create an Outlook Anywhere migration endpoint called "StagedEndpoint" in Exchange Online PowerShell, run the following commands:</span></span>
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

<span data-ttu-id="12ac2-199">Para saber mais sobre o cmdlet **New-MigrationEndpoint**, confira [New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span><span class="sxs-lookup"><span data-stu-id="12ac2-199">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
> [!NOTE]
> <span data-ttu-id="12ac2-p126">O cmdlet **New-MigrationEndpoint** pode ser usado para especificar um banco de dados do serviço a usar, utilizando a opção **-TargetDatabase**. Caso contrário, o banco de dados é atribuído de forma aleatória do site do Serviços de Federação do Active Directory (AD FS) 2.0, no qual a caixa de correio de gerenciamento está localizada.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p126">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="12ac2-202">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="12ac2-202">Verify it worked</span></span>

<span data-ttu-id="12ac2-203">No PowerShell do Exchange Online, execute o seguinte comando para exibir informações sobre o ponto de extremidade de migração "StagedEndpoint":</span><span class="sxs-lookup"><span data-stu-id="12ac2-203">In Exchange Online PowerShell, run the following command to display information about the "StagedEndpoint" migration endpoint:</span></span>
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a><span data-ttu-id="12ac2-204">Etapa 4: criar e iniciar um lote de migração em estágios</span><span class="sxs-lookup"><span data-stu-id="12ac2-204">Step 4: Create and start a stage migration batch</span></span>
<span data-ttu-id="12ac2-205"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-205"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="12ac2-p127">Você pode usar o cmdlet **New-MigrationBatch** no PowerShell do Exchange Online para criar um lote de migração de uso em uma migração de transferência. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo manualmente mais tarde usando o cmdlet **Start-MigrationBatch**. Este exemplo cria um lote de migração chamado "StagedBatch1" e utiliza o ponto de extremidade de migração criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p127">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

<span data-ttu-id="12ac2-p128">Este exemplo também cria um lote de migração chamado "StagedBatch1" e utiliza o ponto de extremidade de migração criado na etapa anterior. Como o parâmetro  _AutoStart_ não está incluído, o lote de migração deve ser iniciado manualmente no painel de migração ou usando o cmdlet **Start-MigrationBatch**. Como dito anteriormente, apenas um lote de migração de transferência pode existir de cada vez.</span><span class="sxs-lookup"><span data-stu-id="12ac2-p128">This example also creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="12ac2-213">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="12ac2-213">Verify it worked</span></span>

<span data-ttu-id="12ac2-214">Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "StagedBatch1":</span><span class="sxs-lookup"><span data-stu-id="12ac2-214">Run the following command in Exchange Online PowerShell to display information about the "StagedBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

<span data-ttu-id="12ac2-215">Você também pode verificar se o lote foi iniciado executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="12ac2-215">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

<span data-ttu-id="12ac2-216">Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="12ac2-216">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a><span data-ttu-id="12ac2-217">Etapa 5: converter caixas de correio locais em usuários habilitados para email</span><span class="sxs-lookup"><span data-stu-id="12ac2-217">Step 5: Convert on-premises mailboxes to mail-enabled users</span></span>
<span data-ttu-id="12ac2-218"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-218"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="12ac2-219">Após ter migrado com êxito um lote de caixas de correio, é necessário permitir que os usuários acessem seus emails de alguma forma.</span><span class="sxs-lookup"><span data-stu-id="12ac2-219">After you have successfully migrated a batch of mailboxes, you need some way to let users get to their mail.</span></span> <span data-ttu-id="12ac2-220">Um usuário cuja caixa de correio foi migrada agora tem uma caixa de correio local e outra no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-220">A user whose mailbox has been migrated now has both a mailbox on-premises and one in Microsoft 365.</span></span> <span data-ttu-id="12ac2-221">Os usuários que têm uma caixa de correio no Microsoft 365 deixarão de receber novos emails em suas caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="12ac2-221">Users who have a mailbox in Microsoft 365 will stop receiving new mail in their on-premises mailbox.</span></span> 
  
<span data-ttu-id="12ac2-222">Como suas migrações ainda não foram feitas, você ainda não está pronto para direcionar todos os usuários para o Microsoft 365 para seus emails.</span><span class="sxs-lookup"><span data-stu-id="12ac2-222">Because you are not done with your migrations, you are not yet ready to direct all users to Microsoft 365 for their email.</span></span> <span data-ttu-id="12ac2-223">Então o que fazer para as pessoas que possuem ambas?</span><span class="sxs-lookup"><span data-stu-id="12ac2-223">So what do you do for those people who have both?</span></span> <span data-ttu-id="12ac2-224">O que você pode fazer é alterar as caixas de correio locais que você já tiver migrado para usuários habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="12ac2-224">What you can do is change the on-premises mailboxes that you've already migrated to mail-enabled users.</span></span> <span data-ttu-id="12ac2-225">Ao alterar de uma caixa de correio para um usuário habilitado para email, você pode direcionar o usuário para o Microsoft 365 para o email em vez de ir para a caixa de correio local.</span><span class="sxs-lookup"><span data-stu-id="12ac2-225">When you change from a mailbox to a mail-enabled user, you can direct the user to Microsoft 365 for their email instead of going to their on-premises mailbox.</span></span> 
  
<span data-ttu-id="12ac2-226">Outro motivo importante para converter caixas de correio locais em usuários habilitados para email é manter endereços proxy das caixas de correio do Microsoft 365 copiando endereços de proxy para os usuários habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="12ac2-226">Another important reason to convert on-premises mailboxes to mail-enabled users is to retain proxy addresses from the Microsoft 365 mailboxes by copying proxy addresses to the mail-enabled users.</span></span> <span data-ttu-id="12ac2-227">Isso permite gerenciar usuários baseados em nuvem da sua organização local usando o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12ac2-227">This lets you manage cloud-based users from your on-premises organization by using Active Directory.</span></span> <span data-ttu-id="12ac2-228">Além disso, se você decidir descomissionar sua organização local do Exchange Server depois que todas as caixas de correio são migradas para o Microsoft 365, os endereços de proxy que você copiou para os usuários habilitados para email permanecerão em seu Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="12ac2-228">Also, if you decide to decommission your on-premises Exchange Server organization after all mailboxes are migrated to Microsoft 365, the proxy addresses you've copied to the mail-enabled users will remain in your on-premises Active Directory.</span></span>
    
### <a name="step-6-delete-a-staged-migration-batch"></a><span data-ttu-id="12ac2-229">Etapa 6: excluir um lote de migração em estágios</span><span class="sxs-lookup"><span data-stu-id="12ac2-229">Step 6: Delete a staged migration batch</span></span>
<span data-ttu-id="12ac2-230"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-230"><a name="BK_Endpoint"> </a></span></span>

 <span data-ttu-id="12ac2-231">Depois que todas as caixas de correio em um lote de migração foram migradas com êxito e você tiver convertido as caixas de correio locais no lote em usuários habilitados para email, você estará pronto para excluir um lote de migração em estágios.</span><span class="sxs-lookup"><span data-stu-id="12ac2-231">After all mailboxes in a migration batch have been successfully migrated, and you've converted the on-premises mailboxes in the batch to mail-enabled users, you're ready to delete a staged migration batch.</span></span> <span data-ttu-id="12ac2-232">Verifique se o email está sendo encaminhado para as caixas de correio do Microsoft 365 no lote de migração.</span><span class="sxs-lookup"><span data-stu-id="12ac2-232">Be sure to verify that mail is being forwarded to the Microsoft 365 mailboxes in the migration batch.</span></span> <span data-ttu-id="12ac2-233">Ao excluir um lote de migração em estágios, o serviço de migração limpa todos os registros relacionados ao lote e o exclui.</span><span class="sxs-lookup"><span data-stu-id="12ac2-233">When you delete a staged migration batch, the migration service cleans up any records related to the migration batch and deletes the migration batch.</span></span>
  
<span data-ttu-id="12ac2-234">Para excluir o lote de migração "StagedBatch1" no PowerShell do Exchange Online, execute o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="12ac2-234">To delete the "StagedBatch1" migration batch in Exchange Online PowerShell, run the following command.</span></span>
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

<span data-ttu-id="12ac2-235">Para saber mais sobre o cmdlet **Remove-MigrationBatch**, confira [Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span><span class="sxs-lookup"><span data-stu-id="12ac2-235">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="12ac2-236">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="12ac2-236">Verify it worked</span></span>

<span data-ttu-id="12ac2-237">Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="12ac2-237">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch StagedBatch1
```

<span data-ttu-id="12ac2-238">O comando retornará o lote de migração com um status de **Removing** ou retornará um erro afirmando que o lote de migração não foi encontrado, confirmando que o lote foi excluído.</span><span class="sxs-lookup"><span data-stu-id="12ac2-238">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="12ac2-239">Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="12ac2-239">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a><span data-ttu-id="12ac2-240">Etapa7: atribuir licenças a usuários do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12ac2-240">Step7: Assign licenses to Microsoft 365 users</span></span>
<span data-ttu-id="12ac2-241"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-241"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="12ac2-242">Ative as contas de usuário do Microsoft 365 para as contas migradas atribuindo licenças.</span><span class="sxs-lookup"><span data-stu-id="12ac2-242">Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.</span></span> <span data-ttu-id="12ac2-243">Se você não atribuir uma licença, a caixa de correio será desabilitada quando terminar o período de cortesia (30 dias).</span><span class="sxs-lookup"><span data-stu-id="12ac2-243">If you don't assign a license, the mailbox is disabled when the grace period (30 days) ends.</span></span> <span data-ttu-id="12ac2-244">Para atribuir uma licença no centro de administração do Microsoft 365, confira Atribuir ou [desatribuição de licenças.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="12ac2-244">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="12ac2-245">Etapa 8: concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="12ac2-245">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="12ac2-246"><a name="BK_Postmigration"> </a></span><span class="sxs-lookup"><span data-stu-id="12ac2-246"><a name="BK_Postmigration"> </a></span></span>

- <span data-ttu-id="12ac2-247">**Crie um registro DNS de Descoberta Automática para que os usuários possam acessar facilmente suas caixas de correio.**</span><span class="sxs-lookup"><span data-stu-id="12ac2-247">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="12ac2-248">Depois que todas as caixas de correio locais são migradas para o Microsoft 365, você pode configurar um registro DNS de Descoberta Automática para sua organização do Microsoft 365 para permitir que os usuários se conectem facilmente às suas novas caixas de correio do Microsoft 365 com o Outlook e clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="12ac2-248">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="12ac2-249">Esse novo registro DNS de Descoberta Automática deve usar o mesmo namespace que você está usando para sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12ac2-249">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="12ac2-250">Por exemplo, se seu namespace baseado na nuvem for cloud.contoso.com, o registro DNS de Descoberta Automática que você precisa criar será autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="12ac2-250">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="12ac2-251">O Microsoft 365 usa um registro CNAME para implementar o serviço descoberta automática para o Outlook e clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="12ac2-251">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="12ac2-252">O registro CNAME de Descoberta Automática deve conter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="12ac2-252">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="12ac2-253">**Alias:** descoberta automática</span><span class="sxs-lookup"><span data-stu-id="12ac2-253">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="12ac2-254">**Destino:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="12ac2-254">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="12ac2-255">Para obter mais informações, [consulte Adicionar registros DNS para conectar seu domínio.](https://go.microsoft.com/fwlink/p/?LinkId=535028)</span><span class="sxs-lookup"><span data-stu-id="12ac2-255">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="12ac2-256">**Encerrar servidores locais do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="12ac2-256">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="12ac2-257">Depois de verificar se todos os emails estão sendo roteados diretamente para as caixas de correio do Microsoft 365 e não precisar mais manter sua organização de email local ou não planejar a implementação de uma solução SSO, você poderá desinstalar o Exchange de seus servidores e remover sua organização local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="12ac2-257">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing an SSO solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="12ac2-258">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12ac2-258">For more information, see the following:</span></span>
    
  - [<span data-ttu-id="12ac2-259">Modificar ou remover o Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="12ac2-259">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [<span data-ttu-id="12ac2-260">Como remover uma Organização do Exchange 2007</span><span class="sxs-lookup"><span data-stu-id="12ac2-260">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [<span data-ttu-id="12ac2-261">Como desinstalar o Exchange Server 2003</span><span class="sxs-lookup"><span data-stu-id="12ac2-261">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)
    

