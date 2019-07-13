---
title: Detalhes do locatário do Azure Active Directory
description: Este tópico descreve as alterações feitas na sua conta do AAD quando você se inscreve na área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643942"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="299fa-104">Detalhes do locatário do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="299fa-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="299fa-105">{Gory detalhes sobre contas, chamadas de API, perms etc., etc.}</span><span class="sxs-lookup"><span data-stu-id="299fa-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="299fa-106">Dados transmitidos de e para a sua conta do AAD</span><span class="sxs-lookup"><span data-stu-id="299fa-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="299fa-107">Dados enviados à sua conta da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="299fa-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="299fa-108">Nomes de grupo</span><span class="sxs-lookup"><span data-stu-id="299fa-108">Group names</span></span>
- <span data-ttu-id="299fa-109">Configuração de política de segurança</span><span class="sxs-lookup"><span data-stu-id="299fa-109">Security policy configuration</span></span>
- <span data-ttu-id="299fa-110">Pedidos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="299fa-110">Device orders</span></span>
- <span data-ttu-id="299fa-111">Contas de usuário (MSadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="299fa-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="299fa-112">Atribuição de licença E5 para as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="299fa-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="299fa-113">Diretivas do Windows Update para toques de atualização</span><span class="sxs-lookup"><span data-stu-id="299fa-113">Windows update policies for update rings</span></span>

<span data-ttu-id="299fa-114">Dados enviados à Microsoft da sua conta:</span><span class="sxs-lookup"><span data-stu-id="299fa-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="299fa-115">Dados de atualização de dispositivo, uso e confiabilidade</span><span class="sxs-lookup"><span data-stu-id="299fa-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="299fa-116">Dados de implantação e confiabilidade de aplicativos</span><span class="sxs-lookup"><span data-stu-id="299fa-116">App deployment and reliability data</span></span>
- <span data-ttu-id="299fa-117">Atualização e dados de implantação de política de segurança</span><span class="sxs-lookup"><span data-stu-id="299fa-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="299fa-118">Usuários atribuídos a dispositivos</span><span class="sxs-lookup"><span data-stu-id="299fa-118">Users assigned to devices</span></span>  

<span data-ttu-id="299fa-119">Os dados transmitidos de sua conta são armazenados em bancos de dados SQL do Azure no Microsoft locatário hospedado nos EUA.</span><span class="sxs-lookup"><span data-stu-id="299fa-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="299fa-120">Os dados são armazenados e manipulados de acordo com as políticas descritas em {segurança do Microsoft Azure}.</span><span class="sxs-lookup"><span data-stu-id="299fa-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="299fa-121">Permissões e chamadas de API</span><span class="sxs-lookup"><span data-stu-id="299fa-121">API permissions and calls</span></span>

<span data-ttu-id="299fa-122">**Durante o registro:**</span><span class="sxs-lookup"><span data-stu-id="299fa-122">**During enrollment:**</span></span>

<span data-ttu-id="299fa-123">Permissões de API:</span><span class="sxs-lookup"><span data-stu-id="299fa-123">API permissions:</span></span>
- <span data-ttu-id="299fa-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="299fa-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="299fa-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="299fa-130">Chamadas de API:</span><span class="sxs-lookup"><span data-stu-id="299fa-130">API calls:</span></span>
- <span data-ttu-id="299fa-131">POSTAR/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="299fa-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="299fa-132">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="299fa-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="299fa-133">GET/POST/Users</span><span class="sxs-lookup"><span data-stu-id="299fa-133">GET/POST /users</span></span>
- <span data-ttu-id="299fa-134">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="299fa-134">GET/POST /groups</span></span>
- <span data-ttu-id="299fa-135">PATCH/groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="299fa-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="299fa-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="299fa-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="299fa-137">OBTER/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="299fa-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="299fa-138">**Após o registro, durante o gerenciamento comum:**</span><span class="sxs-lookup"><span data-stu-id="299fa-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="299fa-139">Permissões de API:</span><span class="sxs-lookup"><span data-stu-id="299fa-139">API permissions:</span></span>
- <span data-ttu-id="299fa-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="299fa-143">Reports.Read.All</span></span>
- <span data-ttu-id="299fa-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="299fa-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="299fa-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="299fa-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="299fa-147">Chamadas de API:</span><span class="sxs-lookup"><span data-stu-id="299fa-147">API calls:</span></span>
- <span data-ttu-id="299fa-148">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="299fa-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="299fa-149">GET/PATCH/POST/Users</span><span class="sxs-lookup"><span data-stu-id="299fa-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="299fa-150">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="299fa-150">GET/POST /groups</span></span>
- <span data-ttu-id="299fa-151">PATCH/groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="299fa-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="299fa-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="299fa-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="299fa-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="299fa-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="299fa-154">OBTER/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="299fa-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="299fa-155">OBTER/Devices</span><span class="sxs-lookup"><span data-stu-id="299fa-155">GET /devices</span></span>
- <span data-ttu-id="299fa-156">POST/Users/{ID | userPrincipalName}/assignLicense</span><span class="sxs-lookup"><span data-stu-id="299fa-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="299fa-157">OBTER/subscribedSkus</span><span class="sxs-lookup"><span data-stu-id="299fa-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="299fa-158">Contas usadas pela área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="299fa-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="299fa-159">Conta</span><span class="sxs-lookup"><span data-stu-id="299fa-159">Account</span></span> | <span data-ttu-id="299fa-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="299fa-160">Description</span></span>  | <span data-ttu-id="299fa-161">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="299fa-161">Conditional access</span></span>  | <span data-ttu-id="299fa-162">Multi-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="299fa-162">Multi-factor authentication</span></span>  | <span data-ttu-id="299fa-163">Por que isso é certo</span><span class="sxs-lookup"><span data-stu-id="299fa-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="299fa-164">MSadmin @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="299fa-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="299fa-165">Conta de serviço limitada com privilégios de administrador, usada como um Microsoft Intune e administrador de usuários {What ' s This?}</span><span class="sxs-lookup"><span data-stu-id="299fa-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="299fa-166">para definir e configurar o locatário para dispositivos de área de trabalho modernos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="299fa-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="299fa-167">Não tem permissões de logon interativas; realiza operações apenas por meio do serviço.</span><span class="sxs-lookup"><span data-stu-id="299fa-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="299fa-168">Excluído, pois ele não é proveniente de sua rede</span><span class="sxs-lookup"><span data-stu-id="299fa-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="299fa-169">Excluído porque não há logon interativo</span><span class="sxs-lookup"><span data-stu-id="299fa-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="299fa-170">Senha armazenada no Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="299fa-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="299fa-171">MSTest @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="299fa-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="299fa-172">mssupport @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="299fa-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="299fa-173">msadminint @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="299fa-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
