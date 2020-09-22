---
title: Gerenciar usuários de e-mail no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Saiba mais sobre como gerenciar usuários de email na proteção do Exchange Online (EOP), incluindo o uso da sincronização de diretórios, da Eat e do PowerShell para gerenciar usuários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56e6f8955b5993fb4b5064aa92cdde80a4c67ffe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201778"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Gerenciar usuários de e-mail no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os usuários de email são o tipo fundamental de conta de usuário. Um usuário de email tem credenciais de conta em sua organização autônoma do EOP e pode acessar recursos (permissões atribuídas). O endereço de email de um usuário de email é externo (por exemplo, em seu ambiente de email local).

> [!NOTE]
> Quando você cria um usuário de email, a conta de usuário correspondente está disponível no centro de administração do Microsoft 365. Ao criar uma conta de usuário no centro de administração do Microsoft 365, você não pode usar essa conta para criar um usuário de email.

O método recomendado para criar e gerenciar usuários de email no EOP autônomo é usar a sincronização de diretórios, conforme descrito na seção [usar a sincronização de diretórios para gerenciar usuários de email](#use-directory-synchronization-to-manage-mail-users) mais adiante neste tópico.

Para organizações EOP autônomas com um pequeno número de usuários, você pode adicionar e gerenciar usuários de email no centro de administração do Exchange (Eat) ou no EOP PowerShell autônomo, conforme descrito neste tópico.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange (Eat), confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Ao criar usuários de email no EOP PowerShell, você pode encontrar limitação. Além disso, os cmdlets do EOP PowerShell usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.

- Você precisa receber permissões para executar esses procedimentos. Especificamente, você precisa das funções de criação de destinatário de email (criar) e de destinatários de email (modificar), que são atribuídas aos grupos de função gerenciamento (administradores globais) e RecipientManagement por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda nos fóruns do Exchange. Visite o fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Usar o centro de administração do Exchange para gerenciar usuários de email

### <a name="use-the-eac-to-create-mail-users"></a>Usar o Eat para criar usuários de email

1. No Eat, vá para **Recipients** \> **contatos** de destinatários

2. Clique em **novo** ![ ícone novo ](../../media/ITPro-EAC-AddIcon.png) . Na página **novo usuário de email** que é aberta, defina as seguintes configurações. As configurações marcadas com um <sup>\*</sup> são obrigatórias.

   - **Nome**

   - **Iniciais**: a inicial do segundo nome da pessoa.

   - **Sobrenome**

   - <sup>\*</sup>**Nome para exibição**: por padrão, essa caixa mostra os valores das **caixas nome**, **iniciais**e **sobrenome** . Você pode aceitar esse valor ou alterá-lo. O valor deve ser exclusivo e ter um comprimento máximo de 64 caracteres.

   - <sup>\*</sup>**Alias**: Insira um alias exclusivo, usando até 64 caracteres, para o usuário

   - **Endereço de email externo**: Insira o endereço de email do usuário. O domínio deve ser externo à sua organização baseada na nuvem.

   - <sup>\*</sup>**ID de usuário**: Insira a conta que a pessoa usará para entrar no serviço. A ID do usuário consiste em um nome de usuário no lado esquerdo do símbolo de arroba (@) e um domínio no lado direito.

   - <sup>\*</sup>**Nova senha** e <sup>\*</sup> **Confirmar senha**: Insira e digite novamente a senha da conta. Verifique se a senha está em conformidade com os requisitos de tamanho, complexidade e histórico de senha da sua organização.

3. Quando tiver terminado, clique em **Salvar** para criar o usuário de email.

### <a name="use-the-eac-to-modify-mail-users"></a>Usar o Eat para modificar usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) .

3. Na página de propriedades do usuário de email que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.

   Quando concluir, clique em **Salvar**.

#### <a name="general"></a>Geral

Use a guia **geral** para exibir ou alterar as informações básicas sobre o usuário de email.

- **Nome**

- **Iniciais**

- **Sobrenome**

- **Nome para exibição**: esse nome é exibido no catálogo de endereços da sua organização, nas linhas para: e de: no email e na lista de contatos no Eat. Esse nome não pode conter espaços vazios antes ou depois do nome para exibição.

- **ID do usuário**: esta é a conta do usuário no Microsoft 365. Você não pode modificar este valor aqui.

#### <a name="contact-information"></a>Informações de contato

Use a guia **informações de contato** para exibir ou alterar as informações de contato do usuário. As informações nesta página são exibidas no catálogo de endereços.

- **123**
- **Cidade**
- **Estado/Província**
- **CEP/código postal**
- **País/região**
- **Telefone comercial**
- **Telefone celular**
- **Fax**
- **Mais opções**

  - **Office**
  - **Telefone residencial**
  - **Página da Web**
  - **Anotações**

#### <a name="organization"></a>Organização

Use a guia **organização** para registrar informações detalhadas sobre a função do usuário na organização.

- **Title**
- **Departamento**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Usar o Eat para remover usuários de email

1. No EAC, acesse **Destinatários** \> **Contatos**.

2. Selecione o usuário de email que você deseja remover e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Usar o PowerShell para gerenciar usuários de email

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Usar o EOP PowerShell autônomo para exibir usuários de email

Para retornar uma lista resumida de todos os usuários de email do EOP PowerShell autônomo, execute o seguinte comando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Para exibir informações detalhadas sobre um usuário de email específico, substitua \<MailUserIdentity\> o nome, o alias ou o nome da conta do usuário de email e execute os seguintes comandos:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Usar o EOP autônomo do PowerShell para criar usuários de email

Para criar usuários de email no EOP PowerShell autônomo, use a seguinte sintaxe:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Observações**:

- O parâmetro _Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo. Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.
- Se você não usar o parâmetro _alias_ , o lado esquerdo do parâmetro _MicrosoftOnlineServicesID_ será usado para o alias.
- Se você não usar o parâmetro _ExternalEmailAddress_ , o valor _MicrosoftOnlineServicesID_ será usado para o endereço de email externo.

Este exemplo cria um usuário de email com as seguintes configurações:

- O nome é JeffreyZeng e o nome de exibição é Jeffrey Martins.
- O primeiro nome é Diogo e o sobrenome é Martins.
- O alias é diogom.
- O endereço de email externo é diogom@tailspintoys.com.
- O nome da conta é jeffreyz@contoso.onmicrosoft.com.
- A senha é Pa$$word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Usar EOP PowerShell autônomo para modificar usuários de email

Para modificar usuários de email existentes no PowerShell autônomo do EOP, use a seguinte sintaxe:

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

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Usar o EOP PowerShell autônomo para remover usuários de email

Para remover usuários de email do EOP PowerShell autônomo, substitua \<MailUserIdentity\> o nome, o alias ou o nome da conta do usuário de email e execute o seguinte comando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

Este exemplo remove o usuário de email de Jeffrey Martins.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito os usuários de email no EOP autônomo, use qualquer um dos seguintes procedimentos:

- No EAC, acesse **Destinatários** \> **Contatos**. Verifique se o usuário de email está listado (ou não está listado). Selecione o usuário de email e visualize as informações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) para exibir as configurações.

