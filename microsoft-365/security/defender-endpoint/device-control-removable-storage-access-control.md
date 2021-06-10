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
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841181"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="5499e-104">Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control</span><span class="sxs-lookup"><span data-stu-id="5499e-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="5499e-105">O Microsoft Defender for Endpoint Device Control Removível Armazenamento Controle de Acesso permite que você faça a seguinte tarefa:</span><span class="sxs-lookup"><span data-stu-id="5499e-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="5499e-106">auditoria, permitindo ou impedindo o acesso de leitura, gravação ou execução ao armazenamento removível com ou sem exclusão</span><span class="sxs-lookup"><span data-stu-id="5499e-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="5499e-107">Privilégio</span><span class="sxs-lookup"><span data-stu-id="5499e-107">Privilege</span></span> |<span data-ttu-id="5499e-108">Permissão</span><span class="sxs-lookup"><span data-stu-id="5499e-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="5499e-109">Access</span><span class="sxs-lookup"><span data-stu-id="5499e-109">Access</span></span>    |  <span data-ttu-id="5499e-110">Leitura, Gravação, Execução</span><span class="sxs-lookup"><span data-stu-id="5499e-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="5499e-111">Modo de ação</span><span class="sxs-lookup"><span data-stu-id="5499e-111">Action Mode</span></span>    |    <span data-ttu-id="5499e-112">Auditar, Permitir, Impedir</span><span class="sxs-lookup"><span data-stu-id="5499e-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="5499e-113">Suporte A CSP</span><span class="sxs-lookup"><span data-stu-id="5499e-113">CSP Support</span></span>   |   <span data-ttu-id="5499e-114">Sim</span><span class="sxs-lookup"><span data-stu-id="5499e-114">Yes</span></span>      |
|<span data-ttu-id="5499e-115">Suporte a GPO</span><span class="sxs-lookup"><span data-stu-id="5499e-115">GPO Support</span></span>    |   <span data-ttu-id="5499e-116">Sim</span><span class="sxs-lookup"><span data-stu-id="5499e-116">Yes</span></span>      |
|<span data-ttu-id="5499e-117">Suporte baseado no usuário</span><span class="sxs-lookup"><span data-stu-id="5499e-117">User-based Support</span></span>     |   <span data-ttu-id="5499e-118">Sim</span><span class="sxs-lookup"><span data-stu-id="5499e-118">Yes</span></span>      |
|<span data-ttu-id="5499e-119">Suporte baseado em máquina</span><span class="sxs-lookup"><span data-stu-id="5499e-119">Machine-based Support</span></span>    |    <span data-ttu-id="5499e-120">Sim</span><span class="sxs-lookup"><span data-stu-id="5499e-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="5499e-121">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="5499e-121">Prepare your endpoints</span></span>

<span data-ttu-id="5499e-122">Implantar controle de acesso Armazenamento removível em dispositivos Windows 10 que tenham o Cliente Anti-malware Versão **4.18.2103.3 ou posterior**.</span><span class="sxs-lookup"><span data-stu-id="5499e-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="5499e-123">**4.18.2104 ou** posterior : Adicionar SerialNumberId, VID_PID, suporte a GPO baseado em filepath</span><span class="sxs-lookup"><span data-stu-id="5499e-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="5499e-124">**4.18.2105** ou posterior : Adicione suporte a curinga para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, a combinação de usuário específico em máquina específica, SSD removêvel (um SSD do SanDisk Extreme)/suporte A USB Attached SCSI (UAS)</span><span class="sxs-lookup"><span data-stu-id="5499e-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="A interface do PowerShell":::

## <a name="policy-properties"></a><span data-ttu-id="5499e-126">Propriedades de política</span><span class="sxs-lookup"><span data-stu-id="5499e-126">Policy properties</span></span>

