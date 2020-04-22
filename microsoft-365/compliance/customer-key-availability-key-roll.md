---
title: Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como rolar as chaves raiz do cliente armazenadas no Azure Key Vault que são usadas com a chave do cliente. Os serviços incluem o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e os arquivos do teams.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633638"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade

> [!CAUTION]
> Apenas Reverta uma chave de criptografia usada com a chave do cliente quando seus requisitos de segurança ou conformidade determinam que você deve rolar a chave. Além disso, não exclua chaves que estejam associadas a políticas. Ao rolar suas chaves, haverá conteúdo criptografado com as teclas anteriores. Por exemplo, enquanto as caixas de correio ativas forem criptografadas freqüentemente, inativas, desconectadas e desativadas, as caixas de correio ainda poderão ser criptografadas com as teclas anteriores. O SharePoint Online realiza o backup de conteúdo para fins de restauração e recuperação, para que ainda possa haver conteúdo arquivado usando chaves antigas.

## <a name="about-rolling-the-availability-key"></a>Sobre a interrupção da chave de disponibilidade

A Microsoft não expõe o controle direto da chave de disponibilidade para os clientes. Por exemplo, você só pode rolar (girar) as chaves que você possui no Azure Key Vault. A Microsoft 365 acumula as chaves de disponibilidade em um cronograma definido internamente. Não há um contrato de nível de serviço (SLA) voltado para o cliente para esses rolos de chave. O Microsoft 365 gira a chave de disponibilidade usando o código de serviço do Microsoft 365 em um processo automatizado e não manual. Os administradores da Microsoft podem iniciar o processo de rolo. A chave é feita usando mecanismos automatizados sem acesso direto ao repositório de chaves. O acesso ao repositório de segredo da chave de disponibilidade não é provisionado para os administradores da Microsoft. A interrupção da chave de disponibilidade aproveita o mesmo mecanismo usado para gerar inicialmente a chave. Para obter mais informações sobre a chave de disponibilidade, consulte [compreenda a chave de disponibilidade](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> As chaves de disponibilidade do Exchange Online e do Skype for Business podem ser efetivamente transferidas por clientes que criam uma nova DEP, uma vez que uma chave de disponibilidade exclusiva é gerada para cada DEP que você cria. As chaves de disponibilidade para os arquivos do SharePoint Online, do OneDrive for Business e do teams existem no nível da floresta e são compartilhadas entre o DEPs e os clientes, o que significa que a interrupção ocorre apenas em um cronograma definido internamente pela Microsoft. Para reduzir o risco de não reverter a chave de disponibilidade sempre que uma nova DEP for criada, o SharePoint, o OneDrive e o Microsoft Teams rolarão a chave intermediária de locatário (TIK), a chave delimitada pelas chaves raiz do cliente e a chave de disponibilidade, sempre que uma nova DEP for criada.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicitar uma nova versão de cada chave raiz existente que você deseja rolar

Ao lançar uma chave, você solicita uma nova versão de uma chave existente. Para solicitar uma nova versão de uma chave existente, use o mesmo cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), com a mesma sintaxe que você usou para criar a chave em primeiro lugar. Após concluir a transferência de qualquer chave associada a uma DEP (política de criptografia de dados), execute outro cmdlet para garantir que a chave do cliente comece a usar a nova chave. Execute esta etapa em cada cofre de chave do Azure (AKV).

Por exemplo:

1. Entre em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Execute o cmdlet Add-AzKeyVaultKey, conforme mostrado no exemplo a seguir:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   Neste exemplo, uma vez que uma chave chamada **contoso-O365EX-VaultA1-Key001** existe no cofre **contoso-O365EX-na-VaultA1** , o cmdlet cria uma nova versão da chave. Essa operação preserva as versões de chave anteriores no histórico de versões da chave. Você precisa da versão da chave anterior para descriptografar os dados que ainda são criptografados. Após concluir a interrupção de qualquer chave associada a uma DEP, execute um cmdlet extra para garantir que a chave do cliente comece a usar a nova chave. As seções a seguir descrevem os cmdlets em mais detalhes.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Atualizar a chave do cliente para o Exchange Online e o Skype for Business

Ao lançar uma das chaves do Azure Key Vault associadas a uma DEP usada com o Exchange Online e o Skype for Business, você deve atualizar a DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

Para instruir a chave do cliente a usar a nova chave para criptografar caixas de correio, execute o cmdlet Set-DataEncryptionPolicy da seguinte maneira:

1. Execute o cmdlet Set-DataEncryptionPolicy no Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Em 72 horas, as caixas de correio ativas associadas a essa DEP são criptografadas com a nova chave.

2. Para verificar o valor da propriedade DataEncryptionPolicyID da caixa de correio, use as etapas em [determinar a DEP atribuída a uma caixa de correio](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). O valor dessa propriedade é alterado depois que o serviço aplica a chave atualizada.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Atualizar a chave do cliente para os arquivos do SharePoint Online, do OneDrive for Business e do teams

O SharePoint Online permite que você Reverta uma chave por vez. Se você quiser rolar as duas chaves em um cofre de chaves, aguarde até que a primeira operação seja concluída. A Microsoft recomenda que você Escalona suas operações para evitar esse problema. Ao lançar uma das chaves do Azure Key Vault associadas a uma DEP usada com o SharePoint Online e o OneDrive for Business, você deve atualizar a DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

1. Execute o cmdlet Update-SPODataEncryptionPolicy da seguinte maneira:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Embora este cmdlet inicie a operação de registro principal para o SharePoint Online e o OneDrive for Business, a ação não é concluída imediatamente.

2. Para ver o andamento da operação do registro principal, execute o cmdlet Get-SPODataEncryptionPolicy da seguinte maneira:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com a chave do cliente para o Office 365](customer-key-overview.md)

- [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)

- [Gerenciar Chave de Cliente do Office 365](customer-key-manage.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)
