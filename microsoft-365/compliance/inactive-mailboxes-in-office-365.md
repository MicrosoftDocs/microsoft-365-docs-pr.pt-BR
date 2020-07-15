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
description: Saiba como reter o conteúdo de caixa de correio para funcionários antigos ao transformar a caixa de correio em uma caixa de correio inativa.
ms.openlocfilehash: baa2daebe65142743df95762a3dcd780d5069c7f
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126742"
---
# <a name="overview-of-inactive-mailboxes"></a>Visão geral de caixas de correio inativas

Sua organização, talvez seja necessário reter email antigos empregados depois que deixam a organização. Dependendo dos requisitos de retenção da sua organização, você pode precisar manter o conteúdo de caixa de correio para alguns meses ou anos após o término de emprego ou você pode precisar manter o conteúdo de caixa de correio indefinidamente. Independentemente de quanto tempo você precisa para reter o email, você pode criar caixas de correio inativas para manter a caixa de correio de antigos funcionários. 
  
## <a name="what-are-inactive-mailboxes"></a>Cite caixas de correio inativas.

Quando um funcionário deixa sua organização (ou fica em uma licença estendida de ausência), você pode remover a conta do Microsoft 365. Os dados de caixa de correio do funcionário são mantidos por 30 dias após a conta ser removida. Durante esse período, você ainda pode recuperar os dados da caixa de correio, desfazendo a exclusão da conta. Após 30 dias, os dados são removidos permanentemente.
  
Mas se sua organização precisar reter o conteúdo de caixa de correio para ex-funcionários, você poderá transformar a caixa de correio em uma caixa de correio inativa, colocando a caixa de correio em retenção de litígio ou aplicando uma política de retenção da Microsoft 365 à caixa de correio no centro de conformidade e segurança do & e, em seguida, removendo a conta do Microsoft 365 correspondente. O conteúdo de uma caixa de correio inativa é mantido por toda a duração da retenção de litígio na caixa de correio ou no período de retenção da política de retenção aplicado antes da caixa de correio ser excluída. You can still recover the corresponding user account for a 30-day period. No entanto, após 30 dias, a caixa de correio inativa é mantida no Microsoft 365 até que a política de retenção ou bloqueio seja removida. 
  
> [!IMPORTANT]
> Como continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange. Isso significa que você deve usar as políticas de retenção de litígio e o Microsoft 365 para criar uma caixa de correio inativa. A partir de 1º de julho de 2020, você não poderá criar novos bloqueios in-loco no Exchange Online. Mas você ainda poderá alterar a duração da retenção de um bloqueio in-loco colocado em uma caixa de correio inativa. No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da retenção. Você só poderá excluir uma caixa de correio inativa removendo o bloqueio in-loco. As caixas de correio inativas existentes que estão no bloqueio in-loco ainda serão preservadas até que a retenção seja removida. Para obter mais informações sobre quando as suspensões in-loco serão desativadas, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
## <a name="inactive-mailboxes-and-microsoft-365-retention-policies"></a>Caixas de correio inativas e políticas de retenção do Microsoft 365

Além da retenção de litígio, o uso do novo recurso de política de retenção do Microsoft 365 no centro de conformidade do & de segurança é outra maneira de tornar uma caixa de correio inativa. To use a retention policy to make an inactive mailbox: 
  
- Ela deve ser configurada para reter conteúdo ou reter e, em seguida, excluir conteúdo. Se uma política de retenção estiver configurada apenas para excluir conteúdo, uma caixa de correio à qual a política é aplicada não se tornará inativa quando a caixa de correio for excluída.

- Ele deve ser aplicadas a caixas de correio do Exchange ou locais de Skype for Business (porque o conteúdo relacionado à Skype é armazenado na caixa de correio do usuário).
  
- Pode ser baseado em consulta para que ele mantém somente os itens que correspondem a uma consulta de pesquisa.

Para obter mais informações sobre políticas de retenção, consulte [saiba mais sobre políticas de retenção e rótulos de retenção](retention.md).
  
Se você usar uma política de retenção para criar uma caixa de correio inativa, a Microsoft 365 continuará processando a política de retenção na caixa de correio inativa. Isso significa que se a política de retenção é configurada para manter e excluir conteúdo, itens serão movidos para a pasta itens recuperáveis quando a duração da retenção expira e eventualmente removidos da caixa de correio inativa. Se a política de retenção não estiver configurada para itens excluídos, os itens que não foram excluídos permanentemente pelo usuário (antes de a caixa de correio ter sido tornado inativa) não serão movidos para a pasta itens recuperáveis e serão retidos indefinidamente após a caixa de correio se tornar inativa. 
  
