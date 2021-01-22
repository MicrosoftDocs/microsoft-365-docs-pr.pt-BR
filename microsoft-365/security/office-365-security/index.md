---
title: Segurança do Office 365, Microsoft Defender para Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Segurança no Office 365, do EOP para o Defender para Planos 1 e 2 do Office 365, Configurações de segurança Padrão versus Estritas e muito mais. Entenda o que você tem e como proteger suas propriedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f83eef6a19e26f4b8f47a049e2b2959b32a92550
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932545"
---
# <a name="office-365-security-overview"></a>Visão geral de segurança do Office 365

Este artigo apresentará as novas propriedades de segurança na nuvem. Seja você parte de um Centro de Operações de Segurança, você é um Administrador de Segurança novo no espaço ou quer uma atualização, vamos começar.

> [!CAUTION]
> Se você estiver usando o **Outlook.com,** o **Microsoft 365 Family** ou o  **Microsoft 365 Personal** e precisar de informações sobre Links seguros ou *anexos* seguros, * clique neste **link** _: segurança avançada do Outlook.com para assinantes do [Microsoft 365.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)

## <a name="office-365-security-spelled-out"></a>Office 365 security spelled out

Cada assinatura do Office 365 vem com recursos de segurança. As metas e ações que você pode tomar dependem do foco dessas assinaturas diferentes. Na segurança do Office 365, há três serviços de segurança principais (ou produtos) vinculados ao seu tipo de assinatura:

1. Proteção do Exchange Online (EOP)
1. Microsoft Defender para Office 365 Plano 1 (Defender para Office P1)
1. Microsoft Defender para Office 365 Plano 2 (Defender para Office P2)

