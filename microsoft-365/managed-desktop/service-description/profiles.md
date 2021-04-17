---
title: Compreender perfis de dispositivo
description: Os vários perfis que os administradores podem atribuir a dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689866"
---
# <a name="device-profiles"></a><span data-ttu-id="e9f4f-104">Perfis de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9f4f-104">Device profiles</span></span>

<span data-ttu-id="e9f4f-105">Você pode atribuir configurações pré-definidas diferentes ("perfis de dispositivo") a dispositivos, cada uma otimizada para as necessidades de tipos específicos de usuários.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-105">You can assign different pre-set configurations ("device profiles") to devices, each optimized for the needs of specific types of users.</span></span> <span data-ttu-id="e9f4f-106">Três perfis de dispositivo estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e9f4f-106">Three device profiles are available:</span></span>

- <span data-ttu-id="e9f4f-107">Padrão</span><span class="sxs-lookup"><span data-stu-id="e9f4f-107">Standard</span></span>
- <span data-ttu-id="e9f4f-108">Dados Confidenciais</span><span class="sxs-lookup"><span data-stu-id="e9f4f-108">Sensitive Data</span></span>
- <span data-ttu-id="e9f4f-109">Usuário do power</span><span class="sxs-lookup"><span data-stu-id="e9f4f-109">Power user</span></span>

<span data-ttu-id="e9f4f-110">Você pode pensar nos perfis de dispositivo como parte de uma hierarquia de opções de configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-110">You can think of device profiles as being part of a hierarchy of device configuration options.</span></span>

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Configurações de dispositivo mostradas como uma pirâmide. Descrição a seguir":::

<span data-ttu-id="e9f4f-112">Fundamentalmente, todos os dispositivos da Área de Trabalho Gerenciada da Microsoft têm uma base que inclui uma linha de base de segurança padrão, políticas de conformidade, configurações e grupos do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-112">Fundamentally, every Microsoft Managed Desktop device has a foundation that includes a standard security baseline, compliance policies, Windows Update settings, and groups.</span></span> <span data-ttu-id="e9f4f-113">Para trabalhar com a Área de Trabalho Gerenciada da Microsoft, todos os dispositivos devem incluir todos esses elementos, que não podem ser alterados pelos administradores sem uma solicitação para a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-113">To work with Microsoft Managed Desktop, every device must include all of these elements, which can't be changed by admins without a request to Microsoft Managed Desktop.</span></span>

<span data-ttu-id="e9f4f-114">Os perfis de dispositivo aparecem no próximo nível superior.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-114">Device profiles appear at the next higher level.</span></span> <span data-ttu-id="e9f4f-115">Cada dispositivo da Área de Trabalho Gerenciada da Microsoft deve ter um (e apenas um) perfil atribuído.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-115">Every Microsoft Managed Desktop device must have one (and only one) profile assigned.</span></span> <span data-ttu-id="e9f4f-116">Os administradores podem escolher qual perfil um dispositivo é atribuído.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-116">Admins can choose which profile a device is assigned.</span></span>

