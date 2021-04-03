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
# <a name="anti-phishing-protection-in-microsoft-365"></a>Proteção anti-phishing no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* é um ataque de email que tenta roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis. Há categorias específicas de phishing. Por exemplo:

- **O phishing** de lança usa conteúdo focado e personalizado especificamente personalizado para os destinatários direcionados (normalmente, após o reconhecimento nos destinatários pelo invasor).

- **A expiração é** direcionada a executivos ou outros destinos de alto valor dentro de uma organização para efeito máximo.

- O **BEC (compromisso** de email comercial) usa senders confiáveis forjados (diretores financeiros, clientes, parceiros confiáveis, etc.) para enganar os destinatários para aprovar pagamentos, transferir fundos ou revelar dados do cliente. Saiba mais assistindo [a este vídeo](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **O ransomware** que criptografa seus dados e exige pagamento para descriptografá-los quase sempre começa em mensagens de phishing. A proteção anti-phishing não pode ajudá-lo a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens iniciais de phishing associadas à campanha de ransomware. Para obter mais informações sobre a recuperação de um ataque de ransomware, consulte [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Com a crescente complexidade dos ataques, é até difícil para usuários treinados identificar mensagens de phishing sofisticadas. Felizmente, a Proteção do Exchange Online (EOP) e os recursos adicionais no Microsoft Defender para Office 365 podem ajudar.

## <a name="anti-phishing-protection-in-eop"></a>Proteção anti-phishing no EOP

O EOP (ou seja, organizações do Microsoft 365 sem o Microsoft Defender para Office 365) contém recursos que podem ajudar a proteger sua organização contra ameaças de phishing:

- **Inteligência contra falsificação**: Revise as mensagens falsas dos remetentes em domínios internos e externos e permita ou bloqueie esses remetentes. Para obter mais informações, [consulte Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

- **Políticas anti-phishing** no EOP : ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação do remetente não autenticado no Outlook e especificar a ação para remetentes espojados bloqueados (mover para a pasta Lixo Eletrônico ou quarentena). Para obter mais informações, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- **Autenticação** implícita de email : O EOP aprimora verificações padrão de autenticação de email para email de entrada ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação de remetente, histórico de remetentes, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes forjados. Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Proteção adicional contra phishing no Microsoft Defender para Office 365

O Microsoft Defender para Office 365 contém recursos anti-phishing adicionais e mais avançados:

- **Políticas anti-phishing no Microsoft Defender para Office 365**: Crie novas políticas personalizadas, configure configurações anti-representação (proteja usuários e domínios contra representação), configurações de inteligência de caixa de correio e limites avançados de phishing ajustáveis. Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Para obter mais informações sobre as diferenças entre políticas anti-phishing no EOP e políticas anti-phishing no Defender para Office 365, consulte [Políticas anti-phishing no Microsoft 365](set-up-anti-phishing-policies.md).

- **Exibições de** campanha : Aprendizado de máquina e outras heurísticas identificam e analisam mensagens envolvidas em ataques de phishing coordenados contra todo o serviço e sua organização. Para obter mais informações, consulte [Exibições de campanha no Microsoft Defender para Office 365](campaigns.md).

- **Simulador de** ataque : os administradores podem criar mensagens de phishing falsas e enviá-las para usuários internos como uma ferramenta educacional. Para obter mais informações, consulte [Simulador de Ataque no Microsoft Defender para Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Outros recursos anti-phishing

- Para usuários finais: [proteja-se contra esquemas de phishing e outras formas de fraude online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Como o Microsoft 365 valida o endereço De para evitar phishing](how-office-365-validates-the-from-address.md).
