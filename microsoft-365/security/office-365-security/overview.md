---
title: Segurança do Office 365, Microsoft Defender para Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Segurança no Office 365, do EOP aos planos 1 e 2 do Defender para Office 365, Configurações de segurança padrão versus estritas e muito mais. Entenda o que você tem e como proteger suas propriedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: db37718ce2feae9c79ff6b323eb22e30f24e72b2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203073"
---
# <a name="office-365-security-overview"></a>Visão geral da Segurança do Office 365

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)


Este artigo apresentará a você suas novas propriedades de segurança na nuvem. Se você faz parte de um Centro de Operações de Segurança, ou é um Administrador de Segurança novo nesse espaço, ou quer uma atualização, vamos começar.

> [!CAUTION]
> Se você estiver usando **Outlook.com**, **Microsoft 365 Family**, or **Microsoft 365 Personal**, e precisar de informações sobre *Links seguros* ou *Anexos seguros*, ***clique nesse link***: [Segurança avançada do Outlook.com para assinantes do Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Especificações da Segurança do Office 365

Todas as assinaturas do Office 365 vêm com recursos de segurança. As metas e ações que você pode tomar dependem do foco dessas assinaturas diferentes. Na Segurança do Office 365, há três serviços de segurança (ou produtos) principais vinculados ao seu tipo de assinatura:

1. Proteção do Exchange Online (EOP)
1. O Microsoft Defender para Office 365 Plano 1 (Defender para Office P1)
1. Microsoft Defender para Office 365 Plano 2 (Defender para Office P2)

> [!NOTE]
> Se você comprou sua assinatura e precisa lançar os recursos de segurança *agora*, pule para as etapas no artigo [Proteção contra ameaças](protect-against-threats.md). Se você ainda não conhece a sua assinatura e quer conhecer sua licença antes de começar, vá para Cobrança > Seus Produtos no [Centro de administração do Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

A Segurança do Office 365 se baseia nas principais proteções oferecidas pelo EOP. O EOP está presente em qualquer assinatura onde as caixas de correio do Exchange Online podem ser encontradas (lembre-se, todos os produtos de segurança discutidos aqui são baseados em nuvem).

Você pode estar acostumado a ver esses três componentes discutidos dessa maneira:

|EOP|P1 do Microsoft Defender para Office 365|P2 do Microsoft Defender para Office 365|
|---|---|---|
|Evita ataques conhecidos, amplos, e baseados em volume.|Protege o email e a colaboração contra malware do dia zero, phishing e email empresarial comprometido.|Adiciona investigação pós-violação, busca, e resposta, além de automação e simulação (para treinamento).|
|

Mas, em termos de arquitetura, vamos começar pensando em cada parte como camadas cumulativas de segurança, cada uma com ênfase de segurança. Assim:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP e Microsoft Defender para Office 365 e suas relações entre si com ênfase de serviço, incluindo uma anotação para autenticação de email.":::

Embora cada um desses serviços enfatizam uma meta entre Proteger, Detectar, Investigar e Responder, ***todos** _ os serviços podem executar _ *_qualquer_** dos objetivos de proteção, detecção, investigação e resposta.

A base da segurança do Office 365 é a proteção EOP. O P1 do Microsoft Defender para Office 365 contém EOP. O P2 do Defender para Office 365 contém P1 e EOP. A estrutura é cumulativa. É por isso que, ao configurar esse produto, você deve começar com o EOP chegar no Defender para Office 365.

Embora a configuração de autenticação de email ocorra no DNS público, é importante configurar esse recurso para ajudar a defender contra a falsificação. *Se tiver o EOP,* ***você deverá configurar a [autenticação de email](email-validation-and-authentication.md)***.

Se você tem um Office 365 E3 ou versão inferior, você tem o EOP, mas com a opção de comprar o P1 do Defender para o Office 365 autônomo por meio da atualização. Se você tem o Office 365 E5, já tem o P2 do Defender para Office 365.

> [!TIP]
> Se sua assinatura não for o Office 365 E3 ou E5, você ainda poderá verificar se tem a opção de atualizar para o P1 do Microsoft Defender para Office 365. Se estiver interessado, essa[página da Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) lista as assinaturas qualificadas para a atualização do Microsoft Defender para Office 365 P1 (confira o final da página para as informações completas).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>A hierarquia de segurança do Office 365 do EOP até o Microsoft Defender para Office 365

![O EOP e Microsoft Defender para Office 365 e suas ênfases em segurança, de Proteger e Detectar à Investigar e Responder. A configuração de autenticação de email (pelo menos DKIM e DMARC) deve estar configurada para EOP e superior.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Saiba os detalhes nessas páginas: [Proteção do Exchange Online](exchange-online-protection-overview.md)e [Defender para Office 365](defender-for-office-365.md).

O que torna a adição de planos do Microsoft Defender para Office 365 uma vantagem ao gerenciamento puro de ameaças do EOP pode ser difícil de dizer à primeira vista. Para ajudar a descobrir se um caminho de atualização é necessário para a sua organização, vamos ver os recursos de cada produto quando se trata de:

- impedir e detectar ameaças
- investigar
- responder

Começando com a **Proteção do Exchange Online**:
<p>

|Prevenir/Detectar|Investigar|Responder|
|---|---|---|
|Tecnologias incluem:<ul><li>spam</li><li>phishing</li><li>malware</li><li>email em massa</li><li>inteligência contra falsificação</li><li>detecção de usurpação de identidade</li><li>Quarentena de administrador</li><li>Envios de administrador e usuário de Falsos Positivos e Falsos Negativos</li><li>Permitir/Bloquear para URLs e arquivos</li><li>Relatórios</li></u1>|<li>Pesquisa de log de auditoria</li><li>Rastreamento de Mensagem</li>|<li>Limpeza Automática Zero Hora</li><li>Refinamento e teste de listas de Permitir e Bloquear</li>|
|

Se você quiser saber mais sobre o EOP, **[pule para esse artigo](exchange-online-protection-overview.md)**.

Como esses produtos são cumulativos, se você avaliar o P1 do Microsoft Defender para Office 365 e decidir inscrever-se nele, adicionará essas capacidades.

Vantagens com o **Microsoft Defender para Office 365 Plano 1** (até hoje):
<p>

|Prevenir/Detectar|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP, mais:<u1><li>Anexos seguros</li><li>Links seguros<li>Proteção do Microsoft Defender para Office 365 para cargas de trabalho (por exemplo, SharePoint Online, Teams, e OneDrive for Business</li><li>Proteção no momento do clique no email, nos clientes do Office e no Teams</li><li>anti-phishing no Defender para Office 365</li><li>Proteção de representação de usuário e domínio</li><li>Alertas e API de integração do SIEM para alertas</li>|<li>API de integração do SIEM para detecções</li><li>**Ferramenta de detecções em tempo real**</li><li>rastreamento de URL</li>|<li>Mesmo</li></u1>

Portanto, o P1 do Microsoft Defender para Office 365 expande a ***prevenção** _ da casa e adiciona formas adicionais de _detecção_**.

O P1 do Microsoft Defender para Office 365 também adiciona **detecções em tempo real** para as investigações. O nome da ferramenta de ameaças está em negrito porque tê-la é uma forma clara de *saber* que você tem o P1 do Defender para Office 365. Ele não aparece no P2 do Defender para Office 365.

Vantagens com o **Defender para Office 365 Plano 2** (até hoje):
<p>

|Prevenir/Detectar|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP e no P1 do Microsoft Defender para Office 365, mais:<u1><li>Mesmo</li>|<li>**Explorador de Ameaças**</li><li>Rastreadores de Ameaças</li><li>Exibição de campanha</li>|<li>Investigação e resposta automatizadas (AIR)</li><li>AIR do Explorador de Ameaças</li><li>AIR para usuários comprometidos</li><li>API de integração do SIEM para investigações automatizadas</li>

Portanto, o P2 do Microsoft Defender para Office 365 expande a ***investigação e a resposta*** ao lado da casa e adiciona uma nova força de busca. Automação.

No P2 do Microsoft Defender para Office 365 P2, a ferramenta de busca principal é chamada **Explorador de ameaças** em vez de detecções em tempo real. Se vir o Explorador de Ameaças ao navegar até o Centro de Segurança, você está no P2 do Microsoft Defender para Office 365.

Para ver os detalhes do P1 e P2 do Microsoft Defender para Office 365, **[pule para esse artigo](defender-for-office-365.md)**.

> [!TIP]
> O EOP e o Microsoft Defender para Office 365 também são diferentes quando se trata de usuários finais. No EOP e no P1 do Defender para Office 365, o foco é *reconhecimento* e, portanto, esses dois serviços incluem o *complemento Reportar mensagem do Outlook* para que os usuários possam relatar emails que acham suspeitos, para análise posterior. <p> No P2 do Defender para Office 365 (que contém tudo no EOP e P1), o foco muda para um *treinamento mais profundo* para usuários finais e, portanto, o Centro de Operações de Segurança tem acesso a uma poderosa ferramenta de *Simulador de ameaças* e às métricas do usuário final que ele fornece.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Folha de referências do Microsoft Defender para Office 365 Plano 1 versus Plano 2

Esta referência rápida ajudará você a entender quais recursos vêm com cada assinatura do Microsoft Defender para Office 365. Quando combinada com seu conhecimento dos recursos do EOP, ela pode ajudar os tomadores de decisões de negócios a determinar qual Microsoft Defender para Office 365 é melhor para as suas necessidades.

|Microsoft Defender para Office 365 Plano 1|Microsoft Defender para Office 365 Plano 2|
|---|---|
|Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](safe-attachments.md)</li><li>[Links Seguros](safe-links.md)</li><li>[Anexos seguros para SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Proteção anti-phishing no Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Microsoft Defender para Office 365 Plano 1 <p> ---mais--- <p> Recursos de automação, investigação, correção e formação educacional: <ul><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](office-365-air.md)</li><li>[Simulador de Ataque](attack-simulator.md)</li></ul>|
|

- O Microsoft Defender para Office 365 Plano 2 está incluído no Office 365 E5, Office 365 A5, e no Microsoft 365 E5.

- O Microsoft Defender para Office 365 Plano 1 está incluído no Microsoft 365 Business Premium.

- O Microsoft Defender para Office 365 Plano 1 e o Microsoft Defender para Office 365 Plano 2 estão disponíveis como complemento para certas assinaturas. Para saber mais, aqui vai mais um link [Disponibilidade de recursos nos planos do Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- O recurso [Documentos Seguros](safe-docs.md) está disponível apenas para usuários com as licenças Microsoft 365 E5 ou Microsoft 365 E5 Security (não incluídas nos planos Microsoft Defender para Office 365).

- Se sua assinatura atual não inclui o Microsoft Defender para Office 365 e o deseja, [entre em contato com a equipe de vendas para iniciar uma avaliação](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) e descubra como o Defender para Office 365 pode funcionar para sua organização.

> [!TIP]
> ***Dicas** _. Você pode usar o sumário do docs.microsoft.com para saber mais sobre o EOP e o Microsoft Defender para Office 365. Navegue novamente para a página [Visão geral da Segurança do Office 365](index.yml)e você verá o sumário na barra lateral. Ele começa com a Implantação (incluindo a migração) e continua com prevenção, detecção, investigação e resposta. <p> Essa estrutura é dividida para que os tópicos da _ *Administração de Segurança** sejam seguidos por tópicos sobre **Operações de Segurança**. Se você for um novo membro de uma dessas funções de trabalho, use o link nessa dica e seu conhecimento do sumário para ajudar a conhecer esse ambiente. Lembre-se de usar *links de comentários* e *avalie os artigos* à medida que você vai avante. Os comentários nos ajudam a melhorar o que oferecemos a você.

## <a name="where-to-go-next"></a>Para onde ir

Se você for um Administrador de Segurança, talvez seja necessário configurar o DKIM ou o DMARC para seu email. Você pode querer lançar predefinições de segurança 'Estritas' para os usuários de prioridade ou saber o que há de novo no produto. Ou, se você estiver em Operações de Segurança, talvez queira aproveitar as Detecções em tempo real ou o Explorador de ameaças para investigar e responder, ou treinar a detecção de usuário final com o Simulador de ataque. De qualquer forma, aqui estão algumas recomendações adicionais para o que vier em seguida.

[Autenticação de email, incluindo SPF, DKIM e DMARC (com links para a configuração dos três)](email-validation-and-authentication.md)

[Veja as configurações de 'ouro' recomendadas](recommended-settings-for-eop-and-office365.md) e [use suas predefinições para configurar políticas de segurança rapidamente](preset-security-policies.md)

Mantenha-se informado sobre [as novidades do Microsoft Defender para Office 365 (incluindo os desenvolvimentos do EOP)](whats-new-in-defender-for-office-365.md)

[Use o Explorador de ameaças ou Detecções em tempo real](threat-explorer.md)

Use o [Simulador de ataques no Microsoft Defender para Office 365](attack-simulator.md).