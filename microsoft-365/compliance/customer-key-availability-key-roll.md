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
description: Saiba como rolar as chaves raiz do cliente armazenadas no Azure Key Vault que são usadas com a Chave do Cliente. Os serviços incluem o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e os arquivos do Teams.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633638"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade

> [!CAUTION]
> Roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key. Além disso, não exclua as chaves que estão ou foram associadas às políticas. Quando você rolar suas chaves, haverá conteúdo criptografado com as chaves anteriores. Por exemplo, embora as caixas de correio ativas sejam criptografadas com frequência, as caixas de correio inativas, desconectadas e desabilitadas ainda podem ser criptografadas com as chaves anteriores. O SharePoint Online executa o backup do conteúdo para fins de restauração e recuperação, portanto, ainda pode haver conteúdo arquivado usando chaves mais antigas.

## <a name="about-rolling-the-availability-key"></a>Sobre a rolagem da chave de disponibilidade

A Microsoft não expõe o controle direto da chave de disponibilidade para os clientes. Por exemplo, você só pode rolar (girar) as teclas que possui no Azure Key Vault. O Microsoft 365 rola as chaves de disponibilidade em um cronograma definido internamente. Não há contrato de nível de serviço (SLA) voltado para o cliente para essas chaves. O Microsoft 365 gira a chave de disponibilidade usando o código de serviço do Microsoft 365 em um processo automatizado e não manual. Os administradores da Microsoft podem iniciar o processo de rolagem. A chave é rolada usando mecanismos automatizados sem acesso direto ao armazenamento de chaves. O acesso ao armazenamento secreto da chave de disponibilidade não é provisionado para os administradores da Microsoft. A rolagem da chave de disponibilidade aproveita o mesmo mecanismo usado para gerar inicialmente a chave. Para obter mais informações sobre a chave de disponibilidade, [consulte Entender a chave de disponibilidade.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> As chaves de disponibilidade do Exchange Online e do Skype for Business podem ser efetivamente roladas pelos clientes que criam uma nova DEP, já que uma chave de disponibilidade exclusiva é gerada para cada DEP criada. As chaves de disponibilidade para arquivos do SharePoint Online, OneDrive for Business e Teams existem no nível da floresta e são compartilhadas entre DEPs e clientes, o que significa que a rolagem só ocorre em um cronograma definido internamente pela Microsoft. Para reduzir o risco de não rolar a chave de disponibilidade sempre que uma nova DEP é criada, o SharePoint, o OneDrive e o Teams rolam a chave intermediária do locatário (TIK), a chave envolvida pelas chaves raiz do cliente e a chave de disponibilidade, cada vez que uma nova DEP é criada.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicitar uma nova versão de cada chave raiz existente que você deseja rolar

Ao rolar uma chave, você solicita uma nova versão de uma chave existente. Para solicitar uma nova versão de uma chave existente, use o mesmo cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), com a mesma sintaxe usada para criar a chave. Depois de terminar de rolar qualquer chave associada a uma DEP (Política de Criptografia de Dados), execute outro cmdlet para garantir que a Chave do Cliente comece a usar a nova chave. Faça esta etapa em cada Azure Key Vault (AKV).

Por exemplo:

1. Entre em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Execute o Add-AzKeyVaultKey cmdlet como mostrado no exemplo a seguir:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   Neste exemplo, como uma chave chamada **Contoso-O365EX-NA-VaultA1-Key001** existe no cofre **Contoso-O365EX-NA-VaultA1,** o cmdlet cria uma nova versão da chave. Essa operação preserva as versões de chave anteriores no histórico de versões da chave. Você precisa da versão da chave anterior para descriptografar os dados que ela ainda criptografa. Depois de concluir a rolagem de qualquer chave associada a um DEP, execute um cmdlet extra para garantir que a Chave do Cliente comece a usar a nova chave. As seções a seguir descrevem os cmdlets mais detalhadamente.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Atualizar a chave do cliente para o Exchange Online e o Skype for Business

Ao rolar qualquer uma das chaves do Azure Key Vault associadas a um DEP usado com o Exchange Online e o Skype for Business, você deve atualizar a DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

Para instruir a Chave do Cliente a usar a nova chave para criptografar caixas de correio, execute o Set-DataEncryptionPolicy cmdlet da seguinte forma:

1. Execute o Set-DataEncryptionPolicy cmdlet no Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Dentro de 72 horas, as caixas de correio ativas associadas a essa DEP serão criptografadas com a nova chave.

2. Para verificar o valor da propriedade DataEncryptionPolicyID da caixa de correio, use as etapas em Determinar a DEP atribuída [a uma caixa de correio.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox) O valor dessa propriedade muda depois que o serviço aplica a chave atualizada.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Atualizar a chave do cliente para arquivos do SharePoint Online, OneDrive for Business e Teams

O SharePoint Online só permite que você role uma tecla por vez. Se você quiser rolar as duas teclas em um cofre de chaves, aguarde a conclusão da primeira operação. A Microsoft recomenda que você escalone suas operações para evitar esse problema. Ao rolar qualquer uma das chaves do Azure Key Vault associadas a um DEP usado com o SharePoint Online e o OneDrive for Business, você deve atualizar a DEP para apontar para a nova chave. Isso não gira a chave de disponibilidade.

1. Execute o Update-SPODataEncryptionPolicy cmdlet da seguinte forma:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Enquanto esse cmdlet inicia a operação de rolagem de chaves para o SharePoint Online e o OneDrive for Business, a ação não é concluída imediatamente.

2. Para ver o progresso da operação de rolagem de teclas, execute o cmdlet Get-SPODataEncryptionPolicy seguinte:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com Chave de Cliente do Office 365](customer-key-overview.md)

- [Configurar a Chave de Cliente do Office 365](customer-key-set-up.md)

- [Gerenciar Chave de Cliente do Office 365](customer-key-manage.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)
