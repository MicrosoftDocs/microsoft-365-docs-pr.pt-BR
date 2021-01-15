---
title: Começar a usar o treinamento de simulação de ataque
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o treinamento de simulação de ataque para executar ataques simulados de phishing e senha em suas organizações do Microsoft 365 E5 ou Microsoft Defender for Office 365 Plano 2.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871236"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="59f91-103">Começar a usar o treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="59f91-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="59f91-104">Se sua organização tiver o Microsoft 365 E5 ou o Microsoft Defender for Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o treinamento de simulação de ataque na Central de Segurança da Microsoft para executar cenários de ataque realistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="59f91-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="59f91-105">Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real a impacte seu resultado final.</span><span class="sxs-lookup"><span data-stu-id="59f91-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="59f91-106">Leia este artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="59f91-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="59f91-107">O treinamento de simulação de ataque substitui a experiência antiga do Simulador de Ataque v1 descrita no Simulador de Ataques no [Microsoft Defender para Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="59f91-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="59f91-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="59f91-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="59f91-109">Para abrir a Central de Segurança da Microsoft, vá para <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="59f91-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="59f91-110">O treinamento de simulação de ataque está disponível no **treinamento de simulação** de ataque e email \> **de colaboração.**</span><span class="sxs-lookup"><span data-stu-id="59f91-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="59f91-111">Para ir diretamente para o treinamento de simulação de ataque, abra <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="59f91-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="59f91-112">Para obter mais informações sobre a disponibilidade do treinamento de simulação de ataques em diferentes assinaturas do Microsoft 365, consulte a descrição do serviço do [Microsoft Defender for Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="59f91-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="59f91-113">Você precisa ter permissões no Centro de Conformidade e Segurança & ou no Azure Active Directory antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="59f91-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="59f91-114">Especificamente, você precisa ser membro do **Gerenciamento** da **Organização,** Administrador de Segurança ou uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="59f91-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="59f91-115">**Administradores do Simulador de** Ataque: criar e gerencia todos os aspectos de campanhas de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="59f91-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="59f91-116">**Autores de Carga do Simulador de Ataque:** Criar cargas de ataque que um administrador pode iniciar mais tarde.</span><span class="sxs-lookup"><span data-stu-id="59f91-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="59f91-117">Para obter mais informações, [consulte Permissões no Centro de Conformidade](permissions-in-the-security-and-compliance-center.md) & segurança ou sobre funções de [administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="59f91-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="59f91-118">Não há cmdlets do PowerShell correspondentes para treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="59f91-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="59f91-119">Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59f91-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="59f91-120">Para saber mais, confira [locais de dados do Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="59f91-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="59f91-121">No momento, a simulação de ataque não está disponível nas seguintes regiões: SGP, NOR, EMIRADOS, ZAF, GER, REIN e CHE.</span><span class="sxs-lookup"><span data-stu-id="59f91-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="59f91-122">Simulações</span><span class="sxs-lookup"><span data-stu-id="59f91-122">Simulations</span></span>

<span data-ttu-id="59f91-123">*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="59f91-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="59f91-124">*Phishing* é uma parte de um subconjunto de técnicas que classificamos como _engenharia social._</span><span class="sxs-lookup"><span data-stu-id="59f91-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="59f91-125">No treinamento de simulação de ataques, vários tipos de técnicas de engenharia social estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="59f91-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="59f91-126">**Coleta de credenciais:** um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="59f91-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="59f91-127">Quando o destinatário clica na URL, ele é levado a um site que normalmente mostra uma caixa de diálogo que solicita ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="59f91-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="59f91-128">Normalmente, a página de destino tem como temas um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="59f91-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="59f91-129">**Anexo de** malware: um invasor envia ao destinatário uma mensagem que contém um anexo.</span><span class="sxs-lookup"><span data-stu-id="59f91-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="59f91-130">Quando o destinatário abre o anexo, o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a entrar mais.</span><span class="sxs-lookup"><span data-stu-id="59f91-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="59f91-131">**Link em anexo:** este é um híbrido de uma coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="59f91-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="59f91-132">Um invasor envia ao destinatário uma mensagem que contém uma URL dentro de um anexo.</span><span class="sxs-lookup"><span data-stu-id="59f91-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="59f91-133">Quando o destinatário abre o anexo e clica na URL, ele é levado a um site que normalmente mostra uma caixa de diálogo que solicita ao usuário seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="59f91-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="59f91-134">Normalmente, a página de destino tem como temas um site conhecido para criar confiança no usuário.</span><span class="sxs-lookup"><span data-stu-id="59f91-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="59f91-135">**Link para malware:** um invasor envia ao destinatário uma mensagem que contém um link para um anexo em um site de compartilhamento de arquivos conhecido (por exemplo, SharePoint Online ou Dropbox).</span><span class="sxs-lookup"><span data-stu-id="59f91-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="59f91-136">Quando o destinatário clica na URL, o anexo é aberto e o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a própria entrada.</span><span class="sxs-lookup"><span data-stu-id="59f91-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="59f91-137">**Drive-by-url:** um invasor envia ao destinatário uma mensagem que contém uma URL.</span><span class="sxs-lookup"><span data-stu-id="59f91-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="59f91-138">Quando o destinatário clica na URL, ele é levado para um site que tenta executar código em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="59f91-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="59f91-139">Esse código em segundo plano tenta coletar informações sobre o destinatário ou implantar código arbitrário em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59f91-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="59f91-140">Normalmente, o site de destino é um site conhecido que foi comprometido ou um clone de um site conhecido.</span><span class="sxs-lookup"><span data-stu-id="59f91-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="59f91-141">A familiaridade com o site ajuda a convencer o usuário de que o link é seguro clicar.</span><span class="sxs-lookup"><span data-stu-id="59f91-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="59f91-142">Essa técnica também é conhecida como um ataque _de buraco de água._</span><span class="sxs-lookup"><span data-stu-id="59f91-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="59f91-143">Verifique a disponibilidade da URL de phishing simulada em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing.</span><span class="sxs-lookup"><span data-stu-id="59f91-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="59f91-144">Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir essas URLs de simulação, nem sempre temos cobertura total (por exemplo, Navegação Segura do Google).</span><span class="sxs-lookup"><span data-stu-id="59f91-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="59f91-145">A maioria dos fornecedores fornece orientações que permitem sempre permitir URLs específicas (por exemplo, <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="59f91-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="59f91-146">As URLs usadas pelo treinamento de simulação de ataque são descritas na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="59f91-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="59f91-147">Criar uma simulação</span><span class="sxs-lookup"><span data-stu-id="59f91-147">Create a simulation</span></span>

<span data-ttu-id="59f91-148">Para obter instruções passo a passo sobre como criar e enviar uma nova simulação, consulte [Simular um ataque de phishing.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="59f91-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="59f91-149">Criar uma carga</span><span class="sxs-lookup"><span data-stu-id="59f91-149">Create a payload</span></span>

<span data-ttu-id="59f91-150">Para obter instruções passo a passo sobre como criar uma carga para uso em uma simulação, consulte Criar uma carga personalizada para treinamento de [simulação de ataque.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="59f91-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="59f91-151">Obter informações</span><span class="sxs-lookup"><span data-stu-id="59f91-151">Gaining insights</span></span>

<span data-ttu-id="59f91-152">Para obter instruções passo a passo sobre como obter informações com relatórios, consulte Obter informações por meio [do treinamento de simulação de ataque.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="59f91-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
