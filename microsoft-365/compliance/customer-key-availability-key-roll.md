---
title: Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como rolar as chaves raiz do cliente armazenadas no Azure Key Vault que são usadas com a Chave do Cliente. Os serviços incluem Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams arquivos.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345113"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade

> [!CAUTION]
> Somente role uma chave de criptografia que você usa com a Chave do Cliente quando seus requisitos de segurança ou conformidade determinam que você deve rolar a chave. Além disso, não exclua as chaves que estão ou foram associadas às políticas. Quando você rolar suas chaves, haverá conteúdo criptografado com as chaves anteriores. Por exemplo, embora as caixas de correio ativas sejam criptografadas com frequência, as caixas de correio inativas, desconectadas e desabilitadas ainda poderão ser criptografadas com as chaves anteriores. SharePoint Online executa backup de conteúdo para fins de restauração e recuperação, portanto, ainda pode haver conteúdo arquivado usando chaves mais antigas.

## <a name="about-rolling-the-availability-key"></a>Sobre a rolagem da chave de disponibilidade

A Microsoft não expõe o controle direto da chave de disponibilidade aos clientes. Por exemplo, você só pode rolar (girar) as chaves que possui no Azure Key Vault. Microsoft 365 as chaves de disponibilidade em um cronograma definido internamente. Não há nenhum contrato de nível de serviço (SLA) voltado para o cliente para esses rolados de chaves. Microsoft 365 gira a chave de disponibilidade usando Microsoft 365 código de serviço em um processo automatizado e não manual. Os administradores da Microsoft podem iniciar o processo de rolagem. A chave é rolada usando mecanismos automatizados sem acesso direto ao armazenamento de chaves. O acesso ao armazenamento secreto da chave de disponibilidade não é provisionado para administradores da Microsoft. A rolagem da chave de disponibilidade aproveita o mesmo mecanismo usado inicialmente para gerar a chave. Para obter mais informações sobre a chave de disponibilidade, consulte [Understand the availability key](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Exchange Online e Skype for Business de disponibilidade podem ser efetivamente roladas pelos clientes criando um novo DEP, pois uma chave de disponibilidade exclusiva é gerada para cada DEP que você criar. As chaves de disponibilidade para arquivos SharePoint Online, OneDrive for Business e Teams existem no nível da floresta e são compartilhadas entre DEPs e clientes, o que significa que a rolagem só ocorre em um cronograma definido internamente pela Microsoft. Para atenuar o risco de não rolar a chave de disponibilidade sempre que uma nova DEP for criada, SharePoint, OneDrive e Teams rolar a chave intermediária do locatário (TIK), a chave envolvida pelas chaves raiz do cliente e pela chave de disponibilidade, sempre que um novo DEP for criado.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicitar uma nova versão de cada chave raiz existente que você deseja rolar

Quando você rola uma chave, solicita uma nova versão de uma chave existente. Para solicitar uma nova versão de uma chave existente, use o mesmo cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), com a mesma sintaxe usada para criar a chave em primeiro lugar. Depois de terminar de rolar qualquer chave associada a uma POLÍTICA de Criptografia de Dados (DEP), execute outro cmdlet para garantir que a Chave do Cliente comece a usar a nova chave. Faça esta etapa em cada Azure Key Vault (AKV).

Por exemplo:

1. Entre em sua assinatura do Azure com Azure PowerShell. Para obter instruções, [consulte Entrar com Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Execute o Add-AzKeyVaultKey cmdlet como mostrado no exemplo a seguir:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   Neste exemplo, como uma chave chamada **Contoso-CK-EX-NA-VaultA1-Key001** existe no cofre **Contoso-CK-EX-NA-VaultA1,** o cmdlet cria uma nova versão da chave. Essa operação preserva as versões de chave anteriores no histórico de versão da chave. Você precisa da versão da chave anterior para descriptografar os dados que eles ainda criptografam. Depois de concluir a rolagem de qualquer chave associada a um DEP, execute um cmdlet extra para garantir que a Chave do Cliente comece a usar a nova chave. As seções a seguir descrevem os cmdlets com mais detalhes.
  
## <a name="update-the-keys-for-multi-workload-deps"></a>Atualizar as chaves para DEPs de várias cargas de trabalho

Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com várias cargas de trabalho, você deve atualizar o DEP para apontar para a nova chave. Esse processo não gira a chave de disponibilidade.

Para instruir a Chave do Cliente a usar a nova chave para criptografar várias cargas de trabalho, conclua estas etapas:

1. Em seu computador local, usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador ou administrador de conformidade em sua organização, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) em uma janela Windows PowerShell de conformidade.

2. Execute o cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

Onde *PolicyName* é o nome ou ID exclusiva da política. Por exemplo, Contoso_Global.

Exemplo:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>Atualizar as chaves para Exchange Online DEPs

Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com Exchange Online e Skype for Business, você deve atualizar o DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

Para instruir a Chave do Cliente a usar a nova chave para criptografar caixas de correio, execute o cmdlet Set-DataEncryptionPolicy da seguinte forma:

1. Execute o cmdlet Set-DataEncryptionPolicy Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. Para verificar o valor da propriedade DataEncryptionPolicyID para a caixa de correio, use as etapas em [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). O valor dessa propriedade muda quando o serviço aplica a chave atualizada.
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Atualizar as chaves para arquivos SharePoint Online, OneDrive for Business e Teams

SharePoint Online só permite rolar uma chave por vez. Se você quiser rolar as duas chaves em um cofre de chaves, aguarde a conclusão da primeira operação. A Microsoft recomenda que você escalone suas operações para evitar esse problema. Quando você rola uma das teclas do Azure Key Vault associadas a um DEP usado com o SharePoint Online e o OneDrive for Business, você deve atualizar o DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

1. Execute o Update-SPODataEncryptionPolicy cmdlet da seguinte forma:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Enquanto esse cmdlet inicia a operação de rolagem de chaves para SharePoint Online e OneDrive for Business, a ação não é concluída imediatamente.

2. Para ver o progresso da operação de rolagem de teclas, execute o cmdlet Get-SPODataEncryptionPolicy da seguinte forma:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com Chave de Cliente para Office 365](customer-key-overview.md)

- [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)

- [Gerenciar Chave de Cliente do Office 365](customer-key-manage.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)