> [!NOTE]
> Se você comprou sua assinatura e precisa lançar recursos de segurança _right agora*, pule para as etapas no artigo Proteção [contra Ameaças.](protect-against-threats.md) Se você for novo em sua assinatura e quiser saber sua licença antes de começar, navegue > Seus Produtos no centro de administração do [Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

A segurança do Office 365 se baseia nas proteções principais oferecidas pelo EOP. O EOP está presente em qualquer assinatura onde as caixas de correio do Exchange Online podem ser encontradas (lembre-se de que todos os produtos de segurança discutidos aqui são baseados em nuvem).

Você pode estar acostumado a ver esses três componentes discutidos dessa maneira:

|EOP|Microsoft Defender para Office 365 P1|Microsoft Defender para Office 365 P2|
|---|---|---|
|Impede ataques conhecidos amplos baseados em volume.|Protege o email e a colaboração contra o comprometimento de malware, phishing e email comercial do dia zero.|Adiciona investigação, busca e resposta pós-violação, bem como automação e simulação (para treinamento).|
|

Mas, em termos de arquitetura, vamos começar pensando em cada parte como camadas cumulativas de segurança, cada uma com ênfase na segurança. Mais ou mais parecido com isto:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="O EOP e o Microsoft Defender para Office 365 e suas relações entre si com ênfase no serviço, incluindo uma observação para autenticação de email.":::

Embora cada um desses serviços enfatiza uma meta entre Proteger, Detectar, Investigar _**_ e Responder,***** todos os serviços podem cumprir qualquer um dos objetivos de proteção, detecção, investigação e resposta.

O núcleo da segurança do Office 365 é a proteção do EOP. O Microsoft Defender para Office 365 P1 contém o EOP. O Defender para Office 365 P2 contém P1 e EOP. A estrutura é cumulativa. É por isso que, ao configurar este produto, você deve começar com o EOP e trabalhar com o Defender para Office 365.

Embora a configuração de autenticação de email ocorre no DNS público, é importante configurar esse recurso para ajudar a se defender contra a spoofing. _Se você tiver o EOP,* * você **deve configurar a [autenticação de email.](email-validation-and-authentication.md)**_

Se você tiver um Office 365 E3 ou abaixo, terá o EOP, mas com a opção de comprar o Defender autônomo para Office 365 P1 por meio da atualização. Se você tiver o Office 365 E5, já tem o Defender para Office 365 P2.

> [!TIP]
> Se sua assinatura não for do Office 365 E3 ou E5, você ainda poderá verificar se tem a opção de atualizar para o Microsoft Defender para Office 365 P1. Se você estiver [interessado,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) esta página da Web lista as assinaturas qualificadas para a atualização do Microsoft Defender para Office 365 P1 (verifique o final da página para a impressão impressa).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>A segurança do Office 365 foi de EOP para o Microsoft Defender para Office 365

![EOP e Microsoft Defender para Office 365 e sua ênfase em segurança, indo de Proteger e Detectar para Investigar e Responder. A configuração de Autenticação de Email (pelo menos DKIM e DMARC) deve ser configurada para e para o EOP.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Saiba os detalhes nestas páginas: [Proteção do Exchange Online](exchange-online-protection-overview.md)e Defender para Office [365.](office-365-atp.md)

O que torna a adição de planos do Microsoft Defender para Office 365 uma vantagem do gerenciamento puro de ameaças do EOP pode ser difícil de saber rapidamente. Para ajudar a classificar se um caminho de atualização é o certo para sua organização, vamos ver os recursos de cada produto quando se trata de:

- evitando e detectando ameaças
- investigando
- responder

começando com _*Proteção do Exchange Online**:
<p>

|Impedir/Detectar|Investigar|Responder|
|---|---|---|
|As tecnologias incluem:<ul><li>spam</li><li>phish</li><li>malware</li><li>email em massa</li><li>inteligência contra spoof</li><li>detecção de representação</li><li>Quarentena de Administrador</li><li>Envios de Administrador e usuário de Falsos Positivos e Falsos Negativos</li><li>Permitir/bloquear URLs e arquivos</li><li>Relatórios</li></u1>|<li>Pesquisa de log de auditoria</li><li>Rastreamento de Mensagem</li>|<li>ZAP (Limpeza Automática Zero Hora)</li><li>Refinamento e teste de listas de permitir e bloquear</li>|
|

Se você quiser se aprofundar no EOP, **[pule para este artigo.](exchange-online-protection-overview.md)**

Como esses produtos são cumulativos, se você avaliar o Microsoft Defender para Office 365 P1 e decidir se inscrever nele, você adicionará essas capacidades.

Ganhos **com o Defender para Office 365, Plano 1** (até o momento):
<p>

|Impedir/Detectar|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP, além de:<u1><li>Anexos seguros</li><li>Links seguros<li>Proteção do Microsoft Defender para Office 365 para cargas de trabalho (ex. SharePoint Online, Teams, OneDrive for Business)</li><li>Proteção de hora de clique em email, clientes do Office e Teams</li><li>anti-phishing no Defender para Office 365</li><li>Proteção contra representação de usuário e domínio</li><li>Alertas e API de integração SIEM para alertas</li>|<li>API de integração SIEM para detecções</li><li>**Ferramenta de detecções em tempo real**</li><li>Rastreamento de URL</li>|<li>Idem</li></u1>

Portanto, o Microsoft Defender para Office 365 P1 se expande no lado **_prevention_* _ da casa e adiciona formas extras de _*_detecção._*_

O Microsoft Defender para Office 365 P1 também adiciona *detecções* em tempo real * para investigações. O nome dessa ferramenta de busca de ameaças está  em negrito porque é claro como saber que você tem o Defender para Office 365 P1. Ele não aparece no Defender para Office 365 P2.

Ganhos **com o Defender para Office 365, Plano 2** (até o momento):
<p>

|Impedir/Detectar|Investigar|Responder|
|---|---|---|
|As tecnologias incluem tudo no EOP e no Microsoft Defender para Office 365 P1, além de:<u1><li>Idem</li>|<li>**Explorador de Ameaças**</li><li>Rastreadores de Ameaças</li><li>Exibições de campanha</li>|<li>Investigação e resposta automatizadas (AIR)</li><li>AIR do Explorador de Ameaças</li><li>AIR para usuários comprometidos</li><li>API de integração SIEM para investigações automatizadas</li>

Portanto, o Microsoft Defender para Office 365 P2 expande o lado **_investigação_* e resposta _ da casa e adiciona um novo poder de busca. Automação.

No Microsoft Defender para Office 365 P2, a ferramenta de busca principal é chamada _ *Explorador* de Ameaças * em vez de detecções em tempo real. Se você vir o Explorador de Ameaças ao navegar para a Central de Segurança, você está no Microsoft Defender para Office 365 P2.

Para entrar em detalhes do Microsoft Defender para Office 365 P1 e P2, **[vá para este artigo.](office-365-atp.md)**

> [!TIP]
> O EOP e o Microsoft Defender para Office 365 também são diferentes quando se trata de usuários finais. No EOP e no Defender para Office 365 P1, o foco é o reconhecimento e, portanto, esses dois serviços incluem o complemento Relatar mensagem do *Outlook* para que os usuários possam relatar emails que eles acham suspeitos para análise posterior.  <p> No Defender para Office 365 P2 (que contém tudo no EOP e no P1), o foco muda para  o treinamento para usuários finais e, portanto, o Centro de Operações de Segurança tem acesso a uma poderosa ferramenta simulador de ameaças e as métricas do usuário final que ele fornece. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 Plano 1 versus Planilha de fraude do Plano 2

Essa referência rápida ajudará você a entender quais recursos vêm com cada assinatura do Microsoft Defender para Office 365. Quando combinado com seu conhecimento dos recursos do EOP, ele pode ajudar os tomadores de decisão de negócios a determinar qual o Microsoft Defender para Office 365 é melhor para suas necessidades.

|Defender para Office 365 Plano 1|Defender para Office 365 Plano 2|
|---|---|
|Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](atp-safe-attachments.md)</li><li>[Links Seguros](atp-safe-links.md)</li><li>[Anexos seguros para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Proteção anti-phishing no Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Defender para Office 365 Plano 1 <p> ---mais--- <p> Recursos de automação, investigação, correção e formação educacional: <ul><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](office-365-air.md)</li><li>[Simulador de Ataque](attack-simulator.md)</li></ul>|
|

- O Microsoft Defender para Office 365 Plano 2 está incluído no Office 365 E5, office 365 A5 e Microsoft 365 E5.

- O Microsoft Defender para Office 365 Plano 1 está incluído no Microsoft 365 Business Premium.

- O Microsoft Defender para Office 365 Plano 1 e o Defender para Office 365 Plano 2 estão disponíveis como um complemento para determinadas assinaturas. Para saber mais, aqui está outro link de disponibilidade [de recursos no Microsoft Defender para planos do Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- O recurso [Documentos Seguros](safe-docs.md) está disponível apenas para usuários com as licenças Microsoft 365 E5 ou Microsoft 365 E5 Security (não incluídas nos planos Microsoft Defender para Office 365).

- Se [sua](https://go.microsoft.com/fwlink/p/?LinkId=518644)assinatura atual não incluir o Microsoft Defender para Office 365 e você quiser, entre em contato com as vendas para iniciar uma avaliação e descubra como o Microsoft Defender para Office 365 pode funcionar em sua organização.

> [!TIP]
> ***Dica do Insider** _. Você pode usar o docs.microsoft.com de conteúdo para saber mais sobre o EOP e o Microsoft Defender para Office 365. Navegue de volta para esta página, visão geral de segurança do [Office 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security)e você notará que a organização do índice na barra lateral. Ele começa com a implantação (incluindo a migração) e, em seguida, continua na prevenção, detecção, investigação e resposta. <p> Essa estrutura é dividida para que os tópicos _ *Administração* de Segurança * sejam seguidos **por tópicos operações** de segurança. Se você for um novo membro de qualquer uma das funções de trabalho, use o link nesta dica e seu conhecimento do índice para ajudar a aprender o espaço. Lembre-se de *usar links de comentários* e *ratear* artigos conforme você vai. Os comentários nos ajudam a melhorar o que oferecemos a você.

## <a name="where-to-go-next"></a>Para onde ir em seguida

Se você for um Administrador de Segurança, talvez seja necessário configurar o DKIM ou o DMARC para seu email. Talvez você queira lançar predefinições de segurança "Estritas" para seus usuários prioritários ou procurar as novidades no produto. Ou, se você estiver com operações de segurança, talvez queira aproveitar as detecções em tempo real ou o Explorador de Ameaças para investigar e responder, ou treinar a detecção do usuário final com o Simulador de Ataque. De qualquer forma, aqui estão algumas recomendações adicionais sobre o que procurar em seguida.

[Autenticação de email, incluindo SPF, DKIM e DMARC (com links para a configuração de todos os três)](email-validation-and-authentication.md)

[Consulte as configurações específicas "ouro" recomendadas](recommended-settings-for-eop-and-office365-atp.md) e [use suas predefinições recomendadas para configurar políticas de segurança rapidamente](preset-security-policies.md)

Acompanhar as [novidades do Microsoft Defender para Office 365 (incluindo desenvolvimentos do EOP)](whats-new-in-office-365-atp.md)

[Usar o Explorador de Ameaças ou detecções em tempo real](threat-explorer.md)

Usar [Simulador de Ataque no Microsoft Defender para Office 365](attack-simulator.md)
