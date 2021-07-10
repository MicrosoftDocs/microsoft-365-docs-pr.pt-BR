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
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363974"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="e84e6-104">Controle de dispositivo para macOS</span><span class="sxs-lookup"><span data-stu-id="e84e6-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e84e6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e84e6-105">**Applies to:**</span></span>
- [<span data-ttu-id="e84e6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e84e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e84e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e84e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e84e6-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e84e6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e84e6-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e84e6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="e84e6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e84e6-110">Requirements</span></span>

<span data-ttu-id="e84e6-111">O controle de dispositivo para macOS tem os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="e84e6-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="e84e6-112">Direito do Microsoft Defender para Ponto de Extremidade (pode ser avaliação)</span><span class="sxs-lookup"><span data-stu-id="e84e6-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="e84e6-113">Versão mínima do sistema operacional: macOS 11 ou superior</span><span class="sxs-lookup"><span data-stu-id="e84e6-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="e84e6-114">Versão mínima do produto: 101.34.20</span><span class="sxs-lookup"><span data-stu-id="e84e6-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="e84e6-115">Política de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-115">Device control policy</span></span>

<span data-ttu-id="e84e6-116">Para configurar o controle de dispositivo para macOS, você deve criar uma política que descreva as restrições que você deseja colocar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e84e6-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="e84e6-117">A política de controle de dispositivo está incluída no perfil de configuração usado para configurar todas as outras configurações do produto.</span><span class="sxs-lookup"><span data-stu-id="e84e6-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="e84e6-118">Para obter mais informações, consulte [Estrutura de perfil de configuração](mac-preferences.md#configuration-profile-structure).</span><span class="sxs-lookup"><span data-stu-id="e84e6-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="e84e6-119">No perfil de configuração, a política de controle de dispositivo é definida na seção a seguir:</span><span class="sxs-lookup"><span data-stu-id="e84e6-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="e84e6-120">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-120">Section</span></span>|<span data-ttu-id="e84e6-121">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-122">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-123">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-123">**Key**</span></span> | <span data-ttu-id="e84e6-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="e84e6-124">deviceControl</span></span> |
| <span data-ttu-id="e84e6-125">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-125">**Data type**</span></span> | <span data-ttu-id="e84e6-126">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e84e6-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e84e6-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e84e6-127">**Comments**</span></span> | <span data-ttu-id="e84e6-128">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e84e6-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="e84e6-129">A política de controle de dispositivo pode ser usada para:</span><span class="sxs-lookup"><span data-stu-id="e84e6-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="e84e6-130">Personalizar o destino da URL para notificações ativas pelo controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="e84e6-131">Permitir ou bloquear dispositivos removíveis</span><span class="sxs-lookup"><span data-stu-id="e84e6-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="e84e6-132">Personalizar destino de URL para notificações ativas pelo controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="e84e6-133">Quando a política de controle de dispositivo que você colocou é imposta em um dispositivo (por exemplo, o acesso a um dispositivo de mídia removível é restrito), uma notificação é exibida para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e84e6-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Notificação de controle de dispositivo](images/mac-device-control-notification.png)

<span data-ttu-id="e84e6-135">Quando os usuários finais clicam nessa notificação, uma página da Web é aberta no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="e84e6-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="e84e6-136">Você pode configurar a URL aberta quando os usuários finais clicarem na notificação.</span><span class="sxs-lookup"><span data-stu-id="e84e6-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="e84e6-137">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-137">Section</span></span>|<span data-ttu-id="e84e6-138">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-139">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-140">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-140">**Key**</span></span> | <span data-ttu-id="e84e6-141">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="e84e6-141">navigationTarget</span></span> |
| <span data-ttu-id="e84e6-142">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-142">**Data type**</span></span> | <span data-ttu-id="e84e6-143">String</span><span class="sxs-lookup"><span data-stu-id="e84e6-143">String</span></span> |
| <span data-ttu-id="e84e6-144">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e84e6-144">**Comments**</span></span> | <span data-ttu-id="e84e6-145">Se não estiver definido, o produto usará uma URL padrão apontando para uma página genérica explicando a ação tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="e84e6-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="e84e6-146">Permitir ou bloquear dispositivos removíveis</span><span class="sxs-lookup"><span data-stu-id="e84e6-146">Allow or block removable devices</span></span>

