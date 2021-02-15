---
title: Sobre a avaliação do Microsoft Defender para Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: Os administradores podem saber mais sobre o modo de avaliação do Microsoft Defender para Office 365
ms.openlocfilehash: 6207ae117f06a0e5f10d4a7a47a251137c51df05
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233573"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Sobre a avaliação do Microsoft Defender para Office 365

O Microsoft Defender para Office 365 protege sua organização contra ameaças mal-intencionadas que são colocadas por mensagens de email, links (URLs) e ferramentas de colaboração. O Defender for Office 365 inclui:

- **Políticas de proteção contra ameaças**: defina políticas de proteção contra ameaças para definir o nível de proteção apropriado para a sua organização.
- **Relatórios:** Exibir relatórios em tempo real para monitorar o desempenho do Defender para Office 365 em sua organização.
- **Recursos de investigação e resposta de ameaças**: use as ferramentas de ponta para investigar, compreender, simular e prevenir ameaças.
- **Recursos de investigação e resposta automatizadas**: poupe tempo e esforço, investigando e reduzindo as ameaças.

Uma avaliação do Microsoft Defender para Office 365 é a maneira mais fácil de experimentar os recursos do Defender para Office 365, e a configuração leva apenas alguns cliques. Após a conclusão da configuração de avaliação, todos os recursos do Defender para Office 365 Plano 1 e Plano 2 estarão disponíveis na organização por até 90 dias.

> [!NOTE]
> A configuração automatizada descrita neste artigo está atualmente na Visualização Pública e pode não estar disponível em seu local.

## <a name="terms-and-conditions"></a>Termos e condições

A avaliação do Defender para Office 365 está disponível por 90 dias e pode ser iniciada para todos os seus usuários. Para saber mais, confira Os Termos de Avaliação do [Microsoft Defender para Office 365 & condições.](defender-for-office-365-trial-terms-and-conditions.md)

## <a name="set-up-a-defender-for-office-365-trial"></a>Configurar um Defender para avaliação do Office 365

Uma avaliação permite que as organizações configurem e configurem facilmente os recursos do Defender para Office 365. Durante a instalação, as políticas que são exclusivas do Defender para Office 365 (especificamente, [Anexos](atp-safe-attachments.md)Seguros, [Links](atp-safe-links.md)Seguros e proteção contra representação em políticas [anti-spam](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) são aplicadas usando o modelo Padrão para políticas de segurança predefinidas. [](preset-security-policies.md)

Por padrão, essas políticas têm escopo para todos os usuários na organização, mas os administradores podem personalizar as políticas durante ou após a instalação para que se apliquem somente a usuários específicos.

Durante a instalação, a funcionalidade de resposta do MDO (encontrada no MDO P2 ou equivalente) também é configurada para toda a organização. Nenhum scoping de política é necessário.

## <a name="licensing"></a>Licenciamento

Como parte da configuração de avaliação, as licenças do Defender para Office 365 são aplicadas automaticamente à organização. As licenças são gratuitas pelos primeiros 90 dias.

## <a name="permissions"></a>Permissões

Para iniciar ou finalizar a avaliação, você precisa  ser membro das funções de Administrador **Global** ou Administrador de Segurança no Azure Active Directory. Para obter detalhes, consulte [Sobre funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

## <a name="additional-information"></a>Informações adicionais

Depois de se inscrever na avaliação, pode levar até 2 horas para que as alterações e as atualizações sejam disponibilizadas. Além disso, os administradores devem fazer logoff e fazer logoff novamente para ver as alterações.

Os administradores podem desabilitar a avaliação a qualquer momento indo para o <> de teste.

## <a name="availability"></a>Disponibilidade

A avaliação do Defender para Office 365 está sendo gradualmente implantada para clientes existentes que atendem a critérios específicos (incluindo geografia) e que não têm licenças existentes do Defender para Office 365 Plano 1 ou Plano 2 (incluídas em sua assinatura ou como um complemento).

## <a name="learn-more-about-defender-for-office-365"></a>Saiba mais sobre o Defender para Office 365

O Defender para Office 365 ajuda as organizações a proteger sua empresa oferecendo uma lista abrangente de recursos.

Você também pode saber mais sobre o Defender para Office 365 neste [guia interativo.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Diagrama conceitual do Microsoft Defender para Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prevenção

Uma pilha de filtragem robusta impede uma ampla variedade de ataques baseados em volume e direcionados, incluindo comprometimento de email comercial, phishing de credenciais, ransomware e malware avançado.

- [Políticas anti-phishing: configurações exclusivas no Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Anexos Seguros](atp-safe-attachments.md)
- [Links Seguros](atp-safe-links.md)

### <a name="detection"></a>Detecção

A IA líder do setor detecta conteúdo mal-intencionado e suspeito e correlaciona padrões de ataque para identificar campanhas projetadas para evitar a proteção.

- [Exibições de campanha no Microsoft Defender para Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Investigação e busca

Experiências poderosas ajudam a identificar, priorizar e investigar ameaças, com recursos avançados de busca para rastrear ataques no Office 365.

- [Detecções do Explorador de Ameaças e em Tempo Real](threat-explorer.md)
- [Relatórios em tempo real no Defender para Office 365](view-reports-for-atp.md)
- [Rastreadores de Ameaças - Novo e Importante](threat-trackers.md)
- Integração [com o Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)

### <a name="response-and-remediation"></a>Resposta e correção

Amplos recursos de automação e resposta a incidentes ampliam a eficácia e a eficiência da equipe de segurança.

- [Investigação e resposta automatizadas (AIR) no Microsoft Defender para Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Conscientização e Treinamento

Recursos avançados de simulação e treinamento, juntamente com experiências integradas em aplicativos cliente, dão reconhecimento ao usuário.

- [Começar a usar o Treinamento de simulação de ataque](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Postura segura

Modelos e percepções de configuração recomendados ajudam os clientes a se manterem seguros.

- [Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365](preset-security-policies.md)
- [Analisador de configuração para políticas de proteção no EOP e no Microsoft Defender para Office 365.](configuration-analyzer-for-security-policies.md)

## <a name="give-feedback"></a>Envie comentários

Seus comentários nos ajudam a melhorar a proteção do seu ambiente contra ataques avançados. Compartilhe sua experiência e impressões de recursos do produto e resultados de avaliação.