- Em EOP autônomo do PowerShell, execute o seguinte comando para verificar se o usuário de email está listado (ou não está listado):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Substitua \<MailUserIdentity\> pelo nome, alias ou nome da conta do usuário de email e execute os seguintes comandos para verificar as configurações:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizar a sincronização de diretórios para gerenciar usuários de email

No EOP autônomo, a sincronização de diretórios está disponível para clientes com o Active Directory local. Você pode sincronizar essas contas no Azure Active Directory (Azure AD), onde as cópias das contas são armazenadas na nuvem. Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, você pode exibir esses usuários no painel **destinatários** do centro de administração do Exchange (Eat) ou no PowerShell do EOP autônomo.

**Observações**:

- Se você usar a sincronização de diretório para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local. Isso porque a sincronização de diretórios sincroniza apenas destinatários de seu Active Directory local com a nuvem.

- A sincronização de diretório é recomendada para uso com os seguintes recursos:

  - Listas **de remetentes seguros do Outlook e listas de remetentes bloqueados**: quando sincronizado com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço. Isso permite que os usuários gerenciem sua própria lista de remetentes confiáveis e a lista de remetentes bloqueados com entradas de domínio e remetentes individuais. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Bloqueio de borda baseado em diretório (DBEB)**: para obter mais informações sobre o DBEB, confira [usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Acesso de usuário final à quarentena**: para acessar suas mensagens em quarentena, os destinatários devem ter uma ID de usuário e senha válidas no serviço. Para obter mais informações sobre quarentena, consulte [Localizar e liberar mensagens em quarentena como um usuário](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).

  - **Regras de fluxo de emails (também conhecidas como regras de transporte)**: quando você usa a sincronização de diretório, os usuários e grupos existentes do Active Directory são carregados automaticamente para a nuvem e você pode criar regras de fluxo de email que se destinam a usuários e/ou grupos específicos sem precisar adicioná-los manualmente no serviço. Observe que os [grupos dinâmicos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.

Obtenha as permissões necessárias e prepare-se para a sincronização de diretório, conforme descrito em [o que é a identidade híbrida com o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Sincronizar diretórios com o Azure Active Directory Connect (AAD Connect)

1. Ative a sincronização de diretórios, conforme descrito na [sincronização do Azure ad Connect: compreender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Instale e configure um computador local para executar o AAD Connect conforme descrito em [pré-requisitos para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Selecione o tipo de instalação a ser usado para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Personalizados](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Autenticação de passagem](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.

Depois de configurar a sincronização, verifique se a conexão do AAD está sincronizando corretamente. No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.
