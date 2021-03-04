---
title: Visão geral de caixas de correio inativas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1fbd74e8-7a60-4157-afe8-fe79f05d2038
ms.custom:
- seo-marvel-apr2020
description: Saiba como reter o conteúdo da caixa de correio para ex-funcionários transformando a caixa de correio em uma caixa de correio inativa.
ms.openlocfilehash: 7a10b3327dda148c3328f53826a81464b86a7a0a
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423612"
---
# <a name="overview-of-inactive-mailboxes"></a>Visão geral de caixas de correio inativas

Sua organização, talvez seja necessário reter email antigos empregados depois que deixam a organização. Dependendo dos requisitos de retenção da sua organização, você pode precisar manter o conteúdo de caixa de correio para alguns meses ou anos após o término de emprego ou você pode precisar manter o conteúdo de caixa de correio indefinidamente. Independentemente do tempo necessário para reter emails, você pode criar caixas de correio inativas para reter a caixa de correio de ex-funcionários.

## <a name="what-are-inactive-mailboxes"></a>Cite caixas de correio inativas.

Quando um funcionário sai da sua organização (ou sai com uma licença estendida), você pode remover a conta do Microsoft 365. Os dados de caixa de correio do funcionário são mantidos por 30 dias após a conta ser removida. Durante esse período, você ainda pode recuperar os dados da caixa de correio deselendo a conta. Após 30 dias, os dados serão removidos permanentemente.

Mas, se sua organização precisar reter o conteúdo da caixa de correio para ex-funcionários, você pode transformar a caixa de correio em uma caixa de correio inativa colocando a caixa de correio em Retenção de Litígio ou aplicando uma política de retenção do Microsoft 36 & 5 à caixa de correio no Centro de Conformidade e segurança e removendo a conta correspondente do Microsoft 365. O conteúdo de uma caixa de correio inativa é mantido durante a retenção de litígio colocada na caixa de correio ou o período de retenção da política de retenção aplicada a ela antes da caixa de correio ser excluída. You can still recover the corresponding user account for a 30-day period. No entanto, após 30 dias, a caixa de correio inativa será mantida no Microsoft 365 até que a política de retenção ou retenção seja removida.

> [!IMPORTANT]
> À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ress contração de In-Place no Centro de administração do Exchange. Isso significa que você deve usar retenção de litígio e políticas de retenção do Microsoft 365 para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos In-Place no Exchange Online. Mas você ainda poderá alterar a duração de espera de uma In-Place de espera colocada em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera. Você só poderá excluir uma caixa de correio inativa removendo o In-Place Hold. As caixas de correio inativas existentes que estão em In-Place de espera ainda serão preservadas até que a espera seja removida. Para obter mais informações sobre quando In-Place o holds será retirado, consulte [Retire of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Caixas de correio inativas e políticas de retenção do Microsoft 365

Além da Retenção de Litígio, usar o novo recurso de política de retenção do Microsoft 365 no centro de conformidade do Microsoft 365 é outra maneira de tornar uma caixa de correio inativa. To use a retention policy to make an inactive mailbox:

- Ele precisa ser configurado para reter conteúdo ou reter e, em seguida, excluir conteúdo. Se uma política de retenção for configurada apenas para excluir conteúdo, uma caixa de correio à que a política é aplicada não se tornará inativa quando a conta de usuário for excluída.

- Ele deve ser aplicadas a caixas de correio do Exchange ou locais de Skype for Business (porque o conteúdo relacionado à Skype é armazenado na caixa de correio do usuário).

- Pode ser baseado em consulta para que ele mantém somente os itens que correspondem a uma consulta de pesquisa.

Para obter mais informações sobre políticas de retenção, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)

Se você usar uma política de retenção para tornar uma caixa de correio inativa, o Microsoft 365 continuará a processar a política de retenção na caixa de correio inativa. Isso significa que se a política de retenção é configurada para manter e excluir conteúdo, itens serão movidos para a pasta itens recuperáveis quando a duração da retenção expira e eventualmente removidos da caixa de correio inativa. Se a política de retenção não estiver configurada para itens excluídos, os itens que não foram excluídos permanentemente pelo usuário (antes da caixa de correio ser inativa) não serão movidos para a pasta Itens Recuperáveis e serão mantidos indefinidamente depois que a caixa de correio ficar inativa.

