---
title: Investigação e resposta automatizadas no Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08e69013c0108d0caaf76c6a227684f5f1b68355
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083687"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Investigação e resposta automatizadas (AIR) no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[O Microsoft Defender para Office 365](defender-for-office-365.md) inclui recursos avançados de investigação e resposta automatizadas (AIR) que podem economizar tempo e esforço da equipe de operações de segurança. À medida que os alertas são disparados, a equipe de operações de segurança deve revisar, priorizar e responder a esses alertas. Acompanhar o volume de alertas de entrada pode ser avassalador. Automatizar algumas dessas tarefas pode ajudar.

O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos air incluem processos de investigação automatizados em resposta a ameaças conhecidas que existem atualmente. As ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda efetivamente a ameaças detectadas. Com o AIR, sua equipe de operações de segurança pode se concentrar em tarefas de prioridade mais alta sem perder a visão de alertas importantes disparados.

Este artigo descreve:

- O [fluxo geral de AIR;](#the-overall-flow-of-air)
- [Como obter AIR;](#how-to-get-air) e
- As [permissões necessárias para](#required-permissions-to-use-air-capabilities) configurar ou usar recursos AIR.
- Alterações que estão chegando em breve ao Microsoft 365 Defender portal

Este artigo também inclui [as próximas etapas](#next-steps)e recursos para saber mais.

## <a name="the-overall-flow-of-air"></a>O fluxo geral do AIR

Um alerta é acionado e uma playbook de segurança inicia uma investigação automatizada, o que resulta em descobertas e ações recomendadas. Aqui está o fluxo geral do AIR, passo a passo:

1. Uma investigação automatizada é iniciada de uma das seguintes maneiras:
   - Um [alerta é disparado por algo](#which-alert-policies-trigger-automated-investigations) suspeito no email (como uma mensagem, anexo, URL ou conta de usuário comprometida). Um incidente é criado e uma investigação automatizada começa; ou
   - Um analista de [segurança inicia uma investigação automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) ao usar o [Explorer](threat-explorer.md).
2. Enquanto uma investigação automatizada é executado, ele coleta dados sobre o email em questão e entidades relacionadas a esse email. Essas entidades podem incluir arquivos, URLs e destinatários. O escopo da investigação pode aumentar à medida que alertas novos e relacionados são disparados.
3. Durante e após uma investigação automatizada, detalhes [e resultados](air-view-investigation-results.md) estão disponíveis para exibição. Os resultados [incluem ações](air-remediation-actions.md) recomendadas que podem ser tomadas para responder e remediar quaisquer ameaças encontradas.
4. Sua equipe de operações de segurança revisa os resultados [e](air-view-investigation-results.md)recomendações da investigação e aprova ou rejeita ações [de correção.](air-review-approve-pending-completed-actions.md)
5. Como as ações de correção pendentes são aprovadas (ou rejeitadas), a investigação automatizada é concluída.

No Microsoft Defender para Office 365, nenhuma ação de correção é realizada automaticamente. As ações de correção só serão tomadas mediante a aprovação da equipe de segurança da sua organização. Os recursos AIR economizam o tempo de equipe de operações de segurança identificando ações de correção e fornecendo os detalhes necessários para tomar uma decisão informada.

Durante e após cada investigação automatizada, sua equipe de operações de segurança pode:

- [Exibir detalhes sobre um alerta relacionado a uma investigação](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Exibir os detalhes dos resultados de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar e aprovar ações como resultado de uma investigação](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obter uma visão geral mais detalhada, consulte [How AIR works](automated-investigation-response-office.md).

## <a name="how-to-get-air"></a>Como obter AIR

Os recursos AIR são incluídos no [Microsoft Defender para Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2), desde que suas políticas e alertas sejam configurados. Precisa de ajuda? Siga as diretrizes em [Proteger contra ameaças](protect-against-threats.md) para configurar ou configurar as seguintes configurações de proteção:

- [Log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md) (deve ser ligado)
- [Proteção antimalware](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Proteção anti-phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [Anti-spam protection](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Cofre Links e Cofre anexos](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

Além disso, revise as políticas [de](../../compliance/alert-policies.md)alerta da sua organização, especialmente as políticas padrão [na categoria gerenciamento de ameaças.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Quais políticas de alerta disparam investigações automatizadas?

Microsoft 365 fornece muitas Exchange políticas de alerta internas que ajudam a identificar o abuso de permissões de administrador, atividades de malware, possíveis ameaças externas e internas e riscos de governança de informações. Várias das políticas [de alerta padrão podem](../../compliance/alert-policies.md#default-alert-policies) disparar investigações automatizadas. A tabela a seguir descreve os alertas que disparam investigações automatizadas, sua gravidade no portal Microsoft 365 Defender e como eles são gerados:

<br>

****

|Alerta|Gravidade|Como o alerta é gerado|
|---|---|---|
|Um clique de URL potencialmente mal-intencionado foi detectado|**High**|Esse alerta é gerado quando ocorre um dos seguintes: <ul><li>Um usuário protegido por links [Cofre em](safe-links.md) sua organização clica em um link mal-intencionado</li><li>Alterações de veredito para URLs são identificadas pelo Microsoft Defender para Office 365</li><li>Os usuários substituem Cofre páginas de aviso links (com base na política de Cofre [Links da sua organização).](set-up-safe-links-policies.md)</li></ul> <p> Para obter mais informações sobre eventos que disparam esse alerta, consulte [Set up Cofre Links policies](set-up-safe-links-policies.md).|
|Uma mensagem de email é relatada por um usuário como malware ou phishing|**Informativo**|Esse alerta é gerado quando os usuários da sua organização relatam mensagens como emails de phishing usando o complemento [Mensagem](enable-the-report-message-add-in.md) de Relatório ou o [complemento Relatar Phishing](enable-the-report-phish-add-in.md).|
|As mensagens de email que contêm malware são removidas após a entrega|**Informativo**|Esse alerta é gerado quando todas as mensagens de email que contêm malware são entregues às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectados de Exchange Online caixas de correio usando limpeza automática [zero hora](zero-hour-auto-purge.md).|
|As mensagens de email que contêm URLs de phishing são removidas após a entrega|**Informativo**|Esse alerta é gerado quando todas as mensagens que contêm phishing são entregues às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectados de Exchange Online caixas de correio usando limpeza automática [zero hora](zero-hour-auto-purge.md).|
|Padrões suspeitos de envio de email são detectados|**Medium**|Esse alerta é gerado quando alguém em sua organização envia emails suspeitos e corre o risco de ser impedido de enviar emails. O alerta é um aviso antecipado sobre o comportamento que pode indicar que a conta está comprometida, mas não grave o suficiente para restringir o usuário. <p> Embora seja raro, um alerta gerado por essa política pode ser uma anomalia. No entanto, é uma boa ideia verificar se a [conta de usuário está comprometida](responding-to-a-compromised-email-account.md).|
|Um usuário é impedido de enviar emails|**High**|Esse alerta é gerado quando alguém em sua organização é impedido de enviar emails de saída. Esse alerta normalmente resulta quando uma conta [de email é comprometida](responding-to-a-compromised-email-account.md). <p> Para obter mais informações sobre usuários restritos, consulte [Remove blocked users from the Restricted Users portal in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|
|

> [!TIP]
> Para saber mais sobre políticas de alerta ou editar as configurações padrão, consulte [Políticas de](../../compliance/alert-policies.md)alerta no Centro de conformidade do Microsoft 365 .

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar recursos AIR

As permissões são concedidas por meio de determinadas funções, como as descritas na tabela a seguir:

<br>

****

|Tarefa|Função(s) obrigatório|
|---|---|
|Configurar recursos AIR|Uma das seguintes funções: <ul><li>Administrador global</li><li>Administrador de Segurança</li></ul> <p> Essas funções podem ser [atribuídas](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Azure Active Directory ou no [portal Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)|
|Iniciar uma investigação automatizada <p> ---ou--- <p> Aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas [no](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Azure Active Directory ou no portal de [Microsoft 365 Defender :](permissions-microsoft-365-security-center.md) <ul><li>Administrador global</li><li>Administrador de Segurança</li><li>Operador de segurança</li><li>Leitor de segurança <br> ---e--- </li><li>Pesquisa e limpeza (essa função é atribuída somente no [portal Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md). Talvez seja necessário criar um novo grupo de função **de** & email e adicionar a função De pesquisa e limpeza a esse novo grupo de funções.</li></ul>|

## <a name="required-licenses"></a>Licenças necessárias

[As licenças do Microsoft Defender Office 365 Plano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) devem ser atribuídas a:

- Administradores de segurança (incluindo administradores globais)
- A equipe de operações de segurança da sua organização (incluindo leitores de segurança e aqueles com a **função Pesquisar e Limpar)**
- Usuários finais

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>As alterações estão chegando em breve em seu portal Microsoft 365 Defender portal

Se você já estiver usando recursos air no Microsoft Defender para Office 365, você está prestes a ver algumas alterações no portal Microsoft 365 Defender [aprimorado.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de Ações Unificadas":::

O novo e aprimorado portal Microsoft 365 Defender reúne recursos AIR no [Microsoft Defender](defender-for-office-365.md) para Office 365 e no Microsoft Defender para Ponto [de Extremidade.](../defender-endpoint/automated-investigations.md) Com essas atualizações e melhorias, sua equipe de operações de segurança poderá exibir detalhes sobre investigações automatizadas e ações de remediação em todo o seu email, conteúdo de colaboração, contas de usuário e dispositivos, tudo em um só lugar.

> [!TIP]
> O novo Microsoft 365 Microsoft 365 Defender portal ( <https://security.microsoft.com> ) substitui os seguintes centros:
>
> - Centro de conformidade & segurança ( <https://protection.office.com> )
> - Central de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> )
>
> Além da alteração da URL, há uma nova aparência, projetada para dar à sua equipe de segurança uma experiência mais simplificada, com visibilidade para mais detecções de ameaças em um só lugar.

### <a name="what-to-expect"></a>O que esperar

A tabela a seguir lista as alterações e melhorias que estão chegando ao AIR no Microsoft Defender para Office 365.

<br>

****

|Item|O que está mudando?|
|---|---|
|**Página Investigações**|A página **de Investigações atualizada** é mais consistente com o que você vê no [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations). Você verá algumas alterações gerais de formato e estilo que se alinham ao novo modo de exibição **investigações unificadas.** Por exemplo, o gráfico de investigação tem um formato mais unificado.|
|**Guia Usuários**|A **guia Usuários** agora é a guia Caixas **de** Correio. Os detalhes sobre os usuários estão listados na guia **Caixa de** Correio.|
|**Guia Email**|A **guia Email** foi removida; visite a **guia Entidades** para ver uma lista de itens de cluster de email e email.|
|**Guia Entidades**|A **guia Entidades** tem um estilo tab-in-tab que inclui um exibição de resumo completo e a capacidade de filtrar por tipo de entidade. A **guia Entidades** agora inclui uma **opção Ir** para busca, além da opção Abrir no **Explorer.** Agora você pode usar o [Explorer](threat-explorer.md) ou [a busca avançada](../defender-endpoint/advanced-hunting-overview.md) para encontrar entidades e ameaças e filtrar os resultados.|
|**Guia Ações**|A guia **Ações atualizada** agora inclui uma guia **Ações Pendentes** e uma guia **Histórico de** Ações. As ações podem ser aprovadas (ou rejeitadas) em um painel lateral que é aberto quando você seleciona uma ação pendente.|
|**Guia Evidências**|Uma nova **guia Evidências** mostra as principais descobertas da entidade relacionadas às ações. As ações relacionadas a cada prova podem ser aprovadas (ou rejeitadas) em um painel lateral que é aberto quando você seleciona uma ação pendente.|
|**Central de ações**|O Centro **de Ações** atualizado ( ) reúne ações pendentes e concluídas em <https://security.microsoft.com/action-center> email, dispositivos e identidades. Para saber mais, confira Centro de ações. (Para saber mais, consulte [O Centro de Ações](../defender/m365d-action-center.md).)|
|**Página Incidentes**|A **página Incidentes** agora correlaciona várias investigações para fornecer uma visão melhor consolidada das investigações. ([Saiba mais sobre Incidentes](../defender/incidents-overview.md).)|
|

## <a name="next-steps"></a>Próximas etapas

- [Consulte detalhes e resultados de uma investigação automatizada](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar e aprovar ações pendentes](air-remediation-actions.md)
