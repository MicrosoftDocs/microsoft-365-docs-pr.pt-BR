---
title: Migração de caixa de correio entre locatários
description: Como mover caixas de correio entre locatários do Microsoft 365 ou Office 365.
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
ms.openlocfilehash: 4296879b36e26f11f945105ccebea351ad88314d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029521"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="844cd-103">Migração de caixa de correio entre locatários (visualização)</span><span class="sxs-lookup"><span data-stu-id="844cd-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="844cd-104">Anteriormente, quando um locatário do Exchange Online precisava mover caixas de correio para outro locatário no mesmo serviço do Exchange Online, ele teria que removê-las completamente para o local e, em seguida, abordá-las para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="844cd-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="844cd-105">Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="844cd-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="844cd-106">Isso elimina a necessidade de remoção e integração de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="844cd-107">Normalmente, durante fusões ou desa instituções, você precisa da capacidade de mover usuários e conteúdo para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="844cd-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="844cd-108">Quando o administrador do locatário de destino executa a movimentação, ela é chamada de movimentação Pull, semelhante às migrações de integração na nuvem no local.</span><span class="sxs-lookup"><span data-stu-id="844cd-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="844cd-109">As movimentações de caixa de correio entre locatários do Exchange são totalmente autoatendida por administradores de locatários, usando interfaces conhecidas que podem ser scripts em fluxos de trabalho maiores necessários para fazer a transição de usuários para a nova organização.</span><span class="sxs-lookup"><span data-stu-id="844cd-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="844cd-110">Os administradores podem usar o cmdlet, disponível por meio da função de gerenciamento Mover Caixas de Correio, para executar movimentações `New-MigrationBatch` entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="844cd-111">O processo de movimentação inclui verificações de autorização de locatário durante a sincronização e finalização da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="844cd-112">Os usuários que estão migrando devem estar presentes no sistema do Exchange Online do locatário de destino como MailUsers, marcados com atributos específicos para habilitar as movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="844cd-113">O sistema falhará nas movimentações para usuários que não estão devidamente definidos no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="844cd-114">Quando as movimentações são concluídas, a caixa de correio do sistema de origem é convertida em MailUser e o targetAddress (mostrado como ExternalEmailAddress no Exchange) é marcado com o endereço de roteamento para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="844cd-115">Esse processo deixa o MailUser herdado no locatário de origem e permite um período de co-existência e roteamento de email.</span><span class="sxs-lookup"><span data-stu-id="844cd-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="844cd-116">Quando os processos empresariais permitem, o locatário de origem pode remover o MailUser de origem ou convertê-los em um contato de email.</span><span class="sxs-lookup"><span data-stu-id="844cd-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="844cd-117">As migrações de caixa de correio entre locatários do Exchange são suportadas para locatários somente em nuvem ou híbrida ou qualquer combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="844cd-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="844cd-118">Este artigo descreve o processo de movimentações de caixa de correio entre locatários e fornece orientações sobre como preparar locatários de origem e destino para a movimentação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="844cd-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="844cd-119">Preparando locatários de origem e destino</span><span class="sxs-lookup"><span data-stu-id="844cd-119">Preparing source and target tenants</span></span>

<span data-ttu-id="844cd-120">O recurso de migração de caixa de correio do Exchange entre locatários exige autorização e o exame para migrações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="844cd-121">Usando o aplicativo Azure Enterprise e as soluções de armazenamento do Key Vault, os administradores de locatários agora têm permissão para gerenciar a autorização e o controle de migrações de caixa de correio do Exchange Online de um locatário para outro.</span><span class="sxs-lookup"><span data-stu-id="844cd-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="844cd-122">As movimentações de caixa de correio entre locatários suportam um modelo de convite e consentimento para estabelecer um aplicativo do Azure Active Directory (Azure AD) usado para autenticação entre um par de locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="844cd-123">Componentes adicionais, como um relacionamento de organização e um ponto de extremidade de migração, também são necessários.</span><span class="sxs-lookup"><span data-stu-id="844cd-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="844cd-124">Esta seção não inclui as etapas específicas necessárias para preparar os objetos de usuário MailUser no diretório de destino, nem inclui o comando de exemplo para enviar um lote de migração.</span><span class="sxs-lookup"><span data-stu-id="844cd-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="844cd-125">Consulte Preparar [objetos de usuário de destino para migração](#prepare-target-user-objects-for-migration) para essas informações.</span><span class="sxs-lookup"><span data-stu-id="844cd-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="844cd-126">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="844cd-126">Prerequisites</span></span>

<span data-ttu-id="844cd-127">O recurso de movimentação de caixa de correio entre locatários exige que o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) estabeleça um aplicativo do Azure específico de par de locatários para armazenar e acessar com segurança o certificado/segredo usado para autenticar e autorizar a migração de caixa de correio de um locatário para o outro, removendo quaisquer requisitos para compartilhar certificados/segredos entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="844cd-128">Antes de começar, certifique-se de ter as permissões necessárias para executar os scripts de implantação a fim de configurar o Azure Key Vault, o aplicativo Mover Caixa de Correio, o Ponto de Extremidade de Migração EXO e o Relacionamento de Organização EXO.</span><span class="sxs-lookup"><span data-stu-id="844cd-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="844cd-129">Normalmente, o Administrador Global tem permissão para executar todas as etapas de configuração.</span><span class="sxs-lookup"><span data-stu-id="844cd-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="844cd-130">Além disso, os grupos de segurança habilitados para email no locatário de origem são necessários antes da execução da instalação.</span><span class="sxs-lookup"><span data-stu-id="844cd-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="844cd-131">Esses grupos são usados para escopo da lista de caixas de correio que podem mudar do locatário de origem (ou às vezes chamado de recurso) para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="844cd-132">Isso permite que o administrador do locatário de origem restrinja ou denove o conjunto específico de caixas de correio que precisam ser movidas, impedindo que usuários não intencionais sejam migrados.</span><span class="sxs-lookup"><span data-stu-id="844cd-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="844cd-133">Não há suporte para grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="844cd-133">Nested groups are not supported.</span></span>

