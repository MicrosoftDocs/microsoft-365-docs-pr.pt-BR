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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Aprenda a implantar os complementos para usuários e grupos em sua organização usando a Implantação Centralizada no centro de administração.
ms.openlocfilehash: 5d17242d98f0e58ec4bfbcfd5b7014e6a6e0a6c5
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114496"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implantar suplementos no centro de administração

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Os complementos do Office ajudam você a personalizar seus documentos e simplificar a maneira como você acessa informações na Web (confira Começar a usar o seu Complemento [do Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) Como administrador, você pode implantar os complementos do Office para os usuários em sua organização usando o recurso Implantação Centralizada no Centro de administração do Microsoft 365. A Implantação Centralizada é a maneira recomendada e mais rica em recursos para a maioria dos administradores implantarem complementos para usuários e grupos dentro de uma organização. 

Para obter mais informações sobre como determinar se sua organização pode suportar a Implantação Centralizada, consulte Determinar se a Implantação Centralizada de [complementos funciona para sua organização.](centralized-deployment-of-add-ins.md)

Para saber mais sobre como gerenciar os complementos após a implantação, consulte [Gerenciar os complementos no centro de administração](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Para o Word, o Excel e o PowerPoint usam um Catálogo de Aplicativos do [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implantar os complementos para usuários em um ambiente local sem conexão com o Microsoft 365 e/ou suporte para os complementos do SharePoint necessários. Para o Outlook, use o painel de controle do Exchange para implantar em um ambiente local sem uma conexão com o Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para implantar os complementos do Office

Para lançar os complementos usando uma abordagem em fases, recomendamos o seguinte:
  
1. Roll out the add-in to a small set of business stakeholders and members of the IT department. Se a implantação for bem-sucedida, vá para a etapa 2.
    
2. Roll out the add-in to more individuals within the business. Novamente, avalie os resultados e, se bem-sucedido, continue com a implantação completa.
    
3. Execute uma lançamento completo para todos os usuários.
    
Dependendo do tamanho do público-alvo, você pode adicionar ou remover etapas de lançamento.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar um complemento do Office usando o centro de administração

Antes de começar, confira [Determinar se a Implantação Centralizada de complementos funciona para sua organização.](centralized-deployment-of-add-ins.md)
  
1. No centro de administração, vá para a **página** \> **Configurações de Complementos.** Se você não vir a Página **de** Complemento, vá para a página Configurações **Integradas** de \>  \> **Aplicativos.**
    
2. Selecione **Implantar o add-in** na parte superior da página e, em seguida, **selecione Próximo**.
 
    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com aplicativos integrados. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **Integradas aplicativos**. Na parte superior da página **Aplicativos integrados,** escolha **Os Complementos.**
    
3. Selecione uma opção e siga as instruções.
  
4. Se você selecionou a opção para adicionar um complemento da Office Store, faça a seleção do seu complemento. </br>

    Você pode exibir os complementos disponíveis por categorias: **Sugerido para você,** **Classificação** ou **Nome.** Somente os complementos gratuitos estão disponíveis na Office Store. Atualmente, não há suporte para os complementos pagos. Depois de selecionar um complemento, aceite os termos e condições para continuar. <br/> 

    > [!NOTE] 
    > Com a opção da Office Store, as atualizações e os aprimoramentos são implantados automaticamente para os usuários.

5. Na próxima página, selecione **Todos**, **Usuários/grupos** específicos ou Apenas eu para especificar em quem o add-in está implantado.  Use a caixa Pesquisar para encontrar usuários ou grupos específicos. <br/>

    > [!NOTE] 
    > Para saber mais sobre outros estados que se aplicam a um add-in, consulte [Estados do complemento.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)
  
6. Selecione **Implantar**.
  
7. Uma marca verde aparece quando o complemento é implantado. Siga as instruções na página para testar o complemento.

    > [!NOTE]
    > Talvez os usuários precisem relançar o Office para exibir o ícone do complemento na faixa de opções do aplicativo. Os complementos do Outlook podem levar até 24 horas para aparecer nas faixas de opções do aplicativo.
    
8. Quando terminar, selecione **Next**. Se você implantou apenas para si mesmo, pode selecionar Alterar quem tem acesso ao **add-in** para implantar para mais usuários.

    Se você implantou o complemento para outros membros da sua organização, siga as instruções para anunciar a implantação do add-in. <br/>
  
    É uma boa prática informar aos usuários e grupos que o complemento implantado está disponível. Considere enviar um email que descreve quando e como usar o complemento. Inclua ou vincule ao conteúdo da Ajuda ou perguntas frequentes que podem ajudar os usuários se eles têm problemas com o complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um complemento a usuários e grupos

Os administradores podem atribuir um complemento a todos ou a usuários e grupos específicos. Cada opção tem implicações:
  
- **Todos** Essa opção atribui o complemento a todos os usuários na organização. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para sua organização. 
    
- **Usuários** Se você atribuir um complemento a um usuário individual e depois implantá-lo para um novo usuário, primeiro você deve adicionar o novo usuário.
    
- **Grupos** Se você atribuir um complemento a um grupo, os usuários adicionados ao grupo receberão automaticamente o complemento. Quando um usuário é removido de um grupo, ele perde o acesso ao complemento. Em ambos os casos, nenhuma ação adicional é necessária do administrador. 

- **Somente eu** Se você atribuir um complemento apenas a si mesmo, o complemento será atribuído apenas à sua conta, o que é ideal para testar o complemento.
    
A opção certa para sua organização depende da configuração. No entanto, recomendamos fazer atribuições usando grupos. Como administrador, você pode achar mais fácil gerenciar os complementos usando grupos e controlando a associação desses grupos em vez de atribuir usuários individuais a cada vez. Em algumas situações, talvez você queira restringir o acesso a um pequeno conjunto de usuários fazendo atribuições a usuários específicos atribuindo usuários manualmente.
  
## <a name="more-about-office-add-ins-security"></a>Mais informações sobre a segurança de complementos do Office

Os complementos do Office combinam um arquivo de manifesto XML que contém alguns metadados sobre o complemento, mas o mais importante aponta para um aplicativo Web que contém todo o código e a lógica. Os complementos podem variar em seus recursos. Por exemplo, os complementos podem:
  
- Exibir dados.
    
- Leia o documento de um usuário para fornecer serviços contextuais.
    
- Ler e gravar dados de e para um documento do usuário para fornecer valor a esse usuário.
    
Para saber mais sobre os tipos e recursos de complementos do Office, confira a visão geral da plataforma de Complementos do [Office,](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)especialmente a seção "Anatomia de um Complemento do Office".
  
Para interagir com o documento do usuário, o complemento precisa declarar de que permissão ele precisa no manifesto. Um modelo de permissões de acesso da API JavaScript de cinco níveis fornece a base para privacidade e segurança para usuários de complementos de painel de tarefas. A maioria dos complementos na Office Store é de nível ReadWriteDocument com quase todos os complementos que suportam pelo menos o nível readDocument. Para obter mais informações sobre os níveis de permissão, consulte Solicitando permissões para uso da API em complementos de conteúdo e de painel [de tarefas.](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)
  
Ao atualizar um manifesto, as alterações típicas são no ícone e no texto de um complemento. Ocasionalmente, os comandos de complemento mudam. No entanto, as permissões do complemento não mudam. O aplicativo Web em que todo o código e a lógica do complemento são executados podem mudar a qualquer momento, que é a natureza dos aplicativos Web.
  
As atualizações para os complementos ocorrem da seguinte forma:
  
- **Complemento de linha de negócios:** Nesse caso, em que um administrador carregou explicitamente um manifesto, o add-in exige que o administrador carregue um novo arquivo de manifesto para dar suporte a alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

    > [!NOTE]
    > O administrador não precisa remover um add-in LOB para fazer uma atualização.   Na seção Add-ins, o administrador pode simplesmente clicar no  add-in LOB e escolher o botão Atualizar no canto inferior direito. A atualização só funcionará se a versão do novo add-in for maior do que a do complemento existente.   
    
- **Office Store add-in:** Quando um administrador seleciona um complemento da Office Store, se um complemento for atualizado na Office Store, ele será atualizado posteriormente na Implantação Centralizada. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 
  
## <a name="learn-more"></a>Saiba mais

[Gerenciar suplementos no centro de administração](manage-addins-in-the-admin-center.md)

[Crie seu primeiro complemento do painel de tarefas do Word.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Menores de idade e aquisição de complementos da loja](minors-and-acquiring-addins-from-the-store.md)
  
[Usar cmdlets do PowerShell de Implantação Centralizada para gerenciar os complementos](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solução de problemas: o usuário não está vendo os complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
