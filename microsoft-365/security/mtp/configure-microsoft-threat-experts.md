---
title: Configurar e gerenciar recursos Especialistas em Ameaças da Microsoft por meio do Microsoft 365 Defender
description: Inscreva-se no Microsoft Threats Experts Microsoft 365 Defender para configurar, gerenciar e usá-lo em suas operações diárias de segurança e trabalho de administração de segurança.
keywords: Especialistas em Ameaças da Microsoft, serviço de busca de ameaças gerenciado, MTE, serviço de busca gerenciada da Microsoft
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
localization_priority: normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 0ccb8482dae94de4a9f43a5ecaf7c701e6dd82a5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844785"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Configurar e gerenciar recursos Especialistas em Ameaças da Microsoft por meio do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de começar

> [!IMPORTANT]
> Antes de aplicar, certifique-se de discutir os requisitos de qualificação para o serviço de busca de ameaças gerenciadas Especialistas em Ameaças da Microsoft – Notificações de Ataque Direcionadas com seu provedor de Serviços Técnicos da Microsoft e sua equipe de conta.

Para receber notificações de ataque direcionadas, você precisará ter o Defender Microsoft 365 implantado com dispositivos inscritos. Em seguida, envie um aplicativo por meio do portal M365 para Especialistas em Ameaças da Microsoft - Notificações de Ataque Direcionado.

Entre em contato com sua equipe de conta ou representante da Microsoft para assinar Especialistas em Ameaças da Microsoft - Especialistas sob Demanda. Os especialistas sob demanda permitem que você consulte nossos especialistas em ameaças sobre como proteger sua organização contra detecções e adversários relevantes.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Aplicar para Especialistas em Ameaças da Microsoft - Serviço de Notificações de Ataque Direcionado

Se você já tiver o Microsoft Defender para o Ponto de Extremidade e o Microsoft 365 Defender, você poderá solicitar Especialistas em Ameaças da Microsoft – Notificações de Ataque Direcionadas por meio do portal Microsoft 365 Defender.  As notificações de ataque direcionadas concedem informações e análises especiais para ajudar a identificar as ameaças mais críticas à sua organização, para que você possa responder a elas rapidamente.

1. No painel de navegação, vá para Configurações > **Endpoints > recursos**> recursos avançados > Especialistas em Ameaças da Microsoft - Notificações de Ataque Direcionado.

2. Selecione **Aplicar**.

    ![Imagem de Especialistas em Ameaças da Microsoft configurações](../../media/mte/mte-collaboratewithmte.png)

3. Insira seu nome e endereço de email para que a Microsoft possa entrar em contato com você sobre seu aplicativo.

    ![Imagem do Especialistas em Ameaças da Microsoft aplicativo](../../media/mte/mte-apply.png)

