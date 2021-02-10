---
title: Implantar um site de equipe do SharePoint Online isolado
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Use este guia de implantação passo a passo para criar e configurar um site de equipe do SharePoint Online isolado no Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165494"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Implantar um site de equipe do SharePoint Online isolado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **Resumo:** Implante um novo site de equipe isolado do SharePoint Online com estas instruções passo a passo.

Este artigo é um guia de implantação passo a passo para criar e configurar um site de equipe isolado do SharePoint Online no Microsoft Office 365. Essas etapas assumem o uso dos três grupos padrão do SharePoint e níveis de permissão correspondentes, com um único grupo de acesso baseado no Azure Active Directory (AD) para cada nível de acesso.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: Criar e preencher os grupos de acesso ao site de equipe

Nesta fase, você cria os três grupos de acesso baseados no Azure AD para os três grupos padrão do SharePoint e os preenche com as contas de usuário apropriadas.

> [!NOTE]
> As etapas a seguir presumem que todas as contas de usuário necessárias já existem e que foram atribuídas as licenças apropriadas. Caso não tenha, adicione-os e atribua licenças antes de prosseguir para a etapa 1.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Etapa 1: Listar os administradores do SharePoint Online para o site

Determine o conjunto de contas de usuário correspondentes aos administradores do SharePoint Online para o site de equipe isolado.

Se você estiver gerenciando contas de usuário e grupos por meio do Microsoft 365 e quiser usar o Windows PowerShell, faça uma lista de seus nomes upNs (upns de exemplo: belindan@contoso.com).

### <a name="step-2-list-the-members-for-the-site"></a>Etapa 2: Listar os membros do site

Determine o conjunto de contas de usuário correspondentes aos membros do site de equipe isolado, aqueles que colaborarão em recursos armazenados no site.

Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365 e quiser usar o PowerShell, faça uma lista de seus UPNs. Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.

### <a name="step-3-list-the-viewers-for-the-site"></a>Etapa 3: Listar os visualizadores do site

Determine o conjunto de contas de usuário correspondentes aos visualizadores do site de equipe isolado, aqueles que podem exibir os recursos armazenados no site, mas não modificá-los ou colaborar diretamente em seu conteúdo.

Se você estiver gerenciando contas e grupos de usuários por meio do Microsoft 365 e quiser usar o PowerShell, faça uma lista de seus UPNs. Se houver muitos membros do site, você poderá armazenar a lista de UPNs em um arquivo de texto e adicioná-los todos com um único comando do PowerShell.

Os visitantes do site podem incluir gerenciamento executivo, consultoria jurídica ou participantes entre departamentos.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Etapa 4: Criar os três grupos de acesso para o site no Azure AD

Você precisa criar os seguintes grupos de acesso no Azure AD:

- Administradores de site (que conterão a lista da etapa 1)
- Membros do site (que conterão a lista da etapa 2)
- Visualizadores do site (que conterão a lista da etapa 3)

1. No navegador, vá para o portal do Azure em e entre com as credenciais de uma conta que tenha sido atribuída com a função de Administrador de Gerenciamento de Usuários ou <https://portal.azure.com> Administrador da Empresa.

2. No Portal do Azure, clique em **Azure Active Directory > Grupos**.

3. Na folha **Grupos – Todos os grupos**, clique em **+ Novo grupo**.

4. Na folha **Novo** Grupo:

   - Selecione **Segurança** em **Tipo de grupo**.

   - Digite o nome do grupo no **nome.**

   - Digite uma descrição do grupo na **descrição do grupo.**

   - Escolha **Atribuído** em **Tipo de Associação**.

5. Clique em **Criar** e, em seguida, feche a folha **Grupo**.

6. Repita as etapas de 3 a 5 para seus grupos adicionais.

> [!NOTE]
> Você precisa usar o portal do Azure para criar os grupos para que eles tenham recursos do Office habilitados. Se um site isolado do SharePoint Online for configurado posteriormente como um site Altamente Confidencial com um rótulo de Proteção de Informações do Azure para criptografar arquivos e atribuir permissão a grupos específicos, os grupos permitidos deverão ter sido criados com os recursos do Office habilitados. Você não pode alterar a configuração de recursos do Office de um grupo do Azure AD depois que ele tiver sido criado.

Esta é a configuração resultante com os três grupos de acesso ao site.

