---
title: Chave do cliente para Microsoft 365 no nível do locatário (visualização pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Saiba como configurar a chave do cliente para todos os dados no seu locatário do Microsoft 365.
ms.openlocfilehash: f14bbc0cb6dd29883efa4c8d294d8d65cae98641
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751258"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Visão geral da chave do cliente para o Microsoft 365 no nível do locatário (visualização pública)

Usando chaves fornecidas, você pode criar uma DEP (política de criptografia de dados) e atribuí-la ao locatário. A DEP criptografa dados entre o locatário para estas cargas de trabalho:

- Mensagens de chat de equipes (1:1 chats, bate-papos de grupo, bate-papos de reunião e conversas de canal)
- Mensagens de mídia do Teams (imagens, trechos de código, vídeos, imagens wiki)
- Reuniões de chamada e de reunião de equipes armazenadas no armazenamento do Microsoft Teams
- Notificações de chat de equipes
- Sugestões de chat de equipes pela Cortana
- Mensagens de status do teams
- Informações de usuário e sinal para o Exchange Online

Para o Microsoft Teams, a chave do cliente no nível do locatário criptografa novos dados desde o momento em que a DEP é atribuída ao locatário. A visualização pública não dá suporte à criptografia de dados passados. Para o Exchange Online, a chave do cliente criptografa todos os dados existentes e novos.

Você pode criar vários DEPs por locatário, mas só pode atribuir uma DEP a qualquer momento. Quando você atribui a DEP, a criptografia começa automaticamente, mas pode levar algum tempo para ser concluída dependendo do tamanho do seu locatário.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Políticas de nível de locatário adicionam um controle mais amplo à chave do cliente para o Microsoft 365

Se você já tiver a chave do cliente configurada para o Exchange Online e o SharePoint Online, veja como a nova visualização pública em nível de locatário se ajusta.

A política de criptografia em nível de locatário que você cria criptografa todos os dados para as cargas de trabalho do Microsoft Teams e do Exchange Online no Microsoft 365. Essa política não interfere no DEPs ajustado corretamente que você já criou na chave do cliente.

Exemplos:

Os arquivos do Microsoft Teams e alguns registros de chamada e de reunião do teams que são salvos no OneDrive for Business e no SharePoint são criptografados por uma DEP do SharePoint Online. Um único SharePoint Online DEP criptografa conteúdo em uma única geografia. A DEP no nível do locatário irá criptografar novamente os dados criptografados com a nova política.

Para o Exchange Online, você pode criar uma DEP que criptografe uma ou mais caixas de correio de usuários com a chave do cliente. Quando você cria uma política de nível de locatário, essa política não criptografará as caixas de correio criptografadas. No entanto, a chave de nível de locatário criptografará as caixas de correio que ainda não são afetadas por uma DEP.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurar a chave do cliente no nível do locatário (visualização pública)

Estas etapas são semelhantes, mas não idênticas às etapas para configurar a chave do cliente no nível do aplicativo. Você só deve usar essa visualização pública com dados de teste em locatários de teste. Não use esta versão com dados de produção ou em seu ambiente de produção. Se você já tem uma implantação de produção da chave de cliente, use estas etapas para configurar a chave do cliente no nível do locatário em um ambiente de teste.

Você concluirá a maioria dessas tarefas, conectando-se remotamente ao Azure PowerShell. Para obter melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.

Antes de começar, verifique o seguinte:

- Você precisará usar uma conta corporativa ou de estudante que tenha a função de administrador de conformidade para configurar a chave do cliente no nível do locatário.
- Verifique se você tem o licenciamento apropriado para sua organização. Use uma assinatura paga do Azure faturada usando um contrato corporativo ou um provedor de serviços de nuvem. As assinaturas do Azure adquiridas usando planos de pagamento à medida que você passa ou usando um cartão de crédito não têm suporte para a chave do cliente. A partir de 1º de abril de 2020, a chave de cliente no Office 365 é oferecida no Office 365 e5, M365 e5, M365 E5 conformidade e M365 E5 proteção de informações & SKUs de governança. Office 365 a SKU de conformidade avançada não está mais disponível para novas licenças do aquisição. As licenças de conformidade avançada existentes do Office 365 continuarão a ser suportadas. Embora o serviço possa ser habilitado com um mínimo de uma licença do locatário com a licença apropriada, você ainda deve certificar-se de que todos os usuários que se beneficiam do serviço têm as licenças apropriadas.

### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure

A chave do cliente requer duas chaves para cada DEP (política de criptografia de dados). Para conseguir isso, você deve criar duas assinaturas do Azure. Como prática recomendada, a Microsoft recomenda que você tenha Membros separados da sua organização para configurar uma chave em cada assinatura. Use essas assinaturas do Azure somente para administrar chaves de criptografia para o Microsoft 365. Isso protegerá a sua organização caso um de seus operadores acidentalmente, intencionalmente ou exclua inadvertidamente as chaves para as quais são responsáveis.

Não há um limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir essa prática recomendada ajuda a minimizar o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela chave do cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório

A perda temporária ou permanente das chaves de criptografia raiz pode causar interrupções ou até mesmo uma operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a chave do cliente exigem uma forte proteção. Todos os recursos do Azure usados com os mecanismos de proteção da oferta de chave do cliente além da configuração padrão. As assinaturas do Azure podem ser marcadas ou registradas de uma maneira que impedirá o cancelamento imediato e irrevogável. Isso é conhecido como registro em um período de retenção obrigatório. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a Microsoft. Esse processo pode levar até cinco dias úteis. Anteriormente, isso também era conhecido como "não cancelar".
  
Antes de entrar em contato com a equipe do Microsoft 365, você deve executar as seguintes etapas para cada assinatura do Azure que você usa com a chave do cliente. Verifique se você tem o módulo [AZ do Azure PowerShell](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) instalado antes de começar.

1. Entre com o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Execute o cmdlet Register-AzProviderFeature para registrar suas assinaturas para usar um período de retenção obrigatório. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Entre em contato com a Microsoft para finalizar o processo em [m365ck@microsoft.com](mailto:m365ck@microsoft.com). Inclua o seguinte em seu email:

   **Assunto**: chave de cliente para \<*Your tenant's fully-qualified domain name*\>

   **Corpo**: IDs de assinatura para as quais você deseja que o período de retenção obrigatório seja concluído.
   A saída de Get-AzProviderFeature para cada assinatura.

   O contrato de nível de serviço (SLA) para a conclusão desse processo é de cinco dias úteis quando a Microsoft é notificada (e verificada) que você registrou suas assinaturas para usar um período de retenção obrigatório.

4. Depois que você receber uma notificação da Microsoft de que o registro foi concluído, verifique o status do seu registro executando o comando Get-AzProviderFeature da seguinte maneira. Se verificado, o comando Get-AzProviderFeature retorna um valor de **registrado** para a propriedade de **estado de registro** . Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para concluir o processo, execute o comando Register-AzResourceProvider. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Criar um cofre de chaves Premium do Azure em cada assinatura

As etapas para criar um cofre de chaves são documentadas na [introdução ao Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que orienta você durante a instalação e inicialização do Azure PowerShell, conexão com sua assinatura do Azure, criação de um grupo de recursos e criação de um cofre de chaves nesse grupo de recursos.
  
Ao criar um cofre de chaves, você deve escolher um SKU: Standard ou Premium. A SKU padrão permite que as chaves do Azure Key Vault sejam protegidas por software – não há nenhuma proteção de chave do módulo de segurança de hardware (HSM), e a SKU Premium permite o uso de HSMs para proteção de chaves de compartimento de chaves. A chave do cliente aceita os principais cofres que usam SKU, embora a Microsoft recomende enfaticamente que você use apenas o SKU Premium. O custo das operações com chaves de qualquer tipo é o mesmo, portanto, a única diferença no custo é o custo por mês para cada chave protegida por HSM. Confira os [preços do Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obter detalhes.
  
> [!IMPORTANT]
> Use os compartimentos de chave de SKU Premium e chaves protegidas por HSM para dados de produção e use somente os compartimentos de chave de SKU padrão e chaves para fins de teste e validação.

Use um prefixo comum para os principais compartimentos e inclua uma abreviação do uso e escopo do compartimento de chaves e chaves. Por exemplo, para o serviço contoso em que os cofres estarão localizados na América do Norte, um possível par de nomes é contoso-O365-nd-VaultA1 e contoso-O365-NA-VaultA2. Os nomes de cofre são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez você precise tentar variações dos nomes desejados, caso os nomes desejados já sejam reivindicados por outros clientes do Azure. Uma vez configurados, os nomes de cofre não podem ser alterados, portanto, a prática recomendada é ter um plano escrito para configuração e usar uma segunda pessoa para verificar se o plano foi executado corretamente.

Se possível, crie seus cofres em regiões não emparelhadas. As regiões emparelhadas do Azure fornecem alta disponibilidade entre domínios de falha de serviço. Portanto, os pares regionais podem ser considerados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região é automaticamente obter tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma política de criptografia de dados onde as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade está em uso. A maioria dos geografias tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma política de criptografia de dados. Isso beneficia de um total de quatro regiões de disponibilidade. Para obter mais informações, consulte [continuidade de negócios e recuperação de desastres (BCDR): regiões emparelhadas do Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para uma lista atual de pares regionais.

### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves

Para cada cofre de chave, você precisará definir três conjuntos separados de permissões para a chave do cliente, dependendo da sua implementação. Por exemplo, você precisará definir um conjunto de permissões para cada um dos seguintes:
  
- **Administradores de compartimentos de chaves** que realizarão o gerenciamento diário de seu cofre de chaves para sua organização. Essas tarefas incluem backup, criar, obter, importar, listar e restaurar.

  > [!IMPORTANT]
  > O conjunto de permissões atribuídas aos administradores de compartimento de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. Excluir chaves de criptografia normalmente não é feito, pois fazer isso permanentemente destrói os dados. Como prática recomendada, não conceda essa permissão a administradores de compartimento de chave por padrão. Em vez disso, Reserve-a para os colaboradores de Key Vault e apenas atribua-o a um administrador a curto prazo quando uma compreensão clara das conseqüências é entendida.
  
  Para atribuir essas permissões a um usuário em sua organização, faça logon em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Execute o cmdlet Set-AzKeyVaultAccessPolicy para atribuir as permissões necessárias.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por exemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Os **principais colaboradores do cofre** que podem alterar as permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários deixam ou ingressarem em sua equipe, ou na rara situação de que os administradores de compartimentos de chave precisam de permissão legítima para excluir ou restaurar uma chave. Esse conjunto de colaboradores de compartimento de chave precisa ter a função de colaborador no seu cofre de chaves. Você pode atribuir essa função usando o Azure Resource Manager. Para obter etapas detalhadas, consulte [Use Role-Based controle de acesso](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) para gerenciar o acesso aos seus recursos de assinatura do Azure. O administrador que cria uma assinatura tem esse acesso por padrão e a capacidade de atribuir outros administradores à função colaborador.

- **Dados da Microsoft 365 no serviço de criptografia REST** que realiza o trabalho da chave do cliente no nível do locatário. Para dar permissão ao Microsoft 365, execute o cmdlet **set-AzKeyVaultAccessPolicy** usando a seguinte sintaxe:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Onde:

  - *nome do cofre* é o nome do cofre de chaves que você criou.

  Exemplo: para os dados do Microsoft 365 no serviço de criptografia REST, substitua  *Microsoft 365 AppID* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar e confirmar a exclusão reversível nos seus principais cofres

Quando você pode recuperar rapidamente suas chaves, é menos provável que haja uma interrupção de serviço estendido devido a chaves acidentalmente ou excluídas de forma mal-intencionada. Habilite essa configuração, conhecida como exclusão reversível, antes de poder usar suas chaves com a chave do cliente. Habilitar a exclusão reversível permite recuperar chaves ou cofres dentro de 90 dias de exclusão sem precisar restaurá-los do backup.
  
Para habilitar a exclusão reversível nos seus cofres de chaves, conclua estas etapas:
  
1. Entre em sua assinatura do Azure com o Windows PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Execute o cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) . Neste exemplo, o *nome do cofre* é o nome do cofre de chaves para o qual você está habilitando a exclusão reversível:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirmar se a exclusão reversível está configurada para o cofre de chaves executando o cmdlet **Get-AzKeyVault** . Se a exclusão reversível estiver configurada corretamente para o cofre de chaves, a propriedade de _exclusão reversível_ retornará um valor **true**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Adicionar uma chave a cada cofre de chaves criando ou importando uma chave

Há duas maneiras de adicionar chaves a um Azure Key Vault; Você pode criar uma chave diretamente no compartimento de chaves ou pode importar uma chave. A criação de uma chave diretamente no cofre de chaves é o método menos complicado, enquanto a importação de uma chave fornece total controle sobre como a chave é gerada. Use as chaves RSA. O Azure Key Vault não suporta quebra automática e quebra automática com as teclas de curva elíptica.
  
Para criar uma chave diretamente no seu cofre de chaves, execute o cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) da seguinte maneira:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Onde:

- *nome do cofre* é o nome do cofre de chaves no qual você deseja criar a chave.

- *nome da chave* é o nome que você deseja dar à nova chave.

  > [!TIP]
  > Chaves de nome usando uma Convenção de nomenclatura semelhante, conforme descrito acima para os principais cofres. Dessa forma, em ferramentas que mostram apenas o nome da chave, a cadeia de caracteres é autodescritivo.
  
Se você pretende proteger a chave com um HSM, certifique-se de especificar o **HSM** como o valor do parâmetro _Destination_ , caso contrário, especifique **software**.

Por exemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Verificar o nível de recuperação de suas chaves

A Microsoft 365 exige que a assinatura do Azure Key Vault esteja definida como não cancelar e que as chaves usadas pela chave do cliente tenham a exclusão reversível habilitada. Você pode confirmar isso examinando o nível de recuperação nas chaves.
  
Para verificar o nível de recuperação de uma chave, no PowerShell do Azure, execute o cmdlet Get-AzKeyVaultKey da seguinte maneira:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se a propriedade de _nível de recuperação_ retornar algo diferente de um valor de **recuperável + ProtectedSubscription**, você precisará revisar este artigo e certificar-se de que você seguiu todas as etapas para colocar a assinatura na lista não cancelar e que habilitou "exclusão reversível" em cada um dos seus compartimentos de chave. Em seguida, envie uma captura de tela da saída de `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` em email para m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Fazer backup do Azure Key Vault

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, tanto online quanto offline. Não conecte cópias offline a qualquer rede. Em vez disso, armazene-as em um recurso físico de armazenamento seguro ou comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que será acessível se ocorrer um desastre. Os blobs de backup são o único meio de restaurar o material chave caso uma chave de compartimento de chave seja permanentemente destruída ou não seja processada. As chaves que são externas para o Azure Key Vault e foram importadas para o Azure Key Vault não se qualificam como um backup porque os metadados necessários para a chave do cliente usar a chave não existem com a chave externa. Somente um backup obtido do Azure Key Vault pode ser usado para operações de restauração com a chave do cliente. Portanto, é essencial fazer um backup do Azure Key Vault após a chave ser carregada ou criada.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) da seguinte maneira:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verifique se o arquivo de saída usa o sufixo `.backup` .
  
O arquivo de saída resultante deste cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup pode ser restaurado somente para a assinatura do Azure a partir da qual o backup foi feito.
  
Por exemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar definições de configuração do Azure Key Vault

Executar a validação antes de usar chaves em uma DEP é opcional, mas altamente recomendado. Em particular, se você usar as etapas para configurar suas chaves e cofres diferentes dos descritos neste tópico, você deve validar a integridade dos recursos do Azure Key Vault antes de configurar a chave do cliente.
  
Para verificar se as chaves têm as operações Get, wrapKey e unwrapKey habilitadas:
  
Execute o cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte maneira:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Na saída, procure a política de acesso e a ID de aplicativo (GUID) do Microsoft 365 conforme apropriado. Todas as três operações, Get, wrapKey e unwrapKey devem ser mostradas em permissões para chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzKeyVaultAccessPolicy da seguinte maneira:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Exemplo: para os dados do Microsoft 365 no serviço de criptografia REST, substitua  *Microsoft 365 AppID* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Para verificar se uma data de vencimento não está definida para suas chaves, execute o cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte maneira:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Uma chave expirada não pode ser usada pela chave do cliente e as operações tentadas com uma chave expirada falharão e resultarão em uma interrupção de serviço. É altamente recomendável que as teclas usadas com a chave do cliente não tenham uma data de validade. Uma data de vencimento, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se for necessário usar uma chave que tenha uma data de expiração definida, altere o valor de expiração para 12/31/9999. As chaves com uma data de expiração definida para uma data diferente de 12/31/9999 não passarão pela validação 365 da Microsoft.
  
Para alterar uma data de expiração que tenha sido definida para qualquer valor diferente de 12/31/9999, execute o cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) da seguinte maneira:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obter o URI para cada chave do Azure Key Vault

