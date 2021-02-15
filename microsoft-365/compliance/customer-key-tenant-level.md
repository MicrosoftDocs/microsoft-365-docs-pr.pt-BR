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
description: Saiba como configurar a Chave do Cliente para todos os dados no locatário do Microsoft 365.
ms.openlocfilehash: f14bbc0cb6dd29883efa4c8d294d8d65cae98641
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751258"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Visão geral da Chave de Cliente do Microsoft 365 no nível do locatário (visualização pública)

Usando chaves fornecidas, você pode criar uma política de criptografia de dados (DEP) e atribuí-la ao locatário. A DEP criptografa dados no locatário para estas cargas de trabalho:

- Mensagens de chat do Teams (chats 1:1, chats em grupo, chats de reunião e conversas de canal)
- Mensagens de mídia do Teams (imagens, trechos de código, vídeos, imagens wiki)
- Gravações de chamada e reunião do Teams armazenadas no armazenamento do Teams
- Notificações de chat do Teams
- Sugestões de chat do Teams da Cortana
- Mensagens de status do Teams
- Informações de usuário e sinal para o Exchange Online

Para o Microsoft Teams, a Chave de Cliente no nível do locatário criptografa novos dados a partir do momento em que a DEP é atribuída ao locatário. A visualização pública não dá suporte à criptografia de dados anteriores. Para o Exchange Online, a Chave do Cliente criptografa todos os dados novos e existentes.

Você pode criar vários DEPs por locatário, mas só pode atribuir um DEP a qualquer momento. Quando você atribui a DEP, a criptografia começa automaticamente, mas pode levar algum tempo para ser concluída, dependendo do tamanho do seu locatário.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>As políticas de nível de locatário adicionam um controle mais amplo à Chave do Cliente para o Microsoft 365

Se você já tiver a Chave do Cliente configurada para o Exchange Online e o SharePoint Online, veja como a nova visualização pública no nível do locatário se encaixa.

A política de criptografia no nível do locatário que você cria criptografa todos os dados para as cargas de trabalho do Microsoft Teams e do Exchange Online no Microsoft 365. Essa política não interfere com DEPs ajustados que você já criou na Chave do Cliente.

Exemplos:

Os arquivos do Microsoft Teams e algumas gravações de chamada e reunião do Teams salvas no OneDrive for Business e no SharePoint são criptografados por uma DEP do SharePoint Online. Uma única DEP do SharePoint Online criptografa conteúdo dentro de uma única área geográfica. A DEP no nível do locatário criptografará os dados novamente com a nova política.

Para o Exchange Online, você pode criar uma DEP que criptografa uma ou mais caixas de correio de usuário com a Chave do Cliente. Quando você cria uma política no nível do locatário, essa política não criptografa as caixas de correio criptografadas. No entanto, a chave no nível do locatário criptografa as caixas de correio que ainda não são afetadas por uma DEP.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurar a Chave do Cliente no nível do locatário (visualização pública)

Essas etapas são semelhantes, mas não idênticas às etapas para configurar a Chave do Cliente no nível do aplicativo. Você só deve usar essa visualização pública com dados de teste em locatários de teste. Não use essa versão com dados de produção ou em seu ambiente de produção. Se você já tiver uma implantação de produção da Chave do Cliente, use estas etapas para configurar a Chave do Cliente no nível do locatário em um ambiente de teste.

Você concluirá a maioria dessas tarefas se conectando remotamente ao Azure PowerShell. Para melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.

Antes de começar, certifique-se do seguinte:

