---
title: Começar a usar o Treinamento de simulação de ataque
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o treinamento de simulação de ataque para executar ataques simulados de phishing e senha em suas Microsoft 365 E5 ou no Microsoft Defender para organizações Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 182d3d3c1d3b7c0c43caa8a809e993933707af00
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878779"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="0cbc7-103">Começar a usar o Treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="0cbc7-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0cbc7-104">**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="0cbc7-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="0cbc7-105">Se sua organização tiver um Microsoft 365 E5 ou o Microsoft Defender para o plano 2 do Office 365, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você pode usar o treinamento de simulação de ataque no portal do Microsoft 365 Defender para executar cenários de ataque realistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0cbc7-106">Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real impacte sua linha inferior.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0cbc7-107">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="0cbc7-108">O treinamento de simulação de ataque substitui a experiência antiga do Simulador de Ataque v1 descrita no [Simulador](attack-simulator.md)de Ataques no Microsoft Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="0cbc7-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0cbc7-109">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="0cbc7-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0cbc7-110">Para abrir o portal Microsoft 365 Defender, vá para <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="0cbc7-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="0cbc7-111">Treinamento de simulação de ataque está disponível em Treinamento de **simulação** de ataque e email \> **e colaboração.**</span><span class="sxs-lookup"><span data-stu-id="0cbc7-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="0cbc7-112">Para ir diretamente ao treinamento de simulação de ataque, abra <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="0cbc7-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="0cbc7-113">Para obter mais informações sobre a disponibilidade do treinamento de simulação de ataque em assinaturas Microsoft 365 diferentes, consulte [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="0cbc7-114">Você precisa ter permissões atribuídas no Centro de Conformidade & Segurança ou Azure Active Directory antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-114">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="0cbc7-115">Especificamente, você precisa ser membro do **Gerenciamento** da **Organização,** Administrador de Segurança ou uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="0cbc7-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="0cbc7-116">**Administradores do Simulador de Ataques**: Crie e gere todos os aspectos de campanhas de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="0cbc7-117">**Autores de Carga do Simulador de Ataque**: Crie cargas de ataque que um administrador pode iniciar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="0cbc7-118">Para obter mais informações, consulte [Permissões no Centro](permissions-in-the-security-and-compliance-center.md) de Conformidade & Segurança ou Sobre funções de [administrador.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0cbc7-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="0cbc7-119">Não há cmdlets correspondentes do PowerShell para treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="0cbc7-120">Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="0cbc7-121">Para obter mais informações, [consulte Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="0cbc7-122">A simulação de ataque está disponível nas seguintes regiões: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN e KOR.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="0cbc7-123">A partir de 15 de junho de 2021, o treinamento de simulação de ataque está disponível GCC.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="0cbc7-124">Se sua organização tiver Office 365 G5 GCC ou Microsoft Defender para Office 365 (Plano 2) para Governo, você poderá usar o treinamento de simulação de ataque no portal do Microsoft 365 Defender para executar cenários de ataque realistas em sua organização, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="0cbc7-125">O treinamento de simulação de ataque ainda não está disponível GCC ambientes High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="0cbc7-126">O treinamento de simulação de ataque oferece um subconjunto de recursos para clientes do E3 como uma avaliação.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="0cbc7-127">A oferta de avaliação contém a capacidade de usar uma carga de Coleta de Credenciais e a capacidade de selecionar experiências de treinamento 'ISA Phishing' ou 'Mass Market Phishing'.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="0cbc7-128">Nenhum outro recursos faz parte da oferta de avaliação do E3.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="0cbc7-129">Simulações</span><span class="sxs-lookup"><span data-stu-id="0cbc7-129">Simulations</span></span>

<span data-ttu-id="0cbc7-130">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0cbc7-131">*Phishing* faz parte de um subconjunto de técnicas que classificamos como _engenharia social._</span><span class="sxs-lookup"><span data-stu-id="0cbc7-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="0cbc7-132">No treinamento de simulação de ataque, vários tipos de técnicas de engenharia social estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0cbc7-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="0cbc7-133">**Coleta de credenciais**: um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="0cbc7-134">Quando o destinatário clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="0cbc7-135">Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="0cbc7-136">**Anexo de malware**: um invasor envia ao destinatário uma mensagem que contém um anexo.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="0cbc7-137">Quando o destinatário abre o anexo, o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="0cbc7-138">**Link in attachment**: Este é um híbrido de uma coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="0cbc7-139">Um invasor envia ao destinatário uma mensagem que contém uma URL dentro de um anexo.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="0cbc7-140">Quando o destinatário abre o anexo e clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="0cbc7-141">Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="0cbc7-142">**Link para malware**: um invasor envia ao destinatário uma mensagem que contém um link para um anexo em um site de compartilhamento de arquivos conhecido (por exemplo, SharePoint Online ou Dropbox).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="0cbc7-143">Quando o destinatário clica na URL, o anexo é aberto e o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="0cbc7-144">**Drive-by-url**: um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="0cbc7-145">Quando o destinatário clica na URL, ele é levado para um site que tenta executar o código em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="0cbc7-146">Esse código em segundo plano tenta coletar informações sobre o destinatário ou implantar código arbitrário em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="0cbc7-147">Normalmente, o site de destino é um site conhecido que foi comprometido ou um clone de um site conhecido.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="0cbc7-148">A familiaridade com o site ajuda a convencer o usuário de que o link é seguro para clicar.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="0cbc7-149">Essa técnica também é conhecida como um ataque de _buraco de regua._</span><span class="sxs-lookup"><span data-stu-id="0cbc7-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="0cbc7-150">Verifique a disponibilidade da URL de phishing simulada em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="0cbc7-151">Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir essas URLs de simulação, nem sempre temos cobertura completa (por exemplo, Google Cofre Navegação).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="0cbc7-152">A maioria dos fornecedores fornece orientações que permitem que você sempre permita URLs específicas (por exemplo, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="0cbc7-153">As URLs usadas pelo treinamento de simulação de ataque são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="0cbc7-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="0cbc7-154">Criar uma simulação</span><span class="sxs-lookup"><span data-stu-id="0cbc7-154">Create a simulation</span></span>

<span data-ttu-id="0cbc7-155">Para obter instruções passo a passo sobre como criar e enviar uma nova simulação, consulte [Simular um ataque de phishing](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="0cbc7-156">Criar uma carga</span><span class="sxs-lookup"><span data-stu-id="0cbc7-156">Create a payload</span></span>

<span data-ttu-id="0cbc7-157">Para obter instruções passo a passo sobre como criar uma carga para uso em uma simulação, consulte [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="0cbc7-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="0cbc7-158">Obter informações</span><span class="sxs-lookup"><span data-stu-id="0cbc7-158">Gaining insights</span></span>

<span data-ttu-id="0cbc7-159">Para obter instruções passo a passo sobre como obter informações com relatórios, consulte Obter informações por meio [do treinamento de simulação de ataque.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="0cbc7-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0cbc7-160">O Simulador de Ataques usa links do Cofre no Defender para Office 365 rastrear com segurança os dados de clique para a URL na mensagem de carga que é enviada a destinatários direcionados de uma campanha de phishing, mesmo que a configuração Não rastrear **cliques** do usuário em Cofre Políticas de Links está conexões.</span><span class="sxs-lookup"><span data-stu-id="0cbc7-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
