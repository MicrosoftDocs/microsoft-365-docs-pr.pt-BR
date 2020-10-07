---
title: Políticas de alerta nos centros de segurança e conformidade
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
ms.custom:
- seo-marvel-apr2020
description: Crie políticas de alerta no centro de segurança e conformidade no Office 365 e no Microsoft 365 para monitorar possíveis ameaças, perda de dados e problemas de permissões.
ms.openlocfilehash: dbe97b207e9683e719155f5dfd94d6f6a0427940
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370439"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Políticas de alerta no centro de conformidade e segurança

Você pode usar a política de alerta e as ferramentas de painel de alerta nos centros de segurança e conformidade do Microsoft 365 para criar políticas de alerta e, em seguida, exibir os alertas gerados quando os usuários realizarem atividades que correspondam às condições de uma política de alerta. Há várias políticas de alerta padrão que ajudam a monitorar atividades, como atribuir privilégios de administrador no Exchange Online, ataques de malware, campanhas de phishing e níveis incomuns de exclusões de arquivos e compartilhamento externo.

As políticas de alerta permitem que você categorize os alertas disparados por uma política, aplique a política a todos os usuários em sua organização, defina um nível de limite para quando um alerta for disparado e decida se receberá notificações por email quando os alertas forem acionados. Há também uma página **exibir alertas** no centro de conformidade e segurança, onde você pode exibir e filtrar alertas, definir um status de alerta para ajudá-lo a gerenciar alertas e, em seguida, ignorar alertas após ter resolvido ou resolvido o incidente subjacente.

> [!NOTE]
> As políticas de alerta estão disponíveis para organizações com o Microsoft 365 Enterprise, o Office 365 Enterprise ou o Office 365 Brasil E1/F1/G1, E3/G3 ou E5/G5 assinatura. A funcionalidade avançada só está disponível para organizações com uma assinatura E5/G5 ou para organizações que possuem uma assinatura E1/F1/G1 ou E3 e uma assinatura do Office 365 Advanced Threat Protection (ATP) P2 ou uma assinatura do Microsoft 365 E5 Compliance ou Microsoft 365 E5 eDiscovery e Audit Add-on. A funcionalidade que requer uma assinatura do E5/G5 ou complemento é realçada neste tópico. Observe também que as políticas de alerta estão disponíveis nos ambientes do Office 365 GCC, GCC High e DoD US governamentais.

## <a name="how-alert-policies-work"></a>Como funcionam as políticas de alerta

Veja aqui uma rápida visão geral de como as políticas de alerta funcionam e os alertas que são disparados quando a atividade de usuário ou administrador corresponde às condições de uma política de alerta.

![Visão geral de como as políticas de alerta funcionam](../media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)

1. Um administrador de sua organização cria, configura e ativa uma política de alerta usando a página **políticas de alerta** no centro de conformidade e segurança. Você também pode criar políticas de alerta usando o cmdlet **New-ProtectionAlert** no PowerShell do centro de conformidade e segurança &. Para criar políticas de alerta, você precisa receber a função Gerenciar alertas ou a função de configuração da organização no centro de segurança e conformidade.

   > [!NOTE]
   > É necessário até 24 horas após a criação ou atualização de uma política de alerta antes que os alertas possam ser disparados pela política. Isso ocorre porque a política deve ser sincronizada com o mecanismo de detecção de alerta.

2. Um usuário realiza uma atividade que corresponde às condições de uma política de alerta. No caso de ataques de malware, mensagens de email infectadas enviadas para os usuários em sua organização disparam um alerta.