- Você precisará usar uma conta comercial ou de estudante que tenha a função de administrador de conformidade para configurar a Chave do Cliente no nível do locatário.
- Verifique se você tem o licenciamento apropriado para sua organização. Use uma Assinatura do Azure paga e faturada usando um Contrato Empresarial ou um Provedor de Serviços de Nuvem. Assinaturas do Azure adquiridas usando planos Pagar à Medida que Você Vai ou usando um cartão de crédito não são suportadas pela Chave do Cliente. A partir de 1º de abril de 2020, a Chave de Cliente no Office 365 é oferecida no Office 365 E5, M365 E5, Conformidade do M365 E5 e SKUs de Proteção de Informações do M365 E5 & Governança. A SKU de Conformidade Avançada do Office 365 não está mais disponível para a aquisição de novas licenças. As licenças existentes de Conformidade Avançada do Office 365 continuarão a ter suporte. Embora o serviço possa ser habilitado com no mínimo uma licença no locatário com a licença apropriada, você ainda deve garantir que todos os usuários que se beneficiam do serviço tenham as licenças apropriadas.

### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure

A Chave do Cliente exige duas chaves para cada DEP (política de criptografia de dados). Para conseguir isso, você deve criar duas assinaturas do Azure. Como prática recomendável, a Microsoft recomenda que você tenha membros separados da sua organização para configurar uma chave em cada assinatura. Use essas assinaturas do Azure somente para administrar chaves de criptografia do Microsoft 365. Isso protege sua organização caso um de seus operadores exclua acidentalmente, intencionalmente ou mal-intencionado ou, de alguma forma, incorretamente as chaves pelas quais são responsáveis.

Não há um limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir essa prática prática ajuda a minimizar o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela Chave do Cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório

A perda temporária ou permanente de chaves de criptografia raiz pode ser prejudicial ou até mesmo catastrófica para a operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a Chave do Cliente exigem proteção forte. Todos os recursos do Azure usados com a Chave do Cliente oferecem mecanismos de proteção além da configuração padrão. As assinaturas do Azure podem ser marcadas ou registradas de forma a impedir o cancelamento imediato e irrevogável. Isso é conhecido como registro para um período de retenção obrigatório. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a Microsoft. Esse processo pode levar até cinco dias úteis. Anteriormente, isso era conhecido como "Não Cancelar".
  
Antes de entrar em contato com a equipe do Microsoft 365, você deve executar as seguintes etapas para cada assinatura do Azure usada com a Chave do Cliente. Verifique se você tem o [módulo do Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) instalado antes de iniciar.

1. Entre com o Azure PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Execute o Register-AzProviderFeature cmdlet para registrar suas assinaturas para usar um período de retenção obrigatório. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Entre em contato com a Microsoft para finalizar o processo [em m365ck@microsoft.com](mailto:m365ck@microsoft.com). Inclua o seguinte no seu email:

   **Assunto**: Chave do Cliente para \<*Your tenant's fully-qualified domain name*\>

   **Corpo:** IDs de assinatura para as quais você deseja finalizar o período de retenção obrigatório.
   A saída do Get-AzProviderFeature para cada assinatura.

   O Contrato de Nível de Serviço (SLA) para conclusão desse processo é de cinco dias úteis após a Microsoft ser notificada (e verificada) de que você registrou suas assinaturas para usar um período de retenção obrigatório.

4. Depois de receber uma notificação da Microsoft de que o registro foi concluído, verifique o status do seu registro executando o Get-AzProviderFeature comando da seguinte forma. Se verificado, o Get-AzProviderFeature comando retornará um valor **registrado** para a propriedade **Estado de** registro. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para concluir o processo, execute o Register-AzResourceProvider comando. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Criar um Azure Key Vault premium em cada assinatura

