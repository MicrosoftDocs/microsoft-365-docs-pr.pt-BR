---
title: Sobre a avaliação do Microsoft Defender Office 365
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
description: Os administradores podem aprender sobre o modo de avaliação do Microsoft Defender para Office 365
ms.openlocfilehash: ba01fa45ca9a4e2e5b3597378bf7ddafc8be3f56
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768741"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Sobre a avaliação do Microsoft Defender Office 365

O Microsoft Defender para Office 365 protege sua organização contra ameaças mal-intencionadas que são colocadas por mensagens de email, links (URLs) e ferramentas de colaboração. O Defender for Office 365 inclui:

- **Políticas de proteção contra ameaças**: defina políticas de proteção contra ameaças para definir o nível de proteção apropriado para a sua organização.
- **Relatórios**: Exibir relatórios em tempo real para monitorar o Defender Office 365 desempenho em sua organização.
- **Recursos de investigação e resposta de ameaças**: use as ferramentas de ponta para investigar, compreender, simular e prevenir ameaças.
- **Recursos de investigação e resposta automatizadas**: poupe tempo e esforço, investigando e reduzindo as ameaças.

Uma avaliação do Microsoft Defender para Office 365 é a maneira mais fácil de experimentar os recursos do Defender para Office 365, e a configuração dele requer apenas alguns cliques. Depois que a configuração de avaliação for concluída, todos os recursos do Defender para Office 365 Plano 1 e Plano 2 estarão disponíveis na organização por até 90 dias.

> [!NOTE]
> A configuração automatizada descrita neste artigo está atualmente na Visualização Pública e pode não estar disponível em seu local.

## <a name="terms-and-conditions"></a>Termos e condições

A avaliação do Defender Office 365 está disponível por 90 dias e pode ser iniciada para todos os usuários. Para obter mais informações, consulte [Microsoft Defender for Office 365 Trial Terms & Conditions](defender-for-office-365-trial-terms-and-conditions.md).

## <a name="set-up-a-defender-for-office-365-trial"></a>Configurar um Defender para Office 365 avaliação

Uma avaliação permite que as organizações configurem e configurem facilmente o Defender para Office 365 recursos. Durante a instalação, as políticas que são exclusivas do Defender para Office 365 (especificamente, anexos do Cofre, links [Cofre e proteção de](safe-links.md)representação em políticas [anti-spam](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) são [aplicadas](safe-attachments.md)usando o modelo Padrão para políticas de segurança predefinidas. [](preset-security-policies.md)

Por padrão, essas políticas têm escopo para todos os usuários da organização, mas os administradores podem personalizar as políticas durante ou após a instalação, para que se apliquem somente a usuários específicos.

Durante a instalação, a funcionalidade de resposta do MDO (encontrada no MDO P2 ou equivalente) também é configurada para toda a organização. Não é necessário fazer o scoping de política.

## <a name="licensing"></a>Licenciamento

Como parte da configuração de avaliação, o Defender para Office 365 licenças são aplicadas automaticamente à organização. As licenças são gratuitas nos primeiros 90 dias.

## <a name="permissions"></a>Permissões

Para iniciar ou encerrar a avaliação, você precisa  ser membro das funções Administrador **Global** ou Administrador de Segurança no Azure Active Directory. Para obter detalhes, consulte [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="additional-information"></a>Informações adicionais

Depois de se inscrever na avaliação, pode levar até 2 horas para que as alterações e atualizações sejam disponibilizadas. E, os administradores devem fazer logoff e fazer logoff novamente para ver as alterações.

Os administradores podem desabilitar a avaliação a qualquer momento, indo para o <> cartão.

## <a name="availability"></a>Disponibilidade

A avaliação do Defender para Office 365 está sendo implantada gradualmente para clientes existentes que atendem a critérios específicos (incluindo geografia) e que não têm licenças existentes do Defender para o Plano 1 ou Plano 2 do Office 365 (incluídos na assinatura ou como complemento).

## <a name="learn-more-about-defender-for-office-365"></a>Saiba mais sobre o Defender para Office 365

O Defender para Office 365 ajuda as organizações a proteger sua empresa oferecendo uma lista abrangente de recursos.

Você também pode saber mais sobre o Defender para Office 365 neste [guia interativo](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189).

![Microsoft Defender para Office 365 diagrama conceitual](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prevenção

Uma pilha de filtragem robusta impede uma ampla variedade de ataques baseados em volume e direcionados, incluindo comprometimento de email comercial, phishing de credenciais, ransomware e malware avançado.

- [Políticas anti-phishing: configurações exclusivas no Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Anexos Seguros](safe-attachments.md)
- [Links Seguros](safe-links.md)

### <a name="detection"></a>Detecção

A IA líder do setor detecta conteúdo mal-intencionado e suspeito e correlaciona padrões de ataque para identificar campanhas projetadas para evitar a proteção.

- [Exibições de campanha no Microsoft Defender para Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Investigação e busca

Experiências avançadas ajudam a identificar, priorizar e investigar ameaças, com recursos avançados de busca para rastrear ataques em Office 365.

- [Explorador de Ameaças e Detecções em tempo real](threat-explorer.md)
- [Relatórios em tempo real no Defender para Office 365](view-reports-for-mdo.md)
- [Rastreadores de Ameaças - Novo e Notável](threat-trackers.md)
- Integração [com Microsoft 365 Defender](../defender/microsoft-365-defender.md)

### <a name="response-and-remediation"></a>Resposta e correção

Recursos abrangentes de resposta a incidentes e automação ampliam a eficácia e a eficiência da equipe de segurança.

- [Investigação e resposta automatizadas (AIR) no Microsoft Defender para Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Conscientização e Treinamento

Recursos avançados de simulação e treinamento, juntamente com experiências integradas em aplicativos cliente, conscientizam o usuário.

- [Começar a usar o Treinamento de simulação de ataque](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Postura segura

Modelos recomendados e percepções de configuração ajudam os clientes a obter e permanecer seguros.

- [Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365](preset-security-policies.md)
- [Analisador de configuração para políticas de proteção no EOP e no Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md).

## <a name="give-feedback"></a>Envie comentários

Seus comentários nos ajudam a melhorar a proteção do ambiente contra ataques avançados. Compartilhe sua experiência e impressões dos recursos do produto e dos resultados de avaliação.