Após concluir todas as etapas no Azure para configurar seus principais cofres e adicionar suas chaves, execute o comando a seguir para obter o URI da chave em cada cofre de chaves. Você precisará usar esses URIs ao criar e atribuir cada DEP mais tarde, portanto, salve essas informações em um local seguro. Lembre-se de executar este comando uma vez para cada cofre de chaves.
  
No Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurar a política de criptografia de chave do cliente para o locatário

Você precisa ter permissões para poder executar estes cmdlets. Embora este artigo liste todos os parâmetros para os cmdlets, talvez você não tenha acesso a alguns parâmetros se não estiverem incluídos nas permissões atribuídas a você. Para localizar as permissões necessárias para executar qualquer cmdlet ou parâmetro em sua organização, confira [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Criar uma política

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Descrição: habilitar o administrador de conformidade para criar uma nova DEP (política de criptografia de dados) usando duas chaves raiz AKV. Uma vez criado, uma política pode ser atribuída usando Set-M365DataAtRestEncryptionPolicy cmdlet. Após a primeira atribuição de chaves ou após a rotação das teclas, pode levar até 24 horas para que as novas teclas entrem em vigor. Se a nova DEP levar mais de 24 horas para entrar em contato com a Microsoft.

Exemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parâmetros:

| Nome | Descrição | Opcional (s/N) |
|--|--|--|
|Nome|Nome amigável da política de criptografia de dados|N|
|AzureKeyIDs|Especifica dois valores de URI das chaves do Azure Key Vault, separados por uma vírgula, para associar com a política de criptografia de dados|N|
|Descrição|Descrição da política de criptografia de dados|N|

### <a name="assign-policy"></a>Atribuir política

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Descrição: Este cmdlet é usado para configurar a política de criptografia de dados padrão. Essa política será usada para criptografar os dados em todas as cargas de trabalho de suporte. 

Exemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parâmetros:
| Nome | Descrição | Opcional (s/N) |
|--|--|--|
-Policy|Especifica a política de criptografia de dados que precisa ser atribuída; Especifique o nome da política ou a ID da política.|N|

### <a name="modify-or-refresh-policy"></a>Modificar ou atualizar política

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descrição: o cmdlet pode ser usado para modificar ou atualizar uma política existente. Ele também pode ser usado para habilitar ou desabilitar uma política. Após a primeira atribuição de chaves ou após a rotação das teclas, pode levar até 24 horas para que as novas teclas entrem em vigor. Se a nova DEP levar mais de 24 horas para entrar em contato com a Microsoft.

Exemplos:

Desabilitar uma política de criptografia de dados.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Atualizar uma política de criptografia de dados.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parâmetros:
| Nome | Descrição | Opcional (s/N) |
|--|--|--|
|-Identity|Especifica a política de criptografia de dados que você deseja modificar.|N|
|– Atualizar|Use a opção Refresh para atualizar a política de criptografia de dados após girar qualquer uma das chaves associadas no Azure Key Vault. Não é preciso especificar um valor com essa opção.|S|
|Habilitado|O parâmetro Enabled habilita ou desabilita a política de criptografia de dados. Antes de desabilitar uma política, você deve desatribuí-la do locatário. Os valores válidos são:</br > $true: a política está habilitada</br > $true: a política está habilitada. Esse é o valor padrão.
|S|
|-Name|O parâmetro Name especifica o nome exclusivo para a política de criptografia de dados.|S
|– Descrição|O parâmetro Description especifica uma descrição opcional para a política de criptografia de dados.|S|

### <a name="get-policy-details"></a>Obter detalhes de política

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descrição: Este cmdlet lista todas as políticas de criptografia do M365DataAtRest criadas para o locatário ou detalhes sobre uma política específica.

Exemplos:

Este exemplo retorna uma lista resumida de políticas de criptografia do M365DatAtRest na organização.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

Este exemplo retorna informações detalhadas sobre a política de criptografia de dados chamada "política".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parâmetros:

| Nome | Descrição | Opcional (s/N) |
|--|--|--|
|-Identity|Especifica a política de criptografia de dados para a qual você deseja listar os detalhes.|S|

### <a name="get-policy-assignment-info"></a>Obter informações de atribuição de política

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descrição: Este cmdlet lista a política que está atribuída ao locatário no momento.

## <a name="offboarding-from-customer-key"></a>Remoção da chave do cliente

Se você precisar reverter para chaves gerenciadas pela Microsoft, é possível. Quando você externamente, seus dados são criptografados novamente usando a criptografia padrão suportada por cada carga de trabalho individual. Por exemplo, o Exchange Online suporta a criptografia padrão usando chaves gerenciadas pela Microsoft.

Se você optou por externamente seu locatário da chave do cliente no nível do locatário, acesse a Microsoft com uma solicitação por email para "Desabilitar" o serviço para o locatário em [m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> A remoção não é o mesmo que uma limpeza de dados. Uma limpeza de dados permanentemente criptografa-exclui os dados da sua organização do Microsoft 365, a remoção não. Não é possível realizar uma limpeza de dados para uma política de nível de locatário. Para saber mais sobre o caminho de limpeza de dados, confira [revogar suas chaves e iniciar o processo de caminho de limpeza de dados](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

## <a name="about-the-availability-key"></a>Sobre a chave de disponibilidade

Para obter informações sobre a chave de disponibilidade, consulte [saiba mais sobre a chave disponibilidade](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Rotação de chaves

Para obter informações sobre as chaves de rotação ou de rolagem usadas com a chave do cliente, consulte [rolo ou rotação de uma chave do cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md). Ao atualizar a DEP para usar a nova versão das chaves, você executará o cmdlet Set-M365DataAtRestEncryptionPolicy conforme descrito anteriormente neste artigo.

## <a name="related-articles"></a>Artigos relacionados:

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Criptografia de serviço](office-365-service-encryption.md)
