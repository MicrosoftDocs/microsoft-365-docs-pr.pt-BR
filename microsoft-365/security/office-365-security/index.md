---
title: Segurança do Office 365, Office 365 ATP, EOP, ATP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Segurança no Office 365, de EOP para planos ATP 1 e 2, configurações de segurança padrão vs. estritos e muito mais, para que você possa entender o que você tem e como proteger suas propriedades.
ms.openlocfilehash: bfce840aa05eaebecc1ec227c6c29bd11cb0a823
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338692"
---
# <a name="office-365-security-overview"></a>Visão geral da segurança do Office 365

Este artigo apresentará as novas propriedades de segurança na nuvem. Se você é parte de um centro de operações de segurança, você é um administrador de segurança novo no espaço ou deseja um atualizador, vamos começar.

> [!CAUTION]
> Oi. Se você estiver usando o **Outlook.com**, a **família do Microsoft 365**ou **o Microsoft 365 Personal**, e precisar de *links seguros* ou informações de *anexos seguros* , ***clique neste link***: [segurança avançada do Outlook.com para assinantes do Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). Muitíssimo!

## <a name="office-365-security-spelled-out"></a>Segurança do Office 365 grafada

Todas as assinaturas do Office 365 vêm com recursos de segurança. As metas e ações que você pode executar dependem do foco dessas diferentes assinaturas. Na segurança do Office 365, há três serviços de segurança principais (ou produtos) associados ao tipo de assinatura:

1. Proteção do Exchange Online (EOP)
1. Proteção avançada contra ameaças, plano 1 (ATP P1)
1. Proteção avançada contra ameaças, plano 2 (ATP P2)