<span data-ttu-id="e84e6-147">A seção mídia removível da política de controle de dispositivo é usada para restringir o acesso à mídia removível.</span><span class="sxs-lookup"><span data-stu-id="e84e6-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="e84e6-148">Os seguintes tipos de mídia removível têm suporte no momento e podem ser incluídos na política: dispositivos de armazenamento USB.</span><span class="sxs-lookup"><span data-stu-id="e84e6-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="e84e6-149">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-149">Section</span></span>|<span data-ttu-id="e84e6-150">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-151">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-152">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-152">**Key**</span></span> | <span data-ttu-id="e84e6-153">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="e84e6-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="e84e6-154">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-154">**Data type**</span></span> | <span data-ttu-id="e84e6-155">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e84e6-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e84e6-156">**Comments**</span><span class="sxs-lookup"><span data-stu-id="e84e6-156">**Comments**</span></span> | <span data-ttu-id="e84e6-157">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e84e6-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="e84e6-158">Esta seção da política é hierárquica, permitindo a máxima flexibilidade e abrangendo uma ampla variedade de casos de uso.</span><span class="sxs-lookup"><span data-stu-id="e84e6-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="e84e6-159">No nível superior estão fornecedores, identificados por uma ID de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e84e6-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="e84e6-160">Para cada fornecedor, há produtos, identificados por uma ID do produto.</span><span class="sxs-lookup"><span data-stu-id="e84e6-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="e84e6-161">Por fim, para cada produto, há números de série que denotam dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="e84e6-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="e84e6-162">Para obter informações sobre como encontrar os identificadores de dispositivo, consulte [Procurar identificadores de dispositivo](#look-up-device-identifiers).</span><span class="sxs-lookup"><span data-stu-id="e84e6-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="e84e6-163">A política é avaliada da entrada mais específica para a mais geral.</span><span class="sxs-lookup"><span data-stu-id="e84e6-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="e84e6-164">Ou seja, quando um dispositivo está conectado, o produto tenta encontrar a combinação mais específica na política para cada dispositivo de mídia removível e aplicar as permissões nesse nível.</span><span class="sxs-lookup"><span data-stu-id="e84e6-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="e84e6-165">Se não houver nenhuma combinação, a próxima melhor combinação será aplicada, até a permissão especificada no nível superior, que é o padrão quando um dispositivo não corresponder a qualquer outra entrada na política.</span><span class="sxs-lookup"><span data-stu-id="e84e6-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="e84e6-166">Nível de imposição de política</span><span class="sxs-lookup"><span data-stu-id="e84e6-166">Policy enforcement level</span></span>

<span data-ttu-id="e84e6-167">Na seção mídia removível, há uma opção para definir o nível de imposição, que pode levar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e84e6-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="e84e6-168">`audit` - Nesse nível de imposição, se o acesso a um dispositivo for restrito, uma notificação será exibida para o usuário, no entanto, o dispositivo ainda poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="e84e6-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="e84e6-169">Esse nível de imposição pode ser útil para avaliar a eficácia de uma política.</span><span class="sxs-lookup"><span data-stu-id="e84e6-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="e84e6-170">`block` - Nesse nível de imposição, as operações que o usuário pode executar no dispositivo são limitadas ao que é definido na política.</span><span class="sxs-lookup"><span data-stu-id="e84e6-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="e84e6-171">Além disso, uma notificação é criada para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e84e6-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e84e6-172">Por padrão, o nível de imposição é definido como `audit` .</span><span class="sxs-lookup"><span data-stu-id="e84e6-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="e84e6-173">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-173">Section</span></span>|<span data-ttu-id="e84e6-174">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-175">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-176">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-176">**Key**</span></span> | <span data-ttu-id="e84e6-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="e84e6-177">enforcementLevel</span></span> |
| <span data-ttu-id="e84e6-178">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-178">**Data type**</span></span> | <span data-ttu-id="e84e6-179">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e84e6-179">String</span></span> |
| <span data-ttu-id="e84e6-180">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e84e6-180">**Possible values**</span></span> | <span data-ttu-id="e84e6-181">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="e84e6-181">audit (default)</span></span> <br/> <span data-ttu-id="e84e6-182">block</span><span class="sxs-lookup"><span data-stu-id="e84e6-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="e84e6-183">Nível de permissão padrão</span><span class="sxs-lookup"><span data-stu-id="e84e6-183">Default permission level</span></span>

<span data-ttu-id="e84e6-184">No nível superior da seção mídia removível, você pode configurar o nível de permissão padrão para dispositivos que não corresponderem a mais nada na política.</span><span class="sxs-lookup"><span data-stu-id="e84e6-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="e84e6-185">Essa configuração pode ser definida como:</span><span class="sxs-lookup"><span data-stu-id="e84e6-185">This setting can be set to:</span></span>

- <span data-ttu-id="e84e6-186">`none` - Nenhuma operação pode ser executada no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="e84e6-187">Uma combinação dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e84e6-187">A combination of the following values:</span></span>
    - <span data-ttu-id="e84e6-188">`read` - As operações de leitura são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="e84e6-189">`write` - As operações de gravação são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="e84e6-190">`execute` - Operações de execução são permitidas no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="e84e6-191">Se estiver presente no nível de permissão, quaisquer outras permissões `none` ( , ou ) serão `read` `write` `execute` ignoradas.</span><span class="sxs-lookup"><span data-stu-id="e84e6-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="e84e6-192">A `execute` permissão refere-se apenas à execução de binários Mach-O.</span><span class="sxs-lookup"><span data-stu-id="e84e6-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="e84e6-193">Ele não inclui a execução de scripts ou outros tipos de cargas.</span><span class="sxs-lookup"><span data-stu-id="e84e6-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="e84e6-194">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-194">Section</span></span>|<span data-ttu-id="e84e6-195">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-196">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-197">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-197">**Key**</span></span> | <span data-ttu-id="e84e6-198">permission</span><span class="sxs-lookup"><span data-stu-id="e84e6-198">permission</span></span> |
| <span data-ttu-id="e84e6-199">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-199">**Data type**</span></span> | <span data-ttu-id="e84e6-200">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e84e6-200">Array of strings</span></span> |
| <span data-ttu-id="e84e6-201">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e84e6-201">**Possible values**</span></span> | <span data-ttu-id="e84e6-202">nenhuma</span><span class="sxs-lookup"><span data-stu-id="e84e6-202">none</span></span> <br/> <span data-ttu-id="e84e6-203">leitura</span><span class="sxs-lookup"><span data-stu-id="e84e6-203">read</span></span> <br/> <span data-ttu-id="e84e6-204">gravação</span><span class="sxs-lookup"><span data-stu-id="e84e6-204">write</span></span> <br/> <span data-ttu-id="e84e6-205">execute</span><span class="sxs-lookup"><span data-stu-id="e84e6-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="e84e6-206">Restringir mídia removível por fornecedor, produto e número de série</span><span class="sxs-lookup"><span data-stu-id="e84e6-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="e84e6-207">Conforme descrito em [Permitir](#allow-or-block-removable-devices)ou bloquear dispositivos removíveis, mídia removível, como dispositivos USB, pode ser identificada pela ID do fornecedor, ID do produto e número de série.</span><span class="sxs-lookup"><span data-stu-id="e84e6-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="e84e6-208">No nível superior da política de mídia removível, você pode, opcionalmente, definir restrições mais granulares no nível do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e84e6-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="e84e6-209">O `vendors` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pela ID do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e84e6-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="e84e6-210">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-210">Section</span></span>|<span data-ttu-id="e84e6-211">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-212">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-213">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-213">**Key**</span></span> | <span data-ttu-id="e84e6-214">vendors</span><span class="sxs-lookup"><span data-stu-id="e84e6-214">vendors</span></span> |
| <span data-ttu-id="e84e6-215">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-215">**Data type**</span></span> | <span data-ttu-id="e84e6-216">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e84e6-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e84e6-217">Para cada fornecedor, você pode especificar o nível de permissão desejado para dispositivos desse fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e84e6-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="e84e6-218">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-218">Section</span></span>|<span data-ttu-id="e84e6-219">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-220">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-221">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-221">**Key**</span></span> | <span data-ttu-id="e84e6-222">permission</span><span class="sxs-lookup"><span data-stu-id="e84e6-222">permission</span></span> |
| <span data-ttu-id="e84e6-223">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-223">**Data type**</span></span> | <span data-ttu-id="e84e6-224">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e84e6-224">Array of strings</span></span> |
| <span data-ttu-id="e84e6-225">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e84e6-225">**Possible values**</span></span> | <span data-ttu-id="e84e6-226">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e84e6-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="e84e6-227">Além disso, opcionalmente, você pode especificar o conjunto de produtos pertencentes a esse fornecedor para o qual as permissões mais granulares são definidas.</span><span class="sxs-lookup"><span data-stu-id="e84e6-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="e84e6-228">O `products` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pela ID do produto.</span><span class="sxs-lookup"><span data-stu-id="e84e6-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="e84e6-229">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-229">Section</span></span>|<span data-ttu-id="e84e6-230">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-231">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-232">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-232">**Key**</span></span> | <span data-ttu-id="e84e6-233">products</span><span class="sxs-lookup"><span data-stu-id="e84e6-233">products</span></span> |
| <span data-ttu-id="e84e6-234">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-234">**Data type**</span></span> | <span data-ttu-id="e84e6-235">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e84e6-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e84e6-236">Para cada produto, você pode especificar o nível de permissão desejado para esse produto.</span><span class="sxs-lookup"><span data-stu-id="e84e6-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="e84e6-237">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-237">Section</span></span>|<span data-ttu-id="e84e6-238">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-239">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-240">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-240">**Key**</span></span> | <span data-ttu-id="e84e6-241">permission</span><span class="sxs-lookup"><span data-stu-id="e84e6-241">permission</span></span> |
| <span data-ttu-id="e84e6-242">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-242">**Data type**</span></span> | <span data-ttu-id="e84e6-243">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e84e6-243">Array of strings</span></span> |
| <span data-ttu-id="e84e6-244">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e84e6-244">**Possible values**</span></span> | <span data-ttu-id="e84e6-245">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e84e6-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="e84e6-246">Além disso, você pode especificar um conjunto opcional de números de série para os quais as permissões mais granulares são definidas.</span><span class="sxs-lookup"><span data-stu-id="e84e6-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="e84e6-247">O `serialNumbers` dicionário contém uma ou mais entradas, com cada entrada sendo identificada pelo número de série.</span><span class="sxs-lookup"><span data-stu-id="e84e6-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="e84e6-248">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-248">Section</span></span>|<span data-ttu-id="e84e6-249">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-250">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-251">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-251">**Key**</span></span> | <span data-ttu-id="e84e6-252">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="e84e6-252">serialNumbers</span></span> |
| <span data-ttu-id="e84e6-253">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-253">**Data type**</span></span> | <span data-ttu-id="e84e6-254">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e84e6-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="e84e6-255">Para cada número de série, você pode especificar o nível de permissão desejado.</span><span class="sxs-lookup"><span data-stu-id="e84e6-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="e84e6-256">Section</span><span class="sxs-lookup"><span data-stu-id="e84e6-256">Section</span></span>|<span data-ttu-id="e84e6-257">Valor</span><span class="sxs-lookup"><span data-stu-id="e84e6-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="e84e6-258">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e84e6-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="e84e6-259">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e84e6-259">**Key**</span></span> | <span data-ttu-id="e84e6-260">permission</span><span class="sxs-lookup"><span data-stu-id="e84e6-260">permission</span></span> |
| <span data-ttu-id="e84e6-261">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e84e6-261">**Data type**</span></span> | <span data-ttu-id="e84e6-262">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e84e6-262">Array of strings</span></span> |
| <span data-ttu-id="e84e6-263">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e84e6-263">**Possible values**</span></span> | <span data-ttu-id="e84e6-264">Mesmo nível [de permissão padrão](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="e84e6-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="e84e6-265">Política de controle de dispositivo de exemplo</span><span class="sxs-lookup"><span data-stu-id="e84e6-265">Example device control policy</span></span>

<span data-ttu-id="e84e6-266">O exemplo a seguir mostra como todos os conceitos acima podem ser combinados em uma política de controle de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e84e6-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="e84e6-267">No exemplo a seguir, observe a natureza hierárquica da política de mídia removível.</span><span class="sxs-lookup"><span data-stu-id="e84e6-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="e84e6-268">Incluímos mais exemplos de políticas de controle de dispositivo nos seguintes documentos:</span><span class="sxs-lookup"><span data-stu-id="e84e6-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="e84e6-269">Exemplos de políticas de controle de dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="e84e6-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="e84e6-270">Exemplos de políticas de controle de dispositivo para JAMF</span><span class="sxs-lookup"><span data-stu-id="e84e6-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="e84e6-271">Procurar identificadores de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-271">Look up device identifiers</span></span>

<span data-ttu-id="e84e6-272">Para encontrar a ID do fornecedor, a ID do produto e o número de série de um dispositivo USB:</span><span class="sxs-lookup"><span data-stu-id="e84e6-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="e84e6-273">Faça logoff em um dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="e84e6-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="e84e6-274">Conecte o dispositivo USB para o qual você deseja procurar os identificadores.</span><span class="sxs-lookup"><span data-stu-id="e84e6-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="e84e6-275">No menu de nível superior do macOS, selecione **Sobre Este Mac**.</span><span class="sxs-lookup"><span data-stu-id="e84e6-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Sobre esse Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="e84e6-277">Selecione **Relatório do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="e84e6-277">Select **System Report**.</span></span>

    ![Relatório do Sistema](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="e84e6-279">Na coluna esquerda, selecione **USB**.</span><span class="sxs-lookup"><span data-stu-id="e84e6-279">From the left column, select **USB**.</span></span>

    ![Modo de exibição de todos os dispositivos USB](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="e84e6-281">Em **Árvore de Dispositivo USB,** navegue até o dispositivo USB conectado.</span><span class="sxs-lookup"><span data-stu-id="e84e6-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Detalhes de um dispositivo USB](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="e84e6-283">A ID do fornecedor, a ID do produto e o número de série são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e84e6-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="e84e6-284">Ao adicionar a ID do fornecedor e a ID do produto à política de mídia removível, você só deve adicionar a parte depois `0x` de .</span><span class="sxs-lookup"><span data-stu-id="e84e6-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="e84e6-285">Por exemplo, na imagem abaixo, a ID do fornecedor é `1000` e a ID do produto é `090c` .</span><span class="sxs-lookup"><span data-stu-id="e84e6-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="e84e6-286">Descobrir dispositivos USB em sua organização</span><span class="sxs-lookup"><span data-stu-id="e84e6-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="e84e6-287">Você pode exibir eventos de montagem, desmontagem e alteração de volume provenientes de dispositivos USB no Microsoft Defender para a busca avançada do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e84e6-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="e84e6-288">Esses eventos podem ser úteis para identificar atividades de uso suspeitas ou realizar investigações internas.</span><span class="sxs-lookup"><span data-stu-id="e84e6-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="e84e6-289">Implantação da política de controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e84e6-289">Device control policy deployment</span></span>

<span data-ttu-id="e84e6-290">A política de controle de dispositivo deve ser incluída ao lado das outras configurações do produto, conforme descrito em Definir preferências do Microsoft Defender para Ponto de Extremidade [no macOS](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="e84e6-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="e84e6-291">Esse perfil pode ser implantado usando as instruções listadas na [implantação do perfil de configuração.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="e84e6-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="e84e6-292">Dicas de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="e84e6-292">Troubleshooting tips</span></span>

<span data-ttu-id="e84e6-293">Depois de empurrar o perfil de configuração através do Intune ou JAMF, você pode verificar se ele foi escolhido com êxito pelo produto executando o seguinte comando no Terminal:</span><span class="sxs-lookup"><span data-stu-id="e84e6-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="e84e6-294">Este comando imprimirá para saída padrão a política de controle de dispositivo que o produto está usando.</span><span class="sxs-lookup"><span data-stu-id="e84e6-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="e84e6-295">Caso isso imprime , certifique-se de que (a) o perfil de configuração tenha sido realmente enviado para o seu dispositivo do console de gerenciamento e (b) ela seja uma política de controle de dispositivo válida, conforme descrito `Policy is empty` neste documento.</span><span class="sxs-lookup"><span data-stu-id="e84e6-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="e84e6-296">Em um dispositivo onde a política foi entregue com êxito e onde há um ou mais dispositivos conectados, você pode executar o comando a seguir para listar todos os dispositivos e as permissões efetivas aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="e84e6-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="e84e6-297">Exemplo de saída:</span><span class="sxs-lookup"><span data-stu-id="e84e6-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="e84e6-298">No exemplo acima, há apenas um dispositivo de mídia removível conectado e ele tem e permissões, de acordo com a política de controle de dispositivo que foi entregue `read` `execute` ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e84e6-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e84e6-299">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e84e6-299">Related topics</span></span>

- [<span data-ttu-id="e84e6-300">Exemplos de políticas de controle de dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="e84e6-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="e84e6-301">Exemplos de políticas de controle de dispositivo para JAMF</span><span class="sxs-lookup"><span data-stu-id="e84e6-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