As etapas para criar um cofre de chaves estão documentadas em Getting [Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que orienta você na instalação e no lançamento do Azure PowerShell, conexão com sua assinatura do Azure, criação de um grupo de recursos e criação de um cofre de chaves nesse grupo de recursos.
  
Ao criar um cofre de chaves, você deve escolher uma SKU: Standard ou Premium. A SKU Padrão permite que as chaves do Azure Key Vault sejam protegidas com software - não há proteção de chave HSM (Módulo de Segurança de Hardware) - e a SKU Premium permite o uso de HSMs para proteção de chaves key Vault. A Chave do Cliente aceita cofres de chaves que usam qualquer uma das SKU, embora a Microsoft recomende que você use apenas a SKU Premium. O custo das operações com chaves de qualquer tipo é o mesmo, portanto, a única diferença no custo é o custo por mês para cada chave protegida por HSM. Confira [os preços do Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obter detalhes.
  
> [!IMPORTANT]
> Use os cofres de chaves Premium SKU e as chaves protegidas por HSM para dados de produção e use somente chaves e cofres de chaves SKU Padrão para fins de teste e validação.

Use um prefixo comum para cofres de chaves e inclua uma abreviação do uso e do escopo do cofre de chaves e chaves. Por exemplo, para o serviço contoso onde os cofres estarão localizados na América do Norte, um par de nomes possíveis é Contoso-O365-NA-VaultA1 e Contoso-O365-NA-VaultA2. Os nomes dos cofres são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez seja necessário experimentar variações dos nomes desejados caso os nomes desejados já sejam reivindicados por outros clientes do Azure. Depois de configurado, os nomes do cofre não podem ser alterados, portanto, a prática ideal é ter um plano escrito para instalação e usar uma segunda pessoa para verificar se o plano foi executado corretamente.

Se possível, crie seus cofres em regiões não emparelhadas. Regiões emparelhadas do Azure fornecem alta disponibilidade entre domínios de falha de serviço. Portanto, pares regionais podem ser pensados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região está ganhando automaticamente tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma política de criptografia de dados onde as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade estão em uso. A maioria das regiões tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma política de criptografia de dados. Isso beneficia-se de um total de quatro regiões de disponibilidade. Para obter mais informações, consulte Continuidade de negócios e recuperação de desastre [(BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) Regiões emparelhadas do Azure para obter uma lista atual de pares regionais.

### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves

Para cada cofre de chaves, você precisará definir três conjuntos separados de permissões para a Chave de Cliente, dependendo da implementação. Por exemplo, você precisará definir um conjunto de permissões para cada um dos seguintes:
  
- **Administradores de cofre de** chaves que executarão o gerenciamento do seu cofre de chaves no dia a dia da sua organização. Essas tarefas incluem backup, criação, obter, importar, listar e restaurar.

  > [!IMPORTANT]
  > O conjunto de permissões atribuídas aos administradores do cofre de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. A exclusão de chaves de criptografia normalmente não é feita, pois fazer isso destrói permanentemente os dados. Como prática prática, não conceda essa permissão aos administradores do cofre de chaves por padrão. Em vez disso, reserve-o para colaboradores do key vault e atribua-o apenas a um administrador a curto prazo, uma vez que uma compreensão clara das consequências seja compreendida.
  
  Para atribuir essas permissões a um usuário em sua organização, entre em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

   Execute o Set-AzKeyVaultAccessPolicy cmdlet para atribuir as permissões necessárias.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por exemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores do key vault** que podem alterar permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários saírem ou ingressarem em sua equipe, ou na rara situação em que os administradores do cofre de chaves precisam de permissão para excluir ou restaurar uma chave. Esse conjunto de colaboradores do key vault precisa ter a função Colaborador no cofre de chaves. Você pode atribuir essa função usando o Gerenciador de Recursos do Azure. Para saber as etapas detalhadas, [confira Usar Role-Based Controle](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) de Acesso para gerenciar o acesso aos recursos de assinatura do Azure. O administrador que cria uma assinatura tem esse acesso por padrão e a capacidade de atribuir outros administradores à função Colaborador.

- **Dados do Microsoft 365 no serviço de** criptografia rest que faz o trabalho da Chave do Cliente no nível do locatário. Para dar permissão ao Microsoft 365, execute o cmdlet **Set-AzKeyVaultAccessPolicy** usando a seguinte sintaxe:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Onde:

  - *O nome do* cofre é o nome do cofre de chaves que você criou.

  Exemplo: para o serviço de Criptografia rest de dados do Microsoft 365, substitua  *o Microsoft 365 appID* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar e confirmar a exclusão suave em seus cofres de chaves

Quando você pode recuperar suas chaves rapidamente, é menos provável que uma paralisação de serviço estendida seja devido a chaves excluídas acidentalmente ou maliciosamente. Habilita essa configuração, conhecida como Exclusão Suave, antes de poder usar suas chaves com a Chave do Cliente. A habilitação da Exclusão Suave permite que você recupere chaves ou cofres dentro de 90 dias após a exclusão sem precisar restaurá-los do backup.
  
Para habilitar a Exclusão Suave em seus cofres de chaves, conclua estas etapas:
  
1. Entre em sua assinatura do Azure com o Windows PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Execute o cmdlet [Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) Neste exemplo, o *nome do cofre* é o nome do cofre de chaves para o qual você está habilitando a exclusão simples:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirme se a exclusão suave está configurada para o cofre de chaves executando o cmdlet **Get-AzKeyVault.** Se a exclusão suave estiver configurada corretamente para o cofre de chaves, a propriedade _Soft Delete Enabled_ retornará um valor **True**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Adicione uma chave a cada cofre de chaves criando ou importando uma chave

Há duas maneiras de adicionar chaves a um Azure Key Vault; você pode criar uma chave diretamente no Key Vault ou pode importar uma chave. Criar uma chave diretamente no Key Vault é o método menos complicado, enquanto importar uma chave fornece controle total sobre como a chave é gerada. Use as teclas RSA. O Azure Key Vault não dá suporte a quebras e quebras de quebra com teclas de curva elípticas.
  
Para criar uma chave diretamente no cofre de chaves, execute o cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) da seguinte forma:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Onde:

- *O nome* do cofre é o nome do cofre de chaves no qual você deseja criar a chave.

- *é o* nome que você deseja dar à nova chave.

  > [!TIP]
  > Name keys using a similar naming convention as described above for key vaults. Dessa forma, em ferramentas que mostram apenas o nome da chave, a cadeia de caracteres é auto-descrevendo.
  
Se você pretende proteger a chave com um HSM, certifique-se de especificar **HSM** como o valor do parâmetro _Destination;_ caso contrário, especifique **Software**.

Por exemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Verificar o nível de recuperação de suas chaves

O Microsoft 365 requer que a assinatura do Azure Key Vault seja definida como Não Cancelar e que as chaves usadas pela Chave do Cliente tenham a exclusão soft habilitada. Você pode confirmar isso analisando o nível de recuperação em suas chaves.
  
Para verificar o nível de recuperação de uma chave, no Azure PowerShell, execute o cmdlet Get-AzKeyVaultKey seguinte:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se a propriedade _Nível_ de Recuperação retornar algo diferente de um valor **recoverable+ProtectedSubscription**, você precisará revisar este artigo e garantir que seguiu todas as etapas para colocar a assinatura na lista Não Cancelar e que você habilitar a "exclusão reversível" em cada um dos seus cofres de chaves. Em seguida, envie uma captura de tela da saída `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` do email para m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, online e offline. Não conecte cópias offline a nenhuma rede. Em vez disso, armazene-os em uma instalação de armazenamento físico seguro ou comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que poderá ser acessado em caso de desastre. Os blobs de backup são o único meio de restaurar material de chave caso uma chave do Key Vault seja destruída permanentemente ou, de outra forma, inoperável. As chaves externas ao Azure Key Vault e que foram importadas para o Azure Key Vault não se qualificam como um backup porque os metadados necessários para a Chave do Cliente usar a chave não existem com a chave externa. Somente um backup feito do Azure Key Vault pode ser usado para operações de restauração com a Chave do Cliente. Portanto, é essencial fazer um backup do Azure Key Vault depois que uma chave é carregada ou criada.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) da seguinte forma:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verifique se o arquivo de saída usa o `.backup` sufixo.
  
O arquivo de saída resultante desse cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup só pode ser restaurado para a assinatura do Azure da qual o backup foi feito.
  
Por exemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar as definições de configuração do Azure Key Vault

Executar a validação antes de usar chaves em um DEP é opcional, mas altamente recomendável. Em particular, se você usar etapas para configurar suas chaves e cofres diferentes dos descritos neste tópico, deverá validar a saúde dos recursos do Azure Key Vault antes de configurar a Chave do Cliente.
  
Para verificar se suas chaves têm operações get, wrapKey e unwrapKey habilitadas:
  
Execute o cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Na saída, procure a Política de Acesso e a ID do aplicativo do Microsoft 365 (GUID), conforme apropriado. Todas as três operações, get, wrapKey e unwrapKey devem ser mostradas em Permissões para Chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzKeyVaultAccessPolicy seguinte:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Exemplo: para o serviço de Criptografia rest de dados do Microsoft 365, substitua  *o Microsoft 365 appID* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Para verificar se uma data de expiração não está definida para suas chaves, execute o cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Uma chave expirada não pode ser usada pela Chave do Cliente, e as tentativas de operações com uma chave expirada falharão e possivelmente resultarão em uma insoização do serviço. É fortemente recomendável que as chaves usadas com a Chave do Cliente não tenham uma data de expiração. Uma data de expiração, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se for necessário usar uma chave que tenha uma data de expiração definida, altere o valor de expiração para 31/12/9999. Chaves com uma data de expiração definida para uma data diferente de 31/12/9999 não passarão na validação do Microsoft 365.
  
Para alterar uma data de expiração que tenha sido definida para qualquer valor diferente de 31/12/9999, execute o cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) da seguinte forma:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obter o URI de cada chave do Azure Key Vault

