---
title: Microsoft Defender for Endpoint Device Control Printer Protection
description: O Microsoft Defender for Endpoint Device Control Printer Protection impede que as pessoas imprimirem por meio de impressoras não corporativas ou impressora USB não aprovada.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289686"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="36121-103">Proteção da Impressora de Controle de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="36121-103">Device Control Printer Protection</span></span>

<span data-ttu-id="36121-104">O Microsoft Defender for Endpoint Device Control Printer Protection impede que as pessoas imprimirem por meio de impressoras não corporativas ou impressora USB não aprovada.</span><span class="sxs-lookup"><span data-stu-id="36121-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="36121-105">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="36121-105">Licensing</span></span>

<span data-ttu-id="36121-106">Antes de começar a proteção de impressora, você deve [confirmar sua assinatura Microsoft 365 .](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="36121-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="36121-107">Para acessar e usar a Proteção contra Impressoras, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="36121-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="36121-108">Microsoft 365 E3 para implantação de funcionalidade/política</span><span class="sxs-lookup"><span data-stu-id="36121-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="36121-109">Microsoft 365 E5 para relatórios</span><span class="sxs-lookup"><span data-stu-id="36121-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="36121-110">Permissão</span><span class="sxs-lookup"><span data-stu-id="36121-110">Permission</span></span>

<span data-ttu-id="36121-111">Para a implantação de política no Intune, para implantar a política por meio do OMA-URI, a conta deve ter permissões para criar, editar, atualizar ou excluir perfis de configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="36121-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="36121-112">Você pode criar funções personalizadas ou usar qualquer uma das funções criadas com essas permissões:</span><span class="sxs-lookup"><span data-stu-id="36121-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="36121-113">Função gerenciador de política e perfil.</span><span class="sxs-lookup"><span data-stu-id="36121-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="36121-114">Ou função personalizada com permissões Create/Edit/Update/Read/Delete/View Reports ativas para perfis de Configuração de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="36121-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="36121-115">Ou administrador global</span><span class="sxs-lookup"><span data-stu-id="36121-115">Or Global admin</span></span>

<span data-ttu-id="36121-116">Para ver relatórios de configuração de dispositivo, a conta deve ter permissões de relatórios de exibição.</span><span class="sxs-lookup"><span data-stu-id="36121-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="36121-117">Você pode criar funções personalizadas ou usar as funções integrados com essas permissões:</span><span class="sxs-lookup"><span data-stu-id="36121-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="36121-118">Administrador de segurança global</span><span class="sxs-lookup"><span data-stu-id="36121-118">Global security admin</span></span>
- <span data-ttu-id="36121-119">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="36121-119">Security admin</span></span>
- <span data-ttu-id="36121-120">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="36121-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="36121-121">Preparar seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="36121-121">Prepare your endpoints</span></span>

<span data-ttu-id="36121-122">Certifique-se de que os Windows 10 dispositivos que você planeja implantar a Proteção de Impressora para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="36121-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="36121-123">Participe do Programa Insider.</span><span class="sxs-lookup"><span data-stu-id="36121-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="36121-124">As seguintes atualizações do Windows foram instaladas.</span><span class="sxs-lookup"><span data-stu-id="36121-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="36121-125">Para Windows 1809: instalar o [Windows KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="36121-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="36121-126">Para Windows 1909: instalar Windows Atualizar [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="36121-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="36121-127">Para Windows 2004 ou posterior</span><span class="sxs-lookup"><span data-stu-id="36121-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="36121-128">Se você estiver planejando implantar a política por meio da Política de Grupo, o dispositivo deve ser ingressado no MDATP; se você estiver planejando implantar a política por meio do MEM, o dispositivo deve ser ingressado no Intune.</span><span class="sxs-lookup"><span data-stu-id="36121-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="36121-129">Implantar política de Proteção de Impressora de Controle de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="36121-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="36121-130">Você pode implantar a política por meio da Política de Grupo ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="36121-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="36121-131">Título</span><span class="sxs-lookup"><span data-stu-id="36121-131">Title</span></span>|<span data-ttu-id="36121-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="36121-132">Description</span></span>|<span data-ttu-id="36121-133">Suporte A CSP</span><span class="sxs-lookup"><span data-stu-id="36121-133">CSP Support</span></span> | <span data-ttu-id="36121-134">Suporte a GPO</span><span class="sxs-lookup"><span data-stu-id="36121-134">GPO Support</span></span> | <span data-ttu-id="36121-135">Suporte baseado no usuário</span><span class="sxs-lookup"><span data-stu-id="36121-135">User-based Support</span></span> | <span data-ttu-id="36121-136">Suporte baseado em máquina</span><span class="sxs-lookup"><span data-stu-id="36121-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="36121-137">**Habilitar restrições de impressão de controle de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="36121-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="36121-138">Impedir a impressão de pessoas por meio de impressora não corporativa</span><span class="sxs-lookup"><span data-stu-id="36121-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="36121-139">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-139">Yes</span></span>|<span data-ttu-id="36121-140">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-140">Yes</span></span>|<span data-ttu-id="36121-141">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-141">Yes</span></span>|<span data-ttu-id="36121-142">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-142">Yes</span></span>|
|<span data-ttu-id="36121-143">**Lista de dispositivos de impressão conectados a USB aprovados**\*</span><span class="sxs-lookup"><span data-stu-id="36121-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="36121-144">Permitir impressora USB específica</span><span class="sxs-lookup"><span data-stu-id="36121-144">Allow specific USB printer</span></span>|<span data-ttu-id="36121-145">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-145">Yes</span></span>|<span data-ttu-id="36121-146">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-146">Yes</span></span>|<span data-ttu-id="36121-147">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-147">Yes</span></span>|<span data-ttu-id="36121-148">Sim</span><span class="sxs-lookup"><span data-stu-id="36121-148">Yes</span></span>|
|

<span data-ttu-id="36121-149">\* Essa política deve ser usada juntamente com **Habilitar Restrições** de Impressão de Controle de Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="36121-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="36121-150">Implantar política por meio do Intune</span><span class="sxs-lookup"><span data-stu-id="36121-150">Deploy policy via Intune</span></span>

<span data-ttu-id="36121-151">Para o Intune, atualmente a Proteção de Impressora de Controle de Dispositivo dá suporte apenas ao OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="36121-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="36121-152">Cenário 1: Bloquear a impressão de pessoas por meio de qualquer impressora não corporativa usando o Intune</span><span class="sxs-lookup"><span data-stu-id="36121-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="36121-153">Aplicar política sobre máquina:</span><span class="sxs-lookup"><span data-stu-id="36121-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="36121-154">Aplicar política sobre o usuário:</span><span class="sxs-lookup"><span data-stu-id="36121-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="36121-155">A cadeia de caracteres de suporte CSP com `<enabled/>` :</span><span class="sxs-lookup"><span data-stu-id="36121-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="linha de edição personalizada":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="36121-157">Cenário 2: Permitir impressoras USB aprovadas específicas usando o Intune</span><span class="sxs-lookup"><span data-stu-id="36121-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="36121-158">Aplicar política sobre máquina:</span><span class="sxs-lookup"><span data-stu-id="36121-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="36121-159">Aplicar política sobre o usuário:</span><span class="sxs-lookup"><span data-stu-id="36121-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="36121-160">A cadeia de caracteres de suporte do CSP com impressoras USB aprovadas por meio da propriedade 'ApprovedUsbPrintDevices', `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` exemplo:</span><span class="sxs-lookup"><span data-stu-id="36121-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="editar linha":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="36121-162">Implantar política por meio da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="36121-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="36121-163">Se o dispositivo não estiver ingressado no Intune, você também poderá implantar a política por meio da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="36121-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="36121-164">Cenário 1: Impedir que as pessoas imprimirem por meio de qualquer impressora não corporativa usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="36121-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="36121-165">Aplicar política sobre máquina:</span><span class="sxs-lookup"><span data-stu-id="36121-165">Apply policy over machine:</span></span>

  <span data-ttu-id="36121-166">Impressora modelos \> administrativos de configuração do \> computador: Habilitar restrições de impressão de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="36121-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="36121-167">Aplicar política sobre o usuário:</span><span class="sxs-lookup"><span data-stu-id="36121-167">Apply policy over user:</span></span>

  <span data-ttu-id="36121-168">Impressoras do Painel de Controle de Modelos Administrativos de Configuração do \> \> \> Usuário: Habilitar restrições de impressão de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="36121-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="habilitar restrições de impressão de dispositivo":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="36121-170">Cenário 2: Permitir impressoras USB aprovadas específicas usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="36121-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="36121-171">Aplicar política sobre máquina:</span><span class="sxs-lookup"><span data-stu-id="36121-171">Apply policy over machine:</span></span>

  <span data-ttu-id="36121-172">Impressora modelos \> administrativos de configuração do \> computador: lista de dispositivos de impressão conectados a USB aprovados</span><span class="sxs-lookup"><span data-stu-id="36121-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="36121-173">Aplicar política sobre o usuário:</span><span class="sxs-lookup"><span data-stu-id="36121-173">Apply policy over user:</span></span>

  <span data-ttu-id="36121-174">Impressoras do Painel de Controle de Modelos Administrativos de Configuração do \> \> \> Usuário: Lista de dispositivos de impressão conectados a USB aprovados</span><span class="sxs-lookup"><span data-stu-id="36121-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista de dispositivos de impressão usb conectados aprovados":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="36121-176">Exibir dados de Proteção de Impressora de Controle de Dispositivo no Portal do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="36121-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="36121-177">O [Microsoft 365 de segurança mostra](https://security.microsoft.com) a impressão bloqueada pela política de Proteção de Impressora de Controle de Dispositivo acima.</span><span class="sxs-lookup"><span data-stu-id="36121-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="busca avançada":::