Você pode considerar a criação de uma política de retenção do Microsoft 365 especificamente para caixas de correio inativas. Aqui estão alguns motivos para fazer isso e coisas em mente.
  
- Você pode configurar a política de retenção para reter somente desde que o necessário para atender aos requisitos da sua organização para ex-funcionários de conteúdo de caixa de correio.

- É uma boa maneira de identificar caixas de correio inativas porque a política de retenção só será aplicada a caixas de correio inativas.

- Você pode identificar rapidamente a política de retenção atribuída às caixas de correio inativas em sua organização. Isso facilita a alteração das configurações de retenção (ou exclusão), se necessário. Isso também facilitará a exclusão permanente de uma caixa de correio inativa, pois você poderá removê-la da política usando o centro de conformidade do & de segurança. Caso contrário, você terá que usar o PowerShell do Exchange Online para remover uma retenção de litígio de uma caixa de correio inativa ou usar o PowerShell de segurança & o centro de conformidade para excluir uma caixa de correio inativa de uma política de retenção da Microsoft 365 em toda a organização.
    
- Se você criar uma política de retenção do Microsoft 365 especificamente para caixas de correio inativas, poderá adicionar um máximo de 1.000 caixas de correio à política. Se você for uma organização de grande porte, talvez seja necessário criar mais de uma política de retenção da Microsoft 365 para usar para caixas de correio inativas.

> [!CAUTION]
> Se você usar uma política de retenção para tornar uma caixa de correio inativa, não altere nem remova o nome principal do usuário (UPN) para a caixa de correio antes de excluir a conta de usuário correspondente. Além disso, não altere o endereço SMTP principal (derivado do UPN) ou remova esse endereço de email da lista de endereços SMTP secundários associados à caixa de correio antes de tornar a caixa de correio inativa. Se você alterar o UPN ou endereços de email (que foram atribuídos à caixa de correio no momento em que a política de retenção foi aplicada a ela) e excluir a conta de usuário para tornar a caixa de correio inativa, não será possível excluir a caixa de correio inativa quando não precisar mais mantê-la. Isso ocorre porque você não pode remover a caixa de correio inativa da política de retenção usando um UPN ou endereço de email (para identificar a caixa de correio inativa) que é diferente daqueles que existiam quando a política de retenção foi inicialmente aplicada à caixa de correio. Para obter mais informações sobre como excluir caixas de correio inativas, consulte [excluir uma caixa de correio inativa no Office 365](delete-an-inactive-mailbox.md).
  
## <a name="inactive-mailboxes-and-ediscovery-case-holds"></a>Caixas de correio inativas e isenções casos de eDiscovery

Se uma retenção associada a uma ocorrência de descoberta eletrônica no centro de conformidade do & de segurança for colocada em uma caixa de correio e a caixa de correio ou a conta do usuário for excluída, a caixa de correio se tornará inativa. However, we don't recommend using eDiscovery case holds to make a mailbox inactive. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed. In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and then the hold is released or the eDiscovery case is closed (or deleted), the inactive mailbox will be permanently deleted. Além disso, você não pode criar um bloqueio de descoberta eletrônica baseado em tempo. Isso significa que o conteúdo em uma caixa de correio inativa é mantido para sempre ou até que a retenção seja removida e a caixa de correio inativa seja excluída. Portanto, é recomendável usar uma retenção de litígio ou uma política de retenção para caixas de correio inativas.
  
Para obter mais informações sobre ocorrências de descoberta eletrônica e isenções, consulte [casos de descoberta eletrônica](ediscovery-cases.md).

## <a name="inactive-mailboxes-and-labels"></a>Caixas de correio inativas e rótulos

Os rótulos de retenção ajudam a classificar dados de email em sua organização para governança e a impor regras de retenção com base nessa classificação. Um rótulo de retenção pode ser aplicado a um item de email manualmente por usuários ou automaticamente por administradores, e um item de email só pode ter um rótulo único atribuído a ele. Se um único item de email na caixa de correio de um usuário tiver um rótulo atribuído a ele (e ele estiver configurado para reter ou reter e excluir o item) e a caixa de correio ou a conta do usuário for excluída, a caixa de correio se tornará uma caixa de correio inativa. Semelhante às isenções de ocorrências de descoberta eletrônica, não recomendamos o uso de rótulos de retenção para tornar uma caixa de correio inativa. Em vez disso, recomendamos que você use uma retenção de litígio ou uma política de retenção. No caso de rótulos de retenção, você pode não perceber que um rótulo de retenção foi aplicado a um item de email e, em seguida, tornar uma caixa de correio inativa inativa ao excluir a conta do usuário. 
  
