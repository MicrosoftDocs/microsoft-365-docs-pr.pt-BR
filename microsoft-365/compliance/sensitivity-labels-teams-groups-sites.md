---
title: Use rótulos de confidencialidade do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Use rótulos de confidencialidade para proteger o conteúdo nos sites do SharePoint, Microsoft Teams e grupos do Microsoft 365.
ms.openlocfilehash: d0ac249483d888b76915e98429b72da88884e135
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357783"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Além de usar [rótulos de confidencialidade](sensitivity-labels.md) para classificar e proteger documentos e emails, você também pode usar rótulos de confidencialidade para proteger o conteúdo nos seguintes contêineres: sites de Microsoft Teams, grupos de Microsoft 365 groups ([antigos grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) e sites do SharePoint. Para a classificação e a proteção de nível de contêiner, use as seguintes configurações de etiqueta:

- Privacidade (pública ou privada) dos sites de equipes conectadas ao grupo do Microsoft 365
- Acesso de usuários externos
- Acesso de dispositivos não gerenciados

> [!IMPORTANT]
> O **Acesso por dispositivos não gerenciados** funciona em conjunto com o recurso SharePoint para [controlar o acesso por dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices). Você deve configurar este recurso dependente do SharePoint para que seu locatário use uma etiqueta confidencial que tenha essa configuração definida. Informações adicionais estão incluídas nas instruções abaixo.

Quando você aplica esse rótulo de confidencialidade a um contêiner suportado, o rótulo aplica automaticamente as opções configuradas ao site ou grupo conectado.