<span data-ttu-id="5499e-127">Você pode usar as seguintes propriedades para criar um grupo de armazenamento removível:</span><span class="sxs-lookup"><span data-stu-id="5499e-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="5499e-128">**Nome da propriedade: ID do grupo**</span><span class="sxs-lookup"><span data-stu-id="5499e-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="5499e-129">Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa o grupo e será usado na política.</span><span class="sxs-lookup"><span data-stu-id="5499e-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="5499e-130">**Nome da propriedade: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="5499e-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="5499e-131">Descrição: listar as propriedades do dispositivo que você deseja usar para cobrir no grupo.</span><span class="sxs-lookup"><span data-stu-id="5499e-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="5499e-132">Listar as propriedades do dispositivo que você deseja usar para cobrir no grupo.</span><span class="sxs-lookup"><span data-stu-id="5499e-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="5499e-133">Para cada propriedade de dispositivo, consulte **a seção Propriedades do Dispositivo** acima para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5499e-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="5499e-134">Opções:</span><span class="sxs-lookup"><span data-stu-id="5499e-134">Options:</span></span>
    - <span data-ttu-id="5499e-135">ID principal</span><span class="sxs-lookup"><span data-stu-id="5499e-135">Primary ID</span></span>
        - <span data-ttu-id="5499e-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="5499e-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="5499e-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="5499e-137">CdRomDevices</span></span>
    - <span data-ttu-id="5499e-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="5499e-138">DeviceId</span></span>
    - <span data-ttu-id="5499e-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="5499e-139">HardwareId</span></span>
    - <span data-ttu-id="5499e-140">InstancePathId: InstancePathId é uma cadeia de caracteres que identifica exclusivamente o dispositivo no sistema, por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="5499e-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="5499e-141">O número no final (por exemplo, **&0**) representa o slot disponível e pode mudar de dispositivo para dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5499e-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="5499e-142">Para melhores resultados, use um curinga no final.</span><span class="sxs-lookup"><span data-stu-id="5499e-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="5499e-143">Por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="5499e-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="5499e-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="5499e-144">FriendlyNameId</span></span>
    - <span data-ttu-id="5499e-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="5499e-145">SerialNumberId</span></span>
    - <span data-ttu-id="5499e-146">VID</span><span class="sxs-lookup"><span data-stu-id="5499e-146">VID</span></span>
    - <span data-ttu-id="5499e-147">PID</span><span class="sxs-lookup"><span data-stu-id="5499e-147">PID</span></span>
    - <span data-ttu-id="5499e-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="5499e-148">VID_PID</span></span>
        - <span data-ttu-id="5499e-149">0751_55E0: corresponder a esse par exato do VID/PID</span><span class="sxs-lookup"><span data-stu-id="5499e-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="5499e-150">_55E0: corresponder qualquer mídia com PID=55E0</span><span class="sxs-lookup"><span data-stu-id="5499e-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="5499e-151">0751_: corresponder qualquer mídia com VID=0751</span><span class="sxs-lookup"><span data-stu-id="5499e-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="5499e-152">**Nome da propriedade: MatchType**</span><span class="sxs-lookup"><span data-stu-id="5499e-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="5499e-153">Descrição: quando há várias propriedades de dispositivo sendo usadas no DescriptorIDList, MatchType define a relação.</span><span class="sxs-lookup"><span data-stu-id="5499e-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="5499e-154">Opções:</span><span class="sxs-lookup"><span data-stu-id="5499e-154">Options:</span></span>
    - <span data-ttu-id="5499e-155">MatchAll: Quaisquer atributos sob o DescritorIdList serão **e** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema verificará se a USB atende aos dois valores.</span><span class="sxs-lookup"><span data-stu-id="5499e-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="5499e-156">MatchAny: Os atributos no DescriptorIdList serão **Ou** relação; por exemplo, se o administrador colocar DeviceID e InstancePathID, para cada USB conectado, o sistema fará a imposição desde que a USB tenha um valor **DeviceID** idêntico ou **InstanceID.**</span><span class="sxs-lookup"><span data-stu-id="5499e-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="5499e-157">A seguir estão as propriedades da política de controle de acesso:</span><span class="sxs-lookup"><span data-stu-id="5499e-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="5499e-158">**Nome da propriedade: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="5499e-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="5499e-159">Descrição: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), uma ID exclusiva, representa a política e será usada no relatório e na solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="5499e-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="5499e-160">**Nome da propriedade: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="5499e-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="5499e-161">Descrição: os grupos ao que a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="5499e-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="5499e-162">Se vários grupos são adicionados, a política será aplicada a qualquer mídia em todos esses grupos.</span><span class="sxs-lookup"><span data-stu-id="5499e-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="5499e-163">Opções: a ID/GUID do grupo deve ser usada nesta instância.</span><span class="sxs-lookup"><span data-stu-id="5499e-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="5499e-164">O exemplo a seguir mostra o uso de GroupID:</span><span class="sxs-lookup"><span data-stu-id="5499e-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="5499e-165">**Nome da propriedade: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="5499e-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="5499e-166">Descrição: os grupos aos que a política não será aplicada.</span><span class="sxs-lookup"><span data-stu-id="5499e-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="5499e-167">Opções: a ID/GUID do grupo deve ser usada nesta instância.</span><span class="sxs-lookup"><span data-stu-id="5499e-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="5499e-168">**Nome da propriedade: ID de entrada**</span><span class="sxs-lookup"><span data-stu-id="5499e-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="5499e-169">Descrição: Um PolicyRule pode ter várias entradas; cada entrada com um GUID exclusivo informa ao Controle de Dispositivo uma restrição.</span><span class="sxs-lookup"><span data-stu-id="5499e-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="5499e-170">**Nome da propriedade: Type**</span><span class="sxs-lookup"><span data-stu-id="5499e-170">**Property name: Type**</span></span>

