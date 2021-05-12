---
title: Pesquisar dados de chat do Teams para usuários locais
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Use as ferramentas de Descoberta Eletrônica no Microsoft 365 para pesquisar e exportar dados de bate-papo do Teams para usuários locais em uma implantação híbrida do Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311791"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Pesquisar dados de chat do Teams para usuários locais

Se a sua organização tiver uma implantação híbrida do Exchange (ou se a sua organização sincronizar uma organização do Exchange local com o Microsoft 365) e tiver habilitado o Microsoft Teams, os usuários poderão usar o aplicativo de chat do Teams para mensagens instantâneas. Para um usuário baseado em nuvem, os dados de chat do Teams (também chamados de *chats 1x1 ou 1xN*) são salvos em suas caixas de correio principais baseadas na nuvem. Quando um usuário local usa o aplicativo de chat do Teams, as mensagens de chat não podem ser armazenadas na caixa de correio principal, que está localizada no local. Para contornar essa limitação, a Microsoft lançou um novo recurso em que uma área de armazenamento baseada em nuvem é criada, para que você use as ferramentas de descoberta eletrônica para pesquisar e exportar dados de chat do Teams para usuários locais.
  
Estes são os requisitos e limitações para a configuração de caixas de correio baseadas em nuvem para usuários locais:
  
- As contas de usuário no serviço de diretório local (por exemplo, o Active Directory) devem ser sincronizadas com o Azure Active Directory, o serviço de diretório do Microsoft 365. Isso significa que uma conta de usuário de email é criada no Microsoft 365 e está associada a um usuário cuja caixa de correio principal está localizada na organização local.

- O usuário cuja caixa de correio principal está localizada na organização local deve receber uma licença do Microsoft Teams e, no mínimo, uma licença do Exchange Online Plan 1.

- Se sua organização não tiver uma implantação híbrida do Exchange, você deve sincronizar seu esquema do Exchange local com o Azure Active Directory. Se você não fizer isso, pode correr o risco de criar caixas de correio duplicadas baseadas em nuvem no Exchange Online para os usuários que têm uma caixa de correio em sua organização do Exchange local.

- Somente os dados de bate-papo do Teams associados a um usuário local são armazenados na área de armazenamento baseada em nuvem. Um usuário local não pode acessar essa área de armazenamento de forma alguma.

