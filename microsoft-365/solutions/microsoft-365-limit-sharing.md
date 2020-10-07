---
title: Limitar o compartilhamento no Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: Saiba mais sobre as opções para limitar ou desabilitar o compartilhamento no Microsoft 365.
ms.openlocfilehash: 7397078b6f347858e4ca91a0deeb9a1cf2fb6911
ms.sourcegitcommit: d648356b27842e779921859480b1b405a1804c7c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361900"
---
# <a name="limit-sharing-in-microsoft-365"></a>Limitar o compartilhamento no Microsoft 365

Embora não seja possível desabilitar o compartilhamento interno inteiramente ou remover o botão compartilhar de sites, há várias maneiras de limitar o compartilhamento no Microsoft 365 para atender às necessidades da sua organização.

Os métodos de compartilhamento de arquivos são listados na tabela a seguir. Clique no link na coluna **método de compartilhamento** para obter informações detalhadas.

|Método de compartilhamento|Descrição|Limitando opções|
|:-------------|:----------|:-------------|
|[Grupo ou equipe do Microsoft 365](#microsoft-365-group-or-team)|As pessoas com acesso a uma equipe do Microsoft Teams ou ao grupo do Microsoft 365 têm acesso à edição de arquivos no site associado do SharePoint.|Se o grupo ou a equipe for privada, o compartilhamento de convites para se juntar à equipe vai para o proprietário para aprovação. Os administradores podem desabilitar o acesso de convidados ou usar rótulos de confidencialidade para impedir o acesso de pessoas de fora da organização.|
|[Site do Microsoft Office SharePoint Online](#sharepoint-site)|Os usuários podem ter acesso de proprietário, membro ou visitante em um site do SharePoint e terão esse nível de acesso a arquivos no site.|As permissões de site podem ser restringidas para que somente proprietários de site possam compartilhar o site. Os administradores podem configurar um site para somente leitura ou bloquear o acesso inteiramente.|
|[Compartilhar com pessoas específicas](#sharing-with-specific-people)|Os membros do site e as pessoas com permissões de edição podem conceder permissões diretas a arquivos e pastas ou compartilhá-los usando links de *pessoas específicas*.|As permissões de site podem ser restringidas para que somente proprietários de sites possam compartilhar arquivos e pastas. Nesse caso, o acesso direto e o compartilhamento de link*pessoas específicas* por membros do site vai para o proprietário do site para aprovação.|
|[Compartilhamento de convidados do SharePoint](#sharepoint-guest-sharing)|Os proprietários e membros do site do SharePoint podem compartilhar arquivos e pastas com pessoas de fora da organização.|O compartilhamento de convidados pode ser desabilitado para toda a organização ou para sites individuais.|
|[*Pessoas na sua organização* links de compartilhamento](#people-in-your-organization-sharing-links)|Os proprietários e membros do site do SharePoint podem compartilhar arquivos usando links *pessoas em sua organização*, que funcionam para todos dentro da organização.|Os links*Pessoas da sua organização* podem ser desabilitados no nível do site.|
|[Criar sites, grupos e equipes](#create-sites-groups-and-teams)|Por padrão, os usuários podem criar novos sites, grupos e equipes a partir dos quais podem compartilhar conteúdo.|Os administradores podem restringir as pessoas que podem criar sites, grupos e equipes.|
|[Email](#email)|As pessoas que têm acesso a um arquivo podem enviá-lo para outras pessoas por e-mail.|Os administradores podem criptografar arquivos usando rótulos de confidencialidade para impedi-los de compartilhar com pessoas não autorizadas.|
|[Baixar ou copiar arquivo](#download-or-file-copy)|As pessoas que têm acesso a um arquivo podem baixá-lo ou copiá-lo e compartilhá-lo com outras pessoas fora do escopo do Microsoft 365.|Os administradores podem criptografar arquivos usando rótulos de confidencialidade para impedi-los de compartilhar com pessoas não autorizadas.|

Você também pode restringir as condições em que as pessoas acessam o conteúdo compartilhado. Confira [acesso condicional](#conditional-access) mais adiante neste artigo para saber mais.

Embora você possa usar os controles de administração descritos neste artigo para limitar o compartilhamento em sua organização, é altamente recomendável que você considere o uso dos recursos de segurança e conformidade disponíveis no Microsoft 365 para criar um ambiente de compartilhamento seguro. Confira [Colaboração de arquivos no SharePoint com o Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) e [Configurar uma equipe com isolamento de segurança](secure-teams-security-isolation.md) para obter informações.

Para entender como o compartilhamento está sendo usado em sua organização, [execute um relatório de compartilhamento de arquivos e pastas](https://docs.microsoft.com/sharepoint/sharing-reports).

## <a name="microsoft-365-group-or-team"></a>Grupo ou equipe do Microsoft 365

Se você deseja limitar o compartilhamento em um grupo do Microsoft 365 ou equipe do Microsoft Teams, é importante tornar o grupo ou a equipe particular. As pessoas da sua organização podem se juntar a um grupo público ou a uma equipe a qualquer momento. A menos que o grupo ou a equipe seja particular, não há nenhuma maneira de limitar o compartilhamento da equipe ou de seus arquivos dentro da organização.

### <a name="guest-sharing"></a>Compartilhamento de convidados

Se você quiser impedir o acesso de convidados nas equipes, é possível desativar o compartilhamento de convidados no centro de administração do Teams.

Para desativar o compartilhamento de convidados para o Teams
1. No centro de administração do Teams, expanda **Configurações para toda a organização**, em seguida, clique em **Acesso de convidado**.
2. Desabilite **Permitir acesso de convidados no Teams**.
3. Clique em **Salvar**.

Se você quiser impedir o acesso de convidado em grupos do Microsoft 365, é possível desativar as configurações de acesso de convidado do grupo no Centro de administração do Microsoft 365.

Para desativar o compartilhamento de convidados no Microsoft 365 Groups
1. No centro de administração do Microsoft 365, clique em **Configurações**e em **Configurações**.
2. Na guia **Serviços**, clique em **Microsoft 365 Groups**.
3. Desmarque as caixas de seleções **Permitir que os membros do grupo fora da organização acessem o conteúdo do grupo**e **Permita que os proprietários de grupos adicionem pessoas de fora da sua organização a grupos**.
4. Clique em **Salvar alterações**.

    ![A captura de tela do compartilhamento de configurações do Microsoft 365 Groups no Centro de administração do Microsoft 365](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> Se você quiser impedir o compartilhamento de convidados para um determinado grupo ou equipe, poderá fazê-lo usando o [Microsoft PowerShell](per-group-guest-access.md) ou[rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Você pode limitar o compartilhamento de convidados a usuários de domínios específicos permitindo ou bloqueando domínios no Azure Active Directory. Isso também afetará o compartilhamento de convidados no SharePoint se você tiver habilitado a [integração do SharePoint e do OneDrive com o B2B do Azure AD](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Para permitir o compartilhamento de convites apenas de domínios especificados
1. Na página Visão geral do Azure Active Directory, clique em **relações organizacionais**.
2. Clique em **Configurações**.
3. Em **restrições de colaboração**, marque **negar convites aos domínios especificados** ou **permitir convites apenas para os domínios especificados**, e digite os domínios que você deseja usar.
4. Clique em **Salvar**.

    ![Captura de tela das configurações de restrições de colaboração do Azure Active Directory](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a>Site do SharePoint

Só é possível limitar o compartilhamento de sites do SharePoint aos proprietários de site. Isso impede que os membros do site compartilhem o site. Lembre-se de que, se o site estiver conectado a um grupo do Microsoft 365, os membros do grupo poderão convidar outras pessoas para o grupo e esses usuários terão acesso ao site.

Para limitar o compartilhamento de sites aos proprietários
1. No site, clique no ícone de engrenagem e, em seguida, clique em **permissões de site**.
2. Em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3. Selecione **Proprietários e membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site**.
4. Clique em **Salvar**.

    ![Captura de tela das configurações de permissões de compartilhamento em um site do SharePoint](../media/sharepoint-site-sharing-permissions-level-two.png)

Você pode impedir que os usuários que não são membros do site solicitem acesso desativando as solicitações de acesso.

Para desativar as solicitações de acesso
1. No site, clique no ícone de engrenagem e, em seguida, clique em **permissões de site**.
2. Em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3. Desabilite **Permitir solicitações de acesso** e clique em **Salvar**.

Para limitar o compartilhamento de sites a domínios específicos, permita ou bloqueie domínios para o site.

Para limitar o compartilhamento do site por domínio
1. No centro de administração do SharePoint, em **sites**, clique **sites ativos**.
2. Clique no site que você deseja configurar.
3. Na guia **Políticas**, em **Compartilhamento externo** clique **Editar**.
4. Em **Configurações avançadas para compartilhamento externo**, marque **Limitar compartilhamento por domínio**.
5. Adicione os domínios que deseja permitir ou bloquear e, em seguida, clique em **Salvar**.
6. Clique em **Salvar**.

    ![Captura de tela da configuração de domínios permitidos no nível do site](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a>Bloquear o acesso a um site

Você pode bloquear o acesso a um site ou torná-lo somente leitura, alterando o estado de bloqueio do site. Para obter detalhes, confira [Bloquear e desbloquear sites](https://docs.microsoft.com/sharepoint/manage-lock-status).

### <a name="permissions-inheritance"></a>Herança de permissões

Embora não seja recomendável, você pode usar a [herança de permissões do SharePoint](https://docs.microsoft.com/sharepoint/what-is-permissions-inheritance) para personalizar os níveis de acesso aos sites e subsites.

## <a name="sharing-with-specific-people"></a>Compartilhar com pessoas específicas

Se desejar limitar o compartilhamento de um site ou de seu conteúdo, você poderá configurar o site para permitir que somente os proprietários de sites compartilhem arquivos, pastas e site. Quando isso é configurado, os membros do site tentam compartilhar arquivos ou pastas usando links de *pessoas específicas* vão para o proprietário do site para aprovação.

Para limitar o compartilhamento de sites, arquivos e pastas aos proprietários
1. No site, clique no ícone de engrenagem e, em seguida, clique em **permissões de site**.
2. Em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.
3. Selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.
4. Clique em **Salvar**.

    ![Captura de tela das configurações de permissões de compartilhamento em um site do SharePoint definidas como somente para proprietários](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a>Compartilhamento de convidados do SharePoint

Se você quiser impedir o compartilhamento de pastas e arquivos do SharePoint ou do OneDrive com pessoas de fora da sua organização, é possível desativar o compartilhamento de convidados para toda a organização ou para um site individual.

Para desativar o compartilhamento de convidados do SharePoint para a sua organização
1. No centro de administração do SharePoint, em **Políticas**, clique em **Compartilhamento**.
2. Em **Compartilhamento externo**, arraste o controle deslizante do SharePoint para baixo para **Somente as pessoas da sua organização**.
3. Clique em **Salvar**.

    ![Captura de tela das configurações de compartilhamento no nível da organização do SharePoint definidas como Qualquer Pessoa](../media/sharepoint-tenant-sharing-off.png)


Para desativar o compartilhamento de convidados para um site
1. No centro de administração do SharePoint, em **sites**, clique **sites ativos**.
2. Clique no site que você deseja configurar.
3. Na guia **Políticas**, em **Compartilhamento externo** clique **Editar**.
4. Em **Compartilhamento externo**, escolha **Somente as pessoas da sua organização**e, em seguida, clique em **Salvar**.

    ![Captura de tela das configurações de compartilhamento no nível do site do SharePoint definidas para Somente as pessoas da sua organização](../media/sharepoint-site-external-sharing-settings-off.png)

Se você deseja permitir o compartilhamento com pessoas de fora da sua organização, mas deseja garantir que todos sejam autenticados, é possível desativar os links *Todos* (compartilhamento anônimo) para toda a organização ou para um site individual.

Para desativar os links *Todos* no nível da organização
1. No centro de administração do SharePoint, em **Políticas**, clique em **Compartilhamento**.
2. Em **Compartilhamento externo**, arraste o controle deslizante do SharePoint para baixo para **Convidados novos e existentes**.
3. Clique em **Salvar**.

    ![Captura de tela das configurações de compartilhamento no nível de organização do SharePoint definidas como Convidados novos e existentes](../media/sharepoint-guest-sharing-new-existing-guests.png)

Para desativar os links para *Qualquer pessoa* de um site
1. No centro de administração do SharePoint, em **sites**, clique **sites ativos**.
2. Clique no site que você deseja configurar.
3. Na guia **Políticas**, em **Compartilhamento externo** clique **Editar**.
4. Em **Compartilhamento externo**, escolha **Convidados novos e existentes**e, em seguida, clique em **Salvar**.

    ![Captura de tela das configurações de compartilhamento no nível do site do SharePoint definidas como Configurações novas e existentes](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a>Links de compartilhamento *Pessoas na sua organização*

Por padrão, os membros de um site podem compartilhar arquivos e pastas com outras pessoas da sua organização, usando o link*pessoas na sua organização*. Você pode desabilitar os links *Pessoas em sua organização* usando o PowerShell:

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

Por exemplo:

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="create-sites-groups-and-teams"></a>Compartilhar sites, grupos e equipes

Por padrão, os usuários podem criar novos sites, grupos e equipes a partir dos quais podem compartilhar conteúdo (dependendo das suas configurações de compartilhamento). Você pode restringir as pessoas que podem criar sites, grupos e equipes. Confira as seguintes referências:

- [Gerenciar a criação de sites no SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
- [Gerenciar quem pode criar grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

Observe que a restrição à criação de um grupo restringe a criação da equipe.

## <a name="email"></a>Email

Você pode impedir o compartilhamento indesejado de e-mails usando criptografia. Isso impede que os e-mails sejam enviados ou compartilhados com usuários não autorizados. A criptografia de e-mail pode ser habilitada usando rótulos de confidencialidade. Confira [Restringir o acesso ao conteúdo usando criptografia nos rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para obter detalhes.

## <a name="download-or-file-copy"></a>Baixar ou copiar arquivo

Os usuários que têm acesso a arquivos e pastas no Microsoft 365 podem baixar e copiar arquivos para uma mídia externa. Para reduzir o risco de compartilhamento indesejado de arquivos, você pode criptografar o conteúdo usando rótulos de confidencialidade.

## <a name="conditional-access"></a>Acesso condicional

O acesso condicional do Azure Active Directory fornece opções para limitar ou impedir o compartilhamento com pessoas com base no local de rede, integridade do dispositivo, riscos de entrada e outros fatores. [O que é o Acesso Condicional?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

O SharePoint fornece integração direta com o acesso condicional do Azure AD para o local de rede e os dispositivos não gerenciados. Confira os detalhes a seguir:

- [Controlar o acesso de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
- [Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a>Confira também

[Referência das configurações de compartilhamento de convidados do Microsoft 365](microsoft-365-guest-settings.md)
