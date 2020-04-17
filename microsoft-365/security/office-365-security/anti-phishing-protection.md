---
title: Proteção antiphishing no Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: O Office 365 oferece uma variedade de proteção contra ataques de phishing por padrão e também por meio de recursos adicionais no Office 365 Advanced Threat Protection (ATP). Este tópico apresenta os recursos online que você pode usar para aprender sobre e implementar opções e estratégias anti-phishing no Office 365.
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537420"
---
# <a name="anti-phishing-protection-in-office-365"></a>Proteção antiphishing no Office 365

*Phishing* um ataque de email que tenta roubar informações confidenciais em mensagens que parecem ser de remetentes legítimos ou confiáveis. Há categorias específicas de phishing. Por exemplo:

- O **spear phishing** usa conteúdo muito focalizado e personalizado que é especificamente ajustado para os destinatários de destino (normalmente, após o reconhecimento dos destinatários pelo invasor).

- O **Whaling** é direcionado para executivos ou outros destinos de alto valor dentro de uma organização para obter o máximo de efeito.

- O **Bec (email de negócios corporativos)** usa remetentes confiáveis falsificados (gerentes financeiros, clientes, parceiros confiáveis etc.) em um esforço para enganar o destinatário para aprovar pagamentos, transferir fundos ou divulgar dados do cliente.

- **Ransomware** que criptografa seus dados e exige que o pagamento seja descriptografado quase sempre inicia em mensagens de phishing. A proteção anti-phishing não pode ajudar você a descriptografar arquivos criptografados, mas pode ajudar a detectar as mensagens de phishing iniciais que estão associadas à campanha de ransomware. Para obter mais informações sobre a recuperação de um ataque de ransomware, confira [recuperar de um ataque de ransomware no Office 365](recover-from-ransomware.md).

Com a crescente complexidade dos ataques, é ainda difícil para os usuários treinados identificar mensagens de phishing sofisticadas. Felizmente, o Exchange Online Protection (EOP) e os recursos adicionais no Office 365 Advanced Threat Protection (ATP) podem ajudar.

## <a name="anti-phishing-protection-in-eop"></a>Proteção contra phishing no EOP

EOP (ou seja, as organizações do Office 365 sem a ATP) contêm recursos que podem ajudar a proteger sua organização contra ameaças de phishing:

- **Inteligência de falsificação**: revise mensagens falsificadas de remetentes em domínios internos e externos e permitir ou bloquear esses remetentes. Para obter mais informações, consulte [Configure spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).

- **Política anti-phishing padrão**: ativar ou desativar a inteligência de falsificação, ativar ou desativar a identificação de remetente não autenticado no Outlook e especificar a ação para remetentes falsificados bloqueados (mover para a pasta lixo eletrônico ou quarentena). Para obter mais informações, consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

- **Autenticação de email implícita**: o EOP aprimora as verificações de autenticação de email padrão para emails de entrada ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)) com reputação de remetente, histórico de remetente, histórico de destinatários, análise comportamental e outras técnicas avançadas para ajudar a identificar remetentes falsificados. Para obter mais informações, consulte [autenticação de email no Office 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Proteção contra phishing adicional no Office 365 ATP

O Office 365 ATP contém recursos adicionais e mais avançados de anti-phishing:

- **Políticas anti-phishing do ATP**: criar novas políticas personalizadas, definir configurações de antipersonificação (proteger usuários e domínios de personificação), configurações de inteligência de caixa de correio e limites de phishing avançados ajustável. Para obter mais informações, consulte [Configure ATP anti-phishing Policies in Office 365](configure-atp-anti-phishing-policies.md). Para obter mais informações sobre as diferenças entre políticas anti-phishing e políticas antiphishing da ATP, consulte [políticas de anti-phishing no Office 365](set-up-anti-phishing-policies.md).

- **Modos de exibição de campanha**: aprendizado de máquina e outros heurísticos identificam e analisam mensagens envolvidas em ataques de phishing coordenados em todo o serviço e sua organização. Para obter mais informações, consulte [Campaign views in Office 365 ATP](campaigns.md).

- **Simulador de ataques**: os administradores podem criar mensagens de phishing falsas e enviá-las aos usuários internos como uma ferramenta de educação. Para obter mais informações, consulte o [simulador de ataques no Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Outros recursos de anti-phishing

- Para usuários finais: [proteger-se contra esquemas de phishing e outras formas de fraude online](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).

- [Como o Office 365 valida o endereço de para impedir o phishing](how-office-365-validates-the-from-address.md).
