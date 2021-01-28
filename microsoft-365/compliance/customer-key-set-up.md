---
title: Configurar a Chave do Cliente no nível do aplicativo
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
description: Saiba como configurar a Chave do Cliente para arquivos do Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams.
ms.openlocfilehash: 94702cecb37686c3996c5ed70b1810a825bb2ff6
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032608"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Configurar a Chave do Cliente no nível do aplicativo

Com a Chave do Cliente, você controla as chaves de criptografia da sua organização e configura o Microsoft 365 para usá-las para criptografar seus dados em repouso nos data centers da Microsoft. Em outras palavras, a Chave do Cliente permite que os clientes adicionem uma camada de criptografia que pertence a eles, com suas chaves. Os dados em repouso incluem dados do Exchange Online e do Skype for Business armazenados em caixas de correio e arquivos armazenados no SharePoint Online e no OneDrive for Business.

Você deve configurar o Azure antes de poder usar a Chave do Cliente para o Office 365. Este artigo descreve as etapas que você precisa seguir para criar e configurar os recursos necessários do Azure e fornece as etapas para configurar a Chave do Cliente no Office 365. Depois de concluir a configuração do Azure, você determina qual política e, portanto, quais chaves atribuir a caixas de correio e arquivos em sua organização. Caixas de correio e arquivos para os quais você não atribui uma política usarão políticas de criptografia controladas e gerenciadas pela Microsoft. Para obter mais informações sobre a Chave do Cliente ou para obter uma visão geral, consulte Criptografia de serviço com a Chave de [Cliente no Office 365.](customer-key-overview.md)
  
> [!IMPORTANT]
> Recomendamos que você siga as práticas recomendadas neste artigo. Eles são chamados de **DICA e** **IMPORTANTE.** A Chave do Cliente oferece controle sobre chaves de criptografia raiz cujo escopo pode ser tão grande quanto toda a organização. Isso significa que os erros feitos com essas chaves podem ter um impacto amplo e podem resultar em interrupções de serviço ou perda irrevogável de seus dados.
  
## <a name="before-you-set-up-customer-key"></a>Antes de configurar a Chave do Cliente

Antes de começar, verifique se você tem o licenciamento apropriado para sua organização. Use uma Assinatura do Azure paga e faturada usando um Contrato Empresarial ou um Provedor de Serviços de Nuvem. Assinaturas do Azure adquiridas usando planos Pagar à Medida que Você Vai ou usando um cartão de crédito não são suportadas pela Chave do Cliente. A partir de 1º de abril de 2020, a Chave de Cliente no Office 365 é oferecida no Office 365 E5, M365 E5, Conformidade do M365 E5 e SKUs de Proteção de Informações do M365 E5 & Governança. A SKU de Conformidade Avançada do Office 365 não está mais disponível para a aquisição de novas licenças. As licenças existentes de Conformidade Avançada do Office 365 continuarão a ter suporte.

Para entender os conceitos e procedimentos deste artigo, revise a documentação do [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/) Além disso, familiarizar-se com os termos usados no Azure, por exemplo, locatário do [Azure AD.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)

O FastTrack é usado apenas para coletar as informações necessárias de configuração de locatário e serviço usadas para registrar a Chave do Cliente. As Ofertas de Chave de Cliente são publicadas por meio do FastTrack para que seja conveniente para você e nossos parceiros enviarem as informações necessárias usando o mesmo método. O FastTrack também facilita o arquivamento dos dados que você fornece na Oferta.
  
Se precisar de mais suporte além da documentação, entre em contato com o Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) ou com um parceiro da Microsoft para obter assistência. Para fornecer comentários sobre a Chave do Cliente, incluindo a documentação, envie suas ideias, sugestões e perspectivas para customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Visão geral das etapas para configurar a Chave do Cliente

Para configurar a Chave do Cliente, conclua essas tarefas na ordem listada. O restante deste artigo fornece instruções detalhadas para cada tarefa ou links para obter mais informações sobre cada etapa do processo.
  
**No Azure e no Microsoft FastTrack:**
  
Você concluirá a maioria dessas tarefas se conectando remotamente ao Azure PowerShell. Para melhores resultados, use a versão 4.4.0 ou posterior do Azure PowerShell.
  
