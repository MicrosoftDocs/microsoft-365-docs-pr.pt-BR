---
title: Configurar a chave do cliente
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
description: Saiba como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e arquivos do teams.
ms.openlocfilehash: 346b723a4741e18d161122edecf985a3fb8c7845
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794216"
---
# <a name="set-up-customer-key"></a>Configurar a chave do cliente

Com a chave do cliente, você controla as chaves de criptografia da sua organização e, em seguida, configura o Microsoft 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft. Em outras palavras, a chave do cliente permite que os clientes adicionem uma camada de criptografia que pertença a eles, com suas chaves. Os dados em repouso incluem dados do Exchange Online e do Skype for Business que são armazenados em caixas de correio e arquivos armazenados no SharePoint Online e no OneDrive for Business.

Você deve configurar o Azure antes de poder usar a chave do cliente para o Office 365. Este tópico descreve as etapas que você precisa seguir para criar e configurar os recursos do Azure necessários e, em seguida, fornece as etapas para configurar a chave do cliente no Office 365. Depois de concluir a instalação do Azure, determine a política e, portanto, quais teclas serão atribuídas a caixas de correio e arquivos em sua organização. Caixas de correio e arquivos para os quais você não atribui uma política usarão políticas de criptografia controladas e gerenciadas pela Microsoft. Para obter mais informações sobre a chave do cliente ou para uma visão geral, consulte [Service Encryption with Customer Key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> É altamente recomendável seguir as práticas recomendadas neste tópico. Eles são chamados de **Tip** e **importante**. A chave do cliente dá controle sobre as chaves de criptografia raiz cujo escopo pode ser tão grande quanto sua organização inteira. Isso significa que os erros feitos com essas chaves podem ter um impacto amplo e podem resultar em interrupções de serviço ou perda irrevogável dos dados.
  
## <a name="before-you-set-up-customer-key"></a>Antes de configurar a chave do cliente

Antes de começar, verifique se você tem o licenciamento apropriado para sua organização. A chave do cliente no Microsoft 365 é oferecida no Office 365 E5 ou no SKU de conformidade avançada. Para entender os conceitos e os procedimentos deste tópico, revise a documentação do [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) . Além disso, familiarize-se com os termos usados no Azure, por exemplo, [locatário](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).

O FastTrack é usado apenas para coletar as informações de locatário e configuração de serviço necessárias usadas para registrar-se na chave do cliente. As ofertas de chave do cliente são publicadas via FastTrack para que você e nossos parceiros enviem as informações necessárias usando o mesmo método. O FastTrack também facilita o arquivamento dos dados que você fornece na oferta.
  
Se você precisar de suporte adicional além da documentação, entre em contato com a MCS (serviços de consultoria da Microsoft), PFE (Engenharia de campo Premier) ou um parceiro da Microsoft para obter assistência. Para fornecer comentários sobre a chave do cliente, incluindo a documentação, envie suas ideias, sugestões e perspectivas para o customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Visão geral das etapas para configurar a chave do cliente

Para configurar a chave do cliente, conclua essas tarefas na ordem listada. O restante deste artigo fornece instruções detalhadas para cada tarefa ou links para mais informações sobre cada etapa do processo.
  
**No Azure e no Microsoft FastTrack:**
  
Você concluirá a maioria dessas tarefas, conectando-se remotamente ao Azure PowerShell. Para obter melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.
  
- [Criar duas novas assinaturas do Azure](#create-two-new-azure-subscriptions)

- [Registrar assinaturas do Azure para usar um período de retenção obrigatório](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  O registro pode levar de um a cinco dias úteis.

- [Enviar uma solicitação para ativar a chave do cliente para o Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Depois de criar as duas novas assinaturas do Azure, você precisará enviar a solicitação de oferta de chave do cliente apropriada, concluindo um formulário da Web hospedado no portal Microsoft FastTrack. **A equipe do FastTrack não fornece assistência com a chave do cliente. O Office simplesmente usa o portal do FastTrack para permitir que você envie o formulário e ajude-nos a acompanhar as ofertas relevantes para a chave do cliente**.

- [Criar um cofre de chaves Premium do Azure em cada assinatura](#create-a-premium-azure-key-vault-in-each-subscription)

- [Atribuir permissões a cada cofre de chaves](#assign-permissions-to-each-key-vault)

- [Habilitar e confirmar a exclusão reversível nos seus principais cofres](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Adicionar uma chave a cada cofre de chaves criando ou importando uma chave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Verificar o nível de recuperação de suas chaves](#check-the-recovery-level-of-your-keys)

- [Fazer backup do Azure Key Vault](#back-up-azure-key-vault)

- [Validar definições de configuração do Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Obter o URI para cada chave do Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)

**No Office 365:**
  
Exchange Online e Skype for Business:
  
- [Criar uma DEP (política de criptografia de dados) para uso com o Exchange Online e o Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Atribuir uma DEP a uma caixa de correio](#assign-a-dep-to-a-mailbox)

- [Validar criptografia de caixa de correio](#validate-mailbox-encryption)

SharePoint Online e OneDrive for Business:
  
- [Criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do OneDrive for Business](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Validar a criptografia de arquivo para os arquivos do SharePoint Online, do OneDrive for Business e do teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Concluir tarefas no Azure Key Vault e no Microsoft FastTrack para chave do cliente

Conclua essas tarefas no Azure Key Vault. Você precisará concluir essas etapas, independentemente se pretende configurar a chave do cliente para o Exchange Online e o Skype for Business ou o SharePoint Online, o OneDrive for Business e os arquivos do Microsoft Teams ou para todos os serviços com suporte no Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure

A chave do cliente requer duas assinaturas do Azure. Como prática recomendada, a Microsoft recomenda que você crie novas assinaturas do Azure para uso com a chave do cliente. Chaves do Azure Key Vault só podem ser autorizadas para aplicativos no mesmo locatário do Azure Active Directory (AAD), você deve criar as novas assinaturas usando o mesmo locatário do Azure AD usado com sua organização onde o DEPs será atribuído. Por exemplo, usando sua conta corporativa ou de estudante que tenha privilégios de administrador global em sua organização. Para obter etapas detalhadas, consulte [inscrever-se no Azure como uma organização](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> A chave do cliente requer duas chaves para cada DEP (política de criptografia de dados). Para conseguir isso, você deve criar duas assinaturas do Azure. Como prática recomendada, a Microsoft recomenda que você tenha Membros separados da sua organização para configurar uma chave em cada assinatura. Além disso, essas assinaturas do Azure devem ser usadas apenas para administrar chaves de criptografia para o Office 365. Isso protegerá a sua organização caso um de seus operadores acidentalmente, intencionalmente ou exclua inadvertidamente as chaves para as quais são responsáveis. <br/> Recomendamos que você configure novas assinaturas do Azure que são usadas unicamente para o gerenciamento de recursos do Azure Key Vault para uso com a chave do cliente. Não há um limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir estas práticas recomendadas minimizará o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela chave do cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar uma solicitação para ativar a chave do cliente para o Office 365

Depois de concluir as etapas do Azure, você precisará enviar uma solicitação de oferta no [portal Microsoft FastTrack](https://fasttrack.microsoft.com/). Depois de enviar uma solicitação pelo portal da Web do FastTrack, a Microsoft verifica os dados de configuração e informações de contato do Azure Key Vault que você forneceu. As seleções feitas no formulário de oferta em relação aos responsáveis autorizados da sua organização são fundamentais e necessárias para a conclusão do registro de chave do cliente. Os gerentes da sua organização selecionados no formulário serão usados para garantir a autenticidade de qualquer solicitação de revogação e destruição de todas as chaves usadas com uma política de criptografia de dados de chave do cliente. Você precisará fazer esta etapa uma vez para ativar a chave do cliente para o Exchange Online e a cobertura do Skype for Business e uma segunda vez para ativar a chave do cliente para o SharePoint Online e o OneDrive for Business.
  
Para enviar uma oferta para ativar a chave do cliente, conclua estas etapas:
  
1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, faça logon no [portal do Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Quando estiver conectado, navegue até o **painel**.

3. Escolha **implantar** na barra de navegação **ou** selecione **Exibir todos os recursos de implantação** no cartão de informações **implantar** e revise a lista de ofertas atuais.

4. Escolha o cartão de informações para a oferta que se aplica a você:

   - **Exchange Online e Skype for Business:** Escolha a **ajuda da chave de criptografia solicitar para o Exchange Online** .

   - **Arquivos do SharePoint Online, do onedrive e do teams:** Escolha a **ajuda da chave de criptografia solicitar para o SharePoint e o onedrive** .

5. Após revisar os detalhes da oferta, escolha **continuar para a etapa 2**.

6. Preencha todos os detalhes aplicáveis e as informações solicitadas sobre o formulário de oferta. Preste bastante atenção às suas seleções para quais responsáveis da sua organização você deseja autorizar a aprovar a destruição permanente e irreversível de chaves e dados de criptografia. Depois de concluir o formulário, escolha **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório

A perda temporária ou permanente das chaves de criptografia raiz pode ser muito prejudicial ou até mesmo uma operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a chave do cliente exigem uma forte proteção. Todos os recursos do Azure usados com os mecanismos de proteção da oferta de chave do cliente além da configuração padrão. As assinaturas do Azure podem ser marcadas ou registradas de uma maneira que impedirá o cancelamento imediato e irrevogável. Isso é conhecido como registro em um período de retenção obrigatório. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a equipe do Microsoft 365. Esse processo pode levar de um a cinco dias úteis. Anteriormente, isso também era conhecido como "não cancelar".
  
Antes de entrar em contato com a equipe do Microsoft 365, você deve executar as seguintes etapas para cada assinatura do Azure que você usa com a chave do cliente. Verifique se você tem o módulo [AZ do Azure PowerShell](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) instalado antes de começar.
  
1. Entre com o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Execute o cmdlet Register-AzProviderFeature para registrar suas assinaturas para usar um período de retenção obrigatório. Execute esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Entre em contato com a Microsoft para finalizar o processo. Para a equipe do SharePoint e do OneDrive for Business, entre em contato com [Spock@microsoft.com](mailto:spock@microsoft.com). Para o Exchange Online e o Skype for Business, entre em contato com a [exock@microsoft.com](mailto:exock@microsoft.com). Inclua o seguinte em seu email:

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
  
Para cada serviço do Microsoft 365 com o qual você usará a chave do cliente, crie um cofre de chaves em cada uma das duas assinaturas do Azure que você criou. Por exemplo, apenas para o Exchange Online e o Skype for Business, somente para o SharePoint Online e o OneDrive for Business, você irá criar apenas um par de cofres. Para habilitar a chave do cliente para o Exchange Online e o SharePoint Online, você irá criar dois pares de cofres de chaves.
  
Use uma Convenção de nomenclatura para os principais cofres que reflitam o uso pretendido da política de criptografia de dados com a qual você irá associar os cofres. Consulte a seção práticas recomendadas abaixo para obter recomendações de Convenção de nomenclatura.
  
Crie um conjunto separado e emparelhado de cofres para cada política de criptografia de dados. Para o Exchange Online, o escopo de uma política de criptografia de dados é escolhido quando você atribui a política à caixa de correio. Uma caixa de correio pode ter apenas uma política atribuída, e você pode criar até 50 políticas. Para o SharePoint Online, o escopo de uma política é todos os dados dentro de uma organização em um local geográfico ou _geo_.

A criação de compartimentos de chave também requer a criação de grupos de recursos do Azure, pois os principais cofres precisam de capacidade de armazenamento (embora muito pequeno) e do registro em log de compartimento de chaves, se habilitado, também gera dados armazenados. Como prática recomendada, a Microsoft recomenda o uso de administradores separados para gerenciar cada grupo de recursos, com a administração centralizada com o conjunto de administradores que gerenciará todos os recursos de chave do cliente relacionados.
  
> [!IMPORTANT]
> Para maximizar a disponibilidade, seus cofres principais devem estar em regiões próximos ao serviço do Microsoft 365. Por exemplo, se sua organização do Exchange Online estiver na América do Norte, coloque seus principais cofres na América do Norte. Se sua organização do Exchange Online estiver na Europa, coloque seus principais cofres na Europa.<br/>Use um prefixo comum para os principais compartimentos e inclua uma abreviação do uso e do escopo do compartimento de chaves e chaves (por exemplo, para o serviço do SharePoint da Contoso onde os cofres estarão localizados na América do Norte, um possível par de nomes é contoso-O365SP-VaultA1-e contoso-O365SP-NA-VaultA2. Os nomes de cofre são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez você precise tentar variações dos nomes desejados, caso os nomes desejados já sejam reivindicados por outros clientes do Azure. Os nomes de cofre de julho de 2017 não podem ser alterados, portanto, uma prática recomendada é ter um plano escrito para configuração e usar uma segunda pessoa para verificar se o plano foi executado corretamente.<br/>Se possível, crie seus cofres em regiões não emparelhadas. As regiões emparelhadas do Azure fornecem alta disponibilidade entre domínios de falha de serviço. Portanto, os pares regionais podem ser considerados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região é automaticamente obter tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma política de criptografia de dados onde as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade está em uso. A maioria dos geografias tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma política de criptografia de dados. Isso beneficia de um total de quatro regiões de disponibilidade. Para obter mais informações, consulte [continuidade de negócios e recuperação de desastres (BCDR): regiões emparelhadas do Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para uma lista atual de pares regionais.
  
### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves

Para cada cofre de chave, você precisará definir três conjuntos separados de permissões para a chave do cliente, dependendo da sua implementação. Por exemplo, você precisará definir um conjunto de permissões para cada um dos seguintes:
  
- **Administradores de compartimentos de chaves** que realizarão o gerenciamento diário de seu cofre de chaves para sua organização. Essas tarefas incluem backup, criar, obter, importar, listar e restaurar.

  > [!IMPORTANT]
  > O conjunto de permissões atribuídas aos administradores de compartimento de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. Excluir chaves de criptografia normalmente não é feito, pois fazer isso permanentemente destrói os dados. Como prática recomendada, não conceda essa permissão a administradores de compartimento de chave por padrão. Em vez disso, Reserve-a para os colaboradores de Key Vault e apenas atribua-o a um administrador a curto prazo quando uma compreensão clara das conseqüências é entendida.
  
  Para atribuir essas permissões a um usuário em sua organização, faça logon em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

- Execute o cmdlet Set-AzKeyVaultAccessPolicy para atribuir as permissões necessárias.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por exemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Os **principais colaboradores do cofre** que podem alterar as permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários saírem ou ingressarem em sua equipe ou na situação extremamente rara que os administradores de cofre de chaves precisam de permissão legítima para excluir ou restaurar uma chave. Esse conjunto de colaboradores de compartimento de chave precisa ter a função de **colaborador** no seu cofre de chaves. Você pode atribuir essa função usando o Azure Resource Manager. Para obter etapas detalhadas, consulte [use Role-Based Access Control para gerenciar o acesso aos seus recursos de assinatura do Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). O administrador que cria uma assinatura tem esse acesso implicitamente, bem como a capacidade de atribuir outros administradores à função colaborador.

- Se você pretende usar a chave do cliente com o Exchange Online e o Skype for Business, precisará conceder permissão ao Microsoft 365 para usar o cofre de chaves em nome do Exchange Online e do Skype for Business. Da mesma forma, se você pretende usar a chave do cliente com o SharePoint Online e o OneDrive for Business, precisará adicionar permissão ao Microsoft 365 para usar o cofre de chaves em nome do SharePoint Online e do OneDrive for Business. Para dar permissão ao Microsoft 365, execute o cmdlet **set-AzKeyVaultAccessPolicy** usando a seguinte sintaxe: 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Onde:

    - *nome do cofre* é o nome do cofre de chaves que você criou.

    - Para o Exchange Online e o Skype for Business, substitua o  *Office 365 AppID* por `00000002-0000-0ff1-ce00-000000000000`

    - Para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, substitua o  *Office 365 AppID* por `00000003-0000-0ff1-ce00-000000000000`

  Exemplo: definir permissões para o Exchange Online e o Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Exemplo: definindo permissões para os arquivos do SharePoint Online, do OneDrive for Business e do teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar e confirmar a exclusão reversível nos seus principais cofres

Quando você pode recuperar rapidamente suas chaves, é menos provável que haja uma interrupção de serviço estendido devido a chaves acidentalmente ou excluídas de forma mal-intencionada. Você precisa habilitar essa configuração, conhecida como exclusão reversível, antes de poder usar suas chaves com a chave do cliente. Habilitar a exclusão reversível permite recuperar chaves ou cofres dentro de 90 dias de exclusão sem precisar restaurá-los do backup.
  
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

Há duas maneiras de adicionar chaves a um Azure Key Vault; Você pode criar uma chave diretamente no compartimento de chaves ou pode importar uma chave. A criação de uma chave diretamente no cofre de chaves é o método menos complicado, enquanto a importação de uma chave fornece total controle sobre como a chave é gerada.
  
Para criar uma chave diretamente no seu cofre de chaves, execute o cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) da seguinte maneira:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Onde:

- *nome do cofre* é o nome do cofre de chaves no qual você deseja criar a chave.

- *nome da chave* é o nome que você deseja dar à nova chave.

  > [!TIP]
  > Chaves de nome usando uma Convenção de nomenclatura semelhante, conforme descrito acima para os principais cofres. Dessa forma, em ferramentas que mostram apenas o nome da chave, a cadeia de caracteres é autodescritivo.
  
- Se você pretende proteger a chave com um HSM, certifique-se de especificar o **HSM** como o valor do parâmetro _Destination_ , caso contrário, especifique **software**.

Por exemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Para importar uma chave diretamente para o seu cofre de chaves, você precisa ter um módulo de segurança de hardware do nCipher nShield.
  
Algumas organizações preferem essa abordagem para estabelecer o comprovante de suas chaves e, em seguida, este método também fornece o seguinte:
  
- O conjunto de ferramentas usado para importação inclui atestado de nCipher que a chave de troca de chave (KEK) que é usada para criptografar a chave gerada não é exportável e é gerada dentro de um HSM autêntico que foi fabricado pela nCipher.

- O conjunto de ferramentas inclui atestado do nCipher que o mundo de segurança do Azure Key Vault também foi gerado em um HSM autêntico fabricado pela nCipher. Esse atestado comprova que a Microsoft também está usando o hardware genuíno nCipher.

Verifique com o grupo de segurança para determinar se os atestado acima são necessários. Para obter etapas detalhadas para criar uma chave no local e importá-la para o seu cofre de chaves, consulte [como gerar e transferir chaves protegidas por HSM para o Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use as instruções do Azure para criar uma chave em cada cofre de chaves.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Verificar o nível de recuperação de suas chaves

A Microsoft 365 exige que a assinatura do Azure Key Vault esteja definida como não cancelar e que as chaves usadas pela chave do cliente tenham a exclusão reversível habilitada. Você pode confirmar isso examinando o nível de recuperação nas chaves.
  
Para verificar o nível de recuperação de uma chave, no PowerShell do Azure, execute o cmdlet Get-AzKeyVaultKey da seguinte maneira:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se a propriedade de _nível de recuperação_ retornar algo diferente de um valor de **recuperável + ProtectedSubscription**, você precisará revisar este tópico e certificar-se de que você seguiu todas as etapas para colocar a assinatura na lista não cancelar e que você tenha a exclusão reversível habilitada em cada um dos seus compartimentos de chave.
  
### <a name="back-up-azure-key-vault"></a>Fazer backup do Azure Key Vault

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, tanto online quanto offline. As cópias offline não devem ser conectadas a qualquer rede, como em uma instalação física segura ou de armazenamento comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que será acessível em caso de desastre. Os blobs de backup são o único meio de restaurar o material chave caso uma chave de compartimento de chave seja permanentemente destruída ou não seja processada. As chaves que são externas para o Azure Key Vault e foram importadas para o Azure Key Vault não se qualificam como um backup porque os metadados necessários para a chave do cliente usar a chave não existem com a chave externa. Somente um backup obtido do Azure Key Vault pode ser usado para operações de restauração com a chave do cliente. Portanto, é essencial que um backup do Azure Key Vault seja feito depois que uma chave é carregada ou criada.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) da seguinte maneira:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verifique se o arquivo de saída usa o sufixo `.backup` .
  
O arquivo de saída resultante deste cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup pode ser restaurado somente para a assinatura do Azure a partir da qual o backup foi feito.
  
> [!TIP]
> Para o arquivo de saída, escolha uma combinação de nome de cofre e nome de chave. Isso fará com que o nome do arquivo seja autodescritivo. Também garantirá que os nomes de arquivo de backup não colidem.
  
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

Na saída, procure a política de acesso e a identidade do Exchange Online (GUID) ou a identidade do SharePoint Online (GUID), conforme apropriado. Todas as três das permissões acima devem ser mostradas em permissões para chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzKeyVaultAccessPolicy da seguinte maneira:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por exemplo, para o Exchange Online e o Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por exemplo, para o SharePoint Online e o OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Para verificar se uma data de vencimento não está definida para suas chaves, execute o cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte maneira:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Uma chave expirada não pode ser usada pela chave do cliente e as operações tentadas com uma chave expirada falharão e possivelmente resultarão em uma interrupção de serviço. É altamente recomendável que as teclas usadas com a chave do cliente não tenham uma data de validade. Uma data de vencimento, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se for necessário usar uma chave que tenha uma data de expiração definida, altere o valor de expiração para 12/31/9999. As chaves com uma data de expiração definida para uma data diferente de 12/31/9999 não passarão pela validação 365 da Microsoft.
  
Para alterar uma data de expiração que tenha sido definida para qualquer valor diferente de 12/31/9999, execute o cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) da seguinte maneira:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Não defina datas de expiração em chaves de criptografia usadas com a chave do cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obter o URI para cada chave do Azure Key Vault

Após concluir todas as etapas no Azure para configurar seus principais cofres e adicionar suas chaves, execute o comando a seguir para obter o URI da chave em cada cofre de chaves. Você precisará usar esses URIs ao criar e atribuir cada DEP mais tarde, portanto, salve essas informações em um local seguro. Lembre-se de executar este comando uma vez para cada cofre de chaves.
  
No Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: configuração da chave do cliente para o Exchange Online e o Skype for Business

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Veja [tarefas completas no Azure Key Vault e Microsoft FastTrack para](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) obter informações sobre a chave do cliente.
  
Para configurar a chave do cliente para o Exchange Online e o Skype for Business, você precisará executar estas etapas conectando-se remotamente ao Exchange Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Criar uma DEP (política de criptografia de dados) para uso com o Exchange Online e o Skype for Business

Uma DEP é associada a um conjunto de chaves armazenadas no Azure Key Vault. Você atribui uma DEP a uma caixa de correio no Microsoft 365. O Microsoft 365 usará as chaves identificadas na política para criptografar a caixa de correio. Para criar a DEP, você precisará dos URIs de compartimento de chave obtidos anteriormente. Consulte [obter o URI de cada chave do Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key) para obter instruções.
  
Esquecer! Ao criar uma DEP, você especifica duas chaves que residem em dois cofres de chaves diferentes do Azure. Verifique se essas chaves estão localizadas em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar a DEP, siga estas etapas:
  
1. No computador local, usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) abrindo o Windows PowerShell e executando o seguinte comando.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Na caixa de diálogo solicitação de credencial do Windows PowerShell, insira as informações da conta corporativa ou de estudante, clique em **OK**e, em seguida, insira o comando a seguir.

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Execute o seguinte comando.

   ```powershell
   Import-PSSession $Session
   ```

4. Para criar uma DEP, use o cmdlet New-DataEncryptionPolicy digitando o comando a seguir.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Onde:

   - *PolicyName* é o nome que você deseja usar para a política. Os nomes não podem conter espaços. Por exemplo, USA_mailboxes.

   - *Descrição da política* é uma descrição amigável da política que ajudará você a se lembrar da política para o. Você pode incluir espaços na descrição. Por exemplo, "chave raiz para caixas de correio nos EUA e seus territórios".

   - *KeyVaultURI1* é o URI da primeira chave na política. Por exemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   - *KeyVaultURI2* é o URI da segunda chave na política. Por exemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe os dois URIs por uma vírgula e um espaço.

   Exemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Atribuir uma DEP a uma caixa de correio

Atribua a DEP a uma caixa de correio usando o cmdlet Set-Mailbox. Depois de atribuir a política, o Microsoft 365 pode criptografar a caixa de correio com a chave designada no DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailboxIdParameter* especifica uma caixa de correio. Para obter mais informações sobre o cmdlet Set-Mailbox, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Para [caixas de correio locais usando o Outlook para IOS e Android com a autenticação moderna híbrida](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth), os dados de caixa de correio local sincronizados em seu locatário do Exchange Online podem ter a DEP atribuída usando o cmdlet Set-MailUser. 

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailUserIdParameter* especifica um usuário de email (também conhecido como usuário habilitado para email). Para obter mais informações sobre o cmdlet Set-MailUser, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).
  
### <a name="validate-mailbox-encryption"></a>Validar criptografia de caixa de correio

Criptografar uma caixa de correio pode levar algum tempo. Para a primeira atribuição de política de tempo, a caixa de correio também deve se mover completamente de um banco de dados para outro antes que o serviço possa criptografar a caixa de correio. Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia após alterar uma DEP ou a primeira vez em que você atribui uma DEP a uma caixa de correio.
  
Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A Propriedade IsEncrypted retornará um valor **true** se a caixa de correio for criptografada e um valor **false** se a caixa de correio não estiver criptografada.

O tempo para concluir movimentações de caixa de correio depende do número de caixas de correio às quais você atribui uma DEP pela primeira vez, bem como o tamanho das caixas de correio. Se as caixas de correio não tiverem sido criptografadas após uma semana a partir do momento em que você atribuiu a DEP, entre em contato com a Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: configuração da chave do cliente para o SharePoint Online, o OneDrive for Business e os arquivos do teams

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Veja [tarefas completas no Azure Key Vault e Microsoft FastTrack para](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) obter informações sobre a chave do cliente.
  
Para configurar a chave do cliente para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, você precisará executar estas etapas conectando-se remotamente ao SharePoint Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do OneDrive for Business

Você associa um DEP com um conjunto de chaves armazenadas no Azure Key Vault. Você aplica uma DEP a todos os seus dados em um local geográfico, também chamado de uma geografia. Se você usar o recurso multigeográfico do Office 365, poderá criar uma DEP por geografia com a capacidade de usar chaves diferentes por Geo. Se você não estiver usando a geografia, poderá criar uma DEP em sua organização para uso com o SharePoint Online, o OneDrive for Business e os arquivos do teams. A Microsoft 365 usa as chaves identificadas na DEP para criptografar seus dados nessa geografia. Para criar a DEP, você precisará dos URIs de compartimento de chave obtidos anteriormente. Consulte [obter o URI de cada chave do Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key) para obter instruções.
  
Esquecer! Ao criar uma DEP, você especifica duas chaves que residem em dois cofres de chaves diferentes do Azure. Verifique se essas chaves estão localizadas em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar uma DEP, você precisa se conectar remotamente ao SharePoint online usando o Windows PowerShell.
  
1. No computador local, usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. No Shell de gerenciamento do Microsoft SharePoint Online, execute o cmdlet Register-SPODataEncryptionPolicy da seguinte maneira:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Quando você registra a DEP, a criptografia começa nos dados na geografia. Isso pode levar algum tempo.

### <a name="validate-file-encryption"></a>Validar a criptografia de arquivo

 Para validar a criptografia de arquivos do SharePoint Online, do OneDrive for Business e do Teams, [Conecte-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)e use o cmdlet Get-SPODataEncryptionPolicy para verificar o status do seu locatário. A propriedade _State_ retornará um valor **registrado** se a criptografia de chave do cliente estiver habilitada e todos os arquivos em todos os sites tiverem sido criptografados. Se a criptografia ainda estiver em andamento, este cmdlet fornecerá informações sobre a porcentagem de sites concluído.

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia de serviço com a chave do cliente](customer-key-overview.md)

- [Gerenciar chave do cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Criptografia de serviço](office-365-service-encryption.md)
