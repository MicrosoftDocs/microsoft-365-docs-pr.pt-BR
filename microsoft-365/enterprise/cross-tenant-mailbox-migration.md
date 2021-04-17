---
title: Migração de caixa de correio entre locatários
description: Como mover caixas de correio entre os locatários do Microsoft 365 ou do Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: d52a0ca4a2dc9b799a32f70962416ffe190e16db
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876182"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="d6d80-103">Migração de caixa de correio entre locatários (visualização)</span><span class="sxs-lookup"><span data-stu-id="d6d80-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="d6d80-104">Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço do Exchange Online, ele teria que removê-las completamente para o local e, em seguida, abordá-las para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="d6d80-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="d6d80-105">Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários em locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="d6d80-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="d6d80-106">Isso remove a necessidade de retirada e integração de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="d6d80-107">Normalmente, durante fusões ou desinvestções, você precisa da capacidade de mover usuários e conteúdo para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="d6d80-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="d6d80-108">Quando o administrador de locatários de destino executa a movimentação, ela é chamada de movimentação pull, semelhante às migrações locais para integração na nuvem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="d6d80-109">As movimentações de caixa de correio entre locatários do Exchange são totalmente autoatendadas por administradores de locatários, usando interfaces conhecidas que podem ser roteadas nos fluxos de trabalho maiores necessários para fazer a transição dos usuários para sua nova organização.</span><span class="sxs-lookup"><span data-stu-id="d6d80-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="d6d80-110">Os administradores podem usar o cmdlet, disponível por meio da função de gerenciamento Mover Caixas de Correio, para executar movimentações `New-MigrationBatch` entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="d6d80-111">O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e a finalização da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="d6d80-112">Os usuários que migram devem estar presentes no sistema de locatário de destino do Exchange Online como MailUsers, marcado com atributos específicos para habilitar as movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="d6d80-113">O sistema falhará em movimentações para usuários que não estão corretamente definidos no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="d6d80-114">Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="d6d80-115">Esse processo deixa o MailUser herdado no locatário de origem e permite um período de co-existência e roteamento de emails.</span><span class="sxs-lookup"><span data-stu-id="d6d80-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="d6d80-116">Quando os processos de negócios permitem, o locatário de origem pode remover o MailUser de origem ou convertê-lo em um contato de email.</span><span class="sxs-lookup"><span data-stu-id="d6d80-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="d6d80-117">As migrações de caixa de correio entre locatários do Exchange são suportadas apenas para locatários em nuvem ou híbrida ou qualquer combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="d6d80-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="d6d80-118">Este artigo descreve o processo de movimentações de caixa de correio entre locatários e fornece orientações sobre como preparar locatários de origem e destino para a movimentação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="d6d80-119">Preparando locatários de origem e destino</span><span class="sxs-lookup"><span data-stu-id="d6d80-119">Preparing source and target tenants</span></span>

<span data-ttu-id="d6d80-120">O recurso de migração de caixa de correio entre locatários do Exchange requer autorização e escolhamento para migrações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="d6d80-121">Usando o aplicativo do Azure Enterprise e as soluções de armazenamento do Cofre de Chaves, os administradores de locatários agora têm a capacidade de gerenciar tanto a autorização quanto o escoamento das migrações de caixa de correio do Exchange Online de um locatário para outro.</span><span class="sxs-lookup"><span data-stu-id="d6d80-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="d6d80-122">As movimentações de caixa de correio entre locatários suportam um modelo de convite e consentimento para estabelecer um aplicativo do Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="d6d80-123">Componentes adicionais, como uma relação de organização e um ponto de extremidade de migração, também são necessários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="d6d80-124">Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="d6d80-125">Confira Preparar [objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.</span><span class="sxs-lookup"><span data-stu-id="d6d80-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6d80-126">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d6d80-126">Prerequisites</span></span>

<span data-ttu-id="d6d80-127">O recurso de movimentação de caixa de correio entre locatários exige que o [Azure Key Vault](/azure/key-vault/basic-concepts) estabeleça um aplicativo do Azure específico do par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para o outro, removendo todos os requisitos para compartilhar certificados/segredos entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="d6d80-128">Antes de começar, certifique-se de que você tem as permissões necessárias para executar os scripts de implantação para configurar o Azure Key Vault, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração do EXO e o Relacionamento da Organização do EXO.</span><span class="sxs-lookup"><span data-stu-id="d6d80-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="d6d80-129">Normalmente, o Administrador Global tem permissão para executar todas as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="d6d80-130">Além disso, grupos de segurança habilitados para email no locatário de origem são necessários antes de executar a instalação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="d6d80-131">Esses grupos são usados para escopo da lista de caixas de correio que podem mudar do locatário de origem (ou às vezes chamado de recurso) para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="d6d80-132">Isso permite que o administrador do locatário de origem restrinja ou escopo o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários não intencionados sejam migrados.</span><span class="sxs-lookup"><span data-stu-id="d6d80-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="d6d80-133">Não há suporte para grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="d6d80-133">Nested groups are not supported.</span></span>

<span data-ttu-id="d6d80-134">Você também precisará se comunicar com sua empresa parceira confiável (com a qual você vai mover caixas de correio) para obter sua ID de locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6d80-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="d6d80-135">Essa ID de locatário é usada no campo Relacionamento da `DomainName` Organização.</span><span class="sxs-lookup"><span data-stu-id="d6d80-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="d6d80-136">Para obter a ID do locatário de uma assinatura, entre no Centro de administração do Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="d6d80-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="d6d80-137">Clique no ícone de cópia da propriedade ID do locatário para copiá-lo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="d6d80-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="d6d80-138">Veja como o processo funciona.</span><span class="sxs-lookup"><span data-stu-id="d6d80-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparação do locatário para migração de caixa de correio.":::

