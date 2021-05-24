---
title: Implantar suplementos no centro de administração
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba como implantar os complementos para usuários e grupos em sua organização usando a Implantação Centralizada no centro de administração.
ms.openlocfilehash: 8cc4f29cd2593d9651edaf87791f46dabdcc30b2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636017"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implantar suplementos no centro de administração

Office os complementos ajudam você a personalizar seus documentos e simplificar a maneira como você acessa informações na Web (consulte [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, você pode implantar Office para os usuários em sua organização usando o recurso Implantação Centralizada no centro de administração Microsoft 365. A Implantação Centralizada é a maneira recomendada e mais rica em recursos para a maioria dos administradores implantarem os complementos para usuários e grupos em uma organização.

Para obter mais informações sobre como determinar se sua organização pode dar suporte à Implantação Centralizada, consulte [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).

Para saber mais sobre como gerenciar os complementos após a implantação, consulte [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Para o Word, Excel e PowerPoint usam um Catálogo de Aplicativos do [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implantar os complementos para usuários em um ambiente local sem conexão com o Microsoft 365 e/ou suporte para os SharePoint complementos necessários. Para Outlook use Exchange painel de controle para implantar em um ambiente local sem uma conexão com Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para a implantação de complementos do Office

Para lançar os complementos usando uma abordagem em fases, recomendamos o seguinte:
  
1. Distribua o complemento para um pequeno conjunto de membros e participantes comerciais do departamento de TI. Se a implantação for bem-sucedida, vá para a etapa 2.
    
2. Role o complemento para mais pessoas dentro da empresa. Novamente, avalie os resultados e, se bem-sucedido, continue com a implantação completa.
    
3. Execute uma adoção completa para todos os usuários.
    
Dependendo do tamanho do público-alvo, você pode adicionar ou remover etapas de lançamento.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar o complemento do Office usando o centro de administração

Antes de começar, consulte [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).
  
1. No centro de administração, vá para a página **de** Configurações \> **Desem seguida.** Se você não vir a Página **de** Complementos, vá para a página Configurações  \>  \> **Aplicativos Integrados.**

2. Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.

    > [!NOTE]
    > O centro de administração está sendo atualizado para a experiência de implantação com Aplicativos Integrados. Os Aplicativos Integrados só são visíveis para administradores globais, enquanto para outras pessoas a experiência antiga ainda existe. Se você não vir as etapas acima, vá para a seção Implantação Centralizada indo para Configurações  >  **aplicativos integrados.** Na parte superior da página **Aplicativos integrados,** escolha **Complementos**.

3. Selecione uma opção e siga as instruções.
  
4. Se você selecionou a opção para adicionar um Office Store, faça a seleção do seu complemento. </br>

    Você pode exibir os complementos disponíveis por categorias: Sugerido para **você,** **Classificação** ou **Nome.** Somente os complementos gratuitos estão disponíveis na Office Store. Os complementos pagos não têm suporte no momento. Depois de selecionar um complemento, aceite os termos e condições a seguir. <br/> 

    > [!NOTE]
    > Com a opção Office Store, as atualizações e aprimoramentos são implantados automaticamente para os usuários.

5. Na próxima página, selecione **Todos**, **Usuários ou grupos específicos** ou **Apenas eu** para especificar para quem o complemento foi implantado. Use a caixa Pesquisar para encontrar usuários ou grupos específicos. <br/>

    > [!NOTE]
    > Para saber mais sobre outros estados que se aplicam a um add-in, consulte [Estados de complemento](./manage-addins-in-the-admin-center.md).
  
6. Selecione **Implantar**.
  
7. Um tick verde é exibido quando o complemento é implantado. Siga as instruções na página para testar o complemento.

    > [!NOTE]
    > Os usuários podem precisar relançar Office para exibir o ícone do complemento na faixa de opções do aplicativo. Outlook os complementos podem levar até 24 horas para aparecerem nas faixas de opções do aplicativo.

8. Quando terminar, selecione **Next**. Se você tiver implantado apenas para si mesmo, poderá selecionar Alterar quem tem acesso ao **add-in** para implantar em mais usuários.

    Se você tiver implantado o complemento para outros membros da sua organização, siga as instruções para anunciar a implantação do complemento. <br/>
  
    É uma boa prática informar aos usuários e grupos que o complemento implantado está disponível. Considere enviar um email que descreva quando e como usar o complemento. Inclua ou vincule a Ajuda conteúdo ou perguntas frequentes que podem ajudar os usuários se eles têm problemas com o complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um complemento a usuários e grupos

Os administradores globais e Exchange podem atribuir um complemento a todos ou a usuários e grupos específicos. Cada opção tem implicações:
  
- **Todos** Essa opção atribui o complemento a todos os usuários da organização. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para sua organização.

- **Usuários** Se você atribuir um complemento a um usuário individual e, em seguida, implantar o complemento a um novo usuário, primeiro adicione o novo usuário.

- **Grupos** Se você atribuir um complemento a um grupo, os usuários adicionados ao grupo serão atribuídos automaticamente ao complemento. Quando um usuário é removido de um grupo, o usuário perde o acesso ao complemento. Em ambos os casos, nenhuma ação adicional é necessária do administrador.

- **Somente eu** Se você atribuir um complemento apenas a si mesmo, o complemento será atribuído apenas à sua conta, o que é ideal para testar o complemento.

A opção certa para sua organização depende da configuração. No entanto, recomendamos fazer atribuições usando grupos. Como administrador, você pode achar mais fácil gerenciar os complementos usando grupos e controlando a associação desses grupos em vez de atribuir usuários individuais a cada vez. Em algumas situações, talvez você queira restringir o acesso a um pequeno conjunto de usuários, fazendo atribuições a usuários específicos atribuindo usuários manualmente.
  
## <a name="more-about-office-add-ins-security"></a>Mais sobre Office segurança de complementos

Office os complementos combinam um arquivo de manifesto XML que contém alguns metadados sobre o complemento, mas, o mais importante, aponta para um aplicativo Web que contém todo o código e a lógica. Os complementos podem variar em seus recursos. Por exemplo, os complementos podem:
  
- Exibir dados.

- Leia o documento de um usuário para fornecer serviços contextuais.

- Ler e gravar dados de e para o documento de um usuário para fornecer valor a esse usuário.

Para obter mais informações sobre os tipos e recursos de Office de Office, consulte Office visão geral da plataforma de [complementos,](/office/dev/add-ins/overview/office-add-ins)especialmente a seção "Anatomia de um Office Add-in".
  
Para interagir com o documento do usuário, o complemento precisa declarar de que permissão ele precisa no manifesto. Um modelo de permissões de acesso para API JavaScript de cinco níveis fornece a base para privacidade e segurança para usuários de complementos do painel de tarefas. A maioria dos add-ins na Office Store é nível ReadWriteDocument com quase todos os complementos que suportam pelo menos o nível ReadDocument. Para obter mais informações sobre os níveis de permissão, consulte Solicitando permissões para uso da API em conteúdo e complementos do painel [de tarefas.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)
  
Ao atualizar um manifesto, as alterações típicas são para o ícone e o texto de um complemento. Ocasionalmente, os comandos de complemento mudam. No entanto, as permissões do complemento não mudam. O aplicativo Web onde todo o código e a lógica para as executações do complemento podem mudar a qualquer momento, que é a natureza dos aplicativos Web.
  
As atualizações para os complementos ocorrem da seguinte forma:
  
- **Complemento de linha de negócios:** Nesse caso, em que um administrador carregou explicitamente um manifesto, o complemento exige que o administrador carregue um novo arquivo de manifesto para dar suporte a alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento.

    > [!NOTE]
    > O administrador não precisa remover um Complemento LOB para fazer uma atualização.   Na seção Add-ins, o Administrador pode simplesmente clicar no Add-in LOB e escolher o botão Atualizar **no** canto inferior direito. A atualização funcionará somente se a versão do novo add-in for maior do que a do complemento existente.

- **Office de armazenamento:** Quando um administrador selecionou um Office Store, se um complemento for atualizado na Office Store, o complemento será atualizado posteriormente na Implantação Centralizada. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento.
  
## <a name="related-content"></a>Conteúdo relacionado

[Gerenciar os complementos no centro de administração](manage-addins-in-the-admin-center.md) (artigo)\
[Crie seu primeiro complemento do painel de tarefas do Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (artigo\
[Secundárias e aquisição](minors-and-acquiring-addins-from-the-store.md) de complementos do armazenamento (artigo)\ [Use cmdlets do PowerShell](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) de Implantação Centralizada para gerenciar os complementos (artigo)\  
[Solução de problemas: o usuário não está vendo os complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artigo)