- [Criar duas novas assinaturas do Azure](#create-two-new-azure-subscriptions)

- [Registrar assinaturas do Azure para usar um período de retenção obrigatório](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  O registro pode levar de um a cinco dias úteis.

- [Enviar uma solicitação para ativar a Chave do Cliente para o Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Depois de criar as duas novas assinaturas do Azure, você precisará enviar a solicitação de oferta da Chave do Cliente apropriada preenchendo um formulário da Web hospedado no portal do Microsoft FastTrack. **A equipe FastTrack não fornece assistência com a Chave do Cliente. O Office simplesmente usa o portal FastTrack** para permitir que você envie o formulário e nos ajude a acompanhar as ofertas relevantes para a Chave do Cliente.

- [Criar um Azure Key Vault premium em cada assinatura](#create-a-premium-azure-key-vault-in-each-subscription)

- [Atribuir permissões a cada cofre de chaves](#assign-permissions-to-each-key-vault)

- [Habilitar e confirmar a exclusão suave em seus cofres de chaves](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Adicione uma chave a cada cofre de chaves criando ou importando uma chave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Verificar o nível de recuperação de suas chaves](#check-the-recovery-level-of-your-keys)

- [Back up Azure Key Vault](#back-up-azure-key-vault)

- [Validar as definições de configuração do Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Obter o URI de cada chave do Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)

**No Office 365:**
  
Exchange Online e Skype for Business:
  
- [Criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Atribuir um DEP a uma caixa de correio](#assign-a-dep-to-a-mailbox)

- [Validar a criptografia de caixa de correio](#validate-mailbox-encryption)

SharePoint Online e OneDrive for Business:
  
- [Criar uma política de criptografia de dados (DEP) para cada área geográfica do SharePoint Online e do OneDrive for Business](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Validar a criptografia de arquivo para arquivos do SharePoint Online, OneDrive for Business e Teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Concluir tarefas no Azure Key Vault e no Microsoft FastTrack for Customer Key

Conclua essas tarefas no Azure Key Vault. Você precisará concluir essas etapas independentemente se pretende configurar a Chave do Cliente para o Exchange Online, Skype for Business ou para arquivos do SharePoint Online, OneDrive for Business e Teams ou para todos os serviços com suporte no Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Criar duas novas assinaturas do Azure

A Chave do Cliente requer duas assinaturas do Azure. Como prática recomendável, a Microsoft recomenda que você crie novas assinaturas do Azure para uso com a Chave do Cliente. As chaves do Azure Key Vault só podem ser autorizadas para aplicativos no mesmo locatário do Azure Active Directory (Microsoft Azure Active Directory), você deve criar as novas assinaturas usando o mesmo locatário do Azure AD usado com sua organização onde os DEPs serão atribuídos. Por exemplo, usar sua conta de trabalho ou de estudante que tenha privilégios de administrador global em sua organização. Para etapas detalhadas, confira [Inscrever-se no Azure como uma organização.](https://azure.microsoft.com/documentation/articles/sign-up-organization/)
  
> [!IMPORTANT]
> A Chave do Cliente exige duas chaves para cada DEP (política de criptografia de dados). Para conseguir isso, você deve criar duas assinaturas do Azure. Como prática recomendável, a Microsoft recomenda que você tenha membros separados da sua organização para configurar uma chave em cada assinatura. Você só deve usar essas assinaturas do Azure para administrar chaves de criptografia do Office 365. Isso protege sua organização caso um de seus operadores exclua acidentalmente, intencionalmente ou mal-intencionado ou, de outra forma, incorretamente as chaves pelas quais são responsáveis.
>

Não há um limite prático para o número de assinaturas do Azure que você pode criar para sua organização. Seguir essas práticas recomendadas minimizará o impacto do erro humano enquanto ajuda a gerenciar os recursos usados pela Chave do Cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar uma solicitação para ativar a Chave do Cliente para o Office 365

Depois de concluir as etapas do Azure, você precisará enviar uma solicitação de oferta no [portal do Microsoft FastTrack.](https://fasttrack.microsoft.com/) Depois que você enviar uma solicitação por meio do portal da Web do FastTrack, a Microsoft verificará os dados de configuração e as informações de contato do Azure Key Vault que você forneceu. As seleções que você faz no formulário de oferta sobre os oficiais autorizados da sua organização são essenciais e necessárias para a conclusão do registro da Chave do Cliente. Os agentes da sua organização garantem a autenticidade de qualquer solicitação para revogar e destruir todas as chaves usadas com uma política de criptografia de dados da Chave do Cliente. Você precisará fazer essa etapa uma vez para ativar a Chave do Cliente para a cobertura do Exchange Online e do Skype for Business e uma segunda vez para ativar a Chave do Cliente para o SharePoint Online e o OneDrive for Business.
  
Para enviar uma oferta para ativar a Chave do Cliente, conclua estas etapas:
  
1. Usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, entre no [portal do Microsoft FastTrack.](https://fasttrack.microsoft.com/)

2. Depois de entrar, navegue até o **Painel.**

3. Escolha **Implantar na** barra de navegação **OU**  selecione **Exibir** todos os recursos de implantação no cartão de informações Implantar e revise a lista de ofertas atuais.

4. Escolha o cartão de informações para a oferta que se aplica a você:

   - **Exchange Online e Skype for Business:** Escolha a **ajuda solicitação da chave de criptografia para a oferta online do Exchange.**

   - **Arquivos do SharePoint Online, OneDrive e Teams:** Escolha a **ajuda solicitação da chave de criptografia para a oferta do SharePoint e do OneDrive.**

5. Depois de analisar os detalhes da oferta, escolha **Continuar para a etapa 2.**

6. Preencha todos os detalhes aplicáveis e informações solicitadas no formulário de oferta. Preste atenção especial às suas seleções para quais oficiais da sua organização você deseja autorizar para aprovar a destruição permanente e irreversível de dados e chaves de criptografia. Depois de concluir o formulário, escolha **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar assinaturas do Azure para usar um período de retenção obrigatório

A perda temporária ou permanente de chaves de criptografia raiz pode ser prejudicial ou até mesmo catastrófica para a operação de serviço e pode resultar em perda de dados. Por esse motivo, os recursos usados com a Chave do Cliente exigem proteção forte. Todos os recursos do Azure usados com a Chave do Cliente oferecem mecanismos de proteção além da configuração padrão. Você pode marcar ou registrar assinaturas do Azure por um período *de retenção obrigatório.* Um período de retenção obrigatório impede o cancelamento imediato e irrevogável de sua assinatura do Azure. As etapas necessárias para registrar assinaturas do Azure para um período de retenção obrigatório exigem colaboração com a equipe do Microsoft 365. Esse processo pode levar de um a cinco dias úteis. Anteriormente, o período de retenção obrigatório às vezes era chamado de "Não Cancelar".
  
Antes de entrar em contato com a equipe do Microsoft 365, você deve seguir as etapas a seguir para cada assinatura do Azure usada com a Chave do Cliente. Verifique se você tem o [módulo do Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) instalado antes de começar.
  
1. Entre com o Azure PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Execute o Register-AzProviderFeature cmdlet para registrar suas assinaturas para usar um período de retenção obrigatório. Conclua esta ação para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Contate a Microsoft para concluir o processo. Para a equipe do SharePoint e do OneDrive for Business, entre em contato [spock@microsoft.com](mailto:spock@microsoft.com). Para o Exchange Online e o Skype for Business, entre [em contato exock@microsoft.com](mailto:exock@microsoft.com). Inclua as seguintes informações em seu email:

   **Assunto**: Chave do Cliente para \<*Your tenant's fully qualified domain name*\>

   **Corpo:** inclua as IDs de assinatura para as quais você deseja concluir o período de retenção obrigatório e a saída de Get-AzProviderFeature para cada assinatura.

   O Contrato de Nível de Serviço (SLA) para conclusão desse processo é de cinco dias úteis após a Microsoft ser notificada (e verificada) de que você registrou suas assinaturas para usar um período de retenção obrigatório.

4. Depois de receber uma notificação da Microsoft de que o registro foi concluído, verifique o status do seu registro executando o Get-AzProviderFeature comando da seguinte forma. Se verificado, o Get-AzProviderFeature comando retornará um valor **registrado** para a propriedade **Estado de** registro. Conclua esta etapa para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para concluir o processo, execute o Register-AzResourceProvider comando. Conclua esta etapa para cada assinatura.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Criar um Azure Key Vault premium em cada assinatura

As etapas para criar um cofre de chaves estão documentadas em Getting [Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que orienta você na instalação e no lançamento do Azure PowerShell, conexão com sua assinatura do Azure, criação de um grupo de recursos e criação de um cofre de chaves nesse grupo de recursos.
  
Ao criar um cofre de chaves, você deve escolher uma SKU: Standard ou Premium. A SKU Padrão permite que as chaves do Azure Key Vault sejam protegidas com software - não há proteção de chave HSM (Módulo de Segurança de Hardware) - e a SKU Premium permite o uso de HSMs para proteção de chaves key Vault. A Chave do Cliente aceita cofres de chaves que usam qualquer uma das SKU, embora a Microsoft recomende que você use apenas a SKU Premium. O custo das operações com chaves de qualquer tipo é o mesmo, portanto, a única diferença no custo é o custo por mês para cada chave protegida por HSM. Confira [os preços do Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obter detalhes.
  
> [!IMPORTANT]
> Use os cofres de chaves Premium SKU e as chaves protegidas por HSM para dados de produção e use somente chaves e cofres de chaves SKU Padrão para fins de teste e validação.
  
Para cada serviço do Microsoft 365 com o qual você usará a Chave do Cliente, crie um cofre de chaves em cada uma das duas assinaturas do Azure que você criou. Por exemplo, somente para o Exchange Online, Skype for Business ou SharePoint Online e OneDrive for Business, você criará apenas um par de cofres. Para habilitar a Chave do Cliente para o Exchange Online e o SharePoint Online, você criará dois pares de cofres de chaves.
  
Use uma convenção de nomen por cofres de chaves que reflita o uso pretendido da DEP à qual você associará os cofres. Consulte a seção Práticas Recomendadas abaixo para saber as recomendações de convenção de nomen por nome.
  
Crie um conjunto separado e emparelhado de cofres para cada política de criptografia de dados. Para o Exchange Online, o escopo de uma política de criptografia de dados é escolhido por você quando você atribui a política à caixa de correio. Uma caixa de correio pode ter apenas uma política atribuída, e você pode criar até 50 políticas. O escopo de uma política do SharePoint Online inclui todos os dados dentro de uma organização em uma localização geográfica ou _geográfica._

A criação de cofres de chaves também exige a criação de grupos de recursos do Azure, pois os cofres de chaves precisam de capacidade de armazenamento (embora pequenas) e o log do Key Vault, se habilitado, também gera dados armazenados. Como prática recomendável, a Microsoft recomenda o uso de administradores separados para gerenciar cada grupo de recursos, com a administração alinhada ao conjunto de administradores que gerenciará todos os recursos relacionados à Chave do Cliente.
  
> [!IMPORTANT]
> Para maximizar a disponibilidade, seus cofres de chaves devem estar em regiões próximas ao seu serviço do Microsoft 365. Por exemplo, se sua organização do Exchange Online estiver na América do Norte, coloque seus cofres de chaves na América do Norte. Se sua organização do Exchange Online estiver na Europa, coloque seus cofres de chaves na Europa.
> 
> Use um prefixo comum para cofres de chaves e inclua uma abreviação do uso e do escopo do cofre de chaves e chaves (por exemplo, para o serviço Do SharePoint da Contoso onde os cofres estarão localizados na América do Norte, um possível par de nomes é Contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. Os nomes dos cofres são cadeias de caracteres globalmente exclusivas no Azure, portanto, talvez seja necessário experimentar variações dos nomes desejados caso os nomes desejados já sejam reivindicados por outros clientes do Azure. A partir de julho de 2017, os nomes dos cofres não podem ser alterados, portanto, uma prática melhor é ter um plano escrito para instalação e usar uma segunda pessoa para verificar se o plano foi executado corretamente.
> 
> Se possível, crie seus cofres em regiões não emparelhadas. As regiões emparelhadas do Azure fornecem alta disponibilidade entre domínios de falha de serviço. Portanto, pares regionais podem ser pensados como a região de backup uns dos outros. Isso significa que um recurso do Azure colocado em uma região está ganhando automaticamente tolerância a falhas por meio da região emparelhada. Por esse motivo, escolher regiões para dois cofres usados em uma política de criptografia de dados onde as regiões estão emparelhadas significa que apenas um total de duas regiões de disponibilidade estão em uso. A maioria das regiões tem apenas duas regiões, portanto, ainda não é possível selecionar regiões não emparelhadas. Se possível, escolha duas regiões não emparelhadas para os dois cofres usados com uma política de criptografia de dados. Isso beneficia-se de um total de quatro regiões de disponibilidade. Para obter mais informações, consulte Continuidade de negócios e recuperação de desastre [(BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) Regiões emparelhadas do Azure para obter uma lista atual de pares regionais.
  
### <a name="assign-permissions-to-each-key-vault"></a>Atribuir permissões a cada cofre de chaves

Você precisará definir três conjuntos separados de permissões para cada cofre de chaves, dependendo da implementação. Por exemplo, você precisará definir um conjunto de permissões para cada um dos seguintes:
  
- **Administradores de cofre de** chaves que fazem o gerenciamento do dia a dia do seu cofre de chaves para sua organização. Essas tarefas incluem backup, criação, obter, importar, listar e restaurar.

  > [!IMPORTANT]
  > O conjunto de permissões atribuídas aos administradores de cofre de chaves não inclui a permissão para excluir chaves. Isso é intencional e uma prática importante. A exclusão de chaves de criptografia normalmente não é feita, pois fazer isso destrói permanentemente os dados. Como prática prática, não conceda essa permissão aos administradores do cofre de chaves por padrão. Em vez disso, reserve-o para colaboradores do key vault e atribua-o apenas a um administrador a curto prazo, uma vez que uma compreensão clara das consequências seja compreendida.
  
  Para atribuir essas permissões a um usuário em sua organização, entre em sua assinatura do Azure com o Azure PowerShell. Para obter instruções, [confira Entrar com o Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- Execute o Set-AzKeyVaultAccessPolicy cmdlet para atribuir as permissões necessárias.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por exemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores do key vault** que podem alterar permissões no próprio Azure Key Vault. Você precisará alterar essas permissões à medida que os funcionários saírem ou ingressarem em sua equipe. Na rara situação em que os administradores de cofre de chaves precisam de permissão para excluir ou restaurar uma chave, você também precisará alterar as permissões. Esse conjunto de colaboradores do key vault precisa ter a função **Colaborador** no cofre de chaves. Você pode atribuir essa função usando o Gerenciador de Recursos do Azure. Para etapas detalhadas, confira Usar Role-Based Controle de Acesso para gerenciar o acesso aos recursos de [assinatura do Azure.](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) O administrador que cria uma assinatura tem esse acesso implicitamente e a capacidade de atribuir outros administradores à função Colaborador.

- Se você pretende usar a Chave do Cliente com o Exchange Online e o Skype for Business, é necessário dar permissão ao Microsoft 365 para usar o cofre de chaves em nome do Exchange Online e do Skype for Business. Da mesma forma, se você pretende usar a Chave do Cliente com o SharePoint Online e o OneDrive for Business, é necessário adicionar permissão para o Microsoft 365 usar o cofre de chaves em nome do SharePoint Online e do OneDrive for Business. Para dar permissão ao Microsoft 365, execute o cmdlet **Set-AzKeyVaultAccessPolicy** usando a seguinte sintaxe:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Onde:

    - *O nome do* cofre é o nome do cofre de chaves que você criou.

    - Para o Exchange Online e o Skype for Business, substitua  *o Office 365 appID* por `00000002-0000-0ff1-ce00-000000000000`

    - Para arquivos do SharePoint Online, OneDrive for Business e Teams, substitua  *o Office 365 appID* por `00000003-0000-0ff1-ce00-000000000000`

  Exemplo: Definindo permissões para o Exchange Online e o Skype for Business:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Exemplo: configurando permissões para arquivos do SharePoint Online, OneDrive for Business e Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar e confirmar a exclusão suave em seus cofres de chaves

Quando você pode recuperar suas chaves rapidamente, é menos provável que uma paralisação de serviço estendida seja devido a chaves excluídas acidentalmente ou maliciosamente. Você precisa habilitar essa configuração, conhecida como Exclusão Suave, antes de poder usar suas chaves com a Chave do Cliente. A habilitação da Exclusão Suave permite que você recupere chaves ou cofres dentro de 90 dias após a exclusão sem precisar restaurá-los do backup.
  
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

Para importar uma chave diretamente para o cofre de chaves, você precisa ter um Módulo de Segurança de Hardware nCipher nShield.
  
Algumas organizações preferem essa abordagem para estabelecer a proveniência de suas chaves e, em seguida, esse método também fornece os seguintes atestados:
  
- O toolset usado para importação inclui o atestado de nCipher de que o KEK (Key Exchange Key) usado para criptografar a chave gerada não é exportável e é gerado dentro de um HSM original que foi fabricado por nCipher.

- O toolset inclui o atestado de nCipher de que o mundo de segurança do Azure Key Vault também foi gerado em um HSM original fabricado por nCipher. Esse atestado prova que a Microsoft também está usando hardware nCipher original.

Verifique com seu grupo de segurança para determinar se os atestados acima são necessários. Para etapas detalhadas para criar uma chave local e importá-la para o cofre de chaves, confira Como gerar e transferir chaves protegidas por HSM para o [Azure Key Vault.](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) Use as instruções do Azure para criar uma chave em cada cofre de chaves.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Verificar o nível de recuperação de suas chaves

O Microsoft 365 requer que a assinatura do Azure Key Vault seja definida como Não Cancelar e que as chaves usadas pela Chave do Cliente tenham a exclusão suave habilitada. Você pode confirmar as configurações de assinaturas observando o nível de recuperação em suas chaves.
  
Para verificar o nível de recuperação de uma chave, no Azure PowerShell, execute o cmdlet Get-AzKeyVaultKey seguinte:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Se a propriedade _Nível_ de Recuperação retornar algo diferente de um valor **recoverable+ProtectedSubscription**, certifique-se de que você colocou a assinatura na lista Não Cancelar e se você tem a exclusão suave habilitada em cada um dos seus cofres de chaves.
  
### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Imediatamente após a criação ou qualquer alteração em uma chave, execute um backup e armazene cópias do backup, online e offline. Cópias offline não devem ser conectadas a nenhuma rede, como em um local de armazenamento físico seguro ou comercial. Pelo menos uma cópia do backup deve ser armazenada em um local que poderá ser acessado em caso de desastre. Os blobs de backup são o único meio de restaurar material de chave caso uma chave do Key Vault seja destruída permanentemente ou, de outra forma, inoperante. As chaves externas ao Azure Key Vault e que foram importadas para o Azure Key Vault não se qualificam como um backup porque os metadados necessários para a Chave do Cliente usar a chave não existem com a chave externa. Somente um backup feito do Azure Key Vault pode ser usado para operações de restauração com a Chave do Cliente. Portanto, você deve criar um backup do Azure Key Vault depois de carregar ou criar uma chave.
  
Para criar um backup de uma chave do Azure Key Vault, execute o cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) da seguinte forma:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Verifique se o arquivo de saída usa o `.backup` sufixo.
  
O arquivo de saída resultante desse cmdlet é criptografado e não pode ser usado fora do Azure Key Vault. O backup só pode ser restaurado para a assinatura do Azure da qual o backup foi feito.
  
> [!TIP]
> Para o arquivo de saída, escolha uma combinação do nome do cofre e do nome da chave. Isso fará com que o nome do arquivo se descrevendo. Ele também garantirá que os nomes dos arquivos de backup não colidam.
  
Por exemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar as definições de configuração do Azure Key Vault

Validar antes de usar chaves em um DEP é opcional, mas altamente recomendável. Se você usar etapas para configurar suas chaves e cofres diferentes dos descritos neste artigo, valide a saúde dos recursos do Azure Key Vault antes de configurar a Chave do Cliente.
  
Para verificar se suas chaves têm `get` `wrapKey` e as operações `unwrapKey` habilitadas:
  
Execute o cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Na saída, procure a Política de Acesso e a GUID (identidade do Exchange Online) ou a guid (identidade) do SharePoint Online, conforme apropriado. Todas as três permissões acima devem ser mostradas em Permissões para Chaves.
  
Se a configuração da política de acesso estiver incorreta, execute o cmdlet Set-AzKeyVaultAccessPolicy seguinte:
  
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

Para verificar se uma data de expiração não está definida para suas chaves, execute o cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) da seguinte forma:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

A Chave do Cliente não pode usar uma chave expirada. As operações tentadas com uma chave expirada falharão e possivelmente resultarão em uma paralisação de serviço. É fortemente recomendável que as chaves usadas com a Chave do Cliente não tenham uma data de expiração. Uma data de expiração, uma vez definida, não pode ser removida, mas pode ser alterada para uma data diferente. Se for necessário usar uma chave que tenha uma data de expiração definida, altere o valor de expiração para 31/12/9999. Chaves com uma data de expiração definida para uma data diferente de 31/12/9999 não passarão na validação do Microsoft 365.
  
Para alterar uma data de expiração que tenha sido definida para qualquer valor diferente de 31/12/9999, execute o cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) da seguinte forma:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Não de definir datas de expiração em chaves de criptografia usadas com a Chave do Cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtenha o URI de cada chave do Azure Key Vault

Depois de configurar seus cofres de chaves e adicionar suas chaves, execute o seguinte comando para obter o URI da chave em cada cofre de chaves. Você precisará usar esses URIs ao criar e atribuir cada DEP posteriormente, portanto, salve essas informações em um local seguro. Execute este comando uma vez para cada cofre de chaves.
  
No Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Configurando a chave do cliente para o Exchange Online e o Skype for Business

Antes de começar, verifique se concluiu as tarefas necessárias para configurar o Azure Key Vault. Confira [Tarefas completas no Azure Key Vault e no Microsoft FastTrack para obter informações.](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)
  
Para configurar a Chave do Cliente para o Exchange Online e o Skype for Business, você concluirá estas etapas conectando-se remotamente ao Exchange Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Criar uma política de criptografia de dados (DEP) para uso com o Exchange Online e o Skype for Business

Uma DEP é associada a um conjunto de chaves armazenadas no Azure Key Vault. Você atribui um DEP a uma caixa de correio no Microsoft 365. O Microsoft 365 usará as chaves identificadas na política para criptografar a caixa de correio. Para criar a DEP, você precisa dos URIs do Key Vault obtidos anteriormente. Consulte [Obter o URI de cada chave do Azure Key Vault para](#obtain-the-uri-for-each-azure-key-vault-key) obter instruções.
  
Lembre-se! Ao criar uma DEP, você especifica duas chaves em dois Azure Key Vaults diferentes. Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar a DEP, siga estas etapas:
  
1. No computador local, usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online em uma janela do Windows PowerShell.

2. Para criar um DEP, use o cmdlet New-DataEncryptionPolicy digitando o comando a seguir.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Onde:

   - *PolicyName* é o nome que você deseja usar para a política. Os nomes não podem conter espaços. Por exemplo, USA_mailboxes.

   - *A Descrição* da Política é uma descrição amigável da política que ajudará você a se lembrar para que a política é. Você pode incluir espaços na descrição. Por exemplo, "Chave raiz para caixas de correio nos EUA e seus territórios".

   - *KeyVaultURI1* é o URI da primeira chave na política. Por exemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* é o URI da segunda chave na política. Por exemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separe os dois URIs por uma vírgula e um espaço.

   Exemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Atribuir um DEP a uma caixa de correio

Atribua a DEP a uma caixa de correio usando o Set-Mailbox cmdlet. Depois de atribuir a política, o Microsoft 365 pode criptografar a caixa de correio com a chave identificada na DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailboxIdParameter especifica* uma caixa de correio de usuário. Para obter mais informações sobre o Set-Mailbox cmdlet, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Em ambientes híbridos, você pode atribuir um DEP aos dados de caixa de correio local que são sincronizados em seu locatário do Exchange Online. Para atribuir um DEP a esses dados de caixa de correio sincronizados, você usará o cmdlet Set-MailUser sincronizado. Para obter mais informações sobre dados de caixa de correio no ambiente híbrido, consulte caixas de correio locais usando o Outlook para iOS e Android com [autenticação moderna híbrida.](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Onde *MailUserIdParameter especifica* um usuário de email (também conhecido como um usuário habilitado para email). Para obter mais informações sobre Set-MailUser cmdlet, consulte [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser).
  
### <a name="validate-mailbox-encryption"></a>Validar a criptografia de caixa de correio

Criptografar uma caixa de correio pode levar algum tempo. Para a atribuição de política pela primeira vez, a caixa de correio também deve se mover completamente de um banco de dados para outro para que o serviço possa criptografar a caixa de correio. Recomendamos que você aguarde 72 horas antes de tentar validar a criptografia depois de alterar uma DEP ou da primeira vez que atribuir um DEP a uma caixa de correio.
  
Use o Get-MailboxStatistics cmdlet para determinar se uma caixa de correio está criptografada.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

A propriedade IsEncrypted retornará um valor verdadeiro se a  caixa de correio estiver criptografada e um valor falso se a caixa de correio não estiver criptografada.  O tempo para concluir as movimentações de caixa de correio depende do número de caixas de correio às quais você atribui uma DEP pela primeira vez e do tamanho das caixas de correio. Se as caixas de correio não foram criptografadas após uma semana a partir do momento em que você atribuiu a DEP, entre em contato com a Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: Configurando a chave do cliente para arquivos do SharePoint Online, OneDrive for Business e Teams

Antes de começar, verifique se concluiu as tarefas necessárias para configurar o Azure Key Vault. Consulte [Tarefas completas no Azure Key Vault e no Microsoft FastTrack para obter informações](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) sobre a Chave do Cliente.
  
Para configurar a Chave do Cliente para os arquivos do SharePoint Online, do OneDrive for Business e do Teams, você conclui essas etapas remotamente conectando-se ao SharePoint Online com o Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Criar uma política de criptografia de dados (DEP) para cada área geográfica do SharePoint Online e do OneDrive for Business

Você associa um DEP a um conjunto de chaves armazenado no Azure Key Vault. Você aplica uma DEP a todos os seus dados em uma localização geográfica, também chamada de localização geográfica. Se você usar o recurso multi-geo do Office 365, poderá criar uma DEP por geo com a capacidade de usar chaves diferentes por geo. Se você não estiver usando a multi-geo, poderá criar uma DEP em sua organização para uso com arquivos do SharePoint Online, OneDrive for Business e Teams. O Microsoft 365 usa as chaves identificadas na DEP para criptografar seus dados nessa área geográfica. Para criar a DEP, você precisa dos URIs do Key Vault obtidos anteriormente. Confira [Obter o URI de cada chave do Azure Key Vault para](#obtain-the-uri-for-each-azure-key-vault-key) obter instruções.
  
Lembre-se! Ao criar uma DEP, você especifica duas chaves em dois Azure Key Vaults diferentes. Crie essas chaves em duas regiões separadas do Azure para garantir a redundância geográfica.
  
Para criar uma DEP, você precisa se conectar remotamente ao SharePoint Online usando o Windows PowerShell.
  
1. No computador local, usando uma conta de trabalho ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao PowerShell do [SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)

2. No Shell de Gerenciamento do Microsoft SharePoint Online, execute o cmdlet Register-SPODataEncryptionPolicy seguinte:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Exemplo:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Quando você registra a DEP, a criptografia começa nos dados na área geográfica. A criptografia pode levar algum tempo. Para obter mais informações sobre como usar esse parâmetro, [consulte Register-SPODataEncryptionPolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true).

### <a name="validate-file-encryption"></a>Validar a criptografia de arquivo

 Para validar a criptografia dos arquivos do SharePoint Online, do OneDrive for Business e do Teams, conecte-se ao PowerShell do [SharePoint Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)e use o cmdlet Get-SPODataEncryptionPolicy para verificar o status do seu locatário. A _propriedade State_ retornará um valor registrado se a criptografia de Chave de Cliente estiver habilitada e todos os arquivos em todos os sites foram criptografados.  Se a criptografia ainda estiver em andamento, este cmdlet fornece informações sobre a porcentagem de sites concluída.

## <a name="related-articles"></a>Artigos relacionados

- [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md)

- [Gerenciar Chave do Cliente](customer-key-manage.md)

- [Rolar ou girar uma Chave de Cliente ou uma chave de disponibilidade](customer-key-availability-key-roll.md)

- [Saiba mais sobre a chave de disponibilidade](customer-key-availability-key-understand.md)

- [Criptografia de Serviço](office-365-service-encryption.md)
