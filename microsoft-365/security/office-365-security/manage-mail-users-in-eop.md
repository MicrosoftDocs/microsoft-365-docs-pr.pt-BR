---
title: Gerenciar usuários de email no EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: A definição de usuários de email é uma parte importante do gerenciamento do serviço Exchange Online Protection (EOP).
ms.openlocfilehash: 53d47452979c42273fd485fa89642eea881bb21a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598978"
---
# <a name="manage-mail-users-in-eop"></a>Gerenciar usuários de email no EOP

A definição de usuários de email é uma parte importante do gerenciamento do serviço Exchange Online Protection (EOP). Existem várias maneiras possíveis de gerenciar usuários no EOP:

- **Utilizar a sincronização de diretórios para gerenciar usuários de email**: se sua empresa possui contas de usuário existentes em um ambiente do Active Directory local, é possível sincronizar essas contas com o Azure Active Directory (AD), onde uma cópia dessas contas fica armazenada na nuvem. Ao sincronizar suas contas de usuário existentes com o Azure Active Directory, será possível exibir esses usuários no painel **Destinatários** do Centro de administração do Exchange (EAC). Recomendamos usar a sincronização de diretório.

- **Usar o EAC para gerenciar usuários de email**: adicione e gerencie usuários de email diretamente no EAC. Esse é o modo mais fácil de adicionar usuários de email e é útil para adicionar um usuário por vez.

- **Use o PowerShell para gerenciar usuários de email**: Adicionar e gerenciar usuários de email no PowerShell do Exchange Online Protection. Este método é útil para adicionar vários registros e criar scripts.

> [!NOTE]
> Você pode adicionar usuários no centro de administração do Microsoft 365, no entanto, esses usuários não podem ser usados como destinatários de email.

## <a name="before-you-begin"></a>Antes de começar

- Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Usuários, contatos e grupos de funções" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).

- Lembre-se de que ao criar usuários de email usando os cmdlets do PowerShell do Exchange Online Protection, você pode encontrar limitação.

- Os comandos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.