1. <span data-ttu-id="5499e-171">Descrição: define a ação para os grupos de armazenamento removíveis em IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="5499e-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="5499e-172">Imposição: Permitir ou Negar</span><span class="sxs-lookup"><span data-stu-id="5499e-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="5499e-173">Auditoria: AuditAllowed ou AuditDenied</span><span class="sxs-lookup"><span data-stu-id="5499e-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="5499e-174">Opções:</span><span class="sxs-lookup"><span data-stu-id="5499e-174">Options:</span></span>
    - <span data-ttu-id="5499e-175">Permitir</span><span class="sxs-lookup"><span data-stu-id="5499e-175">Allow</span></span>
    - <span data-ttu-id="5499e-176">Negar</span><span class="sxs-lookup"><span data-stu-id="5499e-176">Deny</span></span>
    - <span data-ttu-id="5499e-177">AuditAllowed: define notificação e evento quando o acesso é permitido</span><span class="sxs-lookup"><span data-stu-id="5499e-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="5499e-178">AuditDenied: define a notificação e o evento quando o acesso é negado; tem que trabalhar em conjunto com **a entrada Negar.**</span><span class="sxs-lookup"><span data-stu-id="5499e-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="5499e-179">Quando houver tipos de conflito para a mesma mídia, o sistema aplicará o primeiro na política.</span><span class="sxs-lookup"><span data-stu-id="5499e-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="5499e-180">Um exemplo de tipo de conflito é **Permitir** e **Negar.**</span><span class="sxs-lookup"><span data-stu-id="5499e-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="5499e-181">**Nome da propriedade: Opções**</span><span class="sxs-lookup"><span data-stu-id="5499e-181">**Property name: Options**</span></span>

1. <span data-ttu-id="5499e-182">Descrição: define se a notificação deve ser exibida ou não.</span><span class="sxs-lookup"><span data-stu-id="5499e-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="A tela na qual o status do dispositivo pode ser visto":::

1. <span data-ttu-id="5499e-184">Opções: 0-4.</span><span class="sxs-lookup"><span data-stu-id="5499e-184">Options: 0-4.</span></span> <span data-ttu-id="5499e-185">Quando Type Allow ou Deny estiver selecionado:</span><span class="sxs-lookup"><span data-stu-id="5499e-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="5499e-186">0: nothing</span><span class="sxs-lookup"><span data-stu-id="5499e-186">0: nothing</span></span>
   - <span data-ttu-id="5499e-187">4: **desabilite AuditAllowed** e **AuditDenied** para esta Entrada.</span><span class="sxs-lookup"><span data-stu-id="5499e-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="5499e-188">Mesmo que **Block** aconteça e **AuditDenied** estiver configurada, o sistema não mostrará a notificação.</span><span class="sxs-lookup"><span data-stu-id="5499e-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="5499e-189">Quando Type **AuditAllowed** ou **AuditDenied** estiver selecionado:</span><span class="sxs-lookup"><span data-stu-id="5499e-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="5499e-190">0: nothing</span><span class="sxs-lookup"><span data-stu-id="5499e-190">0: nothing</span></span>
   - <span data-ttu-id="5499e-191">1: mostrar notificação</span><span class="sxs-lookup"><span data-stu-id="5499e-191">1: show notification</span></span>
   - <span data-ttu-id="5499e-192">2: enviar evento</span><span class="sxs-lookup"><span data-stu-id="5499e-192">2: send event</span></span>
   - <span data-ttu-id="5499e-193">3: mostrar evento de notificação e envio</span><span class="sxs-lookup"><span data-stu-id="5499e-193">3: show notification and send event</span></span>

