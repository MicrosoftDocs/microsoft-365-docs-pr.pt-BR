---
title: Migração de caixa de correio de vários locatários
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
ms.openlocfilehash: f649a72dc5569e8aec46347df295aa3ff9d93613
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177131"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="e0c43-103">Migração de caixa de correio de locatário cruzado (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="e0c43-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="e0c43-104">Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço do Exchange Online, ele teria que externamente-las completamente para o local e, em seguida, integrá-las a um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="e0c43-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="e0c43-105">Com o novo recurso de migração de caixa de correio de vários locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências de infra-estrutura mínimas em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="e0c43-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="e0c43-106">Isso remove a necessidade de externamente e caixas de correio integradas.</span><span class="sxs-lookup"><span data-stu-id="e0c43-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="e0c43-107">Normalmente, durante mesclagens ou divestitures, você precisa da capacidade de mover os usuários e o conteúdo para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="e0c43-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="e0c43-108">Quando o administrador de locatário de destino executa a movimentação, ela é chamada de movimentação de recepção, semelhante às migrações de integração local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="e0c43-109">As movimentações de caixa de correio do Exchange entre locatários são totalmente autoatendidas por administradores de locatários, usando interfaces conhecidas que podem ser inseridas em scripts nos fluxos de trabalho maiores necessários para fazer a transição de usuários para sua nova organização.</span><span class="sxs-lookup"><span data-stu-id="e0c43-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="e0c43-110">Os administradores podem usar o `New-MigrationBatch` cmdlet, disponível por meio da função de gerenciamento mover caixas de correio, para executar movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="e0c43-111">O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e a finalização da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="e0c43-112">Os usuários que estão migrando devem estar presentes no sistema de locatário do Exchange Online como MailUsers, marcados com atributos específicos para habilitar movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="e0c43-113">O sistema falhará em movimentações para usuários que não estejam configurados corretamente no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="e0c43-114">Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="e0c43-115">Esse processo deixa o MailUser herdado no locatário de origem e permite um período de coexistência e roteamento de email.</span><span class="sxs-lookup"><span data-stu-id="e0c43-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="e0c43-116">Quando o processo de negócios permitir, o locatário de origem poderá remover o MailUser de origem ou convertê-lo em um contato de email.</span><span class="sxs-lookup"><span data-stu-id="e0c43-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="e0c43-117">Há suporte para as migrações de caixa de correio do Exchange entre locatários em locatários apenas híbridos ou em nuvem, ou qualquer combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="e0c43-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="e0c43-118">Este artigo descreve o processo de movimentações de caixa de correio de locatários cruzados e fornece orientação sobre como preparar locatários de origem e de destino para a movimentação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="e0c43-119">Preparar locatários de origem e de destino</span><span class="sxs-lookup"><span data-stu-id="e0c43-119">Preparing source and target tenants</span></span>

<span data-ttu-id="e0c43-120">O recurso de migração de caixa de correio do Exchange de locatário cruzado requer autorização e escopo para migrações entre os locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="e0c43-121">Usando as soluções de armazenamento de aplicativo empresarial e de repositório de chaves do Azure, os administradores de locatários agora são habilitados para gerenciar a autorização e o escopo de migrações de caixa de correio do Exchange Online de um locatário para outro.</span><span class="sxs-lookup"><span data-stu-id="e0c43-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="e0c43-122">As movimentações de caixa de correio de vários locatários dão suporte a um modelo de convite e consentimento para estabelecer um aplicativo do Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="e0c43-123">Também são necessários componentes adicionais, como um relacionamento de organização e um ponto de extremidade de migração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="e0c43-124">Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário do MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="e0c43-125">Consulte [preparar objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.</span><span class="sxs-lookup"><span data-stu-id="e0c43-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0c43-126">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e0c43-126">Prerequisites</span></span>

<span data-ttu-id="e0c43-127">O recurso de movimentação de caixa de correio de vários locatários requer o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) para estabelecer um aplicativo do Azure específico de par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para outro, removendo quaisquer requisitos para compartilhar certificados/segredos entre os locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="e0c43-128">Antes de começar, verifique se você tem as permissões necessárias para executar os scripts de implantação a fim de configurar o Azure Key Vault, mover o aplicativo de caixa de correio, o ponto de extremidade de migração do EXO e o relacionamento de organização do EXO.</span><span class="sxs-lookup"><span data-stu-id="e0c43-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="e0c43-129">Normalmente, o administrador global tem permissão para executar todas as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="e0c43-130">Além disso, os grupos de segurança habilitados para email no locatário de origem são necessários antes de executar a instalação.</span><span class="sxs-lookup"><span data-stu-id="e0c43-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="e0c43-131">Esses grupos são usados para escopo a lista de caixas de correio que podem ser movidas de um locatário de origem (ou às vezes chamado de recurso) para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="e0c43-132">Isso permite que o administrador do locatário de origem restrinja ou escopo o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários indesejados sejam migrados.</span><span class="sxs-lookup"><span data-stu-id="e0c43-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="e0c43-133">Não há suporte para grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="e0c43-133">Nested groups are not supported.</span></span>