Você pode considerar a criação de uma política de retenção do Microsoft 365 especificamente para caixas de correio inativas. Aqui estão alguns motivos para fazer isso e coisas em mente.

- Você pode configurar a política de retenção para reter somente desde que o necessário para atender aos requisitos da sua organização para ex-funcionários de conteúdo de caixa de correio.

- É uma boa maneira de identificar caixas de correio inativas porque a política de retenção só será aplicada a caixas de correio inativas.

- Você pode identificar rapidamente a política de retenção atribuída a caixas de correio inativas em sua organização. Isso facilita a alteração das configurações de retenção (ou exclusão), se necessário. Ele também facilitará a exclusão permanente de uma caixa de correio inativa, pois você pode removê-la da política usando o Centro de Conformidade & Segurança. Caso contrário, você terá que usar o PowerShell do Exchange Online para remover uma Retenção de Litígio de uma caixa de correio & inativa ou usar o Centro de Conformidade e Segurança do PowerShell para excluir uma caixa de correio inativa de uma política de retenção do Microsoft 365 em toda a organização.

- Se você criar uma política de retenção do Microsoft 365 especificamente para caixas de correio inativas, poderá adicionar no máximo 1.000 caixas de correio à política. Se você for uma organização grande, talvez seja preciso criar mais de uma política de retenção do Microsoft 365 a ser usada para caixas de correio inativas.

> [!CAUTION]
> Se você usar uma política de retenção para tornar uma caixa de correio inativa, não altere ou remova o nome principal do usuário (UPN) para a caixa de correio antes de excluir a conta de usuário correspondente. Além disso, não altere o endereço SMTP principal (derivado do UPN) ou remova esse endereço de email da lista de endereços SMTP secundários associados à caixa de correio antes de tornar a caixa de correio inativa. Se você alterar o UPN ou os endereços de email (que foram atribuídos à caixa de correio no momento em que a política de retenção foi aplicada a ela) e, em seguida, excluir a conta de usuário para tornar a caixa de correio inativa, você não poderá excluir a caixa de correio inativa quando não precisar mais retê-la. Isso porque você não pode remover a caixa de correio inativa da política de retenção usando um UPN ou um endereço de email (para identificar a caixa de correio inativa) diferente das que existiam quando a política de retenção foi aplicada inicialmente à caixa de correio. Para obter mais informações sobre como excluir caixas de correio inativas, consulte Excluir uma caixa de correio [inativa no Office 365](delete-an-inactive-mailbox.md).

## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Caixas de correio inativas e isenções casos de eDiscovery

Se uma responsabilidade associada & a um caso de Descoberta Eletrônico no Centro de Conformidade e Segurança for colocada em uma caixa de correio e, em seguida, a caixa de correio ou a conta do usuário for excluída, a caixa de correio se tornará uma caixa de correio inativa. However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Além disso, você não pode criar uma espera de Descoberta eDiscovery baseada em tempo. Isso significa que o conteúdo em uma caixa de correio inativa será mantido para sempre ou até que a moção seja removida e a caixa de correio inativa seja excluída. Portanto, recomendamos usar uma Retenção de Litígio ou uma política de retenção para caixas de correio inativas.

Para obter mais informações sobre os casos de Descoberta e Resções, consulte [eDiscovery cases](ediscovery-cases.md).

## <a name="inactive-mailboxes-and-labels"></a>Caixas de correio e rótulos inativos

Os rótulos de retenção ajudam você a classificar dados de email em sua organização para governança e impor regras de retenção com base nessa classificação. Um rótulo de retenção pode ser aplicado a um item de email manualmente por usuários ou automaticamente por administradores, e um item de email só pode ter um único rótulo atribuído a ele. Se um único item de email na caixa de correio de um usuário tiver um rótulo atribuído a ele (e ele estiver configurado para reter ou reter e excluir o item) e a caixa de correio ou a conta do usuário for excluída, a caixa de correio se tornará uma caixa de correio inativa. Semelhante ao caso de Descoberta Eletrônico, não recomendamos o uso de rótulos de retenção para tornar uma caixa de correio inativa. Em vez disso, recomendamos que você use uma Retenção de Litígio ou uma política de retenção. No caso de rótulos de retenção, você pode não perceber que um rótulo de retenção foi aplicado a um item de email e, em seguida, inadvertidamente tornar uma caixa de correio inativa ao excluir a conta do usuário.

