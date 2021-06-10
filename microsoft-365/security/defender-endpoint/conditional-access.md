---
title: Habilitar o Acesso Condicional para proteger melhor usuários, dispositivos e dados
description: Habilita o Acesso Condicional para impedir que aplicativos sejam executados se um dispositivo for considerado em risco e um aplicativo for determinado como não compatível.
keywords: acesso condicional, bloquear aplicativos, nível de segurança, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166192"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="8f8b5-104">Habilitar o Acesso Condicional para proteger melhor usuários, dispositivos e dados</span><span class="sxs-lookup"><span data-stu-id="8f8b5-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f8b5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8f8b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f8b5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8f8b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f8b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f8b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8f8b5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8f8b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f8b5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="8f8b5-110">O Acesso Condicional é um recurso que ajuda você a proteger melhor seus usuários e informações corporativas, se certificar de que somente dispositivos seguros tenham acesso a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="8f8b5-111">Com o Acesso Condicional, você pode controlar o acesso às informações corporativas com base no nível de risco de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="8f8b5-112">Isso ajuda a manter usuários confiáveis em dispositivos confiáveis usando aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="8f8b5-113">Você pode definir condições de segurança em quais dispositivos e aplicativos podem executar e acessar informações de sua rede, impondo políticas para impedir a execução de aplicativos até que um dispositivo retorne a um estado compatível.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="8f8b5-114">A implementação do Acesso Condicional no Defender para Ponto de Extremidade baseia-se em políticas de conformidade de dispositivo Microsoft Intune (Intune) e políticas de acesso condicional Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8f8b5-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="8f8b5-115">A política de conformidade é usada com o Acesso Condicional para permitir que apenas dispositivos que cumprem uma ou mais regras de política de conformidade de dispositivo acessem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="8f8b5-116">Compreender o fluxo de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="8f8b5-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="8f8b5-117">O Acesso Condicional é colocado no local para que, quando uma ameaça seja vista em um dispositivo, o acesso a conteúdos confidenciais seja bloqueado até que a ameaça seja remediada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="8f8b5-118">O fluxo começa com dispositivos que estão sendo vistos com baixo, médio ou alto risco.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="8f8b5-119">Essas determinações de risco são enviadas para o Intune.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="8f8b5-120">Dependendo de como você configura políticas no Intune, o Acesso Condicional pode ser definido para que, quando determinadas condições são atendidas, a política seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="8f8b5-121">Por exemplo, você pode configurar o Intune para aplicar o Acesso Condicional em dispositivos com alto risco.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="8f8b5-122">No Intune, uma política de conformidade de dispositivo é usada em conjunto com o Acesso Condicional do Azure AD para bloquear o acesso a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="8f8b5-123">Em paralelo, um processo automatizado de investigação e correção é lançado.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="8f8b5-124">Um usuário ainda pode usar o dispositivo enquanto a investigação e a correção automatizadas estão ocorrendo, mas o acesso aos dados corporativos é bloqueado até que a ameaça seja totalmente remediada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="8f8b5-125">Para resolver o risco encontrado em um dispositivo, você precisará retornar o dispositivo para um estado compatível.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="8f8b5-126">Um dispositivo retorna para um estado compatível quando não há risco visto nele.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="8f8b5-127">Há três maneiras de resolver um risco:</span><span class="sxs-lookup"><span data-stu-id="8f8b5-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="8f8b5-128">Use correção manual ou automatizada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="8f8b5-129">Resolva alertas ativos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="8f8b5-130">Isso removerá o risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="8f8b5-131">Você pode remover o dispositivo das políticas ativas e, consequentemente, o Acesso Condicional não será aplicado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="8f8b5-132">A correção manual exige que um administrador do secops investigue um alerta e a fim de resolver o risco visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="8f8b5-133">A correção automatizada é configurada por meio das configurações fornecidas na seção a seguir, [Configure Conditional Access](configure-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f8b5-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="8f8b5-134">Quando o risco é removido por meio de correção manual ou automatizada, o dispositivo retorna para um estado compatível e o acesso a aplicativos é concedido.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="8f8b5-135">A seguinte sequência de exemplo de eventos explica o Acesso Condicional em ação:</span><span class="sxs-lookup"><span data-stu-id="8f8b5-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="8f8b5-136">Um usuário abre um arquivo mal-intencionado e o Defender para Ponto de Extremidade sinaliza o dispositivo como de alto risco.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="8f8b5-137">A avaliação de alto risco é passada para o Intune.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="8f8b5-138">Em paralelo, uma investigação automatizada é iniciada para correção da ameaça identificada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="8f8b5-139">Uma correção manual também pode ser feita para correção da ameaça identificada.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="8f8b5-140">Com base na política criada no Intune, o dispositivo é marcado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="8f8b5-141">Em seguida, a avaliação é comunicada ao Azure AD pela política de Acesso Condicional do Intune.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="8f8b5-142">No Azure AD, a política correspondente é aplicada para bloquear o acesso a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="8f8b5-143">A investigação e a correção manual ou automatizada são concluídas e a ameaça é removida.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="8f8b5-144">O Defender para Ponto de Extremidade vê que não há risco no dispositivo e o Intune avalia que o dispositivo está em estado de conformidade.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="8f8b5-145">O Azure AD aplica a política que permite o acesso a aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="8f8b5-146">Os usuários agora podem acessar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8f8b5-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="8f8b5-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8f8b5-147">Related topic</span></span>
- [<span data-ttu-id="8f8b5-148">Configurar o Acesso Condicional no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8f8b5-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
