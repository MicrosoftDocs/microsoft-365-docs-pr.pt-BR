---
title: Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control
description: Um passo a passo sobre o Microsoft Defender para Ponto de Extremidade
keywords: mídia de armazenamento removível
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327042"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="62068-104">Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control</span><span class="sxs-lookup"><span data-stu-id="62068-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="62068-105">O Microsoft Defender for Endpoint Device Control Removível Armazenamento Controle de Acesso permite que você faça a seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="62068-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="62068-106">auditoria, permitindo ou impedindo o acesso de leitura, gravação ou execução ao armazenamento removível com ou sem exclusão</span><span class="sxs-lookup"><span data-stu-id="62068-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="62068-107">Privilégio</span><span class="sxs-lookup"><span data-stu-id="62068-107">Privilege</span></span> |<span data-ttu-id="62068-108">Permissão</span><span class="sxs-lookup"><span data-stu-id="62068-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="62068-109">Access</span><span class="sxs-lookup"><span data-stu-id="62068-109">Access</span></span>    |  <span data-ttu-id="62068-110">Leitura, Gravação, Execução</span><span class="sxs-lookup"><span data-stu-id="62068-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="62068-111">Modo de ação</span><span class="sxs-lookup"><span data-stu-id="62068-111">Action Mode</span></span>    |    <span data-ttu-id="62068-112">Auditar, Permitir, Impedir</span><span class="sxs-lookup"><span data-stu-id="62068-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="62068-113">Suporte A CSP</span><span class="sxs-lookup"><span data-stu-id="62068-113">CSP Support</span></span>   |   <span data-ttu-id="62068-114">Sim</span><span class="sxs-lookup"><span data-stu-id="62068-114">Yes</span></span>      |
|<span data-ttu-id="62068-115">Suporte a GPO</span><span class="sxs-lookup"><span data-stu-id="62068-115">GPO Support</span></span>    |   <span data-ttu-id="62068-116">Sim</span><span class="sxs-lookup"><span data-stu-id="62068-116">Yes</span></span>      |
|<span data-ttu-id="62068-117">Suporte baseado no usuário</span><span class="sxs-lookup"><span data-stu-id="62068-117">User-based Support</span></span>     |   <span data-ttu-id="62068-118">Sim</span><span class="sxs-lookup"><span data-stu-id="62068-118">Yes</span></span>      |
|<span data-ttu-id="62068-119">Suporte baseado em máquina</span><span class="sxs-lookup"><span data-stu-id="62068-119">Machine-based Support</span></span>    |    <span data-ttu-id="62068-120">Sim</span><span class="sxs-lookup"><span data-stu-id="62068-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="62068-121">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="62068-121">Prepare your endpoints</span></span>

<span data-ttu-id="62068-122">Implantar controle de acesso Armazenamento removível em dispositivos Windows 10 que tenham cliente antimalware versão **4.18.2103.3 ou posterior**.</span><span class="sxs-lookup"><span data-stu-id="62068-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="62068-123">**4.18.2104 ou** posterior : Adicionar SerialNumberId, VID_PID, suporte a GPO baseado em filepath, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="62068-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="62068-124">**4.18.2105** ou posterior : Adicione suporte a curinga para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, a combinação de usuário específico em máquina específica, SSD removêvel (um SSD do SanDisk Extreme)/suporte A USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="62068-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="62068-125">**4.18.2107** ou posterior : Adicionar suporte Windows wpd (dispositivo portátil) (para dispositivos móveis, como tablets)</span><span class="sxs-lookup"><span data-stu-id="62068-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="A interface do PowerShell":::

> [!NOTE]
> <span data-ttu-id="62068-127">Nenhum dos Segurança do Windows componentes precisa estar ativo, você pode executar o Controle de Acesso Removível Armazenamento independentemente do status Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="62068-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="62068-128">Propriedades de política</span><span class="sxs-lookup"><span data-stu-id="62068-128">Policy properties</span></span>

