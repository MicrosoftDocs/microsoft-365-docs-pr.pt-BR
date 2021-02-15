---
title: Usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Impedir violações de dados pessoais com os serviços de identidade, dispositivo e proteção contra ameaças do Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847173"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados

O Microsoft 365 fornece vários recursos de proteção contra ameaças, dispositivos e identidades que as organizações podem empregar para ajudar a cumprir os regulamentos de conformidade relacionados à privacidade de dados. Este artigo descreve o que as regulamentações de privacidade de dados exigem nessas áreas e fornece uma lista de recursos e serviços relacionados do Microsoft 365 com links para obter mais informações para ajudá-lo a atender aos requisitos de implementação.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Como a identidade, o dispositivo e a proteção contra ameaças se relacionam com a regulamentação de privacidade de dados

Embora as regulamentações de privacidade de dados variem em sua especificidade, a essência do que eles chamam é embodiada no Artigo 5(1)(f) do RGPD, que declara que: 

- Os dados pessoais devem ser processados de maneira a garantir a segurança adequada dos dados pessoais, incluindo proteção contra processamento não autorizado ou ilegal e contra perda, destruição ou danos acidentais, usando medidas técnicas ou organizacionais apropriadas ('integridade e confidencialidade').

Como as violações de dados pessoais geralmente são causadas por comprometimento da conta de usuário final ou administrativa e acesso ao sistema mal-intencionado. Por exemplo, um hackers de conta de administrador pode resultar em exfiltração de números de cartão de crédito do cliente ou outras informações pessoais. Todas as identidades, dispositivos e proteção contra ameaças geralmente aconselháveis disponíveis no Microsoft 365 devem ser implementadas, o que será refletido na sua pontuação de conformidade, encontrada no Gerenciador de Conformidade.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Usando os resultados do trabalho de avaliação e do Gerenciador de Conformidade

O Gerenciador de Conformidade inclui identidade, dispositivo e proteção contra ameaças usando estas categorias:

- A identidade corresponde à categoria **Acesso ao** Controle
- O dispositivo corresponde à categoria **Gerenciar Dispositivos**
- A proteção contra ameaças corresponde à categoria **Proteger Contra Ameaças**
 
Se eles forem selecionados em nosso conjunto de amostra de quatro regulamentos de privacidade de dados principais, o Gerenciador de Conformidade especificará 90 ações de melhoria, a maioria delas com pontuação "27". Como um número tão grande é chamado pelo Gerenciador de Conformidade para essas categorias, algumas das mais comuns são listadas aqui, para referência.

Use [o Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria acesso **de** controle, com a qual você pode:

- Implementar a autenticação resistente a repetição (para evitar ataques "Man in the middle")
- Bloquear a autenticação herdada.
- Configure as políticas de risco do usuário e de risco de login do usuário.
- Habilitar o Acesso Condicional e a MFA (autenticação multifacional) para administradores e não administradores.
- Configurar e impor políticas de senha.
- Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.
- Desabilitar o acesso após o término.
- Auditoria de contas de usuário e alterações de status.
- Revise o grupo de funções e as alterações administrativas.

Use [o Microsoft Endpoint Manager para](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) dispositivos e a categoria **Gerenciar** Dispositivos, com a qual você pode:

- Bloqueie a cadeia de dispositivos móveis quebrados e com raiz.
- Configurar o Intune para gerenciamento de dispositivo móvel.
- Crie políticas de conformidade para dispositivos Android, iOS, macOS e Windows.
- Crie um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.
- Crie políticas de proteção de aplicativos para iOS e Windows.
- Ocultar informações com a tela de bloqueio.
- Implementar políticas de senha para dispositivos móveis.
- Exigir que os dispositivos móveis bloqueiem a inatividade.
- Exigir que os dispositivos móveis limpem várias falhas de entrada.

Use [a Proteção do Exchange Online e o Microsoft Defender para Office 365](../security/office-365-security/office-365-atp.md) para a categoria Proteger **Contra** Ameaças, com a qual você pode:

- Habilitar a autenticação de remetente (SPF, DMARC e DKIM).
- Configurar o Microsoft Defender para políticas anti-phishing do Office 365.
- Implementar Anexos Seguros.
- Implementar Links seguros.
- Implementar políticas de detecção e resposta de malware.
- Implementar políticas de spam de saída e de entrada.

### <a name="references"></a>Referências:

- [Identidade comum e políticas de acesso ao dispositivo](../security/office-365-security/identity-access-policies.md)
- [Proteger contra ameaças no Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Anexos Seguros](../security/office-365-security/atp-safe-attachments.md)
- [Links Seguros](../security/office-365-security/atp-safe-links.md)
- [Documentos Seguros](../security/office-365-security/safe-docs.md)