Para obter mais informações sobre políticas de retenção e rótulos de retenção, consulte [saiba mais sobre políticas de retenção e rótulos de retenção no Office 365](retention.md).
  
## <a name="inactive-mailboxes-and-auto-expanding-archives"></a>Caixas de correio inativas e arquivos de expansão automática

Uma caixa de correio inativa configurada com um arquivo morto de expansão automática não pode ser recuperada ou restaurada. Em situações em que é necessário recuperar dados de uma caixa de correio inativa com um arquivo de expansão automática, recomendamos que você use a ferramenta de pesquisa de conteúdo para exportar os dados da caixa de correio e, em seguida, importá-los para outra caixa de correio. Para obter instruções detalhadas de pesquisa de uma caixa de correio inativa e exportar os resultados da pesquisa, consulte:

- [Pesquisa de Conteúdo no Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search)

- [Exportar resultados de pesquisa de conteúdo](https://docs.microsoft.com/microsoft-365/compliance/export-search-results)

## <a name="inactive-mailboxes-and-exchange-mrm-retention-policies"></a>Caixas de correio inativas e políticas de retenção de MRM do Exchange

If an Exchange retention policy (the Messaging Records Management, or MRM, feature in Exchange Online) was applied to mailbox when it was made inactive, any deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy will be moved to the Recoverable Items folder when the retention period expires. Those items are purged from the inactive mailbox when the hold duration expires. If a hold duration isn't specified for the inactive mailbox, items in the Recover Items folder will be retained indefinitely. 
  
Por outro lado, quaisquer políticas de arquivamento (que são marcas de retenção configuradas com uma ação de retenção **MoveToArchive** ) que estão incluídas na política de retenção atribuída a uma caixa de correio inativa serão ignoradas. Isso significa que os itens em uma caixa de correio inativa que estão marcados com uma política de arquivo morto permanecem na caixa de correio principal quando o período de retenção expira. Elas não serão movidas para a caixa de correio de arquivo morto ou para a pasta itens recuperáveis na caixa de correio de arquivo morto. Eles serão mantidos indefinidamente. 
  
## <a name="creating-an-inactive-mailbox"></a>Criando uma caixa de correio inativa

Para tornar uma caixa de correio inativa, ela deve receber uma licença do Exchange Online Plan 2 (ou uma licença do plano 1 do Exchange Online com uma licença de complemento de arquivamento do Exchange Online) para que uma retenção de litígio ou uma política de retenção do Microsoft 365 possa ser aplicada à caixa de correio antes de ser excluída. Depois que a caixa de correio for excluída, qualquer licença do Exchange Online associada a ela estará disponível para ser atribuída a um novo usuário.
  
A tabela a seguir resume o processo para tornar uma caixa de correio inativa para cenários de retenção diferente. Para obter mais informações, consulte [gerenciar caixas de correio inativas](create-and-manage-inactive-mailboxes.md).
  
|**Para...**|**Faça isso …**|**Resultado**|
|:-----|:-----|:-----|
|Manter o conteúdo de caixa de correio indefinidamente depois que um funcionário deixa a organização  <br/> | Coloque a caixa de correio em retenção de litígio ou aplique uma política de retenção da Microsoft 365 (que é configurada para reter conteúdo) para a caixa de correio.  <br/>  Não especifique uma duração de retenção para a retenção de litígio ou não configure a política de retenção para excluir itens. Como alternativa, você pode usar uma política de retenção que mantém os itens para sempre.  <br/>  Remova a conta do usuário do Microsoft 365.  <br/> |Todo o conteúdo da caixa de correio inativa, incluindo itens na pasta itens recuperáveis, é retido indefinidamente.  <br/> |
|Manter o conteúdo de caixa de correio por um período específico após um funcionário deixa a organização e exclua-  <br/> | Aplicar uma política de retenção da Microsoft 365 à caixa de correio.  <br/>  Configure a política de retenção para reter e, em seguida, excluir itens quando o período de retenção expirar.  <br/>  Remova a conta do usuário do Microsoft 365.  <br/> |Quando o período de retenção de um item de caixa de correio expira, o item é movido para a pasta itens recuperáveis e, em seguida, é excluído permanentemente (removido) da caixa de correio inativa quando o período de retenção do item excluído (para caixas de correio do Exchange) expira. O período de retenção da política de retenção do Microsoft 365 pode ser configurado com base na data original em que um item de caixa de correio foi recebido ou criado, ou quando foi modificado pela última vez.  <br/> |
   
**Observação:** Se uma retenção de litígio já estiver em uma caixa de correio ou se uma política de retenção do Microsoft 365 (configurada para reter ou reter e excluir conteúdo) já estiver aplicada à caixa de correio, tudo o que você precisará é excluir a conta de usuário correspondente para criar uma caixa de correio inativa. 
  
## <a name="managing-inactive-mailboxes"></a>Gerenciando caixas de correio inativas

Depois de fazer uma caixa de correio inativas, você pode executar várias tarefas de gerenciamento em caixas de correio inativas.
  
- **Alterar a duração da retenção de uma caixa de correio inativa.** Depois que uma caixa de correio for desativada, você poderá alterar a duração da retenção de litígio ou a política de retenção do Microsoft 365 aplicada à caixa de correio inativa. Para obter os procedimentos passo a passo, consulte [alterar a duração da retenção de uma caixa de correio inativa](change-the-hold-duration-for-an-inactive-mailbox.md).

  > [!NOTE]
  > Você não pode aplicar outras políticas de retenção a uma caixa de correio inativa. Você só pode alterar a duração da retenção de uma política de retenção existente aplicada à caixa de correio inativa.
    
- **Recuperar uma caixa de correio inativa.** Se um antigo funcionário (ou um funcionário em uma licença de ausência) retornar à sua organização, ou se um novo funcionário for contratado para tomar as responsabilidades do cargo do funcionário anterior, você poderá recuperar o conteúdo da caixa de correio inativa. Ao recuperar uma caixa de correio inativa, a caixa de correio é convertida em uma nova caixa de correio, o conteúdo e a estrutura de pastas da caixa de correio inativa são mantidos e a caixa de correio é vinculada a uma nova conta de usuário. Após sua recuperação, a caixa de correio inativa deixa de existir. Para obter os procedimentos passo a passo e informações sobre o que acontece quando você recupera uma caixa de correio inativa, consulte [recuperar uma caixa de correio inativa](recover-an-inactive-mailbox.md).

  > [!NOTE]
  > Se você recuperar uma caixa de correio inativa que foi atribuída a uma política de retenção com bloqueio de preservação (chamada de *política de retenção bloqueada*), a caixa de correio recuperada será atribuída à mesma política de retenção bloqueada. Se você recuperar uma caixa de correio inativa que foi atribuída a uma política de retenção sem bloqueio de preservação, a caixa de correio recuperada será removida da política de retenção desbloqueada. No entanto, a retenção de litígio está habilitada na caixa de correio recuperada para impedir a exclusão de conteúdo de caixa de correio com base em todas as políticas de retenção de toda a organização que excluem conteúdo mais antigo que uma idade específica.

- **Restaurar uma caixa de correio inativa.** Se outro funcionário tomar as responsabilidades de trabalho de um funcionário antigo ou se outra pessoa precisar acessar o conteúdo da caixa de correio inativa, você poderá restaurar (ou mesclar) o conteúdo da caixa de correio inativa para uma caixa de correio existente. Quando você restaura uma caixa de correio inativa, o conteúdo é copiado para outra caixa de correio. A caixa de correio inativa é mantida e permanece uma caixa de correio inativa. A caixa de correio inativa ainda pode ser pesquisada usando ferramentas de descoberta eletrônica, seu conteúdo pode ser restaurado para outra caixa de correio e pode ser recuperado ou excluído mais tarde. Para obter os procedimentos passo a passo, consulte [restaurar uma caixa de correio inativa](restore-an-inactive-mailbox.md).
    
- **Excluir uma caixa de correio inativa.** Quando você não precisa mais reter o conteúdo de uma caixa de correio inativa, é possível excluí-la permanentemente removendo todas as políticas de retenção ou de retenções da Microsoft 365 aplicadas à caixa de correio inativa. Se uma caixa de correio foi feita inativa mais de 30 dias atrás, ele será marcado para exclusão permanente depois de remover o bloqueio. Se a caixa de correio foi feita inativa nos últimos 30 dias, você pode torná-la ativa novamente após remover a política de retenção ou de espera. Para obter os procedimentos passo a passo, consulte [excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md).