4. Leia a [instrução de](https://privacy.microsoft.com/en-us/privacystatement)privacidade e selecione **Enviar** quando terminar. Você receberá um email de boas-vindas depois que seu aplicativo for aprovado.

    ![Imagem da confirmação Especialistas em Ameaças da Microsoft aplicativo](../../media/mte/mte-applicationconfirmation.png)

5. Depois de receber seu email de boas-vindas, você começará automaticamente a receber notificações de ataque direcionadas.

6. Você pode verificar seu status visitando Configurações > pontos de **extremidade > recursos > avançados.** Depois de aprovado, a Especialistas em Ameaças da Microsoft **- Alternância** de Notificação de Ataque Direcionada ficará visível e **comutado**.

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Onde você verá as notificações de ataque direcionadas de Especialistas em Ameaças da Microsoft

Você pode receber uma notificação de ataque direcionada Especialistas em Ameaças da Microsoft pelos seguintes meios:

- A Microsoft 365 **incidentes** do portal do Defender
- O Microsoft 365 painel **Alertas do** portal do Defender
- API de alerta OData [e API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) [REST](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [Tabela DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) em Busca Avançada
- Sua caixa de entrada, se você optar por ter notificações de ataque direcionadas enviadas por email. Consulte [Criar uma regra de notificação de email](#create-an-email-notification-rule) abaixo.

### <a name="create-an-email-notification-rule"></a>Criar uma regra de notificação de email

Você pode criar regras para enviar notificações por email para destinatários de notificação. Para obter detalhes  [completos,](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) consulte Configure alert notifications to create, edit, delete, or troubleshoot email notification.

## <a name="view-targeted-attack-notifications"></a>Exibir notificações de ataque direcionadas

Você começará a receber uma notificação de ataque direcionada Especialistas em Ameaças da Microsoft seu email depois de configurar seu sistema para receber a notificação por email.

1. Selecione o link no email para ir para o contexto de alerta correspondente no painel marcado com **especialistas em ameaças.**

2. Na página **Alertas,** selecione o mesmo tópico de alerta que você recebeu no email, para exibir mais detalhes.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Inscrever-Especialistas em Ameaças da Microsoft - Especialistas sob Demanda

Se você já for um cliente do Microsoft Defender para Ponto de Extremidade, entre em contato com seu representante da Microsoft para assinar o Especialistas em Ameaças da Microsoft - Especialistas sob Demanda.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Consulte um especialista em ameaças da Microsoft sobre atividades suspeitas de segurança cibernética em sua organização

Você pode entrar em Especialistas em Ameaças da Microsoft de dentro do portal Microsoft 365 Defender. Os especialistas podem ajudá-lo a entender ameaças complexas e notificações de ataque direcionadas. Partner with experts for further details about alerts and incidents, or advice on handling compromise. Obtenha informações sobre o contexto de inteligência de ameaças descrito pelo painel do portal.

> [!NOTE]
>
> - As consultas de alerta relacionadas aos dados de inteligência de ameaças personalizadas da sua organização não são suportadas no momento. Consulte suas operações de segurança ou equipe de resposta a incidentes para obter detalhes.
> - Você precisa ter a permissão **Gerenciar** configurações de segurança no Centro de Segurança no portal Microsoft 365 Defender para enviar uma consulta por meio do formulário Consultar um especialista **em** ameaças.

1. Navegue até a página do portal relacionada às informações que você gostaria de investigar: por exemplo, **Device**, **Alert** ou **Incident**. Certifique-se de que a página do portal relacionada à sua investigação está em exibição antes de enviar uma solicitação de investigação.

2. No menu superior, selecione **? Consulte um especialista em ameaças.**

    ![Imagem de Especialistas em Ameaças da Microsoft especialistas sob demanda no menu](../../media/mte/incidents-action-mte-highlighted.png)

    Uma tela de sobrevoo será aberta.

    O header indicará se você está em uma assinatura de avaliação ou uma assinatura completa Especialistas em Ameaças da Microsoft - Especialistas sob Demanda.

    ![Imagem de Especialistas em Ameaças da Microsoft de assinatura de avaliação de especialistas sob demanda](../../media/mte/mte-trial.png)

    O **campo tópico** Investigação já será preenchido com o link para a página relevante para sua solicitação.

3. No próximo campo, forneça informações suficientes para fornecer à Especialistas em Ameaças da Microsoft contexto suficiente para iniciar a investigação.

4. Insira o endereço de email que você gostaria de usar para corresponder Especialistas em Ameaças da Microsoft.

> [!NOTE]
> Se você quiser acompanhar o status de seus casos de Especialistas sob Demanda por meio do Microsoft Services Hub, entre em contato com seu gerente de conta técnica.

Assista a este vídeo para uma visão geral rápida do Microsoft Services Hub.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Tópicos de investigação de exemplo

### <a name="alert-information"></a>Informações de alerta

- Vimos um novo tipo de alerta para um binário de vida fora da terra. Podemos fornecer a ID do alerta. Você pode nos contar mais sobre esse alerta e como podemos investigar isso ainda mais?
- Observamos dois ataques semelhantes, que tentam executar scripts mal-intencionados do PowerShell, mas geram alertas diferentes. Uma é "Linha de comando suspeita do PowerShell" e a outra é "Um arquivo mal-intencionado foi detectado com base na indicação fornecida pelo O365". Qual é a diferença?
- Recebemos um alerta ímpar hoje sobre um número anormal de logins com falha do dispositivo de um usuário de alto perfil. Não é possível encontrar mais evidências para essas tentativas. Como o Microsoft 365 Defender pode ver essas tentativas? Que tipo de logon está sendo monitorado?
- Você pode dar mais contexto ou visão sobre o alerta, "Comportamento suspeito por um utilitário do sistema foi observado"?
- Eu observava um alerta intitulado "Criação de regra de encaminhamento/redirecionamento". Acredito que a atividade seja benigna. Pode me dizer por que recebi um alerta?

### <a name="possible-machine-compromise"></a>Possível comprometimento do computador

- Você pode ajudar a explicar por que vemos uma mensagem ou um alerta para "Processo desconhecido observado" em muitos dispositivos em nossa organização? Agradecemos qualquer entrada para esclarecer se essa mensagem ou alerta está relacionado a atividades mal-intencionadas.
- Você pode ajudar a validar um possível comprometimento no sistema a seguir, datado da semana passada? Ele está se comportando da mesma forma que uma detecção de malware anterior no mesmo sistema há seis meses.

### <a name="threat-intelligence-details"></a>Detalhes da inteligência contra ameaças

- Detectamos um email de phishing que entregava um documento mal-intencionado do Word a um usuário. O documento causou uma série de eventos suspeitos, que dispararam vários alertas para uma família de malware específica. Você tem alguma informação sobre esse malware? Se sim, você pode nos enviar um link?
- Recentemente, vimos uma postagem de blog sobre uma ameaça que está direcionando nosso setor. Você pode nos ajudar a entender que proteção o Defender Microsoft 365 oferece contra esse ator de ameaças?
- Recentemente, observamos uma campanha de phishing conduzida contra nossa organização. Você pode nos dizer se isso foi direcionado especificamente para nossa empresa ou vertical?

### <a name="microsoft-threat-experts-alert-communications"></a>Especialistas em Ameaças da Microsoft de alerta

- Sua equipe de resposta a incidentes pode nos ajudar a lidar com a notificação de ataque direcionada que temos?
- Recebemos essa notificação de ataque direcionada Especialistas em Ameaças da Microsoft. Não temos nossa própria equipe de resposta a incidentes. O que podemos fazer agora e como podemos conter o incidente?
- Recebemos uma notificação de ataque direcionada de Especialistas em Ameaças da Microsoft. Quais dados você pode fornecer para nós que podemos passar para nossa equipe de resposta a incidentes?

> [!NOTE]
> Especialistas em Ameaças da Microsoft é um serviço gerenciado de busca de ameaças e não um serviço de resposta a incidentes. No entanto, os especialistas podem fazer a transição perfeita da investigação para os serviços de Equipe de Detecção e Resposta do Grupo de Soluções de Segurança Cibernética (CSG), quando necessário. Você também pode optar por se envolver com sua própria equipe de resposta a incidentes para resolver problemas que exigem uma resposta a incidentes.

## <a name="scenario"></a>Cenário

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Receber um relatório de progresso sobre sua investigação de busca gerenciada

A resposta do Especialistas em Ameaças da Microsoft irá variar de acordo com sua investigação. Geralmente, você receberá uma das seguintes respostas:

- Mais informações são necessárias para continuar com a investigação
- Um arquivo ou vários exemplos de arquivo são necessários para determinar o contexto técnico
- A investigação requer mais tempo
- As informações iniciais foram suficientes para concluir a investigação

Se um especialista solicitar mais informações ou amostras de arquivo, é fundamental responder rapidamente para manter a investigação em andamento.

## <a name="see-also"></a>Confira também

- [Visão geral dos Especialistas em Ameaças da Microsoft](microsoft-threat-experts.md)
