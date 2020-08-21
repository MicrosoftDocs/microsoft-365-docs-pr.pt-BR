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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Os administradores podem aprender sobre os recursos de proteção contra phishing no Exchange Online Protection (EOP) e a proteção avançada contra ameaças do Office 365 (Office 365 ATP).
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827440"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="2d7d0-103">Proteção contra phishing no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d7d0-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="2d7d0-104">*Phishing* é um ataque de email que tenta roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2d7d0-105">Há categorias específicas de phishing.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-105">There are specific categories of phishing.</span></span> <span data-ttu-id="2d7d0-106">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2d7d0-106">For example:</span></span>

- <span data-ttu-id="2d7d0-107">O **spear phishing** usa conteúdo muito focalizado e personalizado que é especificamente ajustado para os destinatários de destino (normalmente, após o reconhecimento dos destinatários pelo invasor).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="2d7d0-108">O **Whaling** é direcionado para executivos ou outros destinos de alto valor dentro de uma organização para obter o máximo de efeito.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="2d7d0-109">O **Bec (email de negócios corporativos)** usa remetentes confiáveis falsificados (gerentes financeiros, clientes, parceiros confiáveis etc.) em um esforço para enganar o destinatário para aprovar pagamentos, transferir fundos ou divulgar dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="2d7d0-110">**Ransomware** que criptografa seus dados e exige que o pagamento seja descriptografado quase sempre inicia em mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="2d7d0-111">A proteção anti-phishing não pode ajudar você a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens de phishing iniciais que estão associadas à campanha de ransomware.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="2d7d0-112">Para obter mais informações sobre a recuperação de um ataque de ransomware, confira [recuperar de um ataque de ransomware no Microsoft 365](recover-from-ransomware.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="2d7d0-113">Com a crescente complexidade dos ataques, é ainda difícil para os usuários treinados identificar mensagens de phishing sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="2d7d0-114">Felizmente, o Exchange Online Protection (EOP) e os recursos adicionais no Office 365 Advanced Threat Protection (Office 365 ATP) podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="2d7d0-115">Proteção contra phishing no EOP</span><span class="sxs-lookup"><span data-stu-id="2d7d0-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="2d7d0-116">EOP (ou seja, as organizações Microsoft 365 sem ATP) contêm recursos que podem ajudar a proteger sua organização contra ameaças de phishing:</span><span class="sxs-lookup"><span data-stu-id="2d7d0-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="2d7d0-117">**Inteligência contra falsificação**: Revise as mensagens falsas dos remetentes em domínios internos e externos e permita ou bloqueie esses remetentes.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="2d7d0-118">Para obter mais informações, consulte [Configure spoof Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="2d7d0-119">**Políticas anti-phishing no EOP**: ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e especificar a ação para remetentes falsificados bloqueados (mover para a pasta lixo eletrônico ou quarentena).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="2d7d0-120">Para obter mais informações, consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="2d7d0-121">**Autenticação de email implícita**: o EOP aprimora as verificações de autenticação de email padrão para emails de entrada ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação de remetente, histórico de remetente, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes falsificados.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="2d7d0-122">Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="2d7d0-123">Proteção contra phishing adicional no Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2d7d0-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="2d7d0-124">O Office 365 ATP contém recursos adicionais e mais avançados de anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="2d7d0-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="2d7d0-125">**Políticas anti-phishing do ATP**: criar novas políticas personalizadas, definir configurações de antipersonificação (proteger usuários e domínios de personificação), configurações de inteligência de caixa de correio e limites de phishing avançados ajustável.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="2d7d0-126">Para obter mais informações, consulte [Configure ATP anti-phishing Policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="2d7d0-127">Para obter mais informações sobre as diferenças entre as políticas anti-phishing e as políticas anti-phishing da ATP, consulte [anti-phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="2d7d0-128">**Modos de exibição de campanha**: aprendizado de máquina e outros heurísticos identificam e analisam mensagens envolvidas em ataques de phishing coordenados em todo o serviço e sua organização.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="2d7d0-129">Para obter mais informações, consulte [Campaign views in Office 365 ATP](campaigns.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="2d7d0-130">**Simulador de ataques**: os administradores podem criar mensagens de phishing falsas e enviá-las aos usuários internos como uma ferramenta de educação.</span><span class="sxs-lookup"><span data-stu-id="2d7d0-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="2d7d0-131">Para obter mais informações, consulte o [simulador de ataques no Office 365 ATP](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="2d7d0-132">Outros recursos de anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2d7d0-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="2d7d0-133">Para usuários finais: [proteger-se contra esquemas de phishing e outras formas de fraude online](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="2d7d0-134">[Como a Microsoft 365 valida o endereço de origem para impedir o phishing](how-office-365-validates-the-from-address.md).</span><span class="sxs-lookup"><span data-stu-id="2d7d0-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
