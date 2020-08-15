---
title: Usar o PowerShell para realizar uma migração IMAP para o Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Saiba como usar o PowerShell para executar uma migração IMAP (Internet Mail Access Protocol) para o Microsoft 365.
ms.openlocfilehash: 6eb422455d0bdf31fa1859bd0231b68e5568748c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687338"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="9ff8c-103">Usar o PowerShell para realizar uma migração IMAP para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ff8c-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="9ff8c-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9ff8c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9ff8c-105">Como parte do processo de implantação do Microsoft 365, você pode optar por migrar o conteúdo das caixas de correio de usuário de um serviço de email IMAP (Internet Mail Access Protocol) para a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="9ff8c-106">Este artigo apresenta as tarefas para uma migração IMAP de email usando o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9ff8c-107">Você também pode usar o Centro de administração do Exchange para executar a migração IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="9ff8c-108">Consulte [migrar suas caixas de correio IMAP](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ff8c-109">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="9ff8c-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="9ff8c-110">Tempo estimado para a conclusão da tarefa: 2-5 minutos para criar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="9ff8c-111">Depois que o lote de migração é iniciado, a duração da migração irá variar com base no número de caixas de correio no lote, no tamanho de cada caixa de correio e na sua capacidade de rede disponível.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="9ff8c-112">Para obter informações sobre outros fatores que afetam quanto tempo leva para migrar caixas de correio para a Microsoft 365, consulte [desempenho de migração](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="9ff8c-p104">Para executar esses procedimentos, você precisa receber permissões. Para saber quais permissões são necessárias, confira a entrada "Migração" em uma tabela no tópico [Permissões de destinatários](https://go.microsoft.com/fwlink/p/?LinkId=534105).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="9ff8c-p105">Para usar os cmdlets do PowerShell do Exchange Online, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="9ff8c-117">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="9ff8c-118">As seguintes restrições se aplicam às migrações IMAP:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="9ff8c-p106">Apenas itens na caixa de entrada de um usuário ou outras pastas de email pode ser migradas. Não é possível migrar contatos, itens de calendário ou tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p106">Only items in a user's inbox or other mail folders can be migrated. You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="9ff8c-121">No máximo 500.000 itens podem ser migrados de uma caixa de correio de usuário.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="9ff8c-122">O tamanho máximo da mensagem que pode ser migrada é de 35 MB.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="9ff8c-123">Etapas da migração</span><span class="sxs-lookup"><span data-stu-id="9ff8c-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="9ff8c-124">Etapa 1: Preparar uma migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="9ff8c-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="9ff8c-126">**Se você tiver um domínio para sua organização IMAP, adicione-o como um domínio aceito de sua organização do Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="9ff8c-127">Se você deseja usar o mesmo domínio que você já possui para suas caixas de correio do Microsoft 365, primeiro é necessário adicioná-lo como um domínio aceito para a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="9ff8c-128">Depois de adicioná-lo, você pode criar seus usuários no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="9ff8c-129">Para obter mais informações, consulte[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="9ff8c-130">**Adicione cada usuário ao Microsoft 365 para que eles tenham uma caixa de correio.**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="9ff8c-131">Para obter instruções, consulte[Adicionar usuários ao Microsoft 365 for Business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="9ff8c-p109">**Obter o FQDN do servidor IMAP**. Você precisa fornecer o FQDN (nome de domínio totalmente qualificado) (também chamado de nome completo do computador) do servidor IMAP do qual você migrará dados de caixa de correio ao criar um ponto de extremidade de migração IMAP. Use um cliente IMAP ou o comando PING para verificar se você pode usar o FQDN para se comunicar com o servidor IMAP pela Internet.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p109">**Obtain the FQDN of the IMAP server**. You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint. Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="9ff8c-p110">**Configurar o firewall para permitir conexões IMAP**. Você pode precisar abrir portas no firewall da organização que hospeda o servidor IMAP para que o tráfego de rede originário do data center da Microsoft durante a migração tenha permissão para entrar na organização que hospeda o servidor IMAP. Para obter uma lista de endereços IP usada pelos datacenters do Microsoft, confira [Intervalos de endereços IP e URLs do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p110">**Configure the firewall to allow IMAP connections**. You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server. For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="9ff8c-p111">**Atribuir ao administrador permissões de conta para acessar caixas de correio em sua organização IMAP** Se você usar credenciais de administrador no arquivo CSV, a conta usada deverá ter as permissões necessárias para acessar as caixas de correio locais. As permissões necessárias para acessar as caixas de correio do usuário são determinadas pelo servidor IMAP específico.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p111">**Assign the administrator account permissions to access mailboxes in your IMAP organization**. If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes. The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="9ff8c-p112">**Para usar os cmdlets do PowerShell do Exchange Online**, você precisa entrar e importar os cmdlets para sua sessão local do Windows PowerShell. Confira [Conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=534121) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p112">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="9ff8c-143">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="9ff8c-p113">**Verifique se você pode se conectar ao servidor IMAP**. Execute o seguinte comando no PowerShell do Exchange Online para testar as configurações de conexão ao servidor IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p113">**Verify that you can connect to your IMAP server**. Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="9ff8c-146">Para o valor do parâmetro **Port**, é normal usar 143 para conexões descriptografadas ou TLS (Transport Layer Security) e usar 993 para conexões SSL.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="9ff8c-147">Etapa 2: Criar um arquivo CSV para um lote de migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="9ff8c-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="9ff8c-p114">Identifique o grupo de usuários cujas caixas de correio você deseja migrar em um lote de migração IMAP. Cada linha no arquivo CSV contém as informações necessárias para se conectar a uma caixa de correio no sistema de mensagens IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p114">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch. Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="9ff8c-151">Veja a seguir os atributos necessários para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="9ff8c-152">**EmailAddress** especifica a ID de usuário da caixa de correio do Microsoft 365 do usuário.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="9ff8c-153">**UserName** especifica o nome de logon da conta a ser usada para acessar a caixa de correio no servidor IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="9ff8c-154">**Password** especifica a senha para a conta na coluna **UserName**.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="9ff8c-p115">Aqui está um exemplo do formato do arquivo CSV. Neste exemplo, três caixas de correio são migradas:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p115">Here's an example of the format for the CSV file. In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="9ff8c-157">Para o atributo **UserName**, além do nome de usuário, você pode usar as credenciais de uma conta que recebeu as permissões necessárias para acessar caixas de correio no servidor IMAP. A seguir estão alguns dos formatos específicos usados para alguns dos servidores IMAP:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="9ff8c-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="9ff8c-p116">Se você estiver migrando email a partir da implementação IMAP do Microsoft Exchange, use o formato **Domain/Admin_UserName/User_UserName** para o atributo **UserName** no arquivo CSV. Digamos que você esteja migrando emails do Exchange para Pedro Gonçalves, Brenda Fernandes e Henrique Cunha. Você tem uma conta de administrador de email, em que o nome de usuário é **mailadmin** e a senha é **P@ssw0rd**. Esta seria a aparência do seu arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p116">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file. Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon. You have a mail administrator account, where the user name is **mailadmin** and the password is **P@ssw0rd**. Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="9ff8c-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-163">**Dovecot:**</span></span>
  
<span data-ttu-id="9ff8c-p117">Para servidores IMAP que dão suporte a SASL (Simple Authentication and Security Layer), como um servidor Dovecot IMAP, use o formato **Usuário_NomeDeUsuário\*Admin_NomeDeUsuário**, em que o asterisco (\*) é um caractere separador configurável. Suponha que você esteja migrando emails desses mesmos usuários de um servidor Dovecot IMAP usando as credenciais de administrador **mailadmin** e **P@ssw0rd**. Esta seria a aparência do seu arquivo CSV:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p117">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character. Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P@ssw0rd**. Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="9ff8c-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="9ff8c-p118">Se você estiver migrando emails a partir do Mirapoint Message Server, use o formato **#user@domain#Admin_UserName#** para as credenciais de administrador. Para migrar emails do Mirapoint usando as credenciais de administrador **mailadmin** e **P@ssw0rd**, seu arquivo CSV teria a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p118">If you're migrating email from Mirapoint Message Server, use the format **#user@domain#Admin_UserName#** for the administrator credentials. To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="9ff8c-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="9ff8c-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="9ff8c-171">Alguns sistemas de email de origem, como Courier IMAP, não oferecem suporte ao uso de credenciais de administrador de caixa de correio para migrar caixas de correio para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="9ff8c-172">Em vez disso, você pode configurar seu sistema de email de origem para usar pastas compartilhadas virtuais.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="9ff8c-173">Usando pastas compartilhadas virtuais, você pode usar as credenciais de administrador de caixa de correio para acessar caixas de correio do usuário no sistema de email de origem.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="9ff8c-174">Para saber mais sobre como configurar as pastas virtuais compartilhadas do Courier IMAP, confira [Pastas Compartilhadas](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="9ff8c-p120">Para migrar as caixas de correio depois de configurar as pastas compartilhadas virtuais em seu sistema de email de origem, você deve incluir o atributo **UserRoot** opcional no arquivo de migração. Esse atributo especifica o local da caixa de correio de cada usuário na estrutura de pastas compartilhadas virtuais do sistema de email de origem. Por exemplo, o caminho para a caixa de correio de Pedro é /users/pedro.goncalves.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p120">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file. This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system. For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="9ff8c-178">Aqui está um exemplo de um arquivo CSV que contém o atributo **UserRoot**:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="9ff8c-179">Etapa 3: Criar um ponto de extremidade de migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="9ff8c-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="9ff8c-181">Para migrar os emails com êxito, o Microsoft 365 precisa se conectar ao sistema de email de origem e se comunicar com ele.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="9ff8c-182">Para fazer isso, a Microsoft 365 usa um ponto de extremidade de migração.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="9ff8c-183">O ponto de extremidade de migração também define o número de caixas de correio para migração simultânea e o número de caixas de correio para sincronização simultânea durante a sincronização incremental, que ocorre uma vez a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="9ff8c-184">Para criar um ponto de extremidade de migração para a migração IMAP, primeiro [Conecte-se ao Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="9ff8c-185">Para obter uma lista completa dos comandos de migração, confira [Cmdlets de movimentação e migração](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="9ff8c-186">Para criar o ponto de extremidade de migração IMAP chamado "IMAPEndpoint" no PowerShell do Exchange Online, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="9ff8c-p122">Você também pode adicionar parâmetros para especificar migrações simultâneas, migrações simultâneas incrementais e a porta a ser usada. O comando a seguir do PowerShell do Exchange Online cria um ponto de extremidade de migração IMAP chamado "IMAPEndpoint" que dá suporte a 50 migrações simultâneas e até 25 sincronizações incrementais simultâneas. Também configura o ponto de extremidade para usar a porta 143 para criptografia TLS.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p122">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use. The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations. It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="9ff8c-190">Para saber mais sobre o cmdlet **New-MigrationEndpoint**, confira[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="9ff8c-191">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="9ff8c-191">Verify it worked</span></span>

<span data-ttu-id="9ff8c-192">Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="9ff8c-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="9ff8c-193">Etapa 4: Criar e iniciar um lote de migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="9ff8c-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="9ff8c-p123">Você pode usar o cmdlet [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) para criar um lote de migração para uma migração IMAP. É possível criar um lote de migração e iniciá-lo automaticamente incluindo o parâmetro _AutoStart_. Como alternativa, você pode criar o lote de migração e iniciá-lo mais tarde usando o cmdlet [Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p123">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="9ff8c-198">O seguinte comando do PowerShell do Exchange Online iniciará automaticamente o lote de migração chamado "IMAPBatch1" usando o ponto de extremidade IMAP chamado "IMAPEndpoint":</span><span class="sxs-lookup"><span data-stu-id="9ff8c-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="9ff8c-199">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="9ff8c-199">Verify it worked</span></span>

<span data-ttu-id="9ff8c-200">Execute o cmdlet [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) para exibir informações sobre o "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="9ff8c-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="9ff8c-201">Você também pode verificar se o lote foi iniciado executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="9ff8c-202">Etapa 5: encaminhar seu email para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ff8c-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="9ff8c-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="9ff8c-204">Os sistemas de email usam um registro DNS chamado registro MX para descobrir onde entregar emails.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="9ff8c-205">Durante o processo de migração de email, seu registro MX estava apontando para o sistema de email de origem.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="9ff8c-206">Agora que a migração de email para o Microsoft 365 está concluída, é hora de apontar o seu registro MX no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="9ff8c-207">Isso ajuda a garantir que o email seja entregue às suas caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="9ff8c-208">Movendo o registro MX, você também poderá desativar seu sistema de email antigo quando estiver pronto.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="9ff8c-209">Em muitos provedores DNS, existem instruções específicas para alterar o seu registro MX.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="9ff8c-210">Se o seu provedor de DNS não estiver incluído, ou se você quiser ter uma noção das orientações gerais, [as instruções gerais de registro MX ](https://go.microsoft.com/fwlink/?LinkId=397449) também são fornecidas.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="9ff8c-p126">Pode levar até 72 horas para que os sistemas de email de seus clientes e parceiros reconheçam o registro MX alterado. Aguarde pelo menos 72 horas antes de prosseguir para a próxima tarefa: Etapa 6: Excluir o lote de migração IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-p126">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record. Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="9ff8c-213">Etapa 6: Excluir o lote de migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="9ff8c-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="9ff8c-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="9ff8c-215">Depois de alterar o registro MX e verificar se todos os emails estão sendo roteados para as caixas de correio do Microsoft 365, notifique os usuários de que seus emails estão indo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="9ff8c-216">Depois disso, você pode excluir o lote de migração IMAP.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="9ff8c-217">Antes de excluir o lote de migração, verifique os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="9ff8c-218">Todos os usuários estão usando caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="9ff8c-219">Depois que o lote é excluído, os emails enviados para caixas de correio no servidor Exchange local não são copiados para as caixas de correio do Microsoft 365 correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="9ff8c-220">As caixas de correio do Microsoft 365 foram sincronizadas pelo menos uma vez depois que o email começou a ser enviado diretamente a eles.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="9ff8c-221">Para fazer isso, certifique-se de que o valor na caixa de hora da última sincronização do lote de migração seja mais recente do que quando o email começou a ser roteado diretamente para as caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="9ff8c-222">Para excluir o lote de migração "IMAPBatch1" do PowerShell do Exchange Online, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9ff8c-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="9ff8c-223">Para saber mais sobre o cmdlet **Remove-MigrationBatch**, confira[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="9ff8c-224">Verifique se funcionou</span><span class="sxs-lookup"><span data-stu-id="9ff8c-224">Verify it worked</span></span>

<span data-ttu-id="9ff8c-225">Execute o seguinte comando no PowerShell do Exchange Online para exibir informações sobre o "IMAPBatch1":</span><span class="sxs-lookup"><span data-stu-id="9ff8c-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="9ff8c-226">O comando retornará o lote de migração com um status de **Removing** ou retornará um erro afirmando que o lote de migração não foi encontrado, confirmando que o lote foi excluído.</span><span class="sxs-lookup"><span data-stu-id="9ff8c-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="9ff8c-227">Para saber mais sobre o cmdlet **Get-MigrationBatch**, confira[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span><span class="sxs-lookup"><span data-stu-id="9ff8c-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ff8c-228">Confira também</span><span class="sxs-lookup"><span data-stu-id="9ff8c-228">See also</span></span>

[<span data-ttu-id="9ff8c-229">Solução de problemas de migração IMAP</span><span class="sxs-lookup"><span data-stu-id="9ff8c-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