- Para saber como usar o Windows PowerShell para se conectar à Proteção do Exchange Online, confira [Conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizar a sincronização de diretórios para gerenciar usuários de email

Esta seção oferece informações sobre o gerenciamento de usuários de email usando a sincronização de diretório.

**Observações**:

- Se você usar a sincronização de diretório para gerenciar seus destinatários, ainda poderá adicionar e gerenciar usuários no centro de administração do Microsoft 365, mas eles não serão sincronizados com o Active Directory local. Isso ocorre porque a sincronização de diretórios só sincroniza destinatários **do** seu Active Directory local **para** a nuvem.

- A sincronização de diretórios é recomendada para uso com os seguintes recursos:

  - **Remetente seguro do Outlook e listas de remetentes bloqueados**: quando sincronizado com o serviço, essas listas terão precedência sobre a filtragem de spam no serviço. Isso permite que os usuários gerenciem suas próprias listas de remetentes confiáveis e bloqueados por usuário ou por domínio.

  - **Bloqueio de borda baseado em diretório (DBEB)**: para obter mais informações sobre o DBEB, confira [usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Quarentena de spam do usuário final**: para acessar a quarentena de spam do usuário final, os usuários finais devem ter uma ID de usuário e uma senha válida do Office 365. Os clientes do EOP que estão protegendo caixas de correio locais devem ser usuários de email válidos.

  - **Regras de fluxo de emails**: quando você usa a sincronização de diretório, os usuários e grupos existentes do Active Directory são carregados automaticamente para a nuvem e você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) que se destinam a usuários e/ou grupos específicos sem ter que adicioná-los manualmente por meio do PowerShell do Exchange Online Protection. Observe que os [grupos dinâmicos de distribuição](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) não podem ser sincronizados através da sincronização de diretório.

Obtenha as permissões necessárias e prepare-se para a sincronização de diretório, conforme descrito em [o que é a identidade híbrida com o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>Para sincronizar os diretórios de usuário com o Azure Active Directory Connect (AAD Connect)

Para sincronizar os usuários com o Azure Active Directory (AAD), primeiro você precisa **ativar a sincronização de diretórios**, conforme descrito em [sincronização do Azure ad Connect: entender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

A seguir, a instalação e a configuração de um computador local para executar o AAD Connect (se você ainda não tiver uma coisa que vale a pena verificar antes do tempo). A [configuração do AAD Connect, o tópico Express Way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) mostra como configurar e sincronizar suas contas no local para o Azure AD com o AAD Connect.

Mas antes de fazer isso, certifique [-se de que você atende aos pré-requisitos](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)e [escolha o tipo de instalação](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation). O link anterior é para um pequeno artigo para instalações expressas. Você também pode encontrar artigos sobre [instalações personalizadas](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)ou [autenticação de passagem](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) , se for necessário.

> [!IMPORTANT]
> Após a conclusão do Assistente de Configuração da Ferramenta de Sincronização do Microsoft Azure Active Directory, a conta **MSOL_AD_SYNC** será criada em sua floresta do Active Directory. Esta conta é usada para ler e sincronizar suas informações do Active Directory local. Para que a sincronização de diretórios funcione corretamente, verifique se a porta TCP 443 em seu servidor de sincronização de diretórios local está aberta.

Após configurar sua sincronização, verifique se o EOP está sincronizando corretamente. No EAC, vá para **Destinatários** \> **Contatos** e veja se a lista de usuários foi corretamente sincronizada com seu ambiente local.

## <a name="use-the-eac-to-manage-mail-users"></a>Usar o EAC para gerenciar usuários de email

Esta seção oferece informações sobre a adição e o gerenciamento de usuários de email diretamente no EAC.

### <a name="use-the-eac-to-add-a-mail-user"></a>Usar o Eat para adicionar um usuário de email

1. Crie um usuário de email em **Destinatários** \> **Contatos** no EAC e clique em **Novo +**.

2. Na página **Novo usuário de email**, insira as informações do usuário, incluindo o seguinte:

   ****

   |**Propriedade do usuário de email**|**Descrição**|
   |:-----|:-----|
   |**Nome**, **Iniciais** e **Sobrenome**|Digite o nome completo do usuário nas caixas apropriadas.|
   |**Nome para exibição**|Digite um nome, usando até 64 caracteres. Por padrão, essa caixa mostra os nomes nas caixas **Nome**, **Iniciais** e **Sobrenome**, se houver. É necessário fornecer o nome para exibição.  |
   |**Alias**|Digite um alias exclusivo, usando até 64 caracteres para o usuário. O alias é obrigatório.|
   |**Endereço de email externo**|Digite o endereço de email externo do usuário.|
   |**ID de usuário**|Digite o nome que o usuário de email usará para entrar no serviço. O nome de entrada do usuário consiste em um nome de usuário à esquerda do símbolo (@) e um sufixo à direita. Geralmente, o sufixo é o nome de domínio no qual a conta de usuário reside.|
   |**Nova senha**|Digite a senha que o usuário de email usará para entrar no serviço. Verifique se a senha fornecida é compatível com os requisitos de comprimento, complexidade e histórico do domínio no qual você está criando a conta do usuário.|
   |**Confirmação da senha**|Digite novamente a senha para confirmá-la.|

3. Clique em **Salvar** para criar o novo usuário de email. O novo usuário deve aparecer na lista de usuários.

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>Usar o Eat para editar ou remover um usuário de email

- No EAC, acesse **Destinatários** \> **Contatos**. Na lista de usuários, clique no usuário que você deseja exibir ou alterar e selecione **Editar** ![ícone](../media/ITPro-EAC-EditIcon.gif) de edição para atualizar as configurações do usuário, conforme necessário. Você pode alterar o nome, o alias ou as informações de contato do usuário, e pode registrar informações detalhadas sobre a função do usuário na organização. Você também pode selecionar um usuário e, em **** ![seguida, escolher](../media/ITPro-EAC-RemoveIcon.gif) Remover ícone para excluí-lo.

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>Usar o Exchange Online Protection PowerShell para gerenciar usuários de email

Esta seção fornece informações sobre como adicionar e gerenciar usuários de email usando o Windows PowerShell remoto.

### <a name="use-eop-powershell-to-add-a-mail-user"></a>Usar o EOP PowerShell para adicionar um usuário de email

O exemplo usa o cmdlet [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) para criar uma conta de usuário habilitado para email em nome de Diogo Martins com os seguintes detalhes:

- O primeiro nome é Diogo e o sobrenome é Martins.

- O nome é Diogo e o nome de exibição é Diogo Martins.

- O alias é diogom.

- O endereço de email externo é diogom@tailspintoys.com.

- O nome de usuário do Office 365 é diogom@contoso.onmicrosoft.com.

- A senha é Pa$$word1.

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

Para verificar se isso funcionou, execute o seguinte comando para exibir informações sobre o novo usuário de email Jeffrey Martins:

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>Usar o EOP PowerShell para editar as propriedades de um usuário de email

Use os cmdlets [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) para visualizar ou alterar propriedades para usuários de email.

Este exemplo define o endereço de email externo de Brenda Fernandes.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

Este exemplo define a propriedade Company de todos os usuários de email como Contoso.

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Para verificar se isso funcionou, use o cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para verificar as alterações. (Observe que você pode visualizar várias propriedades para vários contatos de email.)

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

No exemplo anterior em que a propriedade Company foi definida como Contoso para todos os usuários de email, execute o comando a seguir para verificar as alterações:

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Esse cmdlet usa um método de processamento em lotes que resulta em um atraso na propagação de alguns minutos até que os resultados do cmdlet estejam visíveis.

### <a name="use-eop-powershell-to-remove-a-mail-user"></a>Usar o EOP PowerShell para remover um usuário de email

Este exemplo usa o cmdlet [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) para excluir o usuário Diogo Martins:

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
Para verificar se isso funcionou, execute o cmdlet [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) para verificar se o usuário de email não existe mais.

```PowerShell
Get-Recipient Jeffrey | Format-List
```