![Os três grupos de acesso para sua implantação de um site isolado do SharePoint Online.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Etapa 5. Adicionar as contas de usuário aos grupos de acesso

Nesta etapa, faça o seguinte:

1. Adicione a lista de usuários da etapa 1 ao grupo de acesso de administradores do site.
2. Adicione a lista de usuários da etapa 2 ao grupo de acesso de membros do site.
3. Adicione a lista de usuários da etapa 3 ao grupo de acesso dos visualizadores do site.

Se você estiver gerenciando contas e grupos de usuários por meio do AD DS (Serviços de Domínio Active Directory), adicione usuários aos grupos de acesso apropriados usando os procedimentos normais de gerenciamento de usuários e grupos do AD DS e aguarde a sincronização com sua assinatura do Microsoft 365.

Se você estiver gerenciando contas e grupos de usuários por meio do Office 365, poderá usar o Centro de administração do Microsoft 365 ou o PowerShell. Se você tiver nomes de grupo duplicados para qualquer um dos grupos de acesso, use o centro de administração do Microsoft 365.

Para o centro de administração do Microsoft 365, entre com uma conta de usuário que tenha sido atribuída a função de Administrador de Conta de Usuário ou Administrador da Empresa e use Grupos para adicionar as contas de usuário e grupos apropriados aos grupos de acesso apropriados.

Para o PowerShell, primeiro [conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

Em seguida, use o seguinte bloco de comando para adicionar uma conta de usuário individual a um grupo de acesso:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Se você armazenou os UPNs de contas de usuário para qualquer um dos grupos de acesso em um arquivo de texto, poderá usar o seguinte bloco de comando do PowerShell para adicioná-los todos de uma só vez:

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Para o PowerShell, use o seguinte bloco de comando para adicionar um grupo individual a um grupo de acesso:

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Os resultados devem ser os seguintes:

- O grupo de administradores do site do Azure AD contém as contas de usuário ou grupos de administradores do site
- O grupo de membros do site do Azure AD contém as contas de usuário ou grupos de membros do site
- O grupo de visualizadores do site do Azure AD contém as contas de usuário ou grupos que só podem exibir o conteúdo do site

Valide a lista de membros do grupo para cada grupo de acesso com o centro de administração do Microsoft 365 ou com o seguinte bloco de comando do PowerShell:

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Esta é a configuração resultante com os três grupos de acesso ao site preenchidos com contas de usuário ou grupos.

![Os três grupos de acesso preenchidos com contas de usuário.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: Criar e configurar o site de equipe isolado

Nesta fase, você cria o site isolado do SharePoint Online e configura as permissões para os níveis de permissão padrão do SharePoint Online para usar seus novos grupos de acesso baseados no Azure AD. Por padrão, novos sites de equipe incluem um grupo do Microsoft 365 e outros recursos relacionados, mas neste caso, criaremos um site de equipe sem um grupo do Microsoft 365. Isso permite manter permissões inteiramente por meio do SharePoint.

Primeiro, crie o site de equipe do SharePoint Online com estas etapas.

1. Entre no centro de administração do Microsoft 365 com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. No Centro de administração do Microsoft 365, em **Centros de administração,** clique **em SharePoint**.

3. No centro de administração do SharePoint, **expanda Sites** e clique em **Sites ativos.**

4. Clique **em** Criar e escolha **Outras opções.**

5. In the **Choose a template** list, choose Team **site**.

6. No **nome do** site, digite um nome para o site de equipe.

7. No **administrador principal,** digite a conta com a qual você está conectado.

8. Clique em **Concluir**.

Em seguida, no novo site de equipe do SharePoint Online, configure as permissões.

1. Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.

2. Em **Compartilhamento de** sites, **clique em Alterar como os membros podem compartilhar.**

3. Choose the **Only site owners can share files, folders, and the site**.

4. Definir **Permitir solicitações de acesso** como **Desligado.**

5. Clique em **Salvar**.

6. No painel **Permissões,** clique em **Configurações avançadas de permissões.**

7. Na guia **Permissões** do navegador, clique **\<site name> em Membros** na lista.

8. Em **Pessoas e Grupos**, clique em **Novo**.

9. Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso de membros do site, selecione-o e clique em **Compartilhar.**

10. Clique no botão Voltar de seu navegador.

11. Clique **\<site name> em** Proprietários na lista.

12. Em **Pessoas e Grupos**, clique em **Novo**.

13. Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso de administradores do site, selecione-o e clique em **Compartilhar.**

14. Clique no botão Voltar de seu navegador.

15. Clique **\<site name> em** Visitantes na lista.

16. Em **Pessoas e Grupos**, clique em **Novo**.

17. Na caixa **de** diálogo Compartilhar, digite o nome do grupo de acesso dos visualizadores do site, selecione-o e clique em **Compartilhar.**

18. Feche a guia **Permissões** do navegador.

Os resultados dessas configurações de permissão são:

- O **\<site name> grupo proprietários** do SharePoint contém o grupo de acesso de administradores de site, no qual todos os membros têm o **nível de** permissão Controle total.
- O **\<site name> grupo Membros** do SharePoint contém o grupo de acesso de membros do site, no qual todos os membros têm o **nível de** permissão Editar.
- O **\<site name> grupo Visitantes** do SharePoint contém o grupo de acesso dos visualizadores do site, no qual todos os membros têm o **nível de permissão** Leitura.
- A capacidade dos membros de convidar outros membros ou de não membros solicitarem acesso está desabilitada.

Esta é a configuração resultante com os três grupos do SharePoint para o site configurados para usar os três grupos de acesso, que são preenchidos com contas de usuário ou grupos do Azure AD.

![A configuração final do site isolado do SharePoint Online com grupos de acesso e contas de usuário.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

Você e os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar usando os recursos do site.

## <a name="next-step"></a>Próxima etapa

Quando precisar alterar a associação do grupo de acesso ao site ou criar uma pasta de documentos com permissões personalizadas, confira Gerenciar um site de equipe do [SharePoint Online isolado.](manage-an-isolated-sharepoint-online-team-site.md)

## <a name="see-also"></a>Confira também

[Sites de equipe do SharePoint Online isolados](isolated-sharepoint-online-team-sites.md)

[Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md)

[Gerenciar um site de equipe do SharePoint Online isolado](manage-an-isolated-sharepoint-online-team-site.md)
