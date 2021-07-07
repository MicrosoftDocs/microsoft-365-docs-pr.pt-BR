---
title: Gerenciar suplementos no centro de administração
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Saiba mais sobre como usar os complementos centralizados para implantar os complementos para usuários e grupos em sua organização.
ms.openlocfilehash: ed9086c77cdf10435bae09f76493af6058d2d758
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314382"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Gerenciar suplementos no centro de administração

Office os complementos ajudam você a personalizar seus documentos e a simplificar a maneira como você acessa informações na Web (consulte [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Depois que um administrador implanta os complementos para usuários em uma organização, o administrador pode desativar ou ativar os complementos, editar, excluir e gerenciar o acesso aos complementos.

Para obter mais informações sobre como instalar os complementos do centro de administração, consulte [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).
  
## <a name="add-in-states"></a>Estados de complementos

Um complemento pode estar no estado **On** ou **Off.**
  
| Estado | Como o estado ocorre | Impacto |
|:-----|:-----|:-----|
|**Ativo**  <br/> |O administrador carregou o complemento e o atribuiu a usuários ou grupos.  <br/> |Os usuários e grupos atribuídos ao complemento o veem nos clientes relevantes.  <br/> |
|**Desativado**  <br/> |O administrador desativou o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> Se o estado do add-in for alterado para Ativo, os usuários e grupos terão acesso a ele novamente.  <br/> |
|**Excluído**  <br/> |O administrador excluiu o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> |
   
Considere a exclusão de um complemento se ninguém o estiver usando mais. Por exemplo, desligar um complemento pode fazer sentido se um add-in for usado somente durante períodos específicos do ano.

## <a name="delete-an-add-in"></a>Excluir um complemento

Você também pode excluir um complemento que foi implantado.

1. No centro de administração, vá para **a** página Configurações  >  **Serviços & de complementos.**

    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.** Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.

2. Selecione o complemento implantado.

3. Clique em **Excluir Add-In**. Remova o botão Adicionar no canto inferior direito.

4. Valide suas seleções e escolha **Remover complemento**.

## <a name="edit-add-in-access"></a>Editar acesso ao complemento

Após a implantação, os administradores também podem gerenciar o acesso do usuário aos complementos.

1. No centro de administração, vá para **a** página Configurações  >  **Serviços & de complementos.**

    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.** Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.

2. Selecione o complemento implantado.

3. Clique em **Editar** em **Who tem Access**.

4. Salve as alterações.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir downloads de complementos ao desligar o Office Store em todos os clientes (exceto Outlook)

> [!NOTE]
> Outlook instalação do add-in é gerenciada por um [processo diferente.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

Como uma organização, você pode querer impedir o download de novos Office de Office Store. Isso pode ser usado em conjunto com a Implantação Centralizada para garantir que apenas os complementos aprovados pela organização sejam implantados para usuários em sua organização.
  
**Para desativar a aquisição de um complemento**
  
1. No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.** Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.
    
3. Selecione **Aplicativos e serviços de propriedade do usuário**.
    
4. Desmarque a opção de permitir que os usuários acessem a Office Store.

    Isso impedirá que todos os usuários adquiram os seguintes complementos da loja.
      
    - Os complementos para Word, Excel e PowerPoint 2016 de:
        
      - Windows
      - Mac
      - Office
        
        
    - Aquisições começando no **AppSource**
        
    - Os complementos no Microsoft 365
        
    Um usuário que tentar acessar o armazenamento verá a seguinte mensagem: Desculpe, Microsoft 365 foi configurada para impedir a aquisição individual de Office **Desempregos da Loja.**
  
O suporte para desligar o Office Store está disponível nas seguintes versões:
  
- Windows: 16.0.9001 - Disponível no momento.
    
- Mac: 16.10.18011401 - Disponível no momento.
    
- iOS: 2.9.18010804 - Disponível no momento.
    
- A Web - Disponível no momento.
    
Isso não impede que um administrador use a Implantação Centralizada para atribuir um Office Store.

> [!NOTE] 
> Os Visio, Bing Mapas e Pessoas Graph ainda aparecerão na faixa de opções, mesmo que um administrador tenha desabilitado a Loja. Para remover esses links, os administradores devem desabilitar a Loja por meio do Objeto de Política de Grupo (GPO).
  
Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar apenas a conta organizacional. Para obter mais informações, [consulte Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).  

> [!NOTE] 
> Impedir que os usuários acessem o office store também os impedirá de fazer sideload Office de complementos para testes de um [compartilhamento de rede.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Mais sobre a experiência do usuário final com os complementos

Depois de implantar um add-in, os usuários finais podem começar a usá-lo em seus aplicativos Office de Office (consulte [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). O complemento aparece em todas as plataformas que o complemento oferece suporte.
  
Se o complemento for compatível com comandos de complemento, os comandos aparecerão na faixa Office faixa de opções. No exemplo a seguir, o comando **Search Citation** é exibido para o complemento **Citações.** 

![Office faixa de opções com citações de pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Se o complemento implantado não dá suporte a comandos de add-in ou se você quiser exibir todos os complementos implantados, poderá **exibi-los** por meio de Meus Complementos . 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Nos aplicativos Word 2016, Excel 2016 ou PowerPoint 2016

1. Selecione **Inserir \> Meus Complementos**. 
    
2. Selecione a **guia Admin Managed** na janela Office Desem seguida. 
    
3. Clique duas vezes no complemento implantado anteriormente (neste exemplo, **Citações**).

    ![Guia Administrador Gerenciado da página de Office Desa somar](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>No Outlook

1. Na faixa **de opções** Home, selecione **Obter Complementos**.

    ![Botão Armazenar no Outlook](../../media/getaddinsicon.png)
  
2. Selecione **Gerenciados pelo Administrador** no painel de administração à esquerda. 

## <a name="related-content"></a>Conteúdo relacionado

[Implantar os complementos no centro de administração](./manage-deployment-of-add-ins.md) (artigo)\
Saiba mais sobre como criar e [criar Office -ins](/office/dev/add-ins/overview/office-add-ins) (artigo)\
[Usar cmdlets do PowerShell de](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) Implantação Centralizada para gerenciar os complementos (artigo)\
[Solução de problemas: o usuário não está vendo os complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artigo)\
[Secundárias e aquisição de complementos do Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (artigo)
