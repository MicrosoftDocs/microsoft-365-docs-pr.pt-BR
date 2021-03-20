---
title: Criar e configurar políticas de retenção para reter ou excluir o conteúdo automaticamente
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
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
description: Use uma política de retenção para manter o controle eficiente do conteúdo que os usuários geram com email, documentos e conversas. Mantenha o que você deseja e descarte o que não.
ms.openlocfilehash: 63670b157a66bad963f02355cbed2bdd95690081
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908285"
---
# <a name="create-and-configure-retention-policies"></a>Criar e configurar políticas de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use uma política de retenção para gerenciar os dados de sua organização, decidindo de forma proativa se retém, exclui ou retém e exclui o conteúdo.

Uma política de retenção permite que você faça isso de forma muito eficiente, atribuindo as mesmas configurações de retenção no nível do contêiner para serem herdadas automaticamente pelo conteúdo desse contêiner. Por exemplo, todos os itens em sites do Windows SharePoint, todas as mensagens de email nas caixas de correio do Exchange dos usuários, todas as mensagens do canal para equipes usadas com o Microsoft Teams. Se você não tiver certeza se deve usar uma política de retenção no nível do contêiner ou um rótulo de retenção no nível do item, consulte [Políticas de retenção e rótulos de retenção](retention.md#retention-policies-and-retention-labels).

Para mais informações sobre políticas de retenção e como funciona a retenção no Microsoft 365, consulte [Saiba mais sobre políticas de retenção e rótulos de retenção](retention.md).

> [!NOTE]
> As informações nesta página são para administradores de conformidade. Se você não é um administrador e deseja entender como as políticas de retenção foram configuradas para os aplicativos que você usa, entre em contato com o suporte técnico, departamento de TI ou administrador. Se estiver vendo mensagens sobre políticas de retenção em chats do Teams e mensagens do canal, pode ser útil revisar [Mensagens do Teams sobre políticas de retenção](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

## <a name="before-you-begin"></a>Antes de começar

O administrador global da sua organização tem permissões completas para criar e editar as políticas de retenção. Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos	de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Criar e configurar uma política de retenção

Embora uma política de retenção possa oferecer suporte a vários serviços identificados como "locais" na política de retenção, você não pode criar uma única política de retenção que inclua todos os locais com suporte:

- Email do Exchange
- Site do SharePoint
- Contas do OneDrive
- Grupos do Microsoft 365
- Skype for Business
- Pastas públicas do Exchange
- Mensagens do canal do Teams
- Chats do Teams
- Mensagens da comunidade do Yammer
- Mensagens privadas do Yammer

Quando você seleciona um dos locais do Teams ou Yammer quando cria uma política de retenção, os outros locais são excluídos automaticamente. Isso significa que as instruções a seguir dependem de você precisar incluir os locais Teams ou do Yammer:

- [Instruções para uma política de retenção para locais do Teams](#retention-policy-for-teams-locations)
- [Instruções para uma política de retenção para locais do Yammer](#retention-policy-for-yammer-locations)
- [Instruções para uma política de retenção para locais do Teams e Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

Quando você tem mais de uma política de retenção, e quando você também usa rótulos de retenção, consulte [Princípios de retenção ou o que tem precedência?](retention.md#the-principles-of-retention-or-what-takes-precedence) para compreender o que acontece quando várias configurações de retenção se aplicam ao mesmo conteúdo.

### <a name="retention-policy-for-teams-locations"></a>Política de retenção para locais do Teams

1. No [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/), selecione **Políticas** > **Retenção**.

2. Selecione **Nova política de retenção** para iniciar o assistente Criar política de retenção, e a nomeie.

3. Para a página **Escolher locais para aplicar a política**, selecione um ou ambos os locais para o Teams: **Mensagem de canal do Teams** e **chats do Teams**.

   Para as **Mensagens de canal do Teams**, estão incluídas mensagens de canais padrão, mas não de [canais privados](/microsoftteams/private-channels). No momento, canais privados não são suportados pelas políticas de retenção.

   Por padrão, [todas as equipes e usuários são selecionados](#a-policy-that-applies-to-entire-locations), mas você pode filtrar isso selecionando as opções de [**Escolha** e **Exclusão**](#a-policy-with-specific-inclusions-or-exclusions).

4. Para **decidir se deseja reter o conteúdo, excluí-lo, ou ambos** página do assistente, especifique as opções de configuração para manter e excluir o conteúdo.

   Você pode criar uma política de retenção que apenas retenha o conteúdo sem excluir, retenha e exclua após um período especificado ou apenas exclua o conteúdo após um período especificado. Para saber mais, confira [Configurações de retenção e exclusão de conteúdo](#settings-for-retaining-and-deleting-content) nesta página.

5. Conclua o assistente para salvar suas configurações.

Para mais informações sobre as políticas de retenção para o Teams, confira [Políticas de retenção no Microsoft Teams](/microsoftteams/retention-policies) da documentação do Teams.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Adicionais políticas de retenção necessárias para oferecer suporte ao Teams

O Teams é muito mais que apenas chats e mensagens de canal. Se você tiver equipes criadas a partir de um grupo do Microsoft 365 (antigo Grupo do Office 365), deverá configurar uma política de retenção que inclui o grupo do Microsoft 365 usando o local **Grupos do Microsoft 365**. Essa política de retenção se aplica ao conteúdo da caixa de correio do grupo, site e arquivos.

Se você tiver um site da equipe que não está conectado a um grupo do Microsoft 365, você precisará de uma política de retenção que inclui os locais dos **sites do SharePoint** ou das **contas do OneDrive** locais para manter e excluir arquivos no Teams:

- Os arquivos compartilhados no chat são armazenados na conta do OneDrive do usuário que compartilhou o arquivo.

- Os arquivos carregados nos canais são armazenados no site do SharePoint usado pela equipe.

> [!TIP]
> Você pode aplicar uma política de retenção aos arquivos apenas para uma equipe específica quando não estiver conectado a um grupo do Microsoft 365, selecionando o site do SharePoint para a equipe e as contas de usuários do OneDrive no Teams.

É possível que uma política de retenção aplicada aos grupos do Microsoft 365, sites do SharePoint ou contas do OneDrive, exclua um arquivo referenciado em uma mensagem de bate-papo ou de um canal do Teams para que as mensagens sejam excluídas. Neste cenário, o arquivo ainda é exibido na mensagem do Teams, mas quando os usuários selecionam o arquivo, eles recebem o erro "arquivo não encontrado". Esse comportamento não é específico das políticas de retenção e também pode acontecer se um usuário exclui manualmente um arquivo do SharePoint ou do OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Política de retenção para locais do Yammer

> [!NOTE]
> As políticas de retenção para o Yammer estão sendo distribuídas na visualização. Caso ainda não veja os novos locais do Yammer, tente novamente em algumas semanas.
>
> Para usar esse recurso, sua rede do Yammer deve ser [Modo Nativo](/yammer/configure-your-yammer-network/overview-native-mode), não no modo híbrido.

1. No [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/), selecione **Políticas** > **Retenção**.

2. Selecione **Nova política de retenção** para criar uma nova política de retenção.

3. Para **decidir se deseja reter o conteúdo, excluí-lo, ou ambos** página do assistente, especifique as opções de configuração para manter e excluir o conteúdo. 
    
    Você pode criar uma política de retenção que apenas retenha o conteúdo sem excluir, retenha e exclua após um período especificado ou apenas exclua o conteúdo após um período especificado. Para saber mais, confira [Configurações de retenção e exclusão de conteúdo](#settings-for-retaining-and-deleting-content) nesta página.
    
    Não selecione **Usar as configurações avançadas de retenção** porque essa opção não tem suporte para os locais do Yammer. 

4. Na página **Escolher locais**, selecione **Deixe-me escolher locais específicos**. Em seguida, alterne em um ou em ambos os locais do Yammer: **Mensagens da comunidade do Yammer** e **mensagens particulares do Yammer**.
    
    Por padrão, todas as comunidades e todos os usuários são selecionados, mas você pode refinar isso especificando as comunidades e os usuários a serem incluídos ou excluídos.
    
    Para mensagens privadas do Yammer: 
    - Se você deixar o padrão em **Todos**, os usuários convidados do Azure B2B não serão incluídos. 
    - Se você selecionar **Escolher usuário**, você poderá aplicar uma política de retenção a usuários externos se souber a conta deles.

5. Conclua o assistente para salvar suas configurações.

Para mais informações a respeito do funcionamento das políticas de retenção para o Yammer, confira [Saiba mais sobre a retenção para Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Políticas de retenção adicionais necessárias para apoiar o Yammer

O Yammer é mais do que somente mensagens e mensagens privadas em uma comunidade. Para reter e excluir as mensagens de email da sua rede do Yammer, configure uma política de retenção adicional que inclua quaisquer grupos do Microsoft 365 que são utilizados pelo Yammer, utilizando o local **Grupos do Microsoft 365**. 

Para manter e excluir arquivos armazenados no Yammer, você precisa de uma política de retenção que inclua localizações de **sites do SharePoint** ou **contas do OneDrive**:

- Os arquivos compartilhados em mensagens privadas são armazenados na conta do OneDrive do usuário que compartilhou o arquivo. 

- Os arquivos carregados nas comunidades são armazenados no site do SharePoint usado pela comunidade Yammer.

É possível que uma política de retenção que seja aplicada aos sites do SharePoint ou contas do OneDrive exclua um arquivo referenciado em uma mensagem do Yammer antes que a mensagem seja excluída. Neste cenário, o arquivo ainda é exibido na mensagem do Yammer, mas quando os usuários selecionam o arquivo, eles recebem o erro "Arquivo não encontrado". Esse comportamento não é específico das políticas de retenção e também pode acontecer se um usuário exclui manualmente um arquivo do SharePoint ou do OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Política de retenção para locais diferentes do Teams e do Yammer

Use as instruções a seguir para políticas de retenção que se aplicam a qualquer um desses serviços:

- Exchange: E-mails e pastas públicas
- SharePoint: Sites
- OneDrive: Contas
- Grupos do Microsoft 365
- Skype for Business

1. No [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/), selecione **Políticas** > **Retenção**.

2. Selecione **Nova política de retenção** para iniciar o assistente Criar política de retenção, e a nomeie.

3. Para a página **Escolha locais**, ative ou desative qualquer uma das localizações, exceto os locais para o Teams. Para cada local, você pode deixá-lo no padrão para [Aplicar a política em todo local](#a-policy-that-applies-to-entire-locations) ou [Especificar inclusões e exclusões](#a-policy-with-specific-inclusions-or-exclusions).

    Informações específicas para locais:
    - [Email do Exchange e pastas públicas do Exchange](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Sites do SharePoint e contas do OneDrive](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Grupos do Microsoft 365](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

4. Para **decidir se deseja reter o conteúdo, excluí-lo, ou ambos** página do assistente, especifique as opções de configuração para manter e excluir o conteúdo.

    Você pode criar uma política de retenção que apenas retenha o conteúdo sem excluir, retenha e exclua após um período especificado ou apenas exclua o conteúdo após um período especificado. Para saber mais, confira [Configurações de retenção e exclusão de conteúdo](#settings-for-retaining-and-deleting-content) nesta página.

5. Conclua o assistente para salvar suas configurações.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Informações de configuração para o email do Exchange e para as pastas públicas do Exchange

O local **email do Exchange** oferece suporte à retenção de emails, calendários e outros itens de caixa de correio dos usuários, aplicando as configurações de retenção no nível de uma caixa de correio.

Para obter informações detalhadas sobre quais itens são incluídos e excluídos quando você define as configurações de retenção do Exchange, confira [O que está incluído para retenção e exclusão](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

Observe que, embora um grupo do Microsoft 365 tenha uma caixa de correio do Exchange, uma política de retenção que inclui todo o local do **Email do Exchange** não inclui conteúdo nas caixas de correio do grupo Microsoft 365. Para reter o conteúdo nessas caixas de correio, selecione o local **Grupos do Microsoft 365**.

O local **Pastas públicas do Exchange** aplica as configurações de retenção a todas as pastas públicas e não pode ser aplicado no nível de pasta ou caixa de correio.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Informações de configuração para sites do SharePoint e contas do OneDrive

Quando você escolhe o local **sites do SharePoint**, a política de retenção pode reter e excluir documentos em sites de comunicação do SharePoint, sites de equipe que não estão conectados por grupos do Microsoft 365 e sites clássicos. Os sites de equipe conectados por grupos do Microsoft 365 não possuem suporte com essa opção. Use o local **Grupos do Microsoft 365** que se aplica ao conteúdo da caixa de correio, sites e arquivos do grupo.

Embora a política de retenção seja aplicada no nível do site, apenas os documentos têm configurações de retenção aplicadas a eles. Para obter informações detalhadas sobre o que está incluído e excluído quando você define as configurações de retenção do Microsoft Office SharePoint Online e do OneDrive, confira [O que está incluído para a retenção e a exclusão](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion). 

Ao especificar os locais para os sites do SharePoint ou contas do OneDrive, não será preciso ter permissões para acessar os sites e nenhuma validação será feita ao especificar a URL na página **Editar locais**. No entanto, os sites do Microsoft Office SharePoint Online que você especifica são verificados para ver se existem no final do assistente. Se essa verificação falhar, uma mensagem será exibida informando que a validação falhou para a URL inserida, e o assistente não criará a política de retenção até que a verificação de validação seja aprovada. Se você vir esta mensagem, volte ao assistente para alterar a URL ou remover o site da política de retenção.

Para especificar contas individuais do OneDrive para incluir ou excluir o URL tem o seguinte formato: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Por exemplo, para um usuário no locatário contoso que tenha um nome de usuário "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Para verificar a sintaxe do seu locatário e identificar URLs dos usuários, confira [Obter uma lista de todas as URLs de usuário do OneDrive em sua organização](/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Informações de configuração do Grupos do Microsoft 365

Para reter ou deletar o conteúdo de um grupo do Microsoft 365 (antigo Grupo Office 365), use o local **Grupos do Microsoft 365**. Mesmo que um grupo do Microsoft 365 tenha uma caixa de correio do Exchange, uma política de retenção que inclua todo o local **E-mail do Exchange** não incluirá conteúdo nas caixas de correio de grupo do Microsoft 365. Além disso, embora o local **E-mail do Exchange** permita inicialmente especificar uma caixa de correio de grupo a ser incluída ou excluída, ao tentar salvar a política de retenção, você recebe um erro indicando que "RemoteGroupMailbox" não é uma seleção válida para o local do Exchange.

Uma política de retenção aplicada a um grupo do Microsoft 365 inclui a caixa de correio e o site de equipe do SharePoint. Os arquivos armazenados no site de equipes do SharePoint são cobertos por este local, mas não os chats do Teams ou as mensagens do canal do Teams que têm seus próprios locais de política de retenção.

### <a name="configuration-information-for-skype-for-business"></a>Informações de configuração do Skype for Business

Diferentemente de um email do Exchange, você não pode ativar ou desativar o status de local do Skype para incluir automaticamente todos os usuários, mas pode ativar esse local e depois deve selecionar manualmente os usuários cujas conversas deseja manter:

![Escolha o local do Skype para políticas de retenção](../media/skype-location-retention-policies.png)

Ao selecionar **Escolher usuário**, você pode incluir rapidamente todos os usuários, selecionando a caixa **Selecionar todos**. No entanto, é importante compreender que cada usuário conta como uma inclusão específica na política. Portanto, se você incluir 1.000 usuários selecionando a caixa **Selecionar todos**, é a mesma coisa que selecionar manualmente 1.000 usuários para incluir, que é o número máximo suportado pelo Skype for Business.

Lembre-se de que o **Histórico da conversa**, uma pasta no Outlook, é um recurso que nada tem a ver com o recurso de arquivamento do Skype. O **Histórico da conversa** pode ser desativado pelo usuário final, mas o arquivamento para o Skype é feito armazenando-se uma cópia das conversas do Skype em uma pasta oculta que é inacessível ao usuário, mas disponível para Descoberta Eletrônica.

## <a name="settings-for-retaining-and-deleting-content"></a>Configurações de retenção e exclusão de conteúdo

Ao escolher as configurações de retenção e exclusão de conteúdo em sua política de retenção, sua política de retenção terá uma das seguintes configurações por um período especificado:

- Somente reter

    Para essa configuração, escolha **Reter itens por um período específico** e **No final do período de retenção: não fazer nada**. Ou marque **Reter itens para sempre**.

- Reter e excluir

    Para essa configuração, escolha **Reter itens por um período específico** e **No final do período de retenção: excluir itens automaticamente**.

- Somente excluir

    Para essa configuração, escolha **Excluir itens somente quando eles atingirem um determinado tempo**.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Reter o conteúdo por um período específico

Ao configurar uma política de retenção, você opta por reter os itens por um número específico de dias, meses ou anos. Ou, se preferir, mantenha os itens indefinidamente.

Ao configurar uma política de retenção, você pode optar por reter o conteúdo indefinidamente ou por um número específico de dias, meses ou anos. O período de retenção é calculado com base na idade desse conteúdo, e não do momento em que a política de retenção foi aplicada.

Para o início do período de retenção, você pode escolher quando o conteúdo foi criado ou com suporte apenas para arquivos e os locais do SharePoint, do OneDrive e dos Grupos do Office 365 quando o conteúdo foi modificado pela última vez.

Exemplos:

- SharePoint: se você quiser preservar os itens em um conjunto de sites por sete anos depois que esse conteúdo foi modificado, e um documento nesse conjunto de sites não tiver sido modificado em seis anos, o documento será retido somente por mais um ano caso não seja modificado. Se o documento for editado novamente, a idade do documento será calculada a partir da última data de modificação, e ele ficará retido por mais sete anos.

- Exchange: se você deseja reter os itens em uma caixa de correio por sete anos, e uma mensagem foi enviada há seis anos, esta será retida por apenas um ano. Para os itens do Exchange, a idade é baseada na data de recebimento do email de entrada ou na data de envio do email de saída. O processo de reter os itens com base em quando ele foi modificado pela última vez é aplicável apenas ao conteúdo de sites do OneDrive e do SharePoint.

No final do período de retenção, você pode escolher se deseja que o conteúdo seja excluído permanentemente:

![Página de configurações de Retenção](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Como excluir conteúdo mais antigo que uma idade específica

Uma política de retenção pode reter e excluir os itens ou excluir os itens antigos sem retê-los.

Em ambos os casos, se sua política de retenção excluir os itens, será importante entender que o período de tempo especificado para uma política de retenção é calculado pelo tempo em que o item foi criado ou modificado, e não a partir do momento em que a política foi atribuída.

Portanto, antes de adicionar uma política de retenção pela primeira vez, e especialmente quando essa política exclui itens, considere primeiro considerar a idade dos conteúdos e de que modo a política poderá afetá-los. Você também poderá informar os seus usuários sobre a nova política antes de atribuí-la, para que eles tenham tempo para avaliar o possível impacto.

### <a name="a-policy-that-applies-to-entire-locations"></a>Uma política aplicável a locais inteiros

Ao escolher locais, com exceção do Skype for Business, a configuração padrão é **Todos** quando o status do local é **Ativado**.

Quando uma política de retenção se aplica a qualquer combinação de locais inteiros, não há limite para o número de destinatários, sites, contas, grupos, etc., que a política pode incluir.

Por exemplo, se uma política incluir todos os emails do Exchange e sites do SharePoint, todos os sites e destinatários serão incluídos, independentemente da quantidade. Além disso, no caso do Exchange, todas as caixas de correio criadas após a aplicação da política herdam a política automaticamente.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Uma política com inclusões ou exclusões específicas

Lembre-se de que se você usar a configuração opcional para estender suas configurações de retenção a usuários específicos, grupos específicos do Microsoft 365 ou sites específicos, haverá alguns limites por política a serem considerados. Para obter mais informações, confira [Limites para políticas e rótulos de retenção](retention-limits.md). 

Para usar a configuração opcional para definir o escopo de suas configurações de retenção, certifique-se de que o **Status** desse local esteja **Ativado**, em seguida, use os links para incluir ou excluir usuários específicos, grupos do Microsoft 365 ou sites.

> [!WARNING]
> Se você inclui-lo e, em seguida, remover o último, a configuração será revertida em **Todas** para o local.  Verifique se esta é a configuração que você pretende antes de salvar a política.
>
> Por exemplo, se você especificar um site do SharePoint a ser incluído na sua política de retenção que está configurada para excluir dados e, em seguida, remover o site único, por padrão, todos os sites do SharePoint estarão sujeitos à política de retenção que exclui permanentemente os dados. O mesmo se aplica a inclusões para os destinatários do Exchange, contas do OneDrive, usuários de chat do Teams, etc.
>
> Neste cenário, desative o local se não quiser que a configuração **Todos** para o local estejam sujeitos à política de retenção. Como alternativa, especifique exclusões a serem isentas da política.

## <a name="updating-retention-policies"></a>Atualizar políticas de retenção

Algumas configurações não podem ser alteradas depois que o rótulo de retenção é criado e salvo, que incluem:
- O nome da política de retenção e as configurações de retenção, exceto o período de retenção, e quando começar o período de retenção.

Se você editar uma política de retenção e os itens já estiverem sujeitos às configurações originais da sua política de retenção, as configurações atualizadas serão aplicadas automaticamente a esses itens, além dos itens identificados recentemente.

Geralmente, essa atualização é bastante rápida, mas pode levar vários dias. Quando a replicação da política nos locais do Microsoft 365 estiver concluída, você verá o status da política de retenção no Centro de Conformidade do Microsoft 365 mudar de **Ativado (Pendente)** para **Ativado (Sucesso)**.

## <a name="locking-the-policy-to-prevent-changes"></a>Bloquear a política para evitar alterações

Se você precisar garantir que ninguém pode desabilitar a política, excluí-la ou torná-la menos restritiva, confira [Usar Bloqueio de Preservação para restringir alterações nas políticas de retenção e nas políticas de rótulo de retenção](retention-preservation-lock.md).