<span data-ttu-id="62068-129">Você pode usar as seguintes propriedades para criar um grupo de armazenamento removível:</span><span class="sxs-lookup"><span data-stu-id="62068-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="62068-130">**Nome da propriedade: ID do grupo**</span><span class="sxs-lookup"><span data-stu-id="62068-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="62068-131">Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa o grupo e será usado na política.</span><span class="sxs-lookup"><span data-stu-id="62068-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="62068-132">**Nome da propriedade: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="62068-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="62068-133">Descrição: listar as propriedades do dispositivo que você deseja usar para cobrir no grupo.</span><span class="sxs-lookup"><span data-stu-id="62068-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="62068-134">Para cada propriedade de dispositivo, consulte **a seção Propriedades do Dispositivo** acima para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="62068-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="62068-135">Opções:</span><span class="sxs-lookup"><span data-stu-id="62068-135">Options:</span></span>
    - <span data-ttu-id="62068-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="62068-136">PrimaryId</span></span>
        - <span data-ttu-id="62068-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="62068-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="62068-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="62068-138">CdRomDevices</span></span>
        - <span data-ttu-id="62068-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="62068-139">WpdDevices</span></span>
    - <span data-ttu-id="62068-140">DeviceId</span><span class="sxs-lookup"><span data-stu-id="62068-140">DeviceId</span></span>
    - <span data-ttu-id="62068-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="62068-141">HardwareId</span></span>
    - <span data-ttu-id="62068-142">InstancePathId: InstancePathId é uma cadeia de caracteres que identifica exclusivamente o dispositivo no sistema, por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="62068-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="62068-143">O número no final (por exemplo, **&0**) representa o slot disponível e pode mudar de dispositivo para dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62068-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="62068-144">Para melhores resultados, use um curinga no final.</span><span class="sxs-lookup"><span data-stu-id="62068-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="62068-145">Por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="62068-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="62068-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="62068-146">FriendlyNameId</span></span>
    - <span data-ttu-id="62068-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="62068-147">SerialNumberId</span></span>
    - <span data-ttu-id="62068-148">VID</span><span class="sxs-lookup"><span data-stu-id="62068-148">VID</span></span>
    - <span data-ttu-id="62068-149">PID</span><span class="sxs-lookup"><span data-stu-id="62068-149">PID</span></span>
    - <span data-ttu-id="62068-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="62068-150">VID_PID</span></span>
        - <span data-ttu-id="62068-151">0751_55E0: corresponder a esse par exato do VID/PID</span><span class="sxs-lookup"><span data-stu-id="62068-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="62068-152">_55E0: corresponder qualquer mídia com PID=55E0</span><span class="sxs-lookup"><span data-stu-id="62068-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="62068-153">0751_: corresponder qualquer mídia com VID=0751</span><span class="sxs-lookup"><span data-stu-id="62068-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="62068-154">**Nome da propriedade: MatchType**</span><span class="sxs-lookup"><span data-stu-id="62068-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="62068-155">Descrição: quando há várias propriedades de dispositivo sendo usadas no DescriptorIDList, MatchType define a relação.</span><span class="sxs-lookup"><span data-stu-id="62068-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="62068-156">Opções:</span><span class="sxs-lookup"><span data-stu-id="62068-156">Options:</span></span>

    - <span data-ttu-id="62068-157">MatchAll: Quaisquer atributos sob o DescritorIdList serão **e** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema verificará se a USB atende aos dois valores.</span><span class="sxs-lookup"><span data-stu-id="62068-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="62068-158">MatchAny: Os atributos no DescriptorIdList serão **Ou** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema fará a imposição desde que a USB tenha um valor **DeviceID** idêntico ou **InstanceID.**</span><span class="sxs-lookup"><span data-stu-id="62068-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="62068-159">A seguir estão as propriedades da política de controle de acesso:</span><span class="sxs-lookup"><span data-stu-id="62068-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="62068-160">**Nome da propriedade: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="62068-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="62068-161">Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa a política e será usada no relatório e na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="62068-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="62068-162">**Nome da propriedade: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="62068-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="62068-163">Descrição: os grupos ao que a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="62068-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="62068-164">Se vários grupos são adicionados, a política será aplicada a qualquer mídia em todos esses grupos.</span><span class="sxs-lookup"><span data-stu-id="62068-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="62068-165">Opções: a ID/GUID do grupo deve ser usada nesta instância.</span><span class="sxs-lookup"><span data-stu-id="62068-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="62068-166">O exemplo a seguir mostra o uso de GroupID:</span><span class="sxs-lookup"><span data-stu-id="62068-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="62068-167">**Nome da propriedade: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="62068-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="62068-168">Descrição: os grupos aos que a política não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="62068-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="62068-169">Opções: a ID/GUID do grupo deve ser usada nesta instância.</span><span class="sxs-lookup"><span data-stu-id="62068-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="62068-170">**Nome da propriedade: Id de entrada**</span><span class="sxs-lookup"><span data-stu-id="62068-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="62068-171">Descrição: Um PolicyRule pode ter várias entradas; cada entrada com um GUID exclusivo informa ao Controle de Dispositivo uma restrição.</span><span class="sxs-lookup"><span data-stu-id="62068-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="62068-172">**Nome da propriedade: Type**</span><span class="sxs-lookup"><span data-stu-id="62068-172">**Property name: Type**</span></span>