<span data-ttu-id="d6d80-140">[Consulte uma versão maior dessa imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span><span class="sxs-lookup"><span data-stu-id="d6d80-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="d6d80-141">Preparar locatários</span><span class="sxs-lookup"><span data-stu-id="d6d80-141">Prepare tenants</span></span>

<span data-ttu-id="d6d80-142">Em alto nível, as seguintes ações de configuração ocorrem ao executar os scripts de instalação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="d6d80-143">Preparar o locatário de destino:</span><span class="sxs-lookup"><span data-stu-id="d6d80-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="d6d80-144">Se um grupo de recursos do Azure existente não for fornecido, um novo será criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="d6d80-145">Se um Cofre de Chaves existente não for fornecido, um novo será criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="d6d80-146">Uma nova Política de Acesso é criada para o aplicativo de Migração de Caixa de Correio do Office 365 Exchange Online (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="d6d80-147">Um novo certificado é criado (ou existente, se especificado) para manter o segredo para o aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="d6d80-148">Um novo aplicativo do Azure AD é criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="d6d80-149">O certificado/segredo é carregado no aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="d6d80-150">As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="d6d80-151">O script de implantação pausa até que o administrador de destino consenta com seu próprio aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="d6d80-152">O administrador do locatário de destino consente com as permissões concedidas ao aplicativo (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="d6d80-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="d6d80-153">Uma relação de organização é criada para o locatário de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="d6d80-154">Um ponto de extremidade de migração é criado para puxar caixas de correio para o locatário de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="d6d80-155">Preparar o locatário de origem:</span><span class="sxs-lookup"><span data-stu-id="d6d80-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="d6d80-156">O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de Migração de Caixa de Correio do locatário de destino (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="d6d80-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="d6d80-157">O administrador do locatário de origem cria um grupo de segurança habilitado para email em seu locatário para conter a lista de caixas de correio permitidas para serem movidas pelo aplicativo de migração (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="d6d80-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="d6d80-158">Uma relação de organização é criada com o locatário de destino especificando que o aplicativo de migração de caixa de correio deve ser usado para verificação OAuth para aceitar a solicitação de movimentação (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="d6d80-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="d6d80-159">Instruções passo a passo para o administrador do locatário de destino</span><span class="sxs-lookup"><span data-stu-id="d6d80-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="d6d80-160">Baixe o SetupCrossTenantRelationshipForTargetTenant.ps1 para a configuração do locatário de destino no [repositório do GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="d6d80-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="d6d80-161">Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador do qual você executará o script.</span><span class="sxs-lookup"><span data-stu-id="d6d80-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="d6d80-162">Crie uma conexão remota do PowerShell com o locatário de destino do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6d80-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="d6d80-163">Novamente, certifique-se de ter as permissões necessárias para executar os scripts de implantação para configurar o certificado e o armazenamento e o certificado do Cofre de Chaves do Azure, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração do EXO e o Relacionamento da Organização do EXO.</span><span class="sxs-lookup"><span data-stu-id="d6d80-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="d6d80-164">Altere o diretório da pasta de arquivos para o local do script ou verifique se o script está salvo no momento no local em sua sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="d6d80-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="d6d80-165">Execute o script com os seguintes parâmetros e valores.</span><span class="sxs-lookup"><span data-stu-id="d6d80-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="d6d80-166">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="d6d80-166">Parameter</span></span> | <span data-ttu-id="d6d80-167">Valor</span><span class="sxs-lookup"><span data-stu-id="d6d80-167">Value</span></span> | <span data-ttu-id="d6d80-168">Obrigatório ou Opcional</span><span class="sxs-lookup"><span data-stu-id="d6d80-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="d6d80-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="d6d80-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="d6d80-170">Domínio de locatário de destino, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="d6d80-171">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-171">Required</span></span> |
    | <span data-ttu-id="d6d80-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="d6d80-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="d6d80-173">Domínio de locatário de origem, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="d6d80-174">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-174">Required</span></span> |
    | <span data-ttu-id="d6d80-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="d6d80-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="d6d80-176">Endereço de email do administrador do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="d6d80-177">Este é o administrador do locatário de origem que consentiá com o uso do aplicativo de migração de caixa de correio enviado do administrador de destino. Este é o administrador que receberá o convite de email para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="d6d80-178">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-178">Required</span></span> |
    | <span data-ttu-id="d6d80-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="d6d80-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="d6d80-180">ID da organização de locatários de origem (GUID).</span><span class="sxs-lookup"><span data-stu-id="d6d80-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="d6d80-181">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-181">Required</span></span> |
    | <span data-ttu-id="d6d80-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="d6d80-182">-SubscriptionId</span></span>                             | <span data-ttu-id="d6d80-183">A assinatura do Azure a ser usada para criar recursos.</span><span class="sxs-lookup"><span data-stu-id="d6d80-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="d6d80-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-184">Required</span></span> |
    | <span data-ttu-id="d6d80-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="d6d80-185">-ResourceGroup</span></span>                              | <span data-ttu-id="d6d80-186">Nome do grupo de recursos do Azure que contém ou conterá o Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="d6d80-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="d6d80-187">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-187">Required</span></span> |
    | <span data-ttu-id="d6d80-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="d6d80-188">-KeyVaultName</span></span>                               | <span data-ttu-id="d6d80-189">Instância do Azure Key Vault que armazenará seu certificado/segredo do aplicativo de migração de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="d6d80-190">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-190">Required</span></span> |
    | <span data-ttu-id="d6d80-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="d6d80-191">-CertificateName</span></span>                            | <span data-ttu-id="d6d80-192">Nome do certificado ao gerar ou pesquisar certificado no cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="d6d80-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="d6d80-193">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-193">Required</span></span> |
    | <span data-ttu-id="d6d80-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="d6d80-194">-CertificateSubject</span></span>                         | <span data-ttu-id="d6d80-195">Nome do assunto do certificado do Azure Key Vault, como CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="d6d80-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="d6d80-196">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-196">Required</span></span> |
    | <span data-ttu-id="d6d80-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="d6d80-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="d6d80-198">Aplicativo de migração de email a ser usado se já tiver sido criado.</span><span class="sxs-lookup"><span data-stu-id="d6d80-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="d6d80-199">Opcional</span><span class="sxs-lookup"><span data-stu-id="d6d80-199">Optional</span></span> |
    | <span data-ttu-id="d6d80-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="d6d80-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="d6d80-201">As permissões necessárias para serem concedidas ao aplicativo de migração de caixa de correio, como Exchange ou MSGraph (Exchange para mover caixas de correio, MSGraph para usar esse aplicativo para enviar um convite de link de consentimento para locatário de recursos).</span><span class="sxs-lookup"><span data-stu-id="d6d80-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="d6d80-202">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="d6d80-202">Required</span></span> |
    | <span data-ttu-id="d6d80-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="d6d80-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="d6d80-204">Parâmetro para usar o aplicativo criado para migração a ser usado para enviar convite de link de consentimento para o administrador do locatário de origem. Se não estiver presente, solicitará que as credenciais do administrador de destino se conectem ao gerenciador de convites do Azure e enviem o convite como administrador de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="d6d80-205">Opcional</span><span class="sxs-lookup"><span data-stu-id="d6d80-205">Optional</span></span> |
    | <span data-ttu-id="d6d80-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="d6d80-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="d6d80-207">A conta de armazenamento onde os logs de auditoria do Key Vault seriam armazenados.</span><span class="sxs-lookup"><span data-stu-id="d6d80-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="d6d80-208">Opcional</span><span class="sxs-lookup"><span data-stu-id="d6d80-208">Optional</span></span> |
    | <span data-ttu-id="d6d80-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="d6d80-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="d6d80-210">O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria do Key Vault.</span><span class="sxs-lookup"><span data-stu-id="d6d80-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="d6d80-211">Opcional</span><span class="sxs-lookup"><span data-stu-id="d6d80-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="d6d80-212">Verifique se você instalou o módulo do PowerShell do Azure AD antes de executar os scripts.</span><span class="sxs-lookup"><span data-stu-id="d6d80-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="d6d80-213">Consulte aqui ![ para etapas de ](/powershell/azure/install-az-ps?view=azps-5.1.0) instalação</span><span class="sxs-lookup"><span data-stu-id="d6d80-213">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="d6d80-214">O script pausa e solicita que você aceite ou consenta com o aplicativo de migração de caixa de correio do Exchange criado durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="d6d80-215">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-215">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="d6d80-216">Uma URL será exibida na sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="d6d80-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="d6d80-217">Copie o link fornecido para o consentimento do locatário e o colar em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="d6d80-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="d6d80-218">Entre com suas credenciais de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="d6d80-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="d6d80-219">Quando a tela a seguir for apresentada, selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="d6d80-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Caixa de diálogo Aceitar permissões":::

9. <span data-ttu-id="d6d80-221">Alternar de volta para a sessão do PowerShell remoto e aperte Enter para continuar.</span><span class="sxs-lookup"><span data-stu-id="d6d80-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="d6d80-222">O script configurará os objetos de instalação restantes.</span><span class="sxs-lookup"><span data-stu-id="d6d80-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="d6d80-223">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="d6d80-224">A configuração do administrador de destino agora está concluída!</span><span class="sxs-lookup"><span data-stu-id="d6d80-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="d6d80-225">Instruções passo a passo para o administrador do locatário de origem</span><span class="sxs-lookup"><span data-stu-id="d6d80-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="d6d80-226">Entre em sua caixa de correio como o -ResourceTenantAdminEmail especificado pelo administrador de destino durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="d6d80-227">Encontre o convite de email do locatário de destino e selecione o **botão Começar.**</span><span class="sxs-lookup"><span data-stu-id="d6d80-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Você foi convidado na caixa de diálogo":::

2. <span data-ttu-id="d6d80-229">Selecione **Aceitar** para aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="d6d80-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissões":::

   > [!NOTE]
   > <span data-ttu-id="d6d80-231">Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino recebeu uma URL direta que pode ser dada a você para aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="d6d80-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="d6d80-232">A URL deve estar na transcrição da sessão do PowerShell Remoto do administrador do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="d6d80-233">No Centro de administração do Microsoft 365 ou em uma sessão do PowerShell Remoto, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para puxar (mover) do locatário de origem para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="d6d80-234">Você não precisa preencher esse grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de instalação (script).</span><span class="sxs-lookup"><span data-stu-id="d6d80-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="d6d80-235">Não há suporte para grupos de aninhar.</span><span class="sxs-lookup"><span data-stu-id="d6d80-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="d6d80-236">Baixe o SetupCrossTenantRelationshipForResourceTenant.ps1 para a configuração do locatário de origem no repositório do GitHub aqui: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="d6d80-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="d6d80-237">Crie uma conexão do PowerShell remota com o locatário de origem com suas permissões de Administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d6d80-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="d6d80-238">As permissões de Administrador Global não são necessárias para configurar o locatário de origem, apenas o locatário de destino devido ao processo de criação de aplicativos do Azure.</span><span class="sxs-lookup"><span data-stu-id="d6d80-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="d6d80-239">Altere o diretório para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="d6d80-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="d6d80-240">Execute o script com os seguintes parâmetros e valores necessários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="d6d80-241">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="d6d80-241">Parameter</span></span> | <span data-ttu-id="d6d80-242">Valor</span><span class="sxs-lookup"><span data-stu-id="d6d80-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="d6d80-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="d6d80-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="d6d80-244">Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo da migração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="d6d80-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="d6d80-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="d6d80-246">Nome de domínio de locatário de origem, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="d6d80-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="d6d80-247">-ApplicationId</span></span> | <span data-ttu-id="d6d80-248">ID do aplicativo do Azure (GUID) do aplicativo usado para migração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="d6d80-249">ID do aplicativo disponível por meio do portal do Azure (Azure AD, Aplicativos Empresariais, nome do aplicativo, ID do aplicativo) ou incluído no email do convite.</span><span class="sxs-lookup"><span data-stu-id="d6d80-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="d6d80-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="d6d80-250">-TargetTenantDomain</span></span> | <span data-ttu-id="d6d80-251">Nome de domínio de locatário de destino, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="d6d80-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="d6d80-252">-TargetTenantId</span></span> | <span data-ttu-id="d6d80-253">ID de locatário do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="d6d80-254">Por exemplo, a ID de locatário do Azure AD da contoso \. onmicrosoft.com locatário.</span><span class="sxs-lookup"><span data-stu-id="d6d80-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="d6d80-255">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="d6d80-256">A configuração do administrador de origem agora está concluída!</span><span class="sxs-lookup"><span data-stu-id="d6d80-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="d6d80-257">Verificar a instalação</span><span class="sxs-lookup"><span data-stu-id="d6d80-257">Verify setup</span></span>

<span data-ttu-id="d6d80-258">Verifique se as relações da organização nos locatários de origem e de destino e no ponto de extremidade de migração no destino foram criadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="d6d80-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="d6d80-259">Locatário de destino</span><span class="sxs-lookup"><span data-stu-id="d6d80-259">Target tenant</span></span>

<span data-ttu-id="d6d80-260">**Relação de organização**</span><span class="sxs-lookup"><span data-stu-id="d6d80-260">**Organization relationship**</span></span>

<span data-ttu-id="d6d80-261">Verifique se o objeto de relação da organização foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="d6d80-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="d6d80-262">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6d80-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="d6d80-263">**Ponto de extremidade de migração**</span><span class="sxs-lookup"><span data-stu-id="d6d80-263">**Migration endpoint**</span></span>

<span data-ttu-id="d6d80-264">Verifique se o objeto de ponto de extremidade de migração foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="d6d80-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="d6d80-265">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="d6d80-266">Locatário de origem</span><span class="sxs-lookup"><span data-stu-id="d6d80-266">Source tenant</span></span>

<span data-ttu-id="d6d80-267">**Relação de organização**</span><span class="sxs-lookup"><span data-stu-id="d6d80-267">**Organization relationship**</span></span>

<span data-ttu-id="d6d80-268">Verifique se o objeto de relação da organização foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="d6d80-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="d6d80-269">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="d6d80-270">Verificar Script de Instalação</span><span class="sxs-lookup"><span data-stu-id="d6d80-270">Verify Setup Script</span></span>

<span data-ttu-id="d6d80-271">Se você receber erros durante a configuração dos locatários de origem ou de destino, poderá executar o script VerifySetup.ps1 localizado no [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) e revisar a saída.</span><span class="sxs-lookup"><span data-stu-id="d6d80-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="d6d80-272">Veja um exemplo de execução de VerifySetup.ps1 no locatário de destino:</span><span class="sxs-lookup"><span data-stu-id="d6d80-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="d6d80-273">Veja um exemplo de VerifySetup.ps1 no locatário de origem:</span><span class="sxs-lookup"><span data-stu-id="d6d80-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="d6d80-274">Mover caixas de correio de volta para a fonte original</span><span class="sxs-lookup"><span data-stu-id="d6d80-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="d6d80-275">Se uma caixa de correio voltar para o locatário de origem original for necessária, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="d6d80-276">O objeto Organization Relationship existente será atualizado ou anexado, não recriado.</span><span class="sxs-lookup"><span data-stu-id="d6d80-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="d6d80-277">Preparar objetos de usuário de destino para migração</span><span class="sxs-lookup"><span data-stu-id="d6d80-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="d6d80-278">Os usuários que migram devem estar presentes no locatário de destino e no sistema do Exchange Online (como MailUsers) marcados com atributos específicos para habilitar as movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="d6d80-279">O sistema falhará em movimentações para usuários que não estão corretamente definidos no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="d6d80-280">A seção a seguir detalha os requisitos de objeto MailUser para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d6d80-281">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d6d80-281">Prerequisites</span></span>
  
<span data-ttu-id="d6d80-282">Você deve garantir que os seguintes objetos e atributos sejam definidos na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="d6d80-283">Para qualquer caixa de correio que se move de uma organização de origem, você deve provisionar um objeto MailUser na organização De destino:</span><span class="sxs-lookup"><span data-stu-id="d6d80-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="d6d80-284">O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto User:</span><span class="sxs-lookup"><span data-stu-id="d6d80-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="d6d80-285">ExchangeGUID (fluxo direto de origem para destino) – O GUID da caixa de correio deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="d6d80-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="d6d80-286">O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="d6d80-287">ArchiveGUID (fluxo direto de origem para destino) – O GUID de arquivo morto deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="d6d80-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="d6d80-288">O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="d6d80-289">(Isso só será necessário se a caixa de correio de origem estiver habilitada para Arquivamento).</span><span class="sxs-lookup"><span data-stu-id="d6d80-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="d6d80-290">LegacyExchangeDN (fluxo como proxyAddress, "x500: ") – O LegacyExchangeDN deve estar presente no MailUser de destino <LegacyExchangeDN> como x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="d6d80-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="d6d80-291">Os processos de movimentação não continuarão se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="d6d80-292">UserPrincipalName – o UPN se alinhará à nova identidade ou à empresa de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="d6d80-293">SMTPAddress principal – O endereço SMTP principal se alinhará à nova empresa do usuário (por exemplo, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="d6d80-294">TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio atual do usuário hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="d6d80-295">Ao atribuir esse valor, verifique se você também está atribuindo PrimarySMTPAddress ou esse valor definirá PrimarySMTPAddress que causará falhas de movimentação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="d6d80-296">Não é possível adicionar endereços proxy smtp herdado da caixa de correio de origem para direcionar MailUser.</span><span class="sxs-lookup"><span data-stu-id="d6d80-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="d6d80-297">Por exemplo, você não pode manter contoso.com no MEU em objetos fabrikam.onmicrosoft.com locatários).</span><span class="sxs-lookup"><span data-stu-id="d6d80-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="d6d80-298">Os domínios são associados apenas a um locatário do Azure AD ou exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6d80-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="d6d80-299">Exemplo **de** objeto MailUser de destino:</span><span class="sxs-lookup"><span data-stu-id="d6d80-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="d6d80-300">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6d80-300">Attribute</span></span>             | <span data-ttu-id="d6d80-301">Valor</span><span class="sxs-lookup"><span data-stu-id="d6d80-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="d6d80-302">Alias</span><span class="sxs-lookup"><span data-stu-id="d6d80-302">Alias</span></span>                 | <span data-ttu-id="d6d80-303">LaraN</span><span class="sxs-lookup"><span data-stu-id="d6d80-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="d6d80-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="d6d80-304">RecipientType</span></span>         | <span data-ttu-id="d6d80-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="d6d80-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="d6d80-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="d6d80-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="d6d80-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="d6d80-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="d6d80-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d6d80-308">UserPrincipalName</span></span>     | <span data-ttu-id="d6d80-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="d6d80-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="d6d80-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="d6d80-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="d6d80-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="d6d80-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="d6d80-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="d6d80-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="d6d80-314">ExchangeGuid</span></span>          | <span data-ttu-id="d6d80-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="d6d80-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="d6d80-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="d6d80-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="d6d80-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="d6d80-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="d6d80-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="d6d80-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="d6d80-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="d6d80-319">EmailAddresses</span></span>        | <span data-ttu-id="d6d80-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="d6d80-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="d6d80-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="d6d80-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="d6d80-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="d6d80-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="d6d80-324">Exemplo do objeto Mailbox de **origem:**</span><span class="sxs-lookup"><span data-stu-id="d6d80-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="d6d80-325">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6d80-325">Attribute</span></span>             | <span data-ttu-id="d6d80-326">Valor</span><span class="sxs-lookup"><span data-stu-id="d6d80-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="d6d80-327">Alias</span><span class="sxs-lookup"><span data-stu-id="d6d80-327">Alias</span></span>                 | <span data-ttu-id="d6d80-328">LaraN</span><span class="sxs-lookup"><span data-stu-id="d6d80-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="d6d80-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="d6d80-329">RecipientType</span></span>         | <span data-ttu-id="d6d80-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="d6d80-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="d6d80-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="d6d80-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="d6d80-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="d6d80-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="d6d80-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d6d80-333">UserPrincipalName</span></span>     | <span data-ttu-id="d6d80-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="d6d80-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="d6d80-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="d6d80-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="d6d80-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="d6d80-337">ExchangeGuid</span></span>          | <span data-ttu-id="d6d80-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="d6d80-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="d6d80-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="d6d80-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="d6d80-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="d6d80-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="d6d80-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="d6d80-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="d6d80-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="d6d80-342">EmailAddresses</span></span>        | <span data-ttu-id="d6d80-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="d6d80-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d6d80-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="d6d80-345">Atributos adicionais já podem ser incluídos na gravação híbrida do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d6d80-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="d6d80-346">Caso não seja, eles devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="d6d80-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="d6d80-347">msExchBlockedSendersHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="d6d80-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="d6d80-348">msExchSafeRecipientsHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="d6d80-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="d6d80-349">msExchSafeSendersHash – Grava novamente dados de remetentes seguros e bloqueados dos clientes no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="d6d80-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="d6d80-350">Se a caixa de correio de origem estiver em LitigationHold e o tamanho de Itens Recuperáveis da caixa de correio de origem for maior do que o padrão do banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor que o tamanho da caixa de correio de origem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="d6d80-351">Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="d6d80-352">Essas instruções funcionarão apenas para identidade híbrida executando o Azure AD Connect, pois os comandos para carimbar os sinalizadores ELC não são expostos aos administradores de locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="d6d80-353">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="d6d80-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="d6d80-354">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="d6d80-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="d6d80-355">Se a fonte tiver litígio ou recuperação de item único habilitada, de definir isso na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="d6d80-356">Isso aumentará o tamanho da lixeira da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="d6d80-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="d6d80-357">Os locatários de destino não híbridos podem modificar a cota na pasta Itens Recuperáveis para os MailUsers antes da migração executando o seguinte comando para habilitar a Responsabilidade de Litígio no objeto MailUser e aumentando a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="d6d80-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="d6d80-358">Observe que isso não funcionará para locatários híbridos.</span><span class="sxs-lookup"><span data-stu-id="d6d80-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="d6d80-359">Os usuários na organização de destino devem ser licenciados com assinaturas apropriadas do Exchange Online aplicáveis à organização.</span><span class="sxs-lookup"><span data-stu-id="d6d80-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="d6d80-360">Você pode aplicar uma licença antes de uma movimentação de caixa de correio, mas SOMENTE depois que o MailUser de destino for corretamente definido com o ExchangeGUID e endereços proxy.</span><span class="sxs-lookup"><span data-stu-id="d6d80-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="d6d80-361">Aplicar uma licença antes da aplicação do ExchangeGUID resultará em uma nova caixa de correio provisionada na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="d6d80-362">Quando você aplica uma licença a um objeto Mailbox ou MailUser, todos os proxy de tipo SMTPAddresses são limpos para garantir que apenas domínios verificados sejam incluídos na matriz EmailAddresses do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d6d80-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="d6d80-363">Você deve garantir que o MailUser de destino não tenha nenhum ExchangeGuid anterior que não corresponder ao ExchangeGuid de origem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="d6d80-364">Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para o Exchange Online e provisionado uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="d6d80-365">Se o MailUser de destino tiver sido licenciado anteriormente ou tiver um ExchangeGuid que não corresponder ao ExchangeGuid de origem, você precisará executar uma limpeza da nuvem MEU.</span><span class="sxs-lookup"><span data-stu-id="d6d80-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="d6d80-366">Para essas MEUs de nuvem, você pode executar `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="d6d80-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="d6d80-367">Esse processo é irreversível.</span><span class="sxs-lookup"><span data-stu-id="d6d80-367">This process is irreversible.</span></span> <span data-ttu-id="d6d80-368">Se o objeto tiver uma caixa de correio softDeleted, ele não poderá ser restaurado após esse ponto.</span><span class="sxs-lookup"><span data-stu-id="d6d80-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="d6d80-369">Uma vez limpo, no entanto, você pode sincronizar o ExchangeGuid correto com o objeto de destino e o MRS conectará a caixa de correio de origem à caixa de correio de destino recém-criada.</span><span class="sxs-lookup"><span data-stu-id="d6d80-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="d6d80-370">(Referência do blog EHLO no novo parâmetro.)</span><span class="sxs-lookup"><span data-stu-id="d6d80-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="d6d80-371">Encontre objetos que eram caixas de correio anteriores usando esse comando.</span><span class="sxs-lookup"><span data-stu-id="d6d80-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="d6d80-372">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="d6d80-373">Limpe a caixa de correio excluída de forma suave usando este comando.</span><span class="sxs-lookup"><span data-stu-id="d6d80-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="d6d80-374">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="d6d80-375">Executar migrações de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="d6d80-375">Perform mailbox migrations</span></span>

<span data-ttu-id="d6d80-376">As migrações de caixa de correio entre locatários do Exchange são enviadas como lotes de migração iniciados do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="d6d80-377">Isso é semelhante à maneira como os lotes de migração ao abordar funcionam ao migrar do Exchange local para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6d80-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="d6d80-378">Criar lotes de migração</span><span class="sxs-lookup"><span data-stu-id="d6d80-378">Create Migration batches</span></span>

<span data-ttu-id="d6d80-379">Aqui está um exemplo de cmdlet em lotes de migração para início de movimentações.</span><span class="sxs-lookup"><span data-stu-id="d6d80-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="d6d80-380">O endereço de email no arquivo CSV deve ser o especificado no locatário de destino, não o locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="d6d80-381">O envio em lote de migração também tem suporte do novo Centro de Administração do Exchange ao selecionar a opção entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="d6d80-382">Atualizar MailUsers local</span><span class="sxs-lookup"><span data-stu-id="d6d80-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="d6d80-383">Depois que a caixa de correio mudar de origem para destino, você deve garantir que os usuários de email locais, origem e o destino, sejam atualizados com o novo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="d6d80-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="d6d80-384">Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="d6d80-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="d6d80-385">Atualize os usuários de email com esse targetAddress.</span><span class="sxs-lookup"><span data-stu-id="d6d80-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d6d80-386">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="d6d80-386">Frequently asked questions</span></span>

<span data-ttu-id="d6d80-387">**Precisamos atualizar RemoteMailboxes na origem local após a movimentação?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="d6d80-388">Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários locais de origem quando a caixa de correio de locatário de origem for migrada para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="d6d80-389">Embora o roteamento de email possa seguir as indicações entre vários usuários de email com destinos diferentesAddresses, as buscas de usuários de email devem direcionar o local do usuário da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="d6d80-390">As buscas de livre/ocupado não perseguirão vários redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="d6d80-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="d6d80-391">**As reuniões do Teams migram entre locatários?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-391">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="d6d80-392">As reuniões serão movimentadas no entanto, a URL de reunião do Teams não será atualizada quando os itens migrarem entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-392">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="d6d80-393">Como a URL será inválida no locatário de destino, você precisará remover e recriar as reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="d6d80-393">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="d6d80-394">**O conteúdo da pasta de chat do Teams migra entre locatários?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-394">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="d6d80-395">Não, o conteúdo da pasta de chat do Teams não migra entre locatários.</span><span class="sxs-lookup"><span data-stu-id="d6d80-395">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="d6d80-396">**Como posso ver apenas movimentações que são movimentações entre locatários, não minhas movimentações de integração e de off-boarding?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-396">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="d6d80-397">Use o `-flags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d6d80-397">Use the `-flags` parameter.</span></span> <span data-ttu-id="d6d80-398">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-398">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="d6d80-399">**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-399">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="d6d80-400">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="d6d80-400">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="d6d80-401">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o destino dos Serviços de Domínio do Active Directory local (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="d6d80-401">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="d6d80-402">Se a fonte tiver litígio ou recuperação de item único habilitada, de definir isso na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-402">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="d6d80-403">Isso aumentará o tamanho da lixeira da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="d6d80-403">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit" 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects 
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="d6d80-404">**Como acessamos o Outlook no dia 1 após a movimentação da caixa de correio de uso?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-404">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="d6d80-405">Como apenas um locatário pode possuir um domínio, o SMTPAddress principal anterior não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; somente os domínios associados ao novo locatário.</span><span class="sxs-lookup"><span data-stu-id="d6d80-405">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="d6d80-406">O Outlook usa o novo UPN dos usuários para autenticar o serviço e o perfil do Outlook espera encontrar o SMTPAddress primário herdado para corresponder à caixa de correio no sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-406">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="d6d80-407">Como o endereço herdado não está no destino O perfil do outlook não se conectará para encontrar a caixa de correio movida recentemente.</span><span class="sxs-lookup"><span data-stu-id="d6d80-407">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="d6d80-408">Para essa implantação inicial, os usuários precisarão recriar seu perfil com seu novo UPN, endereço SMTP principal e ressincronize o conteúdo OST.</span><span class="sxs-lookup"><span data-stu-id="d6d80-408">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="d6d80-409">Planeje de acordo à medida que você lote seus usuários para conclusão.</span><span class="sxs-lookup"><span data-stu-id="d6d80-409">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="d6d80-410">Você precisa levar em conta a utilização e a capacidade da rede quando os perfis de cliente do Outlook são criados e os arquivos OST e OAB subsequentes são baixados para clientes.</span><span class="sxs-lookup"><span data-stu-id="d6d80-410">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="d6d80-411">**De que funções de RBAC do Exchange preciso ser membro para configurar ou concluir uma movimentação entre locatários?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-411">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="d6d80-412">Há uma matriz de funções com base na suposição de funções delegadas ao executar uma movimentação de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-412">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="d6d80-413">Atualmente, duas funções são necessárias:</span><span class="sxs-lookup"><span data-stu-id="d6d80-413">Currently, two roles are required:</span></span>  

- <span data-ttu-id="d6d80-414">A primeira função é para uma tarefa de instalação única que estabelece a autorização de mover o conteúdo para ou para fora do limite de locatário/organizacional.</span><span class="sxs-lookup"><span data-stu-id="d6d80-414">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="d6d80-415">Como a movimentação de dados do controle organizacional é uma preocupação crítica para todas as empresas, optamos pela função mais alta atribuída do Administrador da Organização (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="d6d80-415">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="d6d80-416">Essa função deve alterar ou configurar um novo OrganizationRelationship que define o -MailboxMoveCapability com a organização remota.</span><span class="sxs-lookup"><span data-stu-id="d6d80-416">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="d6d80-417">Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de Compartilhamento Federado.</span><span class="sxs-lookup"><span data-stu-id="d6d80-417">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="d6d80-418">A função de executar os comandos de movimentação real pode ser delegada a uma função de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="d6d80-418">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="d6d80-419">A função de Mover Caixas de Correio recebe a capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d6d80-419">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="d6d80-420">**Como direcionar qual endereço SMTP está selecionado para targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para conversão mailUser)?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-420">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="d6d80-421">As movimentações de caixa de correio do Exchange usando o MRS criarão o targetAddress na caixa de correio de origem original ao converter em um MailUser correspondendo a um endereço de email (proxyAddress) no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-421">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="d6d80-422">O processo pega o valor -TargetDeliveryDomain passado para o comando de movimentação e verifica se há um proxy correspondente para esse domínio no lado de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-422">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="d6d80-423">Quando encontramos uma correspondência, o proxy correspondenteAddress é usado para definir ExternalEmailAddress (targetAddress) no objeto de caixa de correio convertida (agora MailUser).</span><span class="sxs-lookup"><span data-stu-id="d6d80-423">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="d6d80-424">**Como fazer a transição de permissões de caixa de correio?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-424">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="d6d80-425">As permissões de caixa de correio incluem Send on Behalf of e Mailbox Access:</span><span class="sxs-lookup"><span data-stu-id="d6d80-425">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="d6d80-426">Send On Behalf Of (AD:publicDelegates) armazena a DN de destinatários com acesso à caixa de correio de um usuário como representante.</span><span class="sxs-lookup"><span data-stu-id="d6d80-426">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="d6d80-427">Esse valor é armazenado no Active Directory e atualmente não se move como parte da transição de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-427">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="d6d80-428">Se a caixa de correio de origem tiver publicDelegates definida, você precisará manter o publicDelegates na Caixa de Correio de destino assim que a conversão MEU para Caixa de Correio for concluída no ambiente de destino executando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="d6d80-428">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="d6d80-429">As permissões de caixa de correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade e o representante são movidos para o sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-429">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="d6d80-430">Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-430">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="d6d80-431">Depois que a movimentação de caixa de correio é concluída TargetCompany.onmicrosoft.com, as mesmas permissões são configuradas no diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-431">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="d6d80-432">Exemplos usando *Get-MailboxPermission* para TestUser_7 locatários de origem e destino são mostrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-432">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="d6d80-433">Os cmdlets do Exchange são prefixados com origem e destino de acordo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-433">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="d6d80-434">Aqui está um exemplo da saída da permissão de caixa de correio antes de uma movimentação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-434">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="d6d80-435">Aqui está um exemplo da saída da permissão de caixa de correio após a movimentação.</span><span class="sxs-lookup"><span data-stu-id="d6d80-435">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="d6d80-436">As permissões de caixa de correio e calendário entre locatários NÃO são suportadas.</span><span class="sxs-lookup"><span data-stu-id="d6d80-436">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="d6d80-437">Você deve organizar entidades e representantes em lotes de movimentação consolidados para que essas caixas de correio conectadas sejam transidas ao mesmo tempo do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="d6d80-437">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="d6d80-438">**Qual proxy X500 deve ser adicionado aos endereços proxy mailUser de destino para habilitar a migração?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-438">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="d6d80-439">A migração de caixa de correio entre locatários exige que o valor LegacyExchangeDN do objeto de caixa de correio de origem seja carimbado como um endereço de email x500 no objeto MailUser de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-439">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="d6d80-440">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6d80-440">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="d6d80-441">Além desse proxy X500, você precisará copiar todos os proxies X500 da caixa de correio na fonte para a caixa de correio no destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-441">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="d6d80-442">**Onde começar a solucionar problemas se as movimentações não funcionarem?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-442">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="d6d80-443">Comece executando o script VerifySetup.ps1 localizado [no GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) e revise a saída.</span><span class="sxs-lookup"><span data-stu-id="d6d80-443">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="d6d80-444">Veja um exemplo de execução de VerifySetup.ps1 no locatário de destino:</span><span class="sxs-lookup"><span data-stu-id="d6d80-444">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="d6d80-445">Aqui está um eExample de execução de VerifySetup.ps1 no locatário de origem:</span><span class="sxs-lookup"><span data-stu-id="d6d80-445">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="d6d80-446">**O locatário de origem e destino pode usar o mesmo nome de domínio?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-446">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="d6d80-447">Não.</span><span class="sxs-lookup"><span data-stu-id="d6d80-447">No.</span></span> <span data-ttu-id="d6d80-448">Os nomes de domínio de locatário de origem e destino devem ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="d6d80-448">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="d6d80-449">Por exemplo, um domínio de origem de contoso.com e o domínio de destino de fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-449">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="d6d80-450">**As caixas de correio compartilhadas serão movimentadas e ainda funcionarão?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-450">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="d6d80-451">Sim, no entanto, só manteremos as permissões da loja conforme descrito nestes artigos:</span><span class="sxs-lookup"><span data-stu-id="d6d80-451">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="d6d80-452">Microsoft Docs | Gerenciar permissões para destinatários no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-452">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="d6d80-453">Suporte da Microsoft | Como conceder permissões de caixa de correio do Exchange e do Outlook no Office 365 dedicado</span><span class="sxs-lookup"><span data-stu-id="d6d80-453">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="d6d80-454">**O Azure Key Vault é necessário e quando as transações são feitas?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-454">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="d6d80-455">Sim, uma assinatura do Azure é necessária para usar o Key Vault para armazenar o certificado para autorizar a migração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-455">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="d6d80-456">Ao contrário das migrações de integração que usam o nome de usuário & senha para autenticar na origem, as migrações de caixa de correio entre locatários usam o OAuth e esse certificado como segredo/credencial.</span><span class="sxs-lookup"><span data-stu-id="d6d80-456">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="d6d80-457">O acesso ao Cofre de Chaves deve ser mantido em todas as migrações de caixa de correio, pois ele é acessado uma vez no início e depois do fim da migração, bem como uma vez a cada 24 horas durante os tempos de sincronização incrementais.</span><span class="sxs-lookup"><span data-stu-id="d6d80-457">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="d6d80-458">Você pode revisar os detalhes de custo do AKV [aqui]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="d6d80-458">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="d6d80-459">**Você tem alguma recomendação para lotes?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-459">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="d6d80-460">Não exceda 2.000 caixas de correio por lote.</span><span class="sxs-lookup"><span data-stu-id="d6d80-460">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="d6d80-461">Recomendamos o envio de lotes duas semanas antes da data de recortamento, pois não há impacto para os usuários finais durante a sincronização. Se você precisar de orientações para quantidades de caixas de correio com mais de 50.000, você poderá falar com a Lista de Distribuição de Feedback de Engenharia no crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d6d80-461">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="d6d80-462">**E se eu usar a criptografia de serviço com a Chave do Cliente?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-462">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="d6d80-463">A caixa de correio será descriptografada antes de se mover.</span><span class="sxs-lookup"><span data-stu-id="d6d80-463">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="d6d80-464">Verifique se a Chave do Cliente está configurada no locatário de destino, se ela ainda for necessária.</span><span class="sxs-lookup"><span data-stu-id="d6d80-464">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="d6d80-465">Consulte [aqui](../compliance/customer-key-overview.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d6d80-465">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="d6d80-466">**Qual é o tempo estimado de migração?**</span><span class="sxs-lookup"><span data-stu-id="d6d80-466">**What is the estimated migration time?**</span></span>

<span data-ttu-id="d6d80-467">Para ajudá-lo a planejar [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) sua migração, a tabela presente aqui mostra as diretrizes sobre quando esperar que as migrações de caixa de correio em massa ou migrações individuais seja concluídas.</span><span class="sxs-lookup"><span data-stu-id="d6d80-467">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="d6d80-468">Essas estimativas se baseiam em uma análise de dados de migrações anteriores do cliente.</span><span class="sxs-lookup"><span data-stu-id="d6d80-468">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="d6d80-469">Como cada ambiente é exclusivo, a velocidade exata de migração pode variar.</span><span class="sxs-lookup"><span data-stu-id="d6d80-469">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="d6d80-470">Lembre-se de que esse recurso está atualmente em visualização e o SLA e quaisquer Níveis de Serviço aplicáveis não se aplicam a qualquer problema de desempenho ou disponibilidade durante o status de visualização desse recurso.</span><span class="sxs-lookup"><span data-stu-id="d6d80-470">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d6d80-471">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="d6d80-471">Known issues</span></span>  

-  <span data-ttu-id="d6d80-472">**Problema: arquivos expandidos automaticamente não podem ser migrados.**</span><span class="sxs-lookup"><span data-stu-id="d6d80-472">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="d6d80-473">O recurso de migração entre locatários suporta migrações da caixa de correio principal e da caixa de correio de arquivo morto para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="d6d80-473">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="d6d80-474">Se o usuário na origem, no entanto, tiver um arquivo morto expandido automaticamente – ou seja, mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos adicionais e deverá falhar.</span><span class="sxs-lookup"><span data-stu-id="d6d80-474">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="d6d80-475">**Problema: Cloud MailUsers with non-owned smtp proxyAddress block MRS move background.**</span><span class="sxs-lookup"><span data-stu-id="d6d80-475">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="d6d80-476">Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços proxy SMTP pertencem à organização do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="d6d80-476">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="d6d80-477">Se houver um proxy SMTPAddress no usuário de email de destino que não pertença ao locatário local, a conversão do MailUser para a Caixa de Correio será impedida.</span><span class="sxs-lookup"><span data-stu-id="d6d80-477">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="d6d80-478">Isso ocorre devido à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário):</span><span class="sxs-lookup"><span data-stu-id="d6d80-478">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="d6d80-479">Quando você sincroniza usuários do local usando o Azure AD Connect, provisiona objetos MailUser locais com ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso.onmicrosoft.com) e você carimba o PrimarySMTPAddress como um domínio que reside no locatário de destino (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-479">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="d6d80-480">Esses valores são sincronizados com o locatário e um usuário de email apropriado está provisionado e pronto para migração.</span><span class="sxs-lookup"><span data-stu-id="d6d80-480">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="d6d80-481">Um objeto example é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="d6d80-481">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="d6d80-482">O *contoso.onmicrosoft.com* endereço não *está* presente na matriz EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="d6d80-482">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="d6d80-483">**Problema: objetos MailUser com endereços SMTP "externos" primários são modificados/redefinidos para domínios "internos" reivindicados pela empresa**</span><span class="sxs-lookup"><span data-stu-id="d6d80-483">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="d6d80-484">Objetos MailUser são ponteiros para caixas de correio não locais.</span><span class="sxs-lookup"><span data-stu-id="d6d80-484">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="d6d80-485">No caso de migrações de caixa de correio entre locatários, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem).</span><span class="sxs-lookup"><span data-stu-id="d6d80-485">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="d6d80-486">Os MailUsers terão um ExternalEmailAddress (targetAddress) que aponta para o endereço smtp da caixa de correio real (ProxyTest@fabrikam.onmicrosoft.com) e o endereço primarySMTP que representa o endereço SMTP exibido do usuário de caixa de correio no diretório.</span><span class="sxs-lookup"><span data-stu-id="d6d80-486">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="d6d80-487">Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-487">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="d6d80-488">No entanto, uma vez que um objeto de plano de serviço do Exchange é aplicado ao MailUser por meio de operações de licenciamento, o endereço SMTP principal é modificado para mostrar como um domínio verificado pela organização local (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d6d80-488">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="d6d80-489">Há dois motivos potenciais:</span><span class="sxs-lookup"><span data-stu-id="d6d80-489">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="d6d80-490">Quando qualquer plano de serviço do Exchange é aplicado a um MailUser, o processo do Azure AD começa a impor a limpeza de proxy para garantir que a organização local não seja capaz de enviar emails, falsas ou emails de outro locatário.</span><span class="sxs-lookup"><span data-stu-id="d6d80-490">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="d6d80-491">Qualquer endereço SMTP em um objeto de destinatário com esses planos de serviço será removido se o endereço não for verificado pela organização local.</span><span class="sxs-lookup"><span data-stu-id="d6d80-491">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="d6d80-492">Como é o caso no exemplo, o domínio Fabikam.com não é verificado pelo locatário contoso.onmicrosoft.com, portanto, a limpeza remove esse fabrikam.com domínio.</span><span class="sxs-lookup"><span data-stu-id="d6d80-492">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="d6d80-493">Se desejar persistir esses domínios externos no MailUser, antes da migração ou após a migração, você precisará alterar seus processos de migração para retirar licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a identidade visual externa esperada aplicada.</span><span class="sxs-lookup"><span data-stu-id="d6d80-493">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="d6d80-494">Você precisará garantir que o objeto de caixa de correio seja licenciado corretamente para não afetar o serviço de email.</span><span class="sxs-lookup"><span data-stu-id="d6d80-494">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="d6d80-495">Um script de exemplo para remover os planos de serviço em um MailUser no Contoso.onmicrosoft.com locatário é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="d6d80-495">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="d6d80-496">Os resultados do conjunto de ServicePlans atribuídos são mostrados aqui.</span><span class="sxs-lookup"><span data-stu-id="d6d80-496">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="d6d80-497">O PrimarySMTPAddress do usuário não está mais limpo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-497">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="d6d80-498">O fabrikam.com domínio não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.</span><span class="sxs-lookup"><span data-stu-id="d6d80-498">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="d6d80-499">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6d80-499">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="d6d80-500">Quando msExchRemoteRecipientType for definido como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de limpeza de proxy no Azure removerá domínios não proprietários e redefinirá o primarySMTP para um domínio de propriedade.</span><span class="sxs-lookup"><span data-stu-id="d6d80-500">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="d6d80-501">Ao limpar msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais.</span><span class="sxs-lookup"><span data-stu-id="d6d80-501">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="d6d80-502">Abaixo está o conjunto completo de possíveis Planos de Serviço que incluem o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6d80-502">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="d6d80-503">Nome</span><span class="sxs-lookup"><span data-stu-id="d6d80-503">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="d6d80-504">Armazenamento avançado de Descoberta Virtual (500 GB)</span><span class="sxs-lookup"><span data-stu-id="d6d80-504">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="d6d80-505">Sistema de Proteção de Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="d6d80-505">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="d6d80-506">Prevenção contra Perda de Dados</span><span class="sxs-lookup"><span data-stu-id="d6d80-506">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="d6d80-507">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="d6d80-507">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="d6d80-508">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="d6d80-508">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="d6d80-509">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="d6d80-509">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="d6d80-510">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="d6d80-510">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="d6d80-511">Exchange Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="d6d80-511">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="d6d80-512">Exchange Online (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="d6d80-512">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="d6d80-513">Arquivamento do Exchange Online para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-513">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="d6d80-514">Arquivamento do Exchange Online para Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d6d80-514">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="d6d80-515">Complemento do usuário inativo do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-515">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="d6d80-516">Quiosque do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-516">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="d6d80-517">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="d6d80-517">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="d6d80-518">Exchange Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="d6d80-518">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="d6d80-519">POP do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-519">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="d6d80-520">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6d80-520">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="d6d80-521">Barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="d6d80-521">Information Barriers</span></span>                              |
   | <span data-ttu-id="d6d80-522">Proteção de Informações para o Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="d6d80-522">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="d6d80-523">Proteção de informações para o Office 365 – Padrão</span><span class="sxs-lookup"><span data-stu-id="d6d80-523">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="d6d80-524">Insights by MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="d6d80-524">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="d6d80-525">Auditoria Avançada do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6d80-525">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="d6d80-526">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="d6d80-526">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="d6d80-527">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="d6d80-527">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="d6d80-528">Microsoft MyAnalytics (Completo)</span><span class="sxs-lookup"><span data-stu-id="d6d80-528">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="d6d80-529">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="d6d80-529">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="d6d80-530">Microsoft Defender para Office 365 (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="d6d80-530">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="d6d80-531">Microsoft Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="d6d80-531">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="d6d80-532">Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="d6d80-532">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="d6d80-533">Criptografia Premium no Office 365</span><span class="sxs-lookup"><span data-stu-id="d6d80-533">Premium Encryption in Office 365</span></span>                  |
