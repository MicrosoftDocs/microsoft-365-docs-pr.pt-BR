---
title: Considerações de implantação de treinamento de simulação de ataque e perguntas frequentes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre considerações de implantação e perguntas frequentes sobre simulação de ataque e treinamento nas organizações do Microsoft 365 E5 ou do Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921367"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Considerações de implantação de treinamento de simulação de ataque e perguntas frequentes

O treinamento de simulação de ataque [agora está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291). O treinamento de simulação de ataque permite que as organizações do Microsoft 365 E5 ou do Microsoft Defender for Office 365 Plan 2 medam e gerenciem o risco de engenharia social, permitindo a criação e o gerenciamento de simulações de phishing que são movidas por cargas de phishing desarmadas no mundo real. O treinamento hiper-direcionado, fornecido em parceria com a segurança do Terranova, ajuda a melhorar o conhecimento e alterar o comportamento dos funcionários.

Para obter mais informações sobre como começar com o treinamento de simulação de ataque, consulte [Get started using Attack simulation training](attack-simulation-training-get-started.md).

Embora toda a experiência de criação e agendamento de simulação tenha sido projetada para ser de fluxo livre e sem atrito, a execução de simulações em uma escala corporativa geralmente requer planejamento. Este artigo ajuda a resolver desafios específicos que vemos à medida que nossos clientes executarem simulações em seus próprios ambientes.

## <a name="issues-with-end-user-experiences"></a>Problemas com experiências de usuário final

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>URLs de simulação de phishing bloqueadas pela Navegação Segura do Google

Um serviço de reputação de URL pode identificar uma ou mais URLs usadas pelo treinamento de simulação de ataque como não seguras. A Navegação Segura do Google no Google Chrome bloqueia algumas das URLs de phishing simuladas com uma **mensagem de site enganoso à** frente. Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir nossas URLs de simulação, nem sempre temos cobertura completa.

