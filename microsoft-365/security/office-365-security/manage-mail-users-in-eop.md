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
description: Saiba mais sobre como gerenciar usuários de email no Exchange Online Protection (EOP), incluindo o uso de sincronização de diretórios, EAC e PowerShell para gerenciar usuários.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910613"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Gerenciar usuários de email no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os usuários de email são o tipo fundamental de conta de usuário. Um usuário de email tem credenciais de conta em sua organização EOP autônoma e pode acessar recursos (tem permissões atribuídas). O endereço de email de um usuário de email é externo (por exemplo, em seu ambiente de email local).

> [!NOTE]
> Quando você cria um usuário de email, a conta de usuário correspondente está disponível no Centro de administração do Microsoft 365. Ao criar uma conta de usuário no Centro de administração do Microsoft 365, não é possível usar essa conta para criar um usuário de email.

O método recomendado para criar e gerenciar usuários de email no EOP [](#use-directory-synchronization-to-manage-mail-users) autônomo é usar a sincronização de diretório conforme descrito na seção Usar sincronização de diretórios para gerenciar usuários de email posteriormente neste artigo.

Para organizações EOP autônomas com um pequeno número de usuários, você pode adicionar e gerenciar usuários de email no Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo, conforme descrito neste artigo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de administração do Exchange (EAC), consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Ao criar usuários de email no EOP PowerShell, você pode encontrar a throttling. Além disso, os cmdlets do EOP PowerShell usam um método de processamento em lote que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos sejam visíveis.

- Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa das funções **Criação** de Destinatários de Email (criar) e Destinatários de Email  (modificar), que são **atribuídas** aos grupos de função Gerenciamento da Organização **(administradores** globais) e Gerenciamento de Destinatários por padrão. Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda nos fóruns do Exchange. Visite o [fórum de Proteção do Exchange Online.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Usar o Centro de administração do Exchange para gerenciar usuários de email

### <a name="use-the-eac-to-create-mail-users"></a>Usar o EAC para criar usuários de email

1. No EAC, vá  para \> **Destinatários Contatos**

2. Clique **em Novo** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) novo. Na página **Novo usuário de email** que é aberta, configure as configurações a seguir. As configurações marcadas com <sup>\*</sup> um são necessárias.

   - **Nome**

   - **Iniciais**: a inicial do meio da pessoa.

   - **Sobrenome**

   - <sup>\*</sup>**Nome para** exibição : Por padrão, esta caixa mostra os valores das caixas **Nome,** **Iniciais** e **Sobrenome.** Você pode aceitar esse valor ou alterá-lo. O valor deve ser exclusivo e tem um comprimento máximo de 64 caracteres.

   - <sup>\*</sup>**Alias**: insira um alias exclusivo, usando até 64 caracteres, para o usuário

   - **Endereço de email externo**: Insira o endereço de email do usuário. O domínio deve ser externo à sua organização baseada em nuvem.

   - <sup>\*</sup>**ID do** usuário : Insira a conta que a pessoa usará para entrar no serviço. A ID do usuário consiste em um nome de usuário no lado esquerdo do símbolo at (@) e um domínio no lado direito.

   - <sup>\*</sup>**Nova senha e** <sup>\*</sup> **Confirmar senha**: Insira e insira novamente a senha da conta. Verifique se a senha está em conformidade com os requisitos de comprimento, complexidade e histórico de senha da sua organização.

3. Quando tiver terminado, clique em **Salvar** para criar o usuário de email.

### <a name="use-the-eac-to-modify-mail-users"></a>Usar o EAC para modificar usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você deseja modificar e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) editar.

3. Na página propriedades do usuário de email que é aberta, clique em uma das seguintes guias para exibir ou alterar propriedades.

   Quando concluir, clique em **Salvar**.

#### <a name="general"></a>Geral

Use a **guia Geral** para exibir ou alterar informações básicas sobre o usuário de email.

- **Nome**

- **Iniciais**

- **Sobrenome**

- **Nome para** exibição : esse nome aparece no livro de endereços da sua organização, nas linhas Para: e De: no email e na lista de contatos no EAC. Esse nome não pode conter espaços vazios antes ou depois do nome para exibição.

- **ID do** usuário: essa é a conta do usuário no Microsoft 365. Você não pode modificar esse valor aqui.

#### <a name="contact-information"></a>Informações de contato

Use a **guia Informações de** contato para exibir ou alterar as informações de contato do usuário. As informações nesta página são exibidas no catálogo de endereços.

- **Street**
- **Cidade**
- **Estado/Província**
- **CEP/Código postal**
- **País/região**
- **Telefone de trabalho**
- **Telefone celular**
- **Fax**
- **Mais opções**

  - **Office**
  - **Telefone 1**
  - **Página da Web**
  - **Anotações**

#### <a name="organization"></a>Organização

Use a **guia Organização** para registrar informações detalhadas sobre a função do usuário na organização.

- **Título**
- **Departamento**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Usar o EAC para remover usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você deseja remover e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.

## <a name="use-powershell-to-manage-mail-users"></a>Usar o PowerShell para gerenciar usuários de email

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usar o EOP PowerShell autônomo para exibir usuários de email

Para retornar uma lista resumida de todos os usuários de email no EOP PowerShell autônomo, execute o seguinte comando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Para exibir informações detalhadas sobre um usuário de email específico, substitua pelo nome, alias ou nome da conta do usuário de email e execute \<MailUserIdentity\> os seguintes comandos:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-Recipient](/powershell/module/exchange/get-recipient) e [Get-User](/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Usar o EOP PowerShell autônomo para criar usuários de email

Para criar usuários de email no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Observações**:

- O _parâmetro Name_ é necessário, tem um comprimento máximo de 64 caracteres e deve ser exclusivo. Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.
- Se você não usar o parâmetro _Alias,_ o lado esquerdo do _parâmetro MicrosoftOnlineServicesID_ será usado para o alias.
- Se você não usar o parâmetro _ExternalEmailAddress,_ o _valor MicrosoftOnlineServicesID_ será usado para o endereço de email externo.

Este exemplo cria um usuário de email com as seguintes configurações:

- O nome é JeffreyZeng e o nome de exibição é Jeffrey Zeng.
- O primeiro nome é Diogo e o sobrenome é Martins.
- O alias é diogom.
- O endereço de email externo é diogom@tailspintoys.com.
- O nome da conta é jeffreyz@contoso.onmicrosoft.com.
- A senha é Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Usar o EOP PowerShell autônomo para modificar usuários de email

Para modificar os usuários de email existentes no EOP PowerShell autônomo, use a seguinte sintaxe:

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

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Usar o EOP PowerShell autônomo para remover usuários de email

Para remover usuários de email no EOP PowerShell autônomo, substitua pelo nome, alias ou nome da conta do usuário de email e execute \<MailUserIdentity\> o seguinte comando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

Este exemplo remove o usuário de email de Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu usuários de email com êxito no EOP autônomo, use qualquer um dos seguintes procedimentos:

- No EAC, acesse **Destinatários** \> **Contatos**. Verifique se o usuário de email está listado (ou não está listado). Selecione o usuário de email e exibir as informações no painel Detalhes ou clique em **Editar** ![ ícone editar para exibir as ](../../media/ITPro-EAC-AddIcon.png) configurações.

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

No EOP autônomo, a sincronização de diretórios está disponível para clientes com o Active Directory local. Você pode sincronizar essas contas com o Azure Active Directory (Azure AD), onde cópias das contas são armazenadas na nuvem. Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, você pode exibir esses usuários no painel **Destinatários** do Centro de administração do Exchange (EAC) ou no EOP PowerShell autônomo.

**Observações**:

- Se você usar a sincronização de diretórios para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no Centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local. Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.

- A sincronização de diretório é recomendada para uso com os seguintes recursos:

  - **Listas de remetentes** seguros do Outlook e listas de Remetentes Bloqueados : Quando sincronizadas com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço. Isso permite que os usuários gerenciem sua própria lista de Remetentes Seguros e Lista de Remetentes Bloqueados com entradas individuais de remetente e domínio. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

  - Bloqueio de Borda Com Base em Diretório **(DBEB)**: Para obter mais informações sobre DBEB, consulte Use Directory Based Edge Blocking to reject messages sent [to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Acesso do usuário final à quarentena**: Para acessar suas mensagens em quarentena, os destinatários devem ter uma ID de usuário e uma senha válidas no serviço. Para obter mais informações sobre a quarentena, [consulte Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).

  - Regras de fluxo de emails (também conhecidas como regras de **transporte)**: quando você usa a sincronização de diretórios, os usuários e grupos existentes do Active Directory são carregados automaticamente na nuvem e você pode criar regras de fluxo de emails que direcionam usuários específicos e/ou grupos sem precisar adicioná-los manualmente no serviço. Observe que os [grupos dinâmicos de distribuição](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.

Obter as permissões necessárias e preparar-se para a sincronização de diretórios, conforme descrito em O que é a identidade híbrida com o [Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizar diretórios com o Azure Active Directory Connect (AAD Connect)

1. Ativar a sincronização de diretório conforme descrito na sincronização [do Azure AD Connect: Compreender e personalizar a sincronização](/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Instalar e configurar um computador local para executar o AAD Connect conforme descrito em [Pré-requisitos para o Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Selecione o tipo de instalação a ser usado para o Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizados](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticação de passagem](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.

Depois de configurar sua sincronização, verifique se o AAD Connect está sincronizando corretamente. No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.