1. <span data-ttu-id="62068-173">Descrição: define a ação para os grupos de armazenamento removíveis em IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="62068-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="62068-174">Imposição: Permitir ou Negar</span><span class="sxs-lookup"><span data-stu-id="62068-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="62068-175">Auditoria: AuditAllowed ou AuditDenied</span><span class="sxs-lookup"><span data-stu-id="62068-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="62068-176">Opções:</span><span class="sxs-lookup"><span data-stu-id="62068-176">Options:</span></span>

    - <span data-ttu-id="62068-177">Permitir</span><span class="sxs-lookup"><span data-stu-id="62068-177">Allow</span></span>
    - <span data-ttu-id="62068-178">Negar</span><span class="sxs-lookup"><span data-stu-id="62068-178">Deny</span></span>
    - <span data-ttu-id="62068-179">AuditAllowed: define notificação e evento quando o acesso é permitido</span><span class="sxs-lookup"><span data-stu-id="62068-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="62068-180">AuditDenied: define a notificação e o evento quando o acesso é negado; tem que trabalhar em conjunto com **a entrada Negar.**</span><span class="sxs-lookup"><span data-stu-id="62068-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="62068-181">Quando houver tipos de conflito para a mesma mídia, o sistema aplicará o primeiro na política.</span><span class="sxs-lookup"><span data-stu-id="62068-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="62068-182">Um exemplo de tipo de conflito é **Permitir** e **Negar.**</span><span class="sxs-lookup"><span data-stu-id="62068-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="62068-183">**Nome da propriedade: Sid**</span><span class="sxs-lookup"><span data-stu-id="62068-183">**Property name: Sid**</span></span>

<span data-ttu-id="62068-184">Descrição: Sid do computador local ou o Sid do objeto AD define se essa política deve ser aplicada a um usuário ou grupo de usuários específico; uma entrada pode ter no máximo um Sid e uma entrada sem qualquer Sid significa aplicar a política no computador.</span><span class="sxs-lookup"><span data-stu-id="62068-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="62068-185">**Nome da propriedade: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="62068-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="62068-186">Descrição: Sid do computador local ou o Sid do objeto AD define se essa política deve ser aplicada a um grupo específico de máquina ou máquina; uma entrada pode ter no máximo um ComputerSid e uma entrada sem qualquer ComputerSid significa aplicar a política no computador.</span><span class="sxs-lookup"><span data-stu-id="62068-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="62068-187">Se você quiser aplicar uma Entrada a um usuário específico e a um computador específico, adicione Sid e ComputerSid à mesma Entrada.</span><span class="sxs-lookup"><span data-stu-id="62068-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="62068-188">**Nome da propriedade: Opções**</span><span class="sxs-lookup"><span data-stu-id="62068-188">**Property name: Options**</span></span>

<span data-ttu-id="62068-189">Descrição: define se a notificação deve ser exibida ou não.</span><span class="sxs-lookup"><span data-stu-id="62068-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="A tela na qual o status do dispositivo pode ser visto":::

<span data-ttu-id="62068-191">Opções: 0-4.</span><span class="sxs-lookup"><span data-stu-id="62068-191">Options: 0-4.</span></span> <span data-ttu-id="62068-192">Quando Type Allow ou Deny estiver selecionado:</span><span class="sxs-lookup"><span data-stu-id="62068-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="62068-193">0: nothing</span><span class="sxs-lookup"><span data-stu-id="62068-193">0: nothing</span></span>
   - <span data-ttu-id="62068-194">4: **desabilite AuditAllowed** e **AuditDenied** para esta Entrada.</span><span class="sxs-lookup"><span data-stu-id="62068-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="62068-195">Mesmo que **Block** aconteça e **AuditDenied** estiver configurada, o sistema não mostrará a notificação.</span><span class="sxs-lookup"><span data-stu-id="62068-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="62068-196">Quando Type **AuditAllowed** ou **AuditDenied** estiver selecionado:</span><span class="sxs-lookup"><span data-stu-id="62068-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="62068-197">0: nothing</span><span class="sxs-lookup"><span data-stu-id="62068-197">0: nothing</span></span>
   - <span data-ttu-id="62068-198">1: mostrar notificação</span><span class="sxs-lookup"><span data-stu-id="62068-198">1: show notification</span></span>
   - <span data-ttu-id="62068-199">2: enviar evento</span><span class="sxs-lookup"><span data-stu-id="62068-199">2: send event</span></span>
   - <span data-ttu-id="62068-200">3: mostrar evento de notificação e envio</span><span class="sxs-lookup"><span data-stu-id="62068-200">3: show notification and send event</span></span>

