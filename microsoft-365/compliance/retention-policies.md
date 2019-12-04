---
title: Visão geral de políticas de retenção
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Com uma política de retenção, você pode decidir de forma proativa se deseja reter o conteúdo, excluí-lo ou ambos: reter e em seguida excluir o conteúdo; aplicar uma única política para a organização inteira ou a locais ou usuários específicos; e aplicar uma política a todo o conteúdo ou ao conteúdo que cumpra certas condições.'
ms.openlocfilehash: caeec733b3b5722f25210d0d2566e1dd9a5cd95e
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818983"
---
# <a name="overview-of-retention-policies"></a>Visão geral de políticas de retenção

Para a maioria das organizações, o volume e a complexidade dos dados aumentam diariamente, como emails, documentos, mensagens instantâneas e muito mais. O gerenciamento ou controle efetivo dessas informações é importante porque você precisa:
  
- **Estar em conformidade de forma proativa com as regulamentações do setor e as políticas internas** que exigem a retenção do conteúdo por um período mínimo de tempo, por exemplo, a lei Sarbanes-Oxley, pode exigir que você guarde determinados tipos de conteúdo por sete anos. 
    
- **Reduzir seu risco em caso de litígio ou violação de segurança** excluindo definitivamente o conteúdo antigo que você não tem mais obrigação de guardar. 
    
- **Ajudar a sua organização a compartilhar conhecimento de maneira eficaz e ser mais ágil** garantindo que seus usuários trabalhem apenas com conteúdo atual e relevante para eles. 
    
Uma política de retenção pode ajudá-lo a atingir todos esses objetivos. O gerenciamento de conteúdo normalmente requer duas ações:
  
- **Reter** conteúdo para que ele não seja excluído permanentemente antes do fim do período de retenção. 
    
- **Excluir** conteúdo permanentemente no final do período de retenção. 
    
Com uma política de retenção, você pode:
  
- Decidir proativamente se deseja reter o conteúdo, excluí-lo ou ambos, reter e depois excluir o conteúdo.
    
- Aplicar uma única política para a organização inteira ou locais ou usuários específicos.
    
- Aplicar uma política a todo o conteúdo ou ao conteúdo que respeita determinadas condições, por exemplo, como palavras-chave específicas ou [tipos específicos de informações confidenciais](what-the-sensitive-information-types-look-for.md).
    
Quando o conteúdo está sujeito a uma política de retenção, as pessoas podem continuar editando e trabalhando com o conteúdo como de costume, pois o conteúdo é retido no local, em seu local original. Mas se alguém edita ou exclui um conteúdo sujeito à política, uma cópia é salva em um local seguro, no qual será retido enquanto a política estiver em vigor.
  
Finalmente, algumas organizações talvez precisem cumprir regulamentações, como a Regra 17a-4 da agência Securities and Exchange Commission (SEC), que exige que após uma política de retenção ser ativada, ela não pode ser desativada ou se tornar menos restritiva. Para atender a esse requisito, você pode usar o Bloqueio de Preservação. Após uma política ser bloqueada, ninguém, nem mesmo o administrador, poderá desativar a política ou torná-la menos restritiva.
  
Você cria e gerencia políticas de retenção na:

