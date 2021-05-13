---
title: Configurar a Chave do Cliente
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
description: Saiba como configurar a Chave do Cliente para Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344669"
---
# <a name="set-up-customer-key"></a>Configurar a Chave do Cliente

Com a Chave do Cliente, você controla as chaves de criptografia da sua organização e configura Microsoft 365 usá-las para criptografar seus dados em repouso nos data centers da Microsoft. Em outras palavras, a Chave do Cliente permite que os clientes adicionem uma camada de criptografia que pertence a eles, com suas chaves.

Configurar o Azure antes de usar a Chave do Cliente para Office 365. Este artigo descreve as etapas que você precisa seguir para criar e configurar os recursos necessários do Azure e fornece as etapas para configurar a Chave do Cliente no Office 365. Depois de configurar o Azure, você determina qual política e, portanto, quais chaves atribuir para criptografar dados em várias Microsoft 365 cargas de trabalho em sua organização. Para obter mais informações sobre a Chave do Cliente ou para obter uma visão geral, consulte Criptografia de serviço [com Chave](customer-key-overview.md)do Cliente Office 365 .
  
> [!IMPORTANT]
> Recomendamos que você siga as práticas recomendadas neste artigo. Eles são chamados como **TIP** e **IMPORTANTE.** A Chave do Cliente oferece controle sobre chaves de criptografia raiz cujo escopo pode ser tão grande quanto toda a sua organização. Isso significa que erros feitos com essas chaves podem ter um impacto amplo e podem resultar em interrupções de serviço ou perda irrevogável de seus dados.
  
## <a name="before-you-set-up-customer-key"></a>Antes de configurar a Chave do Cliente

Antes de começar, verifique se você tem as assinaturas e o licenciamento apropriados do Azure para sua organização. Use assinaturas pagas do Azure usando um Enterprise Agreement ou um Provedor de Serviços na Nuvem. Os pagamentos com base em cartão de crédito não são aceitos. Aprovar e configurar as necessidades de conta para faturamento. As assinaturas que você recebeu por meio de Free, Trial, Sponsorships, MSDN Subscriptions e as que estão em Suporte Herdado não são qualificadas.

Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance e Microsoft 365 E5 Proteção de Informações & Governança SKUs oferecem Chave do Cliente. Conformidade Avançada do Office 365 O SKU não está mais disponível para obter novas licenças. As licenças Conformidade Avançada do Office 365 existentes continuarão a ser suportadas.

Para entender os conceitos e os procedimentos deste artigo, revise a documentação do [Azure Key Vault.](/azure/key-vault/) Além disso, familiarizar-se com os termos usados no Azure, por exemplo, locatário do [Azure AD](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).
  
Se você precisar de mais suporte além da documentação, entre em contato com o Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) ou um parceiro da Microsoft para obter assistência. Para fornecer comentários sobre a Chave do Cliente, incluindo a documentação, envie suas ideias, sugestões e perspectivas para customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Visão geral das etapas para configurar a Chave do Cliente

Para configurar a Chave do Cliente, conclua essas tarefas na ordem listada. O restante deste artigo fornece instruções detalhadas para cada tarefa ou links para mais informações para cada etapa do processo.
  
**No Azure e no Microsoft FastTrack:**
  
Você concluirá a maioria dessas tarefas conectando-se remotamente a Azure PowerShell. Para melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.
  