<span data-ttu-id="e0c43-134">Você também precisará se comunicar com sua empresa parceira confiável (com a qual você vai mover as caixas de correio) para obter sua ID de locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0c43-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="e0c43-135">Esta ID de locatário é usada no campo relação de organização `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="e0c43-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="e0c43-136">Para obter a ID do locatário de uma assinatura, entre no centro de administração do Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="e0c43-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="e0c43-137">Clique no ícone Copiar da propriedade ID do locatário para copiá-lo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="e0c43-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="e0c43-138">Veja como funciona o processo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg" alt-text="Preparação do locatário para migração de caixa de correio.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="e0c43-140">Preparar locatários</span><span class="sxs-lookup"><span data-stu-id="e0c43-140">Prepare tenants</span></span>

<span data-ttu-id="e0c43-141">Em um nível alto, as seguintes ações de configuração ocorrerão durante a execução dos scripts de instalação.</span><span class="sxs-lookup"><span data-stu-id="e0c43-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="e0c43-142">Prepare o locatário de destino:</span><span class="sxs-lookup"><span data-stu-id="e0c43-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="e0c43-143">Se um grupo de recursos do Azure existente não for fornecido, será criado um novo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="e0c43-144">Se um cofre de chaves existente não for fornecido, será criado um novo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="e0c43-145">Uma nova política de acesso é criada para o aplicativo de migração de caixa de correio (SCRIPT) do Office 365 do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0c43-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="e0c43-146">Um novo certificado é criado (ou existente, se especificado) para manter o segredo para o aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="e0c43-147">Um novo aplicativo do Azure AD é criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="e0c43-148">O certificado/segredo é carregado no aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="e0c43-149">As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="e0c43-150">O script de implantação pausa até que o administrador de destino seja enviado a seu próprio aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="e0c43-151">O administrador do locatário de destino é enviado às permissões concedidas ao aplicativo (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="e0c43-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="e0c43-152">Um relacionamento de organização é criado para o locatário de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="e0c43-153">Um ponto de extremidade de migração é criado para extrair caixas de correio para o locatário (SCRIPT) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="e0c43-154">Prepare o locatário de origem:</span><span class="sxs-lookup"><span data-stu-id="e0c43-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="e0c43-155">O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de migração de caixa de correio do locatário de destino (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="e0c43-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="e0c43-156">O administrador do locatário de origem cria um grupo de segurança habilitado para email em seus locatários para conter a lista de caixas de correio que podem ser movidas pelo aplicativo de migração (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="e0c43-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="e0c43-157">Um relacionamento de organização é criado para o locatário de destino especificar o aplicativo de migração de caixa de correio deve ser usado para verificação de OAuth para aceitar a solicitação de movimentação (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="e0c43-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="e0c43-158">Instruções passo a passo para o administrador de locatários de destino</span><span class="sxs-lookup"><span data-stu-id="e0c43-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="e0c43-159">Baixe o script de SetupCrossTenantRelationshipForTargetTenant.ps1 para a configuração de locatário de destino do [repositório do GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="e0c43-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="e0c43-160">Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador no qual você executará o script.</span><span class="sxs-lookup"><span data-stu-id="e0c43-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="e0c43-161">Crie uma conexão do PowerShell remoto para o locatário de destino do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0c43-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="e0c43-162">Novamente, verifique se você tem as permissões necessárias para executar os scripts de implantação a fim de configurar o armazenamento do Azure Key Vault e o certificado, mover o aplicativo de caixa de correio, o ponto de extremidade de migração do EXO e o relacionamento de organização do EXO.</span><span class="sxs-lookup"><span data-stu-id="e0c43-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="e0c43-163">Altere o diretório de pasta de arquivo para o local do script ou verifique se o script está atualmente salvo no local em sua sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0c43-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="e0c43-164">Execute o script com os seguintes parâmetros e valores.</span><span class="sxs-lookup"><span data-stu-id="e0c43-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="e0c43-165">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="e0c43-165">Parameter</span></span> | <span data-ttu-id="e0c43-166">Valor</span><span class="sxs-lookup"><span data-stu-id="e0c43-166">Value</span></span> | <span data-ttu-id="e0c43-167">Obrigatório ou opcional</span><span class="sxs-lookup"><span data-stu-id="e0c43-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="e0c43-168">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e0c43-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="e0c43-169">Domínio do locatário de origem, como a Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0c43-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="e0c43-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-170">Required</span></span> |
    | <span data-ttu-id="e0c43-171">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="e0c43-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="e0c43-172">Endereço de email do administrador do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="e0c43-173">Este é o administrador do locatário de origem que será consentido no uso do aplicativo de migração de caixa de correio enviado do administrador de destino. Esse é o administrador que receberá o convite de email para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="e0c43-174">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-174">Required</span></span> |
    | <span data-ttu-id="e0c43-175">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e0c43-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="e0c43-176">Domínio de locatário de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0c43-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="e0c43-177">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-177">Required</span></span> |
    | <span data-ttu-id="e0c43-178">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="e0c43-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="e0c43-179">ID da organização do locatário de origem (GUID).</span><span class="sxs-lookup"><span data-stu-id="e0c43-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="e0c43-180">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-180">Required</span></span> |
    | <span data-ttu-id="e0c43-181">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="e0c43-181">-SubscriptionId</span></span>                             | <span data-ttu-id="e0c43-182">A assinatura do Azure a ser usada para criar recursos.</span><span class="sxs-lookup"><span data-stu-id="e0c43-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="e0c43-183">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-183">Required</span></span> |
    | <span data-ttu-id="e0c43-184">-O resourcegroup</span><span class="sxs-lookup"><span data-stu-id="e0c43-184">-ResourceGroup</span></span>                              | <span data-ttu-id="e0c43-185">Nome do grupo de recursos do Azure que contém ou conterá o cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="e0c43-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="e0c43-186">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-186">Required</span></span> |
    | <span data-ttu-id="e0c43-187">-Keyvaultname</span><span class="sxs-lookup"><span data-stu-id="e0c43-187">-KeyVaultName</span></span>                               | <span data-ttu-id="e0c43-188">Instância do Azure Key Vault que armazenará seu certificado/segredo de aplicativo de migração de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="e0c43-189">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-189">Required</span></span> |
    | <span data-ttu-id="e0c43-190">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="e0c43-190">-CertificateName</span></span>                            | <span data-ttu-id="e0c43-191">Nome do certificado ao gerar ou pesquisar o certificado no cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="e0c43-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="e0c43-192">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-192">Required</span></span> |
    | <span data-ttu-id="e0c43-193">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="e0c43-193">-CertificateSubject</span></span>                         | <span data-ttu-id="e0c43-194">Nome do requerente do certificado do Azure Key Vault, como CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e0c43-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="e0c43-195">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-195">Required</span></span> |
    | <span data-ttu-id="e0c43-196">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="e0c43-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="e0c43-197">Aplicativo de migração de email a ser usado se um já tiver sido criado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="e0c43-198">Opcional</span><span class="sxs-lookup"><span data-stu-id="e0c43-198">Optional</span></span> |
    | <span data-ttu-id="e0c43-199">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="e0c43-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="e0c43-200">As permissões exigidas para o aplicativo de migração de caixa de correio, como o Exchange ou o MSGraph (Exchange para mover caixas de correio, MSGraph para usar este aplicativo para enviar um convite de link de consentimento para o locatário de recursos).</span><span class="sxs-lookup"><span data-stu-id="e0c43-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="e0c43-201">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e0c43-201">Required</span></span> |
    | <span data-ttu-id="e0c43-202">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="e0c43-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="e0c43-203">Parâmetro para usar o aplicativo criado para migração a ser usado para enviar o convite de consentimento para o administrador do locatário de origem. Se não estiver presente, solicitará as credenciais do administrador de destino para se conectar ao Gerenciador de convites do Azure e enviará o convite como administrador de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="e0c43-204">Opcional</span><span class="sxs-lookup"><span data-stu-id="e0c43-204">Optional</span></span> |
    | <span data-ttu-id="e0c43-205">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="e0c43-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="e0c43-206">A conta de armazenamento onde os logs de auditoria do Key Vault serão armazenados.</span><span class="sxs-lookup"><span data-stu-id="e0c43-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="e0c43-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="e0c43-207">Optional</span></span> |
    | <span data-ttu-id="e0c43-208">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="e0c43-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="e0c43-209">O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria de compartimento de chave.</span><span class="sxs-lookup"><span data-stu-id="e0c43-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="e0c43-210">Opcional</span><span class="sxs-lookup"><span data-stu-id="e0c43-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="e0c43-211">O script fará uma pausa e solicitará que você aceite ou concorde com o aplicativo de migração de caixa de correio do Exchange que foi criado durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="e0c43-212">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-212">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. <span data-ttu-id="e0c43-213">Uma URL será exibida na sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0c43-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="e0c43-214">Copie o link fornecido para o consentimento do locatário e cole-o em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="e0c43-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="e0c43-215">Entre com suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e0c43-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="e0c43-216">Quando a tela a seguir for apresentada, selecione **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="e0c43-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Caixa de diálogo aceitar permissões":::
    
9. <span data-ttu-id="e0c43-218">Volte para a sessão remota do PowerShell e pressione ENTER para continuar.</span><span class="sxs-lookup"><span data-stu-id="e0c43-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="e0c43-219">O script irá configurar os objetos de instalação restantes.</span><span class="sxs-lookup"><span data-stu-id="e0c43-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="e0c43-220">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="e0c43-221">A configuração do administrador de destino está concluída!</span><span class="sxs-lookup"><span data-stu-id="e0c43-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="e0c43-222">Instruções passo a passo para o administrador de locatários de origem</span><span class="sxs-lookup"><span data-stu-id="e0c43-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="e0c43-223">Entre na sua caixa de correio como-ResourceTenantAdminEmail especificado pelo administrador de destino durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="e0c43-224">Localize o convite de email do locatário de destino e, em seguida, **Selecione o botão introdução.**</span><span class="sxs-lookup"><span data-stu-id="e0c43-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Você foi invided caixa de diálogo":::

2. <span data-ttu-id="e0c43-226">Selecione **aceitar** para aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="e0c43-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissons":::

   > [!NOTE]
   > <span data-ttu-id="e0c43-228">Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino foi fornecido como uma URL direta que pode ser concedida para que você aceite o convite.</span><span class="sxs-lookup"><span data-stu-id="e0c43-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="e0c43-229">A URL deve estar na transcrição da sessão do PowerShell remoto do administrador de locatários de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="e0c43-230">No centro de administração do Microsoft 365 ou em uma sessão remota do PowerShell, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para pull (mover) do locatário de origem para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="e0c43-231">Você não precisa preencher este grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de configuração (script).</span><span class="sxs-lookup"><span data-stu-id="e0c43-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="e0c43-232">Não há suporte para grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="e0c43-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="e0c43-233">Baixe o script de SetupCrossTenantRelationshipForTargetResource.ps1 para a configuração de locatário de origem do repositório do GitHub [aqui](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="e0c43-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="e0c43-234">Crie uma conexão do PowerShell remoto para o locatário de origem com suas permissões de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0c43-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="e0c43-235">As permissões de administrador global não são necessárias para configurar o locatário de origem, somente o locatário de destino por causa do processo de criação de aplicativos do Azure.</span><span class="sxs-lookup"><span data-stu-id="e0c43-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="e0c43-236">Altere o diretório para o local do script ou verifique se o script está salvo atualmente no local em sua sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0c43-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="e0c43-237">Execute o script com os seguintes parâmetros e valores necessários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="e0c43-238">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="e0c43-238">Parameter</span></span> | <span data-ttu-id="e0c43-239">Valor</span><span class="sxs-lookup"><span data-stu-id="e0c43-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="e0c43-240">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="e0c43-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="e0c43-241">Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo para a migração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="e0c43-242">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e0c43-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="e0c43-243">Nome do domínio do locatário de origem, como a Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0c43-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="e0c43-244">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="e0c43-244">-TargetTenantDomain</span></span> | <span data-ttu-id="e0c43-245">Nome do domínio do locatário de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0c43-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="e0c43-246">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="e0c43-246">-ApplicationId</span></span> | <span data-ttu-id="e0c43-247">ID de aplicativo do Azure (GUID) do aplicativo usado para migração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="e0c43-248">ID de aplicativo disponível por meio de seu portal do Azure (Azure AD, aplicativos corporativos, nome do aplicativo, ID do aplicativo) ou incluído em seu email de convite.</span><span class="sxs-lookup"><span data-stu-id="e0c43-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="e0c43-249">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="e0c43-249">-TargetTenantId</span></span> | <span data-ttu-id="e0c43-250">ID do locatário do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="e0c43-251">Por exemplo, a ID de locatário do Azure AD do \. locatário onmicrosoft.com da contoso.</span><span class="sxs-lookup"><span data-stu-id="e0c43-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="e0c43-252">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="e0c43-253">A configuração do administrador de origem já está concluída!</span><span class="sxs-lookup"><span data-stu-id="e0c43-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="e0c43-254">Verificar configuração</span><span class="sxs-lookup"><span data-stu-id="e0c43-254">Verify setup</span></span>

<span data-ttu-id="e0c43-255">Verifique se as relações de organização em locatários de origem e de destino e ponto de extremidade de migração no destino foram criadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="e0c43-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="e0c43-256">Locatário de destino</span><span class="sxs-lookup"><span data-stu-id="e0c43-256">Target tenant</span></span>

<span data-ttu-id="e0c43-257">**Relação de organização**</span><span class="sxs-lookup"><span data-stu-id="e0c43-257">**Organization relationship**</span></span>

<span data-ttu-id="e0c43-258">Verifique se o objeto relationship da organização foi criado e configurado com este comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="e0c43-259">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0c43-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="e0c43-260">**Ponto de extremidade de migração**</span><span class="sxs-lookup"><span data-stu-id="e0c43-260">**Migration endpoint**</span></span>

<span data-ttu-id="e0c43-261">Verifique se o objeto de ponto de extremidade de migração foi criado e configurado com este comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="e0c43-262">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="e0c43-263">Locatário de origem</span><span class="sxs-lookup"><span data-stu-id="e0c43-263">Source tenant</span></span>

<span data-ttu-id="e0c43-264">**Relação de organização**</span><span class="sxs-lookup"><span data-stu-id="e0c43-264">**Organization relationship**</span></span>

<span data-ttu-id="e0c43-265">Verifique se o objeto relationship da organização foi criado e configurado com este comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="e0c43-266">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="e0c43-267">Mover caixas de correio de volta para a fonte original</span><span class="sxs-lookup"><span data-stu-id="e0c43-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="e0c43-268">Se for necessária uma caixa de correio de volta para o locatário de origem original, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de destino e de origem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="e0c43-269">O objeto de relação de organização existente será atualizado ou acrescentado, não recriado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="e0c43-270">Preparar objetos de usuário de destino para migração</span><span class="sxs-lookup"><span data-stu-id="e0c43-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="e0c43-271">Os usuários que estão migrando devem estar presentes no locatário de destino e no sistema do Exchange Online (como MailUsers) marcados com atributos específicos para habilitar movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="e0c43-272">O sistema falhará em movimentações para usuários que não estejam configurados corretamente no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="e0c43-273">A seção a seguir detalha os requisitos do objeto MailUser para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e0c43-274">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e0c43-274">Prerequisites</span></span>
  
<span data-ttu-id="e0c43-275">Você deve garantir que os seguintes objetos e atributos estejam definidos na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="e0c43-276">Para qualquer caixa de correio que se move de uma organização de origem, você deve provisionar um objeto MailUser na organização de destino:</span><span class="sxs-lookup"><span data-stu-id="e0c43-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="e0c43-277">O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto de usuário:</span><span class="sxs-lookup"><span data-stu-id="e0c43-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="e0c43-278">ExchangeGUID (fluxo direto da origem para o destino) – o GUID da caixa de correio deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="e0c43-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="e0c43-279">O processo de movimentação não continuará se não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="e0c43-280">ArchiveGUID (fluxo direto da origem para o destino) – o GUID de arquivo morto deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="e0c43-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="e0c43-281">O processo de movimentação não continuará se não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="e0c43-282">(Isso só será necessário se a caixa de correio de origem estiver habilitada para arquivo).</span><span class="sxs-lookup"><span data-stu-id="e0c43-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="e0c43-283">LegacyExchangeDN (fluxo como proxyAddress, "X500: <LegacyExchangeDN> ") – o legacyExchangeDN deve estar presente no destino MailUser como X500: ProxyAddress.</span><span class="sxs-lookup"><span data-stu-id="e0c43-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="e0c43-284">Os processos de movimentação não continuarão se não estiverem presentes no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="e0c43-285">UserPrincipalName – o UPN será alinhado à nova empresa de identidade ou de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="e0c43-286">SMTPAddress primário – o endereço SMTP principal será alinhado à nova empresa do usuário (por exemplo, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="e0c43-287">TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio do usuário atual hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="e0c43-288">Ao atribuir esse valor, verifique se você também está atribuindo PrimarySMTPAddress ou se esse valor definirá o PrimarySMTPAddress, que causará falhas de movimentação.</span><span class="sxs-lookup"><span data-stu-id="e0c43-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="e0c43-289">Não é possível adicionar endereços de proxy SMTP herdados da caixa de correio de origem ao MailUser de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="e0c43-290">Por exemplo, você não pode manter contoso.com no MEU nos objetos de locatário do fabrikam.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="e0c43-291">Os domínios são associados somente a um locatário do Azure AD ou do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0c43-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="e0c43-292">Exemplo de objeto MailUser de **destino** :</span><span class="sxs-lookup"><span data-stu-id="e0c43-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="e0c43-293">Atributo</span><span class="sxs-lookup"><span data-stu-id="e0c43-293">Attribute</span></span>             | <span data-ttu-id="e0c43-294">Valor</span><span class="sxs-lookup"><span data-stu-id="e0c43-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="e0c43-295">Alias</span><span class="sxs-lookup"><span data-stu-id="e0c43-295">Alias</span></span>                 | <span data-ttu-id="e0c43-296">LaraN</span><span class="sxs-lookup"><span data-stu-id="e0c43-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="e0c43-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="e0c43-297">RecipientType</span></span>         | <span data-ttu-id="e0c43-298">MailUser</span><span class="sxs-lookup"><span data-stu-id="e0c43-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="e0c43-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="e0c43-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="e0c43-300">MailUser</span><span class="sxs-lookup"><span data-stu-id="e0c43-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="e0c43-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e0c43-301">UserPrincipalName</span></span>     | <span data-ttu-id="e0c43-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="e0c43-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="e0c43-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="e0c43-304">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="e0c43-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="e0c43-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="e0c43-306">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="e0c43-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="e0c43-307">ExchangeGuid</span></span>          | <span data-ttu-id="e0c43-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="e0c43-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="e0c43-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="e0c43-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="e0c43-310">/o = First Organization/ou = grupo administrativo do Exchange</span><span class="sxs-lookup"><span data-stu-id="e0c43-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="e0c43-311">(FYDIBOHF23SPDLT)/cn = Recipients/cn = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="e0c43-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="e0c43-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="e0c43-312">EmailAddresses</span></span>        | <span data-ttu-id="e0c43-313">X500:/o = First Organization/ou = grupo administrativo do Exchange (FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="e0c43-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="e0c43-314">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="e0c43-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="e0c43-315">SMTP: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="e0c43-316">SMTP: Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="e0c43-317">Exemplo de objeto de caixa de correio de **origem** :</span><span class="sxs-lookup"><span data-stu-id="e0c43-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="e0c43-318">Atributo</span><span class="sxs-lookup"><span data-stu-id="e0c43-318">Attribute</span></span>             | <span data-ttu-id="e0c43-319">Valor</span><span class="sxs-lookup"><span data-stu-id="e0c43-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="e0c43-320">Alias</span><span class="sxs-lookup"><span data-stu-id="e0c43-320">Alias</span></span>                 | <span data-ttu-id="e0c43-321">LaraN</span><span class="sxs-lookup"><span data-stu-id="e0c43-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="e0c43-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="e0c43-322">RecipientType</span></span>         | <span data-ttu-id="e0c43-323">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="e0c43-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="e0c43-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="e0c43-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="e0c43-325">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="e0c43-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="e0c43-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="e0c43-326">UserPrincipalName</span></span>     | <span data-ttu-id="e0c43-327">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="e0c43-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="e0c43-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="e0c43-329">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="e0c43-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="e0c43-330">ExchangeGuid</span></span>          | <span data-ttu-id="e0c43-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="e0c43-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="e0c43-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="e0c43-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="e0c43-333">/o = First Organization/ou = grupo administrativo do Exchange</span><span class="sxs-lookup"><span data-stu-id="e0c43-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="e0c43-334">(FYDIBOHF23SPDLT)/cn = Recipients/cn = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="e0c43-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="e0c43-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="e0c43-335">EmailAddresses</span></span>        | <span data-ttu-id="e0c43-336">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="e0c43-337">SMTP: Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0c43-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="e0c43-338">Atributos adicionais podem ser incluídos na gravação híbrida do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0c43-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="e0c43-339">Caso contrário, elas deverão ser incluídas.</span><span class="sxs-lookup"><span data-stu-id="e0c43-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="e0c43-340">msExchBlockedSendersHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="e0c43-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="e0c43-341">msExchSafeRecipientsHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="e0c43-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="e0c43-342">msExchSafeSendersHash – grava novamente os dados do remetente seguro online e bloqueados de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="e0c43-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="e0c43-343">Se a caixa de correio de origem estiver no LitigationHold e o tamanho dos itens recuperáveis da caixa de correio de origem for maior do que o padrão de nosso banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor do que o tamanho</span><span class="sxs-lookup"><span data-stu-id="e0c43-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="e0c43-344">Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="e0c43-345">Essas instruções funcionarão apenas para a identidade híbrida executando o Azure AD Connect, pois os comandos a serem carimbados não são expostos aos administradores de locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="e0c43-346">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="e0c43-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="e0c43-347">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="e0c43-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="e0c43-348">Se a origem tiver litígio ou recuperação de item único habilitada, defina isso na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="e0c43-349">Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="e0c43-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="e0c43-350">Os locatários de destino não híbridos podem modificar a cota na pasta itens recuperáveis para o MailUsers antes da migração executando o seguinte comando para habilitar a retenção de litígio no objeto MailUser e aumentar a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="e0c43-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="e0c43-351">Observação isso não funcionará para locatários no híbrido.</span><span class="sxs-lookup"><span data-stu-id="e0c43-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="e0c43-352">Os usuários na organização de destino devem ser licenciados com assinaturas apropriadas do Exchange Online aplicáveis à organização.</span><span class="sxs-lookup"><span data-stu-id="e0c43-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="e0c43-353">Você pode aplicar uma licença com antecedência de uma movimentação de caixa de correio, mas somente depois que o destino MailUser estiver configurado corretamente com o ExchangeGUID e endereços de proxy.</span><span class="sxs-lookup"><span data-stu-id="e0c43-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="e0c43-354">A aplicação de uma licença antes da aplicação de ExchangeGUID resultará em uma nova caixa de correio configurada na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="e0c43-355">Quando você aplica uma licença a uma caixa de correio ou a um objeto MailUser, todos os tipos de SMTP proxyAddresses são depurados para garantir que somente os domínios verificados estão incluídos na matriz EmailAddress do Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0c43-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="e0c43-356">Você deve garantir que o MailUser de destino não tenha ExchangeGuid anterior que não corresponda à ExchangeGuid de origem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="e0c43-357">Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para o Exchange Online e configurado uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="e0c43-358">Se o MailUser de destino tiver sido licenciado anteriormente para ou tivesse um ExchangeGuid que não corresponde ao ExchangeGuid de origem, você precisará executar uma limpeza do MEU de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="e0c43-359">Para essas MEUs de nuvem, você pode executar o `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="e0c43-360">Esse processo é irreversível.</span><span class="sxs-lookup"><span data-stu-id="e0c43-360">This process is irreversible.</span></span> <span data-ttu-id="e0c43-361">Se o objeto tiver uma caixa de correio do softDeleted, ele não poderá ser restaurado após esse ponto.</span><span class="sxs-lookup"><span data-stu-id="e0c43-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="e0c43-362">Depois de desmarcada, no entanto, você pode sincronizar o ExchangeGuid correto para o objeto de destino e Sra conectará a caixa de correio de origem à caixa de correio de destino recém-criada.</span><span class="sxs-lookup"><span data-stu-id="e0c43-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="e0c43-363">(Faça referência ao blog EHLO no novo parâmetro.)</span><span class="sxs-lookup"><span data-stu-id="e0c43-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="e0c43-364">Encontre objetos que foram previamente caixas de correio usando esse comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="e0c43-365">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="e0c43-366">Limpe a caixa de correio excluída por software usando este comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="e0c43-367">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="e0c43-368">Executar migrações de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="e0c43-368">Perform mailbox migrations</span></span>