<span data-ttu-id="5499e-194">**Nome da propriedade: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="5499e-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="5499e-195">Descrição: define o acesso.</span><span class="sxs-lookup"><span data-stu-id="5499e-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="5499e-196">Opções: 1 a 7:</span><span class="sxs-lookup"><span data-stu-id="5499e-196">Options: 1-7:</span></span>
    - <span data-ttu-id="5499e-197">1: Leitura</span><span class="sxs-lookup"><span data-stu-id="5499e-197">1: Read</span></span>
    - <span data-ttu-id="5499e-198">2: Gravar</span><span class="sxs-lookup"><span data-stu-id="5499e-198">2: Write</span></span>
    - <span data-ttu-id="5499e-199">3: Leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="5499e-199">3: Read and Write</span></span>
    - <span data-ttu-id="5499e-200">4: Execute</span><span class="sxs-lookup"><span data-stu-id="5499e-200">4: Execute</span></span>
    - <span data-ttu-id="5499e-201">5: Leitura e execução</span><span class="sxs-lookup"><span data-stu-id="5499e-201">5: Read and Execute</span></span>
    - <span data-ttu-id="5499e-202">6: Gravar e executar</span><span class="sxs-lookup"><span data-stu-id="5499e-202">6: Write and Execute</span></span>
    - <span data-ttu-id="5499e-203">7: Leitura e gravação e execução</span><span class="sxs-lookup"><span data-stu-id="5499e-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="5499e-204">Cenários comuns de controle de acesso Armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="5499e-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="5499e-205">Para ajudar a familiarizá-lo com o Microsoft Defender for Endpoint Removable Armazenamento Access Control, reunimos alguns cenários comuns para você seguir.</span><span class="sxs-lookup"><span data-stu-id="5499e-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="5499e-206">Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados específicos</span><span class="sxs-lookup"><span data-stu-id="5499e-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="5499e-207">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="5499e-207">Create groups</span></span>
    1. <span data-ttu-id="5499e-208">Grupo 1: Qualquer armazenamento removível e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="5499e-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="5499e-209">Um exemplo de armazenamento removível e CD/DVD é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="5499e-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="5499e-210">Grupo 2: USBs aprovados com base nas propriedades do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5499e-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="5499e-211">Um exemplo para este caso de uso é: ID de instância – Grupo **65fa649a-a111-4912-9294-fb6337a25038** no exemplo [usbs aprovados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) arquivo.</span><span class="sxs-lookup"><span data-stu-id="5499e-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5499e-212">Você precisa substituir `&` `&amp;` no valor.</span><span class="sxs-lookup"><span data-stu-id="5499e-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="5499e-213">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="5499e-213">Create policy</span></span>
    1. <span data-ttu-id="5499e-214">Política 1: Bloquear o Acesso de Gravação e Execução, mas permitir USBs aprovados.</span><span class="sxs-lookup"><span data-stu-id="5499e-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="5499e-215">Um exemplo para este caso de uso é: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** no exemplo Cenário 1 Bloquear Gravação e Executar Acesso, mas permitir [USBs aprovados .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) arquivo.</span><span class="sxs-lookup"><span data-stu-id="5499e-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="5499e-216">Política 2: Auditar o acesso de Gravação e Execução a USBs permitidos.</span><span class="sxs-lookup"><span data-stu-id="5499e-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="5499e-217">Um exemplo para este caso de uso é: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** no exemplo [Cenário 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="5499e-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="5499e-218">Cenário 2: AuditAr o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos</span><span class="sxs-lookup"><span data-stu-id="5499e-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="5499e-219">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="5499e-219">Create groups</span></span>
    1. <span data-ttu-id="5499e-220">Grupo 1: Qualquer armazenamento removível e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="5499e-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="5499e-221">Um exemplo para este caso de uso é: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** no exemplo [Any Removable Armazenamento and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="5499e-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="5499e-222">Grupo 2: USBs não aprovados com base nas propriedades do dispositivo, por exemplo, ID do fornecedor/ID do produto, Nome Amigável – **Grupo 65fa649a-a111-4912-9294-fb6337a25038 no** exemplo de [usbs Group.xmlnão aprovados.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="5499e-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5499e-223">Você precisa substituir `&` `&amp;` no valor.</span><span class="sxs-lookup"><span data-stu-id="5499e-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="5499e-224">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="5499e-224">Create policy</span></span>
    1. <span data-ttu-id="5499e-225">Política 1: Bloquear o acesso de Gravação e Execução a todos, mas bloquear USBs não aprovados específicos.</span><span class="sxs-lookup"><span data-stu-id="5499e-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="5499e-226">Um exemplo desse caso de uso é: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** no exemplo Scenario 2 Audit Write and Execute access to all but block specific [unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="5499e-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="5499e-227">Política 2: Auditar o acesso de gravação e execução a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="5499e-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="5499e-228">Um exemplo desse caso de uso é: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** no exemplo [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="5499e-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="5499e-229">Implantação e gerenciamento de política por meio da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="5499e-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="5499e-230">O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio da Política de Grupo a usuários ou dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="5499e-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="5499e-231">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="5499e-231">Licensing</span></span>

<span data-ttu-id="5499e-232">Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="5499e-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="5499e-233">Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5499e-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="5499e-234">Implantando política por meio da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="5499e-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="5499e-235">Combine todos os grupos `<Groups>` `</Groups>` em um arquivo xml.</span><span class="sxs-lookup"><span data-stu-id="5499e-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="5499e-236">A imagem a seguir ilustra o exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir [USBs aprovados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="5499e-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="A tela exibindo as configurações que permitem USBs aprovados específicos em dispositivos":::
    
2. <span data-ttu-id="5499e-238">Combine todas as regras `<PolicyRules>` `</PolicyRules>` em um arquivo xml.</span><span class="sxs-lookup"><span data-stu-id="5499e-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="5499e-239">Se você quiser restringir um usuário específico, use a propriedade SID na Entrada.</span><span class="sxs-lookup"><span data-stu-id="5499e-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="5499e-240">Se não houver SID na Entrada de política, a Entrada será aplicada a todas as instâncias de logon do computador.</span><span class="sxs-lookup"><span data-stu-id="5499e-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="5499e-241">A imagem a seguir ilustra o uso da propriedade SID e um exemplo do Cenário 1: Impedir o acesso de Gravação e Execução a todos, mas permitir USBs aprovados [específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="5499e-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="A tela exibindo um código que indica o uso do atributo de propriedade SID":::

3. <span data-ttu-id="5499e-243">Salve arquivos XML de regra e grupo na pasta de compartilhamento de rede e coloque o caminho da pasta de compartilhamento de rede na configuração da Política de Grupo: Configuração do Computador -> Modelos **Administrativos -> Windows Componentes -> Microsoft Defender Antivírus -> Controle de Dispositivo: "Definir** grupos de política de controle de dispositivo" e "Definir regras de política de controle de dispositivo" .</span><span class="sxs-lookup"><span data-stu-id="5499e-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="5499e-244">O computador de destino deve ser capaz de acessar o compartilhamento de rede para ter a política.</span><span class="sxs-lookup"><span data-stu-id="5499e-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="5499e-245">No entanto, depois que a política é lida, a conexão de compartilhamento de rede não é mais necessária, mesmo após a reinicialização do computador.</span><span class="sxs-lookup"><span data-stu-id="5499e-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="A tela controle de dispositivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="5499e-247">Implantação e gerenciamento de política por meio do Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="5499e-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="5499e-248">O recurso Controle de Acesso Armazenamento removível permite aplicar a política por meio do OMA-URI a usuários ou dispositivos ou ambos.</span><span class="sxs-lookup"><span data-stu-id="5499e-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="5499e-249">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="5499e-249">Licensing</span></span>

<span data-ttu-id="5499e-250">Antes de começar a Armazenamento Controle de Acesso [Removível,](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)você deve confirmar sua assinatura Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="5499e-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="5499e-251">Para acessar e usar o Controle de Acesso Armazenamento removível, você deve ter Microsoft 365 E3 ou Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5499e-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="5499e-252">Permissão</span><span class="sxs-lookup"><span data-stu-id="5499e-252">Permission</span></span>

<span data-ttu-id="5499e-253">Para implantação de política no Intune, a conta deve ter permissões para criar, editar, atualizar ou excluir perfis de configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5499e-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="5499e-254">Você pode criar funções personalizadas ou usar qualquer uma das funções criadas com essas permissões.</span><span class="sxs-lookup"><span data-stu-id="5499e-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="5499e-255">Função de Gerente de Política e Perfil</span><span class="sxs-lookup"><span data-stu-id="5499e-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="5499e-256">Função personalizada com permissões Create/Edit/Update/Read/Delete/View Reports ativas para perfis de Configuração de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="5499e-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="5499e-257">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5499e-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="5499e-258">Implantando política por meio do OMA-URI</span><span class="sxs-lookup"><span data-stu-id="5499e-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="5499e-259">**Microsoft Endpoint Manager centro de administração ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="5499e-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="5499e-260">Para cada Grupo, crie uma regra OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="5499e-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="5499e-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="5499e-261">OMA-URI:</span></span>

      <span data-ttu-id="5499e-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="5499e-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="5499e-263">Por exemplo, para **qualquer grupo de CD/DVD e** armazenamento removível no exemplo, o link deve ser:</span><span class="sxs-lookup"><span data-stu-id="5499e-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="5499e-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="5499e-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="5499e-265">Tipo de dados: cadeia de caracteres (arquivo XML)</span><span class="sxs-lookup"><span data-stu-id="5499e-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="O arquivo xml do tipo de dados STRING":::

2. <span data-ttu-id="5499e-267">Para cada política, também crie um OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="5499e-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="5499e-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="5499e-268">OMA-URI:</span></span>

      <span data-ttu-id="5499e-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="5499e-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="5499e-270">Por exemplo, para a regra Bloquear Gravação e Executar Acesso, mas permitir **USBs** aprovados no exemplo, o link deve ser:</span><span class="sxs-lookup"><span data-stu-id="5499e-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="5499e-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="5499e-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="5499e-272">Tipo de dados: cadeia de caracteres (arquivo XML)</span><span class="sxs-lookup"><span data-stu-id="5499e-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Exibição de arquivo XML para o tipo de dados STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="5499e-274">Implantando e gerenciando a política usando a interface do usuário do Intune</span><span class="sxs-lookup"><span data-stu-id="5499e-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="5499e-275">Esse recurso (no centro de administração do Microsoft Endpoint Manager ( > Dispositivos > Perfis de configuração > Criar perfil > Plataforma: Windows 10 e posterior do & Profile: Device Control) ainda não está https://endpoint.microsoft.com/) disponível.</span><span class="sxs-lookup"><span data-stu-id="5499e-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="5499e-276">Exibir dados do Controle de Dispositivo Removível Armazenamento Access Control no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5499e-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="5499e-277">O Microsoft 365 de segurança mostra o armazenamento removível bloqueado pelo Controle de Dispositivo Removível Armazenamento Controle de Acesso.</span><span class="sxs-lookup"><span data-stu-id="5499e-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="5499e-278">Para acessar a Microsoft 365, você deve ter a seguinte assinatura:</span><span class="sxs-lookup"><span data-stu-id="5499e-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="5499e-279">Microsoft 365 relatório do E5</span><span class="sxs-lookup"><span data-stu-id="5499e-279">Microsoft 365 for E5 reporting</span></span>

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
