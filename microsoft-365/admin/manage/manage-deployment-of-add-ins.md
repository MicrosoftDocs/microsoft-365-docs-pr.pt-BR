---
title: Implantar suplementos no centro de administração
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
description: Saiba como implantar suplementos para usuários e grupos em sua organização usando a implantação centralizada no centro de administração.
ms.openlocfilehash: 37fac34449ee39366778e29c0eeddf1fc7bfdd37
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698284"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implantar suplementos no centro de administração

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Os suplementos do Office ajudam você a personalizar seus documentos e simplificar a forma como você acessa as informações na Web (Confira [começar a usar o suplemento do Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, você pode implantar suplementos do Office para os usuários em sua organização usando o recurso de implantação centralizado no centro de administração do Microsoft 365. A implantação centralizada é a maneira recomendada e mais rica de recursos para a maioria dos administradores implantar suplementos para usuários e grupos em uma organização. 

Para obter mais informações sobre como determinar se sua organização pode dar suporte à implantação centralizada, consulte [determinar se a implantação centralizada de suplementos funciona para sua organização](centralized-deployment-of-add-ins.md).

Para saber mais sobre como gerenciar suplementos após a implantação, consulte [Manage Add-ins no centro de administração](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Para o Word, Excel e PowerPoint, use um [Catálogo de aplicativos do SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implantar suplementos para usuários em um ambiente local sem conexão com o Microsoft 365 e/ou suporte para suplementos do SharePoint necessários. Para o Outlook usar o painel de controle do Exchange para implantar em um ambiente local sem uma conexão com o Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para implantar suplementos do Office

Para distribuir suplementos usando uma abordagem em fases, recomendamos o seguinte:
  
1. Distribua o suplemento para um pequeno conjunto de participantes de negócios e membros do departamento de ti. Se a implantação for bem-sucedida, vá para a etapa 2.
    
2. Distribuir o suplemento para mais pessoas dentro da empresa. Novamente, avalie os resultados e, se bem-sucedido, continue com a implantação completa.
    
3. Executar uma distribuição completa para todos os usuários.
    
Dependendo do tamanho do público-alvo, você poderá adicionar ou remover etapas de distribuição.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar um suplemento do Office usando o centro de administração

Antes de começar, confira [determinar se a implantação centralizada de suplementos funciona para sua organização](centralized-deployment-of-add-ins.md).
  
1. No centro de administração, vá para a página **configurações** \> **de suplementos** . Se você não vir a página do **suplemento** , vá para a página **configurações** de \> **aplicativos integrados** da configuração \>  .
    
2. Selecione **implantar suplemento** na parte superior da página e, em seguida, selecione **Avançar**.
 
    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados. Se você não vir as etapas acima, vá para seção implantação centralizada em aplicativos de **configurações**  >  **integradas**. Na parte superior da página **aplicativos integrados** , escolha **suplementos**.
    
3. Selecione uma opção e siga as instruções.
  
4. Se você selecionou a opção para adicionar um suplemento da Office Store, faça a seleção do seu suplemento. </br>

    Você pode exibir os suplementos disponíveis por categorias: **sugeridas para você**, **classificação** ou **nome**. Apenas os suplementos gratuitos estão disponíveis na Office Store. Atualmente, não há suporte para suplementos pagos. Depois de selecionar um suplemento, aceite os termos e condições para prosseguir. <br/> 

    > [!NOTE] 
    > Com a opção da Office Store, as atualizações e aprimoramentos são implantadas automaticamente para os usuários.

5. Na próxima página, selecione **todos**, **usuários/grupos específicos** ou **apenas eu** para especificar quem o suplemento será implantado. Use a caixa Pesquisar para localizar usuários ou grupos específicos. <br/>

    > [!NOTE] 
    > Para saber mais sobre outros Estados que se aplicam a um suplemento, confira [Estados de suplementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Selecione **Implantar**.
  
7. Um tique verde aparece quando o suplemento é implantado. Siga as instruções na página para testar o suplemento.

    > [!NOTE]
    > Talvez os usuários precisem reiniciar o Office para exibir o ícone de suplemento na faixa de opções do aplicativo. Os suplementos do Outlook podem levar até 24 horas para serem exibidos nas faixas de opções do aplicativo.
    
8. Quando terminar, selecione **Avançar**. Se você implantou para si mesmo, é possível selecionar **alterar quem tem acesso ao suplemento** para implantar para mais usuários.

    Se você implantou o suplemento em outros membros da sua organização, siga as instruções para anunciar a implantação do suplemento. <br/>
  
    É recomendável informar os usuários e grupos de que o suplemento implantado está disponível. Considere enviar um email que descreve quando e como usar o suplemento. Incluir ou vincular ao conteúdo da ajuda ou perguntas frequentes que podem ajudar os usuários se tiverem problemas com o suplemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um suplemento aos usuários e grupos

Os administradores podem atribuir um suplemento a todos ou a usuários e grupos específicos. Cada opção tem implicações:
  
- **Todos** Essa opção atribui o suplemento a todos os usuários da organização. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para sua organização. 
    
- **Usuários** do Se você atribuir um suplemento a um usuário individual e, em seguida, implantar o suplemento em um novo usuário, você deverá primeiro adicionar o novo usuário.
    
- **Grupos** Se você atribuir um suplemento a um grupo, os usuários adicionados ao grupo receberão automaticamente o suplemento. Quando um usuário é removido de um grupo, o usuário perde o acesso ao suplemento. Em ambos os casos, nenhuma ação adicional é necessária do administrador. 

- **Apenas eu** Se você atribuir um suplemento a si mesmo, o suplemento será atribuído apenas à sua conta, o que é ideal para testar o suplemento.
    
A opção certa para sua organização depende da sua configuração. No entanto, recomendamos fazer atribuições usando grupos. Como administrador, você pode achar mais fácil gerenciar suplementos usando grupos e controlando a associação desses grupos, em vez de atribuir usuários individuais a cada vez. Em algumas situações, talvez você queira restringir o acesso a um pequeno conjunto de usuários fazendo atribuições a usuários específicos, atribuindo usuários manualmente.
  
## <a name="more-about-office-add-ins-security"></a>Mais informações sobre a segurança de suplementos do Office

Os suplementos do Office combinam um arquivo de manifesto XML que contém alguns metadados sobre o suplemento, mas que, mais importante, apontam para um aplicativo Web que contém todo o código e a lógica. Os suplementos podem variar em seus recursos. Por exemplo, os suplementos podem:
  
- Dados de exibição.
    
- Leia o documento de um usuário para fornecer serviços contextuais.
    
- Ler e gravar dados de e para o documento de um usuário para fornecer valor a esse usuário.
    
Para obter mais informações sobre os tipos e recursos dos suplementos do Office, confira [visão geral da plataforma](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)de suplementos do Office, especialmente a seção "Anatomia de um suplemento do Office."
  
Para interagir com o documento do usuário, o suplemento precisa declarar a permissão necessária no manifesto. Um modelo de permissões de acesso à API JavaScript de cinco níveis fornece a base para privacidade e segurança para usuários de suplementos do painel de tarefas. A maioria dos suplementos na Office Store são de nível ReadWriteDocument com quase todos os suplementos que suportam pelo menos o nível de ReadDocument. Para obter mais informações sobre os níveis de permissão, consulte [solicitando permissões para uso da API em suplementos de conteúdo e de painel de tarefas](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Ao atualizar um manifesto, as alterações típicas são o ícone e o texto de um suplemento. Ocasionalmente, os comandos de suplemento são alterados. No entanto, as permissões do suplemento não são alteradas. O aplicativo Web em que todo o código e a lógica para o suplemento é executado pode mudar a qualquer momento, que é a natureza dos aplicativos Web.
  
As atualizações para suplementos acontecem da seguinte maneira:
  
- **Suplemento de linha de negócios:** Nesse caso, onde um administrador carregou explicitamente um manifesto, o suplemento requer que o administrador carregue um novo arquivo de manifesto para dar suporte às alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

    > [!NOTE]
    > O administrador não precisa remover um suplemento LOB para fazer uma atualização.   Na seção suplementos, o administrador pode simplesmente clicar no suplemento LOB e escolher o **botão atualizar** no canto inferior direito. A atualização funcionará somente se a versão do novo suplemento for maior do que a do suplemento existente.   
    
- **Suplemento da Office Store:** Quando um administrador selecionou um suplemento da Office Store, se um suplemento for atualizado na Office Store, o suplemento será atualizado posteriormente na implantação centralizada. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 
  
## <a name="learn-more"></a>Saiba mais

[Gerenciar suplementos no centro de administração](manage-addins-in-the-admin-center.md)

[Crie seu primeiro suplemento do painel de tarefas do Word](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).

[Menores e aquisição de suplementos da loja](minors-and-acquiring-addins-from-the-store.md)
  
[Usar cmdlets do PowerShell de implantação centralizada para gerenciar suplementos](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solução de problemas: o usuário não está vendo suplementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