<span data-ttu-id="e0c43-369">As migrações de caixa de correio do Exchange entre locatários são enviadas como lotes de migração iniciados a partir do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="e0c43-370">Isso é semelhante à forma como os lotes de migração de integração funcionam ao migrar do Exchange no local para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0c43-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="e0c43-371">Criar lotes de migração</span><span class="sxs-lookup"><span data-stu-id="e0c43-371">Create Migration batches</span></span>

<span data-ttu-id="e0c43-372">Veja um exemplo de cmdlet de migração de exemplo para Iniciando off moves.</span><span class="sxs-lookup"><span data-stu-id="e0c43-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="e0c43-373">O endereço de email no arquivo CSV deve ser aquele especificado no locatário de destino, não no locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="e0c43-374">O envio em lote de migração também é compatível com o novo centro de administração do Exchange ao selecionar a opção de locatário cruzado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="e0c43-375">Atualizar o MailUsers local</span><span class="sxs-lookup"><span data-stu-id="e0c43-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="e0c43-376">Depois que a caixa de correio é movida da origem para o destino, você deve garantir que os usuários de email locais, tanto de origem quanto de destino, sejam atualizados com o novo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="e0c43-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="e0c43-377">Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso \. onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="e0c43-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="e0c43-378">Atualize os usuários de email com este targetAddress.</span><span class="sxs-lookup"><span data-stu-id="e0c43-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="e0c43-379">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e0c43-379">Frequently asked questions</span></span>
 