> [!NOTE]
> Se você comprou sua assinatura e precisa distribuir recursos de segurança *agora*, pule para as etapas no artigo [proteger contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) . Se você for novo na sua assinatura e quiser saber sua licença antes de começar, navegue para a cobrança > seus produtos no [centro de administração do Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

A segurança do Office 365 é baseada nas proteções principais oferecidas pelo EOP. O EOP está presente em qualquer assinatura em que as caixas de correio do Exchange Online possam ser encontradas (Lembre-se de que todos os produtos de segurança discutidos aqui são baseados em nuvem).

Você pode estar acostumado a ver esses três componentes discutidos desta forma:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Impede ataques de amplos, baseados em volume e conhecidos.    |  Protege o email e a colaboração contra malware, phishing e emails comerciais de dia zero.       | Adiciona investigação, busca e resposta pós-violação, além de automação e simulação (para treinamento).         |

Mas, em termos de arquitetura, vamos começar pensando em cada parte como camadas cumulativas de segurança, cada uma com uma ênfase de segurança. Mais como:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="Placeholder graphic":::

Embora cada um desses serviços enfatize uma meta específica de entre proteger, detectar, investigar e responder, ***todos*** os serviços podem realizar ***qualquer*** uma das metas de proteção, detecção, investigação e resposta.

O núcleo da segurança do Office 365 é a proteção do EOP. ATP P1 contém EOP. ATP P2 contém P1 e EOP. A estrutura é cumulativa. É por isso que, ao configurar a ATP, você deve começar com o EOP e trabalhar nas camadas.

Embora a configuração de autenticação de email ocorra no DNS público, é importante configurar esse recurso para ajudar a se defender contra falsificação. *Se você tiver o EOP,* ***deverá [Configurar a autenticação de email](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)***.

Se você tiver um Office 365 E3 ou abaixo, você tem o EOP, mas com a opção de comprar a ATP P1 autônomo por meio da atualização. Se você tiver o Office 365 e5, você já tem ATP P2.

> [!TIP]
> Se sua assinatura não for o Office 365 E3 ou e5, ainda será possível verificar se você tem a opção de atualizar para a ATP P1. Se você estiver interessado, [esta página da Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) listará as assinaturas qualificadas para a atualização do ATP P1 (verifique o final da página para impressão fina).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>A escada de segurança do Office 365 de EOP para ATP

<br/>

![EOP e ATP e sua ênfase em segurança, indo de proteger e detectar para investigar e responder.A configuração de autenticação de email (pelo menos DKIM e DMARC) deve ser configurada para o EOP e o up.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)


> [!IMPORTANT]
> Saiba mais sobre os detalhes nessas páginas: [proteção do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview)e [proteção avançada contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp).

O que torna a adição de planos ATP uma vantagem para o gerenciamento de ameaças EOP pode ser difícil de informar à primeira vista. Para ajudar a classificar se um caminho de atualização é ideal para a sua organização, vamos dar uma olhada nos recursos de cada produto, quando se trata de:

 - prevenção e detecção de ameaças
 - investiga
 - atender

a partir do **Exchange Online Protection**:
<p>

|Impedir/detectar  |Investigar  |Responder  |
|---------|---------|---------|
| As tecnologias incluem:<ul><li>spam</li><li>Phish</li><li>software</li><li>email em massa</li><li>inteligência de spoof</li><li>detecção de representação</li><li>Quarentena do administrador</li><li>Envios de administrador e de usuário de falsos positivos e falsos negativos</li><li>Permitir/bloquear URLs e arquivos</li><li>Relatórios</li></u1>|<li>Pesquisa de log de auditoria</li><li>Rastreamento de Mensagem</li>|<li>Limpeza automática de zero horas (ZAP)</li><li>Ajuste e teste de listas de permissões e bloqueios</li>|

Se você quiser se aprofundar no EOP, **[vá para este artigo](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**.

Como esses produtos são cumulativos, se você avaliar ATP P1 e decidir inscrever-se nele, você adicionará essas habilidades.

Ganhos com **proteção avançada contra ameaças, plano 1** (até o momento):
<p>

|Impedir/detectar  |Investigar  |Responder  |
|---------|---------|---------|
| As tecnologias incluem tudo no EOP Plus:<u1><li>Anexos seguros</li><li>Links seguros<li>Proteção ATP para cargas de trabalho (ex. SharePoint Online, Teams, OneDrive for Business)</li><li>Proteção de tempo de clique em email, clientes do Office e equipes</li><li>Anti-phishing ATP</li><li>Proteção de personificação de usuário e domínio</li><li>Alertas e API de integração do SIEM para alertas</li>|<li>API de integração do SIEM para detecções</li><li>**Ferramenta de detecções em tempo real**</li><li>Rastreamento de URL</li>|<li>Idem</li></u1>

Portanto, ATP P1 expande o lado de ***prevenção*** da casa e adiciona formas extras de ***detecção***.

A ATP P1 também adiciona **detecções em tempo real** para investigações. Este nome da ferramenta de busca da ameaça está em negrito porque ter *a certeza de que você tem* a ATP P1. Ele não aparece no ATP P2.

Ganhos com **proteção avançada contra ameaças, plano 2** (até o momento):
<p>

|Impedir/detectar  |Investigar  |Responder  |
|---------|---------|---------|
| As tecnologias incluem tudo no EOP e ATP P1 Plus:<u1><li>Idem</li>|<li>**Explorador de Ameaças**</li><li>Rastreadores de Ameaças</li><li>Modos de exibição de campanha</li>|<li>Investigação e resposta automatizadas (AIR)</li><li>AR do explorador de ameaças</li><li>AR para usuários comprometidos</li><li>API de integração do SIEM para investigações automatizadas</li>

Portanto, ATP P2 expande o lado de ***investigação e resposta*** da casa e adiciona uma nova força de caça. Automação.

Em ATP P2, a ferramenta de busca principal é chamada de **Gerenciador de ameaças** em vez de detecções em tempo real. Se você vir o explorador de ameaças ao navegar até a central de segurança, você está em ATP P2.

Para obter detalhes sobre ATP P1 e P2, **[salte para este artigo](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**.

> [!TIP]
> EOP e ATP também são diferentes quando se trata de usuários finais. No EOP e ATP P1, o foco é a *conscientização*e, portanto, esses dois serviços incluem o *suplemento do Outlook de mensagem de relatório* para que os usuários possam relatar emails que acham suspeitos, para análise adicional. <p> No ATP P2 (que contém tudo no EOP e P1), o foco é deslocado para *mais treinamento* para os usuários finais e, portanto, o centro de operações de segurança tem acesso a uma poderosa ferramenta de *simulador de ameaças* e às métricas de usuário final que ele fornece.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP plano 1 versus plano 2 folha de enganar

Esta referência rápida o ajudará a entender quais recursos vêm com cada assinatura ATP. Quando combinado com seu conhecimento dos recursos do EOP, pode ajudar os tomadores de decisões de negócios a determinar qual ATP é melhor para suas necessidades.

|Plano 1 do Office 365 ATP |Plano 2 do Office 365 ATP|
|---|---|
|<br/>Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](atp-safe-attachments.md)</li><li>[Links Seguros](atp-safe-links.md)</li><li>[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Proteção antiphishing ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Plano 1 do Office 365 ATP <br/>---mais---<br/>Recursos de automação, investigação, correção e formação educacional:</li><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Simulador de Ataque](attack-simulator.md)</li></ul>|
|

- O plano 2 do Office 365 ATP está incluído no Office 365 e5, no Office 365 a5 e no Microsoft 365 e5.

- O Plano 1 do Office 365 ATP está incluído no Microsoft 365 Business Premium.

- A ATP do plano 1 do Office 365 e a ATP do plano 2 do Office 365 estão disponíveis cada uma como um complemento para determinadas assinaturas. Para saber mais, veja outro link [disponibilidade de recursos nos planos ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- O recurso [Documentos Seguros](safe-docs.md) só está disponível para usuários com as licenças de segurança da Microsoft 365 E5 ou do Microsoft 365 E5 Security (não incluída nos planos do Office 365 ATP).

- Se sua assinatura atual não inclui o Office 365 ATP e você deseja, [entre em contato com a venda para iniciar uma avaliação](https://go.microsoft.com/fwlink/p/?LinkId=518644)e descubra como a ATP pode trabalhar em sua organização.

> [!TIP]
> ***Dica de insider***. Você pode usar o Sumário do docs.microsoft.com para saber mais sobre o EOP e a ATP. Navegue até os artigos de [segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) e você notará que a organização do Sumário começa com avaliação e implantação (incluindo a migração) e continua em prevenção, detecção, investigação e resposta. <p> Essa estrutura é dividida para que os tópicos de **Administração de segurança** sejam seguidos por tópicos de **operações de segurança** . Se você for um novo membro de qualquer função de trabalho, use o link nesta dica e seu conhecimento sobre o Sumário para ajudar a aprender o espaço. Lembre-se de usar *links de comentários* e *taxas de artigos* conforme você vai. Feedback nos ajuda a melhorar o que oferecemos a você.

## <a name="where-to-go-next"></a>Onde ir para a próxima

Se você for um administrador de segurança, talvez seja necessário configurar o DKIM ou o DMARC para seu email, distribuir predefinições de segurança "estritas" para seus usuários de prioridade ou você pode estar procurando o que há de novo no produto. Se você estiver usando as operações de segurança, talvez queira aproveitar as detecções em tempo real ou o explorador de ameaças para investigar e responder ou treinar a detecção de usuário final com o simulador de ataques. Veja a seguir algumas recomendações adicionais sobre o que examinar em seguida.

[Autenticação de email, incluindo SPF, DKIM e DMARC (com links para configuração de todos os três)](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication)

[Veja as configurações ' ouro ' específicas recomendadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) e [use suas predefinições recomendadas para configurar rapidamente as políticas de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/preset-security-policies)

Acompanhar [o que há de novo no Office 365 ATP (incluindo desenvolvimentos do EOP)](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

[Usar o Gerenciador de ameaças ou as detecções em tempo real](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)

Usar o [simulador de ataque no Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)