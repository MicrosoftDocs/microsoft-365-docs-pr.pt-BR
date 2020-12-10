---
title: Investigue emails mal-intencionados que foram entregues no Office 365, encontre e investigue emails mal-intencionados
keywords: TIMailData-inline, incidente de segurança, incidente, ATP PowerShell, malware de email, usuários comprometidos, golpes por email, malware de email, ler cabeçalhos de email, ler cabeçalhos, cabeçalhos de email abertos, ações especiais
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3fd2e5c0f75de9a1b942e8f0baa8e9d44843de4
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616519"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Investigue emails mal-intencionados que foram entregues no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft defender para Office 365](office-365-atp.md) permite investigar as atividades que colocam as pessoas de sua organização em risco e realizar ações para proteger sua organização. Por exemplo, se você fizer parte da equipe de segurança da sua organização, poderá encontrar e investigar mensagens de email suspeitas que foram entregues. Você pode fazer isso usando o [Explorador de ameaças (ou detecções em tempo real)](threat-explorer.md).

> [!NOTE]
> Vá para o artigo de correção [aqui](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Antes de começar

Verifique se os seguintes requisitos são atendidos:

- Sua organização tem o [Microsoft defender para Office 365](office-365-atp.md) e as [licenças são atribuídas aos usuários](../../admin/manage/assign-licenses-to-users.md).

- o [log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md) está ativado para sua organização.

- Sua organização tem políticas definidas para antispam, anti-malware, anti-phishing e assim por diante. Confira [proteção contra ameaças no Office 365](protect-against-threats.md).

- Você é um administrador global ou tem o administrador de segurança ou a função de pesquisa e limpeza atribuída no centro de conformidade & segurança. Consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md). Para algumas ações, você também deve ter uma nova função de visualização atribuída.

### <a name="preview-role-permissions"></a>Visualizar permissões de função

Para executar determinadas ações, como exibir cabeçalhos de mensagens ou baixar conteúdo de mensagens de email, você deve ter uma nova função chamada *Preview* adicionada a outro grupo de função apropriado. A tabela a seguir esclarece as funções e permissões necessárias.

****

|Atividade|Grupo de função|Função prévia necessária?|
|---|---|---|
|Usar o explorador de ameaças (e detecções em tempo real) para analisar ameaças |Administrador Global <p> Administrador de Segurança <p> Leitor de segurança|Não|
|Usar o explorador de ameaças (e detecções em tempo real) para exibir cabeçalhos para mensagens de email, bem como para visualizar e baixar mensagens de email em quarentena|Administrador Global <p> Administrador de Segurança <p> Leitor de segurança|Não|
|Usar o explorador de ameaças para exibir cabeçalhos e baixar mensagens de email entregues a caixas de correio|Administrador Global <p> Administrador de Segurança <p> Leitor de segurança <p> Visualização|Sim|
|

