---
title: Usar identidade, dispositivo e proteção contra ameaças para a regulamentação de privacidade de dados
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
description: Impedir violações de dados pessoais com os serviços de proteção de identidade, dispositivo e ameaças Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199460"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar identidade, dispositivo e proteção contra ameaças para a regulamentação de privacidade de dados

Microsoft 365 oferece vários recursos de proteção contra ameaças, dispositivos e identidades que as organizações podem empregar para ajudar a cumprir os regulamentos de conformidade relacionados à privacidade de dados. Este artigo descreve o que os regulamentos de privacidade de dados exigem nessas áreas e fornece uma listagem de recursos e serviços relacionados Microsoft 365 com links para mais informações para ajudá-lo a lidar com os requisitos de implementação.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Como a identidade, o dispositivo e a proteção contra ameaças se relacionam com a regulamentação de privacidade de dados

Embora os regulamentos de privacidade de dados variem em sua especificidade, a essência do que eles chamam é personificação no Artigo 5(1)(f) do RGPD, que diz que:

- Os dados pessoais devem ser processados de maneira que garanta a segurança apropriada dos dados pessoais, incluindo a proteção contra o processamento não autorizado ou ilegal e contra perdas acidentais, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas ('integridade e confidencialidade').

Como violações de dados pessoais geralmente são causadas por comprometimento da conta de usuário final ou administrativa e acesso mal-intencionado ao sistema. Por exemplo, um hack de conta de administrador pode resultar em exfiltração de números de cartão de crédito do cliente ou outras informações pessoais. Todas as identidades, dispositivos e proteção contra ameaças geralmente recomendáveis disponíveis com o Microsoft 365 devem ser implementadas, o que será refletido na sua pontuação de conformidade, encontrada no Gerenciador de Conformidade.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Usando os resultados do trabalho de avaliação e do Gerenciador de Conformidade

O Gerenciador de Conformidade inclui identidade, dispositivo e proteção contra ameaças usando estas categorias:

- A identidade corresponde à categoria **Acesso para** Controle
- O dispositivo corresponde à categoria **Gerenciar Dispositivos**
- Proteção contra ameaças corresponde à categoria **Proteger Contra Ameaças**
 
Se eles forem selecionados em nosso conjunto de exemplos de quatro regulamentos principais de privacidade de dados, o Gerenciador de Conformidade especificará 90 ações de melhoria, a maioria delas pontuadas como "27". Como um número tão grande é chamado pelo Gerenciador de Conformidade para essas categorias, algumas das mais comuns são listadas aqui, para referência.

Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria **Acesso para** Controle, com a qual você pode:

- Implementar autenticação resistente a repetição (para evitar ataques "homem no meio" )
- Bloquear a autenticação herdada.
- Configure as políticas de risco de usuário e de login do usuário.
- Habilita o Acesso Condicional e a autenticação multifacional (MFA) para administradores e não administradores.
- Configurar e impor políticas de senha.
- Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.
- Desabilitar o acesso ao término.
- Auditar contas de usuário e alterações de status.
- Revise o grupo de funções e as alterações administrativas.

Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos e a categoria **Gerenciar Dispositivos,** com a qual você pode:

- Bloqueie a cadeia de dispositivos móveis quebrados e enraizado.
- Configure o Intune para gerenciamento de dispositivo móvel.
- Crie políticas de conformidade para dispositivos Android, iOS, macOS e Windows.
- Crie um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.
- Crie políticas de proteção de aplicativos para iOS e Windows.
- Ocultar informações com a tela de bloqueio.
- Implemente políticas de senha para dispositivos móveis.
- Exigir que os dispositivos móveis bloqueiem na inatividade.
- Exigir que os dispositivos móveis limpem várias falhas de entrada.

Use [Proteção do Exchange Online e o Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) para a categoria Proteger Contra **Ameaças,** com a qual você pode:

- Habilitar autenticação de remetente (SPF, DMARC e DKIM).
- Configurar o Microsoft Defender para Office 365 anti-phishing.
- Implementar Cofre Anexos.
- Implementar Cofre Links.
- Implemente políticas de detecção e resposta de malware.
- Implemente políticas de spam de saída e de entrada.

### <a name="references"></a>Referências:

- [Identidade comum e políticas de acesso ao dispositivo](../security/office-365-security/identity-access-policies.md)
- [Proteger contra ameaças em Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Anexos Seguros](../security/office-365-security/safe-attachments.md)
- [Links Seguros](../security/office-365-security/safe-links.md)
- [Documentos Seguros](../security/office-365-security/safe-docs.md)
