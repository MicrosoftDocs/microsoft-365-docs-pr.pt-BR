---
title: Integrar o Microsoft Defender para Ponto de Extremidade com outras soluções da Microsoft
description: Saiba como o Microsoft Defender for Endpoint se integra a outras soluções da Microsoft, incluindo o Microsoft Defender para Identidade e o Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, acesso condicional, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8973a78787345532055161507e2d30f75b3b2cf1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844965"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="d8e15-104">Microsoft Defender para Ponto de Extremidade e outras soluções da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8e15-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d8e15-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d8e15-105">**Applies to:**</span></span>
- [<span data-ttu-id="d8e15-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d8e15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d8e15-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8e15-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d8e15-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d8e15-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d8e15-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="d8e15-110">Integrar com outras soluções da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d8e15-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="d8e15-111">O Microsoft Defender para Ponto de Extremidade integra-se diretamente a várias soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8e15-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="d8e15-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-112">Azure Defender</span></span>
<span data-ttu-id="d8e15-113">O Microsoft Defender for Endpoint fornece uma solução abrangente de proteção do servidor, incluindo detecção e resposta de ponto de extremidade (EDR) em Windows Servidores.</span><span class="sxs-lookup"><span data-stu-id="d8e15-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="d8e15-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="d8e15-114">Azure Sentinel</span></span>
<span data-ttu-id="d8e15-115">O conector do Microsoft Defender para Ponto de Extremidade permite transmitir alertas do Microsoft Defender para Ponto de Extremidade no Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d8e15-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="d8e15-116">Isso permitirá que você analise de forma mais abrangente os eventos de segurança em toda a sua organização e crie playbooks para resposta efetiva e imediata.</span><span class="sxs-lookup"><span data-stu-id="d8e15-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="d8e15-117">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="d8e15-117">Azure Information Protection</span></span>
<span data-ttu-id="d8e15-118">Recentemente, preterimos a integração com a Proteção de Informações do Azure, pois nossos recursos de DLP do Ponto de Extremidade incorporam uma solução aprimorada de descoberta e proteção para dados confidenciais armazenados em dispositivos de ponto de extremidade que facilitam maior visibilidade e integração entre soluções.</span><span class="sxs-lookup"><span data-stu-id="d8e15-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="d8e15-119">Isso foi anunciado no [blog a seguir.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="d8e15-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="d8e15-120">Recomendamos que os clientes mudem para o uso de DLP do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d8e15-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="d8e15-121">Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="d8e15-121">Conditional Access</span></span>
<span data-ttu-id="d8e15-122">A pontuação de risco de dispositivo dinâmico do Microsoft Defender para Endpoint é integrada à avaliação do Acesso Condicional, garantindo que somente dispositivos seguros tenham acesso aos recursos.</span><span class="sxs-lookup"><span data-stu-id="d8e15-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="d8e15-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d8e15-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="d8e15-124">Microsoft Cloud App Security aproveita os sinais de ponto de extremidade do Microsoft Defender para Ponto de Extremidade para permitir visibilidade direta do uso de aplicativos na nuvem, incluindo o uso de serviços de nuvem sem suporte (SHADOW IT) de todos os dispositivos monitorados do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="d8e15-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="d8e15-125">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="d8e15-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="d8e15-126">Atividades suspeitas são processos em execução em um contexto de usuário.</span><span class="sxs-lookup"><span data-stu-id="d8e15-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="d8e15-127">A integração entre o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Identidade fornece a flexibilidade de conduzir a investigação de segurança cibernética entre atividades e identidades.</span><span class="sxs-lookup"><span data-stu-id="d8e15-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="d8e15-128">Microsoft Defender para Office</span><span class="sxs-lookup"><span data-stu-id="d8e15-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="d8e15-129">[O Defender para Office 365](/office365/securitycompliance/office-365-atp) ajuda a proteger sua organização contra malware em mensagens de email ou arquivos por meio de links Cofre, anexos Cofre, recursos avançados de inteligência anti-phishing e spoof.</span><span class="sxs-lookup"><span data-stu-id="d8e15-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="d8e15-130">A integração entre o Microsoft Defender para Office 365 e o Microsoft Defender para Ponto de Extremidade permite que os analistas de segurança acessem o upstream para investigar o ponto de entrada de um ataque.</span><span class="sxs-lookup"><span data-stu-id="d8e15-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="d8e15-131">Por meio do compartilhamento de inteligência de ameaças, os ataques podem ser contidos e bloqueados.</span><span class="sxs-lookup"><span data-stu-id="d8e15-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="d8e15-132">Os dados do Defender Office 365 são exibidos para eventos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d8e15-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="d8e15-133">Para alertas, o Defender para Office 365 dados é exibido com base na primeira hora de atividade.</span><span class="sxs-lookup"><span data-stu-id="d8e15-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="d8e15-134">Depois disso, os dados não estarão mais disponíveis no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="d8e15-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="d8e15-135">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d8e15-135">Skype for Business</span></span>
<span data-ttu-id="d8e15-136">A Skype for Business oferece uma maneira para os analistas se comunicarem com um usuário ou proprietário de dispositivo potencialmente comprometido por meio de um botão simples do portal.</span><span class="sxs-lookup"><span data-stu-id="d8e15-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="d8e15-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="d8e15-138">Com o Microsoft 365 Defender, o Microsoft Defender para Ponto de Extremidade e várias soluções de segurança da Microsoft formam um pacote unificado de defesa empresarial de pré e pós-violação que se integra de forma nativa no ponto de extremidade, identidade, email e aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="d8e15-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="d8e15-139">Saiba mais sobre o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="d8e15-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8e15-140">Related topics</span></span>
- [<span data-ttu-id="d8e15-141">Configurar a integração e outros recursos avançados</span><span class="sxs-lookup"><span data-stu-id="d8e15-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="d8e15-142">Microsoft 365 Visão geral do Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="d8e15-143">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8e15-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="d8e15-144">Proteger usuários, dados e dispositivos com Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="d8e15-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
