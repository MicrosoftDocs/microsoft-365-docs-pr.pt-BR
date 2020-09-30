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
description: Use a ferramenta Pesquisa de conteúdo no Centro de conformidade e segurança para procurar e exportar dados de bate-papo do Teams para usuários locais em uma implantação híbrida do Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bb207463c360d98623caed4024bb87deb5fdfc
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277093"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Pesquisar dados de chat do Teams para usuários locais

Se a sua organização tiver uma implantação híbrida do Exchange (ou se a sua organização sincronizar uma organização do Exchange local com o Microsoft 365) e tiver habilitado o Microsoft Teams, os usuários poderão usar o aplicativo de chat do Teams para mensagens instantâneas. Para um usuário baseado em nuvem, os dados de chat do Teams (também chamados de *chats 1x1 ou 1xN*) são salvos em suas caixas de correio principais baseadas na nuvem. Quando um usuário local usa o aplicativo de chat do Teams, as mensagens de chat não podem ser armazenadas na caixa de correio principal, que está localizada no local. Para contornar essa limitação, a Microsoft lançou um novo recurso em que uma área de armazenamento baseada em nuvem é criada, para que você use as ferramentas de descoberta eletrônica para pesquisar e exportar dados de chat do Teams para usuários locais.
  
Estes são os requisitos e limitações para a configuração de caixas de correio baseadas em nuvem para usuários locais:
  
- As contas de usuário no serviço de diretório local (por exemplo, o Active Directory) devem ser sincronizadas com o Azure Active Directory, o serviço de diretório do Microsoft 365. Isso significa que uma conta de usuário de email é criada no Microsoft 365 e está associada a um usuário cuja caixa de correio principal está localizada na organização local.

- O usuário cuja caixa de correio principal está localizada na organização local deve receber uma licença do Microsoft Teams e, no mínimo, uma licença do Exchange Online Plan 1.

- Somente dados de chat do Teams associadas a um usuário local são armazenados na área de armazenamento baseada na nuvem. Um usuário local não pode acessar essa área de armazenamento de forma alguma.

