---
title: Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection
description: Entenda os "recursos que ajudam a impedir que o usuário ou a máquina ou ambos usem mídia de armazenamento removível não autorizada
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
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538382"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="eca97-104">Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection</span><span class="sxs-lookup"><span data-stu-id="eca97-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="eca97-105">O Microsoft Defender for Endpoint Device Control Removível Armazenamento Proteção impede que o usuário ou máquina ou ambos usem mídia de armazenamento removível não autorizada.</span><span class="sxs-lookup"><span data-stu-id="eca97-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="eca97-106">Políticas de proteção</span><span class="sxs-lookup"><span data-stu-id="eca97-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="eca97-107">Instalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="eca97-107">Device installation</span></span>

<span data-ttu-id="eca97-108">**Recursos** - Impedir a instalação com ou sem exclusão com base em várias propriedades de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eca97-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="eca97-109">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eca97-109">**Description**</span></span>
- <span data-ttu-id="eca97-110">Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="eca97-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="eca97-111">Oferece suporte a MEM e GPO.</span><span class="sxs-lookup"><span data-stu-id="eca97-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="eca97-112">Suporte para '[Propriedades do dispositivo](#device-properties)' conforme listado.</span><span class="sxs-lookup"><span data-stu-id="eca97-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="eca97-113">Para obter mais informações sobre Windows, consulte Como controlar dispositivos USB e outras [mídias removíveis usando o Microsoft Defender para Ponto de Extremidade](control-usb-devices-using-intune.md).</span><span class="sxs-lookup"><span data-stu-id="eca97-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="eca97-114">**Plataforma com suporte** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="eca97-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="eca97-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eca97-115">**Description**</span></span>
- <span data-ttu-id="eca97-116">Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado</span><span class="sxs-lookup"><span data-stu-id="eca97-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="eca97-117">Para obter informações específicas do macOS, consulte [Controle de dispositivo para macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eca97-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="eca97-118">**Plataforma com suporte** - macOS Catalina 10.15.4+ (com extensões do sistema habilitadas)</span><span class="sxs-lookup"><span data-stu-id="eca97-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="eca97-119">Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-119">Removable storage Access Control</span></span>

<span data-ttu-id="eca97-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="eca97-120">**Capabilities**</span></span>
- <span data-ttu-id="eca97-121">*Auditoria* Acesso de leitura ou gravação ou execução ao armazenamento removível com base em várias propriedades de dispositivo, com ou sem exclusão.</span><span class="sxs-lookup"><span data-stu-id="eca97-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="eca97-122">*Impedir* Acesso de leitura ou gravação ou execução com ou sem exclusão - Permitir dispositivo específico com base em várias propriedades de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eca97-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="eca97-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eca97-123">**Description**</span></span>
- <span data-ttu-id="eca97-124">Aplicado em máquina ou usuário ou ambos – permite apenas que pessoas específicas que executam o acesso de Leitura/Gravação/Execução a armazenamento removível específico em máquina específica.</span><span class="sxs-lookup"><span data-stu-id="eca97-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="eca97-125">Suporte a MEM OMA-URI e GPO.</span><span class="sxs-lookup"><span data-stu-id="eca97-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="eca97-126">Suporte para '[Propriedades do dispositivo](#device-properties)' conforme listado.</span><span class="sxs-lookup"><span data-stu-id="eca97-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="eca97-127">Para ver o recurso Windows, consulte [Controle de acesso de armazenamento removível.](device-control-removable-storage-access-control.md)</span><span class="sxs-lookup"><span data-stu-id="eca97-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="eca97-128">**Plataforma com suporte** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="eca97-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="eca97-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eca97-129">**Description**</span></span>
- <span data-ttu-id="eca97-130">Aplicado no nível do computador: a mesma política se aplica a qualquer usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="eca97-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="eca97-131">Para obter informações específicas do macOS, consulte [Controle de dispositivo para macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eca97-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="eca97-132">**Plataforma com suporte** - macOS Catalina 10.15.4+ (com extensões do sistema habilitadas)</span><span class="sxs-lookup"><span data-stu-id="eca97-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="eca97-133">Windows Controle de Acesso a Dispositivo Portátil</span><span class="sxs-lookup"><span data-stu-id="eca97-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="eca97-134">**Recursos** - Negar acesso de leitura ou gravação a qualquer Windows [portátil](/windows-hardware/drivers/portable/), por exemplo: Tablet, iPhone.</span><span class="sxs-lookup"><span data-stu-id="eca97-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="eca97-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eca97-135">**Description**</span></span>
- <span data-ttu-id="eca97-136">Aplicado em máquina ou usuário ou ambos.</span><span class="sxs-lookup"><span data-stu-id="eca97-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="eca97-137">Suporte a MEM OMA-URI e GPO.</span><span class="sxs-lookup"><span data-stu-id="eca97-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="eca97-138">**Plataforma com suporte** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="eca97-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="eca97-139">Armazenamento removível de DLP do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="eca97-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="eca97-140">**Recursos** - Auditar ou Avisar ou Impedir que um usuário copie um item ou informações para mídia removível ou dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="eca97-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="eca97-141">**Descrição** - Para obter mais informações sobre Windows, consulte [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="eca97-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="eca97-142">**Plataforma com suporte** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="eca97-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="eca97-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="eca97-143">BitLocker</span></span> 

