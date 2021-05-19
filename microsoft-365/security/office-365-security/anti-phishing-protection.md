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
description: Os administradores podem aprender sobre os recursos de proteção anti-phishing no Proteção do Exchange Online (EOP) e no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 290f5f7797d987fb65a99e3f9e656bfec4cf83f3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538334"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Proteção anti-phishing Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* é um ataque por email que tenta roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis. Há categorias específicas de phishing. Por exemplo:

- **O phishing** de lança usa conteúdo focado e personalizado especificamente personalizado para os destinatários direcionados (normalmente, após o reconhecimento nos destinatários pelo invasor).

- **A expiração é** direcionada a executivos ou outros destinos de alto valor dentro de uma organização para efeito máximo.

- O **BEC (compromisso** de email comercial) usa senders confiáveis forjados (diretores financeiros, clientes, parceiros confiáveis, etc.) para enganar os destinatários para aprovar pagamentos, transferir fundos ou revelar dados do cliente. Saiba mais assistindo a [este vídeo](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **O ransomware** que criptografa seus dados e exige pagamento para descriptografá-los quase sempre começa em mensagens de phishing. A proteção anti-phishing não pode ajudá-lo a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens iniciais de phishing associadas à campanha de ransomware. Para obter mais informações sobre a recuperação de um ataque de ransomware, consulte [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Com a crescente complexidade dos ataques, é até difícil para usuários treinados identificar mensagens de phishing sofisticadas. Felizmente, Proteção do Exchange Online (EOP) e os recursos adicionais no Microsoft Defender para Office 365 podem ajudar.

## <a name="anti-phishing-protection-in-eop"></a>Proteção anti-phishing em EOP

O EOP (ou seja, Microsoft 365 sem o Microsoft Defender para Office 365) contém recursos que podem ajudar a proteger sua organização contra ameaças de phishing:

- Inteligência de **spoof**: use a visão de inteligência falsa para revisar os envios espoudos detectados em mensagens de domínios externos e internos e permitir ou bloquear manualmente os senders detectados. Para obter mais informações, consulte [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).

- **Políticas anti-phishing** no EOP : ativar ou desativar a inteligência de spoof, ativar ou desativar a identificação do remetente não autenticado no Outlook e especificar a ação para remetentes com spoofed bloqueados. Para obter mais informações, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- Permitir ou bloquear remetentes com spoofed na Lista de Locatários **Permitir/Bloquear**: quando você substituir o veredito no insight de inteligência de spoof, o remetente spoofed se torna uma entrada manual de permitir ou bloquear que só aparece na guia **Spoof** na Lista de Locatários de Permitir/Bloquear. Você também pode criar manualmente entradas de permitir ou bloquear para os envios de spoof antes que eles são detectados pela inteligência de spoof. Para obter mais informações, consulte [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).

- **Autenticação** implícita de email : O EOP aprimora verificações padrão de autenticação de email para email de entrada ([SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação de remetente, histórico de remetentes, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes forjados. Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Proteção anti-phishing adicional no Microsoft Defender para Office 365

O Microsoft Defender para Office 365 contém recursos anti-phishing adicionais e mais avançados:

- **Políticas anti-phishing** no Microsoft Defender para Office 365 : Configure impersonation protection settings for specific message senders and sender domains, mailbox intelligence settings, and adjustable advanced phishing thresholds. Para obter mais informações, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Para obter mais informações sobre as diferenças entre políticas anti-phishing no EOP e políticas anti-phishing no Defender para Office 365, consulte [Políticas anti-phishing em Microsoft 365](set-up-anti-phishing-policies.md).

- **Exibições de** campanha : Aprendizado de máquina e outras heurísticas identificam e analisam mensagens envolvidas em ataques de phishing coordenados contra todo o serviço e sua organização. Para obter mais informações, consulte [Exibições de campanha no Microsoft Defender para Office 365](campaigns.md).

- **Simulador de** ataque : os administradores podem criar mensagens de phishing falsas e enviá-las para usuários internos como uma ferramenta educacional. Para obter mais informações, consulte [Simulador de Ataque no Microsoft Defender para Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Outros recursos anti-phishing

- Para usuários finais: [proteja-se contra esquemas de phishing e outras formas de fraude online.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Como Microsoft 365 valida o endereço De para evitar phishing](how-office-365-validates-the-from-address.md).
