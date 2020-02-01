---
title: Controlar seus dados no Office 365 usando a Chave do Cliente
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
- SPO_Content
description: Saiba como configurar a chave do cliente para o Office 365 para Exchange Online, Skype for Business, SharePoint Online e OneDrive for Business. Com a chave do cliente, você controla as chaves de criptografia da sua organização e, em seguida, configura o Office 365 para usá-las para criptografar seus dados em repouso nos datacenters da Microsoft.
ms.openlocfilehash: 6d8673443fd08edfbe6d9f8b320429a6424d2a30
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595688"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>Controlar seus dados no Office 365 usando a Chave do Cliente

Com a chave do cliente, você controla as chaves de criptografia da sua organização e, em seguida, configura o Office 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft. Em outras palavras, a chave do cliente permite que os clientes adicionem uma camada de criptografia que pertença a eles, com suas chaves. Os dados em repouso incluem dados do Exchange Online e do Skype for Business que são armazenados em caixas de correio e arquivos armazenados no SharePoint Online e no OneDrive for Business.

Você deve configurar o Azure antes de poder usar a chave do cliente para o Office 365. Este tópico descreve as etapas que você precisa seguir para criar e configurar os recursos do Azure necessários e, em seguida, fornece as etapas para configurar a chave do cliente no Office 365. Depois de concluir a instalação do Azure, determine a política e, portanto, quais teclas serão atribuídas a caixas de correio e arquivos em sua organização. Caixas de correio e arquivos para os quais você não atribui uma política usarão políticas de criptografia controladas e gerenciadas pela Microsoft. Para obter mais informações sobre a chave do cliente ou para uma visão geral, consulte a [chave do cliente para perguntas frequentes sobre o Office 365](service-encryption-with-customer-key-faq.md).
  
> [!IMPORTANT]
> É altamente recomendável seguir as práticas recomendadas neste tópico. Eles são chamados de **Tip** e **importante**. A chave do cliente dá controle sobre as chaves de criptografia raiz cujo escopo pode ser tão grande quanto sua organização inteira. Isso significa que os erros feitos com essas chaves podem ter um impacto amplo e podem resultar em interrupções de serviço ou perda irrevogável dos dados.
  
## <a name="before-you-begin-setting-up-customer-key"></a>Antes de começar a configurar a chave do cliente
<a name="Beforeyoustart"> </a>

Antes de começar, verifique se você tem o licenciamento apropriado para sua organização. A chave do cliente no Office 365 é oferecida no Office 365 E5 ou no SKU de conformidade avançada.
  