Para obter mais informações sobre políticas de retenção e rótulos de retenção, consulte Saiba mais sobre políticas de retenção e rótulos de [retenção no Office 365](retention.md).

## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Caixas de correio inativas e arquivos de expansão automática

Uma caixa de correio inativa configurada com um arquivo morto de expansão automática não pode ser recuperada ou restaurada. Em situações em que é necessário recuperar dados de uma caixa de correio inativa com um arquivo morto em expansão automática, recomendamos que você use a ferramenta de pesquisa de conteúdo para exportar os dados da caixa de correio e depois importar para outra caixa de correio. Para obter instruções passo a passo para pesquisar uma caixa de correio inativa e exportar os resultados da pesquisa, consulte:

- [Pesquisa de conteúdo](content-search.md)

- [Exportar resultados da pesquisa de conteúdo](export-search-results.md)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Caixas de correio inativas e políticas de retenção de MRM do Exchange

Se uma política de retenção do Exchange (o recurso Gerenciamento de registros de mensagens ou MRM, no Exchange Online ) foi aplicada à caixa de correio quando ela foi feita inativa, quaisquer políticas de exclusão (que são configuradas com uma ação de retenção **Excluir** as marcas de retenção) continuarão a serem processados na caixa de correio inativa. Isso significa que os itens que estão marcados com uma política de exclusão serão movidos para a pasta itens recuperáveis quando o período de retenção expira. Os itens são removidos da caixa de correio inativa quando a duração da retenção expira. Se um período de retenção não for especificado para a caixa de correio inativa, itens na pasta recuperar itens serão mantidos indefinidamente.

Por outro lado, quaisquer políticas de arquivamento (que são marcas de retenção configuradas com uma ação de retenção **MoveToArchive** ) que estão incluídas na política de retenção atribuída a uma caixa de correio inativa serão ignoradas. Isso significa que os itens em uma caixa de correio inativa marcada com uma política de arquivo morto permanecem na caixa de correio principal quando o período de retenção expira. Elas não serão movidas para a caixa de correio de arquivo morto ou para a pasta itens recuperáveis na caixa de correio de arquivo morto. Eles serão mantidos indefinidamente.

## <a name="creating-an-inactive-mailbox"></a>Criando uma caixa de correio inativa

Para tornar uma caixa de correio inativa, ela deve receber uma licença do Plano 2 do Exchange Online (ou uma licença do Plano 1 do Exchange Online com uma licença de complemento do Arquivamento do Exchange Online) para que uma política de retenção de Litígio ou do Microsoft 365 possa ser aplicada à caixa de correio antes de ser excluída. Depois que a conta de usuário for excluída, qualquer licença do Exchange Online associada à conta de usuário estará disponível para atribuir a um novo usuário.

A tabela a seguir resume o processo para tornar uma caixa de correio inativa para cenários de retenção diferente. Para obter mais informações, consulte [Gerenciar caixas de correio inativas](create-and-manage-inactive-mailboxes.md).

****

|Para...|Faça isso...|Resultado|
|---|---|---|
|Manter o conteúdo de caixa de correio indefinidamente depois que um funcionário deixa a organização|Coloque a caixa de correio em Retenção de Litígio ou aplique uma política de retenção do Microsoft 365 (configurada para reter conteúdo) à caixa de correio. <br/> Não especifique uma duração de retenção para a Retenção de Litígio ou não configure a política de retenção para excluir itens. Como alternativa, você pode usar uma política de retenção que retém itens para sempre. <br/> Remova a conta do Microsoft 365 do usuário.|Todo o conteúdo na caixa de correio inativa, incluindo itens na pasta Itens Recuperáveis, é mantido indefinidamente.|
|Manter o conteúdo de caixa de correio por um período específico após um funcionário deixa a organização e exclua-|Aplique uma política de retenção do Microsoft 365 à caixa de correio. <br/> Configure a política de retenção para reter e exclua itens quando o período de retenção expirar. <br/> Remova a conta do Microsoft 365 do usuário.|Quando o período de retenção de um item de caixa de correio expira, o item é movido para a pasta Itens Recuperáveis e, em seguida, é excluído permanentemente (limpo) da caixa de correio inativa quando o período de retenção de item excluído (para caixas de correio do Exchange) expira. O período de retenção da política de retenção do Microsoft 365 pode ser configurado com base na data original em que um item de caixa de correio foi recebido ou criado ou quando foi modificado pela última vez.|
|