<span data-ttu-id="e9f4f-117">Em um nível ainda mais alto, há [personalizações adicionais.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="e9f4f-117">At a still higher level are additional [customizations](customizing.md).</span></span> <span data-ttu-id="e9f4f-118">Cada dispositivo pode ter uma ou mais personalizações (ou não).</span><span class="sxs-lookup"><span data-stu-id="e9f4f-118">Each device can have one or more (or no) customizations.</span></span> <span data-ttu-id="e9f4f-119">Eles podem modificar uma camada de nível inferior (perfis de dispositivo ou a configuração base) ou ser uma solicitação totalmente nova que é em camadas sobre a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-119">They can either modify a lower-level layer (Device profiles or the foundational configuration),  or be an entirely new request that’s layered on top of the standard configuration.</span></span>

<span data-ttu-id="e9f4f-120">Na parte superior estão suas próprias modificações, como detalhes da rede ou aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-120">At the top are your own modifications, such as network details or applications.</span></span> <span data-ttu-id="e9f4f-121">Um dispositivo pode ter qualquer número dessas modificações, que não são gerenciadas ou bloqueadas pela Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-121">A device can have any number of these modifications, which aren't managed or blocked by Microsoft Managed Desktop.</span></span>


## <a name="device-profile-details"></a><span data-ttu-id="e9f4f-122">Detalhes do perfil do dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9f4f-122">Device profile details</span></span>

<span data-ttu-id="e9f4f-123">A tabela a seguir resume as configurações e seus valores padrão para cada configuração configurada por perfis de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-123">The following table summarizes the settings and their default values for each setting configured by device profiles.</span></span> <span data-ttu-id="e9f4f-124">(Nos bastidores, essas configurações são configuradas com OMA-URIs usando perfis de configuração personalizados no Microsoft Endpoint Manager.)</span><span class="sxs-lookup"><span data-stu-id="e9f4f-124">(Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.)</span></span>

| <span data-ttu-id="e9f4f-125">Recurso</span><span class="sxs-lookup"><span data-stu-id="e9f4f-125">Feature</span></span> | <span data-ttu-id="e9f4f-126">Dados Confidenciais</span><span class="sxs-lookup"><span data-stu-id="e9f4f-126">Sensitive Data</span></span> | <span data-ttu-id="e9f4f-127">Power User</span><span class="sxs-lookup"><span data-stu-id="e9f4f-127">Power User</span></span> | <span data-ttu-id="e9f4f-128">Padrão</span><span class="sxs-lookup"><span data-stu-id="e9f4f-128">Standard</span></span> |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| <span data-ttu-id="e9f4f-129">**Bloquear Armazenamento Externo**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-129">**Block External Storage**</span></span>                                                                                                                               | <span data-ttu-id="e9f4f-130">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-130">Yes</span></span>                       | <span data-ttu-id="e9f4f-131">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-131">Yes</span></span>                   | <span data-ttu-id="e9f4f-132">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-132">No</span></span>                   |
| <span data-ttu-id="e9f4f-133">**[Nível de bloqueio na nuvem](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-133">**[Cloud Block Level](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**</span></span> | <span data-ttu-id="e9f4f-134">Alto</span><span class="sxs-lookup"><span data-stu-id="e9f4f-134">High</span></span>                      | <span data-ttu-id="e9f4f-135">Alto</span><span class="sxs-lookup"><span data-stu-id="e9f4f-135">High</span></span>                  | <span data-ttu-id="e9f4f-136">Alto</span><span class="sxs-lookup"><span data-stu-id="e9f4f-136">High</span></span>                 |
| <span data-ttu-id="e9f4f-137">**Desabilitar contas da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-137">**Disable Microsoft Accounts**</span></span>                                                                                                                           | <span data-ttu-id="e9f4f-138">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-138">Yes</span></span>                       | <span data-ttu-id="e9f4f-139">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-139">Yes</span></span>                   | <span data-ttu-id="e9f4f-140">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-140">No</span></span>                   |
| <span data-ttu-id="e9f4f-141">**Desabilitar o OneDrive pessoal**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-141">**Disable personal OneDrive**</span></span>                                                                                                                            | <span data-ttu-id="e9f4f-142">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-142">Yes</span></span>                       | <span data-ttu-id="e9f4f-143">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-143">Yes</span></span>                   | <span data-ttu-id="e9f4f-144">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-144">No</span></span>                   |
| <span data-ttu-id="e9f4f-145">**Alternar para área de trabalho segura para elevação**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-145">**Switch to secure desktop for elevation**</span></span>                                                                                                               | <span data-ttu-id="e9f4f-146">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-146">No</span></span>                        | <span data-ttu-id="e9f4f-147">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-147">Yes</span></span>                   | <span data-ttu-id="e9f4f-148">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-148">No</span></span>                   |
| <span data-ttu-id="e9f4f-149">**Marca de dispositivo do Microsoft Defender para Ponto de Extremidade**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-149">**Microsoft Defender for Endpoint Device Tag**</span></span>                                                                                                           | <span data-ttu-id="e9f4f-150">M365Managed-SensitiveData</span><span class="sxs-lookup"><span data-stu-id="e9f4f-150">M365Managed-SensitiveData</span></span> | <span data-ttu-id="e9f4f-151">M365Managed-PowerUser</span><span class="sxs-lookup"><span data-stu-id="e9f4f-151">M365Managed-PowerUser</span></span> | <span data-ttu-id="e9f4f-152">M365Managed-Standard</span><span class="sxs-lookup"><span data-stu-id="e9f4f-152">M365Managed-Standard</span></span> |
| <span data-ttu-id="e9f4f-153">**Administrador no dispositivo?**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-153">**Admin on the device?**</span></span>                                                                                                                                 | <span data-ttu-id="e9f4f-154">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-154">No</span></span>                        | <span data-ttu-id="e9f4f-155">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-155">Yes</span></span>                   | <span data-ttu-id="e9f4f-156">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-156">No</span></span>                   |
| <span data-ttu-id="e9f4f-157">**Perfil do Piloto Automático**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-157">**Autopilot Profile**</span></span>                                                                                                                                     | <span data-ttu-id="e9f4f-158">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="e9f4f-158">MMD Standard</span></span>               | <span data-ttu-id="e9f4f-159">Usuário de Energia MMD</span><span class="sxs-lookup"><span data-stu-id="e9f4f-159">MMD Power User</span></span>         | <span data-ttu-id="e9f4f-160">MMD Standard</span><span class="sxs-lookup"><span data-stu-id="e9f4f-160">MMD Standard</span></span>          |
| <span data-ttu-id="e9f4f-161">**AppLocker**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-161">**AppLocker**</span></span>                                                                                                                                            | <span data-ttu-id="e9f4f-162">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-162">Yes</span></span>                       | <span data-ttu-id="e9f4f-163">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-163">No</span></span>                    | <span data-ttu-id="e9f4f-164">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-164">No</span></span>                   |
| <span data-ttu-id="e9f4f-165">**Bloquear o Armazenamento Público**</span><span class="sxs-lookup"><span data-stu-id="e9f4f-165">**Block Public Store**</span></span>                                                                                                                                   | <span data-ttu-id="e9f4f-166">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-166">Yes</span></span>                       | <span data-ttu-id="e9f4f-167">Sim</span><span class="sxs-lookup"><span data-stu-id="e9f4f-167">Yes</span></span>                   | <span data-ttu-id="e9f4f-168">Não</span><span class="sxs-lookup"><span data-stu-id="e9f4f-168">No</span></span>                   |

<span data-ttu-id="e9f4f-169">Cada perfil de dispositivo também envolve esses itens:</span><span class="sxs-lookup"><span data-stu-id="e9f4f-169">Each device profile also involves these items:</span></span>

- <span data-ttu-id="e9f4f-170">Um grupo de dispositivos do Azure Active Directory (AAD) de associação dinâmica</span><span class="sxs-lookup"><span data-stu-id="e9f4f-170">A dynamic membership Azure Active Directory (AAD) device group</span></span>
- <span data-ttu-id="e9f4f-171">Um grupo de dispositivos AAD de associação estática</span><span class="sxs-lookup"><span data-stu-id="e9f4f-171">A static membership AAD device group</span></span>
- <span data-ttu-id="e9f4f-172">Um perfil de configuração do Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e9f4f-172">A Microsoft Endpoint Manager Configuration profile</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9f4f-173">Não modifique diretamente a associação desses grupos.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-173">Don’t modify the membership of these groups directly.</span></span> <span data-ttu-id="e9f4f-174">Use a interface conforme descrito em [Reatribuir perfis](../working-with-managed-desktop/change-device-profile.md).</span><span class="sxs-lookup"><span data-stu-id="e9f4f-174">Use the interface as described in [Reassign profiles](../working-with-managed-desktop/change-device-profile.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="e9f4f-175">Limitações</span><span class="sxs-lookup"><span data-stu-id="e9f4f-175">Limitations</span></span>

<span data-ttu-id="e9f4f-176">Você pode solicitar exceções para os perfis de dispositivo e seus detalhes, como faria com qualquer outra política.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-176">You can request exceptions to the device profiles and their details as you would with any other policy.</span></span> <span data-ttu-id="e9f4f-177">Lembre-se de que você só pode ter um de cada perfil de dispositivo em sua organização do Azure Active Directory ("locatário").</span><span class="sxs-lookup"><span data-stu-id="e9f4f-177">Keep in mind that you can only have one of each device profile in your Azure Active Directory organization ("tenant").</span></span> <span data-ttu-id="e9f4f-178">Por exemplo, você não pode solicitar que o perfil do dispositivo de dados confidenciais desabilite o AppLocker para apenas alguns de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-178">For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users.</span></span> <span data-ttu-id="e9f4f-179">Todos os dispositivos com o perfil de dados Confidenciais devem ter a mesma configuração.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-179">All devices with the Sensitive data profile must have the same configuration.</span></span>

<span data-ttu-id="e9f4f-180">Cada dispositivo só pode ter um perfil.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-180">Each device can only have one profile.</span></span> <span data-ttu-id="e9f4f-181">Se um determinado dispositivo for usado por mais de um usuário, todos os usuários nesse dispositivo terão a mesma configuração.</span><span class="sxs-lookup"><span data-stu-id="e9f4f-181">If a given device is used by more than one user, all users on that device will have the same configuration.</span></span>