Depois de concluir todas as etapas no Azure para configurar seus cofres de chaves e adicionar suas chaves, execute o seguinte comando para obter o URI da chave em cada cofre de chaves. Você precisará usar esses URIs ao criar e atribuir cada DEP posteriormente, portanto, salve essas informações em um local seguro. Lembre-se de executar esse comando uma vez para cada cofre de chaves.
  
No Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurar a política de criptografia de Chave de Cliente para seu locatário

Para executar esses cmdlets, você precisa ter permissões. Embora este artigo lista todos os parâmetros para os cmdlets, talvez você não tenha acesso a alguns parâmetros se eles não estão incluídos nas permissões atribuídas a você. Para localizar as permissões necessárias para executar qualquer cmdlet ou parâmetro em sua organização, confira [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Criar uma política

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Descrição: permitir que o administrador de conformidade crie uma nova política de criptografia de dados (DEP) usando duas chaves raiz AKV. Depois de criada, uma política pode ser atribuída usando Set-M365DataAtRestEncryptionPolicy cmdlet. Após a primeira atribuição de teclas ou depois de girar as teclas, pode levar até 24 horas para que as novas teclas entre em vigor. Se a nova DEP levar mais de 24 horas para entrar em vigor, entre em contato com a Microsoft.

Exemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parâmetros:

| Nome | Descrição | Opcional (S/N) |
|--|--|--|
|Nome|Nome amigável da política de criptografia de dados|N|
|AzureKeyIDs|Especifica dois valores de URI das chaves do Azure Key Vault, separadas por vírgula, para associar à política de criptografia de dados|N|
|Descrição|Descrição da política de criptografia de dados|N|

### <a name="assign-policy"></a>Atribuir política

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Descrição: este cmdlet é usado para configurar a Política de Criptografia de Dados padrão. Essa política será usada para criptografar dados em todas as cargas de trabalho de suporte. 

Exemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parâmetros:
| Nome | Descrição | Opcional (S/N) |
|--|--|--|
-Policy|Especifica a política de criptografia de dados que precisa ser atribuída; especifique o Nome da Política ou a ID da Política.|N|

### <a name="modify-or-refresh-policy"></a>Modificar ou atualizar política

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descrição: o cmdlet pode ser usado para modificar ou atualizar uma política existente. Ele também pode ser usado para habilitar ou desabilitar uma política. Após a primeira atribuição de teclas ou depois de girar as teclas, pode levar até 24 horas para que as novas teclas entre em vigor. Se a nova DEP levar mais de 24 horas para entrar em vigor, entre em contato com a Microsoft.

Exemplos:

Desabilite uma política de criptografia de dados.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Atualizar uma política de criptografia de dados.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parâmetros:
| Nome | Descrição | Opcional (S/N) |
|--|--|--|
|-Identity|Especifica a política de criptografia de dados que você deseja modificar.|N|
|-Refresh|Use a opção Atualizar para atualizar a política de criptografia de dados depois de girar qualquer uma das chaves associadas no Azure Key Vault. Não é preciso especificar um valor com essa opção.|S|
|-Enabled|O parâmetro Enabled habilita ou desabilita a política de criptografia de dados. Antes de desabilitar uma política, você deve reaigná-la do seu locatário. Os valores válidos são:</br > $true: a política está habilitada</br > $true: a política está habilitada. Esse é o valor padrão.
|S|
|-Name|O parâmetro Name especifica o nome exclusivo da política de criptografia de dados.|S
|-Description|O parâmetro Description especifica uma descrição opcional para a política de criptografia de dados.|S|

### <a name="get-policy-details"></a>Obter detalhes da política

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descrição: este cmdlet lista todas as políticas de criptografia M365DataAtRest criadas para o locatário ou detalhes sobre uma política específica.

Exemplos:

Este exemplo retorna uma lista resumida das políticas de Criptografia M365DatAtRest na organização.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

Este exemplo retorna informações detalhadas sobre a política de criptografia de dados chamada "POLÍTICA DE NAM".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parâmetros:

| Nome | Descrição | Opcional (S/N) |
|--|--|--|
|-Identity|Especifica a política de criptografia de dados para a que você deseja listar os detalhes.|S|

### <a name="get-policy-assignment-info"></a>Obter informações de atribuição de política

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descrição: este cmdlet lista a política que está atribuída no momento ao locatário.

## <a name="offboarding-from-customer-key"></a>Offboarding from Customer Key

Se você precisar reverter para as chaves gerenciadas pela Microsoft, poderá. Quando você se desalografa, seus dados são criptografados de forma recriptada usando a criptografia padrão suportada por cada carga de trabalho individual. Por exemplo, o Exchange Online dá suporte à criptografia padrão usando chaves gerenciadas pela Microsoft.

Se você decidiu excluir o locatário da Chave do Cliente no nível do locatário, entre em contato com a Microsoft com uma solicitação por email para "desabilitar" o serviço para o locatário [em m365ck@microsoft.com.](mailto:m365ck@microsoft.com)

> [!IMPORTANT]
> A reação não é igual à limpeza de dados. Uma limpeza de dados exclui permanentemente os dados da sua organização do Microsoft 365, a exclusão não faz. Não é possível executar uma limpeza de dados para uma política no nível do locatário. Para obter informações sobre o caminho de limpeza de dados, [consulte Revogar suas chaves e iniciar o processo de limpeza de dados.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>Sobre a chave de disponibilidade

Para obter informações sobre a chave de disponibilidade, [consulte Saiba mais sobre a chave de disponibilidade.](customer-key-availability-key-understand.md)

## <a name="key-rotation"></a>Rotação de teclas

Para obter informações sobre como girar ou rolar chaves usadas com a Chave do Cliente, consulte Rolar ou girar uma Chave de Cliente [ou uma chave de disponibilidade.](customer-key-availability-key-roll.md) Ao atualizar a DEP para usar a nova versão das chaves, você executará o cmdlet Set-M365DataAtRestEncryptionPolicy conforme descrito anteriormente neste artigo.

## <a name="related-articles"></a>Artigos relacionados:

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Criptografia de Serviço](office-365-service-encryption.md)
