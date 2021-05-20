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
description: Aprenda a implantar complementos para usuários e grupos em sua organização usando a Implantação Centralizada no centro administrativo.
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572268"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implantar suplementos no centro de administração

Office complementos ajudam a personalizar seus documentos e agilizar a maneira como você acessa informações na web (consulte [Iniciar o uso de seu Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, você pode implantar Office complementos para os usuários em sua organização usando o recurso Implantação Centralizada no centro administrativo Microsoft 365. A Implantação Centralizada é a maneira recomendada e mais rica em recursos para a maioria dos administradores implantar complementos para usuários e grupos dentro de uma organização.

Para obter mais informações sobre como determinar se sua organização pode suportar a implantação centralizada, consulte Determinar se a [implantação centralizada de complementos funciona para sua organização](centralized-deployment-of-add-ins.md).

Para saber mais sobre como gerenciar complementos após a implantação, consulte [Gerenciar complementos no centro administrativo](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Para o Word, Excel e PowerPoint usam um [Catálogo de Aplicativos SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implantar complementos aos usuários em um ambiente local sem conexão com Microsoft 365 e/ou suporte para SharePoint complementos necessários. Para Outlook use Exchange painel de controle para implantar em um ambiente local sem conexão com Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para a implantação de complementos do Office

Para implementar complementos usando uma abordagem em fases, recomendamos o seguinte:
  
1. Distribua o complemento para um pequeno conjunto de membros e participantes comerciais do departamento de TI. Se a implantação for bem sucedida, passe para o passo 2.
    
2. Implantar o complemento para mais indivíduos dentro do negócio. Novamente, avalie os resultados e, se for bem sucedido, continue com a implantação completa.
    
3. Realize um lançamento completo para todos os usuários.
    
Dependendo do tamanho do público-alvo, você pode adicionar ou remover etapas de implantação.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar o complemento do Office usando o centro de administração

Antes de começar, consulte [Determinar se a implantação centralizada de complementos funciona para sua organização](centralized-deployment-of-add-ins.md).
  
1. No centro administrativo, vá para a página **Configurações** \> **Add-ins.** Se você não ver a página **de complementos,** vá para a página de complementos de aplicativos  \>  \> **integrados** Configurações.

2. Selecione **Implantar add-in** na parte superior da página e selecione **Próximo**.

    > [!NOTE]
    > O centro administrativo está se atualizando para a experiência de implantação com Aplicativos Integrados. Aplicativos integrados só são visíveis para administradores globais, enquanto para outros a experiência antiga ainda existe. Se você não ver os passos acima, vá para a seção Implantação Centralizada indo para **Configurações**  >  **aplicativos Integrados**. No topo da página **de aplicativos Integrados,** escolha **Complementos**.

3. Selecione uma opção e siga as instruções.
  
4. Se você selecionou a opção de adicionar um complemento da loja de Office, faça sua seleção adicional. </br>

    Você pode visualizar complementos disponíveis por categorias: **Sugerido para você,** **Classificação** ou **Nome**. Apenas complementos gratuitos estão disponíveis na loja de Office. Os complementos pagos não são suportados atualmente. Depois de selecionar um complemento, aceite os termos e condições para prosseguir. <br/> 

    > [!NOTE]
    > Com a opção Office Store, atualizações e melhorias são automaticamente implantados aos usuários.

5. Na próxima página, selecione **Todos**, **Usuários ou grupos específicos** ou **Apenas eu** para especificar para quem o complemento foi implantado. Use a caixa Pesquisa para encontrar usuários ou grupos específicos. <br/>

    > [!NOTE]
    > Para saber mais sobre outros estados que se aplicam a um complemento, consulte [estados adicionais](./manage-addins-in-the-admin-center.md).
  
6. Selecione **Implantar**.
  
7. Um carrapato verde aparece quando o complemento é implantado. Siga as instruções na página para testar o complemento.

    > [!NOTE]
    > Os usuários podem precisar relançar Office para visualizar o ícone de complemento na fita do aplicativo. Outlook complementos podem levar até 24 horas para aparecer em fitas de aplicativos.

8. Quando terminar, selecione **Next**. Se você implantou apenas para si mesmo, você pode selecionar **Alterar quem tem acesso ao complemento** para implantar em mais usuários.

    Se você tiver implantado o complemento para outros membros da sua organização, siga as instruções para anunciar a implantação do complemento. <br/>
  
    É uma boa prática informar usuários e grupos que o complemento implantado está disponível. Considere enviar um e-mail que descreve quando e como usar o complemento. Inclua ou link para ajudar o conteúdo ou perguntas frequentes que podem ajudar os usuários se eles tiverem problemas com o complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um complemento a usuários e grupos

Os administradores e administradores de Exchange globais podem atribuir um complemento a todos ou a usuários e grupos específicos. Cada opção tem implicações:
  
- **Todos** Essa opção atribui o complemento a todos os usuários da organização. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para sua organização.

- **Usuários** Se você atribuir um complemento a um usuário individual e, em seguida, implantar o complemento em um novo usuário, você deve primeiro adicionar o novo usuário.

- **Grupos** Se você atribuir um complemento a um grupo, os usuários que forem adicionados ao grupo receberão automaticamente o complemento. Quando um usuário é removido de um grupo, o usuário perde o acesso ao complemento. Em ambos os casos, nenhuma ação adicional é necessária do administrador.

- **Só eu.** Se você atribuir um complemento apenas a si mesmo, o complemento será atribuído apenas à sua conta, o que é ideal para testar o complemento.

A opção certa para sua organização depende da sua configuração. No entanto, recomendamos fazer tarefas usando grupos. Como administrador, você pode achar mais fácil gerenciar complementos usando grupos e controlando a adesão desses grupos em vez de atribuir usuários individuais cada vez. Em algumas situações, você pode querer restringir o acesso a um pequeno conjunto de usuários, fazendo atribuições a usuários específicos, atribuindo usuários manualmente.
  
## <a name="more-about-office-add-ins-security"></a>Mais sobre Office segurança de complementos

Office complementos combinam um arquivo manifesto XML que contém alguns metadados sobre o complemento, mas o mais importante aponta para um aplicativo web que contém todo o código e lógica. Os complementos podem variar em suas capacidades. Por exemplo, os complementos podem:
  
- Exibir dados.

- Leia o documento de um usuário para fornecer serviços contextuais.

- Leia e escreva dados de e para o documento de um usuário para fornecer valor a esse usuário.

Para obter mais informações sobre os tipos e recursos de Office complementos, consulte [Office visão geral da plataforma Add-ins](/office/dev/add-ins/overview/office-add-ins), especialmente a seção "Anatomia de um Office Add-in".
  
Para interagir com o documento do usuário, o complemento precisa declarar qual a permissão que ele precisa no manifesto. Um modelo de permissões de acesso javascript de cinco níveis fornece a base para privacidade e segurança para os usuários de complementos de painel de tarefas. A maioria dos complementos na loja de Office são nivelados ReadWriteDocument com quase todos os complementos que suportam pelo menos o nível ReadDocument. Para obter mais informações sobre os níveis de permissão, consulte [Solicitando permissões para uso de API em complementos de conteúdo e painel de tarefas](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Ao atualizar um manifesto, as alterações típicas são para o ícone e texto de um complemento. Ocasionalmente, os comandos adicionais mudam. No entanto, as permissões do complemento não mudam. O aplicativo web onde todo o código e lógica para os complementos pode mudar a qualquer momento, que é a natureza dos aplicativos web.
  
Atualizações para complementos acontecem da seguinte forma:
  
- **Complemento de linha de negócios:** Neste caso, quando um administrador fez um upload explícito de um manifesto, o complemento exige que o administrador carregue um novo arquivo manifesto para apoiar alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo web pode mudar a qualquer momento.

    > [!NOTE]
    > O administrador não precisa remover um complemento LOB para fazer uma atualização.   Na seção Adicionar, o administrador pode simplesmente clicar no complemento LOB e escolher o **botão de atualização** no canto inferior direito. A atualização funcionará somente se a versão do novo complemento for maior do que a do complemento existente.

- **complemento da loja Office:** Quando um administrador selecionou um complemento da Office Store, se um complemento de atualizações na Office Store, o complemento será atualizado mais tarde na Implantação Centralizada. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo web pode mudar a qualquer momento.
  
## <a name="related-content"></a>Conteúdo relacionado

[Gerenciar complementos no centro administrativo](manage-addins-in-the-admin-center.md) (artigo)

[Construa seu primeiro complemento de painel de tarefas](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) do Word (artigo)

[Menores e aquisição de complementos da loja](minors-and-acquiring-addins-from-the-store.md) (artigo)
  
[Use cmdlets de implantação centralizada para gerenciar complementos](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artigo)
  
[Solução de problemas: Usuário não vê complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artigo)