- Página **Políticas** no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).
- Página **Retenção** em **Governança de informações** no [Centro de Conformidade&amp; e Segurança do Office 365](https://protection.office.com/).
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a>Como funciona uma política de retenção com conteúdo in-loco

Quando você incluir um local como um site ou caixa de correio em uma política de retenção, o conteúdo permanecerá no local original. As pessoas podem continuar a trabalhar com seus documentos ou emails como se nada tivesse mudado. Mas, se elas editarem ou excluírem o conteúdo incluído na política, será mantida uma cópia do conteúdo conforme existia antes da aplicação da política.
  
Para conjuntos de sites do SharePoint, uma cópia do conteúdo original é guardada na biblioteca de retenção para preservação quando os usuários o editam ou o excluem. No caso de emails e pastas públicas, a cópia é mantida na pasta Itens Recuperáveis. Esses locais seguros e o conteúdo retido não ficam visíveis para a maioria das pessoas. Com uma política de retenção, as pessoas nem precisam saber que o conteúdo está sujeito à política.
  
Observações:
  
- O conteúdo do Teams (chat) é armazenado no Exchange, em que a política é aplicada com base no tipo de mensagem (email ou conversas).
    
- Uma política de retenção aplicada a um grupo do Office 365 inclui a caixa de correio do grupo e um site.
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a>Conteúdo em contas do OneDrive e dos sites do SharePoint

Uma política de retenção é aplicada no nível de um conjunto de site. Quando um conjunto de sites do SharePoint ou uma conta do OneDrive é incluído em uma política de retenção, uma biblioteca de retenção para preservação será criada, caso ainda não exista. Você pode ver essa biblioteca na página **Conteúdo do site** no site de nível superior do conjunto de sites. A maioria dos usuários não poderá ver a biblioteca de Retenção para Preservação porque ela só fica visível para os administradores do conjunto de sites.
  
Caso uma pessoa tente alterar ou excluir o conteúdo de um site que esteja sujeito à política de retenção, primeiro a política verificará se o conteúdo foi alterado desde a aplicação da política. Se essa for a primeira alteração desde que a política foi aplicada, a política de retenção copiará o conteúdo na Biblioteca de Retenção para Preservação e, então, permitirá que a pessoa altere ou exclua o conteúdo original. Qualquer conteúdo do conjunto de sites poderá ser copiado para a Biblioteca de Retenção para Preservação, mesmo se o conteúdo não corresponder à consulta usada pela política de retenção.
  
Em seguida, uma tarefa do temporizador limpa a Biblioteca de Retenções para Preservação. A tarefa do temporizador é executada periodicamente e compara todo o conteúdo da biblioteca de Retenção com todas as consultas usadas pelas políticas de retenção no site. A menos que o conteúdo corresponda a pelo menos uma das consultas, a tarefa do temporizador excluirá permanentemente o conteúdo da Biblioteca de Retenções para Preservação.
  
A medida anterior se aplica ao conteúdo existente, na ocasião em que a política de retenção é aplicada. Além disso, qualquer conteúdo novo criado ou adicionado ao conjunto de sites depois que ele for incluído na política será retido após a exclusão. Entretanto, o novo conteúdo não será copiado na biblioteca de retenção para preservação na primeira vez em que for editado, somente quando for excluído. Para reter todas as versões de um arquivo, será necessário ativar o controle de versão. Confira a seção abaixo sobre controle de versão.
  
Observe que o usuário recebe um erro se tentar excluir uma biblioteca, lista, pasta ou um site sujeitos a uma política de retenção. Para excluir uma pasta, o usuário deve mover ou excluir todos os arquivos da pasta que estejam sujeitos à política. Além disso, a Biblioteca de Retenção para Preservação será criada somente quando o primeiro item precisar ser copiado para a biblioteca e não quando a política de retenção for criada. Portanto, para testar a política, primeiro é necessário editar ou excluir um documento em um site sujeito à política e, em seguida, navegar até a Biblioteca de Retenção para Preservação para exibir a cópia retida.
  
Depois que uma política de retenção é atribuída a uma conta do OneDrive ou site do SharePoint, o conteúdo pode seguir um destes dois caminhos:

![Diagrama do ciclo de vida de conteúdo no SharePoint e no OneDrive](media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Se o conteúdo for modificado ou excluído** durante o período de retenção, uma cópia do conteúdo original existente na ocasião em que a política de retenção foi atribuída será criada na Biblioteca de Retenção para Preservação. Lá, um trabalho de temporizador é executado periodicamente e identifica itens cujo período de retenção expirou, e esses itens são movidos para a lixeira de segundo estágio, onde serão excluídos permanentemente após 93 dias. A lixeira de segundo estágio não está visível para os usuários finais (somente a lixeira de primeiro estágio está), mas os administradores de conjunto de sites podem exibir e restaurar o conteúdo de lá.

    > [!NOTE]
    > Alteramos recentemente como o conteúdo é excluído da Biblioteca de Retenção para Preservação. Para ajudar a evitar a perda de dados acidental, não excluímos mais permanentemente o conteúdo da biblioteca de Retenção para Preservação. Em vez disso, excluímos permanentemente somente o conteúdo da lixeira, portanto, todo o conteúdo da Biblioteca de Retenção para Preservação agora passará pela lixeira de segundo estágio.
    
2. **Se o conteúdo não for modificado ou excluído** durante o período de retenção, ele será movido para a lixeira de primeiro estágio no final do período de retenção. Se um usuário excluir o conteúdo da lixeira ou esvaziá-la (processo também conhecido como limpeza), o documento será movido para a lixeira de segundo estágio. Um período de retenção de 93 dias abrange as lixeiras de primeiro e de segundo estágio. Após os 93 dias, o documento será excluído permanentemente de onde estiver, seja na Lixeira de primeiro ou de segundo estágio. Observe que a lixeira não é indexada e, portanto, pesquisas não localizam seu conteúdo. Isso significa que um bloqueio de Descoberta Eletrônica não pode localizar conteúdo na lixeira para retê-lo. 
    
### <a name="content-in-mailboxes-and-public-folders"></a>Conteúdo em caixas de correio e pastas públicas

Para os emails de um usuário, calendário e outros itens, uma política de retenção é aplicada no nível de uma caixa de correio. Para uma pasta pública, uma política de retenção é aplicada ao nível da pasta, não ao nível da caixa de correio. Tanto uma caixa de correio quanto uma pasta pública usam a pasta Itens Recuperáveis para reter itens. Somente as pessoas às quais foram atribuídas permissões de Descoberta Eletrônica podem exibir itens na pasta de itens recuperáveis de outro usuário. 
  
Por padrão, quando alguém exclui uma mensagem de uma pasta diferente da pasta Itens Excluídos, a mensagem é movida para a pasta Itens Excluídos. Quando alguém exclui um item da pasta Itens Excluídos, a mensagem é movida para a pasta Itens Recuperáveis. Além disso, uma pessoa pode excluir um item de forma reversível (SHIFT+DELETE) em qualquer pasta, o que ignora a pasta Itens Excluídos e move o item diretamente para a pasta Itens Recuperáveis.
  
Um processo avalia itens periodicamente na pasta Itens Recuperáveis. Se um item não corresponder às regras de pelo menos uma política de retenção, o item será excluído permanentemente (também chamado exclusão forçada) da pasta Itens Recuperáveis.
  
Quando uma pessoa tenta alterar determinadas propriedades de um item de caixa de correio, como assunto, corpo, anexos, remetentes e destinatários, ou a data de envio ou de recebimento de uma mensagem, uma cópia do item original é salva na pasta Itens Recuperáveis antes da confirmação da alteração. Isso acontecerá para todas as alterações subsequentes. Após o período de retenção, as cópias na pasta Itens Recuperáveis serão removidas permanentemente.
  
Se um usuário deixar a sua organização e a sua caixa de correio for incluída em uma política de retenção, a caixa de correio se tornará inativa quando a conta do Office 365 do usuário for excluída. O conteúdo de uma caixa de correio inativa ainda está sujeito a qualquer política de retenção que tiver sido aplicada a essa caixa antes de ela se tornar inativa e fica disponível para uma pesquisa de Descoberta Eletrônica. Para saber mais, confira [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md).
  
Depois que uma política de retenção é atribuída a uma caixa de correio ou pasta pública, o conteúdo pode seguir um destes dois caminhos:

![Diagrama de fluxo de retenção em emails e pastas públicas](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Se o item for modificado ou excluído permanentemente** pelo usuário (usando SHIFT + DELETE ou excluído de Itens Excluídos) durante o período de retenção, o item será movido (ou copiado, no caso de edição) para a pasta Itens Recuperáveis. Lá, um processo é executado periodicamente e identifica itens cujo período de retenção tenha expirado, e esses itens são permanentemente excluídos em até 14 dias após o fim do período de retenção. Observe que 14 dias é a configuração padrão, que pode ser estendida para até 30 dias.
    
2. **Se o item não for modificado ou excluído** durante o período de retenção, o mesmo processo será executado periodicamente em todas as pastas na caixa de correio, identificando itens cujo período de retenção expirou. Esses itens são então permanentemente excluídos em até 14 dias após o fim do período de retenção. Observe que 14 dias é a configuração padrão, podendo ser estendida para até 30 dias. 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Como funciona uma política de retenção com versões de documento em um conjunto de sites

O controle de versão é um recurso de todas as bibliotecas de documentos no SharePoint Online e no OneDrive for Business. Por padrão, o controle de versão retém no mínimo 500 versões principais, embora você possa aumentar esse limite. Confira mais informações em [Habilitar e configurar o controle de versão para uma lista ou biblioteca](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Uma política de retenção (política de retenção que mantém o conteúdo, em vez de somente exclusão) mantém todas as versões de um documento em um conjunto de sites do SharePoint ou em uma conta do OneDrive. Sempre que um documento sujeito a uma política de retenção ou de bloqueio for editado, uma versão será copiada para a Biblioteca de Retenção para Preservação. Sempre que um documento sujeito a uma política de retenção ou de bloqueio for excluído, todas as versões serão copiadas para a Biblioteca de Retenção para Preservação se o controle de versão estiver habilitado. Cada versão de um documento na Biblioteca de Retenção para Preservação existe como um item separado com seu próprio período de retenção:
  
- Se a política de retenção se basear em quando o conteúdo foi criado, cada versão terá a mesma data de expiração do documento original. O documento original e suas versões expirarão ao mesmo tempo.
    
- Se a política de retenção estiver baseada na data da última modificação do conteúdo, cada versão terá sua própria data de expiração com base em quando o documento original foi modificado para criar essa versão. Os documentos originais e suas versões expirarão de maneira independente entre si.

> [!NOTE]
> As versões preservadas dos documentos do SharePoint e do OneDrive não são pesquisáveis por ferramentas de Descoberta Eletrônica.

## <a name="retaining-content-for-a-specific-period-of-time"></a>Reter o conteúdo por um período específico

Com uma política de retenção, é possível manter o conteúdo indefinidamente ou por um número específico de dias, meses ou anos. A duração para retenção do conteúdo é calculada com base na idade desse conteúdo, e não do momento em que a política de retenção foi aplicada. Você pode escolher se a idade se baseia em quando o conteúdo foi criado ou (para o OneDrive e o SharePoint) em quando ele foi modificado pela última vez.
  
Por exemplo, se você quiser reter o conteúdo em um conjunto de sites por sete anos desde que foi modificado pela última vez, e se um documento nesse conjunto de sites não tiver sido modificado em seis anos, o documento será retido somente por mais um ano, caso não seja modificado. Se o documento for editado novamente, a idade do documento será calculada a partir da data da última modificação, e ele será retido por mais sete anos.
  
Da mesma forma, se você desejar reter o conteúdo em uma caixa de correio por sete anos, e uma mensagem tiver sido enviada há seis anos, a mensagem será retida por apenas um ano. Para conteúdo do Exchange, a idade sempre se baseará na data de recebimento ou de envio (elas são iguais). A retenção do conteúdo com base em quando ele foi modificado pela última vez aplica-se apenas ao conteúdo de site do OneDrive e do SharePoint.
  
Você pode escolher se deseja que o conteúdo seja excluído permanentemente no final do período de retenção. Uma política de retenção também pode excluir o conteúdo antigo sem retê-lo. Confira a próxima seção.
  
![Página de configurações de Retenção](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a>Como excluir conteúdo mais antigo que uma idade específica

Uma política de retenção pode reter e excluir o conteúdo ou excluir o conteúdo antigo sem retê-lo.
  
Se sua política de retenção excluir conteúdo, será importante entender que o período de tempo especificado para uma política de retenção é calculado pelo tempo em que o documento foi criado ou modificado, e não a partir do momento em que a política foi atribuída.
  
![Configurações de exclusão](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
Por exemplo, suponha que você crie uma política de retenção que exclui conteúdo após três anos e, em seguida, atribui essa política a todas as contas do OneDrive, que incluem uma grande quantidade de conteúdo criado há quatro ou cinco anos. Nesse caso, muito conteúdo será excluído logo após atribuir a política de retenção pela primeira vez. Por esse motivo **uma política de retenção que exclui conteúdo pode ter um impacto considerável sobre o conteúdo**. 
  
Portanto, quando atribuir uma política de retenção a um conjunto de sites pela primeira vez, primeiro considere a idade do conteúdo e de que modo a política poderá afetá-los. Você também poderá informar os usuários sobre a nova política antes de atribuí-la, para que eles tenham tempo de avaliar o possível impacto. Observe esse aviso que é exibido quando você revisa as configurações da política de retenção antes de criá-la.
  
![Aviso sobre exclusão de conteúdo](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a>Configurações avançadas que aplicam uma política apenas ao conteúdo que atenda a determinadas condições

Uma política de retenção pode ser aplicada a todo o conteúdo nos locais em que inclui ou você pode aplicar uma política de retenção apenas ao conteúdo que inclui palavras-chave específicas ou [tipos específicos de informações confidenciais](what-the-sensitive-information-types-look-for.md).
  
![Opções avançadas de retenção](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a>Reter conteúdo que inclui palavras-chave específicas

Você pode aplicar uma política de retenção apenas ao conteúdo que atenda a certas condições e realizar ações de retenção apenas nesse conteúdo. As condições disponíveis agora dão suporte à aplicação de uma política de retenção ao conteúdo que inclui palavras ou frases específicas. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT. Para saber mais sobre esses operadores, confira [Consultas de palavra-chave e critérios de pesquisa para pesquisa de conteúdo](keyword-queries-and-search-conditions.md).
  
O suporte à adição de propriedades pesquisáveis (por exemplo, **assunto:**) estará disponível em breve.
  
A retenção com base em consulta usa o índice de pesquisa para identificar conteúdo.
  
![Editor de consultas](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a>Reter conteúdo com informações confidenciais

Você também pode aplicar uma política de retenção apenas ao conteúdo que inclui [tipos específicos de informações confidenciais](what-the-sensitive-information-types-look-for.md). Por exemplo, você pode optar por aplicar exigências de retenção exclusivas somente ao conteúdo com informações de identificação pessoal (PII) como números de identificação de contribuinte, números de CPF ou números de passaporte.
  
![Página Tipos de informações confidenciais](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
Observações:
  
- A retenção avançada para informações confidenciais não se aplica a pastas públicas do Exchange ou Skype for Business, pois esses locais não dão suporte a tipos de informações confidenciais.
    
- Você deve compreender que o Exchange Online usa regras de fluxo de emails (também conhecidas como regras de transporte) para identificar informações confidenciais; portanto, isso funciona apenas em mensagens em trânsito, não em todos os itens já armazenados em uma caixa de correio. Para o Exchange Online, isso significa que uma política de retenção pode identificar informações confidenciais e realizar ações de retenção apenas em mensagens recebidas **após** a política ser aplicada à caixa de correio. (Observe que a retenção com base em consulta descrita na seção anterior não apresenta essa limitação porque ela usa o índice de pesquisa para identificar conteúdo). 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>Aplicar uma política de retenção a uma organização inteira ou locais específicos

Você pode facilmente aplicar uma política de retenção a uma organização inteira, locais inteiros ou apenas a locais ou usuários específicos.
  
### <a name="org-wide-policy"></a>Política no âmbito da organização

Um dos recursos mais avançados de política de retenção é que, por padrão, aplica-se aos locais no Office 365, incluindo:
  
- Email do Exchange
    
- Conjuntos de sites do SharePoint
    
- Contas do OneDrive
    
- Grupos do Office 365 (aplicável ao conteúdo da caixa de correio, site e documentos do grupo. Em breve, haverá suporte para conteúdo no Planner, Yammer, CRM Microsoft Teams, PowerBI, Stream, Exchange e sites de equipe do SharePoint
    
- Pastas públicas do Exchange
    
![Opção Todos os locais](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
Outros recursos importantes de uma política de retenção no âmbito da organização incluem:
  
- Não há um limite para o número de caixas de correio ou sites que essa política pode incluir.
    
- Para o Exchange, as caixas de correio criadas após a aplicação da política herdam a política automaticamente.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>Uma política aplicável a locais inteiros

Ao escolher locais, você pode facilmente incluir ou excluir um local inteiro, como emails do Exchange ou contas do OneDrive. Para fazer isso, ative ou desative o **Status** desse local. 
  
Como uma política no âmbito da organização, se uma política for aplicada a qualquer combinação de locais inteiros, não haverá um limite para o número de caixas de correio ou sites que essa política poderá incluir. Por exemplo, se uma política incluir todos os emails do Exchange e sites do SharePoint, todos os sites e caixas de correio serão incluídas, independentemente da quantidade. E para o Exchange, as caixas de correio criadas após a aplicação da política herdarão a política automaticamente.
 
![Página Escolher locais](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Uma política com inclusões ou exclusões específicas

Você também pode aplicar uma política de retenção a usuários específicos, grupos do Office 365 ou sites. Para fazer isso, ative o **Status** desse local e, em seguida, use os links para incluir ou excluir usuários, grupos do Office 365 ou locais específicos. 
  
No entanto, observe que os seguintes limites existem para uma política de retenção que inclui ou exclui mais de 1.000 locais específicos:
  
- Essa política de retenção pode conter, no máximo, 1.000 caixas de correio e 100 conjuntos de sites.
    
- Um locatário pode conter no máximo 10.000 políticas de retenção.
    
Embora esses limites existam, entenda que você pode acessar ignorá-los aplicando uma política no âmbito da organização ou uma política a locais inteiros.
  
### <a name="skype-locations"></a>Locais do Skype

Ao contrário de email do Exchange, você não pode ativar ou desativar o status de local do Skype para incluir todos os usuários, mas pode ativar esse local e depois selecionar manualmente os usuários cujas conversas deseja manter.
  
Ao escolher usuários do Skype for Business, você pode incluir rapidamente todos os usuários, selecionando a caixa de **Nome** no cabeçalho da coluna. No entanto, é importante compreender que cada usuário é como uma inclusão específica na política. Portanto, se mais de 1.000 usuários forem incluídos, os limites indicados na seção anterior serão aplicáveis. Aqui, selecionar todos os usuários do Skype não é o mesmo como se uma política no âmbito da organização fosse capaz de incluir todos os usuários do Skype por padrão. 
  
![Página Escolher usuários do Skype](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Observe que o **Histórico da Conversa**, uma pasta no Outlook, é um recurso que não tem nada a ver com o arquivamento do Skype. **Histórico da Conversa** pode ser desativado pelo usuário final, mas o arquivamento para o Skype é feito armazenando-se uma cópia das conversas do Skype em uma pasta oculta que é inacessível ao usuário, mas disponível para Descoberta Eletrônica.

### <a name="teams-locations"></a>Locais do Teams

Você pode usar uma política de retenção para manter as conversas e as mensagens de canal em Teams. As conversas do Teams são armazenadas em uma pasta oculta na caixa de correio de cada usuário incluído na conversa e as mensagens de canal do Teams são armazenadas em uma pasta oculta semelhante na caixa de correio de grupo para a equipe. No entanto, é importante compreender que o Teams usa um serviço de chat fornecido pelo Azure que também armazena esses dados e, por padrão, esse serviço armazena os dados para sempre. Por esse motivo, é altamente recomendável usar a localização para reter e excluir dados do Teams. Usar o local do Teams excluirá permanentemente os dados de caixa de correio do Exchange e o serviço de chat subjacente fornecido pelo Azure. Para saber mais, confira [Visão geral de segurança e conformidade no Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258).
  
As mensagens do canal e do chat do Teams não são afetadas pelas políticas de retenção aplicadas às caixas de correio de usuário ou do grupo nos locais de grupos do Exchange ou do Office 365. Mesmo que as mensagens do canal e do chat do Teams estejam armazenadas no Exchange, elas são afetadas apenas por uma política de retenção aplicada ao local do Teams.
  
Depois que uma política de retenção é atribuída a uma equipe, chat e canal, as mensagens podem seguir um destes dois caminhos:

![Diagrama do fluxo de retenção para mensagens do chat e do canal do Teams](media/TeamsRetentionLifecycle.png)

1. **Se uma mensagem do chat ou do canal for modificada ou excluída** pelo usuário durante o período de retenção, a mensagem será movida (ou copiada, no caso de edição) para a pasta SubstrateHolds (que é uma pasta oculta em todas as caixas de correio de usuários ou grupos) e será armazenada nessa pasta até que o período de retenção expire. As mensagens são excluídas permanentemente no dia do término do período de retenção.

2. **Se uma mensagem do chat ou do canal não for excluída** durante o período de retenção, a mensagem será movida para a pasta SubstrateHolds dentro de um dia após o término do período de retenção (de 0 a 24 horas). A mensagem é permanentemente excluída um dia após ser movida para a pasta SubstrateHolds. 

> [!NOTE]
> As mensagens na pasta SubstrateHolds são pesquisáveis por ferramentas de descoberta eletrônica. Após a exclusão permanente de uma mensagem, ela não será exibida em uma pesquisa de descoberta eletrônica.

Estamos trabalhando continuamente na otimização da funcionalidade de retenção no Teams, e planejamos lançar novos recursos nos próximos meses. Enquanto isso, estas são algumas limitações a considerar:
  
- **O Teams exige uma política de retenção independente**. Ao criar uma política de retenção e ativar o local do Teams, todos os demais locais são desativados. Uma política de retenção que inclui o Teams só pode incluí-lo e nenhum outro local. 
    
- **O Teams não está incluído em uma política no âmbito da organização**. Se criar uma política no âmbito da organização, o Teams não estará incluído, porque ele exige uma política de retenção independente. 
    
- **O Teams não é compatível com retenção avançada.** Ao criar uma política de retenção, se você escolher o [Configurações avançadas que aplicam uma política apenas ao conteúdo que atende a determinadas condições](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions), o local do Teams não estará disponível. No momento, a retenção no Teams se aplica a todo o conteúdo de mensagem do chat e do canal. 

- **Não há suporte para o conteúdo do Teams em canais privados**. Neste momento, políticas de retenção criadas para o Teams não se aplicam a mensagens de canal privado. Somente as mensagens em canais padrão estão sujeitas a uma política de retenção criada para o Teams. O suporte para políticas de retenção para canais privados será lançado em breve. 
    
- **O Teams pode levar até três dias para limpar as mensagens expiradas**. Uma política de retenção aplicada ao Teams excluirá mensagens de chat e de canal ao fim do período de retenção. No entanto, pode levar até três dias para limpar essas mensagens e excluí-las permanentemente. Além disso, as mensagens de chat e de canal serão pesquisáveis com as ferramentas de descoberta eletrônica durante o período de retenção e quando as mensagens forem excluídas permanentemente.

   > [!NOTE]
   > Antes, uma política de retenção não podia excluir o conteúdo do Teams em menos de 30 dias, mas removemos essa limitação. Agora, o período de retenção do conteúdo do Teams pode ser personalizado, sendo no mínimo de um dia. Se o período de retenção for de um dia, as mensagens serão excluídas permanentemente três dias após o término do período de retenção.
    
Em uma equipe do Teams, arquivos compartilhados em chat são armazenados na conta do OneDrive do usuário que compartilhou o arquivo. Arquivos carregados em canais são armazenados no site do SharePoint da equipe do Teams. Portanto, para manter ou excluir arquivos em uma equipe do Teams, você precisa criar uma política de retenção que se aplique especificamente aos locais do SharePoint e do OneDrive. Para aplicar uma política aos arquivos apenas para uma equipe específica, escolha o site do SharePoint da equipe do Teams e as contas do OneDrive dos usuários na equipe do Teams.
  
Uma política de retenção que se aplica ao Teams pode usar [Bloqueio de Preservação](#locking-a-retention-policy).
  
![Os locais do Teams para chat e mensagens de canal](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
> [!NOTE]
> Se você criar políticas de retenção para os locais do Skype ou Teams em sua organização, uma dessas políticas será exibida como a política de pasta padrão quando um usuário exibir as propriedades de uma pasta de caixa de correio no cliente da área de trabalho do Outlook. Esse é um problema de exibição incorreta no Outlook e [um problema conhecido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). O que deve ser exibido como a política de pasta padrão é a política de retenção da caixa de correio aplicada à pasta. A política de retenção do Skype ou Teams não é aplicada à caixa de correio do usuário.  

### <a name="office-365-groups-locations"></a>Locais de grupos do Office 365

Para manter o conteúdo de um grupo do Office 365, você precisa usar o local de grupos do Office 365. Mesmo que um grupo do Office 365 tenha uma caixa de correio do Exchange, uma política de retenção que inclua todo o local do Exchange não incluirá conteúdo nas caixas de correio de grupo do Office 365. Uma política de retenção aplicada a um grupo do Office 365 inclui a caixa de correio do grupo e um site. Uma política de retenção aplicada a um grupo do Office 365 protege os recursos criados por um grupo do Office 365, que inclui o Microsoft Teams.

Além disso, não é possível usar o local do Exchange para incluir ou excluir uma caixa de correio de grupo específica. Embora o local do Exchange permita inicialmente que uma caixa de correio de grupo seja selecionada, ao tentar salvar a política de retenção, você recebe um erro indicando que "RemoteGroupMailbox" não é uma seleção válida para o local do Exchange. 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Como excluir tipos específicos de itens do Exchange de uma política de retenção
Usando o PowerShell, você poderá excluir tipos específicos de itens do Exchange de uma política de retenção. Por exemplo, você poderá excluir mensagens de caixa postal, conversas de mensagens instantâneas e outro conteúdo do Skype for Business Online nas caixas de correio. Você também pode excluir o calendário, as anotações e os itens de tarefas. Esse recurso está disponível apenas usando o PowerShell; não está disponível na interface de usuário quando você cria uma política de retenção.
  
Para fazer isso, use o parâmetro `ExcludedItemClasses` dos cmdlets `New-RetentionComplianceRule` e `Set-RetentionComplianceRule`. Para saber mais sobre o PowerShell, confira a seção abaixo [Encontre os cmdlets do PowerShell para políticas de retenção](#find-the-powershell-cmdlets-for-retention-policies).

## <a name="locking-a-retention-policy"></a>Como bloquear uma política de retenção
Algumas organizações talvez precisem cumprir regras definidas por órgãos regulamentadores, como a Regra 17a-4 do Securities and Exchange Commission (SEC), que exige que após uma política de retenção ser ativada, ela não pode ser desativada ou se tornar menos restritiva. Com o Bloqueio de Preservação, você pode bloquear a política para que ninguém, nem o administrador, possa desativar a política ou torná-la menos restritiva.
  
Após o bloqueio de uma política, ninguém poderá desativá-la nem remover locais da política. Além disso, não é possível modificar ou excluir o conteúdo que está sujeito à política durante o período de retenção. Depois que a política for bloqueada, só se poderá modificar a política de retenção adicionando locais a ela ou ampliando sua duração. Uma política bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.
  
Portanto, antes de bloquear uma política de retenção, é **fundamental** que você entenda os requisitos de conformidade da sua organização e **não bloqueie uma política** até ter certeza de que isso é necessário.

### <a name="lock-a-retention-policy-by-using-powershell"></a>Bloquear uma política de retenção usando o PowerShell
  
Você pode bloquear uma política de retenção apenas usando o PowerShell.

Primeiro, [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://go.microsoft.com/fwlink/p/?LinkID=799771).

Em segundo lugar, para exibir uma lista de suas políticas de retenção e encontrar o nome da política que você quer bloquear, execute `Get-RetentionCompliancePolicy`.

![Lista de políticas de retenção no PowerShell](media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

Em terceiro lugar, para colocar um bloqueio de preservação na política de retenção, execute `Set-RetentionCompliancePolicy` com o parâmetro `RestrictiveRetention` definido como verdadeiro. Por exemplo:

`Set-RetentionCompliancePolicy -Identity “<Name of Policy>” – RestrictiveRetention $true`

![Parâmetro RestrictiveRetention no PowerShell](media/retention-policy-preservation-lock-restrictiveretention.PNG)

Depois de executar esse cmdlet, você pode ver um prompt de confirmação. Escolha **Sim para todos**.

![Solicitar confirmação que deseja bloquear uma política de retenção no PowerShell](media/retention-policy-preservation-lock-confirmation-prompt.PNG)

O Bloqueio de Preservação agora está localizado na política de retenção. Se executar `Get-RetentionCompliancePolicy`, o parâmetro `RestrictiveRetention` é definido como verdadeiro. Por exemplo:

`Get-RetentionCompliancePolicy -Identity “<Name of Policy>” |Fl`

![Bloquear a política com todos os parâmetros mostrados no PowerShell](media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="releasing-a-retention-policy"></a>Como liberar uma política de retenção

Você pode desativar ou excluir uma política de retenção a qualquer momento. Quando você faz isso, todo o conteúdo do SharePoint ou do OneDrive que está sendo mantido na biblioteca de retenção de preservação não é excluído imediata e permanentemente. Em vez disso, para ajudar a evitar a perda acidental de dados, há um período de cortesia de 30 dias, durante o qual a expiração de conteúdo dessa política não acontece na biblioteca de retenção para preservação para que você possa restaurar todo o conteúdo de lá, se necessário. Você também pode ativar a política de retenção novamente durante o período de cortesia e nenhum conteúdo será excluído para essa política.

O período de cortesia de 30 dias no SharePoint e no OneDrive corresponde à retenção por atraso de 30 dias no Exchange. Para saber mais, confira [Gerenciar caixas de correios em retenção por atraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Os princípios de retenção ou o que tem precedência?

É possível ou até mesmo provável que o conteúdo tenha várias políticas de retenção aplicadas a ele, cada uma com uma ação diferente (manter, excluir ou ambas) e o período de retenção. O que tem precedência? No nível mais alto, esteja certo de que o conteúdo retido por uma política não pode ser excluído permanentemente por outra política.
  
![Diagrama dos princípios de retenção](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Para entender como as diferentes políticas de retenção são aplicadas ao conteúdo, lembre-se destes princípios de retenção:
  
1. **A retenção prevalece sobre a exclusão.** Suponha que uma política de retenção diga que o email deve ser excluído do Exchange após três anos, mas que outra política de retenção diga que o email do Exchange deve ser mantido por cinco anos e depois excluído. Qualquer conteúdo com três anos será excluído e ocultado dos usuários, mas ainda será mantido na pasta Itens Recuperáveis até que o conteúdo complete cinco anos, quando será permanentemente excluído. 
    
2. **O período de retenção mais longo prevalece.** Se o conteúdo estiver sujeito a várias políticas que retêm o conteúdo, ele será mantido até o fim do período de retenção mais longo. 
    
3. **A inclusão explícita prevalece sobre a inclusão implícita.** Isso significa que: 
    
    1. Se um rótulo com configurações de retenção for atribuído manualmente por um usuário a um item, como um email do Exchange ou um documento do OneDrive, esse rótulo tem prioridade sobre uma política atribuída no nível do site ou da caixa de correio e um rótulo padrão atribuído pela biblioteca de documentos. Por exemplo, se o rótulo explícito determina a retenção por dez anos, mas a política atribuída ao site estabelecer a retenção por apenas cinco anos, o rótulo terá prioridade. Os rótulos de aplicação automática são considerados implícitos, não explícitos, pois são aplicados automaticamente pelo Office 365.
    
    2. Se uma política de retenção incluir um local específico, como a caixa de correio de um usuário específico ou conta OneDrive for Business, essa política terá precedência sobre outra política de retenção que se aplica a caixas de correio de todos os usuários ou contas do OneDrive for Business, mas não incluirá especificamente essa caixa de correio do usuário.
    
4. **O período de exclusão mais curto tem precedência.** Da mesma forma, se o conteúdo estiver sujeito a várias políticas que excluem o conteúdo (sem retenção), ele será excluído ao fim do período de retenção mais curto. 
    
Entenda que os princípios de retenção funcionam como um fluxo de desempate de cima para baixo: se as regras aplicadas por todas as políticas ou rótulos forem as mesmas em um nível, o fluxo se moverá para baixo até o próximo nível para determinar a precedência para a qual a regra será aplicada.
  
Por fim, uma política de retenção ou rótulo não pode excluir permanentemente qualquer conteúdo que esteja retido para Descoberta Eletrônica. Quando a retenção for liberada, o conteúdo estará novamente qualificado para o processo de limpeza descrito acima.
  
## <a name="use-a-retention-policy-instead-of-these-features"></a>Usar uma política de retenção em vez destes recursos

Uma única política de retenção pode ser facilmente aplicada a uma organização inteira e a locais por todo o Office 365, incluindo o Exchange Online, o SharePoint Online, o OneDrive for Business e grupos do Office 365. Se precisar manter ou excluir conteúdo em qualquer lugar no Office 365, é recomendável usar uma política de retenção. (Você também pode usar rótulos com configurações de retenção. Para obter mais informações, consulte [Visão Geral do rótulos](labels.md).)
  
Há vários outros recursos que já foram usados para reter ou excluir conteúdo no Office 365. Eles estão listados abaixo. Esses recursos continuarão a funcionar lado a lado com políticas de retenção e rótulos de retenção. Porém, futuramente, para governança de informações, recomendamos o uso de uma política de retenção ou o uso de rótulos em vez de todos esses recursos. Uma política de retenção é o único recurso que pode tanto reter quanto excluir conteúdo por todo o Office 365.
  
### <a name="exchange-online"></a>Exchange Online

- [Gerenciar ocorrências de Descoberta Eletrônica no &amp;Centro de Conformidade e Segurança ](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da)do Office 365 (Retenção de Descoberta Eletrônica) 
    
- [Bloqueio In-loco e a Retenção de Litígio](https://go.microsoft.com/fwlink/?linkid=846124) (Retenção de Descoberta Eletrônica) 

- [Como identificar o tipo de retenção de uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Marcas de retenção e políticas de retenção](https://go.microsoft.com/fwlink/?linkid=846125), também conhecidas como [gerenciamento de registros de mensagens (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (apenas exclusão) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online e OneDrive for Business

- [Gerenciar ocorrências de Descoberta Eletrônica no &amp;Centro de Conformidade e Segurança ](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da)do Office 365 (Retenção de Descoberta Eletrônica) 
    
- [Adicionar conteúdo a uma ocorrência e colocar fontes em retenção na Descoberta Eletrônica](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (Retenção de Descoberta Eletrônica) 
    
- [Visão geral das políticas de exclusão de documentos](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (apenas exclusão) 
    
- [Como configurar o gerenciamento de registros no local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retenção) 
    
- [Use políticas de fechamento de site e exclusão](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (apenas exclusão) 
    
- [Políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md) (apenas exclusão) 
    
Se tiver usado anteriormente qualquer um dos bloqueios de descoberta eletrônica para fins de governança de informações, você deve usar uma política de retenção para conformidade proativa. Você deve usar um bloqueio apenas para a descoberta eletrônica.
  
### <a name="retention-policies-override-information-management-policies"></a>As políticas de retenção substituem as políticas de gerenciamento de informações

Nos sites do SharePoint, talvez você esteja usando [políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md) para reter conteúdo. Se você aplicar uma política de retenção em um site que já usa políticas de tipo de conteúdo ou políticas de gerenciamento de informações para uma lista ou biblioteca, essas políticas serão ignoradas enquanto a política de retenção estiver em vigor. 
  
## <a name="what-happened-to-preservation-policies"></a>O que aconteceu com as políticas de preservação?

Se você estava usando uma política de preservação, essa política foi automaticamente convertida em uma política de retenção que usa apenas a ação de retenção – a política não excluirá conteúdo. A política de preservação continuará a funcionar e a preservar seu conteúdo sem exigir mudanças da sua parte. Você pode encontrar essas políticas na página **Políticas** no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/) ou na página **Retenção**, em **Governança de informações**, no [Centro de Conformidade&amp; e Segurança](https://protection.office.com/). Você pode editar uma política de preservação para alterar o período de retenção, mas você não pode fazer outras alterações, como adicionar ou remover locais. 
  
## <a name="permissions"></a>Permissões

Os membros da sua equipe de conformidade que criarão políticas de retenção precisam de permissões para o [Centro de Conformidade&amp; e Segurança](https://protection.office.com/). Por padrão, o administrador de locatário terá acesso a esse local e pode dar acesso a outras pessoas e aos responsáveis pela conformidade ao [Centro de Conformidade&amp; e Segurança](https://protection.office.com/), sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você acesse a página **Permissões** do [Centro de Conformidade&amp; e Segurança](https://protection.office.com/), edite o grupo de função **Administrador de Conformidade** e adicione membros a esse grupo de função. 
  
Para saber mais, consulte [Dar aos usuários acesso ao &amp;Centro de Conformidade](/security/office-365-security/grant-access-to-the-security-and-compliance-center.md) e Segurança do Office 365.
  
Essas permissões são necessárias somente para criar e aplicar uma política de retenção. A imposição da política não exige acesso ao conteúdo.
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>Localizar os cmdlets do PowerShell para políticas de retenção

Para usar os cmdlets de política de retenção, você precisará:
  
1. [Conectar ao &amp;Centro de Conformidade e Segurança do Office 365 usando o PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Use esses [cmdlets do &amp;Centro de Conformidade e Segurança do Office 365](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
## <a name="more-information"></a>Mais informações

- [Visão geral de rótulos](labels.md)
- [Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limites e especificações para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
    