- [Criar duas novas assinaturas do Azure](#create-two-new-azure-subscriptions)

- [Enviar uma solicitação para ativar a Chave do Cliente para Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [Registrar assinaturas do Azure para usar um período de retenção obrigatório](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  O registro pode levar de um a cinco dias úteis.

- [Criar um Cofre de Chaves premium do Azure em cada assinatura](#create-a-premium-azure-key-vault-in-each-subscription)

- [Atribuir permissões a cada cofre de chaves](#assign-permissions-to-each-key-vault)

- [Certifique-se de que a exclusão suave está habilitada em seus cofres de chaves](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Adicionar uma chave a cada cofre de chaves criando ou importando uma chave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Verifique o nível de recuperação de suas chaves](#check-the-recovery-level-of-your-keys)

- [Back up Azure Key Vault](#back-up-azure-key-vault)

- [Validar as configurações do Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Obter o URI para cada chave do Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Concluir tarefas no Azure Key Vault e no Microsoft FastTrack para Chave do Cliente

Conclua essas tarefas no Azure Key Vault. Você precisará concluir essas etapas para todos os DEPs que usar com a Chave do Cliente.
  
### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure

A Chave do Cliente requer duas assinaturas do Azure. Como prática prática, a Microsoft recomenda que você crie novas assinaturas do Azure para uso com a Chave do Cliente. As chaves do Azure Key Vault só podem ser autorizadas para aplicativos no mesmo locatário Azure Active Directory (Microsoft Azure Active Directory), você deve criar as novas assinaturas usando o mesmo locatário do Azure AD usado com sua organização onde os DEPs serão atribuídos. Por exemplo, usando sua conta de estudante ou de trabalho que tenha privilégios globais de administrador em sua organização. Para etapas detalhadas, consulte [Inscrever-se no Azure como uma organização](/azure/active-directory/fundamentals/sign-up-organization).
  
> [!IMPORTANT]
> A Chave do Cliente requer duas chaves para cada POLÍTICA de criptografia de dados (DEP). Para isso, você deve criar duas assinaturas do Azure. Como prática prática, a Microsoft recomenda que você tenha membros separados da sua organização configurar uma chave em cada assinatura. Você só deve usar essas assinaturas do Azure para administrar chaves de criptografia para Office 365. Isso protege sua organização caso um de seus operadores exclua acidentalmente, intencionalmente ou maliciosamente ou, de outra forma, as chaves pelas quais são responsáveis.

Não há limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir essas práticas recomendadas minimizará o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela Chave do Cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar uma solicitação para ativar a Chave do Cliente para Office 365

Depois de criar as duas novas assinaturas do Azure, você precisará enviar a solicitação de oferta de Chave de Cliente apropriada no [portal do Microsoft FastTrack.](https://fasttrack.microsoft.com/) As seleções que você faz no formulário de oferta sobre as designações autorizadas em sua organização são críticas e necessárias para a conclusão do registro da Chave do Cliente. Os oficiais nessas funções selecionadas em sua organização garantem a autenticidade de qualquer solicitação para revogar e destruir todas as chaves usadas com uma política de criptografia de dados de Chave de Cliente. Você precisará fazer essa etapa uma vez para cada tipo de DEP de Chave de Cliente que você pretende usar para sua organização.

**A equipe do FastTrack não fornece assistência com a Chave do Cliente. Office 365 simplesmente usa o portal do FastTrack para permitir que você envie o formulário e nos ajude a rastrear as ofertas relevantes para a Chave do Cliente. Depois de enviar a solicitação do FastTrack, entre em contato com a equipe de integração da Chave do Cliente correspondente para iniciar o processo de integração.**
  
Para enviar uma oferta para ativar a Chave do Cliente, conclua estas etapas:
  
1. Usando uma conta de trabalho ou de estudante que tenha permissões globais de administrador em sua organização, entre no [portal do Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Quando você estiver conectado, selecione o domínio apropriado.

3. Para o domínio selecionado, escolha **Solicitar serviços** na barra de navegação superior e revise a lista de ofertas disponíveis.

4. Escolha o cartão de informações para a oferta que se aplica a você:

   - **Várias Microsoft 365 de trabalho:** Escolha a **ajuda solicitar a chave de criptografia para Microsoft 365** oferta.

   - **Exchange Online e Skype for Business:** Escolha a **ajuda solicitar a chave de criptografia para Exchange** oferta.

   - **SharePoint online, OneDrive e Teams arquivos:** Escolha a **ajuda solicitação de chave de criptografia para SharePoint e OneDrive for Business** oferta.

5. Depois de revisar os detalhes da oferta, escolha **Continuar para a etapa 2**.

6. Preencha todos os detalhes aplicáveis e informações solicitadas sobre o formulário de oferta. Preste atenção especial às suas seleções para quais oficiais da sua organização você deseja autorizar a aprovação da destruição permanente e irreversível de chaves e dados de criptografia. Depois de concluir o formulário, escolha **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório

A perda temporária ou permanente de chaves de criptografia raiz pode ser prejudicial ou até catastrófica para a operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a Chave do Cliente exigem uma proteção forte. Todos os recursos do Azure usados com a Chave do Cliente oferecem mecanismos de proteção além da configuração padrão. Você pode marcar ou registrar assinaturas do Azure para um *período de retenção obrigatório.* Um período de retenção obrigatório impede o cancelamento imediato e irrevogável da sua assinatura do Azure. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a Microsoft 365 equipe. Esse processo pode levar de um a cinco dias úteis. Anteriormente, o período de retenção obrigatório às vezes era chamado de "Não Cancelar".
  
Antes de entrar em contato com a equipe Microsoft 365, você deve fazer as etapas a seguir para cada assinatura do Azure que você usa com a Chave do Cliente. Verifique se você tem o [Azure PowerShell do Az](/powershell/azure/new-azureps-module-az) instalado antes de iniciar.
  
1. Entre com Azure PowerShell. Para obter instruções, [consulte Entrar com Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Execute o cmdlet Register-AzProviderFeature para registrar suas assinaturas para usar um período de retenção obrigatório. Conclua essa ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contate a Microsoft para concluir o processo.

   - Para habilbilizar a Chave do Cliente para atribuir o DEP a caixas de correio Exchange Online individuais, entre [em contato exock@microsoft.com](mailto:exock@microsoft.com).

   - Para habilizar a Chave do Cliente para atribuir DEPs para criptografar SharePoint Online e OneDrive for Business conteúdo (incluindo arquivos Teams) para todos os usuários de locatários, entre em contato com spock@microsoft.com [.](mailto:spock@microsoft.com)

   - Para habilizar a Chave do Cliente para atribuir DEPs para criptografar conteúdo em várias cargas de trabalho de Microsoft 365 (Exchange Online, Teams, MIP EDM) para todos os usuários de locatários, contate m365-ck@service.microsoft.com [.](mailto:m365-ck@service.microsoft.com)

- Inclua as seguintes informações em seu email:

   **Assunto**: Chave do Cliente para \<*Your tenant's fully qualified domain name*\>

   **Corpo**: Inclua as IDs de assinatura para as quais você deseja concluir o período de retenção obrigatório e a saída de Get-AzProviderFeature para cada assinatura.

   O Contrato de Nível de Serviço (SLA) para conclusão desse processo é de cinco dias úteis depois que a Microsoft foi notificada (e verificada) de que você registrou suas assinaturas para usar um período de retenção obrigatório.

4. Depois de receber uma notificação da Microsoft de que o registro está concluído, verifique o status do seu registro executando o comando Get-AzProviderFeature da seguinte forma. Se verificado, o comando Get-AzProviderFeature retornará um valor **de Registered** para a propriedade **Registration State.** Conclua esta etapa para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para concluir o processo, execute o comando Register-AzResourceProvider. Conclua esta etapa para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Criar um Cofre de Chaves premium do Azure em cada assinatura

As etapas para criar um cofre de chaves estão documentadas em [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), que orienta você durante a instalação e o lançamento do Azure PowerShell, a conexão com sua assinatura do Azure, a criação de um grupo de recursos e a criação de um cofre de chaves nesse grupo de recursos.
  
Ao criar um cofre de chaves, você deve escolher um SKU: Standard ou Premium. A SKU padrão permite que as chaves do Azure Key Vault sejam protegidas com software - não há proteção de chave HSM (Módulo de Segurança de Hardware) - e o SKU do Premium permite o uso de HSMs para proteção de chaves do Key Vault. A Chave do Cliente aceita cofres-chave que usam SKU, embora a Microsoft recomenda que você use apenas o SKU Premium de segurança. O custo das operações com chaves de qualquer tipo é o mesmo, portanto, a única diferença de custo é o custo por mês para cada chave protegida por HSM. Consulte [Key Vault pricing for](https://azure.microsoft.com/pricing/details/key-vault/) details.
  
> [!IMPORTANT]
> Use os Premium chave SKU e as chaves protegidas por HSM para dados de produção e use apenas os cofres e chaves de chave SKU padrão para fins de teste e validação.
  
Para cada Microsoft 365 com o qual você usará a Chave do Cliente, crie um cofre de chaves em cada uma das duas assinaturas do Azure criadas. Por exemplo, para habilitar a Chave do Cliente a usar DEPs para cenários de Exchange Online, SharePoint Online e de várias cargas de trabalho, você criará três pares de cofres-chave.
  
Use uma convenção de nomenbo para cofres de chaves que reflita o uso pretendido do DEP com o qual você associará os cofres. Consulte a seção Práticas Recomendadas abaixo para saber as recomendações de convenção de nomenis.
  
Crie um conjunto separado e emparelhado de cofres para cada política de criptografia de dados. Para Exchange Online, o escopo de uma política de criptografia de dados é escolhido por você ao atribuir a política à caixa de correio. Uma caixa de correio pode ter apenas uma política atribuída e você pode criar até 50 políticas. O escopo de uma política SharePoint Online inclui todos os dados em uma organização em uma localização geográfica ou _geográfica._ O escopo de uma política de várias cargas de trabalho inclui todos os dados em todas as cargas de trabalho suportadas para todos os usuários.

A criação de cofres-chave também exige a criação de grupos de recursos do Azure, já que os cofres-chave precisam de capacidade de armazenamento (embora pequena) e o log do Cofre de Chaves, se habilitado, também gera dados armazenados. Como prática prática, a Microsoft recomenda o uso de administradores separados para gerenciar cada grupo de recursos, com a administração alinhada ao conjunto de administradores que gerenciará todos os recursos de Chave do Cliente relacionados.
  
> [!IMPORTANT]
> Para maximizar a disponibilidade, coloque seus cofres chave em regiões próximas ao seu serviço Microsoft 365 Por exemplo, se sua organização Exchange Online estiver na América do Norte, coloque seus cofres principais na América do Norte. Se sua Exchange Online estiver na Europa, coloque seus cofres principais na Europa.
>
> Use um prefixo comum para cofres de chaves e inclua uma abreviação do uso e escopo do cofre de chaves e chaves (por exemplo, para o serviço de SharePoint contoso onde os cofres estarão localizados na América do Norte, um possível par de nomes é Contoso-CK-SP-NA-VaultA1 e Contoso-CK-SP-NA-VaultA2. Os nomes de cofre são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez seja necessário experimentar variações dos nomes desejados caso os nomes desejados já sejam reivindicados por outros clientes do Azure. A partir de julho de 2017, os nomes de cofre não podem ser alterados, portanto, uma prática ideal é ter um plano escrito para instalação e usar uma segunda pessoa para verificar se o plano foi executado corretamente.
>
> Se possível, crie seus cofres em regiões não emparelhadas. Regiões emparelhadas do Azure fornecem alta disponibilidade em domínios de falha de serviço. Portanto, os pares regionais podem ser pensados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região está ganhando automaticamente tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma política de criptografia de dados em que as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade estão em uso. A maioria das regiões tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma política de criptografia de dados. Isso beneficia um total de quatro regiões de disponibilidade. Para obter mais informações, consulte Continuidade de negócios e recuperação de desastres [(BCDR): Regiões emparelhadas do Azure](/azure/best-practices-availability-paired-regions) para obter uma lista atual de pares regionais.
  
### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves

Você precisará definir três conjuntos separados de permissões para cada cofre de chaves, dependendo da implementação. Por exemplo, você precisará definir um conjunto de permissões para cada uma das seguintes:
  
- **Os principais administradores do** cofre de chaves que fazem o gerenciamento dia a dia do seu cofre de chaves para sua organização. Essas tarefas incluem backup, criação, obter, importar, listar e restaurar.

  > [!IMPORTANT]
  > O conjunto de permissões atribuídas aos administradores do cofre de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. A exclusão de chaves de criptografia normalmente não é feita, pois isso destrói permanentemente os dados. Como prática prática, não conceda essa permissão aos administradores do cofre de chaves por padrão. Em vez disso, reserve-o para colaboradores chave do cofre e atribua-o apenas a um administrador em curto prazo, uma vez que uma compreensão clara das consequências seja compreendida.
  
  Para atribuir essas permissões a um usuário em sua organização, entre na assinatura do Azure com Azure PowerShell. Para obter instruções, [consulte Entrar com Azure PowerShell](/powershell/azure/authenticate-azureps).

- Execute o cmdlet Set-AzKeyVaultAccessPolicy para atribuir as permissões necessárias.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por exemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores do cofre de chaves** que podem alterar permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários sairem ou ingressarem em sua equipe. Na situação rara em que os administradores do cofre de chaves precisam legitimamente de permissão para excluir ou restaurar uma chave, você também precisará alterar as permissões. Esse conjunto de colaboradores do cofre de chaves precisa ser concedido à função **Colaborador** no seu cofre de chaves. Você pode atribuir essa função usando o Gerenciador de Recursos do Azure. Para etapas detalhadas, consulte Use Role-Based Access Control para gerenciar o acesso aos recursos de [assinatura do Azure.](/azure/active-directory/role-based-access-control-configure) O administrador que cria uma assinatura tem esse acesso implicitamente e a capacidade de atribuir outros administradores à função Colaborador.

- Permissões para **Microsoft 365 aplicativos** para cada cofre de chaves que você usa para a Chave do Cliente, você precisa dar wrapKey, unwrapKey e obter permissões para a Entidade de Serviço Microsoft 365 correspondente. 

Para dar permissão para Microsoft 365 de Serviço Principal, execute o cmdlet **Set-AzKeyVaultAccessPolicy** usando a seguinte sintaxe:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Onde:

   - *nome do* cofre é o nome do cofre de chaves que você criou.
   - Para Exchange Online e Skype for Business, substitua *Office 365 appID* por`00000002-0000-0ff1-ce00-000000000000`
   - Para SharePoint online, OneDrive for Business e Teams, substitua Office 365 *appID* por`00000003-0000-0ff1-ce00-000000000000`
   - Para política de várias cargas de trabalho (Exchange, Teams, MIP EDM) que se aplica a todos os usuários de locatários, substitua Office 365 *appID* por`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Exemplo: Definindo permissões para Exchange Online e Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Exemplo: Definindo permissões para arquivos SharePoint Online, OneDrive for Business e Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Certifique-se de que a exclusão suave está habilitada em seus cofres de chaves

Quando você pode recuperar rapidamente suas chaves, é menos provável que você tenha uma paralisação de serviço estendida devido a chaves excluídas acidentalmente ou maliciosamente. Habilita essa configuração, conhecida como Exclusão Suave, antes de poder usar suas chaves com a Chave do Cliente. A habilitação da Exclusão Suave permite que você recupere chaves ou cofres dentro de 90 dias após a exclusão sem precisar restaurá-las do backup.
  
Para habilitar a Exclusão Suave em seus cofres de chaves, conclua estas etapas:
  
1. Entre em sua assinatura do Azure com Windows PowerShell. Para obter instruções, [consulte Entrar com Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Execute o cmdlet [Get-AzKeyVault.](/powershell/module/az.keyvault/get-azkeyvault) Neste exemplo, *o nome do cofre* é o nome do cofre de chaves para o qual você está habilitando a exclusão suave:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirme se a exclusão suave está configurada para o cofre de chaves executando o cmdlet **Get-AzKeyVault.** Se a exclusão suave estiver configurada corretamente para o cofre de chaves, a propriedade _Soft Delete Enabled_ retornará um valor **true**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Adicionar uma chave a cada cofre de chaves criando ou importando uma chave

Há duas maneiras de adicionar chaves a um Cofre de Chaves do Azure; você pode criar uma chave diretamente no Cofre de Chaves ou pode importar uma chave. Criar uma chave diretamente no Cofre de Chaves é menos complicado, mas importar uma chave fornece controle total sobre como a chave é gerada. Use as teclas RSA. O Azure Key Vault não dá suporte a quebras e quebras com chaves de curva elípticas.
  
Para criar uma chave diretamente no cofre de chaves, execute o cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) da seguinte forma:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Onde:

- *nome do* cofre é o nome do cofre de chaves no qual você deseja criar a chave.

- *nome da* chave é o nome que você deseja dar à nova chave.

  > [!TIP]
  > Teclas de nome usando uma convenção de nomenbo semelhante conforme descrito acima para cofres de chaves. Dessa forma, em ferramentas que mostram apenas o nome da chave, a cadeia de caracteres é auto-descrevendo.
  
Se você pretende proteger a chave com um HSM, certifique-se de especificar **HSM** como o valor do parâmetro _Destination,_ caso contrário, especifique **Software**.

Por exemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Para importar uma chave diretamente para seu cofre de chaves, você precisa ter um Módulo de Segurança de Hardware nCipher nShield.
  
Algumas organizações preferem essa abordagem para estabelecer a procedência de suas chaves e, em seguida, este método também fornece os seguintes atestados:
  
- O toolset usado para importação inclui o atestado do nCipher de que o KEK (Key Exchange Key) usado para criptografar a chave gerada não é exportável e é gerado dentro de um HSM original que foi fabricado pelo nCipher.

- O toolset inclui atestado do nCipher de que o mundo de segurança do Azure Key Vault também foi gerado em um HSM original fabricado pelo nCipher. Esse atestado prova que a Microsoft também está usando hardware nCipher original.

Verifique com seu grupo de segurança para determinar se os atestados acima são necessários. Para etapas detalhadas para criar uma chave local e importá-la para seu cofre de chaves, consulte Como gerar e transferir chaves protegidas por HSM para o [Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys). Use as instruções do Azure para criar uma chave em cada cofre de chaves.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Verifique o nível de recuperação de suas chaves

Microsoft 365 requer que a assinatura do Azure Key Vault seja definida como Não Cancelar e que as chaves usadas pela Chave do Cliente tenham exclusão suave habilitada. Você pode confirmar as configurações de assinaturas olhando para o nível de recuperação em suas chaves.
  
Para verificar o nível de recuperação de uma chave, em Azure PowerShell, execute o cmdlet Get-AzKeyVaultKey da seguinte forma:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se a propriedade _Nível_ de Recuperação retornar algo diferente de um valor **Recoverable+ProtectedSubscription**, verifique se você colocou a assinatura na lista Não Cancelar e se você tem a exclusão suave habilitada em cada um dos seus cofres principais.
  
### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, online e offline. Não conecte cópias offline a nenhuma rede. Em vez disso, armazene-os em um local offline, como em um local de armazenamento físico seguro ou comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que será acessível se ocorrer um desastre. Os blobs de backup são o único meio de restaurar o material de chave caso uma chave do Cofre de Chaves seja permanentemente destruída ou renderizada inoperável. Chaves externas ao Azure Key Vault e importadas para o Azure Key Vault não se qualificam como backup porque os metadados necessários para a Chave do Cliente usar a chave não existem com a chave externa. Somente um backup feito do Azure Key Vault pode ser usado para restaurar operações com a Chave do Cliente. Portanto, você deve criar um backup do Azure Key Vault depois de carregar ou criar uma chave.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) da seguinte forma:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verifique se o arquivo de saída usa o sufixo `.backup` .
  
O arquivo de saída resultante desse cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup só pode ser restaurado para a assinatura do Azure da qual o backup foi feito.
  
> [!TIP]
> Para o arquivo de saída, escolha uma combinação do nome do cofre e o nome da chave. Isso fará com que o nome do arquivo se auto-descreva. Ele também garantirá que os nomes de arquivo de backup não colidam.
  
Por exemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar as configurações do Azure Key Vault

Validar antes de usar chaves em um DEP é opcional, mas altamente recomendado. Se você usar etapas para configurar suas chaves e cofres diferentes dos descritos neste artigo, valide a saúde dos recursos do Azure Key Vault antes de configurar a Chave do Cliente.
  
Para verificar se suas chaves têm `get` , `wrapKey` e operações `unwrapKey` habilitadas:
  
Execute o cmdlet [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Na saída, procure a Política de Acesso e o GUID (Exchange Online de SharePoint online) conforme apropriado. Todas as três permissões acima devem ser mostradas em Permissões para Chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzKeyVaultAccessPolicy da seguinte maneira:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por exemplo, para Exchange Online e Skype for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por exemplo, para SharePoint Online e OneDrive for Business:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Para verificar se uma data de expiração não está definida para suas chaves, execute o cmdlet [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

A Chave do Cliente não pode usar uma chave expirada. Operações tentadas com uma chave expirada falharão e possivelmente resultarão em uma paralisação de serviço. É recomendável que as chaves usadas com a Chave do Cliente não tenham uma data de expiração. Uma data de expiração, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se uma chave tiver que ser usada com um conjunto de datas de expiração, altere o valor de expiração para 31/12/9999. Chaves com uma data de expiração definida como uma data diferente de 31/12/9999 não passarão na validação Microsoft 365.
  
Para alterar uma data de expiração definida para qualquer valor diferente de 31/12/9999, execute o cmdlet [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) da seguinte forma:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Não desmarco datas de expiração em chaves de criptografia que você usa com a Chave do Cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obter o URI para cada chave do Azure Key Vault

Depois de configurar seus cofres de chaves e adicionar suas chaves, execute o seguinte comando para obter o URI da chave em cada cofre de chaves. Você usará esses URIs ao criar e atribuir cada DEP posteriormente, portanto, salve essas informações em um local seguro. Execute este comando uma vez para cada cofre de chaves.
  
Em Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Próximas etapas

Depois de concluir as etapas deste artigo, você estará pronto para criar e atribuir DEPs. Para obter instruções, consulte [Manage Customer Key](customer-key-manage.md).

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Criptografia de Serviço](office-365-service-encryption.md)