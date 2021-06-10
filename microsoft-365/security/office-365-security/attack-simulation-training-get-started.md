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
ms.openlocfilehash: c5d4b77204f207c31f2014df797f6209b92c9ccb
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822329"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="75c37-103">Começar a usar o Treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="75c37-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="75c37-104">Se sua organização tiver um Microsoft 365 E5 ou o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você pode usar o treinamento de simulação de ataque no Centro de Segurança da Microsoft para executar cenários de ataque realistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="75c37-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="75c37-105">Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real impacte sua linha inferior.</span><span class="sxs-lookup"><span data-stu-id="75c37-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="75c37-106">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="75c37-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="75c37-107">O treinamento de simulação de ataque substitui a experiência antiga do Simulador de Ataque v1 descrita no [Simulador](attack-simulator.md)de Ataques no Microsoft Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="75c37-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75c37-108">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="75c37-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="75c37-109">Para abrir o Centro de Segurança da Microsoft, vá para <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="75c37-109">To open the Microsoft Security Center, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="75c37-110">Treinamento de simulação de ataque está disponível em Treinamento de **simulação** de ataque e email \> **e colaboração.**</span><span class="sxs-lookup"><span data-stu-id="75c37-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="75c37-111">Para ir diretamente ao treinamento de simulação de ataque, abra <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="75c37-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="75c37-112">Para obter mais informações sobre a disponibilidade do treinamento de simulação de ataque em assinaturas Microsoft 365 diferentes, consulte [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="75c37-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="75c37-113">Você precisa ter permissões atribuídas no Centro de Conformidade & Segurança ou Azure Active Directory antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="75c37-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="75c37-114">Especificamente, você precisa ser membro do **Gerenciamento** da **Organização,** Administrador de Segurança ou uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="75c37-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="75c37-115">**Administradores do Simulador de Ataques**: Crie e gere todos os aspectos de campanhas de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="75c37-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="75c37-116">**Autores de Carga do Simulador de Ataque**: Crie cargas de ataque que um administrador pode iniciar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="75c37-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="75c37-117">Para obter mais informações, consulte [Permissões no Centro](permissions-in-the-security-and-compliance-center.md) de Conformidade & Segurança ou Sobre funções de [administrador.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="75c37-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="75c37-118">Não há cmdlets correspondentes do PowerShell para treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="75c37-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="75c37-119">Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="75c37-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="75c37-120">Para obter mais informações, [consulte Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="75c37-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="75c37-121">A simulação de ataque está disponível nas seguintes regiões: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN e KOR.</span><span class="sxs-lookup"><span data-stu-id="75c37-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="75c37-122">A partir de 15 de junho de 2021, o treinamento de simulação de ataque está disponível GCC.</span><span class="sxs-lookup"><span data-stu-id="75c37-122">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="75c37-123">Se sua organização tiver Office 365 G5 GCC ou Microsoft Defender para Office 365 (Plano 2) para Governo, você poderá usar o treinamento de simulação de ataque no Centro de Segurança da Microsoft para executar cenários de ataque realistas em sua organização, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="75c37-123">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="75c37-124">O treinamento de simulação de ataque ainda não está disponível GCC ambientes High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="75c37-124">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="75c37-125">O treinamento de simulação de ataque oferece um subconjunto de recursos para clientes do E3 como uma avaliação.</span><span class="sxs-lookup"><span data-stu-id="75c37-125">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="75c37-126">A oferta de avaliação contém a capacidade de usar uma carga de Coleta de Credenciais e a capacidade de selecionar experiências de treinamento 'ISA Phishing' ou 'Mass Market Phishing'.</span><span class="sxs-lookup"><span data-stu-id="75c37-126">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="75c37-127">Nenhum outro recursos faz parte da oferta de avaliação do E3.</span><span class="sxs-lookup"><span data-stu-id="75c37-127">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="75c37-128">Simulações</span><span class="sxs-lookup"><span data-stu-id="75c37-128">Simulations</span></span>

<span data-ttu-id="75c37-129">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="75c37-129">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="75c37-130">*Phishing* faz parte de um subconjunto de técnicas que classificamos como _engenharia social._</span><span class="sxs-lookup"><span data-stu-id="75c37-130">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="75c37-131">No treinamento de simulação de ataque, vários tipos de técnicas de engenharia social estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="75c37-131">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="75c37-132">**Coleta de credenciais**: um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="75c37-132">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="75c37-133">Quando o destinatário clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="75c37-133">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="75c37-134">Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="75c37-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="75c37-135">**Anexo de malware**: um invasor envia ao destinatário uma mensagem que contém um anexo.</span><span class="sxs-lookup"><span data-stu-id="75c37-135">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="75c37-136">Quando o destinatário abre o anexo, o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="75c37-136">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="75c37-137">**Link in attachment**: Este é um híbrido de uma coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="75c37-137">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="75c37-138">Um invasor envia ao destinatário uma mensagem que contém uma URL dentro de um anexo.</span><span class="sxs-lookup"><span data-stu-id="75c37-138">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="75c37-139">Quando o destinatário abre o anexo e clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="75c37-139">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="75c37-140">Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="75c37-140">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="75c37-141">**Link para malware**: um invasor envia ao destinatário uma mensagem que contém um link para um anexo em um site de compartilhamento de arquivos conhecido (por exemplo, SharePoint Online ou Dropbox).</span><span class="sxs-lookup"><span data-stu-id="75c37-141">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="75c37-142">Quando o destinatário clica na URL, o anexo é aberto e o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="75c37-142">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="75c37-143">**Drive-by-url**: um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="75c37-143">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="75c37-144">Quando o destinatário clica na URL, ele é levado para um site que tenta executar o código em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="75c37-144">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="75c37-145">Esse código em segundo plano tenta coletar informações sobre o destinatário ou implantar código arbitrário em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75c37-145">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="75c37-146">Normalmente, o site de destino é um site conhecido que foi comprometido ou um clone de um site conhecido.</span><span class="sxs-lookup"><span data-stu-id="75c37-146">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="75c37-147">A familiaridade com o site ajuda a convencer o usuário de que o link é seguro para clicar.</span><span class="sxs-lookup"><span data-stu-id="75c37-147">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="75c37-148">Essa técnica também é conhecida como um ataque de _buraco de regua._</span><span class="sxs-lookup"><span data-stu-id="75c37-148">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="75c37-149">Verifique a disponibilidade da URL de phishing simulada em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="75c37-149">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="75c37-150">Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir essas URLs de simulação, nem sempre temos cobertura completa (por exemplo, Google Cofre Navegação).</span><span class="sxs-lookup"><span data-stu-id="75c37-150">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="75c37-151">A maioria dos fornecedores fornece orientações que permitem que você sempre permita URLs específicas (por exemplo, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="75c37-151">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="75c37-152">As URLs usadas pelo treinamento de simulação de ataque são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="75c37-152">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="75c37-153">Criar uma simulação</span><span class="sxs-lookup"><span data-stu-id="75c37-153">Create a simulation</span></span>

<span data-ttu-id="75c37-154">Para obter instruções passo a passo sobre como criar e enviar uma nova simulação, consulte [Simular um ataque de phishing](attack-simulation-training.md).</span><span class="sxs-lookup"><span data-stu-id="75c37-154">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="75c37-155">Criar uma carga</span><span class="sxs-lookup"><span data-stu-id="75c37-155">Create a payload</span></span>

<span data-ttu-id="75c37-156">Para obter instruções passo a passo sobre como criar uma carga para uso em uma simulação, consulte [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="75c37-156">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="75c37-157">Obter informações</span><span class="sxs-lookup"><span data-stu-id="75c37-157">Gaining insights</span></span>

<span data-ttu-id="75c37-158">Para obter instruções passo a passo sobre como obter informações com relatórios, consulte Obter informações por meio [do treinamento de simulação de ataque.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="75c37-158">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="75c37-159">O Simulador de Ataques usa links do Cofre no Defender para Office 365 rastrear com segurança os dados de clique para a URL na mensagem de carga que é enviada a destinatários direcionados de uma campanha de phishing, mesmo que a configuração Não rastrear **cliques** do usuário em Cofre Políticas de Links está conexões.</span><span class="sxs-lookup"><span data-stu-id="75c37-159">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