![Aviso de site enganoso no Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

Observe que esse problema não afeta o Microsoft Edge.

Como parte da fase de planejamento, verifique a disponibilidade da URL em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing. Se as URLs são bloqueadas pela Navegação Segura do [Google,](https://support.google.com/chrome/a/answer/7532419) siga essas diretrizes do Google para permitir o acesso às URLs.

Consulte [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>UrLs de administrador e simulação de phishing bloqueadas por soluções de proxy de rede e drivers de filtro

UrLs de simulação de phishing e URLs de administrador podem ser bloqueadas ou largas por seus dispositivos de segurança intermediários ou filtros. Por exemplo:

- Firewalls
- Soluções waf (firewall de aplicativo web)
- Drivers de filtro de terceiros (por exemplo, filtros de modo kernel)

Embora vimos poucos clientes sendo bloqueados nessa camada, isso acontece. Se você encontrar problemas, considere configurar as SEGUINTES URLs para ignorar a verificação por seus dispositivos de segurança ou filtros, conforme necessário:

- As URLs de phishing simuladas conforme descrito em [Get started using Attack simulation training](attack-simulation-training-get-started.md).
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Mensagens de simulação não entregues a todos os usuários direcionados

É possível que o número de usuários que realmente recebem as mensagens de email de simulação seja menor do que o número de usuários que foram direcionados pela simulação. Os seguintes tipos de usuários serão excluídos como parte da validação de destino:

- Endereços de email de destinatário inválidos.
- Usuários convidados.
- Usuários que não estão mais ativos no Azure Active Directory (Azure AD).

Somente usuários não convidados válidos com uma caixa de correio válida serão incluídos em simulações. Se você usar grupos de distribuição ou grupos de segurança habilitados para email para direcionar usuários, poderá usar o cmdlet [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) no [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online para exibir e validar membros do grupo de distribuição.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problemas com relatórios de treinamento de simulação de ataque

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>Relatórios de treinamento de simulação de ataque não contêm detalhes de atividade

O treinamento de simulação de ataque vem com ideias ricas e ativas que o mantêm informado sobre o progresso da preparação de ameaças de seus funcionários. Se os relatórios de treinamento de simulação de ataque não são preenchidos com dados, verifique se a pesquisa de log de auditoria está 100% 100% 100%.

A pesquisa de log de auditoria é necessária pelo treinamento de simulação de ataque para que os eventos possam ser capturados, gravados e lidos de volta. Desligar a pesquisa de log de auditoria tem as seguintes consequências para o treinamento de simulação de ataque:

- Os dados de relatório não estão disponíveis em todos os relatórios. Os relatórios aparecerão vazios.
- As atribuições de treinamento são bloqueadas porque os dados não estão disponíveis.

Para ativar a pesquisa de log de auditoria, consulte Ativar ou desativar a pesquisa [de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> Detalhes de atividades vazias também podem ser causados por nenhuma licença do E5 ser atribuída aos usuários. Verifique se pelo menos uma licença E5 é atribuída a um usuário ativo para garantir que os eventos de relatório sejam capturados e gravados.

### <a name="simulation-reports-are-not-updated-immediately"></a>Relatórios de simulação não são atualizados imediatamente

Relatórios detalhados de simulação não são atualizados imediatamente após o início de uma campanha. Não se preocupe. esse comportamento é esperado.

Cada campanha de simulação tem um ciclo de vida. Quando criada pela primeira vez, a simulação está no **estado Agendado.** Quando a simulação é iniciada, ela faz a transição para o **estado em** andamento. Quando concluída, a simulação faz a transição para o **estado** Concluído.

Enquanto uma simulação estiver no **estado Agendado,** os relatórios de simulação estarão em sua maioria vazios. Durante esse estágio, o mecanismo de simulação está resolvendo os endereços de email do usuário de destino, expandindo grupos de distribuição, removendo usuários convidados da lista, etc.:

![Relatórios no estado Agendado](../../media/attack-sim-empty-reporting.png)

Depois que a simulação entrar **no estágio Em andamento,** você observará as informações que começam a entrar no relatório:

![Relatórios no estado em andamento](../../media/attack-sim-in-progress.png)

Pode levar até 30 minutos para que os relatórios de simulação individuais atualizem após a transição para o **estado em** andamento. Os dados do relatório continuam a ser construídos até que a simulação atinja o **estado Concluído.** As atualizações de relatórios ocorrem nos seguintes intervalos:

- A cada 10 minutos dos primeiros 60 minutos.
- A cada 15 minutos após 60 minutos até 2 dias.
- A cada 30 minutos após 2 dias até 7 dias.
- A cada 60 minutos após sete dias.

Os widgets na página **Visão** Geral fornecem um instantâneo rápido da postura de segurança baseada em simulação da sua organização ao longo do tempo. Como esses widgets refletem sua postura geral de segurança e sua jornada ao longo do tempo, eles são atualizados após a conclusão de cada campanha de simulação.

> [!NOTE]
> Você pode usar a **opção Exportar** nas várias páginas de relatórios para extrair dados.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>Mensagens relatadas como phishing por usuários não aparecem em relatórios de simulação

Relatórios de simulação no treinamento do simulador de ataque fornecem detalhes sobre a atividade do usuário. Por exemplo:

- Usuários que clicaram no link na mensagem.
- Usuários que abriram mão de suas credenciais.
- Usuários que relataram a mensagem como phishing.

Se as mensagens relatadas pelos usuários como phishing não são capturadas nos relatórios de simulação de simulação de ataque, pode haver uma regra de fluxo de emails do Exchange (também conhecida como regra de transporte) que está bloqueando a entrega das mensagens relatadas para a Microsoft. Verifique se as regras de fluxo de emails não estão bloqueando a entrega para os seguintes endereços de email:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- não \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>Outras perguntas frequentes

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>P: Qual é o método recomendado para direcionar usuários para campanhas de simulação?

R: Várias opções estão disponíveis para os usuários de destino:

- Inclua todos os usuários (atualmente disponíveis para organizações com menos de 40.000 usuários).
- Escolha usuários específicos.
- Selecione usuários de um arquivo CSV.
- Direcionamento baseado em grupo do Azure AD.

Descobrimos que as campanhas nas quais os usuários direcionados são identificados pelos grupos do Azure AD geralmente são mais fáceis de gerenciar.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>P: Há limites para direcionar usuários ao importar de um CSV ou adicionar usuários?

R: O limite para importar destinatários de um arquivo CSV ou adicionar destinatários individuais a uma simulação é 40.000.

Um destinatário pode ser um usuário individual ou um grupo. Um grupo pode conter centenas ou milhares de destinatários, portanto, um limite real não é colocado no número de usuários individuais.

Gerenciar um arquivo CSV grande ou adicionar muitos destinatários individuais pode ser complicado. O uso de grupos do Azure AD simplificará o gerenciamento geral da simulação.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>P: A Microsoft fornece cargas em outros idiomas?

R: Atualmente, há 5 cargas localizadas disponíveis. Notamos que as traduções diretas ou automáticas de cargas existentes para outros idiomas levarão a imprecisões e redução de relevância.

Dito isso, você pode criar sua própria carga no idioma de sua escolha usando a experiência de criação de carga personalizada. Também recomendamos que você colhe cargas existentes que foram usadas para direcionar usuários em uma geografia específica. Em outras palavras, deixe que os invasores localizem o conteúdo para você.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>P: Como posso alternar para outros idiomas para meu portal de administração e experiência de treinamento?

R: No Microsoft 365 ou Office 365, a configuração de idioma é específica e centralizada para cada conta de usuário. Para obter instruções sobre como alterar sua configuração de idioma, consulte Alterar seu idioma de exibição e fuso [horário no Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).

Observe que a alteração de configuração pode levar até 30 minutos para ser sincronizada em todos os serviços.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>P: Posso disparar uma simulação de teste para entender como ela é antes de iniciar uma campanha completa?

R: Sim, você pode! Na última página **De simulação** de revisão no assistente para criar uma nova simulação, há uma opção **para Enviar um teste**. Essa opção enviará uma mensagem de simulação de phishing de exemplo para o usuário conectado no momento. Depois de validar a mensagem de phishing em sua Caixa de Entrada, você pode enviar a simulação.

![Enviar um botão de teste na página Revisar simulação](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>P: Posso direcionar usuários que pertencem a um locatário diferente como parte da mesma campanha de simulação?

R: Não. Atualmente, não há suporte para simulações entre locatários. Verifique se todos os usuários direcionados estão no mesmo locatário. Quaisquer usuários entre locatários ou usuários convidados serão excluídos da campanha de simulação.

### <a name="q-how-does-region-aware-delivery-work"></a>P: Como funciona a entrega ciente da região?

R: A entrega ciente da região usa o atributo TimeZone da caixa de correio do usuário direcionado e a lógica "não antes" para determinar quando entregar a mensagem. Por exemplo, considere o seguinte cenário:

- Às 7:00 da manhã no fuso horário do Pacífico (UTC-8), um administrador cria e agenda uma campanha para começar às 9:00 no mesmo dia.
- UserA está no fuso horário do Leste (UTC-5).
- UserB também está no fuso horário do Pacífico.

Às 9:00 da manhã do mesmo dia, a mensagem de simulação é enviada para UserB. Com a entrega ciente da região, a mensagem não é enviada para UserA no mesmo dia, pois 9:00 hora do Pacífico é 12:00 horário de Leste. Em vez disso, a mensagem é enviada para UserA às 9:00 horário do Leste no dia seguinte.

Portanto, na primeira etapa de uma campanha com a entrega ciente de região habilitada, pode parecer que a mensagem de simulação foi enviada somente para usuários em um fuso horário específico. Mas, à medida que o tempo passa e mais usuários chegam ao escopo, os usuários direcionados aumentarão.