<span data-ttu-id="eca97-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="eca97-144">**Capabilities**</span></span>
- <span data-ttu-id="eca97-145">Bloquear dados a serem gravados em unidades removíveis que não BitLocker protegidas.</span><span class="sxs-lookup"><span data-stu-id="eca97-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="eca97-146">Bloquear o acesso a unidades removíveis, a menos que tenham sido criptografadas em um computador pertencente à sua organização</span><span class="sxs-lookup"><span data-stu-id="eca97-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="eca97-147">**Descrição** - Para obter mais informações sobre Windows, [consulte BitLocker – Unidade Removível Configurações](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="eca97-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="eca97-148">**Plataforma com suporte** - Windows 10</span><span class="sxs-lookup"><span data-stu-id="eca97-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="eca97-149">Propriedades do dispositivo</span><span class="sxs-lookup"><span data-stu-id="eca97-149">Device properties</span></span>

<span data-ttu-id="eca97-150">O Microsoft Defender for Endpoint Device Control Removable Armazenamento Protection permite restringir o acesso de armazenamento removível com base nas propriedades descritas na tabela abaixo:</span><span class="sxs-lookup"><span data-stu-id="eca97-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="eca97-151">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="eca97-151">Property Name</span></span>  |<span data-ttu-id="eca97-152">Políticas aplicáveis</span><span class="sxs-lookup"><span data-stu-id="eca97-152">Applicable Policies</span></span>  |<span data-ttu-id="eca97-153">Aplica-se a sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="eca97-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="eca97-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="eca97-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="eca97-155">Classe device</span><span class="sxs-lookup"><span data-stu-id="eca97-155">Device Class</span></span>    |     [<span data-ttu-id="eca97-156">Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="eca97-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="eca97-157">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-157">Windows</span></span>      |  <span data-ttu-id="eca97-158">Para obter informações sobre formatos de ID de dispositivo, consulte [classe de configuração do dispositivo](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span><span class="sxs-lookup"><span data-stu-id="eca97-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="eca97-159">**Observação:** a instalação do dispositivo pode ser aplicada a qualquer dispositivo, não apenas ao armazenamento removível.</span><span class="sxs-lookup"><span data-stu-id="eca97-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="eca97-160">ID principal</span><span class="sxs-lookup"><span data-stu-id="eca97-160">Primary ID</span></span>   |     <span data-ttu-id="eca97-161">Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="eca97-162">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-162">Windows</span></span>      |      <span data-ttu-id="eca97-163">A ID primária inclui armazenamento removível e CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="eca97-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="eca97-164">ID do dispositivo</span><span class="sxs-lookup"><span data-stu-id="eca97-164">Device ID</span></span>     |  <span data-ttu-id="eca97-165">[Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade;](control-usb-devices-using-intune.md) Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="eca97-166">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-166">Windows</span></span>   |    <span data-ttu-id="eca97-167">Para obter informações sobre formatos de ID de dispositivo, consulte [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="eca97-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="eca97-168">Hardware ID</span><span class="sxs-lookup"><span data-stu-id="eca97-168">Hardware ID</span></span>     |     <span data-ttu-id="eca97-169">[Como controlar dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade;](control-usb-devices-using-intune.md) Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="eca97-170">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-170">Windows</span></span>    |    <span data-ttu-id="eca97-171">Uma cadeia de caracteres identificou o dispositivo no sistema, por exemplo, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Observação:** a ID de hardware não é exclusiva; dispositivos diferentes podem compartilhar o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="eca97-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="eca97-172">ID da Instância</span><span class="sxs-lookup"><span data-stu-id="eca97-172">Instance ID</span></span>    | <span data-ttu-id="eca97-173">Instalação do dispositivo; Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="eca97-174">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-174">Windows</span></span>    |   <span data-ttu-id="eca97-175">Uma cadeia de caracteres identifica exclusivamente o dispositivo no sistema, por exemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="eca97-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="eca97-176">Nome Amigável</span><span class="sxs-lookup"><span data-stu-id="eca97-176">Friendly Name</span></span>     |     <span data-ttu-id="eca97-177">Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="eca97-178">Windows</span><span class="sxs-lookup"><span data-stu-id="eca97-178">Windows</span></span>      |    <span data-ttu-id="eca97-179">Uma cadeia de caracteres anexada ao dispositivo, por exemplo, Dispositivo USB de Disco Flash Genérico</span><span class="sxs-lookup"><span data-stu-id="eca97-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="eca97-180">ID do fornecedor/ID do produto</span><span class="sxs-lookup"><span data-stu-id="eca97-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="eca97-181">Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="eca97-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="eca97-182">Windows Mac</span></span>      |     <span data-ttu-id="eca97-183">ID do fornecedor é o código de fornecedor de quatro dígitos que o comitê USB atribui ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="eca97-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="eca97-184">A ID do produto é o código de produto de quatro dígitos que o fornecedor atribui ao dispositivo; Suporte a caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="eca97-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="eca97-185">NumberId de série</span><span class="sxs-lookup"><span data-stu-id="eca97-185">Serial NumberId</span></span>     |     <span data-ttu-id="eca97-186">Controle de acesso de armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="eca97-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="eca97-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="eca97-187">Windows Mac</span></span>   |     <span data-ttu-id="eca97-188">Por exemplo, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="eca97-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="eca97-189">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="eca97-189">Related topic</span></span>

- [<span data-ttu-id="eca97-190">Microsoft Defender for Endpoint Device Control Removível Armazenamento Access Control</span><span class="sxs-lookup"><span data-stu-id="eca97-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