- Você deve enviar uma solicitação para o suporte da Microsoft para permitir que sua organização pesquise dados de chat do Teams nas caixas de correio baseadas em nuvem para usuários locais. Confira [Arquivando uma solicitação com o suporte da Microsoft para habilitar esse recurso](#filing-a-request-with-microsoft-support-to-enable-this-feature) neste artigo.

> [!NOTE]
> As conversas em canais do Teams sempre são armazenadas na caixa de correio baseada em nuvem associada à equipe. Isso significa que você pode usar a Pesquisa de Conteúdo para pesquisar conversas de canal sem ter que registrar uma solicitação de suporte. Para obter mais informações sobre como Pesquisar conversas de canal do Teams, confira [Pesquisar no Microsoft Teams e Grupos do Microsoft 365 ](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Como funciona

Se um usuário habilitado do Microsoft Teams tiver uma caixa de correio local e a respectiva conta de usuário/identidade tiver sido sincronizada com a nuvem, a Microsoft criará armazenamento baseado em nuvem para associar dados de chat 1xN do Teams do usuário local. Os dados de chat do Teams para usuários locais são indexados para pesquisa. Isso permite que você use a Pesquisa de Conteúdo (e as pesquisas associadas a casos Principais e de Descoberta Eletrônica) para pesquisar, visualizar e exportar dados de chat do Teams para usuários locais. Você também pode usar os cmdlets do **\*ComplianceSearch** no PowerShell do Centro de Conformidade e Segurança para procurar dados de bate-papo de equipes para usuários locais.
  
O gráfico a seguir mostra o fluxo de trabalho de como os dados de chat do Teams para usuários locais estão disponíveis para pesquisa, visualização e exportação.
  
![Armazenamento baseado em nuvem para usuários locais no Microsoft Teams](../media/EHAMShard1.png)
  
Além desse novo recurso, você ainda poderá usar a Pesquisa de Conteúdo para pesquisar, visualizar e exportar conteúdo do Teams no site do SharePoint baseado na nuvem e na caixa de correio do Exchange associada a cada dado de chat do Microsoft Teams e 1xN Teams na caixa de correio do Exchange Online para usuários baseados em nuvem.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Registrando uma solicitação com o suporte da Microsoft para habilitar esse recurso

Você deve registrar uma solicitação com o suporte da Microsoft para permitir que a sua organização use a interface gráfica do usuário no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams para usuários locais. Esse recurso está disponível no PowerShell do Centro de Conformidade e Segurança. Você não precisa enviar uma solicitação de suporte para usar o PowerShell para pesquisar os dados de chat do Teams para usuários locais.
  
Inclua as seguintes informações ao enviar a solicitação para o suporte da Microsoft:
  
- O nome de domínio padrão da sua organização.

- O nome do locatário e o ID do locatário da sua organização. Você pode encontrá-los no portal do Azure Active Directory (em **Gerenciar** \> **Propriedades**). Confira [Localizar sua ID de locatário do Microsoft 365](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).

- O seguinte título ou a descrição de finalidade da solicitação de suporte: "Habilitar a pesquisa de conteúdo do aplicativo para usuários locais". Isso ajuda a rotear a solicitação para a equipe de engenharia de Descoberta eletrônica, o qual implementará a solicitação.

Após a mudança de engenharia, o suporte da Microsoft enviará a você uma data estimada da implantação. O processo de implantação geralmente demora de duas a três semanas após o envio da solicitação de suporte.
  
### <a name="what-happens-after-this-feature-is-enabled"></a>O que acontece após esse recurso ser habilitado?

Após a implantação desse recurso na sua organização, as seguintes alterações são feitas na Pesquisa de Conteúdo e em pesquisas associadas a um caso de Descoberta eletrônica no Centro de Conformidade e Segurança:
  
- A caixa de seleção**Adicionar o conteúdo do aplicativo do Office para usuários no local** é adicionada em **Locais** na Pesquisa de Conteúdo.

    ![A caixa de seleção "Adicionar conteúdo do aplicativo do Office para usuários locais" é adicionada à IU de Pesquisa de Conteúdo](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Os usuários locais são exibidos no seletor de locais de conteúdo que você usa para selecionar as caixas de correio dos usuários.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Pesquisando conteúdo de chat do Teams para usuários locais

Após habilitar o recurso, você poderá usar a pesquisa de conteúdo no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams para usuários locais.
  
1. No Centro de Conformidade e Segurança, acesse **Pesquisar** \> **Pesquisa de Conteúdo**

2. Na página **Pesquisar**, clique em ![Adicionar ícone](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nova pesquisa**.

    Como explicado anteriormente, a caixa de seleção **Adicionar o conteúdo do aplicativo do Office para usuários locais** é exibida em **Locais**. Ela é selecionada por padrão.

3. Crie uma consulta de palavra-chave e adicione condições à consulta de pesquisa, se necessário. Para pesquisar apenas dados de chat da equipe, você pode adicionar a seguinte consulta na caixa **Palavras-chave**:

    ```text
    kind:im
    ```

4. Neste ponto, você pode escolher uma das seguintes opções em **Locais**:

    - **Todos os locais:** Selecione essa opção para pesquisar nas caixas de correio de todos os usuários em sua organização. Quando a caixa de seleção estiver marcada, todos os dados de chat do Teams para usuários locais também serão pesquisados.

    - **Locais específicos:** Selecione essa opção e clique em **Modificar** \> Escolha usuário, grupos ou equipes para pesquisar caixas de correio específicas. Como explicado anteriormente, o seletor de local permite pesquisar dados de chats do Teams para usuários locais.

5. Salve e execute a pesquisa. Os resultados da pesquisa para usuários locais podem ser visualizados como qualquer outro resultado da pesquisa. Você também pode exportar os resultados da pesquisa (inclusive dados de chat do Teams) para um arquivo PST. Para saber mais, confira:

    - [Criar uma pesquisa](content-search.md#create-a-search)

    - [Visualização de resultados de pesquisa](content-search.md#preview-search-results)

    - [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Usando o PowerShell para pesquisar dados de chat do Teams para usuários locais

Você pode usar os cmdlets **New-ComplianceSearch** e **Set-ComplianceSearch** no PowerShell do Centro de Conformidade e Segurança para pesquisar dados de chat do Teams para usuários locais. Como foi explicado anteriormente, você não precisa enviar uma solicitação de suporte para usar o PowerShell para pesquisar os dados de chat do Teams para usuários locais.
  
1. [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Execute o seguinte comando do PowerShell para criar uma pesquisa de conteúdo que pesquise os dados de chat do Teams para usuários locais.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    O parâmetro *IncludeUserAppContent* é usado para especificar o armazenamento baseado em nuvem para o usuário ou usuários especificados pelo parâmetro *ExchangeLocation*. O*AllowNotFoundExchangeLocationsEnabled* permite que você pesquise o armazenamento baseado em nuvem para usuários locais. Quando você usa o valor `$true` para esse parâmetro, a pesquisa não tenta validar a existência da caixa de correio antes de ser executada. Isso é necessário para pesquisar o armazenamento baseado em nuvem para usuários locais porque esse armazenamento baseado em nuvem não é resolvido como uma caixa de correio comum baseada em nuvem.

    O exemplo a seguir procura por diversos chats do Teams (que são mensagens instantâneas) que contenham a palavra-chave "redstone" no armazenamento baseado em nuvem da Sara Davis, que é uma usuária local na organização da Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Depois de criar uma pesquisa, certifique-se de usar o cmdlet **Start-ComplianceSearch** para executar a pesquisa. 
  
Para mais informações sobre esses cmdlets, confira:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemas conhecidos

- Atualmente, você pode pesquisar, visualizar e exportar dados de chat do Teams para usuários locais. Também é possível colocar dados de chat do Teams para um usuário local em um bloqueio associado com o caso Principal ou de Descoberta eletrônica e aplicar uma política de retenção para chats do Teams ou mensagens de canal para usuários locais. No entanto, no momento, você não pode aplicar uma política de retenção para outros locais de conteúdo (como as caixas de correio do Exchange e sites do SharePoint) para usuários locais.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

 **Onde está localizado o armazenamento baseado em nuvem para usuários locais?**
  
O armazenamento baseado em nuvem é provisionado no mesmo Centro de Dados da sua organização.
  
 **Há outros requisitos além de enviar uma solicitação de suporte?**
  
 Como explicado anteriormente, as identidades dos usuários com caixas de correio locais devem ser sincronizadas com a sua organização baseada em nuvem para que uma conta de usuário de e-mail correspondente seja criada para cada conta de usuário local no Office 365. Sua organização também deve ter uma assinatura do Office 365 Enterprise, assim como uma assinatura do Office 365 Enterprise E1, E3 ou e5.
  
 **Há o risco de perder os dados de chat do Teams se a caixa de correio local do usuário for migrada para a nuvem?**
  
Não. Quando você migrar a caixa de correio principal de um usuário local para a nuvem, os dados de chat do Teams serão migrados para a sua nova caixa de correio primária baseada na nuvem.
  
 **Posso aplicar um bloqueio de Descoberta eletrônica ou políticas de retenção para usuários locais?**
  
Sim. Você pode aplicar bloqueios de Descoberta eletrônica ou políticas de retenção para chats do Teams e mensagens de canal para usuários locais.
  
 **A Pesquisa de Conteúdo pode encontrar dados de chat do Teams mais antigos para usuários locais antes do momento em que a minha organização enviou a solicitação para habilitar esse recurso?**
  
A Microsoft começou a armazenar os dados de chat do Teams para usuários locais em 31 de janeiro de 2018. Portanto, se a identidade de um usuário local do Teams tiver sido sincronizada entre o Active Directory e o Azure Active Directory depois dessa data, os dados de chat do Teams estarão armazenados na nuvem e podem ser pesquisados usando a Pesquisa de Conteúdo. A Microsoft também está trabalhando no armazenamento de dados de chat do Teams de antes de 31 de janeiro de 2018 no armazenamento baseado em nuvem para usuários locais. Mais informações sobre isso estarão disponíveis em breve.

 **Os usuários locais precisam de uma licença para armazenar os dados de chat do Teams na nuvem?**
  
Sim. Para armazenar dados de chat do Teams de um usuário local em um armazenamento baseado em nuvem, o usuário deve receber uma licença do Microsoft Teams e uma licença do Exchange Online Plan no Office 365 (ou Microsoft 365).
