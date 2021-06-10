---
title: Controle de dispositivo para macOS
description: Saiba como configurar o Microsoft Defender para Ponto de Extremidade no Mac para reduzir as ameaças de armazenamento removível, como dispositivos USB.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, dispositivo, controle, usb, removível, mídia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 39f8367c34e98c5e9dd11e9716f08e6c9e7fd9c0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935120"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="bbe02-104">Controle de dispositivo para macOS</span><span class="sxs-lookup"><span data-stu-id="bbe02-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bbe02-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bbe02-105">**Applies to:**</span></span>
- [<span data-ttu-id="bbe02-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bbe02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bbe02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbe02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bbe02-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bbe02-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bbe02-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bbe02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="bbe02-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbe02-110">Requirements</span></span>

<span data-ttu-id="bbe02-111">O controle de dispositivo para macOS tem os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="bbe02-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="bbe02-112">Direito do Microsoft Defender para Ponto de Extremidade (pode ser avaliação)</span><span class="sxs-lookup"><span data-stu-id="bbe02-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="bbe02-113">Versão mínima do sistema operacional: macOS 10.15.4 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbe02-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="bbe02-114">Versão mínima do produto: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="bbe02-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="bbe02-115">Seu dispositivo deve estar em execução com extensões do sistema (esse é o padrão no macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="bbe02-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="bbe02-116">Você pode verificar se seu dispositivo está sendo executado em extensões do sistema executando o seguinte comando e verificar se ele está imprimindo `endpoint_security_extension` no console:</span><span class="sxs-lookup"><span data-stu-id="bbe02-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="bbe02-117">Seu dispositivo deve estar `Beta` no (anteriormente chamado ) canal de atualização do Microsoft `InsiderFast` AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="bbe02-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="bbe02-118">Para obter mais informações, [consulte Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="bbe02-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="bbe02-119">Você pode verificar o canal de atualização usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="bbe02-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="bbe02-120">Se o comando acima não imprimir ou `Beta` , execute o seguinte comando do `InsiderFast` Terminal.</span><span class="sxs-lookup"><span data-stu-id="bbe02-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="bbe02-121">A atualização de canal entra em vigor na próxima vez que o produto é iniciado (quando a próxima atualização do produto é instalada ou quando o dispositivo é reiniciado).</span><span class="sxs-lookup"><span data-stu-id="bbe02-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="bbe02-122">Como alternativa, se você estiver em um ambiente gerenciado (JAMF ou Intune), poderá configurar o canal de atualização remotamente.</span><span class="sxs-lookup"><span data-stu-id="bbe02-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="bbe02-123">Para obter mais informações, [consulte Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span><span class="sxs-lookup"><span data-stu-id="bbe02-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="bbe02-124">Política de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-124">Device control policy</span></span>

<span data-ttu-id="bbe02-125">Para configurar o controle de dispositivo para macOS, você deve criar uma política que descreva as restrições que você deseja colocar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbe02-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="bbe02-126">A política de controle de dispositivo está incluída no perfil de configuração usado para configurar todas as outras configurações do produto.</span><span class="sxs-lookup"><span data-stu-id="bbe02-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="bbe02-127">Para obter mais informações, consulte [Estrutura de perfil de configuração](mac-preferences.md#configuration-profile-structure).</span><span class="sxs-lookup"><span data-stu-id="bbe02-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="bbe02-128">No perfil de configuração, a política de controle de dispositivo é definida na seção a seguir:</span><span class="sxs-lookup"><span data-stu-id="bbe02-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="bbe02-129">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-129">Section</span></span>|<span data-ttu-id="bbe02-130">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-131">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-132">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-132">**Key**</span></span> | <span data-ttu-id="bbe02-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="bbe02-133">deviceControl</span></span> |
| <span data-ttu-id="bbe02-134">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-134">**Data type**</span></span> | <span data-ttu-id="bbe02-135">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="bbe02-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bbe02-136">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bbe02-136">**Comments**</span></span> | <span data-ttu-id="bbe02-137">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="bbe02-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="bbe02-138">A política de controle de dispositivo pode ser usada para:</span><span class="sxs-lookup"><span data-stu-id="bbe02-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="bbe02-139">Personalizar o destino da URL para notificações ativas pelo controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="bbe02-140">Permitir ou bloquear dispositivos removíveis</span><span class="sxs-lookup"><span data-stu-id="bbe02-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="bbe02-141">Personalizar destino de URL para notificações ativas pelo controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="bbe02-142">Quando a política de controle de dispositivo que você colocou é imposta em um dispositivo (por exemplo, o acesso a um dispositivo de mídia removível é restrito), uma notificação é exibida para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bbe02-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Notificação de controle de dispositivo](images/mac-device-control-notification.png)

<span data-ttu-id="bbe02-144">Quando os usuários finais clicam nessa notificação, uma página da Web é aberta no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="bbe02-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="bbe02-145">Você pode configurar a URL aberta quando os usuários finais clicarem na notificação.</span><span class="sxs-lookup"><span data-stu-id="bbe02-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="bbe02-146">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-146">Section</span></span>|<span data-ttu-id="bbe02-147">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-148">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-149">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-149">**Key**</span></span> | <span data-ttu-id="bbe02-150">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="bbe02-150">navigationTarget</span></span> |
| <span data-ttu-id="bbe02-151">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-151">**Data type**</span></span> | <span data-ttu-id="bbe02-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-152">String</span></span> |
| <span data-ttu-id="bbe02-153">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bbe02-153">**Comments**</span></span> | <span data-ttu-id="bbe02-154">Se não estiver definido, o produto usará uma URL padrão apontando para uma página genérica explicando a ação tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="bbe02-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="bbe02-155">Permitir ou bloquear dispositivos removíveis</span><span class="sxs-lookup"><span data-stu-id="bbe02-155">Allow or block removable devices</span></span>

<span data-ttu-id="bbe02-156">A seção mídia removível da política de controle de dispositivo é usada para restringir o acesso à mídia removível.</span><span class="sxs-lookup"><span data-stu-id="bbe02-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="bbe02-157">Os seguintes tipos de mídia removível têm suporte no momento e podem ser incluídos na política: dispositivos de armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="bbe02-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="bbe02-158">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-158">Section</span></span>|<span data-ttu-id="bbe02-159">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-160">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-161">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-161">**Key**</span></span> | <span data-ttu-id="bbe02-162">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="bbe02-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="bbe02-163">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-163">**Data type**</span></span> | <span data-ttu-id="bbe02-164">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="bbe02-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="bbe02-165">**Comments**</span><span class="sxs-lookup"><span data-stu-id="bbe02-165">**Comments**</span></span> | <span data-ttu-id="bbe02-166">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="bbe02-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="bbe02-167">Esta seção da política é hierárquica, permitindo a máxima flexibilidade e abrangendo uma ampla variedade de casos de uso.</span><span class="sxs-lookup"><span data-stu-id="bbe02-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="bbe02-168">No nível superior estão fornecedores, identificados por uma ID de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe02-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="bbe02-169">Para cada fornecedor, há produtos, identificados por uma ID do produto.</span><span class="sxs-lookup"><span data-stu-id="bbe02-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="bbe02-170">Por fim, para cada produto, há números de série que denotam dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="bbe02-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="bbe02-171">Para obter informações sobre como encontrar os identificadores de dispositivo, consulte [Procurar identificadores de dispositivo](#look-up-device-identifiers).</span><span class="sxs-lookup"><span data-stu-id="bbe02-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="bbe02-172">A política é avaliada da entrada mais específica para a mais geral.</span><span class="sxs-lookup"><span data-stu-id="bbe02-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="bbe02-173">Ou seja, quando um dispositivo está conectado, o produto tenta encontrar a combinação mais específica na política para cada dispositivo de mídia removível e aplicar as permissões nesse nível.</span><span class="sxs-lookup"><span data-stu-id="bbe02-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="bbe02-174">Se não houver nenhuma combinação, a próxima melhor combinação será aplicada, até a permissão especificada no nível superior, que é o padrão quando um dispositivo não corresponder a qualquer outra entrada na política.</span><span class="sxs-lookup"><span data-stu-id="bbe02-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="bbe02-175">Nível de imposição de política</span><span class="sxs-lookup"><span data-stu-id="bbe02-175">Policy enforcement level</span></span>

<span data-ttu-id="bbe02-176">Na seção mídia removível, há uma opção para definir o nível de imposição, que pode levar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bbe02-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="bbe02-177">`audit` - Nesse nível de imposição, se o acesso a um dispositivo for restrito, uma notificação será exibida para o usuário, no entanto, o dispositivo ainda poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="bbe02-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="bbe02-178">Esse nível de imposição pode ser útil para avaliar a eficácia de uma política.</span><span class="sxs-lookup"><span data-stu-id="bbe02-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="bbe02-179">`block` - Nesse nível de imposição, as operações que o usuário pode executar no dispositivo são limitadas ao que é definido na política.</span><span class="sxs-lookup"><span data-stu-id="bbe02-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="bbe02-180">Além disso, uma notificação é criada para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bbe02-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="bbe02-181">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-181">Section</span></span>|<span data-ttu-id="bbe02-182">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-183">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-184">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-184">**Key**</span></span> | <span data-ttu-id="bbe02-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="bbe02-185">enforcementLevel</span></span> |
| <span data-ttu-id="bbe02-186">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-186">**Data type**</span></span> | <span data-ttu-id="bbe02-187">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-187">String</span></span> |
| <span data-ttu-id="bbe02-188">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="bbe02-188">**Possible values**</span></span> | <span data-ttu-id="bbe02-189">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="bbe02-189">audit (default)</span></span> <br/> <span data-ttu-id="bbe02-190">block</span><span class="sxs-lookup"><span data-stu-id="bbe02-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="bbe02-191">Nível de permissão padrão</span><span class="sxs-lookup"><span data-stu-id="bbe02-191">Default permission level</span></span>

<span data-ttu-id="bbe02-192">No nível superior da seção mídia removível, você pode configurar o nível de permissão padrão para dispositivos que não corresponderem a mais nada na política.</span><span class="sxs-lookup"><span data-stu-id="bbe02-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="bbe02-193">Essa configuração pode ser definida como:</span><span class="sxs-lookup"><span data-stu-id="bbe02-193">This setting can be set to:</span></span>

- <span data-ttu-id="bbe02-194">`none` - Nenhuma operação pode ser executada no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="bbe02-195">Uma combinação dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bbe02-195">A combination of the following values:</span></span>
    - <span data-ttu-id="bbe02-196">`read` - As operações de leitura são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="bbe02-197">`write` - As operações de gravação são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="bbe02-198">`execute` - Operações de execução são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="bbe02-199">Se estiver presente no nível de permissão, quaisquer outras permissões `none` ( , ou ) serão `read` `write` `execute` ignoradas.</span><span class="sxs-lookup"><span data-stu-id="bbe02-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="bbe02-200">A `execute` permissão refere-se apenas à execução de binários Mach-O.</span><span class="sxs-lookup"><span data-stu-id="bbe02-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="bbe02-201">Ele não inclui a execução de scripts ou outros tipos de cargas.</span><span class="sxs-lookup"><span data-stu-id="bbe02-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="bbe02-202">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-202">Section</span></span>|<span data-ttu-id="bbe02-203">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-204">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-205">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-205">**Key**</span></span> | <span data-ttu-id="bbe02-206">permission</span><span class="sxs-lookup"><span data-stu-id="bbe02-206">permission</span></span> |
| <span data-ttu-id="bbe02-207">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-207">**Data type**</span></span> | <span data-ttu-id="bbe02-208">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-208">Array of strings</span></span> |
| <span data-ttu-id="bbe02-209">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="bbe02-209">**Possible values**</span></span> | <span data-ttu-id="bbe02-210">nenhuma</span><span class="sxs-lookup"><span data-stu-id="bbe02-210">none</span></span> <br/> <span data-ttu-id="bbe02-211">leitura</span><span class="sxs-lookup"><span data-stu-id="bbe02-211">read</span></span> <br/> <span data-ttu-id="bbe02-212">gravação</span><span class="sxs-lookup"><span data-stu-id="bbe02-212">write</span></span> <br/> <span data-ttu-id="bbe02-213">execute</span><span class="sxs-lookup"><span data-stu-id="bbe02-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="bbe02-214">Restringir mídia removível por fornecedor, produto e número de série</span><span class="sxs-lookup"><span data-stu-id="bbe02-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="bbe02-215">Conforme descrito em [Permitir](#allow-or-block-removable-devices)ou bloquear dispositivos removíveis, mídia removível, como dispositivos USB, pode ser identificada pela ID do fornecedor, ID do produto e número de série.</span><span class="sxs-lookup"><span data-stu-id="bbe02-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="bbe02-216">No nível superior da política de mídia removível, você pode, opcionalmente, definir restrições mais granulares no nível do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe02-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="bbe02-217">O `vendors` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pela ID do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe02-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="bbe02-218">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-218">Section</span></span>|<span data-ttu-id="bbe02-219">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-220">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-221">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-221">**Key**</span></span> | <span data-ttu-id="bbe02-222">vendors</span><span class="sxs-lookup"><span data-stu-id="bbe02-222">vendors</span></span> |
| <span data-ttu-id="bbe02-223">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-223">**Data type**</span></span> | <span data-ttu-id="bbe02-224">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="bbe02-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="bbe02-225">Para cada fornecedor, você pode especificar o nível de permissão desejado para dispositivos desse fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bbe02-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="bbe02-226">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-226">Section</span></span>|<span data-ttu-id="bbe02-227">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-228">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-229">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-229">**Key**</span></span> | <span data-ttu-id="bbe02-230">permission</span><span class="sxs-lookup"><span data-stu-id="bbe02-230">permission</span></span> |
| <span data-ttu-id="bbe02-231">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-231">**Data type**</span></span> | <span data-ttu-id="bbe02-232">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-232">Array of strings</span></span> |
| <span data-ttu-id="bbe02-233">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="bbe02-233">**Possible values**</span></span> | <span data-ttu-id="bbe02-234">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="bbe02-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="bbe02-235">Além disso, opcionalmente, você pode especificar o conjunto de produtos pertencentes a esse fornecedor para o qual as permissões mais granulares são definidas.</span><span class="sxs-lookup"><span data-stu-id="bbe02-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="bbe02-236">O `products` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pela ID do produto.</span><span class="sxs-lookup"><span data-stu-id="bbe02-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="bbe02-237">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-237">Section</span></span>|<span data-ttu-id="bbe02-238">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-239">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-240">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-240">**Key**</span></span> | <span data-ttu-id="bbe02-241">products</span><span class="sxs-lookup"><span data-stu-id="bbe02-241">products</span></span> |
| <span data-ttu-id="bbe02-242">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-242">**Data type**</span></span> | <span data-ttu-id="bbe02-243">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="bbe02-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="bbe02-244">Para cada produto, você pode especificar o nível de permissão desejado para esse produto.</span><span class="sxs-lookup"><span data-stu-id="bbe02-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="bbe02-245">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-245">Section</span></span>|<span data-ttu-id="bbe02-246">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-247">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-248">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-248">**Key**</span></span> | <span data-ttu-id="bbe02-249">permission</span><span class="sxs-lookup"><span data-stu-id="bbe02-249">permission</span></span> |
| <span data-ttu-id="bbe02-250">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-250">**Data type**</span></span> | <span data-ttu-id="bbe02-251">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-251">Array of strings</span></span> |
| <span data-ttu-id="bbe02-252">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="bbe02-252">**Possible values**</span></span> | <span data-ttu-id="bbe02-253">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="bbe02-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="bbe02-254">Além disso, você pode especificar um conjunto opcional de números de série para os quais as permissões mais granulares são definidas.</span><span class="sxs-lookup"><span data-stu-id="bbe02-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="bbe02-255">O `serialNumbers` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pelo número de série.</span><span class="sxs-lookup"><span data-stu-id="bbe02-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="bbe02-256">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-256">Section</span></span>|<span data-ttu-id="bbe02-257">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-258">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-259">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-259">**Key**</span></span> | <span data-ttu-id="bbe02-260">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="bbe02-260">serialNumbers</span></span> |
| <span data-ttu-id="bbe02-261">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-261">**Data type**</span></span> | <span data-ttu-id="bbe02-262">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="bbe02-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="bbe02-263">Para cada número de série, você pode especificar o nível de permissão desejado.</span><span class="sxs-lookup"><span data-stu-id="bbe02-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="bbe02-264">Section</span><span class="sxs-lookup"><span data-stu-id="bbe02-264">Section</span></span>|<span data-ttu-id="bbe02-265">Valor</span><span class="sxs-lookup"><span data-stu-id="bbe02-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="bbe02-266">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="bbe02-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="bbe02-267">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bbe02-267">**Key**</span></span> | <span data-ttu-id="bbe02-268">permission</span><span class="sxs-lookup"><span data-stu-id="bbe02-268">permission</span></span> |
| <span data-ttu-id="bbe02-269">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bbe02-269">**Data type**</span></span> | <span data-ttu-id="bbe02-270">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="bbe02-270">Array of strings</span></span> |
| <span data-ttu-id="bbe02-271">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="bbe02-271">**Possible values**</span></span> | <span data-ttu-id="bbe02-272">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="bbe02-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="bbe02-273">Política de controle de dispositivo de exemplo</span><span class="sxs-lookup"><span data-stu-id="bbe02-273">Example device control policy</span></span>

<span data-ttu-id="bbe02-274">O exemplo a seguir mostra como todos os conceitos acima podem ser combinados em uma política de controle de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbe02-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="bbe02-275">No exemplo a seguir, observe a natureza hierárquica da política de mídia removível.</span><span class="sxs-lookup"><span data-stu-id="bbe02-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="bbe02-276">Incluímos mais exemplos de políticas de controle de dispositivo nos seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="bbe02-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="bbe02-277">Exemplos de políticas de controle de dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="bbe02-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="bbe02-278">Exemplos de políticas de controle de dispositivo para JAMF</span><span class="sxs-lookup"><span data-stu-id="bbe02-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="bbe02-279">Procurar identificadores de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-279">Look up device identifiers</span></span>

<span data-ttu-id="bbe02-280">Para encontrar a ID do fornecedor, a ID do produto e o número de série de um dispositivo USB:</span><span class="sxs-lookup"><span data-stu-id="bbe02-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="bbe02-281">Faça logoff em um dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="bbe02-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="bbe02-282">Conecte o dispositivo USB para o qual você deseja procurar os identificadores.</span><span class="sxs-lookup"><span data-stu-id="bbe02-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="bbe02-283">No menu de nível superior do macOS, selecione **Sobre Este Mac**.</span><span class="sxs-lookup"><span data-stu-id="bbe02-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Sobre esse Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="bbe02-285">Selecione **Relatório do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="bbe02-285">Select **System Report**.</span></span>

    ![Relatório do Sistema](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="bbe02-287">Na coluna esquerda, selecione **USB**.</span><span class="sxs-lookup"><span data-stu-id="bbe02-287">From the left column, select **USB**.</span></span>

    ![Modo de exibição de todos os dispositivos USB](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="bbe02-289">Em **Árvore de Dispositivo USB,** navegue até o dispositivo USB conectado.</span><span class="sxs-lookup"><span data-stu-id="bbe02-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Detalhes de um dispositivo USB](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="bbe02-291">A ID do fornecedor, a ID do produto e o número de série são exibidos.</span><span class="sxs-lookup"><span data-stu-id="bbe02-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="bbe02-292">Ao adicionar a ID do fornecedor e a ID do produto à política de mídia removível, você só deve adicionar a parte depois `0x` de .</span><span class="sxs-lookup"><span data-stu-id="bbe02-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="bbe02-293">Por exemplo, na imagem abaixo, a ID do fornecedor é `1000` e a ID do produto é `090c` .</span><span class="sxs-lookup"><span data-stu-id="bbe02-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="bbe02-294">Descobrir dispositivos USB em sua organização</span><span class="sxs-lookup"><span data-stu-id="bbe02-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="bbe02-295">Você pode exibir eventos de montagem, desmontagem e alteração de volume provenientes de dispositivos USB no Microsoft Defender para a busca avançada do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="bbe02-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="bbe02-296">Esses eventos podem ser úteis para identificar atividades de uso suspeitas ou realizar investigações internas.</span><span class="sxs-lookup"><span data-stu-id="bbe02-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="bbe02-297">Implantação da política de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbe02-297">Device control policy deployment</span></span>

<span data-ttu-id="bbe02-298">A política de controle de dispositivo deve ser incluída ao lado das outras configurações do produto, conforme descrito em Definir preferências do Microsoft Defender para Ponto de Extremidade [no macOS](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="bbe02-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="bbe02-299">Esse perfil pode ser implantado usando as instruções listadas na [implantação do perfil de configuração.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="bbe02-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="bbe02-300">Dicas de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bbe02-300">Troubleshooting tips</span></span>

<span data-ttu-id="bbe02-301">Depois de empurrar o perfil de configuração através do Intune ou JAMF, você pode verificar se ele foi escolhido com êxito pelo produto executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="bbe02-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="bbe02-302">Este comando imprimirá para saída padrão a política de controle de dispositivo que o produto está usando.</span><span class="sxs-lookup"><span data-stu-id="bbe02-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="bbe02-303">Caso isso imprime , certifique-se de que (a) o perfil de configuração tenha sido realmente enviado para o seu dispositivo do console de gerenciamento e (b) ela seja uma política de controle de dispositivo válida, conforme descrito `Policy is empty` neste documento.</span><span class="sxs-lookup"><span data-stu-id="bbe02-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="bbe02-304">Em um dispositivo onde a política foi entregue com êxito e onde há um ou mais dispositivos conectados, você pode executar o comando a seguir para listar todos os dispositivos e as permissões efetivas aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="bbe02-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="bbe02-305">Exemplo de saída:</span><span class="sxs-lookup"><span data-stu-id="bbe02-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="bbe02-306">No exemplo acima, há apenas um dispositivo de mídia removível conectado e ele tem e permissões, de acordo com a política de controle de dispositivo que foi entregue `read` `execute` ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbe02-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbe02-307">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bbe02-307">Related topics</span></span>

- [<span data-ttu-id="bbe02-308">Exemplos de políticas de controle de dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="bbe02-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="bbe02-309">Exemplos de políticas de controle de dispositivo para JAMF</span><span class="sxs-lookup"><span data-stu-id="bbe02-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
