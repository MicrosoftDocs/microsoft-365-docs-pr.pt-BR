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
description: Os administradores podem saber mais sobre os recursos de proteção anti-phishing no Exchange Online Protection (EOP) e no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289048"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Proteção anti-phishing no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Phishing* é um ataque de email que tenta roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis. Há categorias específicas de phishing. Por exemplo:

- **O phishing** em busca de phishing usa conteúdo focado e personalizado especificamente adaptado aos destinatários-alvo (normalmente, após a ida e volta aos destinatários pelo invasor).

- **A busca é** direcionada a executivos ou a outros alvos de alto valor dentro de uma organização para um efeito máximo.

- O **BEC (comprometimento de email empresarial)** usa os destinatários confiáveis forjados (diretores financeiros, clientes, parceiros confiáveis etc.) para ajudar os destinatários a aprovar pagamentos, transferir fundos ou revelar dados de clientes.

- **Ransomware** que criptografa seus dados e exige pagamento para descriptografá-los quase sempre começa em mensagens de phishing. A proteção anti-phishing não pode ajudá-lo a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens iniciais de phishing associadas à campanha de ransomware. Para obter mais informações sobre a recuperação de um ataque de ransomware, confira [Recuperar-se de um ataque de ransomware no Microsoft 365.](recover-from-ransomware.md)

Com a crescente complexidade dos ataques, é até difícil para usuários treinados identificar mensagens de phishing sofisticadas. Felizmente, a Proteção do Exchange Online (EOP) e os recursos adicionais do Microsoft Defender para Office 365 podem ajudar.

## <a name="anti-phishing-protection-in-eop"></a>Proteção anti-phishing no EOP

O EOP (ou seja, organizações do Microsoft 365 sem o Microsoft Defender para Office 365) contém recursos que podem ajudar a proteger sua organização contra ameaças de phishing:

- **Inteligência contra falsificação**: Revise as mensagens falsas dos remetentes em domínios internos e externos e permita ou bloqueie esses remetentes. Para obter mais informações, [consulte Configurar a inteligência contra spoof no EOP.](learn-about-spoof-intelligence.md)

- **Políticas anti-phishing no EOP:** ativar ou desativar a inteligência contra spoof, ativar ou desativar a identificação de remetente não autenticado no Outlook e especificar a ação para remetentes com spoofed bloqueados (mover para a pasta Lixo Eletrônico ou quarentena). Para obter mais informações, [consulte Configurar políticas anti-phishing no EOP.](configure-anti-phishing-policies-eop.md)

- Autenticação implícita de **email:** o EOP aprimora verificações de autenticação de email padrão para emails de entrada ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação do remetente, histórico do remetente, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes forjados. Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Proteção anti-phishing adicional no Microsoft Defender para Office 365

O Microsoft Defender para Office 365 contém recursos anti-phishing adicionais e mais avançados:

- Políticas **anti-phishing no Microsoft Defender para Office 365:** criar novas políticas personalizadas, definir configurações anti-representação (proteger usuários e domínios contra representação), configurações de inteligência de caixa de correio e limites de phishing avançados ajustáveis. Para obter mais informações, [consulte Configurar políticas anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md) Para obter mais informações sobre as diferenças entre as políticas anti-phishing no EOP e as políticas anti-phishing no Defender para Office 365, consulte [Políticas anti-phishing no Microsoft 365.](set-up-anti-phishing-policies.md)

- **Exibições de** Campanha: Aprendizado de máquina e outras heurísticas identificam e analisam mensagens envolvidas em ataques coordenados de phishing contra todo o serviço e sua organização. Para obter mais informações, consulte [Exibições de Campanha no Microsoft Defender para Office 365.](campaigns.md)

- **Simulador de** ataque: os administradores podem criar mensagens falsas de phishing e enviá-las aos usuários internos como uma ferramenta educacional. Para saber mais, confira [Simulador de Ataque no Microsoft Defender para Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Outros recursos anti-phishing

- Para usuários finais: [proteja-se contra esquemas de phishing e outras formas de fraude online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Como o Microsoft 365 valida o endereço De para evitar phishing.](how-office-365-validates-the-from-address.md)