> [!NOTE]
> As conversas de canal do Teams sempre são armazenadas na caixa de correio baseada em nuvem associada à Equipe, o que significa que você pode pesquisar por conversas de canal. Para obter mais informações sobre como Pesquisar conversas de canal do Teams, confira [Pesquisar no Microsoft Teams e Grupos do Microsoft 365 ](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Como funciona

Se um usuário habilitado do Microsoft Teams tiver uma caixa de correio local e a respectiva conta de usuário/identidade tiver sido sincronizada com a nuvem, a Microsoft criará armazenamento baseado em nuvem para associar dados de chat 1xN do Teams do usuário local. Os dados de chat do Teams para usuários locais são indexados para pesquisa. Isto permite que você Use a Pesquisa de Conteúdo (e as pesquisas associadas aos casos de Descoberta Eletrônica Principal e Descoberta Eletrônica Avançada) para pesquisar, visualizar e exportar dados de bate-papo das equipes para usuários locais. Você também pode usar os cmdlets do **\*ComplianceSearch** no PowerShell do Centro de Conformidade e Segurança para procurar dados de bate-papo de equipes para usuários locais.
  
O gráfico a seguir mostra o fluxo de trabalho de como os dados de chat do Teams para usuários locais estão disponíveis para pesquisa, visualização e exportação.
  
![Armazenamento baseado em nuvem para usuários locais no Microsoft Teams](../media/EHAMShard1.png)
  
Além deste recurso, você também pode usar as ferramentas de Descoberta Eletrônica para pesquisar, visualizar e exportar o conteúdo do Teams no site do SharePoint baseado na nuvem e na caixa de correio Exchange associada a cada Equipe da Microsoft e os dados de bate-papo 1xN do Teams na caixa de correio do Exchange Online para usuários baseados na nuvem.

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>Como este recurso é suportado nas ferramentas de Pesquisa de Conteúdo e nas ferramentas de pesquisa de Descoberta Eletrônica Principal

Os seguintes elementos de IU na Pesquisa de Conteúdo e na ferramenta de pesquisa associada com os casos de Descoberta Eletrônica Principal no Centro de conformidade do Microsoft 365:
  
- A caixa de seleção **Adicionar conteúdo do aplicativo para usuários locais** é exibida na página do assistente **Locais** na ferramenta Pesquisa de conteúdo e está selecionada por padrão. Selecione esta caixa de seleção para incluir o armazenamento baseado em nuvem para usuários locais em uma pesquisa de conteúdo.

    ![A caixa de seleção "Adicionar conteúdo do Aplicativo do Office para usuários locais" é adicionada à IU de Pesquisa de Conteúdo](../media/EHAMShardCheckBox.png)
  
- Você pode procurar usuários locais quando escolher usuários específicos para procurar.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Pesquisando conteúdo de chat do Teams para usuários locais

Veja como usar a Pesquisa de Conteúdo no Centro de conformidade do Microsoft 365 para pesquisar os dados de bate-papo do Teams para usuários locais.
  
1. No Centro de conformidade do Microsoft 365, vá para **Pesquisa de Conteúdo**.

2. Na guia **Pesquisas**, clique em **Nova pesquisa** e nomeie a nova pesquisa.

3. Na página **Locais**, configure a alternância como **Ativada** para caixas de correio do Exchange. Observe que a caixa de seleção **Adicionar conteúdo do aplicativo para usuários locais** é exibida e selecionada por padrão.

4. Para procurar conteúdo do Teams para usuários específicos, selecione **Escolher usuário, grupos ou equipes** e escolha usuários específicos para incluir na pesquisa. Caso contrário, clique em **Próximo** para pesquisar conteúdo do Teams para todos os usuários, incluindo usuários locais

5. Na página **Definir as condições da pesquisa**, digite uma consulta de palavra-chave e adicione condições à consulta de pesquisa, se necessário. Para pesquisar apenas dados de chats do Teams, você pode adicionar a seguinte consulta na caixa **Palavras-chave**:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Salve e execute a pesquisa. Os resultados da pesquisa para usuários locais podem ser visualizados como qualquer outro resultado da pesquisa. Você também pode exportar os resultados da pesquisa (inclusive dados de chat do Teams) para um arquivo PST. Para saber mais, confira:

    - [Criar uma pesquisa](content-search.md)

    - [Visualização de resultados de pesquisa](preview-ediscovery-search-results.md)

    - [Exportar resultados de pesquisa](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Usando o PowerShell para pesquisar dados de chat do Teams para usuários locais

Você pode usar os cmdlets **New-ComplianceSearch** e **Set-ComplianceSearch** no PowerShell do Centro de Conformidade e Segurança para pesquisar dados de chat do Teams para usuários locais. Como foi explicado anteriormente, você não precisa enviar uma solicitação de suporte para usar o PowerShell para pesquisar os dados de chat do Teams para usuários locais.
  
1. [Conectar ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Execute o seguinte comando do PowerShell para criar uma pesquisa de conteúdo que pesquise os dados de chat do Teams para usuários locais.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    O parâmetro *IncludeUserAppContent* é usado para especificar o armazenamento baseado em nuvem para o usuário ou usuários especificados pelo parâmetro *ExchangeLocation*. O *AllowNotFoundExchangeLocationsEnabled* permite que você pesquise o armazenamento baseado em nuvem para usuários locais. Quando você usa o valor `$true` para esse parâmetro, a pesquisa não tenta validar a existência da caixa de correio antes de ser executada. Isso é necessário para pesquisar o armazenamento baseado em nuvem para usuários locais porque esse armazenamento baseado em nuvem não é resolvido como uma caixa de correio comum baseada em nuvem.

    O exemplo a seguir procura por diversos chats do Teams que contenham a palavra-chave "redstone" no armazenamento baseado em nuvem da Sara Davis, que é uma usuária local na organização da Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Depois de criar uma pesquisa, certifique-se de usar o cmdlet **Start-ComplianceSearch** para executar a pesquisa.
  
Para mais informações sobre esses cmdlets, confira:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemas conhecidos

- Atualmente, você pode pesquisar, visualizar e exportar dados de chat do Teams para usuários locais. Também é possível colocar dados de chat do Teams para um usuário local em um bloqueio associado com o caso Principal ou de Descoberta eletrônica e aplicar uma política de retenção para chats do Teams ou mensagens de canal para usuários locais. No entanto, no momento, você não pode aplicar uma política de retenção para outros locais de conteúdo (como as caixas de correio do Exchange e sites do SharePoint) para usuários locais.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Preciso enviar solicitação uma de suporte para procurar por mensagens de bate-papo para usuários locais?**

Não. Este recurso está habilitado por padrão para todas as organizações. Em certo momento, você teve que entrar em contato com o Suporte da Microsoft, mas esse não é mais o caso.
  
 **As ferramentas de Descoberta Eletrônica podme encontrar dados de bate-papo do Teams mais antigos para usuários locais antes do momento em que este recurso foi habilitado por padrão para todas as organizações?**
  
A Microsoft começou a armazenar dados de chat do Teams para usuários locais em 31 de janeiro de 2018. Portanto, se a identidade de um usuário local do Teams foi sincronizada entre vocês no Active Directory local e no Azure Active Directory no Microsoft 365 desde esta data, então os dados de bate-papo do Teams estão armazenados na nuvem e poderão ser pesquisados usando as ferramentas de Descoberta eletrônica.

 **Os usuários locais precisam de uma licença para armazenar os dados de chat do Teams na nuvem?**
  
Para armazenar dados de chat do Teams de um usuário local em um armazenamento baseado em nuvem, o usuário deve receber uma licença do Microsoft Teams e uma licença do Exchange Online Plan no Office 365 (ou Microsoft 365).

**Onde está localizado o armazenamento baseado em nuvem para usuários locais?**
  
Os dados do bate-papo das equipes são armazenados no local de dados preferencial (PDL) para um usuário local. O PDL é homenageado em ambientes Single Geo e Multi Geo. Para mais informações, consulte [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

**Há o risco de perder os dados de chat do Teams se a caixa de correio local do usuário for migrada para a nuvem?**
  
Quando você migrar a caixa de correio principal de um usuário local para a nuvem, os dados de chat do Teams serão migrados para a sua nova caixa de correio principal baseada na nuvem.
  
 **Posso aplicar um bloqueio de Descoberta eletrônica ou políticas de retenção para usuários locais?**
  
Sim. Você pode aplicar bloqueios de Descoberta eletrônica ou políticas de retenção para chats do Teams e mensagens de canal para usuários locais. Entretanto, para preservar ou reter o conteúdo do Teams para usuários locais, um usuário local deve receber uma licença do Exchange Online (Plano 2).