Em seguida, para entender os conceitos e procedimentos deste tópico, você deve revisar a documentação do [Azure Key Vault](https://azure.microsoft.com/documentation/services/key-vault/) . Além disso, familiarize-se com os termos usados no Azure, por exemplo, [locatário](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).
  
Para fornecer comentários sobre a chave do cliente, incluindo a documentação, envie suas ideias, sugestões e perspectivas para o customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>Visão geral da configuração da chave do cliente para o Office 365
<a name="Overview"> </a>

Para configurar a chave do cliente, você concluirá essas tarefas. O restante deste tópico fornece instruções detalhadas para cada tarefa ou links para mais informações de cada etapa do processo.
  
**No Azure e no Microsoft FastTrack:**
  
Você concluirá a maioria dessas tarefas, conectando-se remotamente ao Azure PowerShell. Para obter melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.
  
- [Criar duas novas assinaturas do Azure](controlling-your-data-using-customer-key.md#Create2newsubs)

- [Registrar assinaturas do Azure para usar um período de retenção obrigatório](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)

    O registro pode levar de um a cinco dias úteis.

- [Enviar uma solicitação para ativar a chave do cliente para o Office 365](controlling-your-data-using-customer-key.md#FastTrack)

    Depois de criar as duas novas assinaturas do Azure, você precisará enviar a solicitação de oferta de chave do cliente apropriada, concluindo um formulário da Web hospedado no portal Microsoft FastTrack. **A equipe do FastTrack não fornece assistência com a chave do cliente. O Office simplesmente usa o portal do FastTrack para permitir que você envie o formulário e ajude-nos a acompanhar as ofertas relevantes para a chave do cliente**.
  
Depois de enviar uma oferta de chave do cliente, a Microsoft revisa sua solicitação e notifica você quando você pode prosseguir com o restante das tarefas de configuração. Esse processo pode levar até cinco dias úteis.

- [Criar um cofre de chaves Premium do Azure em cada assinatura](controlling-your-data-using-customer-key.md#CreateKeyVault)

- [Atribuir permissões a cada cofre de chaves](controlling-your-data-using-customer-key.md#KeyVaultPerms)

- [Habilitar e confirmar a exclusão reversível nos seus principais cofres](controlling-your-data-using-customer-key.md#SoftDelete)

- [Adicionar uma chave a cada cofre de chaves criando ou importando uma chave](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)

- [Verificar o nível de recuperação de suas chaves](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)

- [Backup do Azure Key Vault](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)

- [Validar definições de configuração do Azure Key Vault](controlling-your-data-using-customer-key.md#Validateconfiguration)

- [Obter o URI para cada chave do Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI)

**No Office 365:**
  
Exchange Online e Skype for Business:
  
- [Criar uma DEP (política de criptografia de dados) para uso com o Exchange Online e o Skype for Business](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [Atribuir uma DEP a uma caixa de correio](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [Validar criptografia de caixa de correio](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online e OneDrive for Business:
  
- [Criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do OneDrive for Business](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [Validar a criptografia de sites de grupo, sites de equipe e o OneDrive for Business](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Concluir tarefas no Azure Key Vault e no Microsoft FastTrack para chave do cliente
<a name="AzureSteps"> </a>

Conclua essas tarefas no Azure Key Vault para configurar a chave do cliente para o Office 365. Você precisará concluir essas etapas, independentemente se pretende configurar a chave do cliente para o Exchange Online e o Skype for Business ou o SharePoint Online e o OneDrive for Business ou para todos os serviços com suporte no Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure
<a name="Create2newsubs"> </a>

Duas assinaturas do Azure são necessárias para a chave do cliente. Como prática recomendada, a Microsoft recomenda que você crie novas assinaturas do Azure para uso com a chave do cliente. Chaves do Azure Key Vault só podem ser autorizadas para aplicativos no mesmo locatário do Azure Active Directory (AAD), você deve criar as novas assinaturas usando o mesmo locatário do Azure AD usado com sua organização do Office 365, onde o DEPs será atribuído. Por exemplo, usando sua conta corporativa ou de estudante que tenha privilégios de administrador global em sua organização do Office 365. Para obter etapas detalhadas, consulte [inscrever-se no Azure como uma organização](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> A chave do cliente requer duas chaves para cada DEP (política de criptografia de dados). Para conseguir isso, você deve criar duas assinaturas do Azure. Como prática recomendada, a Microsoft recomenda que você tenha Membros separados da sua organização para configurar uma chave em cada assinatura. Além disso, essas assinaturas do Azure devem ser usadas apenas para administrar chaves de criptografia para o Office 365. Isso protegerá a sua organização caso um de seus operadores acidentalmente, intencionalmente ou exclua inadvertidamente as chaves para as quais são responsáveis. <br/> Recomendamos que você configure novas assinaturas do Azure que são usadas unicamente para o gerenciamento de recursos do Azure Key Vault para uso com a chave do cliente. Não há um limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir estas práticas recomendadas minimizará o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela chave do cliente. 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar uma solicitação para ativar a chave do cliente para o Office 365
<a name="FastTrack"> </a>

Depois de concluir as etapas do Azure, você precisará enviar uma solicitação de oferta no [portal Microsoft FastTrack](https://fasttrack.microsoft.com/). Depois de enviar uma solicitação pelo portal da Web do FastTrack, a Microsoft verifica os dados de configuração e informações de contato do Azure Key Vault que você forneceu. As seleções feitas no formulário de oferta em relação aos responsáveis autorizados da sua organização são fundamentais e necessárias para a conclusão do registro de chave do cliente. Os gerentes da sua organização selecionados no formulário serão usados para garantir a autenticidade de qualquer solicitação de revogação e destruição de todas as chaves usadas com uma política de criptografia de dados de chave do cliente. Você precisará fazer esta etapa uma vez para ativar a chave do cliente para o Exchange Online e a cobertura do Skype for Business e uma segunda vez para ativar a chave do cliente para o SharePoint Online e o OneDrive for Business.
  
Para enviar uma oferta para ativar a chave do cliente, conclua estas etapas:
  
1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, faça logon no [portal do Microsoft FastTrack](https://fasttrack.microsoft.com/).
    
2. Quando estiver conectado, navegue até o **painel**.
    
3. Escolha **ofertas**e revise a lista de ofertas atuais.
    
4. Escolha **saiba mais** para a oferta que se aplica a você: 
    
  - **Exchange Online e Skype for Business:** Escolha **saiba mais** sobre a **chave do cliente para a oferta do Exchange** . 
    
  - **SharePoint Online e onedrive for Business:** Escolhido **saiba mais** sobre a **chave do cliente para o SharePoint e o onedrive for Business** offer. 
    
5. Na página **detalhes da oferta** , escolha **criar solicitação**.
    
6. Preencha todos os detalhes aplicáveis e as informações solicitadas sobre o formulário de oferta. Preste bastante atenção às suas seleções para quais responsáveis da sua organização você deseja autorizar a aprovar a destruição permanente e irreversível de chaves e dados de criptografia. Depois de concluir o formulário, escolha **Enviar**.
    
    Esse processo pode levar até cinco dias úteis quando a Microsoft for notificada de sua solicitação.
    
7. Continue na seção período de retenção obrigatório abaixo.
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório
<a name="RegisterSubsforMRP"> </a>

A perda temporária ou permanente das chaves de criptografia raiz pode ser muito prejudicial ou até mesmo uma operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a chave do cliente exigem uma forte proteção. Todos os recursos do Azure usados com os mecanismos de proteção da oferta de chave do cliente além da configuração padrão. As assinaturas do Azure podem ser marcadas ou registradas de uma maneira que impedirá o cancelamento imediato e irrevogável. Isso é conhecido como registro em um período de retenção obrigatório. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a equipe do Office 365. Esse processo pode levar de um a cinco dias úteis. Anteriormente, isso também era conhecido como "não cancelar".
  
Antes de entrar em contato com a equipe do Office 365, você deve executar as seguintes etapas para cada assinatura do Azure que você usa com a chave do cliente:
  
1. Faça logon em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, consulte [fazer logon com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
2. Execute o cmdlet Register-AzureRmProviderFeature para registrar suas assinaturas para usar um período de retenção obrigatório.
    
  ```powershell
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. Entre em contato com a Microsoft para finalizar o processo. Para a equipe do SharePoint e do OneDrive for Business, entre em contato com [Spock@microsoft.com](mailto:spock@microsoft.com). Para o Exchange Online e o Skype for Business, entre em contato com a [exock@microsoft.com](mailto:exock@microsoft.com). O contrato de nível de serviço (SLA) para a conclusão desse processo é de cinco dias úteis quando a Microsoft é notificada (e verificada) que você registrou suas assinaturas para usar um período de retenção obrigatório. Inclua o seguinte em seu email:
    
    **Subject**: chave de cliente \<para *o nome de domínio totalmente qualificado do seu locatário*\> 
    
    **Corpo**: IDs de assinatura para as quais você deseja que o período de retenção obrigatório seja concluído. 
    
4. Depois que você receber uma notificação da Microsoft de que o registro foi concluído, verifique o status do seu registro executando o cmdlet Get-AzureRmProviderFeature da seguinte maneira:
    
  ```powershell
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. Depois de verificar se a propriedade de **estado de registro** do cmdlet Get-AzureRmProviderFeature retorna um valor de **Registered**, execute o seguinte comando para concluir o processo:
    
  ```powershell
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Criar um cofre de chaves Premium do Azure em cada assinatura
<a name="CreateKeyVault"> </a>

As etapas para criar um cofre de chaves são documentadas na [introdução ao Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que orienta você durante a instalação e inicialização do Azure PowerShell, conexão com sua assinatura do Azure, criação de um grupo de recursos e criação de um cofre de chaves nesse grupo de recursos.
  
Ao criar um cofre de chaves, você deve escolher um SKU: Standard ou Premium. A SKU padrão permite que as chaves do Azure Key Vault sejam protegidas por software – não há nenhuma proteção de chave do módulo de segurança de hardware (HSM), e a SKU Premium permite o uso de HSMs para proteção de chaves de compartimento de chaves. A chave do cliente aceita os principais cofres que usam SKU, embora a Microsoft recomende enfaticamente que você use apenas o SKU Premium. O custo das operações com chaves de qualquer tipo é o mesmo, portanto, a única diferença no custo é o custo por mês para cada chave protegida por HSM. Confira os [preços do Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obter detalhes. 
  
> [!IMPORTANT]
> Use os compartimentos de chave de SKU Premium e chaves protegidas por HSM para dados de produção e use somente os compartimentos de chave de SKU padrão e chaves para fins de teste e validação. 
  
Para cada serviço do Office 365 com o qual você usará a chave do cliente, crie um cofre de chaves em cada uma das duas assinaturas do Azure que você criou. Por exemplo, apenas para o Exchange Online e o Skype for Business, somente para o SharePoint Online e o OneDrive for Business, você irá criar apenas um par de cofres. Para habilitar a chave do cliente para o Exchange Online e o SharePoint Online, você irá criar dois pares de cofres de chaves.
  
Use uma Convenção de nomenclatura para os principais cofres que reflitam o uso pretendido da DEP com a qual você irá associar os cofres. Consulte a seção práticas recomendadas abaixo para obter recomendações de Convenção de nomenclatura.
  
Crie um conjunto separado e emparelhado de cofres para cada política de criptografia de dados. Para o Exchange Online, o escopo de uma política de criptografia de dados é escolhido quando você atribui a política à caixa de correio. Uma caixa de correio pode ter apenas uma política atribuída, e você pode criar até 50 políticas. Para o SharePoint Online, o escopo de uma política é todos os dados dentro de uma organização em um local geográfico ou Geo.
  
A criação de compartimentos de chave também requer a criação de grupos de recursos do Azure, pois os principais cofres precisam de capacidade de armazenamento (embora muito pequeno) e do registro em log de compartimento de chaves, se habilitado, também gera dados armazenados. Como prática recomendada, a Microsoft recomenda o uso de administradores separados para gerenciar cada grupo de recursos, com a administração centralizada com o conjunto de administradores que gerenciará todos os recursos de chave do cliente relacionados.
  
> [!IMPORTANT]
> Para maximizar a disponibilidade, seus cofres de chaves devem estar próximos às regiões do serviço do Office 365. Por exemplo, se sua organização do Exchange Online estiver na América do Norte, coloque seus principais cofres na América do Norte. Se sua organização do Exchange Online estiver na Europa, coloque seus principais cofres na Europa.<br/>Use um prefixo comum para os principais compartimentos e inclua uma abreviação do uso e do escopo do compartimento de chaves e chaves (por exemplo, para o serviço do SharePoint da Contoso onde os cofres estarão localizados na América do Norte, um possível par de nomes é contoso-O365SP-NÃODISP-VaultA1 e Contoso-O365SP-NA-VaultA2. Os nomes de cofre são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez você precise tentar variações dos nomes desejados, caso os nomes desejados já sejam reivindicados por outros clientes do Azure. Os nomes de cofre de julho de 2017 não podem ser alterados, portanto, uma prática recomendada é ter um plano escrito para configuração e usar uma segunda pessoa para verificar se o plano foi executado corretamente.<br/>Se possível, crie seus cofres em regiões não emparelhadas. As regiões emparelhadas do Azure fornecem alta disponibilidade entre domínios de falha de serviço. Portanto, os pares regionais podem ser considerados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região é automaticamente obter tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma DEP onde as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade está em uso. A maioria dos geografias tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma DEP. Isso beneficia de um total de quatro regiões de disponibilidade. Para obter mais informações, consulte [continuidade de negócios e recuperação de desastres (BCDR): regiões emparelhadas do Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para uma lista atual de pares regionais. 
  
### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves
<a name="KeyVaultPerms"> </a>

Para cada cofre de chave, você precisará definir três conjuntos separados de permissões para a chave do cliente, dependendo da sua implementação. Por exemplo, você precisará definir um conjunto de permissões para cada um dos seguintes:
  
- **Administradores de compartimentos de chaves** que realizarão o gerenciamento diário de seu cofre de chaves para sua organização. Essas tarefas incluem backup, criar, obter, importar, listar e restaurar. 
    
    > [!IMPORTANT]
    > O conjunto de permissões atribuídas aos administradores de compartimento de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. Excluir chaves de criptografia normalmente não é feito, pois fazer isso permanentemente destrói os dados. Como prática recomendada, não conceda essa permissão a administradores de compartimento de chave por padrão. Em vez disso, Reserve-a para os colaboradores de Key Vault e apenas atribua-o a um administrador a curto prazo quando uma compreensão clara das conseqüências é entendida. 
  
    Para atribuir essas permissões a um usuário na sua organização do Office 365, faça logon em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, consulte [fazer logon com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).
    
- Execute o cmdlet Set-AzureRmKeyVaultAccessPolicy para atribuir as permissões necessárias.
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  Por exemplo:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- Os **principais colaboradores do cofre** que podem alterar as permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários saírem ou ingressarem em sua equipe ou na situação extremamente rara que os administradores de cofre de chaves precisam de permissão legítima para excluir ou restaurar uma chave. Esse conjunto de colaboradores de compartimento de chave precisa ter a função de **colaborador** no seu cofre de chaves. Você pode atribuir essa função usando o Azure Resource Manager. Para obter etapas detalhadas, consulte [use Role-Based Access Control para gerenciar o acesso aos seus recursos de assinatura do Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). O administrador que cria uma assinatura tem esse acesso implicitamente, bem como a capacidade de atribuir outros administradores à função colaborador.
    
- Se você pretende usar a chave do cliente com o Exchange Online e o Skype for Business, precisará conceder permissão ao Office 365 para usar o cofre de chaves em nome do Exchange Online e do Skype for Business. Da mesma forma, se você pretende usar a chave do cliente com o SharePoint Online e o OneDrive for Business, precisará adicionar permissão para o Office 365 para usar o cofre de chaves em nome do SharePoint Online e do OneDrive for Business. Para dar permissão ao Office 365, execute o cmdlet **set-AzureRmKeyVaultAccessPolicy** usando a seguinte sintaxe: 
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    Onde:
    
  - *vaultname* é o nome do cofre de chaves que você criou. 
    
  - Para o Exchange Online e o Skype for Business, substitua o *Office 365 AppID* por`00000002-0000-0ff1-ce00-000000000000`
    
  - Para o SharePoint Online e o OneDrive for Business, substitua o *Office 365 AppID* por`00000003-0000-0ff1-ce00-000000000000`
    
  Exemplo: definir permissões para o Exchange Online e o Skype for Business:
    
  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  Exemplo: definindo permissões para o SharePoint Online e o OneDrive for Business

  ```powershell
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar e confirmar a exclusão reversível nos seus principais cofres
<a name="SoftDelete"> </a>

Quando você pode recuperar rapidamente suas chaves, é menos provável que haja uma interrupção de serviço estendido devido a chaves acidentalmente ou excluídas de forma mal-intencionada. Você precisa habilitar essa configuração, conhecida como exclusão reversível, antes de poder usar suas chaves com a chave do cliente. Habilitar a exclusão reversível permite recuperar chaves ou cofres dentro de 90 dias de exclusão sem precisar restaurá-los do backup.
  
Para habilitar a exclusão reversível nos seus cofres de chaves, conclua estas etapas:
  
1. Faça logon em sua assinatura do Azure com o Windows PowerShell. Para obter instruções, consulte [fazer logon com o Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Execute o cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . Neste exemplo, o *cofre* é o nome do cofre de chaves para o qual você está habilitando a exclusão reversível: 

   ```powershell
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirmar se a exclusão reversível está configurada para o cofre de chaves executando o cmdlet **Get-AzureRmKeyVault** . Se a exclusão reversível estiver configurada corretamente para o cofre de chaves, a exclusão reversível será habilitada? Propriedade retorna um valor **true**: 

   ```powershell
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Adicionar uma chave a cada cofre de chaves criando ou importando uma chave
<a name="AddKeystoKeyVault"> </a>

Há duas maneiras de adicionar chaves a um Azure Key Vault; Você pode criar uma chave diretamente no compartimento de chaves ou pode importar uma chave. A criação de uma chave diretamente no cofre de chaves é o método menos complicado, enquanto a importação de uma chave fornece total controle sobre como a chave é gerada.
  
Para criar uma chave diretamente no seu cofre de chaves, execute o cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) da seguinte maneira: 
  
```powershell
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Onde:
  
- *compartimentalizaname* é o nome do cofre de chaves em que você deseja criar a chave.

- *KeyName* é o nome que você deseja dar à nova chave.

    > [!TIP]
    > Chaves de nome usando uma Convenção de nomenclatura semelhante, conforme descrito acima para os principais cofres. Dessa forma, em ferramentas que mostram apenas o nome da chave, a cadeia de caracteres é autodescritivo. 
  
- Se você pretende proteger a chave com um HSM, certifique-se de especificar o **HSM** como o valor do parâmetro _Destination_ , caso contrário, especifique **software**.

Por exemplo,
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Para importar uma chave diretamente para o seu cofre de chaves, você precisa ter um módulo de segurança de hardware do Thales nShield.
  
Algumas organizações preferem essa abordagem para estabelecer o comprovante de suas chaves, e o método também fornece o seguinte:
  
- O conjunto de ferramentas usado para importação inclui atestado de Thales que a chave de troca de chave (KEK) que é usada para criptografar a chave gerada não é exportável e é gerada dentro de um HSM autêntico que foi fabricado pela Thales.

- O conjunto de ferramentas inclui atestado do Thales que o mundo de segurança do Azure Key Vault também foi gerado em um HSM autêntico fabricado pela Thales. Esse atestado comprova que a Microsoft também está usando o hardware genuíno Thales.

Verifique com o grupo de segurança para determinar se os atestado acima são necessários. Para obter etapas detalhadas para criar uma chave no local e importá-la para o seu cofre de chaves, consulte [como gerar e transferir chaves protegidas por HSM para o Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use as instruções do Azure para criar uma chave em cada cofre de chaves.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Verificar o nível de recuperação de suas chaves
<a name="CheckKeyRecoveryLevel"> </a>

O Office 365 requer que a assinatura do Azure Key Vault esteja definida como não cancelar e que as chaves usadas pela chave do cliente tenham a exclusão reversível habilitada. Você pode confirmar isso examinando o nível de recuperação nas chaves.
  
Para verificar o nível de recuperação de uma chave, no PowerShell do Azure, execute o cmdlet Get-AzureKeyVaultKey da seguinte maneira:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes
```

Se a propriedade de _nível de recuperação_ retornar algo diferente de um valor de **recuperável + ProtectedSubscription**, você precisará revisar este tópico e certificar-se de que você seguiu todas as etapas para colocar a assinatura na lista não cancelar e que você tenha a exclusão reversível habilitada em cada um dos seus compartimentos de chave.
  
### <a name="backup-azure-key-vault"></a>Backup do Azure Key Vault
<a name="BackupAzureKeyVaultkeys"> </a>

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, tanto online quanto offline. As cópias offline não devem ser conectadas a qualquer rede, como em uma instalação física segura ou de armazenamento comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que será acessível em caso de desastre. Os blobs de backup são o único meio de restaurar o material chave caso uma chave de compartimento de chave seja permanentemente destruída ou não seja processada. As chaves que são externas para o Azure Key Vault e foram importadas para o Azure Key Vault não se qualificam como um backup porque os metadados necessários para a chave do cliente usar a chave não existem com a chave externa. Somente um backup obtido do Azure Key Vault pode ser usado para operações de restauração com a chave do cliente. Portanto, é essencial que um backup do Azure Key Vault seja feito depois que uma chave é carregada ou criada.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) da seguinte maneira:

```powershell
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>
-OutputFile <filename .backup>
```

Verifique se o arquivo de saída usa o `.backup`sufixo.
  
O arquivo de saída resultante deste cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup pode ser restaurado somente para a assinatura do Azure a partir da qual o backup foi feito.
  
> [!TIP]
> Para o arquivo de saída, escolha uma combinação de nome de cofre e nome de chave. Isso fará com que o nome do arquivo seja autodescritivo. Também garantirá que os nomes de arquivo de backup não colidem.
  
Por exemplo:
  
```powershell
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar definições de configuração do Azure Key Vault
<a name="Validateconfiguration"> </a>

Executar a validação antes de usar chaves em uma DEP é opcional, mas altamente recomendado. Em particular, se você usar as etapas para configurar suas chaves e cofres diferentes dos descritos neste tópico, você deve validar a integridade dos recursos do Azure Key Vault antes de configurar a chave do cliente.
  
Para verificar se as chaves têm as operações Get, wrapKey e unwrapKey habilitadas:
  
Execute o cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) da seguinte maneira:
  
```powershell
Get-AzureRMKeyVault -VaultName <vaultname>
```

Na saída, procure a política de acesso e a identidade do Exchange Online (GUID) ou a identidade do SharePoint Online (GUID), conforme apropriado. Todas as três das permissões acima devem ser mostradas em permissões para chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzureRmKeyVaultAccessPolicy da seguinte maneira:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por exemplo, para o Exchange Online e o Skype for Business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por exemplo, para o SharePoint Online e o OneDrive for Business:
  
```powershell
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Para verificar se uma data de vencimento não está definida para suas chaves, execute o cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) da seguinte maneira:
  
```powershell
Get-AzureKeyVaultKey -VaultName <vaultname>
```

Uma chave expirada não pode ser usada pela chave do cliente e as operações tentadas com uma chave expirada falharão e possivelmente resultarão em uma interrupção de serviço. É altamente recomendável que as teclas usadas com a chave do cliente não tenham uma data de validade. Uma data de vencimento, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se for necessário usar uma chave que tenha uma data de expiração definida, altere o valor de expiração para 12/31/9999. As chaves com uma data de expiração definida para uma data diferente de 12/31/9999 não passarão pela validação do Office 365.
  
Para alterar uma data de expiração que tenha sido definida para qualquer valor diferente de 12/31/9999, execute o cmdlet [set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) da seguinte maneira:
  
```powershell
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Não defina datas de expiração em chaves de criptografia usadas com a chave do cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obter o URI para cada chave do Azure Key Vault
<a name="GetKeyURI"> </a>

Após concluir todas as etapas no Azure para configurar seus principais cofres e adicionar suas chaves, execute o comando a seguir para obter o URI da chave em cada cofre de chaves. Você precisará usar esses URIs ao criar e atribuir cada DEP mais tarde, portanto, salve essas informações em um local seguro. Lembre-se de executar este comando uma vez para cada cofre de chaves.
  
No Azure PowerShell:
  
```powershell
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: configuração da chave do cliente para o Exchange Online e o Skype for Business
<a name="AzureSteps"> </a>

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Veja [tarefas completas no Azure Key Vault e Microsoft FastTrack para](controlling-your-data-using-customer-key.md#AzureSteps) obter informações sobre a chave do cliente. 
  
Para configurar a chave do cliente para o Exchange Online e o Skype for Business, você precisará executar estas etapas conectando-se remotamente ao Exchange Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Criar uma DEP (política de criptografia de dados) para uso com o Exchange Online e o Skype for Business
<a name="CreateDEP4EXOSkype"> </a>

Uma DEP é associada a um conjunto de chaves armazenadas no Azure Key Vault. Você atribui uma DEP a uma caixa de correio no Office 365. O Office 365 usará as chaves identificadas na política para criptografar a caixa de correio. Para criar a DEP, você precisará dos URIs de compartimento de chave obtidos anteriormente. Consulte [obter o URI de cada chave do Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obter instruções.
  
Esquecer! Ao criar uma DEP, você especifica duas chaves que residem em dois cofres de chaves diferentes do Azure. Verifique se essas chaves estão localizadas em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar a DEP, siga estas etapas:
  
1. No computador local, usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, [Conecte-se ao PowerShell do Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx) abrindo o Windows PowerShell e executando o seguinte comando.

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
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Onde:

   -  *PolicyName* é o nome que você deseja usar para a política. Os nomes não podem conter espaços. Por exemplo, USA_mailboxes.

   -  *PolicyDescription* é uma descrição amigável da política que ajudará você a se lembrar do que a política é para o. Você pode incluir espaços na descrição. Por exemplo, chave raiz para caixas de correio nos EUA e seus territórios.

   -  *KeyVaultURI1* é o URI da primeira chave na política. Por exemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   -  *KeyVaultURI2* é o URI da segunda chave na política. Por exemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe os dois URIs por uma vírgula e um espaço.

   Exemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Atribuir uma DEP a uma caixa de correio
<a name="assignDEPtomailbox"> </a>

Atribua a DEP a uma caixa de correio usando o cmdlet Set-Mailbox. Depois de atribuir a política, o Office 365 pode criptografar a caixa de correio com a chave designada no DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailboxIdParameter* especifica uma caixa de correio. Para obter mais informações sobre o cmdlet Set-Mailbox, consulte [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).
  
### <a name="validate-mailbox-encryption"></a>Validar criptografia de caixa de correio
<a name="validatemailboxencryption"> </a>

Criptografar uma caixa de correio pode levar algum tempo. Para a primeira atribuição de política de tempo, a caixa de correio também deve concluir a movimentação de um banco de dados para outro antes que o serviço possa criptografar a caixa de correio. Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia após alterar uma DEP ou a primeira vez em que você atribui uma DEP a uma caixa de correio.
  
Use o cmdlet Get-MailboxStatistics para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A Propriedade IsEncrypted retornará um valor **true** se a caixa de correio for criptografada e um valor **false** se a caixa de correio não estiver criptografada. 

O tempo para concluir movimentações de caixa de correio depende do número de caixas de correio às quais você atribui uma DEP pela primeira vez, bem como o tamanho das caixas de correio. Se as caixas de correio não foram criptografadas após uma semana a partir do momento em que você atribuiu a DEP, inicie uma movimentação de caixa de correio para as caixas de correio não criptografadas usando o cmdlet New-MoveRequest.

```powershell
New-MoveRequest <mailbox alias>
```

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: configuração da chave do cliente para o SharePoint Online e o OneDrive for Business
<a name="AzureSteps"> </a>

Antes de começar, verifique se você concluiu as tarefas necessárias para configurar o Azure Key Vault. Veja [tarefas completas no Azure Key Vault e Microsoft FastTrack para](controlling-your-data-using-customer-key.md#AzureSteps) obter informações sobre a chave do cliente.
  
Para configurar a chave do cliente para o SharePoint Online e o OneDrive for Business, você precisará executar estas etapas conectando-se remotamente ao SharePoint Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Criar uma DEP (política de criptografia de dados) para cada Geografia do SharePoint Online e do OneDrive for Business
<a name="CreateDEP4SPOODfB"> </a>

Uma DEP é associada a um conjunto de chaves armazenadas no Azure Key Vault. Você aplica uma DEP a todos os seus dados em um local geográfico, também chamado de uma geografia. Se você usar o recurso multigeográfico do Office 365, poderá criar uma DEP por Geo. Se você não estiver usando a geografia, é possível criar uma DEP no Office 365 para uso com o SharePoint Online e o OneDrive for Business. O Office 365 usará as chaves identificadas na DEP para criptografar seus dados nessa geografia. Para criar a DEP, você precisará dos URIs de compartimento de chave obtidos anteriormente. Consulte [obter o URI de cada chave do Azure Key Vault](controlling-your-data-using-customer-key.md#GetKeyURI) para obter instruções. 
  
Esquecer! Ao criar uma DEP, você especifica duas chaves que residem em dois cofres de chaves diferentes do Azure. Verifique se essas chaves estão localizadas em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar uma DEP, você precisa se conectar remotamente ao SharePoint online usando o Windows PowerShell.
  
1. No computador local, usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, [Conecte-se ao PowerShell do SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx).

2. No Shell de gerenciamento do Microsoft SharePoint Online, execute o cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) da seguinte maneira:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Quando você registra a DEP, a criptografia começa nos dados na geografia. Isso pode levar algum tempo.

### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>Validar a criptografia de sites de grupo, sites de equipe e o OneDrive for Business
<a name="validateencryptionSPO"> </a>

Você pode verificar o status da criptografia executando o cmdlet Get-SPODataEncryptionPolicy da seguinte maneira:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

A saída deste cmdlet inclui:
  
- O URI da chave primária.

- O URI da chave secundária.

- O status de criptografia para a geografia. Os Estados possíveis incluem:

  - Não **registrado:** A criptografia de chave do cliente ainda não foi aplicada.

  - **Registro:** A criptografia da chave do cliente foi aplicada e seus arquivos estão em processo de criptografia. Se sua geografia estiver nesse estado, você também verá informações sobre a porcentagem de sites na geografia que podem ser concluídas para que você possa monitorar o andamento da criptografia.

  - **Registrado:** A criptografia da chave do cliente foi aplicada e todos os arquivos em todos os sites foram criptografados.

  - **Sem interrupção:** Um rolo de chave está em andamento. Se sua geografia estiver nesse estado, você também verá informações sobre a porcentagem de sites que concluíram a operação do registro principal para que você possa monitorar o progresso.

## <a name="managing-customer-key-for-office-365"></a>Gerenciando a chave do cliente para o Office 365
<a name="ManageCustomerKey"> </a>

Depois de configurar a chave do cliente para o Office 365, você pode executar essas tarefas de gerenciamento adicionais.
  
- [Restaurar chaves do Azure Key Vault](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)

- [Reverter ou girar uma chave no Azure Key Vault que você usa com a chave do cliente](controlling-your-data-using-customer-key.md#RollCKkey)

- [Gerenciar permissões do Key Vault](controlling-your-data-using-customer-key.md#Managekeyvaultperms)

- [Determinar a DEP atribuída a uma caixa de correio](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>Restaurar chaves do Azure Key Vault
<a name="RestoreAzureKeyVaultKeys"> </a>

Antes de executar uma restauração, use os recursos de recuperação fornecidos pela exclusão reversível. Todas as chaves usadas com a chave do cliente são necessárias para que a exclusão reversível seja habilitada. A exclusão reversível funciona como uma lixeira e permite a recuperação de até 90 dias sem a necessidade de restauração. A restauração deve ser necessária somente em circunstâncias extremas ou incomuns, por exemplo, se a chave ou o cofre de chaves for perdido. Se for necessário restaurar uma chave para uso com a chave do cliente, no PowerShell do Azure, execute o cmdlet Restore-AzureKeyVaultKey da seguinte maneira:
  
```powershell
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

Por exemplo:
  
```powershell
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Se já existir uma chave com o mesmo nome no cofre de chaves, a operação de restauração falhará. Restore-AzureKeyVaultKey restaura todas as versões de chave e todos os metadados da chave, incluindo o nome da chave.
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>Reverter ou girar uma chave no Azure Key Vault que você usa com a chave do cliente
<a name="RollCKkey"> </a>

As chaves sem interrupção não são exigidas pelo Azure Key Vault ou pela chave do cliente. Além disso, as chaves protegidas com um HSM são praticamente impossíveis de ser comprometidas. Mesmo que uma chave raiz estivesse na posse de um ator mal-intencionado, não há meios viáveis de usá-lo para descriptografar dados, já que apenas o código do Office 365 sabe como usá-lo. No entanto, a chave do cliente oferece suporte à substituição de uma chave.
  
> [!CAUTION]
> Apenas rolo uma chave de criptografia que você usa com a chave do cliente quando existe uma razão técnica clara ou um requisito de conformidade determina que você precisa rolar a chave. Além disso, não exclua chaves que estejam associadas a políticas. Ao rolar suas chaves, haverá conteúdo criptografado com as teclas anteriores. Por exemplo, enquanto as caixas de correio ativas forem criptografadas freqüentemente, inativas, desconectadas e desativadas, as caixas de correio ainda poderão ser criptografadas com as teclas anteriores. O SharePoint Online realiza o backup de conteúdo para fins de restauração e recuperação, para que ainda possa haver conteúdo arquivado usando chaves antigas. <br/> Para garantir a segurança de seus dados, o SharePoint Online permitirá que não haja mais de uma operação de registro de chave em andamento por vez. Se quiser rolar as duas chaves em um cofre de chaves, você precisará aguardar a conclusão completa da primeira operação do rolo de chave. Nossa recomendação é escalonar as operações de seu rolo principal em intervalos diferentes, para que isso não seja um problema.
  
Ao lançar uma chave, você está solicitando uma nova versão de uma chave existente. Para solicitar uma nova versão de uma chave existente, use o mesmo cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), com a mesma sintaxe que você usou para criar a chave no primeiro lugar.
  
Por exemplo:
  
```powershell
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

Neste exemplo, como uma chave chamada **contoso-O365EX-nd-VaultA1-Key001** já existe no cofre **contoso-O365EX-na-VaultA1** , uma nova versão de chave será criada. A operação adiciona uma nova versão de chave. Essa operação preserva as versões de chave anteriores no histórico de versão da chave, para que os dados anteriormente criptografados com essa chave ainda possam ser descriptografados. Depois de concluir a transferência de qualquer chave associada a uma DEP, você deve executar um cmdlet adicional para garantir que a chave do cliente comece a usar a nova chave.
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar o Exchange Online e o Skype for Business usar uma nova chave após rolar ou girar as teclas no Azure Key Vault

Ao lançar uma das chaves do Azure Key Vault associadas a uma DEP usada com o Exchange Online e o Skype for Business, você deve executar o seguinte comando para atualizar a DEP e habilitar o Office 365 para começar a usar a nova chave.
  
Para instruir a chave do cliente a usar a nova chave para criptografar caixas de correio no Office 365, execute o cmdlet Set-DataEncryptionPolicy da seguinte maneira:
  
```powershell
Set-DataEncryptionPolicy <policyname> -Refresh
```

Em 48 horas, as caixas de correio ativas criptografadas usando essa política serão associadas à chave atualizada. Use as etapas em [determinar a DEP atribuída a uma caixa de correio](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) para verificar o valor da propriedade DataEncryptionPolicyID da caixa de correio. O valor dessa propriedade será alterado após a aplicação da chave atualizada.
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>Habilitar o SharePoint Online e o OneDrive for Business para usar uma nova chave após rolar ou girar as teclas no Azure Key Vault

Ao lançar uma das chaves do Azure Key Vault associadas a uma DEP usada com o SharePoint Online e o OneDrive for Business, você deve executar o cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) para atualizar a DEP e habilitar o Office 365 para começar a usar a nova chave. 
  
```powershell
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

Isso iniciará a operação do rolo principal para o SharePoint Online e o OneDrive for Business. Esta ação não é imediata. Para ver o andamento da operação do registro principal, execute o cmdlet Get-SPODataEncryptionPolicy da seguinte maneira:
  
```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>Gerenciar permissões do Key Vault
<a name="Managekeyvaultperms"> </a>

Há vários cmdlets disponíveis que permitem que você visualize e, se necessário, remova as permissões do Key Vault. Talvez seja necessário remover permissões, por exemplo, quando um funcionário sair da equipe.
  
Para exibir as permissões do compartimento de chaves, execute o cmdlet Get-AzureRmKeyVault:
  
```powershell
Get-AzureRmKeyVault -VaultName <vaultname>
```

Por exemplo:
  
```powershell
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Para remover as permissões de um administrador, execute o cmdlet Remove-AzureRmKeyVaultAccessPolicy:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname>
-UserPrincipalName <UPN of user>
```

Por exemplo:
  
```powershell
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Determinar a DEP atribuída a uma caixa de correio
<a name="DeterminemailboxDEP"> </a>

Para determinar a DEP atribuída a uma caixa de correio, use o cmdlet Get-MailboxStatistics. O cmdlet retorna um identificador exclusivo (GUID).
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

Onde *GeneralMailboxOrMailUserIdParameter* especifica uma caixa de correio. Para obter mais informações sobre o cmdlet Get-MailboxStatistics, consulte [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).
  
Use o GUID para descobrir o nome amigável da DEP à qual a caixa de correio é atribuída executando o cmdlet a seguir.
  
```powershell
Get-DataEncryptionPolicy <GUID>
```

Onde *GUID* é o GUID retornado pelo cmdlet Get-MailboxStatistics na etapa anterior.
