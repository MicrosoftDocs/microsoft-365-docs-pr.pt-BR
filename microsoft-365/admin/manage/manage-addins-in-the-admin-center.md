---
title: Gerenciar suplementos no centro de administração
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba como usar os complementos centralizados para implantar os complementos para usuários e grupos em sua organização.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114196"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Gerenciar suplementos no centro de administração

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Os complementos do Office ajudam a personalizar seus documentos e simplificar a maneira como você acessa informações na Web (confira Começar a usar o [seu complemento do Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Depois que um administrador implanta os complementos para usuários em uma organização, o administrador pode ativar ou desativar os complementos, editar, excluir e gerenciar o acesso aos complementos.

Para obter mais informações sobre como instalar os complementos do centro de administração, consulte Implantar os [complementos no centro de administração.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
  
## <a name="add-in-states"></a>Estados de suplementos

Um complemento pode estar no estado **On** ou **Off.**
  
|**State**|**Como o estado ocorre**|**Impacto**|
|:-----|:-----|:-----|
|**Active**  <br/> |O administrador carregou o complemento e o atribuiu a usuários ou grupos.  <br/> |Os usuários e grupos atribuídos ao complemento o veem nos clientes relevantes.  <br/> |
|**Desativado**  <br/> |O administrador desativou o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> Se o estado do complemento for alterado para Ativo, os usuários e grupos terão acesso a ele novamente.  <br/> |
|**Excluído**  <br/> |O administrador excluiu o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> |
   
Considere a exclusão de um complemento se ninguém mais o estiver usando. Por exemplo, a opção de desligar um complemento pode fazer sentido se um complemento for usado somente durante períodos específicos do ano.

## <a name="delete-an-add-in"></a>Excluir um complemento

Você também pode excluir um complemento que foi implantado.

1. No centro de administração, vá para a página **Serviços**&  >  **configurações.**

     > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas de aplicativos.** Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**

2. Selecione o complemento implantado.

3. Clique em **Excluir Complemento.** Remova o botão Desaixar no canto inferior direito.

4. Valide suas seleções e escolha **Remover o complemento.**

## <a name="edit-add-in-access"></a>Editar o acesso de um complemento

Após a implantação, os administradores também podem gerenciar o acesso do usuário aos complementos.

1. No centro de administração, vá para a página **Serviços**&  >  **configurações.**

     > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas aplicativos**. Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**

2. Selecione o complemento implantado.

3. Clique em **Editar** em **Quem tem Acesso.**

4. Salve as alterações.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir downloads de complementos ao desligar a Office Store em todos os clientes (exceto o Outlook)

> [!NOTE]
> A instalação de um complemento do Outlook é gerenciada por [um processo diferente.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)

Como organização, você pode querer impedir o download de novos complementos do Office da Office Store. Isso pode ser usado em conjunto com a Implantação Centralizada para garantir que somente os complementos aprovados pela organização sejam implantados para usuários dentro da sua organização.
  
**Para desativar a aquisição de um complemento**
  
1. No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas aplicativos**. Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**
    
3. Selecione **aplicativos e serviços de propriedade do usuário.**
    
4. Limpe a opção para permitir que os usuários acessem a Office Store.

Isso impedirá que todos os usuários adquirem os seguintes complementos da loja.
  
- Add-ins for Word, Excel, and PowerPoint 2016 from:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aquisições a partir do **AppSource**
    
- Add-ins within Microsoft 365
    
Um usuário que tentar acessar a loja verá a seguinte mensagem: Desculpe, o **Microsoft 365** foi configurado para impedir a aquisição individual de complementos da Office Store.
  
O suporte para desligar a Office Store está disponível nas seguintes versões:
  
- Windows: 16.0.9001 - Disponível no momento.
    
- Mac: 16.10.18011401 - Disponível no momento.
    
- iOS: 2.9.18010804 - Disponível no momento.
    
- A Web - Disponível no momento.
    
Isso não impede que um administrador use a Implantação Centralizada para atribuir um complemento da Office Store.
  
Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar somente a conta organizacional. Para saber mais, confira [Identidade, autenticação e autorização no Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)  

> [!NOTE]
> Impedir que os usuários acessem a Office Store também os impedirá de [fazer sideload de complementos](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)do Office para teste.

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Mais informações sobre a experiência do usuário final com os complementos

Depois de implantar um add-in, os usuários finais podem começar a [usá-lo](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)em seus aplicativos do Office (confira Começar a usar o seu Complemento do Office). O complemento aparece em todas as plataformas compatíveis com o add-in.
  
Se o complemento for compatível com comandos de complemento, os comandos aparecerão na faixa de opções do Office. No exemplo a seguir, o comando **Pesquisar Citação** aparece **para** o complemento Citações. 

![Faixa de opções do Office com Citações de Pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Se o complemento implantado não dá suporte a comandos de add-in ou se você quiser exibir todos os complementos implantados, poderá exibi-los por meio de Meus **Complementos.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>No Word 2016, Excel 2016 ou PowerPoint 2016

1. Selecione **Inserir \> Meus Complementos.** 
    
2. Selecione a **guia Administração** Gerenciada na janela Desem 
    
3. Clique duas vezes no complemento implantado anteriormente (neste exemplo, **Citações** ). <br/>![Guia Administração Gerenciada da página Desem que o Office Add-ins](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>No Outlook

1. Na faixa **de opções Página** Home, selecione Obter **Complementos.**<br/>![Botão Armazenar no Outlook](../../media/getaddinsicon.png)
  
2. Selecione **Admin-managed** na nav esquerda. 

## <a name="learn-more"></a>Saiba mais

[Implantar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Saiba mais sobre como criar e [criar Os Complementos do Office.](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)
  
[Use cmdlets do PowerShell de implantação centralizada para gerenciar os complementos.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solução de problemas: o usuário não está vendo os complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Menores e aquisição de complementos da Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
