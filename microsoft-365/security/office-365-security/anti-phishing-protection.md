---
title: Proteção anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Os administradores podem aprender sobre os recursos de proteção anti-phishing no Exchange Online Protection (EOP) e no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a100e28ddee1629b2fe35e28742a43b891d13e57
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570607"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="0ace3-103">Proteção anti-phishing no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ace3-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ace3-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="0ace3-104">**Applies to**</span></span>
- [<span data-ttu-id="0ace3-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0ace3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ace3-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0ace3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ace3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ace3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ace3-108">*Phishing* é um ataque de email que tenta roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="0ace3-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0ace3-109">Há categorias específicas de phishing.</span><span class="sxs-lookup"><span data-stu-id="0ace3-109">There are specific categories of phishing.</span></span> <span data-ttu-id="0ace3-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0ace3-110">For example:</span></span>

- <span data-ttu-id="0ace3-111">**O phishing** de lança usa conteúdo focado e personalizado especificamente personalizado para os destinatários direcionados (normalmente, após o reconhecimento nos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="0ace3-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="0ace3-112">**A expiração é** direcionada a executivos ou outros destinos de alto valor dentro de uma organização para efeito máximo.</span><span class="sxs-lookup"><span data-stu-id="0ace3-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="0ace3-113">O **BEC (compromisso** de email comercial) usa senders confiáveis forjados (diretores financeiros, clientes, parceiros confiáveis, etc.) para enganar os destinatários para aprovar pagamentos, transferir fundos ou revelar dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="0ace3-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="0ace3-114">Saiba mais assistindo [a este vídeo](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span><span class="sxs-lookup"><span data-stu-id="0ace3-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="0ace3-115">**O ransomware** que criptografa seus dados e exige pagamento para descriptografá-los quase sempre começa em mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="0ace3-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="0ace3-116">A proteção anti-phishing não pode ajudá-lo a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens iniciais de phishing associadas à campanha de ransomware.</span><span class="sxs-lookup"><span data-stu-id="0ace3-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="0ace3-117">Para obter mais informações sobre a recuperação de um ataque de ransomware, consulte [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="0ace3-118">Com a crescente complexidade dos ataques, é até difícil para usuários treinados identificar mensagens de phishing sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="0ace3-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="0ace3-119">Felizmente, a Proteção do Exchange Online (EOP) e os recursos adicionais no Microsoft Defender para Office 365 podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="0ace3-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="0ace3-120">Proteção anti-phishing no EOP</span><span class="sxs-lookup"><span data-stu-id="0ace3-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="0ace3-121">O EOP (ou seja, organizações do Microsoft 365 sem o Microsoft Defender para Office 365) contém recursos que podem ajudar a proteger sua organização contra ameaças de phishing:</span><span class="sxs-lookup"><span data-stu-id="0ace3-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="0ace3-122">**Inteligência contra falsificação**: Revise as mensagens falsas dos remetentes em domínios internos e externos e permita ou bloqueie esses remetentes.</span><span class="sxs-lookup"><span data-stu-id="0ace3-122">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="0ace3-123">Para obter mais informações, [consulte Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-123">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="0ace3-124">**Políticas anti-phishing** no EOP : ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação do remetente não autenticado no Outlook e especificar a ação para remetentes espojados bloqueados (mover para a pasta Lixo Eletrônico ou quarentena).</span><span class="sxs-lookup"><span data-stu-id="0ace3-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="0ace3-125">Para obter mais informações, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="0ace3-126">**Autenticação** implícita de email : O EOP aprimora verificações padrão de autenticação de email para email de entrada ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação de remetente, histórico de remetentes, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes forjados.</span><span class="sxs-lookup"><span data-stu-id="0ace3-126">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="0ace3-127">Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-127">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0ace3-128">Proteção adicional contra phishing no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0ace3-128">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0ace3-129">O Microsoft Defender para Office 365 contém recursos anti-phishing adicionais e mais avançados:</span><span class="sxs-lookup"><span data-stu-id="0ace3-129">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="0ace3-130">**Políticas anti-phishing no Microsoft Defender para Office 365**: Crie novas políticas personalizadas, configure configurações anti-representação (proteja usuários e domínios contra representação), configurações de inteligência de caixa de correio e limites avançados de phishing ajustáveis.</span><span class="sxs-lookup"><span data-stu-id="0ace3-130">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="0ace3-131">Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-131">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="0ace3-132">Para obter mais informações sobre as diferenças entre políticas anti-phishing no EOP e políticas anti-phishing no Defender para Office 365, consulte [Políticas anti-phishing no Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-132">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="0ace3-133">**Exibições de** campanha : Aprendizado de máquina e outras heurísticas identificam e analisam mensagens envolvidas em ataques de phishing coordenados contra todo o serviço e sua organização.</span><span class="sxs-lookup"><span data-stu-id="0ace3-133">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="0ace3-134">Para obter mais informações, consulte [Exibições de campanha no Microsoft Defender para Office 365](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-134">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="0ace3-135">**Simulador de** ataque : os administradores podem criar mensagens de phishing falsas e enviá-las para usuários internos como uma ferramenta educacional.</span><span class="sxs-lookup"><span data-stu-id="0ace3-135">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="0ace3-136">Para obter mais informações, consulte [Simulador de Ataque no Microsoft Defender para Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-136">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="0ace3-137">Outros recursos anti-phishing</span><span class="sxs-lookup"><span data-stu-id="0ace3-137">Other anti-phishing resources</span></span>

- <span data-ttu-id="0ace3-138">Para usuários finais: [proteja-se contra esquemas de phishing e outras formas de fraude online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)</span><span class="sxs-lookup"><span data-stu-id="0ace3-138">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="0ace3-139">[Como o Microsoft 365 valida o endereço De para evitar phishing](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="0ace3-139">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
