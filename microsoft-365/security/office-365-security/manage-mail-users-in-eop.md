---
title: Gerenciar usuários de email no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Saiba como gerenciar usuários de email no Exchange Online Protection (EOP), incluindo o uso da sincronização de diretórios, do EAC e do PowerShell para gerenciar usuários.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34edafea7567da04094ea386d469d3d27937eee5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166388"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Gerenciar usuários de email no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](https://go.microsoft.com/fwlink/?linkid=2148611)

Em organizações autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, os usuários de email são o tipo fundamental de conta de usuário. Um usuário de email tem credenciais de conta em sua organização autônoma do EOP e pode acessar recursos (ter permissões atribuídas). O endereço de email de um usuário de email é externo (por exemplo, em seu ambiente de email local).

> [!NOTE]
> Quando você cria um usuário de email, a conta de usuário correspondente fica disponível no centro de administração do Microsoft 365. Ao criar uma conta de usuário no centro de administração do Microsoft 365, você não pode usar essa conta para criar um usuário de email.

O método recomendado para criar e gerenciar usuários de email no EOP [](#use-directory-synchronization-to-manage-mail-users) autônomo é usar a sincronização de diretório conforme descrito na sincronização usar diretório para gerenciar a seção usuários de email posteriormente neste artigo.

Para organizações autônomas do EOP com um pequeno número de usuários, você pode adicionar e gerenciar usuários de email no Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo, conforme descrito neste artigo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de administração do Exchange (EAC), confira o Centro de administração [do Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Ao criar usuários de email no EOP PowerShell, você pode encontrar a throttling. Além disso, os cmdlets do EOP PowerShell usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos sejam visíveis.

- Você precisa ter permissões no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa das funções de Criação **de** Destinatário de Email (criar) e Destinatários de  Email (modificar), que são **atribuídas** aos grupos de função Gerenciamento da Organização **(administradores** globais) e Gerenciamento de Destinatários por padrão. Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda nos fóruns do Exchange. Visite o fórum [do Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Usar o Centro de administração do Exchange para gerenciar usuários de email

### <a name="use-the-eac-to-create-mail-users"></a>Usar o EAC para criar usuários de email

1. No EAC, vá para **Contatos** \> **de Destinatários**

2. Clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Novo. Na página **Novo usuário de** email que é aberta, de configure as configurações a seguir. As configurações marcadas com <sup>\*</sup> um são necessárias.

   - **Nome**

   - **Iniciais:** a inicial do meio da pessoa.

   - **Sobrenome**

   - <sup>\*</sup>**Nome para** exibição: por padrão, essa caixa mostra os valores das caixas Nome **,** **Iniciais** e **Sobrenome.** Você pode aceitar esse valor ou alterá-lo. O valor deve ser exclusivo e ter um comprimento máximo de 64 caracteres.

   - <sup>\*</sup>**Alias:** insira um alias exclusivo, usando até 64 caracteres, para o usuário

   - **Endereço de email externo:** insira o endereço de email do usuário. O domínio deve ser externo à sua organização baseada em nuvem.

   - <sup>\*</sup>**ID de** usuário: insira a conta que a pessoa usará para entrar no serviço. A ID de usuário consiste em um nome de usuário à esquerda do símbolo de aa (@) e um domínio no lado direito.

   - <sup>\*</sup>**Nova senha** e <sup>\*</sup> **Confirmar senha:** insira e insira novamente a senha da conta. Verifique se a senha está em conformidade com os requisitos de comprimento, complexidade e histórico da sua organização.

3. Quando tiver terminado, clique em **Salvar** para criar o usuário de email.

### <a name="use-the-eac-to-modify-mail-users"></a>Usar o EAC para modificar usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você deseja modificar e clique em **Editar** ![ ](../../media/ITPro-EAC-AddIcon.png) ícone.

3. Na página de propriedades do usuário de email que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.

   Quando concluir, clique em **Salvar**.

#### <a name="general"></a>Geral

Use a **guia Geral** para exibir ou alterar informações básicas sobre o usuário de email.

- **Nome**

- **Iniciais**

- **Sobrenome**

- **Nome para** exibição: esse nome aparece no livro de endereços da sua organização, nas linhas Para: e De: no email e na lista de contatos no EAC. Esse nome não pode conter espaços vazios antes ou depois do nome para exibição.

- **ID de** usuário: esta é a conta do usuário no Microsoft 365. Você não pode modificar esse valor aqui.

#### <a name="contact-information"></a>Informações de contato

Use a **guia Informações de** contato para exibir ou alterar as informações de contato do usuário. As informações nesta página são exibidas no catálogo de endereços.

- **Street**
- **Cidade**
- **Estado/Província**
- **CEP**
- **País/região**
- **Telefone de trabalho**
- **Celular**
- **Fax**
- **Mais opções**

  - **Office**
  - **Telefone home**
  - **Página da Web**
  - **Anotações**

#### <a name="organization"></a>Organização

Use a **guia** Organização para registrar informações detalhadas sobre a função do usuário na organização.

- **Title**
- **Departamento**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Usar o EAC para remover usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você  deseja remover e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.

## <a name="use-powershell-to-manage-mail-users"></a>Usar o PowerShell para gerenciar usuários de email

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usar o EOP PowerShell autônomo para exibir usuários de email

Para retornar uma lista resumida de todos os usuários de email no EOP PowerShell autônomo, execute o seguinte comando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Para exibir informações detalhadas sobre um usuário de email específico, substitua pelo nome, alias ou nome da conta do usuário de email e \<MailUserIdentity\> execute os seguintes comandos:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-User.](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Usar o EOP PowerShell autônomo para criar usuários de email

Para criar usuários de email no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Observações**:

- O _parâmetro Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo. Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.
- Se você não usar o parâmetro _Alias,_ o lado esquerdo do parâmetro _MicrosoftOnlineServicesID_ será usado para o alias.
- Se você não usar o _parâmetro ExternalEmailAddress,_ o valor _de MicrosoftOnlineServicesID_ será usado para o endereço de email externo.

Este exemplo cria um usuário de email com as seguintes configurações:

- O nome é Ingárquica e o nome de exibição é Ãozão Zeng.
- O primeiro nome é Diogo e o sobrenome é Martins.
- O alias é diogom.
- O endereço de email externo é diogom@tailspintoys.com.
- O nome da conta é jeffreyz@contoso.onmicrosoft.com.
- A senha é Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Usar o EOP PowerShell autônomo para modificar usuários de email

Para modificar usuários de email existentes no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

Este exemplo define o endereço de email externo de Brenda Fernandes.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

Este exemplo define a propriedade Company de todos os usuários de email como Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Usar o EOP PowerShell autônomo para remover usuários de email

Para remover usuários de email no EOP PowerShell autônomo, substitua pelo nome, alias ou nome da conta do usuário de email e \<MailUserIdentity\> execute o seguinte comando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

Este exemplo remove o usuário de email de Ãozão Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu usuários de email com êxito no EOP autônomo, use um dos seguintes procedimentos:

- No EAC, acesse **Destinatários** \> **Contatos**. Verifique se o usuário de email está listado (ou não está listado). Selecione o usuário de email e veja as informações no painel Detalhes ou clique em **Editar** ícone ![ para exibir as ](../../media/ITPro-EAC-AddIcon.png) configurações.

- No EOP PowerShell autônomo, execute o seguinte comando para verificar se o usuário de email está listado (ou não está listado):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Substitua pelo nome, alias ou nome da conta do usuário de email e execute os seguintes comandos \<MailUserIdentity\> para verificar as configurações:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizar a sincronização de diretórios para gerenciar usuários de email

No EOP autônomo, a sincronização de diretórios está disponível para clientes com o Active Directory local. Você pode sincronizar essas contas com o Azure Active Directory (Azure AD), onde as cópias das contas são armazenadas na nuvem. Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, você pode exibir esses usuários no painel **Destinatários** do Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo.

**Observações**:

- Se você usar a sincronização de diretórios para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no Centro de administração do Microsoft 365, mas eles não serão sincronizados com seu Active Directory local. Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.

- A sincronização de diretório é recomendada para uso com os seguintes recursos:

  - **Listas de Remetentes** Seguros do Outlook e Listas de Remetentes Bloqueados: Quando sincronizadas com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço. Isso permite que os usuários gerenciem suas próprias listas de Remetentes Seguros e Remetentes Bloqueados com entradas individuais de remetente e domínio. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - Bloqueio de Borda Baseado em Diretório **(DBEB)**: Para obter mais informações sobre DBEB, consulte Usar Bloqueio de Borda Baseado em Diretório para rejeitar mensagens enviadas [a destinatários inválidos.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Acesso do usuário final à quarentena:** para acessar suas mensagens em quarentena, os destinatários devem ter uma ID de usuário e senha válidas no serviço. Para obter mais informações sobre a quarentena, consulte Encontrar e [liberar mensagens em quarentena como um usuário.](find-and-release-quarantined-messages-as-a-user.md)

  - Regras de fluxo de emails (também conhecidas como regras de **transporte)**: quando você usa a sincronização de diretórios, seus usuários e grupos existentes do Active Directory são carregados automaticamente para a nuvem e, em seguida, você pode criar regras de fluxo de email que visam usuários e/ou grupos específicos sem precisar adicioná-los manualmente no serviço. Observe que os [grupos dinâmicos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.

Obter as permissões necessárias e preparar a sincronização de diretórios, conforme descrito em O que é a identidade híbrida [com o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizar diretórios com o Azure Active Directory Connect (AAD Connect)

1. Ative a sincronização de diretórios conforme descrito na sincronização do [Azure AD Connect: entender e personalizar a sincronização.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Instale e configure um computador local para executar o AAD Connect conforme descrito em Pré-requisitos do [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Selecione o tipo de instalação a ser usado para o Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizados](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticação de passagem](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.

Depois de configurar sua sincronização, certifique-se de verificar se o AAD Connect está sincronizando corretamente. No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.
