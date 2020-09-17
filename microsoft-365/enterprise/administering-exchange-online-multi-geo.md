---
title: Administrar caixas de correio do Exchange Online em um ambiente multigeográfico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Saiba como administrar as configurações multigeográficas do Exchange Online no seu ambiente do Microsoft 365 com o PowerShell.
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950671"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Administrar caixas de correio do Exchange Online em um ambiente multigeográfico

O PowerShell do Exchange Online é necessário para exibir e configurar várias propriedades geográficas no seu ambiente do Microsoft 365. Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

É necessário o [Módulo Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 ou superior em v1. x para ver a propriedade **PreferredDataLocation** nos objetos do usuário. Objetos do usuário sincronizados por meio do AAD Connect no AAD não podem ter seu valore **PreferredDataLocation** modificado diretamente por meio do AAD PowerShell. Objetos Apenas Nuvem de usuário podem ser modificados pelo AAD PowerShell. Para se conectar ao PowerShell do Azure AD, consulte [Conectar-se ao PowerShell](connect-to-microsoft-365-powershell.md).

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Conecte-se diretamente em uma localização geográfica usando o Exchange Online PowerShell

Normalmente, o PowerShell do Exchange Online se conectará à localização geográfica central. Mas você também pode se conectar diretamente a localizações geográficas por satélite. Devido a melhorias no desempenho, recomendamos que você se conecte diretamente à localização geográfica por satélite quando você gerenciar apenas usuários nessa localização.

Os requisitos para instalar e usar o módulo EXO V2 são descritos em [Instalar e manter o módulo EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Para conectar o PowerShell do Exchange Online a uma localização geográfica específica, o parâmetro *ConnectionURI* é diferente das instruções de conexão normais. O restante dos comandos e valores são iguais.

Especificamente, você precisa adicionar o `?email=<emailaddress>` valor para o final do valor _ConnectionURI_ . `<emailaddress>` é o endereço de email de **qualquer** caixa de correio na localização geográfica de destino. Suas permissões para essa caixa de correio ou a relação com suas credenciais não são um fator; o endereço de email simplesmente diz ao Exchange Online PowerShell onde se conectar.

Os clientes Microsoft 365 ou Microsoft 365 GCC normalmente não precisam usar o parâmetro _ConnectionURI_ para se conectar ao PowerShell do Exchange Online. Mas, para se conectar a um local geográfico específico, você precisa usar o parâmetro _ConnectionURI_ para que possa usar `?email=<emailaddress>` o valor.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a>Conectar-se a um local geográfico no PowerShell do Exchange Online usando a protocolo de autenticação multifator (MFA)

1. Em uma janela do Windows PowerShell, carregue o módulo EXO V2 executando o seguinte comando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. No exemplo a seguir, admin@contoso.onmicrosoft.com é a conta de administrador e a localização geográfica de destino é onde o olga@contoso.onmicrosoft.com de caixa de correio reside.

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a>Conectar-se a um local geográfico no PowerShell do Exchange Online sem usar a MFA

1. Em uma janela do Windows PowerShell, carregue o módulo EXO V2 executando o seguinte comando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. Execute o seguinte comando:

   ```powershell
   $UserCredential = Get-Credential
   ```

   Na caixa de diálogo **Solicitação de Credencial do Windows PowerShell** que aparece, digite sua conta corporativa ou de estudante e a senha, e clique em **OK**.

3. No exemplo a seguir, a localização geográfica de destino é onde reside a caixa de correio olga@contoso.onmicrosoft.com.

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Exibir as localizações geográficas disponíveis que estão configurados em sua organização do Exchange Online

Para visualizar a lista dos locais geográficos configurados no Microsoft 365 Multi-Geo, execute o seguinte comando no Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Ver a localização geográfica central da sua organização do Exchange Online

Para exibir a localização geográfica central do seu locatário, execute o seguinte comando no PowerShell do Exchange Online:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Descobrir a localização geográfica de uma caixa de correio

O cmdlet **Get-Mailbox** no Exchange Online PowerShell exibe as seguintes propriedades relacionadas às áreas multigeográficas nas caixas de correio:

- **Banco de dados**: As 3 primeiras letras do nome do banco de dados correspondem ao código geográfico, o que determina onde a caixa de correio está localizada no momento. Para Caixas de Correio com Arquivo Online a propriedade **ArchiveDatabase** deve ser usada.

- **MailboxRegion**: Especifica o código da localização geográfica que foi definida pelo administrador (sincronizado do **PreferredDataLocation** no Azure AD).

- **MailboxRegionLastUpdateTime**: Indica quando o MailboxRegion foi atualizado (automaticamente ou manualmente).

Para ver as propriedades de uma caixa de correio, use a seguinte sintaxe:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Por exemplo, para ver as informações da localização geográfica da caixa de correio de chris@contoso.onmicrosoft.com, execute o seguinte comando:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

A saída do comando será parecida com o seguinte:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Se o código de localização geográfica no nome do banco de dados não corresponder ao valor de **MailboxRegion** , a caixa de correio será automaticamente colocada em uma fila de realocação e movida para o local geográfico especificado pelo valor **MailboxRegion** (o Exchange Online procura por uma incompatibilidade entre esses valores de propriedade).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Mover uma caixa de correio apenas nuvem existente para uma localização geográfica específica

Um usuário somente na nuvem é um usuário não sincronizado com o locatário por meio do AAD Connect. Esse usuário foi criado diretamente no Azure AD. Use os cmdlets **Get-MsolUser** e **Set-MsolUser** no Módulo Azure AD para Windows PowerShell para exibir ou especificar a localização geográfica onde a caixa de correio de um usuário somente na nuvem será armazenada.

Para exibir o valor **PreferredDataLocation** para um usuário, use esta sintaxe no Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Por exemplo, para ver o valor **PreferredDataLocation** para o usuário michelle@contoso.onmicrosoft.com, execute o seguinte comando:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Para modificar o valor **PreferredDataLocation** para um objeto de usuário apenas nuvem, use a seguinte sintaxe no Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Por exemplo, para configurar o valor **PreferredDataLocation** para a área geográfica União Europeia (UE) para o usuário michelle@contoso.onmicrosoft.com, execute o seguinte comando:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Como mencionado anteriormente, você não pode usar este procedimento para objetos de usuário sincronizados do Active Directory local. Você precisa alterar o valor **PreferredDataLocation** no Active Directory e sincronizá-lo usando o AAD Connect. Para obter mais informações, consulte [Sincronização do Azure Active Directory Connect: Configurar o local preferencial dos dados dos recursos do Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - O tempo que leva para relocar uma caixa de correio para uma nova localização geográfica depende de vários fatores:
>
>   - O tamanho e tipo de caixa de correio.
>   - O número de caixas de correio sendo movidas.
>   - Disponibilidade de recursos de movimentação.

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a>Mover caixas de correio desabilitadas que estão em Retenção de Litígio

Caixas de correio desabilitadas em Retenção de Litígio são preservadas para fins de descoberta eletrônica não podem ser movidas alterando seu valor **PreferredDataLocation** no estado desabilitado. Para mover uma caixa de correio desabilitada em retenção de litígio:

1. Atribua temporariamente uma licença à caixa de correio.

2. Altere o **PreferredDataLocation**.

3. Remova a licença da caixa de correio depois de ser movida para a localização geográfica selecionada para colocá-la novamente no estado desabilitado.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Criar novas caixas de correio em nuvem em uma localização geográfica específica

Para criar uma nova caixa de correio em uma localização geográfica específica, é preciso seguir uma destas etapas:

- Configurar o valor **PreferredDataLocation** conforme descrito na seção anterior *antes* da caixa de correio ser criada no Exchange Online. Por exemplo, configure valor **PreferredDataLocation** em um usuário antes de atribuir uma licença.

- Atribuir uma licença e definir o valor **PreferredDataLocation** ao mesmo tempo.

Para criar um novo usuário licenciado somente na nuvem (não sincronizado pelo AAD Connect) em uma localização geográfica específica, use a seguinte sintaxe no PowerShell do Azure AD:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

Este exemplo cria uma nova conta de usuário para Elizabeth Brunner com os seguintes valores:

- Nome de usuário principal: ebrunner@contoso.onmicrosoft.com
- Nome: Elizabeth
- Sobrenome: Brunner
- Nome para exibição: Elizabeth Brunner
- Senha: gerada aleatoriamente e mostrada nos resultados do comando (porque não estamos usando o parâmetro *Senha*)
- Licença: `contoso:ENTERPRISEPREMIUM` (E5)
- Local: Austrália (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Para obter mais informações de como criar novas contas de usuário e encontrar os valores LicenseAssignment no Azure AD PowerShell, consulte [Criar contas de usuário com o PowerShell](create-user-accounts-with-microsoft-365-powershell.md) e [Exibir licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Se você estiver usando o PowerShell do Exchange Online para habilitar uma caixa de correio e precisar que a caixa de correio seja criada diretamente na localização geográfica especificada em **PreferredDataLocation**, será necessário usar um cmdlet do Exchange Online como **Enable-Mailbox** ou **New-Mailbox** diretamente no serviço de nuvem. Se você usar o cmdlet **Enable-RemoteMailbox** no Exchange PowerShell local, a caixa de correio será criada na localização geográfica central.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Integração de caixas de correio locais existentes em uma localização geográfica específica

Você pode usar as ferramentas de integração padrão e os processos para migrar uma caixa de correio de uma organização do Exchange local para o Exchange Online, incluindo o [Painel de migração no EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)e o cmdlet [New-MigrationBatch ](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) no Exchange Online PowerShell.

A primeira etapa consiste em verificar um objeto de usuário existente para cada caixa de correio a ser integrada e verificar se o valor **PreferredDataLocation** correto está configurado no Azure AD. As ferramentas de integração respeitarão o valor **PreferredDataLocation** e migrarão as caixas de correio diretamente para a localização geográfica especificada.

Ou você pode usar as etapas a seguir para integrar as caixas de correio diretamente em uma localização geográfica específica usando o cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet no Exchange Online PowerShell.

1. Verifique se o objeto do usuário existe para cada caixa de correio integrada e se o **PreferredDataLocation** está definido com o valor desejado no Azure AD. O valor do **PreferredDataLocation** será sincronizado com o atributo **MailboxRegion** do objeto do usuário de email correspondentes no Exchange Online.

2. Conecte-se diretamente à localização geográfica por satélite específica usando as instruções de conexão descritas anteriormente neste tópico.

3. No Exchange Online PowerShell armazene as credenciais de administrador local usadas para realizar a migração da caixa de correio em uma variável ao executar o seguinte comando:

   ```powershell
   $RC = Get-Credential
   ```

4. No Exchange Online PowerShell, crie um novo **New-MoveRequest** semelhante ao exemplo a seguir:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Repita a etapa 4 para cada caixa de correio que você precisa migrar do Exchange local para a localização geográfica por satélite à qual você está conectado no momento.

6. Se você precisar migrar caixas de correio adicionais para diferentes localizações geográficas por satélite, repita as etapas de 2 a 4 para cada localização específica.

## <a name="multi-geo-reporting"></a>Relatórios multigeográficos

**Relatórios de uso multigeográfico** no centro de administração do Microsoft 365 centro exiba a contagem de usuários por localização geográfica. O relatório exibe a distribuição do usuário no mês atual e fornece dados históricos para os últimos seis meses.

## <a name="see-also"></a>Confira também

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