O conteúdo desses contêineres, no entanto, não herda os rótulos da classificação e configurações como marcações visuais ou criptografia. Para que os usuários possam rotular seus documentos em sites do SharePoint ou em sites de equipe, [habilite rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

> [!NOTE]
> Os rótulos de confidencialidade de contêineres não têm suporte com o CDNs (redes de distribuição de conteúdo) do Office 365.

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Use rótulos de confidencialidade para Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint

Antes de habilitar os rótulos de confidencialidade para contêineres e configurar rótulos de confidencialidade para as novas configurações, os usuários podem ver e aplicar rótulos de confidencialidade em seus aplicativos. Por exemplo, no Word:

![Um rótulo de confidencialidade exibido no aplicativo Word para área de trabalho](../media/sensitivity-label-word.png)

Depois de habilitar e configurar os rótulos de confidencialidade para os contêineres, os usuários também podem ver e aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint. Por exemplo, quando você cria um novo site de equipe no SharePoint:

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a>Como habilitar rótulos de confidencialidade para contêineres e sincronizar rótulos

1. Como esse recurso usa a funcionalidade do Azure Active Directory, siga as instruções na documentação do Azure Active Directory para habilitar o suporte de rótulos de confidencialidade: [Atribuir rótulos de confidencialidade aos grupos do Microsoft 365 no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).

2. Agora, você precisa sincronizar seus rótulos de sensibilidade com o Azure Active Directory. Primeiro, [conecte-se ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

   Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global.

3. Execute o seguinte comando para assegurar seus rótulos de confidencialidade possam ser usados com os grupos do Microsoft 365:

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a>Como definir as configurações de site e grupo

Agora você está pronto para criar ou editar os rótulos de confidencialidade que deseja disponibilizar para sites e grupos. Habilitar os rótulos de confidencialidade para contêineres torna uma nova página visível nas assistentes de rotulagem de confidencialidade: **Configurações de site e grupo**

Se precisar de ajuda para criar ou editar um rótulo de confidencialidade, confira as instruções em [Criar e configurar os rótulos de confidencialidade](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).

Nesta nova página **Configurações de site e grupo**, defina as configurações:

- **Privacidade dos sites de equipes conectados ao grupo do Office 365**: Manter a configuração padrão de **Público - qualquer pessoa em sua organização pode acessar o site **se você quiser que todos na sua organização acessem o site de equipe ou grupo no qual o rótulo foi aplicado.

  Selecione **Particular** se desejar que o acesso seja restrito apenas a membros aprovados da sua organização.

  Selecione **Nenhuma - permita que o usuário tenha acesso ao site** quando desejar proteger o conteúdo do contêiner usando o rótulo de confidencialidade, mas ainda permita que os usuários configurem a própria configuração de privacidade.

  Selecione **Pública** ou **Privada** para definir e bloquear a configuração de privacidade quando você aplicar esse rótulo ao contêiner. A configuração escolhida substituirá qualquer configuração de privacidade anterior que possa ser configurada para a equipe ou grupo, e bloqueará o valor de privacidade para que ele possa ser alterado apenas pela primeira remoção da etiqueta de confidencialidade do contêiner. Depois de remover o rótulo de confidencialidade, a configuração de privacidade do rótulo permanece e os usuários agora podem alterá-lo novamente.

- **Acesso de usuários externos**: Controle se o proprietário do grupo pode [adicionar convidados ao grupo](/office365/admin/create-groups/manage-guest-access-in-groups).

- **Dispositivos não administrados**: Para essa opção, você também deve configurar o recurso do SharePoint que usa o acesso condicional do Azure AD para bloquear ou limitar o acesso ao conteúdo do SharePoint e OneDrive de dispositivos não gerenciados. Para obter instruções, consulte [Controle de acesso de dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices). A opção que você especificar para esta configuração de rótulo equivale ao [bloqueio ou limitação de acesso a um site do SharePoint específico ou ao OneDrive](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive).
    
    Se você não configurar o recurso dependente do SharePoint, a opção que você especificar aqui não terá efeito. Além disso, não terá efeito se for menos restritivo do que a configuração definida ao nível do locatário. Escolha uma configuração de rótulo que seja a mesma que a configuração de nível do locatário, ou mais restritiva.
    
    Por exemplo, se seu locatário estiver configurado para **Permitir acesso limitado apenas à Web**, a configuração de rótulo que permite acesso total não terá efeito porque é menos restritiva. Para esta configuração de nível de locatário, escolha a configuração de rótulo para bloquear o acesso (mais restritiva) ou a configuração de rótulo para acesso limitado (a mesma que a configuração do locatário).
    
    Como você pode configurar o recurso do SharePoint independentemente da configuração do rótulo, não há verificação no assistente do rótulo de confidencialidade de que as dependências estejam no lugar.

![Guia configurações de site e grupo](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> Somente essas configurações de site e grupo entrarão em vigor quando você aplicar um rótulo a uma equipe, grupo ou site. Outras configurações de rótulo, como criptografia e marcação de conteúdo, não são aplicadas ao conteúdo da equipe, grupo ou site.
>
> Implementação gradual para locatários: Somente os rótulos com as configurações de site e grupo estarão disponíveis para seleção quando os usuários criarem equipes, grupos e sites. Se você pode aplicar um rótulo a um contêiner quando o rótulo não possui as configurações de site e grupo ativadas, apenas o nome do rótulo é aplicado ao contêiner.

Se o seu rótulo de confidencialidade ainda não estiver publicado, publique-o agora [adicionando-o a uma política de rótulo de confidencialidade](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). Os usuários aos quais tenha sido atribuída uma política de rótulo de confidencialidade que inclua esse rótulo poderão selecioná-lo para sites e grupos.

Na política de rótulo, apenas a configuração de política **Aplicar esta etiqueta por padrão aos documentos e o email** é válida quando você aplica esse rótulo aos contêineres. Outras configurações de política não são aplicadas, as que incluem rotulagem obrigatória, exigindo justificativa do usuário e um link para a página de ajuda personalizada.

## <a name="sensitivity-label-management"></a>Gerenciamento de rótulo de confidencialidade

Use as diretrizes a seguir para criar, modificar ou excluir rótulos de confidencialidade que estão configurados para sites e grupos.

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a>Criar e publicar rótulos configurados para sites e grupos

Quando um novo rótulo de confidencialidade é criado e publicado, torna-se visível para os usuários em equipes, grupos e sites dentro de uma hora. No entanto, se tiver modificado um rótulo existente será preciso aguardar até 24 horas. Use as diretrizes a seguir para publicar um rótulo para seus usuários quando esse rótulo estiver configurado para as configurações de site e de grupo:

1. Depois de criar e configurar o rótulo de confidencialidade, adicione esse rótulo a uma política de rótulo que se aplica a apenas alguns usuários de teste.

2. Aguarde o seguinte prazo para que a alteração seja replicada:

   - Rótulo novo: aguarde uma hora.
   - Rótulo existente: aguarde 24 horas.

3. Após esse período de espera, use uma das contas de usuário de teste para criar uma equipe, grupo do Microsoft 365 ou site do SharePoint com o rótulo que você criou na etapa 1.

4. Se não houver erros durante a operação de criação, você saberá que é seguro publicar o rótulo para todos os usuários em seu locatário.

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a>Modificar rótulos publicados que estão configurados para sites e grupos

Como prática recomendada, não altere as configurações de site e grupo de um rótulo de confidencialidade após aplicá-lo a várias equipes, grupos ou sites. Se decidir fazer isso, lembre-se de aguardar até 24 horas para que as alterações sejam replicadas para todos os contêineres que têm o rótulo aplicado.

Além disso, se suas alterações incluírem a configuração de **Acesso de usuários externos**:

- A nova configuração aplica-se a novos usuários, mas não a usuários existentes. Por exemplo, se essa configuração tiver sido selecionada anteriormente e, como resultado, os usuários convidados acessarem o site. esses usuários convidados ainda poderão acessar o site depois que essa configuração for limpa na configuração do rótulo.

- As configurações de privacidade para as propriedades do grupo hiddenMembership e roleEnabled não são atualizadas.

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a>Excluindo rótulos publicados que estão configurados para sites e grupos

Se você excluir um rótulo de confidencialidade com as configurações de site e grupo ativadas e esse rótulo estiver incluído em uma ou mais políticas de rótulo, essas ações poderão resultar em falhas na criação de todas as equipes, grupos e sites. Para evitar essa situação, use as instruções a seguir:

1. Remova o rótulo de confidencialidade de todas as políticas de rótulo que incluam o rótulo.

2. Aguarde uma hora.

3. Após esse período de espera, tente criar uma equipe, grupo ou site e confirme se o rótulo não está mais visível.

4. Se a etiqueta de confidencialidade não estiver visível, agora você pode excluí-la com segurança.

## <a name="how-to-apply-sensitivity-labels-to-containers"></a>Como aplicar rótulos de confidencialidade aos contêineres

Agora você está pronto para aplicar os rótulos ou rótulos de confidencialidade aos seguintes contêineres:

- [Grupo do Microsoft 365 no Azure Active Directory](#apply-sensitivity-labels-to-microsoft-365-groups)
- [Site de equipe do Microsoft Teams](#apply-a-sensitivity-label-to-a-new-team)
- [Grupo do Microsoft 365 no Outlook na Web](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [Site do Microsoft Office SharePoint Online](#apply-a-sensitivity-label-to-a-new-site)

Você pode usar o Windows PowerShell se precisar [aplicar um rótulo de confidencialidade a vários sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a>Aplicar rótulos de confidencialidade aos grupos do Microsoft 365

Agora você está pronto para aplicar os rótulos ou rótulos de confidencialidade aos grupos do Microsoft 365. Retorne à documentação do Azure AD para obter instruções:

- [Atribuir um rótulo a um novo grupo no portal do Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [Atribuir um rótulo a um grupo existente no portal do Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- [Remover um rótulo de um grupo existente no portal do Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).

### <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar um rótulo de confidencialidade a uma nova equipe

Os usuários podem selecionar os rótulos de confidencialidade ao criar novas equipes no Microsoft Teams. Quando eles selecionam o rótulo na lista suspensa **Confidencialidade**, a configuração de privacidade pode mudar para refletir a configuração de rótulo. Dependendo da configuração de acesso de usuários externos que você selecionou para o rótulo, os usuários podem ou não adicionar pessoas de fora da organização à equipe.

[Saiba mais sobre Rótulos de confidencialidade](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![A configuração de privacidade ao criar uma nova equipe](../media/privacy-setting-new-team.png)

Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.

![O rótulo de confidencialidade aparece na equipe](../media/privacy-setting-teams.png)

O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Microsoft 365 e ao site de equipe do SharePoint conectado.

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Aplicar um rótulo de confidencialidade a um novo grupo no Outlook na Web

No Outlook na Web, ao criar um novo grupo, você pode selecionar ou alterar a opção de **Confidencialidade** para rótulos publicados:

![Criando um grupo e selecionando uma opção em Confidencialidade](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar um rótulo de confidencialidade a um novo site

Os administradores e os usuários finais podem selecionar os rótulos de confidencialidade ao [criar sites de equipe e sites de comunicação modernos](/sharepoint/create-site-collection) e expandir as **Configurações avançadas**:

![Criando um site e selecionando uma opção de confidencialidade](../media/sensitivity-label-new-communication-site.png)

A caixa suspensa exibe os nomes dos rótulos para a seleção e o ícone de ajuda exibe todos os nomes dos rótulos com a dica de ferramenta, o que pode ajudar os usuários a determinar o rótulo correto a ser aplicado.

Quando o rótulo é aplicado e os usuários navegam no site, eles veem o nome do rótulo e as políticas aplicadas. Por exemplo, este site foi rotulado como **Confidencial** e a configuração de privacidade está definida como **Privada**:

![Um site com uma etiqueta de confidencialidade aplicada](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a>Usar o Windows PowerShell para aplicar um rótulo de confidencialidade a vários sites

Você pode usar o cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) e [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) com o parâmetro *SensitivityLabel* do atual [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) para aplicar um rótulo de confidencialidade a vários sites. Os sites podem ser um conjunto de sites do Microsoft Office SharePoint Online ou um site do OneDrive.

Verifique se você tem a versão 16.0.19418.12000 ou posterior do Shell de gerenciamento do SharePoint Online.

1. Abra uma sessão do Windows PowerShell com a opção **Executar como administrador**.

2. Se você não souber o GUID de seu rótulo: [Conectar ao Centro de Segurança e Conformidade do PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) e obter a lista de rótulos de confidencialidade e seus GUIDs.

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. Agora [conectar-se ao SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e armazenar o GUID de seu rótulo como uma variável. Por exemplo:

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. Criar uma nova variável que identifique vários sites com uma cadeia de caracteres de identificação em comum na URL. Por exemplo:

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. Execute o seguinte comando para aplicar o rótulo a esses sites. Usando nossos exemplos:

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

Para aplicar diferentes rótulos a diferentes sites, repita o seguinte comando para cada site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Exibir e gerenciar rótulos de confidencialidade no Centro de Administração do SharePoint Online

Para exibir, classificar e pesquisar os rótulos de confidencialidade aplicados, use a página de **Sites ativos** no novo Centro de Administração do SharePoint Online. Talvez seja necessário adicionar primeiro a coluna **Confidencialidade**:

![A coluna Confidencialidade na página sites ativos](../media/manage-site-sensitivity-labels.png)

Para obter mais informações sobre como gerenciar sites na página de sites ativos, inclusive como adicionar uma coluna, confira [Gerenciar sites no novo Centro de Administração do SharePoint Online](/sharepoint/manage-sites-in-new-admin-center).

Você também pode alterar e aplicar um rótulo da seguinte página:

1. Selecione o nome do site para abrir o painel de detalhes.

2. Selecione a guia **Políticas** e, em seguida, selecione **Editar** para a configuração de **Confidencialidade**.

3. No painel **Editar configuração de confidencialidade**, selecione o rótulo de confidencialidade que você deseja aplicar ao site e, em seguida, selecione **Salvar**.

## <a name="support-for-sensitivity-labels"></a>Suporte de rótulos de confidencialidade.

Os seguintes aplicativos e serviços oferecem suporte as etiquetas de confidencialidade configuradas para configurações de sites e grupos:

- Centros de administração:

  - Centro de administração do SharePoint
  - Portal do Azure Active Directory
  - Centro de conformidade do Microsoft 365, Centro de segurança do Microsoft 365, Centro de Conformidade e Segurança.

- Aplicativos e serviços do usuário:

  - Microsoft Office SharePoint Online
  - Teams
  - Outlook na Web e para Windows, MacOS, iOS e Android
  - Formulários
  - Fluxo

Os seguintes aplicativos e serviços não oferecem suporte as etiquetas de confidencialidade configuradas para configurações de sites e grupos:

- Centros de administração:

  - Centro de administração do Microsoft 365
  - Centro de administração do Teams
  - Centro de administração do Exchange

- Aplicativos e serviços do usuário:

  - Dynamics 365
  - Yammer
  - Planner
  - Project
  - Power BI

## <a name="classic-azure-ad-group-classification"></a>Classificação clássica de grupo do Azure Active Directory

O Microsoft 365 não oferece mais suporte às classificações antigas para novos grupos do Microsoft 365 e sites do SharePoint quando você habilita os rótulos de confidencialidade para contêineres. No entanto, os grupos e sites existentes que oferecem suporte a rótulos de confidencialidade ainda exibem os valores de classificação antigos, até que você os converta para usar rótulos de confidencialidade.

Como um exemplo de como você pode ter usado a classificação de grupo antiga do SharePoint, confira [Classificação de sites “moderna”](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Essas classificações foram configuradas usando o Azure AD PowerShell ou a biblioteca Principal do PnP e definindo valores para a configuração do `ClassificationList`. Se seu locatário tiver valores de classificação definidos, eles serão mostrados quando você executar o seguinte comando no [módulo AzureADPreview PowerShell](https://www.powershellgallery.com/packages/AzureADPreview):

```powershell
($setting["ClassificationList"])
```

Para converter suas classificações antigas em rótulos de confidencialidade, siga um destes procedimentos:

- Usar rótulos existentes: Especifique as configurações de rótulo desejadas para sites e grupos editando rótulos de confidencialidade existentes que já foram publicados.

- Criar novos rótulos: Especifique as configurações de rótulos desejados para sites e grupos, criando e publicando novos rótulos de confidencialidade que tenham os mesmos nomes das suas classificações existentes.

Depois:

1. Use o PowerShell para aplicar os rótulos de confidencialidade a grupos existentes do Microsoft 365 e sites do SharePoint usando o mapeamento de nomes. Confira a seção a seguir para obter instruções.

2. Remova as classificações antigas dos grupos e sites existentes.

Embora você não possa impedir que os usuários criem novos grupos em aplicativos e serviços que ainda não suportam rótulos de confidencialidade, é possível executar um script recorrente do PowerShell para procurar novos grupos que os usuários criaram com as classificações antigas e convertê-los para uso de rótulos de confidencialidade.

Para ajudar você a gerenciar a coexistência de rótulos de sensibilidade e classificações do Azure Active Directory para sites e grupos, confira [rótulos de classificação e confidencialidade do Azure Active Directory para grupos do Microsoft 365](migrate-aad-classification-sensitivity-labels.md).

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>Use o PowerShell para converter classificações de grupos do Microsoft 365 em rótulos de confidencialidade

1. Primeiro, [conecte-se ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

   Por exemplo, em uma sessão do PowerShell que você executa como administrador, entre com uma conta de administrador global:

2. Obtenha a lista de rótulos de confidencialidade e suas GUIDs usando o cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps):

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. Anote o GUIDe dos rótulos de confidencialidade que você deseja aplicar a seus grupos do Microsoft 365.

4. Agora [conecte-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) em uma janela separada do Windows PowerShell.

5. Use o seguinte comando como exemplo para obter a lista de grupos que atualmente têm a classificação "Geral":

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, adicione o novo GUID de rótulo de confidencialidade. Por exemplo:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. Repita as etapas 5 e 6 para as classificações de grupo restantes.

## <a name="auditing-sensitivity-label-activities"></a>Atividades de rótulo de confidencialidade de auditoria

Se alguém enviar um documento para um site protegido por um rótulo de confidencialidade e o documento tiver um rótulo de confidencialidade com [prioridade mais alta](sensitivity-labels.md#label-priority-order-matters) que o rótulo de confidencialidade aplicado ao site, essa ação não será bloqueada. Por exemplo, você aplicou o rótulo **Geral** a um site do SharePoint e alguém carrega neste site um documento chamado **Confidencial**. Como um rótulo de confidencialidade com prioridade mais alta identifica o conteúdo que é mais confidencial do que o conteúdo com ordem de prioridade mais baixa, essa situação pode ser um problema de segurança.

Embora a ação não seja bloqueada, ela é auditada e gera automaticamente um email para a pessoa que carregou o documento e para o administrador do site. Como resultado, tanto o usuário como os administradores podem identificar documentos que tenham esse desalinhamento da prioridade do rótulo e tomar medidas, se necessário. Por exemplo, excluir ou mover o documento carregado do site.

Não seria um problema de segurança se o documento tivesse um rótulo de confidencialidade de prioridade mais baixa que o rótulo de confidencialidade aplicado ao site. Por exemplo, um documento chamado **Geral** é carregado em um site chamado **Confidencial**. Neste cenário, um evento de auditoria e email não são gerados.

Para pesquisar o log de auditoria para esse evento, procure por **Incompatibilidade de confidencialidade em documento detectada** na categoria **Atividades de arquivo e página**.

O email gerado automaticamente tem o assunto **Rótulo de confidencialidade incompatível detectado** e a mensagem do email explica a incompatibilidade de rótulo com um link para o documento e o site carregados. Ele também contém um link de documentação que explica como os usuários podem alterar o rótulo de confidencialidade. Atualmente, não é possível desabilitar ou personalizar esses emails.

Quando alguém adiciona ou remove um rótulo de confidencialidade para ou de um site ou grupo, essas atividades também são auditadas, mas não geram um email automático.

Todos esses eventos podem ser encontrados na categoria [Atividades de rótulo de confidencialidade](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities). Para obter instruções sobre como pesquisar o log de auditoria, confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md).

## <a name="how-to-disable-sensitivity-labels-for-containers"></a>Como desabilitar os rótulos de confidencialidade para contêineres

Você pode desativar os rótulos de confidencialidade do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint usando as mesmas instruções de [Habilitar o suporte a rótulo de confidencialidade no PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). No entanto, para desabilitar o recurso, na etapa 5, especifique `$setting["EnableMIPLabels"] = "False"`.

Além de ocultar a página de **Sites e configurações de grupo** quando você cria ou edita rótulos de confidencialidade, essa ação reverte qual propriedade os contêineres usam para a configuração. Habilitar rótulos de confidencialidade para o Microsoft Teams, o Microsoft 365 Groups, e os sites do SharePoint altera a propriedade usada de **Classificação** (usada para [classificação de grupo do Azure Active Direcroty](#classic-azure-ad-group-classification)) para **Confidencialidade**. Quando você desabilita os rótulos de confidencialidade para contêineres, os contêineres ignoram a propriedade Confidencialidade e usam novamente a propriedade de Classificação.

Isso significa que todas as configurações de rótulo de sites e grupos aplicados anteriormente aos contêineres não serão forçadas e os contêineres não exibirão mais os rótulos.

Se esses contêineres tiverem valores de classificação do Azure Active Directory aplicados, eles voltarão a usar as classificações novamente. Lembre-se de que todos os novos sites ou grupos criados depois de habilitar o recurso não exibirão um rótulo ou terão uma classificação. Para esses contêineres e todos os novos contêineres, você pode aplicar valores de classificação. Para saber mais, confira [Classificação de sites modernos do Microsoft Office SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) e [Criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell).

## <a name="additional-resources"></a>Recursos adicionais

Consulte a gravação do seminário on-line e as perguntas respondidas para [Usar rótulos de sensibilidade nos sites Microsoft Teams, O365 Groups e SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).

Esse webinar foi gravado quando o recurso ainda estava na visualização, para que você possa observar algumas discrepâncias na interface do usuário. No entanto, as informações para esse recurso ainda são precisas, com todos os novos recursos documentados nesta página.