<span data-ttu-id="844cd-134">Você também precisará se comunicar com sua empresa parceira confiável (com quem você vai mover caixas de correio) para obter a ID de locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="844cd-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="844cd-135">Essa ID de locatário é usada no campo Relacionamento da `DomainName` Organização.</span><span class="sxs-lookup"><span data-stu-id="844cd-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="844cd-136">Para obter a ID de locatário de uma assinatura, entre no centro de administração do Microsoft 365 e vá para [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="844cd-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="844cd-137">Clique no ícone de cópia da propriedade de ID de locatário para copiá-lo para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="844cd-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="844cd-138">Veja como funciona o processo.</span><span class="sxs-lookup"><span data-stu-id="844cd-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparação do locatário para migração de caixa de correio.":::

<span data-ttu-id="844cd-140">[Veja uma versão maior desta imagem.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="844cd-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="844cd-141">Preparar locatários</span><span class="sxs-lookup"><span data-stu-id="844cd-141">Prepare tenants</span></span>

<span data-ttu-id="844cd-142">Em um nível alto, as seguintes ações de configuração ocorrem ao executar os scripts de instalação.</span><span class="sxs-lookup"><span data-stu-id="844cd-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="844cd-143">Prepare o locatário de destino:</span><span class="sxs-lookup"><span data-stu-id="844cd-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="844cd-144">Se um Grupo de Recursos do Azure existente não for fornecido, um novo será criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="844cd-145">Se um Key Vault existente não for fornecido, um novo será criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="844cd-146">Uma nova Política de Acesso é criada para o aplicativo de Migração de Caixa de Correio do Exchange Online (SCRIPT) do Office 365.</span><span class="sxs-lookup"><span data-stu-id="844cd-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="844cd-147">Um novo certificado é criado (ou existente, se especificado) para manter o segredo do aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="844cd-148">Um novo aplicativo do Azure AD é criado (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="844cd-149">O certificado/segredo é carregado no aplicativo de migração (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="844cd-150">As permissões de migração de caixa de correio são atribuídas ao aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="844cd-151">O script de implantação pausa até que o administrador de destino consenta com seu próprio aplicativo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="844cd-152">O administrador do locatário de destino concorda com as permissões concedidas ao aplicativo (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="844cd-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="844cd-153">Um relacionamento de organização é criado para o locatário de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="844cd-154">Um ponto de extremidade de migração é criado para puxar caixas de correio para o locatário de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="844cd-155">Prepare o locatário de origem:</span><span class="sxs-lookup"><span data-stu-id="844cd-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="844cd-156">O administrador do locatário de origem aceita o consentimento para o convite do aplicativo de Migração de Caixa de Correio do locatário de destino (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="844cd-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="844cd-157">O administrador de locatários de origem cria um grupo de segurança habilitado para email em seu locatário para conter a lista de caixas de correio que podem ser movidas pelo aplicativo de migração (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="844cd-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="844cd-158">Um relacionamento de organização é criado para o locatário de destino especificando que o aplicativo de migração de caixa de correio deve ser usado para verificação OAuth para aceitar a solicitação de movimentação (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="844cd-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="844cd-159">Instruções passo a passo para o administrador do locatário de destino</span><span class="sxs-lookup"><span data-stu-id="844cd-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="844cd-160">Baixe o SetupCrossTenantRelationshipForTargetTenant.ps1 script para a configuração do locatário de destino no repositório [do GitHub.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="844cd-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="844cd-161">Salve o script (SetupCrossTenantRelationshipForTargetTenant.ps1) no computador do qual você executará o script.</span><span class="sxs-lookup"><span data-stu-id="844cd-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="844cd-162">Crie uma conexão do PowerShell Remoto com o locatário de destino do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="844cd-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="844cd-163">Novamente, certifique-se de ter as permissões necessárias para executar os scripts de implantação a fim de configurar o armazenamento e o certificado do Azure Key Vault, o aplicativo Mover Caixa de Correio, o ponto de extremidade de migração exO e o relacionamento de organização EXO.</span><span class="sxs-lookup"><span data-stu-id="844cd-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="844cd-164">Altere o diretório da pasta de arquivos para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="844cd-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="844cd-165">Execute o script com os seguintes parâmetros e valores.</span><span class="sxs-lookup"><span data-stu-id="844cd-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="844cd-166">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="844cd-166">Parameter</span></span> | <span data-ttu-id="844cd-167">Valor</span><span class="sxs-lookup"><span data-stu-id="844cd-167">Value</span></span> | <span data-ttu-id="844cd-168">Obrigatório ou opcional</span><span class="sxs-lookup"><span data-stu-id="844cd-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="844cd-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="844cd-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="844cd-170">Domínio de locatário de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-170">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="844cd-171">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-171">Required</span></span> |
    | <span data-ttu-id="844cd-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="844cd-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="844cd-173">Domínio do locatário de origem, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-173">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="844cd-174">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-174">Required</span></span> |
    | <span data-ttu-id="844cd-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="844cd-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="844cd-176">Endereço de email do administrador do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="844cd-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="844cd-177">Este é o administrador de locatários de origem que concordará com o uso do aplicativo de migração de caixa de correio enviado pelo administrador de destino. Este é o administrador que receberá o convite de email para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="844cd-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="844cd-178">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-178">Required</span></span> |
    | <span data-ttu-id="844cd-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="844cd-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="844cd-180">ID da organização do locatário de origem (GUID).</span><span class="sxs-lookup"><span data-stu-id="844cd-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="844cd-181">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-181">Required</span></span> |
    | <span data-ttu-id="844cd-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="844cd-182">-SubscriptionId</span></span>                             | <span data-ttu-id="844cd-183">A assinatura do Azure a ser usada para criar recursos.</span><span class="sxs-lookup"><span data-stu-id="844cd-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="844cd-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-184">Required</span></span> |
    | <span data-ttu-id="844cd-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="844cd-185">-ResourceGroup</span></span>                              | <span data-ttu-id="844cd-186">Nome do grupo de recursos do Azure que contém ou conterá o Key Vault.</span><span class="sxs-lookup"><span data-stu-id="844cd-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="844cd-187">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-187">Required</span></span> |
    | <span data-ttu-id="844cd-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="844cd-188">-KeyVaultName</span></span>                               | <span data-ttu-id="844cd-189">Instância do Azure Key Vault que armazenará o certificado/segredo do aplicativo de migração de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="844cd-190">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-190">Required</span></span> |
    | <span data-ttu-id="844cd-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="844cd-191">-CertificateName</span></span>                            | <span data-ttu-id="844cd-192">Nome do certificado ao gerar ou procurar certificado no cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="844cd-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="844cd-193">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-193">Required</span></span> |
    | <span data-ttu-id="844cd-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="844cd-194">-CertificateSubject</span></span>                         | <span data-ttu-id="844cd-195">Nome do assunto do certificado do Azure Key Vault, como CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="844cd-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="844cd-196">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-196">Required</span></span> |
    | <span data-ttu-id="844cd-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="844cd-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="844cd-198">Aplicativo de migração de email a ser usado se já tiver sido criado.</span><span class="sxs-lookup"><span data-stu-id="844cd-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="844cd-199">Opcional</span><span class="sxs-lookup"><span data-stu-id="844cd-199">Optional</span></span> |
    | <span data-ttu-id="844cd-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="844cd-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="844cd-201">As permissões necessárias para serem concedidas ao aplicativo de migração de caixa de correio, como Exchange ou MSGraph (Exchange para mover caixas de correio, MSGraph para usar este aplicativo para enviar um convite de link de consentimento para o locatário do recurso).</span><span class="sxs-lookup"><span data-stu-id="844cd-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="844cd-202">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="844cd-202">Required</span></span> |
    | <span data-ttu-id="844cd-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="844cd-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="844cd-204">Parâmetro para usar o aplicativo criado para migração a ser usado para enviar convite de link de consentimento para o administrador do locatário de origem. Se não estiver presente, isso solicitará que as credenciais do administrador de destino se conectem ao gerenciador de convites do Azure e enviem o convite como administrador de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="844cd-205">Opcional</span><span class="sxs-lookup"><span data-stu-id="844cd-205">Optional</span></span> |
    | <span data-ttu-id="844cd-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="844cd-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="844cd-207">A conta de armazenamento onde os logs de auditoria do Key Vault seriam armazenados.</span><span class="sxs-lookup"><span data-stu-id="844cd-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="844cd-208">Opcional</span><span class="sxs-lookup"><span data-stu-id="844cd-208">Optional</span></span> |
    | <span data-ttu-id="844cd-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="844cd-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="844cd-210">O grupo de recursos que contém a conta de armazenamento para armazenar logs de auditoria do Key Vault.</span><span class="sxs-lookup"><span data-stu-id="844cd-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="844cd-211">Opcional</span><span class="sxs-lookup"><span data-stu-id="844cd-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="844cd-212">Verifique se você instalou o módulo do PowerShell do Azure AD antes de executar os scripts.</span><span class="sxs-lookup"><span data-stu-id="844cd-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="844cd-213">Confira aqui as ![ ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) etapas de instalação</span><span class="sxs-lookup"><span data-stu-id="844cd-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="844cd-214">O script pausa e solicita que você aceite ou consenta com o aplicativo de migração de caixa de correio do Exchange criado durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="844cd-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="844cd-215">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-215">Here is an example.</span></span>

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

7. <span data-ttu-id="844cd-216">Uma URL será exibida na sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="844cd-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="844cd-217">Copie o link fornecido para o consentimento do locatário e o colar em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="844cd-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="844cd-218">Entre com suas credenciais de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="844cd-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="844cd-219">Quando a tela a seguir for apresentada, selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="844cd-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Caixa de diálogo Aceitar permissões":::

9. <span data-ttu-id="844cd-221">Volte para a sessão do PowerShell Remoto e aperte Enter para continuar.</span><span class="sxs-lookup"><span data-stu-id="844cd-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="844cd-222">O script configurará os objetos de instalação restantes.</span><span class="sxs-lookup"><span data-stu-id="844cd-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="844cd-223">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="844cd-224">A configuração do administrador de destino agora está concluída!</span><span class="sxs-lookup"><span data-stu-id="844cd-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="844cd-225">Instruções passo a passo para o administrador do locatário de origem</span><span class="sxs-lookup"><span data-stu-id="844cd-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="844cd-226">Entre em sua caixa de correio como o -ResourceTenantAdminEmail especificado pelo administrador de destino durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="844cd-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="844cd-227">Encontre o convite de email do locatário de destino e selecione o **botão Começar.**</span><span class="sxs-lookup"><span data-stu-id="844cd-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Você foi convidado para a caixa de diálogo":::

2. <span data-ttu-id="844cd-229">Selecione **Aceitar** para aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="844cd-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Caixa de diálogo para aceitar permissões":::

   > [!NOTE]
   > <span data-ttu-id="844cd-231">Se você não receber esse email ou não conseguir encontrá-lo, o administrador do locatário de destino recebeu uma URL direta que pode ser fornecida para você aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="844cd-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="844cd-232">A URL deve estar na transcrição da sessão do PowerShell Remoto do administrador do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="844cd-233">No Centro de administração do Microsoft 365 ou em uma sessão do PowerShell Remoto, crie um ou mais grupos de segurança habilitados para email para controlar a lista de caixas de correio permitidas pelo locatário de destino para puxar (mover) do locatário de origem para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="844cd-234">Você não precisa preencher esse grupo com antecedência, mas pelo menos um grupo deve ser fornecido para executar as etapas de configuração (script).</span><span class="sxs-lookup"><span data-stu-id="844cd-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="844cd-235">Não há suporte para grupos de aninhar.</span><span class="sxs-lookup"><span data-stu-id="844cd-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="844cd-236">Baixe o SetupCrossTenantRelationshipForResourceTenant.ps1 script para a configuração do locatário de origem no repositório do GitHub aqui: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="844cd-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="844cd-237">Crie uma conexão do PowerShell Remoto com o locatário de origem com suas permissões de Administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="844cd-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="844cd-238">As permissões de Administrador Global não são necessárias para configurar o locatário de origem, somente o locatário de destino devido ao processo de criação de aplicativos do Azure.</span><span class="sxs-lookup"><span data-stu-id="844cd-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="844cd-239">Altere o diretório para o local do script ou verifique se o script está atualmente salvo no local em sua sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="844cd-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="844cd-240">Execute o script com os seguintes parâmetros e valores necessários.</span><span class="sxs-lookup"><span data-stu-id="844cd-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="844cd-241">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="844cd-241">Parameter</span></span> | <span data-ttu-id="844cd-242">Valor</span><span class="sxs-lookup"><span data-stu-id="844cd-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="844cd-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="844cd-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="844cd-244">Grupo de segurança habilitado para email criado pelo locatário de origem para as identidades/caixas de correio que estão no escopo da migração.</span><span class="sxs-lookup"><span data-stu-id="844cd-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="844cd-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="844cd-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="844cd-246">Nome de domínio do locatário de origem, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-246">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="844cd-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="844cd-247">-ApplicationId</span></span> | <span data-ttu-id="844cd-248">A ID do aplicativo do Azure (GUID) do aplicativo usado para migração.</span><span class="sxs-lookup"><span data-stu-id="844cd-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="844cd-249">ID do aplicativo disponível por meio do portal do Azure (Azure AD, Aplicativos Empresariais, nome do aplicativo, ID do aplicativo) ou incluído no email do convite.</span><span class="sxs-lookup"><span data-stu-id="844cd-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="844cd-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="844cd-250">-TargetTenantDomain</span></span> | <span data-ttu-id="844cd-251">Nome de domínio do locatário de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-251">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="844cd-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="844cd-252">-TargetTenantId</span></span> | <span data-ttu-id="844cd-253">ID de locatário do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="844cd-254">Por exemplo, a ID de locatário do Azure AD da contoso \. onmicrosoft.com locatário.</span><span class="sxs-lookup"><span data-stu-id="844cd-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="844cd-255">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="844cd-256">A configuração do administrador de origem agora está concluída!</span><span class="sxs-lookup"><span data-stu-id="844cd-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="844cd-257">Verificar a configuração</span><span class="sxs-lookup"><span data-stu-id="844cd-257">Verify setup</span></span>

<span data-ttu-id="844cd-258">Verifique se os relacionamentos da organização nos locatários de origem e de destino e no ponto de extremidade de migração no destino foram criados com êxito.</span><span class="sxs-lookup"><span data-stu-id="844cd-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="844cd-259">Locatário de destino</span><span class="sxs-lookup"><span data-stu-id="844cd-259">Target tenant</span></span>

<span data-ttu-id="844cd-260">**Relacionamento de organização**</span><span class="sxs-lookup"><span data-stu-id="844cd-260">**Organization relationship**</span></span>

<span data-ttu-id="844cd-261">Verifique se o objeto de relacionamento da organização foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="844cd-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="844cd-262">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="844cd-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="844cd-263">**Ponto de extremidade de migração**</span><span class="sxs-lookup"><span data-stu-id="844cd-263">**Migration endpoint**</span></span>

<span data-ttu-id="844cd-264">Verifique se o objeto do ponto de extremidade de migração foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="844cd-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="844cd-265">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="844cd-266">Locatário de origem</span><span class="sxs-lookup"><span data-stu-id="844cd-266">Source tenant</span></span>

<span data-ttu-id="844cd-267">**Relacionamento de organização**</span><span class="sxs-lookup"><span data-stu-id="844cd-267">**Organization relationship**</span></span>

<span data-ttu-id="844cd-268">Verifique se o objeto de relacionamento da organização foi criado e configurado com esse comando.</span><span class="sxs-lookup"><span data-stu-id="844cd-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="844cd-269">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="844cd-270">Mover caixas de correio de volta para a origem original</span><span class="sxs-lookup"><span data-stu-id="844cd-270">Move mailboxes back to the original source</span></span>

<span data-ttu-id="844cd-271">Se uma caixa de correio voltar para o locatário de origem original for necessária, o mesmo conjunto de etapas e scripts precisará ser executado nos novos locatários de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-271">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="844cd-272">O objeto De relacionamento de organização existente será atualizado ou anexado, não recriado.</span><span class="sxs-lookup"><span data-stu-id="844cd-272">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="844cd-273">Preparar objetos de usuário de destino para migração</span><span class="sxs-lookup"><span data-stu-id="844cd-273">Prepare target user objects for migration</span></span>

<span data-ttu-id="844cd-274">Os usuários que estão migrando devem estar presentes no locatário de destino e no sistema do Exchange Online (como MailUsers) marcados com atributos específicos para habilitar as movimentações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-274">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="844cd-275">O sistema falhará nas movimentações para usuários que não estão devidamente definidos no locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-275">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="844cd-276">A seção a seguir detalha os requisitos do objeto MailUser para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-276">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="844cd-277">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="844cd-277">Prerequisites</span></span>
  
<span data-ttu-id="844cd-278">Você deve garantir que os seguintes objetos e atributos sejam definidos na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-278">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="844cd-279">Para qualquer caixa de correio que se mover de uma organização de origem, você deve provisionar um objeto MailUser na organização de destino:</span><span class="sxs-lookup"><span data-stu-id="844cd-279">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="844cd-280">O MailUser de destino deve ter esses atributos da caixa de correio de origem ou atribuídos ao novo objeto User:</span><span class="sxs-lookup"><span data-stu-id="844cd-280">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="844cd-281">ExchangeGUID (fluxo direto de origem para destino) – O GUID da caixa de correio deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="844cd-281">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="844cd-282">O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-282">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="844cd-283">ArchiveGUID (fluxo direto de origem para destino) – o GUID de arquivo morto deve corresponder.</span><span class="sxs-lookup"><span data-stu-id="844cd-283">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="844cd-284">O processo de movimentação não prosseguirá se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-284">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="844cd-285">(Isso só será necessário se a caixa de correio de origem estiver habilitada para Arquivo Morto).</span><span class="sxs-lookup"><span data-stu-id="844cd-285">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="844cd-286">LegacyExchangeDN (fluxo como proxyAddress, "x500: ") – o LegacyExchangeDN deve estar presente no MailUser de destino <LegacyExchangeDN> como x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="844cd-286">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="844cd-287">Os processos de movimentação não prosseguirão se isso não estiver presente no objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-287">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="844cd-288">UserPrincipalName – o UPN será alinhado com a nova identidade ou empresa de destino do usuário (por exemplo, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-288">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="844cd-289">SMTPAddress principal – o endereço SMTP principal será alinhado à empresa NEW do usuário (por exemplo, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-289">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="844cd-290">TargetAddress/ExternalEmailAddress – MailUser fará referência à caixa de correio atual do usuário hospedada no locatário de origem (por exemplo, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-290">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="844cd-291">Ao atribuir esse valor, verifique se você tem/está atribuindo PrimarySMTPAddress ou esse valor definirá PrimarySMTPAddress que causará falhas de movimentação.</span><span class="sxs-lookup"><span data-stu-id="844cd-291">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="844cd-292">Você não pode adicionar endereços proxy smtp herdado da caixa de correio de origem para MailUser de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-292">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="844cd-293">Por exemplo, você não pode manter contoso.com no MEU em fabrikam.onmicrosoft.com de locatário).</span><span class="sxs-lookup"><span data-stu-id="844cd-293">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="844cd-294">Os domínios são associados apenas a um locatário do Azure AD ou do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="844cd-294">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="844cd-295">Exemplo **de** objeto MailUser de destino:</span><span class="sxs-lookup"><span data-stu-id="844cd-295">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="844cd-296">Atributo</span><span class="sxs-lookup"><span data-stu-id="844cd-296">Attribute</span></span>             | <span data-ttu-id="844cd-297">Valor</span><span class="sxs-lookup"><span data-stu-id="844cd-297">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="844cd-298">Alias</span><span class="sxs-lookup"><span data-stu-id="844cd-298">Alias</span></span>                 | <span data-ttu-id="844cd-299">LaraN</span><span class="sxs-lookup"><span data-stu-id="844cd-299">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="844cd-300">RecipientType</span><span class="sxs-lookup"><span data-stu-id="844cd-300">RecipientType</span></span>         | <span data-ttu-id="844cd-301">MailUser</span><span class="sxs-lookup"><span data-stu-id="844cd-301">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="844cd-302">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="844cd-302">RecipientTypeDetails</span></span>  | <span data-ttu-id="844cd-303">MailUser</span><span class="sxs-lookup"><span data-stu-id="844cd-303">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="844cd-304">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="844cd-304">UserPrincipalName</span></span>     | <span data-ttu-id="844cd-305">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="844cd-305">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="844cd-306">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="844cd-306">PrimarySmtpAddress</span></span>    | <span data-ttu-id="844cd-307">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="844cd-307">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="844cd-308">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="844cd-308">ExternalEmailAddress</span></span>  | <span data-ttu-id="844cd-309">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="844cd-309">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="844cd-310">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="844cd-310">ExchangeGuid</span></span>          | <span data-ttu-id="844cd-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="844cd-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="844cd-312">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="844cd-312">LegacyExchangeDN</span></span>      | <span data-ttu-id="844cd-313">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="844cd-313">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="844cd-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="844cd-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="844cd-315">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="844cd-315">EmailAddresses</span></span>        | <span data-ttu-id="844cd-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="844cd-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="844cd-317">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="844cd-317">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="844cd-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="844cd-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="844cd-319">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="844cd-319">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="844cd-320">Exemplo de **objeto de caixa** de correio de origem:</span><span class="sxs-lookup"><span data-stu-id="844cd-320">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="844cd-321">Atributo</span><span class="sxs-lookup"><span data-stu-id="844cd-321">Attribute</span></span>             | <span data-ttu-id="844cd-322">Valor</span><span class="sxs-lookup"><span data-stu-id="844cd-322">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="844cd-323">Alias</span><span class="sxs-lookup"><span data-stu-id="844cd-323">Alias</span></span>                 | <span data-ttu-id="844cd-324">LaraN</span><span class="sxs-lookup"><span data-stu-id="844cd-324">LaraN</span></span>                                                                    |
     | <span data-ttu-id="844cd-325">RecipientType</span><span class="sxs-lookup"><span data-stu-id="844cd-325">RecipientType</span></span>         | <span data-ttu-id="844cd-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="844cd-326">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="844cd-327">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="844cd-327">RecipientTypeDetails</span></span>  | <span data-ttu-id="844cd-328">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="844cd-328">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="844cd-329">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="844cd-329">UserPrincipalName</span></span>     | <span data-ttu-id="844cd-330">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="844cd-330">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="844cd-331">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="844cd-331">PrimarySmtpAddress</span></span>    | <span data-ttu-id="844cd-332">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="844cd-332">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="844cd-333">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="844cd-333">ExchangeGuid</span></span>          | <span data-ttu-id="844cd-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="844cd-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="844cd-335">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="844cd-335">LegacyExchangeDN</span></span>      | <span data-ttu-id="844cd-336">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="844cd-336">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="844cd-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="844cd-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="844cd-338">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="844cd-338">EmailAddresses</span></span>        | <span data-ttu-id="844cd-339">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="844cd-339">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="844cd-340">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="844cd-340">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="844cd-341">Atributos adicionais já podem estar incluídos no write-back híbrido do Exchange.</span><span class="sxs-lookup"><span data-stu-id="844cd-341">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="844cd-342">Caso não sejam, eles devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="844cd-342">If not, they should be included.</span></span> 
   - <span data-ttu-id="844cd-343">msExchBlockedSendersHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="844cd-343">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="844cd-344">msExchSafeRecipientsHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="844cd-344">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="844cd-345">msExchSafeSendersHash – Grava novamente dados de remetentes seguros e bloqueados online de clientes para o Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="844cd-345">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="844cd-346">Se a caixa de correio de origem estiver em LitigationHold e o tamanho dos Itens Recuperáveis da caixa de correio de origem for maior que o padrão do banco de dados (30 GB), as movimentações não continuarão, pois a cota de destino é menor que o tamanho da caixa de correio de origem.</span><span class="sxs-lookup"><span data-stu-id="844cd-346">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="844cd-347">Você pode atualizar o objeto MailUser de destino para fazer a transição dos sinalizadores de caixa de correio ELC do ambiente de origem para o destino, o que dispara o sistema de destino para expandir a cota do MailUser para 100 GB, permitindo assim a movimentação para o destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-347">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="844cd-348">Essas instruções funcionarão apenas para a identidade híbrida executando o Azure AD Connect, pois os comandos para carimbar os sinalizadores ELC não são expostos aos administradores de locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-348">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="844cd-349">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="844cd-349">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="844cd-350">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e o Active Directory local de destino (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="844cd-350">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="844cd-351">Se a fonte tiver litígio ou recuperação de item único habilitado, de definida na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-351">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="844cd-352">Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="844cd-352">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="844cd-353">Os locatários de destino não híbridos podem modificar a cota na pasta Itens Recuperáveis para mailUsers antes da migração executando o seguinte comando para habilitar a responsabilidade de litígio no objeto MailUser e aumentando a cota para 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="844cd-353">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="844cd-354">Observe que isso não funcionará para locatários híbridos.</span><span class="sxs-lookup"><span data-stu-id="844cd-354">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="844cd-355">Os usuários na organização de destino devem ser licenciados com as assinaturas apropriadas do Exchange Online aplicáveis à organização.</span><span class="sxs-lookup"><span data-stu-id="844cd-355">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="844cd-356">Você pode aplicar uma licença antes de uma movimentação de caixa de correio, mas apenas uma vez que o MailUser de destino está corretamente definido com o ExchangeGUID e endereços proxy.</span><span class="sxs-lookup"><span data-stu-id="844cd-356">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="844cd-357">A aplicação de uma licença antes da aplicação do ExchangeGUID resultará em uma nova caixa de correio provisionada na organização de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-357">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="844cd-358">Quando você aplica uma licença em um objeto MailUser ou Caixa de Correio, todos os proxyAddresses do tipo SMTP são limpos para garantir que apenas domínios verificados sejam incluídos na matriz Exchange EmailAddresses.</span><span class="sxs-lookup"><span data-stu-id="844cd-358">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="844cd-359">Você deve garantir que o MailUser de destino não tenha ExchangeGuid anterior que não corresponder ao ExchangeGuid de origem.</span><span class="sxs-lookup"><span data-stu-id="844cd-359">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="844cd-360">Isso pode ocorrer se o MEU de destino tiver sido licenciado anteriormente para o Exchange Online e provisionado uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-360">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="844cd-361">Se o MailUser de destino tiver sido licenciado anteriormente ou tiver um ExchangeGuid que não corresponder ao ExchangeGuid de origem, você precisará executar uma limpeza do MEU de nuvem.</span><span class="sxs-lookup"><span data-stu-id="844cd-361">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="844cd-362">Para essas MEUs de nuvem, você pode `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` executar.</span><span class="sxs-lookup"><span data-stu-id="844cd-362">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="844cd-363">Esse processo é irreversível.</span><span class="sxs-lookup"><span data-stu-id="844cd-363">This process is irreversible.</span></span> <span data-ttu-id="844cd-364">Se o objeto tiver uma caixa de correio softDeleted, ele não poderá ser restaurado após esse ponto.</span><span class="sxs-lookup"><span data-stu-id="844cd-364">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="844cd-365">Uma vez limpo, no entanto, você pode sincronizar o ExchangeGuid correto com o objeto de destino e o MRS conectará a caixa de correio de origem à caixa de correio de destino recém-criada.</span><span class="sxs-lookup"><span data-stu-id="844cd-365">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="844cd-366">(Referência do blog EHLO sobre o novo parâmetro.)</span><span class="sxs-lookup"><span data-stu-id="844cd-366">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="844cd-367">Encontre objetos que anteriormente eram caixas de correio usando este comando.</span><span class="sxs-lookup"><span data-stu-id="844cd-367">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="844cd-368">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-368">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="844cd-369">Limpe a caixa de correio excluída de forma suave usando este comando.</span><span class="sxs-lookup"><span data-stu-id="844cd-369">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="844cd-370">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-370">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="844cd-371">Executar migrações de caixa de correio</span><span class="sxs-lookup"><span data-stu-id="844cd-371">Perform mailbox migrations</span></span>

<span data-ttu-id="844cd-372">As migrações de caixa de correio do Exchange entre locatários são enviadas como lotes de migração iniciados do locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-372">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="844cd-373">Isso é semelhante à maneira como os lotes de migração de relembro funcionam ao migrar do Exchange local para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="844cd-373">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="844cd-374">Criar lotes de migração</span><span class="sxs-lookup"><span data-stu-id="844cd-374">Create Migration batches</span></span>

<span data-ttu-id="844cd-375">Aqui está um cmdlet de lote de migração de exemplo para movimentações de desaquete.</span><span class="sxs-lookup"><span data-stu-id="844cd-375">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="844cd-376">O endereço de email no arquivo CSV deve ser o especificado no locatário de destino, não o locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="844cd-376">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="844cd-377">O envio de lote de migração também é suportado no novo Centro de Administração do Exchange ao selecionar a opção entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-377">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="844cd-378">Atualizar MailUsers local</span><span class="sxs-lookup"><span data-stu-id="844cd-378">Update on-premises MailUsers</span></span>

<span data-ttu-id="844cd-379">Depois que a caixa de correio se mover de origem para destino, você deve garantir que os usuários de email locais, origem e destino, sejam atualizados com o novo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="844cd-379">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="844cd-380">Nos exemplos, o targetDeliveryDomain usado na movimentação é **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="844cd-380">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="844cd-381">Atualize os usuários de email com este targetAddress.</span><span class="sxs-lookup"><span data-stu-id="844cd-381">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="844cd-382">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="844cd-382">Frequently asked questions</span></span>

<span data-ttu-id="844cd-383">**Precisamos atualizar RemoteMailboxes na origem local após a mudança?**</span><span class="sxs-lookup"><span data-stu-id="844cd-383">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="844cd-384">Sim, você deve atualizar o targetAddress (RemoteRoutingAddress/ExternalEmailAddress) dos usuários locais de origem quando a caixa de correio de locatário de origem for movimentada para o locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-384">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="844cd-385">Embora o roteamento de email possa seguir as indicações em vários usuários de email com targetAddresses diferentes, as buscas de usuários de email DEVEM direcionar o local do usuário de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-385">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="844cd-386">As buscas de informações de livre/ocupado não irão seguir vários redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="844cd-386">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="844cd-387">**O conteúdo da pasta de chat do Teams migra entre locatários?**</span><span class="sxs-lookup"><span data-stu-id="844cd-387">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="844cd-388">Não, o conteúdo da pasta de chat do Teams não migra entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-388">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="844cd-389">**Como posso ver apenas movimentações que são movimentações entre locatários, não minhas movimentações de integração e de integração?**</span><span class="sxs-lookup"><span data-stu-id="844cd-389">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="844cd-390">Use o `-flags` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="844cd-390">Use the `-flags` parameter.</span></span> <span data-ttu-id="844cd-391">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-391">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="844cd-392">**Você pode fornecer scripts de exemplo para copiar atributos usados no teste?**</span><span class="sxs-lookup"><span data-stu-id="844cd-392">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="844cd-393">EXEMPLO – COMO ESTÁ, SEM GARANTIA</span><span class="sxs-lookup"><span data-stu-id="844cd-393">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="844cd-394">Esse script pressupõe uma conexão com a caixa de correio de origem (para obter valores de origem) e os Serviços de Domínio Active Directory locais de destino (para carimbar o objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="844cd-394">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="844cd-395">Se a fonte tiver litígio ou recuperação de item único habilitado, de definida na conta de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-395">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="844cd-396">Isso aumentará o tamanho do dumpster da conta de destino para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="844cd-396">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="844cd-397">**Como acessamos o Outlook no Dia 1 depois que a caixa de correio de uso for movida?**</span><span class="sxs-lookup"><span data-stu-id="844cd-397">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="844cd-398">Como apenas um locatário pode ter um domínio, o antigo SMTPAddress principal não será associado ao usuário no locatário de destino quando a movimentação da caixa de correio for concluída; somente os domínios associados ao novo locatário.</span><span class="sxs-lookup"><span data-stu-id="844cd-398">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="844cd-399">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span><span class="sxs-lookup"><span data-stu-id="844cd-399">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="844cd-400">Como o endereço herdado não está no sistema de destino, o perfil do outlook não se conectará para encontrar a caixa de correio recém-movida.</span><span class="sxs-lookup"><span data-stu-id="844cd-400">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="844cd-401">Para essa implantação inicial, os usuários precisarão recriar seu perfil com seu novo UPN, endereço SMTP principal e ressincronize o conteúdo OST.</span><span class="sxs-lookup"><span data-stu-id="844cd-401">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="844cd-402">Planeje conforme você lote seus usuários para conclusão.</span><span class="sxs-lookup"><span data-stu-id="844cd-402">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="844cd-403">Você precisa levar em conta a utilização e a capacidade da rede quando os perfis de cliente do Outlook são criados e os arquivos OST e OAB subsequentes são baixados para os clientes.</span><span class="sxs-lookup"><span data-stu-id="844cd-403">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="844cd-404">**De quais funções do Exchange RBAC preciso ser membro para configurar ou concluir uma movimentação entre locatários?**</span><span class="sxs-lookup"><span data-stu-id="844cd-404">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="844cd-405">Há uma matriz de funções com base na suposição de tarefas delegadas ao executar uma movimentação de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-405">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="844cd-406">Atualmente, duas funções são necessárias:</span><span class="sxs-lookup"><span data-stu-id="844cd-406">Currently, two roles are required:</span></span>  

- <span data-ttu-id="844cd-407">A primeira função é para uma tarefa de configuração única que estabelece a autorização para mover o conteúdo para dentro ou para fora do limite do locatário/organização.</span><span class="sxs-lookup"><span data-stu-id="844cd-407">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="844cd-408">Como a movimentação de dados de seu controle organizacional é uma preocupação crítica para todas as empresas, optamos pela função mais alta atribuída de Administrador da Organização (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="844cd-408">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="844cd-409">Essa função deve alterar ou configurar uma nova OrganizationRelationship que define o -MailboxMoveCapability com a organização remota.</span><span class="sxs-lookup"><span data-stu-id="844cd-409">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="844cd-410">Somente o OrgAdmin pode alterar a configuração MailboxMoveCapability, enquanto outros atributos no OrganizationRelationhip podem ser gerenciados pelo administrador de Compartilhamento Federado.</span><span class="sxs-lookup"><span data-stu-id="844cd-410">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="844cd-411">A função de executar os comandos de movimentação real pode ser delegada a uma função de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="844cd-411">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="844cd-412">A função de Mover Caixas de Correio recebe a capacidade de mover caixas de correio para dentro ou para fora da organização usando o `-RemoteTenant` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="844cd-412">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="844cd-413">**Como podemos direcionar qual endereço SMTP é selecionado para targetAddress (TargetDeliveryDomain) na caixa de correio convertida (para conversão de MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="844cd-413">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="844cd-414">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span><span class="sxs-lookup"><span data-stu-id="844cd-414">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="844cd-415">O processo assume o valor -TargetDeliveryDomain passado para o comando de movimentação e verifica se há um proxy correspondente para esse domínio no lado de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-415">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="844cd-416">Quando encontramos uma correspondência, o proxyAddress correspondente é usado para definir ExternalEmailAddress (targetAddress) no objeto de caixa de correio convertida (agora MailUser).</span><span class="sxs-lookup"><span data-stu-id="844cd-416">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="844cd-417">**Como fazer a transição de permissões de caixa de correio?**</span><span class="sxs-lookup"><span data-stu-id="844cd-417">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="844cd-418">As permissões de caixa de correio incluem Enviar em Nome de e Acesso à Caixa de Correio:</span><span class="sxs-lookup"><span data-stu-id="844cd-418">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="844cd-419">Send On Behalf Of (AD:publicDelegates) armazena o DN dos destinatários com acesso à caixa de correio de um usuário como um representante.</span><span class="sxs-lookup"><span data-stu-id="844cd-419">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="844cd-420">Esse valor é armazenado no Active Directory e atualmente não é movimentado como parte da transição da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="844cd-420">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="844cd-421">Se a caixa de correio de origem tiver publicDelegates definida, você precisará executar publicDelegates na Caixa de Correio de destino assim que a conversão de MEU para Caixa de Correio for concluída no ambiente de destino executando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="844cd-421">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="844cd-422">As Permissões de Caixa de Correio armazenadas na caixa de correio serão movidas com a caixa de correio quando a entidade de segurança e o representante são movidos para o sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-422">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="844cd-423">Por exemplo, o usuário TestUser_7 é concedido FullAccess à caixa de correio TestUser_8 no locatário SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-423">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="844cd-424">Depois que a movimentação de caixa de correio TargetCompany.onmicrosoft.com concluída, as mesmas permissões são configuradas no diretório de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-424">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="844cd-425">Exemplos usando *Get-MailboxPermission* para TestUser_7 locatários de origem e destino são mostrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="844cd-425">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="844cd-426">Os cmdlets do Exchange têm o prefixo de origem e destino de acordo.</span><span class="sxs-lookup"><span data-stu-id="844cd-426">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="844cd-427">Aqui está um exemplo da saída da permissão da caixa de correio antes de uma movimentação.</span><span class="sxs-lookup"><span data-stu-id="844cd-427">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="844cd-428">Veja um exemplo da saída da permissão da caixa de correio após a movimentação.</span><span class="sxs-lookup"><span data-stu-id="844cd-428">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="844cd-429">Não há suporte para permissões de calendário e caixa de correio entre locatários.</span><span class="sxs-lookup"><span data-stu-id="844cd-429">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="844cd-430">Você deve organizar entidades e representantes em lotes de movimentação consolidados para que essas caixas de correio conectadas sejam transição ao mesmo tempo do locatário de origem.</span><span class="sxs-lookup"><span data-stu-id="844cd-430">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="844cd-431">**Qual proxy X500 deve ser adicionado aos endereços proxy MailUser de destino para habilitar a migração?**</span><span class="sxs-lookup"><span data-stu-id="844cd-431">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="844cd-432">A migração de caixa de correio entre locatários exige que o valor LegacyExchangeDN do objeto de caixa de correio de origem seja carimbado como um endereço de email x500 no objeto MailUser de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-432">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="844cd-433">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="844cd-433">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="844cd-434">Além desse proxy X500, você precisará copiar todos os proxies X500 da caixa de correio na fonte para a caixa de correio no destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-434">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="844cd-435">**O Azure Key Vault é necessário e quando as transações são feitas?**</span><span class="sxs-lookup"><span data-stu-id="844cd-435">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="844cd-436">Sim, uma assinatura do Azure é necessária para usar o Key Vault para armazenar o certificado para autorizar a migração.</span><span class="sxs-lookup"><span data-stu-id="844cd-436">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="844cd-437">Ao contrário das migrações de integração que usam o nome de usuário & senha para se autenticar na origem, as migrações de caixa de correio entre locatários usam o OAuth e esse certificado como o segredo/credencial.</span><span class="sxs-lookup"><span data-stu-id="844cd-437">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="844cd-438">O acesso ao Key Vault deve ser mantido em todas as migrações de caixa de correio, pois ele é acessado uma vez no início e depois do fim da migração, bem como uma vez a cada 24 horas durante os tempos de sincronização incrementais.</span><span class="sxs-lookup"><span data-stu-id="844cd-438">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="844cd-439">Você pode revisar os detalhes de custo de AKV [aqui.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="844cd-439">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="844cd-440">**Você tem alguma recomendação para lotes?**</span><span class="sxs-lookup"><span data-stu-id="844cd-440">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="844cd-441">Não exceder 2.000 caixas de correio por lote.</span><span class="sxs-lookup"><span data-stu-id="844cd-441">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="844cd-442">É recomendável enviar lotes duas semanas antes da data de recortar, pois não há impacto para os usuários finais durante a sincronização. Se você precisar de orientação para quantidades de caixas de correio acima de 50.000, entre em contato com a Lista de Distribuição de Comentários de Engenharia em crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="844cd-442">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="844cd-443">**E se eu usar a criptografia de serviço com a Chave do Cliente?**</span><span class="sxs-lookup"><span data-stu-id="844cd-443">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="844cd-444">A caixa de correio será descriptografada antes da movimentação.</span><span class="sxs-lookup"><span data-stu-id="844cd-444">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="844cd-445">Verifique se a Chave do Cliente está configurada no locatário de destino, se ainda for necessária.</span><span class="sxs-lookup"><span data-stu-id="844cd-445">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="844cd-446">Consulte [aqui](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="844cd-446">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="844cd-447">**Qual é o tempo estimado de migração?**</span><span class="sxs-lookup"><span data-stu-id="844cd-447">**What is the estimated migration time?**</span></span>

<span data-ttu-id="844cd-448">Para ajudá-lo a planejar [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) a migração, a tabela apresentada aqui mostra as diretrizes sobre quando esperar a conclusão de migrações de caixa de correio em massa ou migrações individuais.</span><span class="sxs-lookup"><span data-stu-id="844cd-448">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="844cd-449">Essas estimativas são baseadas em uma análise de dados de migrações anteriores do cliente.</span><span class="sxs-lookup"><span data-stu-id="844cd-449">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="844cd-450">Como cada ambiente é exclusivo, sua velocidade de migração exata pode variar.</span><span class="sxs-lookup"><span data-stu-id="844cd-450">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="844cd-451">Lembre-se de que esse recurso está atualmente em visualização, e o SLA e quaisquer Níveis de Serviço aplicáveis não se aplicam a nenhum problema de desempenho ou disponibilidade durante o status de visualização desse recurso.</span><span class="sxs-lookup"><span data-stu-id="844cd-451">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="844cd-452">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="844cd-452">Known issues</span></span>  

-  <span data-ttu-id="844cd-453">**Problema: arquivos expandidos automaticamente não podem ser migrados.**</span><span class="sxs-lookup"><span data-stu-id="844cd-453">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="844cd-454">O recurso de migração entre locatários suporta migrações da caixa de correio principal e da caixa de correio de arquivo morto para um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="844cd-454">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="844cd-455">No entanto, se o usuário na fonte tiver um arquivo morto expandido automaticamente, ou seja, mais de uma caixa de correio de arquivo morto, o recurso não poderá migrar os arquivos morto adicionais.</span><span class="sxs-lookup"><span data-stu-id="844cd-455">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="844cd-456">**Problema: Cloud MailUsers com proxy smtp não pertencente ao bloco MRS move o plano de fundo.**</span><span class="sxs-lookup"><span data-stu-id="844cd-456">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="844cd-457">Ao criar objetos MailUser de locatário de destino, você deve garantir que todos os endereços proxy SMTP pertencem à organização de locatário de destino.</span><span class="sxs-lookup"><span data-stu-id="844cd-457">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="844cd-458">Se houver um proxyAddress SMTP no usuário de email de destino que não pertença ao locatário local, a conversão de MailUser em Caixa de Correio será impedida.</span><span class="sxs-lookup"><span data-stu-id="844cd-458">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="844cd-459">Isso se deve à nossa garantia de que os objetos de caixa de correio só podem enviar emails de domínios para os quais o locatário é autoritativo (domínios reivindicados pelo locatário):</span><span class="sxs-lookup"><span data-stu-id="844cd-459">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="844cd-460">Ao sincronizar usuários do local usando o Azure AD Connect, você provisiona objetos MailUser locais com ExternalEmailAddress apontando para o locatário de origem onde a caixa de correio existe (laran@contoso.onmicrosoft.com) e carimba o PrimarySMTPAddress como um domínio que reside no locatário de destino (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-460">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="844cd-461">Esses valores são sincronizados com o locatário e um usuário de email apropriado está provisionado e pronto para a migração.</span><span class="sxs-lookup"><span data-stu-id="844cd-461">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="844cd-462">Um objeto de exemplo é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="844cd-462">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="844cd-463">O *contoso.onmicrosoft.com* endereço não *está* presente na matriz EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="844cd-463">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="844cd-464">**Problema: os objetos MailUser com endereços SMTP primários "externos" são modificados/redefinidos para domínios "internos" reivindicados pela empresa**</span><span class="sxs-lookup"><span data-stu-id="844cd-464">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="844cd-465">Objetos MailUser são ponteiros para caixas de correio não locais.</span><span class="sxs-lookup"><span data-stu-id="844cd-465">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="844cd-466">No caso de migrações de caixa de correio entre locatários, usamos objetos MailUser para representar a caixa de correio de origem (da perspectiva da organização de destino) ou a caixa de correio de destino (da perspectiva da organização de origem).</span><span class="sxs-lookup"><span data-stu-id="844cd-466">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="844cd-467">MailUsers terá um ExternalEmailAddress (targetAddress) que aponta para o endereço smtp da caixa de correio real (ProxyTest@fabrikam.onmicrosoft.com) e o endereço primarySMTP que representa o endereço SMTP exibido do usuário de caixa de correio no diretório.</span><span class="sxs-lookup"><span data-stu-id="844cd-467">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="844cd-468">Algumas organizações optam por exibir o endereço SMTP principal como um endereço SMTP externo, não como um endereço de propriedade/verificado pelo locatário local (como fabrikam.com em vez de contoso.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-468">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="844cd-469">No entanto, depois que um objeto de plano de serviço do Exchange é aplicado ao MailUser por meio de operações de licenciamento, o endereço SMTP principal é modificado para aparecer como um domínio verificado pela organização local (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="844cd-469">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="844cd-470">Há dois motivos possíveis:</span><span class="sxs-lookup"><span data-stu-id="844cd-470">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="844cd-471">Quando qualquer plano de serviço do Exchange é aplicado a um MailUser, o processo do Azure AD começa a impor a depuração de proxy para garantir que a organização local não consiga enviar emails, spoof ou emails de outro locatário.</span><span class="sxs-lookup"><span data-stu-id="844cd-471">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="844cd-472">Qualquer endereço SMTP em um objeto de destinatário com esses planos de serviço será removido se o endereço não for verificado pela organização local.</span><span class="sxs-lookup"><span data-stu-id="844cd-472">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="844cd-473">Como é o caso no exemplo, o domínio Fabikam.com não é verificado pelo locatário do contoso.onmicrosoft.com, portanto, a depuração remove esse fabrikam.com domínio.</span><span class="sxs-lookup"><span data-stu-id="844cd-473">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="844cd-474">Se você quiser manter esses domínios externos em MailUser, antes da migração ou após a migração, será necessário alterar seus processos de migração para retirar licenças após a conclusão da movimentação ou antes da movimentação para garantir que os usuários tenham a identidade visual externa esperada aplicada.</span><span class="sxs-lookup"><span data-stu-id="844cd-474">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="844cd-475">Você precisará garantir que o objeto de caixa de correio está licenciado corretamente para não afetar o serviço de email.</span><span class="sxs-lookup"><span data-stu-id="844cd-475">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="844cd-476">Um script de exemplo para remover os planos de serviço em um MailUser no Contoso.onmicrosoft.com locatário é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="844cd-476">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="844cd-477">Os resultados no conjunto de ServicePlans atribuídos são mostrados aqui.</span><span class="sxs-lookup"><span data-stu-id="844cd-477">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="844cd-478">PrimarySMTPAddress do usuário não é mais limpo.</span><span class="sxs-lookup"><span data-stu-id="844cd-478">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="844cd-479">O fabrikam.com domínio não pertence ao locatário contoso.onmicrosoft.com e persistirá como o endereço SMTP principal mostrado no diretório.</span><span class="sxs-lookup"><span data-stu-id="844cd-479">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="844cd-480">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="844cd-480">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="844cd-481">Quando msExchRemoteRecipientType é definida como 8 (DeprovisionMailbox), para MailUsers locais que são migrados para o locatário de destino, a lógica de depuração de proxy no Azure removerá domínios não proprietários e redefinirá o primarySMTP para um domínio de propriedade.</span><span class="sxs-lookup"><span data-stu-id="844cd-481">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="844cd-482">Ao limpar msExchRemoteRecipientType no MailUser local, a lógica de limpeza de proxy não se aplica mais.</span><span class="sxs-lookup"><span data-stu-id="844cd-482">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="844cd-483">Abaixo está o conjunto completo de planos de serviço possíveis que incluem o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="844cd-483">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="844cd-484">Nome</span><span class="sxs-lookup"><span data-stu-id="844cd-484">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="844cd-485">Armazenamento Avançado de Descobertas Públicas (500 GB)</span><span class="sxs-lookup"><span data-stu-id="844cd-485">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="844cd-486">Sistema de Proteção de Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="844cd-486">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="844cd-487">Prevenção contra Perda de Dados</span><span class="sxs-lookup"><span data-stu-id="844cd-487">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="844cd-488">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="844cd-488">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="844cd-489">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="844cd-489">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="844cd-490">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="844cd-490">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="844cd-491">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="844cd-491">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="844cd-492">Exchange Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="844cd-492">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="844cd-493">Exchange Online (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="844cd-493">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="844cd-494">Arquivamento do Exchange Online para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="844cd-494">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="844cd-495">Arquivamento do Exchange Online para Exchange Server</span><span class="sxs-lookup"><span data-stu-id="844cd-495">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="844cd-496">Complemento do usuário inativo do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="844cd-496">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="844cd-497">Quiosque do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="844cd-497">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="844cd-498">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="844cd-498">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="844cd-499">Exchange Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="844cd-499">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="844cd-500">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="844cd-500">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="844cd-501">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="844cd-501">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="844cd-502">Barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="844cd-502">Information Barriers</span></span>                              |
   | <span data-ttu-id="844cd-503">Proteção de Informações para o Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="844cd-503">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="844cd-504">Proteção de informações para o Office 365 – Padrão</span><span class="sxs-lookup"><span data-stu-id="844cd-504">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="844cd-505">Insights do MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="844cd-505">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="844cd-506">Auditoria Avançada do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="844cd-506">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="844cd-507">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="844cd-507">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="844cd-508">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="844cd-508">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="844cd-509">Microsoft MyAnalytics (Completo)</span><span class="sxs-lookup"><span data-stu-id="844cd-509">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="844cd-510">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="844cd-510">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="844cd-511">Microsoft Defender para Office 365 (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="844cd-511">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="844cd-512">Microsoft Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="844cd-512">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="844cd-513">Privileged Access Management para Office 365</span><span class="sxs-lookup"><span data-stu-id="844cd-513">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="844cd-514">Criptografia Premium no Office 365</span><span class="sxs-lookup"><span data-stu-id="844cd-514">Premium Encryption in Office 365</span></span>                  |
    
