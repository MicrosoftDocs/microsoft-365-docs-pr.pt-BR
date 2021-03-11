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
description: Segurança no Office 365, do EOP ao Defender for Office 365 Planos 1 e 2, Configurações de segurança padrão vs. Estritas e muito mais. Entenda o que você tem e como proteger suas propriedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711935"
---
# <a name="office-365-security-overview"></a>Visão geral de segurança do Office 365

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)


Este artigo apresentará suas novas propriedades de segurança na Nuvem. Se você faz parte de um Centro de Operações de Segurança, é um Administrador de Segurança novo no espaço ou quer uma atualização, vamos começar.

> [!CAUTION]
> Se você estiver usando **o Outlook.com**, a Família do **Microsoft 365** ou o **Microsoft 365 Pessoal** e precisar de informações de *Links* Seguros ou *Anexos* Seguros, clique neste ***link***: Segurança avançada Outlook.com para assinantes do [Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Segurança do Office 365 escrita fora

Cada assinatura do Office 365 vem com recursos de segurança. As metas e ações que você pode tomar dependem do foco dessas assinaturas diferentes. Na segurança do Office 365, há três serviços de segurança (ou produtos) principais vinculados ao tipo de assinatura:

1. Proteção do Exchange Online (EOP)
1. Microsoft Defender para Office 365 Plano 1 (Defender para Office P1)
1. Microsoft Defender para Office 365 Plano 2 (Defender para Office P2)

> [!NOTE]
> Se você comprou sua assinatura e precisa lançar recursos de segurança *agora,* pule para as etapas no [artigo Proteger Contra Ameaças.](protect-against-threats.md) Se você é novo em sua assinatura e gostaria de saber sua licença antes de começar, navegue por Cobrança > Seus Produtos no centro de administração [do Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

A segurança do Office 365 se baseia nas principais proteções oferecidas pelo EOP. O EOP está presente em qualquer assinatura em que as caixas de correio do Exchange Online podem ser encontradas (lembre-se de que todos os produtos de segurança discutidos aqui são baseados em nuvem).

Você pode estar acostumado a ver esses três componentes discutidos desta maneira:

|EOP|Microsoft Defender para Office 365 P1|Microsoft Defender para Office 365 P2|
|---|---|---|
|Impede ataques amplos, baseados em volume e conhecidos.|Protege o email e a colaboração contra o comprometimento de malware, phishing e email comercial de dia zero.|Adiciona investigação, busca e resposta pós-violação, bem como automação e simulação (para treinamento).|
|

Mas, em termos de arquitetura, vamos começar pensando em cada peça como camadas cumulativas de segurança, cada uma com ênfase em segurança. Mais ou mais assim:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP e Microsoft Defender para Office 365 e suas relações entre si com ênfase no serviço, incluindo uma observação para autenticação de email.":::

Embora cada um desses serviços enfatiza uma meta entre Proteger, Detectar, Investigar e Responder,***** todos _ os serviços podem realizar *___* qualquer * das metas de proteção, detecção, investigação e resposta.

O núcleo da segurança do Office 365 é a proteção EOP. O Microsoft Defender para Office 365 P1 contém o EOP nele. O Defender para Office 365 P2 contém P1 e EOP. A estrutura é cumulativa. Por isso, ao configurar esse produto, você deve começar com o EOP e trabalhar com o Defender para Office 365.

Embora a configuração de autenticação de email tenha lugar no DNS público, é importante configurar esse recurso para ajudar a se defender contra a spoofing. *Se você tiver EOP,* ***configure a [autenticação de email](email-validation-and-authentication.md)***.

Se você tiver um Office 365 E3 ou abaixo, terá o EOP, mas com a opção de comprar o Defender autônomo para o Office 365 P1 por meio da atualização. Se você tiver o Office 365 E5, já terá o Defender para Office 365 P2.

> [!TIP]
> Se sua assinatura não for do Office 365 E3 ou E5, você ainda poderá verificar se tem a opção de atualizar para o Microsoft Defender para o Office 365 P1. Se você estiver interessado, esta página da [Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) lista as assinaturas qualificadas para a atualização do Microsoft Defender para Office 365 P1 (verifique o final da página para a impressão fina).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>A escala de segurança do Office 365 do EOP para o Microsoft Defender para o Office 365

![EOP e Microsoft Defender para Office 365 e sua ênfase de segurança, indo de Proteger e Detectar para Investigar e Responder. A configuração de Autenticação de Email (pelo menos DKIM e DMARC) deve ser configurada para EOP e para cima.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Saiba os detalhes nessas páginas: [Proteção do Exchange Online](exchange-online-protection-overview.md)e Defender para Office [365](office-365-atp.md).

O que torna a adição de planos do Microsoft Defender para Office 365 uma vantagem para o gerenciamento puro de ameaças do EOP pode ser difícil de dizer à primeira vista. Para ajudar a classificar se um caminho de atualização é o correto para sua organização, vamos ver os recursos de cada produto quando se trata de:

- prevenção e detecção de ameaças
- investigando
- responding

começando com **a Proteção do Exchange Online**:
<p>

|Prevent/Detect|Investigar|Responder|
|---|---|---|
|As tecnologias incluem:<ul><li>spam</li><li>phish</li><li>malware</li><li>bulk mail</li><li>spoof intelligence</li><li>detecção de representação</li><li>Quarentena de administrador</li><li>Envios de administrador e usuário de Falsos Positivos e Falsos Negativos</li><li>Permitir/bloquear URLs e arquivos</li><li>Relatórios</li></u1>|<li>Pesquisa de log de auditoria</li><li>Rastreamento de Mensagem</li>|<li>Limpeza automática zero hora (ZAP)</li><li>Refinamento e teste de listas Permitir e Bloquear</li>|
|

Se você quiser entrar no EOP, **[pule para este artigo](exchange-online-protection-overview.md)**.

Como esses produtos são cumulativos, se você avaliar o Microsoft Defender para o Office 365 P1 e decidir se inscrever nele, você adicionará essas habilidades.

Ganhos **com o Defender para Office 365, Plano 1** (até o momento):
<p>

|Prevent/Detect|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP mais:<u1><li>Anexos seguros</li><li>Links seguros<li>Proteção do Microsoft Defender para Office 365 para cargas de trabalho (ex. SharePoint Online, Teams, OneDrive for Business)</li><li>Proteção de hora em clique no email, clientes do Office e no Teams</li><li>anti-phishing no Defender para Office 365</li><li>Proteção de representação de usuário e domínio</li><li>Alertas e API de integração do SIEM para alertas</li>|<li>API de integração siem para detecções</li><li>**Ferramenta de detecções em tempo real**</li><li>Rastreamento de URL</li>|<li>Idem</li></u1>

Portanto, o Microsoft Defender para Office 365 P1 se expande no ***prevention** _ side da casa e adiciona formas extras de detecção __*_**.

O Microsoft Defender para Office 365 P1 também adiciona detecções em tempo **real** para investigações. O nome dessa ferramenta de busca de ameaças está  em negrito porque, tendo isso, é claro como saber que você tem o Defender para o Office 365 P1. Ele não aparece no Defender para Office 365 P2.

Ganhos **com o Defender para Office 365, Plano 2** (até o momento):
<p>

|Prevent/Detect|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP e o Microsoft Defender para Office 365 P1 mais:<u1><li>Idem</li>|<li>**Explorador de Ameaças**</li><li>Rastreadores de Ameaças</li><li>Exibições de campanha</li>|<li>Investigação e Resposta Automatizadas (AIR)</li><li>AIR do Explorador de Ameaças</li><li>AIR para usuários comprometidos</li><li>API de integração siem para investigações automatizadas</li>

Portanto, o Microsoft Defender para Office 365 P2 se expande no lado de investigação e resposta da casa e adiciona uma nova força de busca.  Automação.

No Microsoft Defender para Office 365 P2, a ferramenta de busca principal é chamada **de Explorador** de Ameaças, em vez de detecções em tempo real. Se você vir o Explorador de Ameaças ao navegar até o Centro de Segurança, você está no Microsoft Defender para Office 365 P2.

Para entrar nos detalhes do Microsoft Defender para Office 365 P1 e P2, **[vá para este artigo](office-365-atp.md)**.

> [!TIP]
> O EOP e o Microsoft Defender para Office 365 também são diferentes quando se trata de usuários finais. No EOP e no Defender para o Office 365 P1, o foco é a conscientização *e,* portanto, esses dois serviços incluem o complemento Relatório de mensagem do *Outlook* para que os usuários possam relatar emails que eles encontrem suspeitos, para análise mais detalhada. <p> No Defender for Office 365 P2 (que contém tudo no EOP e no P1), o foco muda para o treinamento para os usuários finais e, portanto, o Centro de Operações de Segurança tem acesso a uma poderosa ferramenta *simulador* de ameaças e as métricas do usuário final que ele fornece. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Planilha de fraude do Microsoft Defender para Office 365 Plano 1 vs. Plano 2

Essa referência rápida ajudará você a entender quais recursos vêm com cada assinatura do Microsoft Defender para Office 365. Quando combinado com seu conhecimento dos recursos do EOP, ele pode ajudar os tomadores de decisão dos negócios a determinar o que o Microsoft Defender para Office 365 é melhor para suas necessidades.

|Defender para Office 365 Plano 1|Defender para Office 365 Plano 2|
|---|---|
|Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](atp-safe-attachments.md)</li><li>[Links Seguros](atp-safe-links.md)</li><li>[Anexos seguros para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Proteção anti-phishing no Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Defender para o Plano 1 do Office 365 <p> ---mais--- <p> Recursos de automação, investigação, correção e formação educacional: <ul><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](office-365-air.md)</li><li>[Simulador de Ataque](attack-simulator.md)</li></ul>|
|

- O Microsoft Defender para Office 365 Plano 2 está incluído no Office 365 E5, no Office 365 A5 e no Microsoft 365 E5.

- O Microsoft Defender para Office 365 Plano 1 está incluído no Microsoft 365 Business Premium.

- O Microsoft Defender para Office 365 Plano 1 e o Defender para Office 365 Plano 2 estão disponíveis como complemento para determinadas assinaturas. Para saber mais, aqui está outro link Disponibilidade de recursos em [planos do Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- O recurso [Documentos Seguros](safe-docs.md) está disponível apenas para usuários com as licenças Microsoft 365 E5 ou Microsoft 365 E5 Security (não incluídas nos planos Microsoft Defender para Office 365).

- Se [sua](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)assinatura atual não incluir o Microsoft Defender para Office 365 e você quiser, contate as vendas para iniciar uma avaliação e descubra como o Microsoft Defender para Office 365 pode funcionar em sua organização.

> [!TIP]
> ***Dica de insider** _. Você pode usar o docs.microsoft.com de conteúdo para saber mais sobre o EOP e o Microsoft Defender para Office 365. Navegue até esta página, Visão geral de segurança do [Office 365](index.md)e você notará que a organização do conteúdo está na barra lateral. Ele começa com a Implantação (incluindo a migração) e continua na prevenção, detecção, investigação e resposta. <p> Essa estrutura é dividida para que os tópicos _ Administração de *Segurança** sejam seguidos por tópicos **de Operações** de Segurança. Se você for um novo membro de uma das funções de trabalho, use o link nesta dica e seu conhecimento do conteúdo para ajudar a aprender o espaço. Lembre-se de usar *links de comentários* e artigos de *taxa* conforme você vai. Comentários nos ajudam a melhorar o que oferecemos a você.

## <a name="where-to-go-next"></a>Onde ir em seguida

Se você for um Administrador de Segurança, talvez seja necessário configurar dKIM ou DMARC para seu email. Você pode querer lançar predefinições de segurança 'Estritas' para seus usuários prioritários ou procurar novidades no produto. Ou se você estiver com Operações de Segurança, talvez queira aproveitar as detecções em tempo real ou o Explorador de Ameaças para investigar e responder, ou treinar a detecção do usuário final com o Simulador de Ataques. De qualquer forma, aqui estão algumas recomendações adicionais sobre o que procurar em seguida.

[Autenticação de Email, incluindo SPF, DKIM e DMARC (com links para a instalação dos três)](email-validation-and-authentication.md)

[Consulte as configs "ouro" recomendadas específicas](recommended-settings-for-eop-and-office365-atp.md) e [use suas predefinições recomendadas para configurar políticas de segurança rapidamente](preset-security-policies.md)

Acompanhar as [novidades do Microsoft Defender para Office 365 (incluindo desenvolvimentos do EOP)](whats-new-in-office-365-atp.md)

[Usar o Explorador de Ameaças ou detecções em tempo real](threat-explorer.md)

Usar [o Simulador de Ataque no Microsoft Defender para Office 365](attack-simulator.md)
