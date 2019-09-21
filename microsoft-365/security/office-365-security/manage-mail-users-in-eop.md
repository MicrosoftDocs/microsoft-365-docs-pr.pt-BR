---
title: Gerenciar usuários de email no EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: A definição de usuários de email é uma parte importante do gerenciamento do serviço Exchange Online Protection (EOP).
ms.openlocfilehash: d445bceb9e796c11c40ab778ed3d056df0f4c44b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073721"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="b148f-103">Gerenciar usuários de email no EOP</span><span class="sxs-lookup"><span data-stu-id="b148f-103">Manage mail users in EOP</span></span>

<span data-ttu-id="b148f-p101">A definição de usuários de email é uma parte importante do gerenciamento do serviço Exchange Online Protection (EOP). Existem várias maneiras possíveis de gerenciar usuários no EOP:</span><span class="sxs-lookup"><span data-stu-id="b148f-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="b148f-106">Utilizar a sincronização de diretórios para gerenciar usuários de email: se sua empresa possui contas de usuário existentes em um ambiente do Active Directory local, é possível sincronizar essas contas com o Azure Active Directory (AD), onde uma cópia dessas contas fica armazenada na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b148f-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="b148f-107">Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, será possível exibir esses usuários no painel **Destinatários** do Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="b148f-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="b148f-108">Recomendamos usar a sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="b148f-108">Using directory synchronization is recommended.</span></span> 

- <span data-ttu-id="b148f-109">Usar o EAC para gerenciar usuários de email: adicione e gerencie usuários de email diretamente no EAC.</span><span class="sxs-lookup"><span data-stu-id="b148f-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="b148f-110">Esse é o modo mais fácil de adicionar usuários de email e é útil para adicionar um usuário por vez.</span><span class="sxs-lookup"><span data-stu-id="b148f-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="b148f-111">Usar o Windows PowerShell remoto para gerenciar usuários de email: adicione e gerencie usuários de email executando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="b148f-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="b148f-112">Este método é útil para adicionar vários registros e criar scripts.</span><span class="sxs-lookup"><span data-stu-id="b148f-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="b148f-113">Você pode adicionar usuários no centro de administração do Microsoft 365, no entanto, esses usuários não podem ser usados como destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="b148f-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b148f-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b148f-114">Before you begin</span></span>