**OBSERVAÇÃO:** Se uma Retenção de Litígio já estiver colocada em uma caixa de correio ou se uma política de retenção do Microsoft 365 (configurada para reter ou reter e excluir conteúdo) já estiver aplicada à caixa de correio, tudo o que você precisa fazer é excluir a conta de usuário correspondente para criar uma caixa de correio inativa.

## <a name="managing-inactive-mailboxes"></a>Gerenciando caixas de correio inativas

Depois de fazer uma caixa de correio inativas, você pode executar várias tarefas de gerenciamento em caixas de correio inativas.

- **Altere a duração de espera para uma caixa de correio inativa.** Depois que uma caixa de correio é inativa, você pode alterar a duração da retenção da Retenção de Litígio ou da política de retenção do Microsoft 365 aplicada à caixa de correio inativa. Para procedimentos passo a passo, consulte [Change the hold duration for an inactive mailbox](change-the-hold-duration-for-an-inactive-mailbox.md).

  > [!NOTE]
  > Não é possível aplicar outras políticas de retenção a uma caixa de correio inativa. Você só pode alterar a duração de retenção de uma política de retenção existente aplicada à caixa de correio inativa.

- **Recupere uma caixa de correio inativa.** Se um ex-funcionário (ou um funcionário em licença) retornar à sua organização ou se um novo funcionário for contratado para assumir as responsabilidades de trabalho do ex-funcionário, você poderá recuperar o conteúdo da caixa de correio inativa. Quando você recupera uma caixa de correio inativa, a caixa de correio é convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e a caixa de correio é vinculada a uma nova conta de usuário. Após sua recuperação, a caixa de correio inativa deixa de existir. Para obter procedimentos passo a passo e informações sobre o que acontece quando você recupera uma caixa de correio inativa, consulte [Recover an inactive mailbox](recover-an-inactive-mailbox.md).

  > [!NOTE]
  > Se você recuperar uma caixa de correio inativa atribuída a uma política de retenção com Bloqueio de Preservação (chamada de política de retenção *bloqueada),* a caixa de correio recuperada será atribuída à mesma política de retenção bloqueada. Se você recuperar uma caixa de correio inativa atribuída a uma política de retenção sem o Bloqueio de Preservação, a caixa de correio recuperada será removida da política de retenção desbloqueada. No entanto, a Retenção de Litígio está habilitada na caixa de correio recuperada para impedir a exclusão do conteúdo da caixa de correio com base em quaisquer políticas de retenção em toda a organização que excluam conteúdo mais antigo do que uma idade específica.

- **Restaure uma caixa de correio inativa.** Se outro funcionário assumir as responsabilidades de trabalho de um ex-funcionário ou se outra pessoa precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Quando você restaura uma caixa de correio inativa, o conteúdo é copiado para outra caixa de correio. A caixa de correio inativa é mantida e permanece uma caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando ferramentas de Descoberta Eletrônico, seu conteúdo pode ser restaurado para outra caixa de correio e pode ser recuperado ou excluído posteriormente. Para procedimentos passo a passo, consulte [Restore an inactive mailbox](restore-an-inactive-mailbox.md).

- **Exclua uma caixa de correio inativa.** Quando você não precisar mais reter o conteúdo de uma caixa de correio inativa, poderá excluí-la permanentemente removendo todas as retenções ou políticas de retenção do Microsoft 365 aplicadas à caixa de correio inativa. Se uma caixa de correio foi feita inativa mais de 30 dias atrás, ele será marcado para exclusão permanente depois de remover o bloqueio. Se a caixa de correio foi feita inativa nos últimos 30 dias, você pode torná-la ativa novamente após remover a política de retenção ou de espera. Para procedimentos passo a passo, consulte [Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md).