<span data-ttu-id="e0c43-380">**Precisamos atualizar o RemoteMailboxes na origem no local após a movimentação?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="e0c43-381">Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários do local de origem quando a caixa de correio do locatário de origem for movida para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="e0c43-382">Embora o roteamento de email possa seguir as indicações entre vários usuários de email com targetAddresses diferentes, pesquisas de disponibilidade para usuários de email devem direcionar o local do usuário de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="e0c43-383">Pesquisas de disponibilidade não causarão vários redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="e0c43-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="e0c43-384">**O conteúdo da pasta de chat do teams migram vários locatários?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="e0c43-385">Não, o conteúdo da pasta de chat do Teams não migra o locatário cruzado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="e0c43-386">**Como posso ver apenas as movimentações que são movimentações entre locatários, e não minha integração e remoções de remoção?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="e0c43-387">Use o `-flags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e0c43-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="e0c43-388">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="e0c43-389">**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="e0c43-390">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="e0c43-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="e0c43-391">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e os serviços de domínio do Active Directory local de destino (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="e0c43-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="e0c43-392">Se a origem tiver litígio ou recuperação de item único habilitada, defina isso na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="e0c43-393">Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="e0c43-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="e0c43-394">**Como podemos acessar o Outlook no dia 1 após a movimentação da caixa de correio de uso?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="e0c43-395">Como apenas um locatário pode ser proprietário de um domínio, o primeiro SMTPAddress primário não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; Apenas os domínios associados ao novo locatário.</span><span class="sxs-lookup"><span data-stu-id="e0c43-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="e0c43-396">O Outlook usa o novo UPN Users para autenticar o serviço e o perfil do Outlook espera localizar o SMTPAddress primário herdado para corresponder à caixa de correio no sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="e0c43-397">Como o endereço herdado não está no sistema de destino, o perfil do Outlook não se conectará para localizar a caixa de correio recentemente movida.</span><span class="sxs-lookup"><span data-stu-id="e0c43-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="e0c43-398">Para essa implantação inicial, os usuários precisarão reconstruir o perfil com o novo endereço SMTP principal e o próprio UPN e sincronizar novamente o conteúdo do OST.</span><span class="sxs-lookup"><span data-stu-id="e0c43-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="e0c43-399">Planeje conforme o lote de usuários para conclusão.</span><span class="sxs-lookup"><span data-stu-id="e0c43-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="e0c43-400">Você precisa considerar a capacidade e a utilização da rede quando os perfis de cliente do Outlook são criados e os arquivos OST e OAB subsequentes são baixados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="e0c43-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="e0c43-401">**O que as funções RBAC do Exchange precisam ser membro para configurar ou concluir uma movimentação entre vários locatários?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="e0c43-402">Há uma matriz de funções com base na pressuposição de tarefas delegadas ao executar uma movimentação de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="e0c43-403">No momento, são necessárias duas funções:</span><span class="sxs-lookup"><span data-stu-id="e0c43-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="e0c43-404">A primeira função é para uma tarefa de configuração única que estabelece a autorização de mover o conteúdo para dentro ou para fora do seu limite de locatário/organização.</span><span class="sxs-lookup"><span data-stu-id="e0c43-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="e0c43-405">Como a transferência de dados do controle organizacional é uma preocupação crucial para todas as empresas, decidimos com a maior função atribuída do administrador da organização (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="e0c43-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="e0c43-406">Essa função deve alterar ou configurar um novo OrganizationRelationship que define o-MailboxMoveCapability com a organização remota.</span><span class="sxs-lookup"><span data-stu-id="e0c43-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="e0c43-407">Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de compartilhamento federado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="e0c43-408">A função de execução dos comandos de movimentação real pode ser delegada a uma função de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="e0c43-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="e0c43-409">A função das caixas de correio de movimentação é atribuída à capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="e0c43-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="e0c43-410">**Como direcionarmos qual endereço SMTP está selecionado para o targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para a conversão MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="e0c43-411">As movimentações de caixa de correio do Exchange usando o Sra targetAddress na caixa de correio de origem original ao converter em um MailUser correspondendo a um endereço de email (proxyAddress) no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="e0c43-412">O processo usa o valor-TargetDeliveryDomain passado para o comando move e, em seguida, verifica se há um proxy correspondente para esse domínio no lado de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="e0c43-413">Quando encontramos uma correspondência, a proxyAddress correspondente é usada para definir o ExternalEmailAddress (targetAddress) no objeto Mailbox convertido (agora MailUser).</span><span class="sxs-lookup"><span data-stu-id="e0c43-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="e0c43-414">**Como a transição de permissões de caixa de correio?**</span><span class="sxs-lookup"><span data-stu-id="e0c43-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="e0c43-415">As permissões de caixa de correio incluem enviar em nome de e acesso à caixa de correio:</span><span class="sxs-lookup"><span data-stu-id="e0c43-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="e0c43-416">Enviar em nome de (AD: publicDelegates) armazena o DN dos destinatários com acesso à caixa de correio de um usuário como um representante.</span><span class="sxs-lookup"><span data-stu-id="e0c43-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="e0c43-417">Esse valor é armazenado no Active Directory e, no momento, não é movido como parte da transição da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e0c43-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="e0c43-418">Se a caixa de correio de origem tiver publicDelegates definido, será necessário recarimbar o publicDelegates na caixa de correio de destino quando a conversão de MEU para caixa de correio for concluída no ambiente de destino usando o `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` comando.</span><span class="sxs-lookup"><span data-stu-id="e0c43-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="e0c43-419">As permissões de caixa de correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade de segurança e o representante forem movidos para o sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="e0c43-420">Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e0c43-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="e0c43-421">Após a movimentação da caixa de correio ser concluída para o TargetCompany.onmicrosoft.com, as mesmas permissões são configuradas no diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="e0c43-422">Exemplos usando *Get-MailboxPermission* para TestUser_7 nos locatários de origem e de destino são mostrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="e0c43-423">Os cmdlets do Exchange são prefixados com a origem e o destino de acordo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="e0c43-424">Veja um exemplo da saída da permissão de caixa de correio antes de mover.</span><span class="sxs-lookup"><span data-stu-id="e0c43-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="e0c43-425">Veja um exemplo da saída da permissão de caixa de correio após a movimentação.</span><span class="sxs-lookup"><span data-stu-id="e0c43-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="e0c43-426">Não há suporte para permissões de caixa de correio e calendário entre locatários.</span><span class="sxs-lookup"><span data-stu-id="e0c43-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="e0c43-427">Você deve organizar entidades e representantes em lotes de movimentação consolidada para que essas caixas de correio conectadas sejam transformadas ao mesmo tempo do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="e0c43-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="e0c43-428">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="e0c43-428">Known issues</span></span> 

-  <span data-ttu-id="e0c43-429">**Problema: os arquivos mortos expandidos automáticos não podem ser migrados.**</span><span class="sxs-lookup"><span data-stu-id="e0c43-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="e0c43-430">O recurso de migração entre locatários suporta migrações da caixa de correio principal e caixa de correio de arquivo morto para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="e0c43-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="e0c43-431">No entanto, se o usuário na fonte tiver um arquivo morto de expansão automática – o que significa mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos adicionais.</span><span class="sxs-lookup"><span data-stu-id="e0c43-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="e0c43-432">**Problema: o Cloud MailUsers com bloqueio de proxyAddress SMTP não proprietário Sra move o plano de fundo.**</span><span class="sxs-lookup"><span data-stu-id="e0c43-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="e0c43-433">Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços de proxy SMTP pertençam à organização de locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="e0c43-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="e0c43-434">Se uma proxyAddress SMTP existir no usuário de email de destino que não pertença ao locatário local, a conversão do MailUser para a caixa de correio será impedida.</span><span class="sxs-lookup"><span data-stu-id="e0c43-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="e0c43-435">Isso se deve à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário):</span><span class="sxs-lookup"><span data-stu-id="e0c43-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="e0c43-436">Ao sincronizar usuários do no local usando o Azure AD Connect, configure os objetos do MailUser no local com o ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso \. onmicrosoft.com) e você carimba o PrimarySmtpAddress como um domínio que reside no locatário de destino (Lara. Newton@northwind \. com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="e0c43-437">Esses valores são sincronizados com o locatário, e um usuário de email apropriado é provisionado e está pronto para a migração.</span><span class="sxs-lookup"><span data-stu-id="e0c43-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="e0c43-438">Um objeto de exemplo é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="e0c43-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="e0c43-439">O endereço *contoso. onmicrosoft \. com* *não* está presente na matriz emailaddresss/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="e0c43-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="e0c43-440">**Problema: os objetos MailUser com endereços SMTP "externos" primários são modificados/redefinidos para os domínios "internos" da empresa afirmados**</span><span class="sxs-lookup"><span data-stu-id="e0c43-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="e0c43-441">Os objetos MailUser são ponteiros para caixas de correio não locais.</span><span class="sxs-lookup"><span data-stu-id="e0c43-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="e0c43-442">No caso de migrações de caixa de correio de locatário cruzado, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem).</span><span class="sxs-lookup"><span data-stu-id="e0c43-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="e0c43-443">O MailUsers terá um ExternalEmailAddress (targetAddress) que aponta para o endereço SMTP da caixa de correio real (ProxyTest \@ fabrikam \. onmicrosoft.com) e endereço primarySMTP que representa o endereço SMTP exibido do usuário da caixa de correio no diretório.</span><span class="sxs-lookup"><span data-stu-id="e0c43-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="e0c43-444">Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="e0c43-445">No entanto, depois que um objeto de plano do serviço do Exchange é aplicado ao MailUser via operações de licenciamento, o endereço SMTP principal é modificado para ser exibido como um domínio verificado pela organização local (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e0c43-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="e0c43-446">Há dois motivos possíveis:</span><span class="sxs-lookup"><span data-stu-id="e0c43-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="e0c43-447">Quando qualquer plano de serviço do Exchange é aplicado a um MailUser, o processo do Azure AD começa a impor o scrubbing de proxy para garantir que a organização local não possa enviar emails, falsificar ou email de outro locatário.</span><span class="sxs-lookup"><span data-stu-id="e0c43-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="e0c43-448">Qualquer endereço SMTP em um objeto Recipient com estes planos de serviço será removido se o endereço não for verificado pela organização local.</span><span class="sxs-lookup"><span data-stu-id="e0c43-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="e0c43-449">Como é o caso no exemplo, o \. domínio com do FABIKAM não é verificado pelo locatário do \. onmicrosoft.com da Contoso, portanto, a depuração remove esse \. domínio com da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="e0c43-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="e0c43-450">Se quiser persistir esse domínio externo no MailUser, antes da migração ou após a migração, você precisará alterar seus processos de migração para retirar as licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a marca externa esperada aplicada.</span><span class="sxs-lookup"><span data-stu-id="e0c43-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="e0c43-451">Você precisará garantir que o objeto de caixa de correio seja devidamente licenciado para não afetar o serviço de email.</span><span class="sxs-lookup"><span data-stu-id="e0c43-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="e0c43-452">Um script de exemplo para remover os planos de serviço em um MailUser no \. locatário da Contoso onmicrosoft.com é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="e0c43-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="e0c43-453">Os resultados no conjunto de onplans atribuídos são mostrados aqui.</span><span class="sxs-lookup"><span data-stu-id="e0c43-453">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="e0c43-454">O PrimarySMTPAddress do usuário não está mais depurado.</span><span class="sxs-lookup"><span data-stu-id="e0c43-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="e0c43-455">O domínio fabrikam.com não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.</span><span class="sxs-lookup"><span data-stu-id="e0c43-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="e0c43-456">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="e0c43-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="e0c43-457">Quando msExchRemoteRecipientType é definido como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de depuração de proxy no Azure removerá domínios não pertencentes e redefinirá o primarySMTP para um domínio de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e0c43-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="e0c43-458">Limpando msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais.</span><span class="sxs-lookup"><span data-stu-id="e0c43-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="e0c43-459">Veja a seguir o conjunto completo de possíveis planos de serviço que incluem o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0c43-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="e0c43-460">Nome</span><span class="sxs-lookup"><span data-stu-id="e0c43-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="e0c43-461">Armazenamento de descoberta eletrônica avançado (500GB)</span><span class="sxs-lookup"><span data-stu-id="e0c43-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="e0c43-462">Sistema de Proteção de Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="e0c43-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="e0c43-463">Prevenção contra Perda de Dados</span><span class="sxs-lookup"><span data-stu-id="e0c43-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="e0c43-464">Serviços CAL do Exchange Enterprise (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="e0c43-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="e0c43-465">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="e0c43-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="e0c43-466">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="e0c43-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="e0c43-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="e0c43-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="e0c43-468">Exchange Online (plano 1)</span><span class="sxs-lookup"><span data-stu-id="e0c43-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="e0c43-469">Exchange Online (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="e0c43-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="e0c43-470">Arquivamento do Exchange Online para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0c43-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="e0c43-471">Arquivamento do Exchange Online para Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e0c43-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="e0c43-472">Complemento de usuário inativo do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0c43-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="e0c43-473">Quiosque do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0c43-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="e0c43-474">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="e0c43-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="e0c43-475">Exchange Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="e0c43-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="e0c43-476">POP do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0c43-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="e0c43-477">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0c43-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="e0c43-478">Barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="e0c43-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="e0c43-479">Proteção de Informações para o Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="e0c43-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="e0c43-480">Proteção de informações para o Office 365 – Padrão</span><span class="sxs-lookup"><span data-stu-id="e0c43-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="e0c43-481">Ideias do myAnalytics</span><span class="sxs-lookup"><span data-stu-id="e0c43-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="e0c43-482">Auditoria avançada da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0c43-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="e0c43-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="e0c43-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="e0c43-484">Centro de negócios da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0c43-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="e0c43-485">Microsoft MyAnalytics (Completo)</span><span class="sxs-lookup"><span data-stu-id="e0c43-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="e0c43-486">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="e0c43-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="e0c43-487">Proteção contra Ameaças do Office 365 Advanced (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="e0c43-487">Office 365 Advanced Threat Protection (Plan 1)</span></span>    |
   | <span data-ttu-id="e0c43-488">Proteção contra Ameaças do Office 365 Advanced (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="e0c43-488">Office 365 Advanced Threat Protection (Plan 2)</span></span>    |
   | <span data-ttu-id="e0c43-489">Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0c43-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="e0c43-490">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="e0c43-490">Outlook Customer Manager</span></span>                          |
   | <span data-ttu-id="e0c43-491">Criptografia Premium no Office 365</span><span class="sxs-lookup"><span data-stu-id="e0c43-491">Premium Encryption in Office 365</span></span>                  |
   || 
 