- <span data-ttu-id="b148f-115">Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b148f-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b148f-p105">Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Usuários, contatos e grupos de funções" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b148f-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="b148f-118">Lembre-se de que ao criar usuários de email usando os cmdlets do PowerShell do Exchange Online Protection, você pode encontrar limitação.</span><span class="sxs-lookup"><span data-stu-id="b148f-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="b148f-119">Os comandos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="b148f-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="b148f-120">Para saber como usar o Windows PowerShell para se conectar à proteção do Exchange Online, confira [conectar-se ao PowerShell do Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span><span class="sxs-lookup"><span data-stu-id="b148f-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>

- <span data-ttu-id="b148f-121">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b148f-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b148f-122">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="b148f-122">Having problems?</span></span> <span data-ttu-id="b148f-123">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="b148f-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="b148f-124">Utilizar a sincronização de diretórios para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="b148f-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="b148f-125">Esta seção oferece informações sobre o gerenciamento de usuários de email usando a sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="b148f-125">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b148f-126">Se você usar a sincronização de diretório para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="b148f-126">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="b148f-127">Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="b148f-127">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> <br/><br/> <span data-ttu-id="b148f-128">A sincronização de diretórios é recomendada para uso com os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="b148f-128">Directory synchronization is recommended for use with the following features:</span></span> <br/><br/><span data-ttu-id="b148f-129">• **Remetente seguro do Outlook e listas de remetentes bloqueados**: quando sincronizadas com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço.</span><span class="sxs-lookup"><span data-stu-id="b148f-129">• **Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="b148f-130">Isso permite que os usuários gerenciem suas próprias listas de remetentes confiáveis e bloqueados por usuário ou por domínio.</span><span class="sxs-lookup"><span data-stu-id="b148f-130">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span> <br/><br/><span data-ttu-id="b148f-131">• **Bloqueio de borda baseado em diretório (DBEB)**: para obter mais informações sobre o DBEB, confira [usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span><span class="sxs-lookup"><span data-stu-id="b148f-131">• **Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span> <br/><br/><span data-ttu-id="b148f-132">• **Quarentena de spam do usuário final**: para acessar a quarentena de spam do usuário final, os usuários finais devem ter uma ID de usuário e uma senha válida do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b148f-132">• **End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="b148f-133">Os clientes do EOP que estão protegendo caixas de correio locais devem ser usuários de email válidos.</span><span class="sxs-lookup"><span data-stu-id="b148f-133">EOP customers protecting on-premises mailboxes must be valid email users.</span></span> <br/><br/><span data-ttu-id="b148f-134">• **Regras de fluxo de emails**: quando você usa a sincronização de diretório, os usuários e grupos existentes do Active Directory são carregados automaticamente para a nuvem e você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) que direcionam usuários específicos e/ou grupos sem precisar adicioná-los manualmente por meio do PowerShell de proteção do Exchange Online ou do Eat.</span><span class="sxs-lookup"><span data-stu-id="b148f-134">• **Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="b148f-135">Observe que os [grupos dinâmicos de distribuição](https://go.microsoft.com/fwlink/?LinkId=507569) não podem ser sincronizados através da sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="b148f-135">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span>
  
<span data-ttu-id="b148f-136">Obtenha as permissões necessárias e prepare-se para a sincronização de diretórios, como descrito em [Preparar a sincronização de diretórios](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span><span class="sxs-lookup"><span data-stu-id="b148f-136">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="b148f-137">Para sincronizar os diretórios de usuário com o Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="b148f-137">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="b148f-138">Para sincronizar os usuários com o Azure Active Directory (AAD), primeiro você deve **ativar a sincronização de diretórios**, conforme descrito em [Activate Directory Synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span><span class="sxs-lookup"><span data-stu-id="b148f-138">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>

<span data-ttu-id="b148f-139">A seguir, a instalação e a configuração de um computador local para executar o AAD Connect (se você ainda não tiver uma coisa que vale a pena verificar antes do tempo).</span><span class="sxs-lookup"><span data-stu-id="b148f-139">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="b148f-140">A [configuração do AAD Connect, o tópico Express Way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) mostra como configurar e sincronizar suas contas no local para o Azure AD com o AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="b148f-140">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="b148f-141">Mas antes de fazer isso, certifique [-se de que você atende aos pré-requisitos](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)e [escolha o tipo de instalação](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="b148f-141">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="b148f-142">O link anterior é para um pequeno artigo para instalações expressas.</span><span class="sxs-lookup"><span data-stu-id="b148f-142">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="b148f-143">Você também pode encontrar artigos sobre [instalações personalizadas](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)ou [autenticação de passagem](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) , se for necessário.</span><span class="sxs-lookup"><span data-stu-id="b148f-143">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b148f-p114">Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.</span><span class="sxs-lookup"><span data-stu-id="b148f-p114">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="b148f-147">Após configurar sua sincronização, verifique se o EOP está sincronizando corretamente.</span><span class="sxs-lookup"><span data-stu-id="b148f-147">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="b148f-148">No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="b148f-148">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="b148f-149">Usar o EAC para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="b148f-149">Use the EAC to manage mail users</span></span>

<span data-ttu-id="b148f-150">Esta seção oferece informações sobre a adição e o gerenciamento de usuários de email diretamente no EAC.</span><span class="sxs-lookup"><span data-stu-id="b148f-150">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="b148f-151">Usar o Eat para adicionar um usuário de email</span><span class="sxs-lookup"><span data-stu-id="b148f-151">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="b148f-152">Crie um usuário de email em **Destinatários** \> **Contatos** no EAC e clique em **Novo +**.</span><span class="sxs-lookup"><span data-stu-id="b148f-152">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="b148f-153">Na página **Novo usuário de email**, insira as informações do usuário, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b148f-153">On the **New mail user** page, enter the user's information, including the following:</span></span> 

   ****

   |<span data-ttu-id="b148f-154">**Propriedade do usuário de email**</span><span class="sxs-lookup"><span data-stu-id="b148f-154">**Mail user property**</span></span>|<span data-ttu-id="b148f-155">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b148f-155">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b148f-156">**Nome**, **Iniciais** e **Sobrenome**</span><span class="sxs-lookup"><span data-stu-id="b148f-156">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="b148f-157">Digite o nome completo do usuário nas caixas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="b148f-157">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="b148f-158">**Nome para exibição**</span><span class="sxs-lookup"><span data-stu-id="b148f-158">**Display name**</span></span>|<span data-ttu-id="b148f-p116">Digite um nome, usando até 64 caracteres. Por padrão, essa caixa mostra os nomes nas caixas **Nome**, **Iniciais** e **Sobrenome**, se houver. É necessário fornecer o nome para exibição.  </span><span class="sxs-lookup"><span data-stu-id="b148f-p116">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.</span></span>|
   |<span data-ttu-id="b148f-162">**Alias**</span><span class="sxs-lookup"><span data-stu-id="b148f-162">**Alias**</span></span>|<span data-ttu-id="b148f-p117">Digite um alias exclusivo, usando até 64 caracteres para o usuário. O alias é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="b148f-p117">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>|
   |<span data-ttu-id="b148f-165">**Endereço de email externo**</span><span class="sxs-lookup"><span data-stu-id="b148f-165">**External email address**</span></span>|<span data-ttu-id="b148f-166">Digite o endereço de email externo do usuário.</span><span class="sxs-lookup"><span data-stu-id="b148f-166">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="b148f-167">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="b148f-167">**User id**</span></span>|<span data-ttu-id="b148f-p118">Digite o nome que o usuário de email usará para entrar no serviço. O nome de entrada do usuário consiste em um nome de usuário à esquerda do símbolo (@) e um sufixo à direita. Geralmente, o sufixo é o nome de domínio no qual a conta de usuário reside.</span><span class="sxs-lookup"><span data-stu-id="b148f-p118">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="b148f-171">**Nova senha**</span><span class="sxs-lookup"><span data-stu-id="b148f-171">**New password**</span></span>|<span data-ttu-id="b148f-p119">Digite a senha que o usuário de email usará para entrar no serviço. Verifique se a senha fornecida é compatível com os requisitos de comprimento, complexidade e histórico do domínio no qual você está criando a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="b148f-p119">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="b148f-174">**Confirmação da senha**</span><span class="sxs-lookup"><span data-stu-id="b148f-174">**Confirm password**</span></span>|<span data-ttu-id="b148f-175">Digite novamente a senha para confirmá-la.</span><span class="sxs-lookup"><span data-stu-id="b148f-175">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="b148f-p120">Clique em **Salvar** para criar o novo usuário de email. O novo usuário deve aparecer na lista de usuários.</span><span class="sxs-lookup"><span data-stu-id="b148f-p120">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="b148f-178">Usar o Eat para editar ou remover um usuário de email</span><span class="sxs-lookup"><span data-stu-id="b148f-178">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="b148f-179">No EAC, acesse **Destinatários** \> **Contatos**.</span><span class="sxs-lookup"><span data-stu-id="b148f-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="b148f-180">Na lista de usuários, clique no usuário que você deseja exibir ou alterar e selecione **Editar** ![ícone](../media/ITPro-EAC-EditIcon.gif) de edição para atualizar as configurações do usuário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b148f-180">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="b148f-181">Você pode alterar o nome, o alias ou as informações de contato do usuário, e pode registrar informações detalhadas sobre a função do usuário na organização.</span><span class="sxs-lookup"><span data-stu-id="b148f-181">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="b148f-182">Você também pode selecionar um usuário e, em \*\*\*\* ![seguida, escolher](../media/ITPro-EAC-RemoveIcon.gif) Remover ícone para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="b148f-182">You can also select a user and then choose **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="b148f-183">Usar o Exchange Online Protection PowerShell para gerenciar usuários de email</span><span class="sxs-lookup"><span data-stu-id="b148f-183">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="b148f-184">Esta seção fornece informações sobre como adicionar e gerenciar usuários de email usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="b148f-184">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="b148f-185">Usar o EOP PowerShell para adicionar um usuário de email</span><span class="sxs-lookup"><span data-stu-id="b148f-185">Use EOP PowerShell to add a mail user</span></span>
  
<span data-ttu-id="b148f-186">O exemplo usa o cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) para criar uma conta de usuário habilitado para email em nome de Diogo Martins com os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b148f-186">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>
  
- <span data-ttu-id="b148f-187">O primeiro nome é Diogo e o sobrenome é Martins.</span><span class="sxs-lookup"><span data-stu-id="b148f-187">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="b148f-188">O nome é Diogo e o nome de exibição é Diogo Martins.</span><span class="sxs-lookup"><span data-stu-id="b148f-188">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="b148f-189">O alias é diogom.</span><span class="sxs-lookup"><span data-stu-id="b148f-189">The alias is jeffreyz.</span></span>

- <span data-ttu-id="b148f-190">O endereço de email externo é diogom@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="b148f-190">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="b148f-191">O nome de usuário do Office 365 é diogom@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b148f-191">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="b148f-192">A senha é Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="b148f-192">The password is Pa$$word1.</span></span>

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="b148f-193">Para verificar se isso funcionou, execute o seguinte comando para exibir informações sobre o novo usuário de email Jeffrey Martins:</span><span class="sxs-lookup"><span data-stu-id="b148f-193">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="b148f-194">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="b148f-194">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="b148f-195">Usar o EOP PowerShell para editar as propriedades de um usuário de email</span><span class="sxs-lookup"><span data-stu-id="b148f-195">Use EOP PowerShell to edit the properties of a mail user</span></span>
  
<span data-ttu-id="b148f-196">Use os cmdlets [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) para visualizar ou alterar propriedades para usuários de email.</span><span class="sxs-lookup"><span data-stu-id="b148f-196">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>
  
<span data-ttu-id="b148f-197">Este exemplo define o endereço de email externo de Brenda Fernandes.</span><span class="sxs-lookup"><span data-stu-id="b148f-197">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="b148f-198">Este exemplo define a propriedade Company de todos os usuários de email como Contoso.</span><span class="sxs-lookup"><span data-stu-id="b148f-198">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
<span data-ttu-id="b148f-199">Para verificar se isso funcionou, use o cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para verificar as alterações.</span><span class="sxs-lookup"><span data-stu-id="b148f-199">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="b148f-200">(Observe que você pode visualizar várias propriedades para vários contatos de email.)</span><span class="sxs-lookup"><span data-stu-id="b148f-200">(Note that you can view multiple properties for multiple mail contacts.)</span></span>
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="b148f-201">No exemplo anterior em que a propriedade Company foi definida como Contoso para todos os usuários de email, execute o comando a seguir para verificar as alterações:</span><span class="sxs-lookup"><span data-stu-id="b148f-201">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="b148f-202">Esse cmdlet usa um método de processamento em lotes que resulta em um atraso na propagação de alguns minutos até que os resultados do cmdlet estejam visíveis.</span><span class="sxs-lookup"><span data-stu-id="b148f-202">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="b148f-203">Usar o EOP PowerShell para remover um usuário de email</span><span class="sxs-lookup"><span data-stu-id="b148f-203">Use EOP PowerShell to remove a mail user</span></span>
  
<span data-ttu-id="b148f-204">Este exemplo usa o cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) para excluir o usuário Diogo Martins:</span><span class="sxs-lookup"><span data-stu-id="b148f-204">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="b148f-205">**Para verificar se funcionou**</span><span class="sxs-lookup"><span data-stu-id="b148f-205">**To verify that this worked**</span></span>
  
<span data-ttu-id="b148f-206">Para verificar se isso funcionou, execute o cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para verificar se o usuário de email não existe mais.</span><span class="sxs-lookup"><span data-stu-id="b148f-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>
  
```Powershell
Get-Recipient Jeffrey | Format-List
```