3. O Microsoft 365 gera um alerta que é exibido na página **exibir alertas** no centro de conformidade do & de segurança. Além disso, se as notificações por email estiverem habilitadas para a política de alerta, a Microsoft enviará uma notificação para uma lista de destinatários. Os alertas que um administrador ou outros usuários podem ver que na página exibir alertas é determinado pelas funções atribuídas ao usuário. Para obter mais informações, consulte a seção [permissões RBAC necessárias para exibir alertas](#rbac-permissions-required-to-view-alerts) .

4. Um administrador gerencia alertas no centro de segurança e conformidade. O gerenciamento de alertas consiste em atribuir um status de alerta para ajudar a rastrear e gerenciar qualquer investigação.

## <a name="alert-policy-settings"></a>Configurações de política de alerta

Uma política de alerta consiste em um conjunto de regras e condições que definem o usuário ou a atividade de administrador que gera um alerta, uma lista de usuários que disparam o alerta se eles executarem a atividade e um limite que define quantas vezes a atividade deve ocorrer antes de um alerta ser acionado. Você também categoriza a política e a atribui a um nível de severidade. Essas duas configurações ajudam você a gerenciar políticas de alerta (e os alertas disparados quando as condições de política são correspondidas), pois você pode filtrar essas configurações ao gerenciar políticas e exibir alertas no centro de segurança e conformidade. Por exemplo, você pode exibir alertas que correspondam às condições da mesma categoria ou exibir alertas com o mesmo nível de severidade.

Para exibir e criar políticas de alerta, vá para [https://protection.office.com](https://protection.office.com) e selecione **alertas** \> **políticas de alerta**.

![No centro de segurança e conformidade, selecione alertas e, em seguida, selecione políticas de alerta para exibir e criar políticas de alerta](../media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)

Uma política de alerta consiste nas configurações e condições a seguir.

- **Atividade o alerta é o acompanhamento** -você cria uma política para controlar uma atividade ou, em alguns casos, algumas atividades relacionadas, como compartilhar um arquivo com um usuário externo compartilhando-o, atribuindo permissões de acesso ou criando um link anônimo. Quando um usuário realiza a atividade definida pela política, um alerta é acionado com base nas configurações de limite de alerta.

    > [!NOTE]
    > As atividades que você pode acompanhar dependem do plano do governo dos EUA da organização do Office 365 Enterprise ou do Office 365. Em geral, as atividades relacionadas às campanhas de malware e aos ataques de phishing exigem uma assinatura do E5/G5 ou uma assinatura E1/F1/G1 ou E3 com uma assinatura complementar do plano 2 de [proteção avançada contra ameaças do Office 365](../security/office-365-security/office-365-atp.md) .

- **Condições da atividade** – para a maioria das atividades, você pode definir condições adicionais que devem ser atendidas para acionar um alerta. As condições comuns incluem endereços IP (para que um alerta seja disparado quando o usuário executa a atividade em um computador com um endereço IP específico ou dentro de um intervalo de endereços IP), se um alerta é disparado se um usuário ou usuários específicos realizam essa atividade, e se a atividade é executada em um nome de arquivo específico ou uma URL. Você também pode configurar uma condição que dispara um alerta quando a atividade é realizada por qualquer usuário em sua organização. As condições disponíveis dependem da atividade selecionada.

- **Quando o alerta é disparado** , você pode definir uma configuração que define a frequência com que uma atividade pode ocorrer antes de um alerta ser acionado. Isso permite que você configure uma política para gerar um alerta sempre que uma atividade corresponder às condições da política, quando um determinado limite for excedido ou quando a ocorrência da atividade que o alerta estiver rastreando se tornar incomum para sua organização.

    ![Configurar como os alertas são acionados, com base em quando a atividade ocorre, um limite ou atividade incomum para sua organização](../media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)

    Se você selecionar a configuração com base em atividade incomum, a Microsoft estabelecerá um valor de linha de base que define a frequência normal para a atividade selecionada. Leva até sete dias para estabelecer essa linha de base, durante a qual os alertas não serão gerados. Depois que a linha de base é estabelecida, um alerta é disparado quando a frequência da atividade rastreada pela política de alerta excede muito o valor da linha de base. Para atividades relacionadas à auditoria (como atividades de arquivo e pasta), você pode estabelecer uma linha de base com base em um único usuário ou com base em todos os usuários em sua organização; para atividades relacionadas a malware, você pode estabelecer uma linha de base com base em uma única família de malware, um único destinatário ou todas as mensagens em sua organização.

    > [!NOTE]
    > A capacidade de configurar políticas de alerta com base em um limite ou com base em atividade incomum requer uma assinatura do E5/G5 ou uma assinatura E1/F1/G1 ou E3 com uma assinatura do Office 365 ATP P2, Microsoft 365 E5 conformidade ou Microsoft 365 eDiscovery e auditoria de Complementos. As organizações com uma assinatura E1/F1/G1 e E3/G3 só podem criar políticas de alerta em que um alerta é acionado sempre que uma atividade ocorre.

- **Categoria de alerta** – para ajudar no controle e gerenciamento dos alertas gerados por uma política, você pode atribuir uma das seguintes categorias a uma política.

  - Prevenção contra perda de dados

  - Governança de informações

  - Fluxo de emails

  - Permissões

  - Gerenciamento de ameaças

  - Outros

  Quando ocorre uma atividade que corresponde às condições da política de alerta, o alerta gerado é marcado com a categoria definida nesta configuração. Isso permite que você rastreie e gerencie alertas que tenham a mesma configuração de categoria na página **exibir alertas** no centro de conformidade e segurança, pois é possível classificar e filtrar alertas com base na categoria.

- **Severidade de alerta** -semelhante à categoria de alerta, você atribui um atributo de gravidade (**baixo**, **médio**, **alto**ou **informativo**) a políticas de alerta. Como a categoria de alerta, quando ocorre uma atividade que corresponde às condições da política de alerta, o alerta gerado é marcado com o mesmo nível de gravidade definido para a política de alerta. Novamente, isso permite que você rastreie e gerencie alertas com a mesma configuração de gravidade na página **exibir alertas** . Por exemplo, você pode filtrar a lista de alertas para que apenas os alertas com uma severidade **alta** sejam exibidos.

    > [!TIP]
    > Ao configurar uma política de alerta, considere a atribuição de uma severidade maior às atividades que podem resultar em conseqüências severamente negativas, como a detecção de malware após a entrega aos usuários, a exibição de dados confidenciais ou classificados, o compartilhamento de dados com usuários externos ou outras atividades que podem resultar em perda de dados ou ameaças de segurança. Isso pode ajudar você a priorizar alertas e as ações tomadas para investigar e resolver as causas subjacentes.

- **Notificações por email** -você pode configurar a política para que as notificações por email sejam enviadas (ou não enviadas) para uma lista de usuários quando um alerta é acionado. Você também pode definir um limite de notificação diária para que, depois que o número máximo de notificações tiver sido atingido, nenhuma notificação será enviada para o alerta durante esse dia. Além das notificações por email, você ou outros administradores podem exibir os alertas disparados por uma política na página **exibir alertas** . Considere habilitar notificações por email para políticas de alerta de uma categoria específica ou que tenham uma configuração de severidade mais alta.

## <a name="default-alert-policies"></a>Políticas de alerta padrão

A Microsoft fornece políticas de alerta internas que ajudam a identificar abuso de permissões de administração do Exchange, atividade de malware, ameaças externas e internas possíveis e riscos de governança de informações. Na página **políticas de alerta** , os nomes dessas políticas internas estão em negrito e o tipo de política é definido como **sistema**. Essas políticas são ativadas por padrão. Você pode desativar essas políticas (ou voltar novamente), configurar uma lista de destinatários para enviar notificações por email e definir um limite diário de notificação. As outras configurações dessas políticas não podem ser editadas.

A tabela a seguir lista e descreve as políticas de alerta padrão disponíveis e a categoria à qual cada política é atribuída. A categoria é usada para determinar quais alertas um usuário pode exibir na página exibir alertas. Para obter mais informações, consulte a seção [permissões RBAC necessárias para exibir alertas](#rbac-permissions-required-to-view-alerts) .

A tabela também indica o plano do governo dos EUA do Office 365 Enterprise e do Office 365 necessário para cada um. Algumas políticas de alerta padrão estão disponíveis se sua organização tem a assinatura complementar apropriada, além de uma assinatura E1/F1/G1 ou E3.

| Política de alerta padrão | Descrição | Categoria | Assinatura do Office 365 Enterprise |
|:-----|:-----|:-----|:-----|
|**Um clique em URL potencialmente mal-intencionado foi detectado**|Gera um alerta quando um usuário protegido por [links seguros de ATP do Office 365](../security/office-365-security/atp-safe-links.md) em sua organização clica em um link mal-intencionado. Este evento é disparado quando as alterações de URL veredicto são identificadas pelo Office 365 ATP ou quando os usuários substituem as páginas de links seguros do Office 365 ATP (com base na política de links seguros de ATP da sua organização Microsoft 365 para empresas). Essa política de alerta tem uma configuração de **alta** gravidade. Para os clientes do Office 365 ATP P2, e5, G5, este alerta dispara automaticamente a [investigação e a resposta automatizadas no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Para obter mais informações sobre eventos que disparam esse alerta, consulte [set up Office 365 ATP Safe links Policies](../security/office-365-security/set-up-atp-safe-links-policies.md).|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Resultado do envio do administrador concluído**|Gera um alerta quando um [envio de administrador](../security/office-365-security/admin-submission.md) conclui a verificação da entidade enviada. Um alerta será disparado toda vez que um resultado de nova verificação for renderizado de um envio de administrador. Esses alertas destinam-se a lembrá-lo de [revisar os resultados de](https://protection.office.com/reportsubmission)envios anteriores, enviar mensagens relatadas pelo usuário para obter a verificação mais recente da política e reexaminar o verdicts e ajudá-lo a determinar se as políticas de filtragem em sua organização estão tendo o impacto desejado. Essa política tem uma configuração de **baixa** gravidade.|Gerenciamento de ameaças|E1/F1, E3 ou e5|
|**Investigação manual de email disparada pelo administrador**|Gera um alerta quando um administrador aciona a investigação manual de um email a partir do Gerenciador de ameaças. Para obter mais informações, consulte [exemplo: um administrador de segurança dispara uma investigação do explorador de ameaças] ( https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) . Este alerta notifica sua organização de que a investigação foi iniciada. O alerta fornece informações sobre quem disparou e inclui um link para a investigação. Essa política tem uma configuração de severidade **informativa** .|Gerenciamento de ameaças| Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2| 
|**Criação de regra de encaminhamento/redirecionamento**|Gera um alerta quando alguém em sua organização cria uma regra de caixa de entrada para a caixa de correio que encaminha ou redireciona mensagens para outra conta de email. Esta política controla apenas as regras de caixa de entrada que são criadas usando o Outlook na Web (anteriormente conhecido como Outlook Web App) ou o PowerShell do Exchange Online. Essa política tem uma configuração de **baixa** gravidade. Para obter mais informações sobre como usar regras de caixa de entrada para encaminhar e redirecionar emails no Outlook na Web, confira [usar regras no Outlook na Web para encaminhar automaticamente as mensagens para outra conta](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**pesquisa de descoberta eletrônica iniciada ou exportada**|Gera um alerta quando alguém usa a ferramenta de pesquisa de conteúdo no centro de segurança e conformidade. Um alerta é disparado quando as seguintes atividades de pesquisa de conteúdo são executadas: <br/><br/>* Uma pesquisa de conteúdo foi iniciada<br/>* Os resultados de uma pesquisa de conteúdo são exportados<br/>* Um relatório de pesquisa de conteúdo é exportado<br/><br/>Os alertas também são acionados quando as atividades de pesquisa de conteúdo anteriores são realizadas em associação a uma ocorrência de descoberta eletrônica. Essa política tem uma configuração de severidade **média** . Para obter mais informações sobre as atividades de pesquisa de conteúdo, consulte [Search for eDiscovery Activities no log de auditoria](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**Elevação do privilégio de administrador do Exchange**|Gera um alerta quando alguém recebe permissões administrativas na sua organização do Exchange Online. Por exemplo, quando um usuário é adicionado ao grupo de função gerenciamento da organização no Exchange Online. Essa política tem uma configuração de **baixa** gravidade.|Permissões|E1/F1/G1, E3/G3 ou E5/G5|
|**Mensagens de email contendo malware removidos após a entrega**|Gera um alerta quando qualquer mensagem que contenha malware é entregue às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectadas das caixas de correio do Exchange Online usando a [limpeza automática de zero hora](../security/office-365-security/zero-hour-auto-purge.md). Essa política tem uma configuração de severidade **informativa** e dispara automaticamente a [investigação e a resposta automatizadas no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Mensagens de email que contêm URLs de phishing removidos após a entrega**|Gera um alerta quando qualquer mensagem que contenha Phish é entregue às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectadas das caixas de correio do Exchange Online usando a [limpeza automática de zero hora](../security/office-365-security/zero-hour-auto-purge.md). Essa política tem uma configuração de severidade **informativa** e dispara automaticamente a [investigação e a resposta automatizadas no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Email relatado por usuário como malware ou phishing**|Gera um alerta quando os usuários na sua organização relatam mensagens como email de phishing usando o suplemento de mensagem de relatório. Essa política tem uma configuração de severidade **informativa** . Para obter mais informações sobre esse suplemento, confira [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Para os clientes do Office 365 ATP P2, e5, G5, este alerta dispara automaticamente a [investigação e a resposta automatizadas no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**Limite de envio de email excedido**|Gera um alerta quando alguém em sua organização enviou mais emails do que o permitido pela política de spam de saída. Isso geralmente é uma indicação de que o usuário está enviando muito email ou que a conta pode estar comprometida. Essa política tem uma configuração de severidade **média** . Se você receber um alerta gerado por essa política de alerta, é uma boa ideia [verificar se a conta de usuário está comprometida](../security/office-365-security/responding-to-a-compromised-email-account.md).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**As mensagens foram atrasadas**|Gera um alerta quando a Microsoft não pode entregar mensagens de email para sua organização local ou um servidor parceiro usando um conector. Quando isso acontece, a mensagem é enfileirada no Office 365. Este alerta é disparado quando há 2.000 mensagens ou mais que foram enfileiradas por mais de uma hora. Essa política tem uma configuração de **alta** gravidade.|Fluxo de emails|E1/F1/G1, E3/G3 ou E5/G5|
|**Campanha de malware detectada após a entrega**|Gera um alerta quando um número excepcionalmente grande de mensagens contendo malware é entregue às caixas de correio em sua organização. Se esse evento ocorrer, a Microsoft removerá as mensagens infectadas das caixas de correio do Exchange Online. Essa política tem uma configuração de **alta** gravidade.|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Campanha de malware detectada e bloqueada**|Gera um alerta quando alguém tentava enviar um número excepcionalmente grande de mensagens de email contendo um determinado tipo de malware para os usuários em sua organização. Se esse evento ocorrer, as mensagens infectadas são bloqueadas pela Microsoft e não são entregues a caixas de correio. Essa política tem uma configuração de **baixa** gravidade.|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Campanha de malware detectada no SharePoint e no OneDrive**|Gera um alerta quando um volume excepcionalmente alto de malware ou vírus é detectado em arquivos localizados em sites do SharePoint ou em contas do OneDrive em sua organização. Essa política tem uma configuração de **alta** gravidade.|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Phishing entregue devido à substituição de locatário ou usuário**<sup>1</sup>|Gera um alerta quando a Microsoft detecta um administrador ou substituição de usuário permitiu a entrega de uma mensagem de phishing para uma caixa de correio. Exemplos de substituições incluem uma regra de caixa de entrada ou de fluxo de emails que permite mensagens de um remetente ou domínio específico ou uma política antispam que permite mensagens de remetentes ou domínios específicos. Essa política tem uma configuração de **alta** gravidade.|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Atividade de encaminhamento de emails suspeitos**|Gera um alerta quando alguém em sua organização tem emails automaticamente encaminhados para uma conta externa suspeita. Este é um aviso antecipado para o comportamento que pode indicar que a conta está comprometida, mas não grave o suficiente para restringir o usuário. Essa política tem uma configuração de severidade **média** . Embora seja raro, um alerta gerado por essa política pode ser uma anomalia. É uma boa ideia [verificar se a conta do usuário está comprometida](../security/office-365-security/responding-to-a-compromised-email-account.md).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**Padrões de envio de emails suspeitos detectados**|Gera um alerta quando alguém em sua organização enviou emails suspeitos e está correndo o risco de ser restrito a enviar emails. Este é um aviso antecipado para comportamento que pode indicar que a conta está comprometida, mas não grave o suficiente para restringir o usuário. Essa política tem uma configuração de severidade **média** . Embora seja raro, um alerta gerado por essa política pode ser uma anomalia. No entanto, é uma boa ideia [verificar se a conta do usuário está comprometida](../security/office-365-security/responding-to-a-compromised-email-account.md).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5  |
|**Locatário restrito do envio de email**|Gera um alerta quando a maior parte do tráfego de email da sua organização é detectada como suspeita e a Microsoft restringiu sua organização a enviar emails. Investigue todas as contas de usuário e de administrador potencialmente comprometidas, novos conectores ou retransmissões abertas e, em seguida, entre em contato com o suporte da Microsoft para desbloquear sua organização. Essa política tem uma configuração de **alta** gravidade. Para obter mais informações sobre por que as organizações são bloqueadas, confira [corrigir problemas de entrega de email com o código de erro 5.7.7 XX no Exchange Online](https://go.microsoft.com/fwlink/?linkid=2022138).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|**Atividade de arquivo de usuário externo incomum**|Gera um alerta quando um número excepcionalmente alto de atividades é executado em arquivos no SharePoint ou no OneDrive por usuários fora da sua organização. Isso inclui atividades como acessar arquivos, baixar arquivos e excluir arquivos. Essa política tem uma configuração de **alta** gravidade.|Governança de informações|E5/G5, Office 365 ATP P2 ou assinatura de complemento do Microsoft 365 e5|
|**Volume incomum de compartilhamento de arquivos externos**|Gera um alerta quando um número excepcionalmente grande de arquivos no SharePoint ou no OneDrive são compartilhados com usuários fora da sua organização. Essa política tem uma configuração de severidade **média** .|Governança de informações|E5/G5, Office 365 ATP P2 ou assinatura de complemento do Microsoft 365 e5|
|**Volume incomum de exclusão de arquivo**|Gera um alerta quando um número excepcionalmente grande de arquivos é excluído no SharePoint ou no OneDrive dentro de um curto período de tempo. Essa política tem uma configuração de severidade **média** .|Governança de informações|E5/G5, Office 365 ATP P2 ou assinatura de complemento do Microsoft 365 e5|
|**Aumento incomum no email relatado como phishing**|Gera um alerta quando há um aumento significativo no número de pessoas em sua organização usando o suplemento de mensagem de relatório no Outlook para relatar mensagens como email de phishing. Essa política tem uma configuração de **alta** gravidade. Para obter mais informações sobre esse suplemento, confira [usar o suplemento de mensagem de relatório](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Phishing de representação de usuário entregue à caixa de entrada/pasta**<sup>1,</sup><sup>2</sup>|Gera um alerta quando a Microsoft detecta que um administrador ou substituição de usuário permitiu a entrega de uma mensagem de phishing de personificação do usuário para a caixa de entrada (ou outra pasta acessível pelo usuário) de uma caixa de correio. Exemplos de substituições incluem uma regra de caixa de entrada ou de fluxo de emails que permite mensagens de um remetente ou domínio específico ou uma política antispam que permite mensagens de remetentes ou domínios específicos. Essa política tem uma configuração de severidade **média** .|Gerenciamento de ameaças|Licença de complemento do Microsoft E5/G5 ou do Office 365 ATP P2|
|**Usuário impedido de enviar email**|Gera um alerta quando alguém em sua organização não tem permissão para enviar emails de saída. Isso geralmente ocorre quando uma conta é comprometida e o usuário é listado na página **usuários restritos** no centro de conformidade do & de segurança. (Para acessar essa página, vá para **Gerenciamento de ameaças > Revisar > usuários restritos**). Essa política tem uma configuração de **alta** gravidade. Para obter mais informações sobre usuários restritos, consulte [removendo um usuário, domínio ou endereço IP de uma lista de bloqueios após o envio de email de spam](https://docs.microsoft.com/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam).|Gerenciamento de ameaças|E1/F1/G1, E3/G3 ou E5/G5|
|||||

> [!NOTE]
> <sup>1</sup> removemos temporariamente essa política de alerta padrão com base nos comentários dos clientes. Estamos trabalhando para melhorá-lo e o substituirá por uma nova versão no futuro próximo. Até lá, você pode criar uma política de alerta personalizada para substituir essa funcionalidade usando as seguintes configurações:<br/>&nbsp; * A atividade é o phishing e-mail detectado no momento da entrega<br/>&nbsp; * O email não é ZAP<br/>&nbsp; * A direção do email é de entrada<br/>&nbsp; * O status de entrega de emails é entregue<br/>&nbsp; * A tecnologia de detecção é uma retenção de URL maliciosa, acionamento de URL, filtro de phishing avançado, filtro de phishing geral, representação de domínio, representação de usuário e representação de marca<br/><br/>&nbsp;&nbsp;&nbsp;Para obter mais informações sobre o anti-phishing no Office 365, consulte [set up anti-phishing and anti-phishing Policies](../security/office-365-security/set-up-anti-phishing-policies.md).<br/><br/><sup>2</sup> para recriar esta política de alerta, siga as orientações da nota de rodapé anterior, mas escolha representação do usuário como a única tecnologia de detecção.

A atividade incomum monitorada por algumas das políticas internas é baseada no mesmo processo da configuração de limite de alerta descrita anteriormente. A Microsoft estabelece um valor de linha de base que define a frequência normal da atividade "normal". Os alertas são disparados quando a frequência das atividades rastreadas pela política de alerta interna excede muito o valor da linha de base.

## <a name="viewing-alerts"></a>Exibir alertas

Quando uma atividade realizada pelos usuários em sua organização corresponde às configurações de uma política de alerta, um alerta é gerado e exibido na página **exibir alertas** no centro de segurança e conformidade. Dependendo das configurações de uma política de alerta, uma notificação por email também é enviada para uma lista de usuários especificados quando um alerta é disparado. Para cada alerta, o painel na página **exibir alertas** exibe o nome da política de alerta correspondente, a gravidade e a categoria para o alerta (definido na política de alerta) e o número de vezes que uma atividade ocorreu, resultando na geração do alerta. Esse valor é baseado na configuração de limite da política de alerta. O painel também mostra o status de cada alerta. Para obter mais informações sobre como usar a propriedade status para gerenciar alertas, consulte a seção [Managing Alerts](#managing-alerts) .

Para exibir alertas, vá para [https://protection.office.com](https://protection.office.com) e selecione alertas **Alerts** \> **exibir alertas**.

![Na segurança e conformidade, selecione alertas e, em seguida, selecione exibir alertas para exibir alertas](../media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)

Você pode usar os filtros a seguir para exibir um subconjunto de todos os alertas da página **exibir alertas** .

- **Estado.** Use este filtro para mostrar os alertas atribuídos a um status específico. O status padrão é **ativo**. Você ou outros administradores podem alterar o valor de status.

- **Política.** Use este filtro para mostrar os alertas que correspondem à configuração de uma ou mais políticas de alerta. Ou você pode exibir todos os alertas de todas as políticas de alerta.

- **Intervalo de tempo.** Use este filtro para mostrar os alertas que foram gerados dentro de um intervalo de data e hora específico.

- **Gravidade.** Use este filtro para mostrar os alertas atribuídos a uma severidade específica.

- **Categorias.** Use este filtro para mostrar alertas de uma ou mais categorias de alerta.

- **Originais.** Use este filtro para mostrar os alertas acionados pelas políticas de alerta no centro de segurança e conformidade ou alertas disparados pelas políticas de segurança do aplicativo Cloud do Office 365 ou ambos. Para obter mais informações sobre os alertas do Office 365 Cloud app Security, consulte a seção [exibindo os alertas de segurança do Cloud app](#viewing-cloud-app-security-alerts) .

## <a name="alert-aggregation"></a>Agregação de alerta

Quando vários eventos que correspondam às condições de uma política de alerta ocorrem com um curto período de tempo, eles são adicionados a um alerta existente por um processo chamado *agregação de alerta*. Quando um evento dispara um alerta, o alerta é gerado e exibido na página **exibir alertas** e uma notificação é enviada. Se o mesmo evento ocorrer dentro do intervalo de agregação, o Microsoft 365 adiciona detalhes sobre o novo evento ao alerta existente, em vez de acionar um novo alerta. O objetivo da agregação de alerta é ajudar a reduzir o alerta "fatigue" e permitir que você se concentre e tomar medidas em menos alertas para o mesmo evento.

O comprimento do intervalo de agregação depende da sua assinatura do Office 365 ou do Microsoft 365.

|Assinatura|Intervalo de agregação|
|:---------|:---------:|
|Office 365 ou Microsoft 365 E5/G5|1 minuto|
|Plano 2 do Office 365 ATP |1 minuto|
|Complemento de conformidade E5 ou o complemento de descoberta e de auditoria e5|1 minuto|
|Office 365 ou Microsoft 365 E1/F1/G1 ou E3/F3/G3|15 minutos|
|Office 365 ATP plano 1 ou proteção do Exchange Online|15 minutos|
|||

Quando os eventos que correspondem à mesma política de alerta ocorrem no intervalo de agregação, os detalhes sobre o evento subsequente são adicionados ao alerta original. Para todos os eventos, as informações sobre eventos agregados são exibidas no campo detalhes e o número de vezes que um evento ocorreu com o intervalo de agregação é exibido no campo atividade/contagem de ocorrências. Você pode exibir mais informações sobre todas as instâncias de eventos agregados exibindo a lista de atividades.

A captura de tela a seguir mostra um alerta com quatro eventos agregados. A lista de atividades contém informações sobre as quatro mensagens de email relevantes para o alerta.

![Exemplo de agregação de alerta](../media/AggregatedAlertExample.png)

Considere os seguintes aspectos em relação à agregação de alertas:

- Alertas acionados por **uma URL possivelmente mal-intencionada o clique em a política de** [alerta padrão](#default-alert-policies) foi detectada não é agregada. Isso ocorre porque os alertas acionados por essa política são exclusivos para cada usuário e mensagem de email.

- No momento, a propriedade de alerta **contagem de ocorrências** não indica o número de eventos agregados para todas as políticas de alerta. Para alertas disparados por essas políticas de alerta, você pode exibir os eventos agregados clicando em **Exibir lista de mensagens** ou **Exibir atividade** no alerta. Estamos trabalhando para tornar o número de eventos agregados listado na propriedade de alerta **contagem de ocorrências** disponível para todas as políticas de alerta.

## <a name="rbac-permissions-required-to-view-alerts"></a>Permissões de RBAC necessárias para exibir alertas

As permissões de controle de acesso baseado em função (RBAC) atribuídas aos usuários em sua organização determinam quais alertas um usuário pode ver na página **exibir alertas** . Como isso é feito? As funções de gerenciamento atribuídas aos usuários (com base em sua associação em grupos de função no centro de conformidade & segurança) determinam quais categorias de alerta um usuário pode ver na página **exibir alertas** . Aqui estão alguns exemplos:

- Os membros do grupo de função gerenciamento de registros podem exibir apenas os alertas gerados por políticas de alerta atribuídas à categoria de **governança de informações** .

- Os membros do grupo de função Administrador de conformidade não podem exibir alertas gerados por políticas de alerta atribuídas à categoria **Gerenciamento de ameaças** .

- Os membros do grupo de função Gerenciador de descoberta eletrônica não podem exibir nenhum alerta porque nenhuma das funções atribuídas fornece permissão para exibir alertas de qualquer categoria de alerta.

Esse design (baseado nas permissões RBAC) permite que você determine quais alertas podem ser exibidos (e gerenciados) por usuários em funções de trabalho específicas em sua organização.

A tabela a seguir lista as funções necessárias para exibir alertas das seis categorias de alerta diferentes. A primeira coluna nas tabelas lista todas as funções no centro de conformidade de & de segurança.  Uma marca de seleção indica que um usuário atribuído a essa função pode exibir alertas da categoria de alerta correspondente listada na linha superior.

Para ver a qual categoria uma política de alerta padrão é atribuída, confira a tabela na seção [políticas de alerta padrão](#default-alert-policies) .

|Função|Governança de informações|Prevenção contra perda de dados|Fluxo de emails|Permissões|Gerenciamento de ameaças|Outros|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Logs de auditoria|||||||
|Gerenciamento de casos|||||||
|Administrador de Conformidade|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Pesquisa de Conformidade|||||||
|Gerenciamento de dispositivo|||||||
|Gerenciamento de descarte|||||||
|Gerenciamento de conformidade de DLP||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||||
|Exportar|||||||
|Retenção|||||||
|Gerenciar Alertas||||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Configuração da organização||||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Visualização|||||||
|Gerenciamento de registros|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Gerenciamento de retenção|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Analisar|||||||
|Descriptografia do RMS|||||||
|Gerenciamento de função||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|Pesquisa e limpeza|||||||
|Administrador de Segurança||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Leitor de segurança||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|Exibição da garantia de serviço|||||||
|Administrador de análise de supervisão|||||||
|Logs de auditoria somente para exibição|||||||
|Gerenciamento de dispositivos somente exibição|||||||
|Somente exibição Gerenciamento de conformidade DLP||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||||
|Somente exibição Gerenciar alertas||||||![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|Destinatários Somente para Exibição|||  ![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||
|Gerenciamento de registros somente de exibição|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|Gerenciamento de retenção somente para exibição|![Marca de seleção](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||||||
|||||||

> [!TIP]
> Para exibir as funções atribuídas a cada um dos grupos de função padrão, execute os seguintes comandos no PowerShell do centro de conformidade & segurança:
> 
> ```powershell
> $RoleGroups = Get-RoleGroup
> ```
> 
> ```powershell
> $RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
> ```
> 
> Você também pode exibir as funções atribuídas a um grupo de função no centro de conformidade de & de segurança. Vá até a página **permissões** e selecione um grupo de função. As funções atribuídas estão listadas na página do menu de atalho.

## <a name="managing-alerts"></a>Gerenciar alertas

Após os alertas terem sido gerados e exibidos na página **exibir alertas** no centro de conformidade e segurança, você pode fazer a triagem, investigar e resolvê-los. Veja algumas tarefas que você pode executar para gerenciar alertas.

- **Atribua um status a alertas.** Você pode atribuir um dos seguintes status a alertas: **ativo** (o valor padrão), **investigando**, **resolvido**ou **Descartado**. Em seguida, você pode filtrar essa configuração para exibir alertas com a mesma configuração de status. Essa configuração de status pode ajudar a acompanhar o processo de gerenciamento de alertas.

- **Exibir detalhes do alerta.** Você pode selecionar um alerta para exibir uma página de submenu com detalhes sobre o alerta. As informações detalhadas dependem da política de alerta correspondente, mas normalmente incluem o seguinte: nome da operação real que disparou o alerta (como um cmdlet), uma descrição da atividade que disparou o alerta, o usuário (ou a lista de usuários) que disparou o alerta e o nome (e o link para) da política de alerta correspondente.

  - O nome da operação real que disparou o alerta, como um cmdlet ou uma operação de log de auditoria.

  - Uma descrição da atividade que disparou o alerta.

  - O usuário que disparou o alerta. Isso é incluído apenas para políticas de alerta que são configuradas para controlar um único usuário ou uma única atividade.

  - O número de vezes que a atividade rastreada pelo alerta foi executada. Esse número pode não coincidir com o número real de alertas relacionados listados na página exibir alertas, pois mais alertas podem ter sido disparados.

  - Um link para uma lista de atividades que inclui um item para cada atividade que foi executada que disparou o alerta. Cada entrada dessa lista identifica quando a atividade ocorreu, o nome da operação real (como "filedelete") e o usuário que realizou a atividade, o objeto (como um arquivo, uma ocorrência de descoberta eletrônica ou uma caixa de correio) em que a atividade foi executada e o endereço IP do computador do usuário. Para alertas relacionados a malware, esses links para uma lista de mensagens.

  - O nome (e o link para) da política de alerta correspondente.

- **Suprimir notificações por email.** Você pode desativar (ou suprimir) notificações por email da página de menu de um alerta. Quando você suprimir notificações por email, a Microsoft não enviará notificações quando atividades ou eventos que corresponderem às condições da política de alerta. Mas os alertas serão disparados quando as atividades realizadas pelos usuários atenderem às condições da política de alerta. Você também pode desativar as notificações por email editando a política de alerta.

- **Resolver alertas.** Você pode marcar um alerta como resolvido na página do menu de alerta (que define o status do alerta como **resolvido**). A menos que você altere o filtro, os alertas resolvidos não são exibidos na página **exibir alertas** .

## <a name="viewing-cloud-app-security-alerts"></a>Exibindo alertas do Cloud app Security

Os alertas que são acionados pelas políticas de segurança do aplicativo Cloud do Office 365 agora são exibidos na página **exibir alertas** no centro de segurança e conformidade. Isso inclui alertas disparados por políticas de atividade e alertas disparados por políticas de detecção de anomalias no Office 365 Cloud app Security. Isso significa que você pode exibir todos os alertas no centro de conformidade e segurança. O Office 365 Cloud app Security só está disponível para organizações com uma assinatura do Office 365 Enterprise E5 ou do Office 365 US governos do governo dos EUA. Para obter mais informações, consulte [Overview of Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

As organizações que têm o Microsoft Cloud app Security como parte de uma assinatura Enterprise Mobility + Security E5 ou como um serviço autônomo também podem exibir os alertas de segurança do aplicativo na nuvem que estão relacionados aos aplicativos e serviços do Office 365 no centro de conformidade e segurança do &.

Para exibir apenas os alertas de segurança do Cloud app no centro de segurança e conformidade, use o filtro de **origem** e selecione **Cloud app Security**.

![Usar o filtro de origem para exibir somente os alertas de segurança do aplicativo na nuvem](../media/FilterCASAlerts.png)

Semelhante a um alerta disparado por uma política de alerta no centro de segurança e conformidade, você pode selecionar um alerta de segurança do Cloud app para exibir uma página de submenu com detalhes sobre o alerta. O alerta inclui um link para exibir os detalhes e gerenciar o alerta no portal do Cloud app Security e um link para a política de segurança de aplicativo na nuvem correspondente que disparou o alerta. Consulte [monitorar alertas no Cloud app Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts).

![Detalhes do alerta contêm links para o portal do Cloud app Security](../media/CASAlertDetail.png)

> [!IMPORTANT]
> Alterar o status de um alerta do Cloud app Security no centro de segurança e conformidade não atualizará o status de resolução para o mesmo alerta no portal do Cloud app Security. Por exemplo, se você marcar o status do alerta como **resolvido** no centro de segurança e conformidade, o status do alerta no portal de segurança do aplicativo na nuvem não será alterado. Para resolver ou descartar um alerta de segurança do aplicativo na nuvem, gerencie o alerta no portal do Cloud app Security.
