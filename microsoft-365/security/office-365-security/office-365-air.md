---
title: Investigação e resposta automatizadas no Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Começar a usar recursos automatizados de investigação e resposta no Microsoft Defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6ccefb5c435f08fcef4dcc872af676fba70668ee
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794539"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigação e resposta automatizadas (AIR) no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[O Microsoft Defender para Office 365](office-365-atp.md) inclui poderosos recursos automatizados de investigação e resposta (AIR) que podem economizar tempo e esforço da equipe de operações de segurança. À medida que os alertas são disparados, fica a sua equipe de operações de segurança revisar, priorizar e responder a esses alertas. Acompanhar o volume de alertas de entrada pode sobrecarregar. Automatizar algumas dessas tarefas pode ajudar.

O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos air incluem processos de investigação automatizada em resposta a ameaças conhecidas que existem atualmente. As ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda efetivamente a ameaças detectadas. Com o AIR, sua equipe de operações de segurança pode se concentrar em tarefas de prioridade mais alta sem perder a visão de alertas importantes que são disparados.

Este artigo descreve:

- O [fluxo geral do AIR](#the-overall-flow-of-air);
- [Como obter AIR](#how-to-get-air); e
- As [permissões necessárias para configurar](#required-permissions-to-use-air-capabilities) ou usar os recursos air.

Este artigo também inclui [as próximas etapas](#next-steps)e recursos para saber mais.

## <a name="the-overall-flow-of-air"></a>O fluxo geral do AIR

Um alerta é disparado, e um manual de segurança inicia uma investigação automatizada, o que resulta em descobertas e ações recomendadas. Aqui está o fluxo geral do AIR, passo a passo:

1. Uma investigação automatizada é iniciada de uma das seguintes maneiras:

   - Um [alerta é acionado por](#which-alert-policies-trigger-automated-investigations) algo suspeito no email (como uma mensagem, anexo, URL ou conta de usuário comprometida). Um incidente é criado e uma investigação automatizada começa.

     ---ou---

   - Um analista de [segurança inicia uma investigação automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) ao usar o Explorador de [Ameaças.](threat-explorer.md)

2. Enquanto uma investigação automatizada é executado, ela coleta dados adicionais sobre o email em questão e entidades relacionadas a esse email. Essas entidades podem incluir arquivos, URLs e destinatários.  O escopo da investigação pode aumentar à medida que alertas novos e relacionados são acionados.

3. Durante e após uma investigação automatizada, [detalhes e resultados](air-view-investigation-results.md) estão disponíveis para exibição. Os resultados [incluem](air-remediation-actions.md) ações recomendadas que podem ser tomadas para responder e remediar quaisquer ameaças encontradas. Além disso, um [log do playbook](air-view-investigation-results.md#playbook-log) está disponível que rastreia todas as atividades de investigação.

4. Sua equipe de operações de segurança [revisa os](air-view-investigation-results.md)resultados e recomendações da investigação e aprova ou [rejeita ações de correção.](air-review-approve-pending-completed-actions.md)

5. Como as ações de correção pendentes são aprovadas (ou rejeitadas), a investigação automatizada é concluída.

> [!IMPORTANT]
> No Microsoft Defender para Office 365, nenhuma ação de correção é realizada automaticamente. As ações de correção só serão tomadas mediante a aprovação da equipe de segurança da sua organização.
>
> Os recursos da AIR economizam o tempo da equipe de operações de segurança identificando ações de correção e fornecendo os detalhes necessários para tomar uma decisão informada.

Durante e após cada investigação automatizada, sua equipe de operações de segurança pode:

- [Exibir detalhes sobre um alerta relacionado a uma investigação](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Exibir os detalhes dos resultados de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar e aprovar ações como resultado de uma investigação](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obter uma visão geral mais detalhada, consulte [Como funciona o AIR.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Como obter o AIR

Os recursos AIR estão incluídos [no Microsoft Defender para Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)desde que suas políticas e alertas sejam configurados. Se você quiser ajuda com isso, siga [](protect-against-threats.md) as orientações em Proteger contra ameaças para configurar ou definir as seguintes configurações de proteção:

1. [Log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (deve estar ligado)

2. [Políticas antimalware](protect-against-threats.md#part-1---anti-malware-protection)

3. [Proteção antiphishing](protect-against-threats.md#part-2---anti-phishing-protection)

4. [Proteção antispam.](protect-against-threats.md#part-3---anti-spam-protection)

5. [Links seguros e anexos seguros.](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

6. [Anexos seguros para SharePoint, OneDrive e Microsoft Teams.](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)

7. [Limpeza automática zero hora para email.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Além disso, certifique-se [de revisar as políticas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)de alerta da sua organização, especialmente as políticas padrão na categoria gerenciamento de [ameaças.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Quais políticas de alerta disparam investigações automatizadas?

O Microsoft 365 fornece muitas políticas de alerta internas que ajudam a identificar o abuso de permissões de administrador do Exchange, atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Várias das políticas [de alerta padrão podem](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) disparar investigações automatizadas. A tabela a seguir descreve os alertas que disparam investigações automatizadas, sua gravidade no centro de segurança do Microsoft 365 e como eles são gerados:

|Alerta|Severity|Como o alerta é gerado|
|---|---|---|
|Um clique de URL potencialmente mal-intencionado foi detectado|**High**|Esse alerta é gerado quando ocorre um dos seguintes: <ul><li>Um usuário protegido por [Links seguros em](atp-safe-links.md) sua organização clica em um link mal-intencionado</li><li>As alterações de veredito para URLs são identificadas pelo Microsoft Defender para Office 365</li><li>Os usuários substituem as páginas de aviso de Links seguros (com base na política de [Links seguros da sua organização).](set-up-atp-safe-links-policies.md)</li></ul> <p> Para obter mais informações sobre eventos que disparam esse alerta, consulte [Configurar políticas de Links seguros.](set-up-atp-safe-links-policies.md)|
|Uma mensagem de email é relatada por um usuário como malware ou phishing|**Informacional**|Esse alerta é gerado quando os usuários em sua organização relatam mensagens como emails de phishing usando o complemento Mensagem [de Relatório.](enable-the-report-message-add-in.md)|
|As mensagens de email que contêm malware são removidas após a entrega|**Informacional**|Esse alerta é gerado quando as mensagens de email que contêm malware são entregues às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectados das caixas de correio do Exchange Online usando a limpeza automática [zero hora.](zero-hour-auto-purge.md)|
|As mensagens de email que contêm URLs de phishing são removidas após a entrega|**Informacional**|Esse alerta é gerado quando as mensagens que contêm phishing são entregues às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectados das caixas de correio do Exchange Online usando a limpeza automática [zero hora.](zero-hour-auto-purge.md)|
|Padrões suspeitos de envio de email são detectados|**Medium**|Esse alerta é gerado quando alguém em sua organização envia emails suspeitos e está em risco de ser impedido de enviar emails. Esse é um aviso antecipado sobre o comportamento que pode indicar que a conta está comprometida, mas não grave o suficiente para restringir o usuário. <p> Embora seja raro, um alerta gerado por essa política pode ser uma anomalia. No entanto, é uma boa ideia verificar [se a conta de usuário está comprometida.](responding-to-a-compromised-email-account.md)|
|Um usuário está impedido de enviar emails|**High**|Esse alerta é gerado quando alguém em sua organização está impedido de enviar emails de saída. Isso normalmente resulta quando uma conta [de email é comprometida.](responding-to-a-compromised-email-account.md) <p> Para saber mais sobre usuários restritos, confira Remover usuários bloqueados do portal Usuários [Restritos no Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Para saber mais sobre políticas de alerta ou editar as configurações padrão, confira Políticas de alerta no centro de conformidade do [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar os recursos air

As permissões são concedidas por meio de determinadas funções, como as descritas na tabela a seguir:

|Tarefas|Função(s) necessária|
|---|---|
|Configurar recursos do AIR|Uma das seguintes funções: <ul><li>Administrador Global</li><li>Administrador de Segurança</li></ul> <p> Essas funções podem ser atribuídas no [Azure Active Directory ou](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) no Centro de Conformidade e [& Segurança.](permissions-in-the-security-and-compliance-center.md)|
|Iniciar uma investigação automatizada <p> ---ou--- <p> Aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas no [Azure Active Directory ou](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) no Centro de Conformidade & [Segurança:](permissions-in-the-security-and-compliance-center.md) <ul><li>Administrador Global</li><li>Administrador de Segurança</li><li>Leitor de segurança <br> ---e--- </li><li>Pesquisar e Limpar (essa função é atribuída apenas no Centro de Conformidade e [Segurança & Segurança.](permissions-in-the-security-and-compliance-center.md) Talvez seja preciso criar um novo grupo de funções e adicionar a função Pesquisar e Limpar a esse novo grupo de funções.</li></ul>|
|

## <a name="required-licenses"></a>Licenças necessárias

[As licenças do Microsoft Defender para Office 365 Plano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) devem ser atribuídas a:

- Administradores de segurança (incluindo administradores globais)
- A equipe de operações de segurança da sua organização (incluindo leitores de segurança e aqueles com a **função Pesquisar e** Limpar)
- Usuários finais

## <a name="next-steps"></a>Próximas etapas

- [Ver detalhes e resultados de uma investigação automatizada](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar e aprovar ações pendentes](air-remediation-actions.md)

## <a name="see-also"></a>Confira também

- [Investigação e correção automatizadas no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigação e resposta automatizadas no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