> [!NOTE]
> *Preview* é uma função e não um grupo de função; a função Preview deve ser adicionada a um grupo de função existente para o Office 365. A função de administrador global é atribuída ao centro de administração do Microsoft 365 ( <https://admin.microsoft.com> ), e as funções do administrador de segurança e do leitor de segurança são atribuídas no centro de conformidade do & de segurança <https://protection.office.com> . Para saber mais sobre funções e permissões, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="find-suspicious-email-that-was-delivered"></a>Localizar emails suspeitos que foram entregues

O Gerenciador de ameaças é um poderoso relatório que pode atender a vários propósitos, como localizar e excluir mensagens, identificar o endereço IP de um remetente de email mal-intencionado ou iniciar um incidente para investigação adicional. O procedimento a seguir enfoca o uso do Explorer para localizar e excluir emails mal-intencionados das caixas de correio do destinatário.

> [!NOTE]
> Pesquisas padrão no Explorer não incluem atualmente itens zapped.  Isso se aplica a todos os modos de exibição, por exemplo, malware ou phishing. Para incluir itens do zapped, você precisa adicionar uma "ação de entrega" definida para incluir "removido por ZAP". Se você incluir todas as opções, verá todos os resultados da ação de entrega, incluindo os itens do zapped.

1. **Navegue até Gerenciador de ameaças**: Vá para <https://protection.office.com> e entre usando sua conta corporativa ou de estudante para o Office 365. Isso leva você para o centro de conformidade & segurança.

2. No início rápido da navegação à esquerda, escolha Gerenciador de **Gerenciamento de ameaças** \> .

    ![Explorer com ação de entrega e campos de local de entrega.](../../media/ThreatExFields.PNG)

    Você pode observar a nova coluna **especial de ações** . Esse recurso é destinado a informar aos administradores o resultado do processamento de um email. A coluna **especial ações** pode ser acessada no mesmo lugar que a **ação de entrega** e o local de **entrega**. Ações especiais podem ser atualizadas no final da linha do tempo de email do explorador de ameaças, que é um novo recurso destinado a tornar a experiência de busca melhor para administradores.

3. **Modos de exibição no explorador de ameaças**: no menu **Exibir** , escolha **todos os emails**.

    ![Menu Exibir do explorador de ameaças e email-malware, Phish, envios e todas as opções de email, também malware de conteúdo.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    No momento, o modo de exibição de *malware* é o padrão e captura emails onde uma ameaça de malware é detectada. O modo de *Phish* funciona da mesma maneira, para phishing.

    No entanto, *todas as* exibições de email listam todos os emails recebidos pela organização, se as ameaças foram detectadas ou não. Como você pode imaginar, esta é uma grande quantidade de dados, que é o motivo pelo qual este modo de exibição mostra um espaço reservado que faz com que um filtro seja aplicado. (Este modo de exibição está disponível somente para clientes do defender for Office 365 P2.)

    O *modo de exibição envios* mostra todos os emails enviados por administradores ou usuários que foram relatados à Microsoft.

4. **Pesquisar e filtrar no explorador de ameaças**: os filtros aparecem na parte superior da página na barra de pesquisa para ajudar os administradores na sua investigação. Observe que vários filtros podem ser aplicados ao mesmo tempo e vários valores separados por vírgula adicionados a um filtro para restringir a pesquisa. Lembre-se:

    - Os filtros correspondem exatamente à maioria das condições de filtro.
    - O filtro de assunto usa uma consulta contém.
    - Os filtros de URL funcionam com ou sem protocolos (ex. https).
    - O domínio da URL, o caminho da URL e o domínio da URL e os filtros de caminho não exigem um protocolo para filtrar.
    - Você deve clicar no ícone atualizar sempre que alterar os valores de filtro para obter resultados relevantes.

5. **Filtros avançados**: com esses filtros, você pode criar consultas complexas e filtrar seu conjunto de dados. Clicar em *filtros avançados* abre um submenu com opções.

   A filtragem avançada é uma ótima adição aos recursos de pesquisa. Um Boolean **não** filtrado foi introduzido no *destinatário*, *remetente* e *domínio do remetente* para permitir que os administradores investiguem excluindo valores. Essa opção aparece em o parâmetro Selection não *contém nenhum de*. **Não** permitirá que os administradores excluam as caixas de correio de alerta, as caixas de correio de resposta padrão de suas investigações e sejam úteis para casos em que os administradores pesquisam um assunto específico (Subject = "attention"), onde o destinatário pode ser definido como *nenhum de defaultmail \@ contoso.com*. Este é um valor exato de pesquisa.

   ![Os destinatários-' contém nenhum de ' filtro avançado '.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Filtrar por horas* ajudará a equipe de segurança da sua organização a aprofundar-se rapidamente. A duração de tempo mais curta permitida é de 30 minutos. Se você puder restringir a ação suspeita por período de tempo (por exemplo, ocorreu 3 horas atrás), isso limitará o contexto e ajudará a identificar o problema.

   ![A opção filtragem por horas para reduzir a quantidade de dados que as equipes de segurança precisam processar e cuja duração mais curta é de 30 minutos.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campos no Gerenciador de ameaças**: o explorador de ameaças expõe muito mais informações de email relacionadas à segurança, como *ação de entrega*, *local de entrega*, *ação especial*, *direcionalização*, *substituições* e *ameaça de URL*. Também permite que a equipe de segurança da sua organização investigue com maior certeza.

    A *ação de entrega* é a ação realizada em um email devido a políticas ou detecções existentes. Veja a seguir as possíveis ações que um email pode executar:

    - **Entregue** – o email foi entregue à caixa de entrada ou pasta de um usuário, e o usuário pode acessá-lo diretamente.
    - **Lixo eletrônico** (entregue a lixo eletrônico) – o email foi enviado à pasta de lixo eletrônico ou à pasta excluída do usuário, e o usuário tem acesso a mensagens de email em suas pastas de lixo eletrônico ou excluídas.
    - **Bloqueado** – quaisquer mensagens de email em quarentena, que falharam ou foram descartadas. (Isso é completamente inacessível pelo usuário.)
    - **Substituído** – qualquer email onde anexos mal-intencionados são substituídos por arquivos. txt que indicam que o anexo foi mal-intencionado

    **Local de entrega**: o filtro de local de entrega está disponível para ajudar os administradores a entender onde o email mal-intencionado suspeito terminou e quais ações foram tomadas nele. Os dados resultantes podem ser exportados para a planilha. Os locais de entrega possíveis são:

    - **Caixa de entrada ou pasta** – o email está na caixa de entrada ou em uma pasta específica, de acordo com suas regras de email.
    - **Local ou externo** – a caixa de correio não existe na nuvem, mas está no local.
    - **Pasta de lixo eletrônico** – o email está na pasta lixo eletrônico de um usuário.
    - **Pasta itens excluídos** – o email está na pasta itens excluídos de um usuário.
    - **Quarentena** – o email em quarentena e não na caixa de correio de um usuário.
    - **Falha** – o email não pôde chegar à caixa de correio.
    - **Descartado** – o email foi perdido em algum lugar no fluxo de emails.

    **Direcionalidade**: essa opção permite que sua equipe de operações de segurança filtre pelo ' Direction ' que um email provém ou esteja em andamento. Os valores de direcionalização são de *entrada*, de *saída* e de *intra-org* (correspondentes a emails que chegam à sua organização, de fora, enviados à sua organização ou enviados internamente para sua organização, respectivamente). Essas informações podem ajudar as equipes de operações de segurança a falsificação e representação, porque uma incompatibilidade entre o valor de direcionalidade (ex. *Entrada*) e o domínio do remetente (que *parece* ser um domínio interno) será evidente! O valor de direcionalidade é separado e pode ser diferente do rastreamento de mensagens. Os resultados podem ser exportados para a planilha.

    **Substitui**: Este filtro utiliza informações que aparecem na guia detalhes do email e usa-a para expor onde as políticas organizacionais ou de usuário, para permitir e bloquear emails, foram *substituídas*. O aspecto mais importante sobre esse filtro é que ele ajuda a equipe de segurança da sua organização a ver quantos emails suspeitos foram entregues devido à configuração. Isso proporciona a eles uma oportunidade de modificar os bloqueios e, conforme necessário. Esse conjunto de resultados desse filtro pode ser exportado para a planilha.

    ****

    |O explorador de ameaças substitui|O que eles significam|
    |---|---|
    |Permitido pela política da organização|O email foi permitido para a caixa de correio, conforme indicado pela política da organização.|
    |Bloqueado pela política da organização|O email foi impedido de entrega para a caixa de correio, conforme indicado pela política da organização.|
    |Extensão de arquivo bloqueada pela política org|O arquivo foi bloqueado da entrega para a caixa de correio, conforme indicado pela política da organização.|
    |Permitido pela política de usuário|O email foi permitido para a caixa de correio, conforme indicado pela política de usuário.|
    |Bloqueado pela política de usuário|O email foi impedido de entrega para a caixa de correio, conforme indicado pela política de usuário.|
    |

    **Ameaça de URL**: o campo de ameaça de URL foi incluído na guia *detalhes* de um email para indicar a ameaça apresentada por uma URL. As ameaças apresentadas por uma URL podem incluir *malware*, *phishing* ou *spam*, e uma URL sem *ameaça* informará *nenhuma* na seção ameaças.

7. **Exibição de linha do tempo de email**: sua equipe de operações de segurança pode precisar aprofundar-se nos detalhes de email para investigar mais. A linha do tempo de email permite que os administradores exibam ações realizadas em um email da entrega para a entrega. Para exibir uma linha do tempo de email, clique no assunto de uma mensagem de email e clique em linha do tempo de email. (Ele aparece entre outros títulos no painel, como resumo ou detalhes). Esses resultados podem ser exportados para a planilha.

    A linha do tempo de email será aberta para uma tabela que mostra todos os eventos Delivery e post-Delivery para o email. Se não houver mais ações no email, você verá um único evento para a entrega original que declara um resultado, como *bloqueado*, com um veredicto como *Phish*. Os administradores podem exportar toda a linha do tempo de email, incluindo todos os detalhes na guia e email (como assunto, remetente, destinatário, rede e ID da mensagem). A linha do tempo de email reduz a randomização porque há menos tempo gasto na verificação de locais diferentes para tentar entender os eventos que ocorreram desde que o email chegou. Quando vários eventos ocorrem ou próximos ao mesmo tempo em um email, esses eventos aparecem em um modo de exibição de linha do tempo.

8. **Visualizar/baixar**: o Gerenciador de ameaças dá à equipe de operações de segurança os detalhes de que eles precisam para investigar emails suspeitos. Sua equipe de operações de segurança pode:

    - [Verifique a ação e o local de entrega](#check-the-delivery-action-and-location).

    - [Exibir a linha do tempo de seu email](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Verificar a ação e o local de entrega

No [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md), agora você tem as colunas de **ação de entrega** e **local de entrega** em vez da coluna **status de entrega** anterior. Isso resulta em uma imagem mais completa de onde suas mensagens de email estão no terreno. Parte do objetivo dessa mudança é tornar as investigações mais fáceis para as equipes de operações de segurança, mas o resultado líquido é saber o local das mensagens de email de problemas em um relance.

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

> [!IMPORTANT]
> Vá para um tópico de correção [aqui](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Tópicos relacionados

[Corrigir emails mal-intencionados entregues no Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft defender para Office 365](office-365-ti.md)

[Proteção contra ameaças no Office 365](protect-against-threats.md)

[Exibir relatórios do defender para Office 365](view-reports-for-atp.md)
