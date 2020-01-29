---
title: Encontre e investigue emails mal-intencionados que foram entregues no Office 365
keywords: TIMailData-inline, incidente de segurança, incidente, ATP PowerShell, malware de email, usuários comprometidos, golpes por email, malware de email, ler cabeçalhos de email, ler cabeçalhos, abrir cabeçalhos de email
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Saiba como usar os recursos de investigação e resposta contra ameaças para encontrar e investigar emails mal-intencionados.
ms.openlocfilehash: f2eadfaf23c4485e6b50b6550f0a884690a79548
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572978"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Encontre e investigue emails mal-intencionados que foram entregues no Office 365

A [proteção avançada contra ameaças do Office 365](office-365-atp.md) permite investigar as atividades que colocam as pessoas da sua organização em risco e realizar ações para proteger sua organização. Por exemplo, se você fizer parte da equipe de segurança da sua organização, poderá encontrar e investigar mensagens de email suspeitas que foram entregues. Você pode fazer isso usando o [Explorador de ameaças (ou detecções em tempo real)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Antes de começar...

Verifique se os seguintes requisitos são atendidos:
  
- Sua organização tem a [proteção avançada contra ameaças do Office 365](office-365-atp.md) e as [licenças são atribuídas aos usuários](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- O [log de auditoria do Office 365](../../compliance/turn-audit-log-search-on-or-off.md) está ativado para sua organização. 
    
- Sua organização tem políticas definidas para antispam, anti-malware, anti-phishing e assim por diante. Confira [proteção contra ameaças no Office 365](protect-against-threats.md).
    
- Você é um administrador global do Office 365 ou tem o administrador de segurança ou a função de pesquisa e limpeza atribuída no centro de &amp; conformidade de segurança. Consulte [permissões no centro de conformidade de &amp; segurança do Office 365](permissions-in-the-security-and-compliance-center.md). Para algumas ações, você também deve ter uma nova função de visualização atribuída. 

#### <a name="preview-role-permissions"></a>Visualizar permissões de função

Para executar determinadas ações, como exibir cabeçalhos de mensagens ou baixar conteúdo de mensagens de email, você deve ter uma nova função chamada *Preview* adicionada a outro grupo de função apropriado do Office 365. A tabela a seguir esclarece as funções e permissões necessárias.

|Atividade  |Grupo de função |Função prévia necessária?  |
|---------|---------|---------|
|Usar o explorador de ameaças (e detecções em tempo real) para analisar ameaças     |Administrador Global do Office 365 <br> Administrador de Segurança <br> Leitor de segurança     | Não   |
|Usar o explorador de ameaças (e detecções em tempo real) para exibir cabeçalhos para mensagens de email, bem como para visualizar e baixar mensagens de email em quarentena    |Administrador Global do Office 365 <br> Administrador de Segurança <br>Leitor de segurança   |       Não  |
|Usar o explorador de ameaças para exibir cabeçalhos e baixar mensagens de email entregues a caixas de correio     |Administrador Global do Office 365 <br>Administrador de Segurança <br> Leitor de segurança <br> Visualização   |   Sim      |

> [!NOTE]
> *Preview* é uma função e não um grupo de função; a função Preview deve ser adicionada a um grupo de função existente para o Office 365. A função de administrador global do Office 365 é atribuída ao centro de administração[https://admin.microsoft.com](https://admin.microsoft.com)do Microsoft 365 (), e as funções de administrador de segurança e leitor de segurança são atribuídas no[https://protection.office.com](https://protection.office.com)centro de conformidade & segurança do Office 365 (). Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Localizar e excluir emails suspeitos que foram entregues

O Gerenciador de ameaças é um poderoso relatório que pode atender a vários propósitos, como localizar e excluir mensagens, identificar o endereço IP de um remetente de email mal-intencionado ou iniciar um incidente para investigação adicional. O procedimento a seguir se concentra no uso do Explorer para localizar e excluir emails mal-intencionados de caixas de correio de destinatários.

1. Acesse [https://protection.office.com](https://protection.office.com) e entre usando sua conta corporativa ou de estudante para o Office 365. Isso leva você para o centro &amp; de conformidade de segurança. 
    
2. No painel de navegação à esquerda, escolha **Gerenciador**de **Gerenciamento** \> de ameaças.

    ![Explorer com ação de entrega e campos de local de entrega.](../media/ThreatExFields.PNG)

    Você pode observar a nova coluna **especial de ações** . Esse recurso é destinado a informar aos administradores o resultado do processamento de um email. A coluna **especial ações** pode ser acessada no mesmo lugar que a **ação de entrega** e o local de **entrega**. Ações especiais podem ser atualizadas no final da linha do tempo de email do explorador de ameaças, que é um novo recurso destinado a tornar a experiência de busca melhor para administradores.

3. Para exibir uma linha do tempo de email, clique no assunto de uma mensagem de email e clique em **linha do tempo de email**. (Ele aparece entre outros títulos no painel, como **Resumo** ou **detalhes**).

    Depois de abrir a linha do tempo de email, você deverá ver uma tabela que informa os eventos de envio de entrega para esse email. Caso não haja mais eventos para o email, você verá um único evento para a entrega original que diz um resultado como **bloqueado** com um veredicto como **phishing**. A guia também tem a opção de exportar toda a linha do tempo de email, e isso exporta todos os detalhes na guia e os detalhes no email (coisas como assunto, remetente, destinatário, rede e ID da mensagem).

    A linha do tempo de email reduz a randomização porque há menos tempo gasto na verificação de locais diferentes para tentar entender os eventos que ocorreram desde que o email chegou. Quando vários eventos ocorrem ou próximos ao mesmo tempo em um email, esses eventos aparecem em um modo de exibição de linha do tempo. 
    
    Alguns eventos que ocorrem após a entrega para seus emails são capturados na coluna **ações especiais** . Combinar as informações da linha do tempo de email juntamente com ações especiais realizadas no email post-Delivery fornece aos administradores informações sobre como suas políticas funcionam, onde o email foi finalmente encaminhado e, em alguns casos, qual era a avaliação final. 

4. No menu **Exibir** , escolha **todos os emails**.

    ![Usar o menu Exibir para escolher entre relatórios de email e conteúdo](../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Observe os rótulos que aparecem no relatório, como **entregue**, **desconhecido**ou **entregue ao lixo eletrônico**.

    ![Explorador de ameaças mostrando dados para todos os emails](../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Dependendo das ações que foram tomadas nas mensagens de email da sua organização, você poderá ver outros rótulos, como **bloqueados** ou **substituídos**.)
    
6. No relatório, escolha **entregue** para exibir apenas as mensagens de email que acabaram nas caixas de entrada dos usuários.

    ![Clicar em "entregue a lixo eletrônico" remove esses dados da exibição](../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. Abaixo do gráfico, revise a lista de **emails** abaixo do gráfico.

    ![Abaixo do gráfico, exiba uma lista de mensagens de email que foram detectadas](../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. Na lista, escolha um item para exibir mais detalhes sobre a mensagem de email. Por exemplo, você pode clicar na linha de assunto para exibir informações sobre o remetente, destinatários, anexos e outras mensagens de email semelhantes.

    ![Você pode exibir informações adicionais sobre um item](../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. Após exibir informações sobre mensagens de email, selecione um ou mais itens na lista para ativar **+ ações**.
    
10. Use a lista de **ações +** para aplicar uma ação, como **mover para itens excluídos** . Isso exclui as mensagens selecionadas das caixas de correio dos destinatários.

    ![Ao selecionar uma ou mais mensagens de email, você pode escolher entre várias ações disponíveis](../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a>Lidando com mensagens de email suspeitas

Invasores mal-intencionados podem estar enviando emails para pessoas em sua organização em uma tentativa de realizar a Phish de suas credenciais e obter acesso aos seus segredos corporativos. Para ajudar a evitar isso, você usa os serviços de proteção contra ameaças no Office 365, incluindo [proteção do Exchange Online](exchange-online-protection-overview.md) e [proteção avançada contra ameaças](office-365-atp.md). No entanto, ocasionalmente acontece que um invasor envia emails que contenham um link (URL) que só aponta para conteúdo mal-intencionado (como malware). Ou você pode perceber muito tarde que alguém em sua organização foi comprometido e, enquanto eles estavam comprometidos, um invasor usava sua conta para enviar emails para outras pessoas da sua organização. Como parte do lidando com um desses cenários, você pode remover mensagens de email suspeitas de caixas de entrada de usuários. Para fazer isso, você pode usar o [Gerenciador de ameaças](threat-explorer.md).

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a>Localizando mensagens de email redirecionadas após a tomada de ações

O Gerenciador de ameaças fornece à equipe de operações de segurança os detalhes necessários para investigar emails suspeitos. Sua equipe de operações de segurança pode:

- [Exibir os cabeçalhos de email e baixar o corpo do email](#view-the-email-headers-and-download-the-email-body) 

- [Verificar a ação e o local de entrega](#check-the-delivery-action-and-location)

- [Exibir a linha do tempo de seu email](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a>Exibir os cabeçalhos de email e baixar o corpo do email

A capacidade de Visualizar cabeçalhos de email e baixar o corpo de um corpo de email são recursos avançados no explorador de ameaças. [As permissões](permissions-in-the-security-and-compliance-center.md) apropriadas devem ser atribuídas. Consulte [Visualizar permissões de função](#preview-role-permissions).

Para acessar suas opções de cabeçalho de mensagem e download de email, siga estas etapas: 

1. Acesse [https://protection.office.com](https://protection.office.com) e entre usando sua conta corporativa ou de estudante para o Office 365. Isso leva você para o centro &amp; de conformidade de segurança. 
    
2. No painel de navegação à esquerda, escolha **Gerenciador**de **Gerenciamento** \> de ameaças.

3. Clique em um assunto na tabela Gerenciador de ameaças. 

    Isso abre o submenu, onde os links de visualização de cabeçalho e download de email são posicionados.

    ![Submenu do Gerenciador de ameaças com links para baixar e Visualizar na página.](../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> Esse recurso não é exibido para mensagens de email que nunca foram encontradas na caixa de correio de um usuário, o que pode acontecer se um email tiver sido descartado ou se houve falha na entrega. Nos casos em que as mensagens de email foram excluídas das caixas de correio dos usuários, os administradores veem uma mensagem de erro "email não encontrado".

### <a name="check-the-delivery-action-and-location"></a>Verificar a ação e o local de entrega

No [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md), agora você tem as colunas de **ação de entrega** e **local de entrega** em vez da coluna **status de entrega** anterior. Isso resulta em uma imagem mais completa de onde suas mensagens de email estão no terreno. Parte do objetivo dessa alteração é tornar a busca mais fácil para as operações de segurança, mas o resultado líquido é saber o local das mensagens de email de problemas em um relance.

O status de entrega agora é dividido em duas colunas:

- **Ação de entrega** -Qual é o status desse email?

- **Local de entrega** -onde esse email foi roteado como resultado?

A ação de entrega é a ação realizada em um email devido a políticas ou detecções existentes. Veja a seguir as possíveis ações que um email pode executar:

- **Entregue** – o email foi entregue à caixa de entrada ou pasta de um usuário, e o usuário pode acessá-lo diretamente.

- **Lixo eletrônico** – o email foi enviado à pasta de lixo eletrônico ou à pasta excluída do usuário, e o usuário tem acesso a mensagens de email em suas pastas de lixo eletrônico ou excluídas.

- **Bloqueado** – quaisquer mensagens de email em quarentena, que falharam ou foram descartadas. (Isso é completamente inacessível pelo usuário.)

- **Substituído** – qualquer email onde anexos mal-intencionados são substituídos por arquivos. txt que indicam que o anexo era mal-intencionado.
 
O local de entrega mostra os resultados das políticas e detecções que executam post-Delivery. Ele está vinculado a uma ação de entrega. Este campo foi adicionado para dar informações sobre a ação tomada quando um email de problema é encontrado. Estes são os possíveis valores de local de entrega:

- **Caixa de entrada ou pasta** – o email está na caixa de entrada ou em uma pasta (de acordo com suas regras de email).

- **Local ou externo** – a caixa de correio não existe na nuvem, mas está no local.

- **Pasta lixo eletrônico** – o email está na pasta lixo eletrônico de um usuário.

- **Pasta itens excluídos** – o email está na pasta itens excluídos de um usuário.

- **Quarentena** – o email em quarentena e não na caixa de correio de um usuário.

- **Falha** – o email não pôde chegar à caixa de correio.

- **Descartado** – o email é perdido em algum lugar no fluxo de emails.

### <a name="view-the-timeline-of-your-email"></a>Exibir a linha do tempo de seu email
  
A **linha do tempo de email** é um campo no explorador de ameaças que facilita a busca da equipe de operações de segurança. Quando vários eventos ocorrem ou próximos ao mesmo tempo em um email, esses eventos aparecem em um modo de exibição de linha do tempo. Alguns eventos que ocorrem após a entrega para email são capturados na coluna **ações especiais** . A combinação de informações da linha do tempo de uma mensagem de email com qualquer ação especial que tenha sido realizada pela entrega oferece aos administradores informações sobre políticas e tratamento de ameaças (por exemplo, onde o email foi roteado e, em alguns casos, qual era a avaliação final).
  
## <a name="related-topics"></a>Tópicos relacionados

[Proteção Avançada contra Ameaças do Office 365](office-365-ti.md)
  
[Proteção contra ameaças no Office 365](protect-against-threats.md)
  
[Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)
  

