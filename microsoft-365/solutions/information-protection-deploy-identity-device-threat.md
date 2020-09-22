---
title: Usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados
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
ms.custom: ''
description: Evitar violações de dados pessoais com serviços de proteção de identidade, dispositivo e ameaça do Microsoft 365.
ms.openlocfilehash: a0efdcfe8e9d27e19b6cf1355a6d0943b7cdaa59
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195658"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados

A Microsoft 365 fornece vários recursos de proteção de identidade, dispositivo e ameaça que as organizações podem empregar para ajudar a cumprir as normas de conformidade relacionadas à privacidade dos dados. Este artigo descreve o que as normas de privacidade de dados exigem nessas áreas e fornece uma lista de recursos e serviços do Microsoft 365 relacionados com links para mais informações para ajudá-lo a lidar com os requisitos de implementação.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Como a proteção de identidade, dispositivo e ameaça se relaciona à regulamentação de privacidade de dados

Embora as leis de privacidade dos dados variem em sua especificidade, a essência do que eles chamam é incorporada no artigo da RGPD 5 (1) (f), que afirma que: 

- Os dados pessoais devem ser processados de forma a garantir a segurança adequada dos dados pessoais, incluindo proteção contra processamento não autorizado ou não ilegal e contra perda acidental, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas (' integridade e confidencialidade ').

Como as violações de dados pessoais são freqüentemente causadas por comprometimento de conta de usuário ou administrador e acesso de sistema mal-intencionado. Por exemplo, uma conta de administrador atacante pode resultar em exfiltration de números de cartão de crédito do cliente ou outras informações pessoais. Toda a proteção de identidade, dispositivo e ameaça do recomendável disponível com o Microsoft 365 pode ser implementada, que será refletida em sua pontuação de conformidade, encontrada no gerente de conformidade.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>Usando os resultados do trabalho de avaliação e do gerente de conformidade

O Gerenciador de conformidade inclui a proteção de identidade, dispositivo e ameaça usando estas categorias:

- Identity corresponde à categoria de **acesso de controle**
- O dispositivo corresponde à categoria **gerenciar dispositivos**
- Proteção contra ameaças corresponde à categoria **proteger contra ameaças**
 
Se eles forem selecionados em nosso conjunto de exemplos de quatro principais regulamentações de privacidade de dados, o Gerenciador de conformidade especificará 90 ações aprimoradas, a maioria delas será classificada como "27". Como um grande número é chamado de Gerenciador de conformidade para essas categorias, algumas das mais comuns estão listadas aqui, para referência.

Use o [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) para identidade e a categoria **acesso de controle** , com a qual você pode:

- Implementar a autenticação resistente à repetição (para evitar ataques de interceptação)
- Bloquear a autenticação herdada.
- Configure o risco do usuário e as políticas de risco de entrada do usuário.
- Habilitar o acesso condicional e a MFA (autenticação multifator) para administradores e não administradores.
- Configurar e impor diretivas de senha.
- Restringir o acesso a contas privilegiadas com o Azure AD Privileged Identity Management.
- Desabilitar o acesso ao término.
- Auditar contas de usuário e alterações de status.
- Revise as alterações administrativas e grupo de funções.

Use o [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) para dispositivos e a categoria **gerenciar dispositivos** , com a qual você pode:

- Bloquear desbloqueado dispositivos móveis quebrados e com raiz.
- Configure o Intune para gerenciamento de dispositivos móveis.
- Criar políticas de conformidade para dispositivos Android, iOS, macOS e Windows.
- Criar um perfil de configuração de dispositivo para dispositivos Android, iOS, macOS e Windows.
- Criar políticas de proteção de aplicativos para iOS e Windows.
- Oculta as informações com tela de bloqueio.
- Implementar diretivas de senha para dispositivos móveis.
- Exigir dispositivos móveis para bloqueio na inatividade.
- Exigir dispositivos móveis para apagar em várias falhas de entrada.

Use o [Exchange Online Protection e a proteção avançada contra ameaças do Office 365 (ATP)](../security/office-365-security/office-365-atp.md) para a categoria **proteger contra ameaças** , com a qual você pode:

- Habilitar autenticação de remetente (SPF, DMARC e DKIM).
- Configure as políticas anti-phishing da proteção avançada contra ameaças (ATP) do Office 365.
- Implementar anexos seguros de ATP.
- Implementar links de ATP seguros.
- Implementar políticas de detecção e resposta de malware.
- Implementar políticas de spam de saída e de entrada.

### <a name="references"></a>Referencie

- [Identidade comum e políticas de acesso ao dispositivo](../enterprise/identity-access-policies.md)
- [Proteção contra ameaças no Office 365](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [Anexos Seguros da ATP](../security/office-365-security/atp-safe-attachments.md)
- [Links Seguros de ATP](../security/office-365-security/atp-safe-links.md)
- [Documentos Seguros da ATP](../security/office-365-security/safe-docs.md)