<span data-ttu-id="62068-201">**Nome da propriedade: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="62068-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="62068-202">Descrição: define o acesso.</span><span class="sxs-lookup"><span data-stu-id="62068-202">Description: Defines the access.</span></span>

<span data-ttu-id="62068-203">Opções 1 a 7:</span><span class="sxs-lookup"><span data-stu-id="62068-203">Options 1-7:</span></span>
  - <span data-ttu-id="62068-204">1: Leitura</span><span class="sxs-lookup"><span data-stu-id="62068-204">1: Read</span></span>
  - <span data-ttu-id="62068-205">2: Gravar</span><span class="sxs-lookup"><span data-stu-id="62068-205">2: Write</span></span>
  - <span data-ttu-id="62068-206">3: Leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="62068-206">3: Read and Write</span></span>
  - <span data-ttu-id="62068-207">4: Execute</span><span class="sxs-lookup"><span data-stu-id="62068-207">4: Execute</span></span>
  - <span data-ttu-id="62068-208">5: Leitura e execução</span><span class="sxs-lookup"><span data-stu-id="62068-208">5: Read and Execute</span></span>
  - <span data-ttu-id="62068-209">6: Gravar e executar</span><span class="sxs-lookup"><span data-stu-id="62068-209">6: Write and Execute</span></span>
  - <span data-ttu-id="62068-210">7: Leitura e gravação e execução</span><span class="sxs-lookup"><span data-stu-id="62068-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="62068-211">Cenários comuns de controle de acesso Armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="62068-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="62068-212">Para ajudar a familiarizá-lo com o Microsoft Defender for Endpoint Removable Armazenamento Access Control, reunimos alguns cenários comuns para você seguir.</span><span class="sxs-lookup"><span data-stu-id="62068-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="62068-213">Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados específicos</span><span class="sxs-lookup"><span data-stu-id="62068-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="62068-214">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="62068-214">Create groups</span></span>

    1. <span data-ttu-id="62068-215">Grupo 1: Qualquer armazenamento removível e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="62068-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="62068-216">Um exemplo de armazenamento removível e CD/DVD é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="62068-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="62068-217">Grupo 2: USBs aprovados com base nas propriedades do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62068-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="62068-218">Um exemplo para este caso de uso é: ID de instância – Grupo **65fa649a-a111-4912-9294-fb6337a25038** no exemplo [usbs aprovados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) arquivo.</span><span class="sxs-lookup"><span data-stu-id="62068-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62068-219">Você precisa substituir `&` `&amp;` no valor.</span><span class="sxs-lookup"><span data-stu-id="62068-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="62068-220">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="62068-220">Create policy</span></span>

    1. <span data-ttu-id="62068-221">Política 1: Bloquear o Acesso de Gravação e Execução, mas permitir USBs aprovados.</span><span class="sxs-lookup"><span data-stu-id="62068-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="62068-222">Um exemplo para este caso de uso é: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** no exemplo [Cenário 1 Bloquear](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Gravação e Executar Acesso, mas permitir arquivo USBs.xmlaprovado.</span><span class="sxs-lookup"><span data-stu-id="62068-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="62068-223">Política 2: Auditar o acesso de Gravação e Execução a USBs permitidos.</span><span class="sxs-lookup"><span data-stu-id="62068-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="62068-224">Um exemplo para este caso de uso é: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** no exemplo [Cenário 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="62068-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="62068-225">Cenário 2: AuditAr o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos</span><span class="sxs-lookup"><span data-stu-id="62068-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="62068-226">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="62068-226">Create groups</span></span>

    1. <span data-ttu-id="62068-227">Grupo 1: Qualquer armazenamento removível e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="62068-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="62068-228">Um exemplo para este caso de uso é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="62068-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="62068-229">Grupo 2: USBs não aprovados com base nas propriedades do dispositivo, por exemplo, ID do fornecedor/ID do produto, Nome Amigável – **Grupo 65fa649a-a111-4912-9294-fb6337a25038 no** exemplo de [usbs Group.xmlnão aprovados.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="62068-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="62068-230">Você precisa substituir `&` `&amp;` no valor.</span><span class="sxs-lookup"><span data-stu-id="62068-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="62068-231">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="62068-231">Create policy</span></span>

    1. <span data-ttu-id="62068-232">Política 1: Bloquear o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos.</span><span class="sxs-lookup"><span data-stu-id="62068-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="62068-233">Um exemplo desse caso de uso é: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** no exemplo Scenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="62068-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="62068-234">Política 2: Auditar o acesso de gravação e execução a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="62068-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="62068-235">Um exemplo desse caso de uso é: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** no exemplo [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="62068-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="62068-236">Implantação e gerenciamento de política por meio da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="62068-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="62068-237">O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio da Política de Grupo a usuários ou dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="62068-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="62068-238">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="62068-238">Licensing</span></span>

<span data-ttu-id="62068-239">Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="62068-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="62068-240">Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="62068-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="62068-241">Implantando política por meio da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="62068-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="62068-242">Combine todos os grupos `<Groups>` `</Groups>` em um arquivo xml.</span><span class="sxs-lookup"><span data-stu-id="62068-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="62068-243">A imagem a seguir ilustra o exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir [USBs aprovados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="62068-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="A tela exibindo as configurações que permitem USBs aprovados específicos em dispositivos":::
    
2. <span data-ttu-id="62068-245">Combine todas as regras `<PolicyRules>` `</PolicyRules>` em um arquivo xml.</span><span class="sxs-lookup"><span data-stu-id="62068-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="62068-246">Se você quiser restringir um usuário específico, use a propriedade SID na Entrada.</span><span class="sxs-lookup"><span data-stu-id="62068-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="62068-247">Se não houver SID na Entrada de política, a Entrada será aplicada a todas as instâncias de logon do computador.</span><span class="sxs-lookup"><span data-stu-id="62068-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="62068-248">A imagem a seguir ilustra o uso da propriedade SID e um exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados [específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="62068-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="A tela exibindo um código que indica o uso do atributo de propriedade SID":::

3. <span data-ttu-id="62068-250">Salve arquivos XML de regra e grupo na pasta de compartilhamento de rede e coloque o caminho da pasta de compartilhamento de rede na configuração da Política de Grupo: Configuração do Computador -> Modelos **Administrativos -> Windows Componentes -> Microsoft Defender Antivírus -> Controle de Dispositivo: "Definir** grupos de política de controle de dispositivo" e "Definir regras de política de controle de dispositivo" .</span><span class="sxs-lookup"><span data-stu-id="62068-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="62068-251">O computador de destino deve ser capaz de acessar o compartilhamento de rede para ter a política.</span><span class="sxs-lookup"><span data-stu-id="62068-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="62068-252">No entanto, depois que a política é lida, a conexão de compartilhamento de rede não é mais necessária, mesmo após a reinicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="62068-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="A tela controle de dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="62068-254">Implantação e gerenciamento de política por meio do Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="62068-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="62068-255">O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio do OMA-URI a usuários ou dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="62068-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="62068-256">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="62068-256">Licensing</span></span>

<span data-ttu-id="62068-257">Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="62068-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="62068-258">Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="62068-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="62068-259">Permissão</span><span class="sxs-lookup"><span data-stu-id="62068-259">Permission</span></span>

<span data-ttu-id="62068-260">Para implantação de política no Intune, a conta deve ter permissões para criar, editar, atualizar ou excluir perfis de configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62068-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="62068-261">Você pode criar funções personalizadas ou usar qualquer uma das funções criadas com essas permissões.</span><span class="sxs-lookup"><span data-stu-id="62068-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="62068-262">Função de Gerente de Política e Perfil</span><span class="sxs-lookup"><span data-stu-id="62068-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="62068-263">Função personalizada com permissões Create/Edit/Update/Read/Delete/View Reports ativas para perfis de Configuração de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="62068-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="62068-264">Administrador global</span><span class="sxs-lookup"><span data-stu-id="62068-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="62068-265">Implantando política por meio do OMA-URI</span><span class="sxs-lookup"><span data-stu-id="62068-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="62068-266">**Microsoft Endpoint Manager centro de administração ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="62068-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="62068-267">Para cada Grupo, crie uma regra OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="62068-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="62068-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="62068-268">OMA-URI:</span></span>

      <span data-ttu-id="62068-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="62068-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="62068-270">Por exemplo, para **qualquer grupo de CD/DVD e** armazenamento removível no exemplo, o link deve ser:</span><span class="sxs-lookup"><span data-stu-id="62068-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="62068-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="62068-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="62068-272">Tipo de dados: cadeia de caracteres (arquivo XML)</span><span class="sxs-lookup"><span data-stu-id="62068-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="O arquivo xml do tipo de dados STRING":::

2. <span data-ttu-id="62068-274">Para cada política, também crie um OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="62068-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="62068-275">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="62068-275">OMA-URI:</span></span>

      <span data-ttu-id="62068-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="62068-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="62068-277">Por exemplo, para a regra Bloquear Gravação e Executar Acesso, mas permitir **USBs** aprovados no exemplo, o link deve ser:</span><span class="sxs-lookup"><span data-stu-id="62068-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="62068-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="62068-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="62068-279">Tipo de dados: cadeia de caracteres (arquivo XML)</span><span class="sxs-lookup"><span data-stu-id="62068-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Exibição de arquivo XML para o tipo de dados STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="62068-281">Implantando e gerenciando a política usando a interface do usuário do Intune</span><span class="sxs-lookup"><span data-stu-id="62068-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="62068-282">Esse recurso (no centro de administração do Microsoft Endpoint Manager ( > Dispositivos > Perfis de configuração > Criar perfil > Plataforma: Windows 10 e posterior do & Profile: Device Control) ainda não está https://endpoint.microsoft.com/) disponível.</span><span class="sxs-lookup"><span data-stu-id="62068-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="62068-283">Exibir dados do Controle de Dispositivo Removível Armazenamento Access Control no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="62068-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="62068-284">O Microsoft 365 de segurança mostra o armazenamento removível bloqueado pelo Controle de Dispositivo Removível Armazenamento Controle de Acesso.</span><span class="sxs-lookup"><span data-stu-id="62068-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="62068-285">Para acessar a Microsoft 365, você deve ter a seguinte assinatura:</span><span class="sxs-lookup"><span data-stu-id="62068-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="62068-286">Microsoft 365 relatório do E5</span><span class="sxs-lookup"><span data-stu-id="62068-286">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="A tela que representa o bloqueio do armazenamento removível":::

## <a name="frequently-asked-questions"></a><span data-ttu-id="62068-288">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="62068-288">Frequently asked questions</span></span>

<span data-ttu-id="62068-289">**Qual é a limitação de mídia de armazenamento removível para o número máximo de USBs?**</span><span class="sxs-lookup"><span data-stu-id="62068-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="62068-290">Validamos um grupo USB com 100.000 mídias - até 7 MB de tamanho.</span><span class="sxs-lookup"><span data-stu-id="62068-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="62068-291">A política funciona no Intune e no GPO sem problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="62068-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="62068-292">**Por que a política não funciona?**</span><span class="sxs-lookup"><span data-stu-id="62068-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="62068-293">O motivo mais comum é que não há nenhuma versão de cliente [antimalware necessária.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="62068-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="62068-294">Outro motivo pode ser que o arquivo XML não está formatado corretamente, por exemplo, não usando a formatação de marcação correta para o caractere "&" no arquivo XML, ou o editor de texto pode adicionar uma marca de ordem de byte (BOM) 0xEF 0xBB 0xBF no início dos arquivos que faz com que a análise XML não funcione.</span><span class="sxs-lookup"><span data-stu-id="62068-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="62068-295">Uma solução simples é baixar o arquivo [de exemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (selecione **Raw** e, em **seguida, Salvar como**) e atualizar.</span><span class="sxs-lookup"><span data-stu-id="62068-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="62068-296">Se houver um valor e a política for gerenciada por meio da Política de Grupo, verifique se o dispositivo cliente pode acessar o caminho XML da política.</span><span class="sxs-lookup"><span data-stu-id="62068-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="62068-297">**Como posso saber qual máquina está usando a versão do cliente antimalware desacordo na organização?**</span><span class="sxs-lookup"><span data-stu-id="62068-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="62068-298">Você pode usar a seguinte consulta para obter a versão do cliente antimalware no portal Microsoft 365 segurança:</span><span class="sxs-lookup"><span data-stu-id="62068-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
