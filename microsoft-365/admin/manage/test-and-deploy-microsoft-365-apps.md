---
title: Testar e implantar Microsoft 365 Apps por parceiros no portal aplicativos integrados
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Encontre, teste e implante aplicativos de parceiros microsoft e microsoft para usuários e grupos em sua organização a partir do portal aplicativos integrados no Centro de administração do Microsoft 365.
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007052"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testar e implantar Microsoft 365 Apps por parceiros no portal aplicativos integrados

A Centro de administração do Microsoft 365 oferece flexibilidade para implantar aplicativos de armazenamento único, linha de negócios personalizada de aplicativos e Microsoft 365 aplicativos parceiros de um único local. O local pode ser acessado nas configurações do Centro de Administração da Microsoft, em Aplicativos integrados. A capacidade de encontrar, testar e implantar totalmente aplicativos comprados e licenciados por parceiros da Microsoft no portal aplicativos integrados fornece a conveniência e os benefícios necessários para manter os serviços comerciais atualizados regularmente e em execução com eficiência.

Para obter informações adicionais sobre a compra e licenciamento Microsoft 365 aplicativos de parceiros para sua organização, consulte Gerenciar e implantar Microsoft 365 Apps [do Centro de administração do Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Para obter mais informações sobre como os parceiros criam esses aplicativos, consulte [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

O portal aplicativos integrados só está acessível para administradores globais e está disponível apenas para clientes de todo o mundo. Esse recurso não está disponível em nuvens soberanas e governamentais.

O portal aplicativos integrados exibe uma lista de aplicativos, que inclui aplicativos individuais e Microsoft 365 aplicativos de parceiros implantados em sua organização. Somente aplicativos web, SPFx aplicativos, Office e Teams aplicativos estão listados. Para aplicativos Web, você pode ver dois tipos de aplicativos.

- Aplicativos SaaS que estão disponíveis no appsource.microsoft.com e podem ser implantados por administradores que dão consentimento em nome da organização.
- Aplicativos de galeria SAML vinculados aos complementos do office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gerenciar aplicativos no portal aplicativos integrados

Você pode gerenciar testes e implantação de Microsoft 365 Apps adquiridos e licenciados de parceiros.

1. No centro de administração, selecione **Configurações** e selecione **Aplicativos integrados.**

2. Escolha um aplicativo **com Status** de **Mais aplicativos disponíveis** para abrir o painel **Gerenciar.** O status de **mais aplicativos** disponíveis permite que você saiba que há mais integrações dos ISVs que ainda não foram implantados.

3. Na guia **Visão** Geral, selecione **Implantar**. Alguns aplicativos exigem que você adicione usuários antes de selecionar Implantar.

4. Selecione  **Usuários**, escolha **É uma implantação de teste** e escolha **Toda** a organização , **Usuários/grupos específicos** **ou Somente eu**. Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização. Usuários ou grupos específicos podem ser um grupo Microsoft 365, um grupo de segurança ou um grupo de distribuição.

5. Selecione **Atualizar** **e,** em seguida, Feito . Agora você pode selecionar Implantar na guia Visão Geral.

6. Revise as informações do aplicativo e selecione **Implantar**.

7. Selecione **Concluído na** página Implantação concluída e revise os detalhes do teste ou implantação completa na guia **Visão** geral.

8. Se o aplicativo tiver um status de **Atualização** pendente, você poderá clicar no aplicativo para abrir o painel Gerenciar e atualizar o aplicativo.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Encontre aplicativos publicados para teste e implantação completa

Você pode encontrar, testar e implantar totalmente aplicativos publicados que ainda não aparecem na lista na página Aplicativos integrados. Ao comprar e licenciar os aplicativos do centro de administração, você pode adicionar aplicativos de parceiros Microsoft e Microsoft à sua lista de um único local.

1. No centro de administração, na tela esquerda, escolha **Configurações** e escolha **Aplicativos integrados.**

2. Selecione **Obter aplicativos** para obter uma exibição dos aplicativos.

3. Na página **Microsoft 365 Apps** aplicativos publicados, selecione o aplicativo que você deseja implantar escolhendo **Obter agora**. Os aplicativos exibidos principalmente são word, PowerPoint, Excel, Outlook, aplicativo Teams e aplicativos SharePoint (baseados na tecnologia Estrutura do SharePoint). Aceite as permissões e selecione **Continuar**.

5. Selecione **Implantar** na parte superior da página ao lado da mensagem que se refere à espera de ser implantada.

    Se o aplicativo selecionado estiver vinculado a uma oferta SaaS por um ISV, todos os outros aplicativos que fazem parte dessa oferta vinculada aparecerão na página Configuração. Se você optar por implantar todos os aplicativos, selecione **Próximo**. Caso contrário, **selecione Editar** e escolha quais aplicativos você deseja implantados. Alguns aplicativos exigem que você adicione usuários antes de selecionar **Implantar**.

6. Selecione **Adicionar usuários**, escolha É uma **implantação de teste** e escolha **Toda** a organização ou **Usuários/grupos específicos** ou **Apenas eu**.

    Usuários/grupos específicos podem ser um grupo Microsoft 365, um grupo de segurança ou um grupo distribuído. Você também pode escolher **Testar implantação** se preferir aguardar para implantar o aplicativo em toda a organização.

7. Selecione **Próximo** para chegar à página **Aceitar solicitação de** permissão. Os recursos do aplicativo e as permissões de cada um dos aplicativos estão listados. Se o aplicativo precisar de consentimento, selecione **Aceitar permissões**. Somente um administrador global pode dar consentimento.

8. Selecione **Próximo para** revisar a implantação e escolha Concluir **implantação**. Você pode exibir a implantação na guia **Visão** Geral escolhendo **Exibir essa implantação**. No Centro de administração do Microsoft 365, você pode ver o status de cada aplicativo implantado e a data em que implantou o aplicativo.

> [!NOTE]
> Se um aplicativo tiver sido implantado anteriormente em outro lugar que não seja o portal aplicativos integrados, o Tipo **de Implantação** será **Personalizado.**

## <a name="unsupported-scenarios"></a>Cenários não suportados

Você não poderá implantar um único aplicativo de loja ou Microsoft 365 Apps por parceiro no portal de aplicativos integrados para os seguintes cenários.

- O mesmo complemento está vinculado a mais de uma oferta SaaS.
- A oferta saaS está vinculada a complementos, mas não se integra ao Microsoft Graph e nenhuma ID do aplicativo AAD é fornecida.
- A oferta do SaaS está vinculada a complementos, mas a ID do aplicativo AAD fornecida para o Microsoft Graph integração é compartilhada entre várias ofertas saaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload aplicativos de linha de negócios personalizados para testes e implantação completa

1. No centro de administração, na tela esquerda, **escolha** Configurações e, em seguida, **aplicativos integrados.**

2. Selecione **Upload aplicativos personalizados.** Somente uma linha personalizada de aplicativos para Word, PowerPoint, Excel e Outlook é suportada.

3. Upload o arquivo de manifesto do dispositivo ou adicione um link de URL. Alguns aplicativos exigem que você adicione usuários antes de selecionar Implantar.

4. Selecione **Adicionar usuários**, escolha É uma **implantação de** teste e escolha **Toda** a organização ou **Usuários/grupos específicos** ou **Somente eu**.

    Usuários/grupos específicos podem ser um grupo Microsoft 365, um grupo de segurança ou um grupo distribuído. Você também pode escolher **Testar implantação** se quiser esperar para implantar o aplicativo em toda a organização.

5. Selecione **Próximo** para chegar à página **Aceitar solicitação de** permissão. Os recursos do aplicativo e as permissões dos aplicativos estão listados. Se o aplicativo precisar de consentimento, selecione **Aceitar permissões**. Somente um administrador global pode dar consentimento.

6. Selecione **Próximo para** revisar a implantação e escolha Concluir **implantação**. Você pode exibir a implantação na guia **Visão** Geral escolhendo **Exibir essa implantação**.

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Preparar para implantar os complementos em aplicativos integrados

Office os complementos ajudam você a personalizar seus documentos e a simplificar a maneira como você acessa informações na Web (consulte Start using your Office Add-in). 

Os complementos proporcionam os seguintes benefícios: 

- Quando o aplicativo Office relevante é iniciado, o complemento baixa automaticamente. Se o complemento suportar comandos de Office. 

- Os complementos não aparecerão mais para os usuários se o administrador desligar ou excluir o complemento ou se o usuário for removido do Active Directory do Azure ou de um grupo ao que o complemento é atribuído. 

Os complementos são suportados em três plataformas de área de trabalho Windows, Mac e Online Office aplicativos. Ele também é suportado no iOS e no Android (Outlook Somente complementos móveis). 

Pode levar até 24 horas para um complemento aparecer para cliente para todos os usuários. 

Atualmente, Exchange administradores globais e administradores globais podem implantar os complementos de aplicativos integrados.   

### <a name="before-you-begin"></a>Antes de começar

A implantação de complementos exige que os usuários usem licenças Microsoft 365 Enterprise (E3/E5/F3) ou licenças do Microsoft 365 Business (Business Basic, Business Standard, Business Premium). Os usuários também precisam entrar no Office usando sua ID organizacional) e ter Exchange Online caixas de correio Exchange Online ativas. Seu diretório de assinatura deve estar ou federado para Active Directory do Azure. 

A implantação não dá suporte ao seguinte: 

- Suplementos que visam o Word, Excel ou o PowerPoint no Office 2013 
- Um serviço de diretório local 
- Implantação de add-in para uma caixa de correio Exchange no pré-lançamento 
- Implantação de componentes modelo de objeto (COM) ou Visual Studio Tools para Office (VSTO) de componentes. 
- Implantações de Microsoft 365 que não incluem Exchange Online como Microsoft 365 Apps para Empresas e Microsoft 365 Apps para Enterprise.  

### <a name="office-requirements"></a>Office Requisitos 

Para o Word, Excel e PowerPoint, os usuários devem estar usando um dos seguintes: 
- Em um dispositivo Windows, versão 1704 ou posterior de licenças do Microsoft 365 Enterprise (E3/E5/F3) ou licenças do Microsoft 365 Business (Business Basic, Business Standard, Business Premium). 
- Em um Mac, versão 15.34 ou posterior. 

Para Outlook, os usuários devem estar usando um dos seguintes: 
- Versão 1701 ou posterior das licenças Microsoft 365 Enterprise (E3/E5/F3) ou Microsoft 365 Business licenses (Business Basic, Business Standard, Business Premium). 
- Versão 1808 ou posterior do Office Professional Plus 2019 ou Office Standard 2019. 
- Versão 16.0.4494.1000 ou posterior do Office Professional Plus 2016 (MSI) ou Office Standard 2016 (MSI).
    > [!NOTE]
    > As versões MSI do Outlook mostram os complementos instalados pelo administrador na faixa de opções apropriada do Outlook, não a seção "Meus complementos".  
- Versão 15.0.4937.1000 ou posterior do Office Professional Plus 2013 (MSI) ou Office Standard 2013 (MSI).
- Versão 16.0.9318.1000 ou posterior do Office 2016 para Mac. 
- Versão 2.75.0 ou posterior do Outlook mobile para iOS. 
- Versão 2.2.145 ou posterior do Outlook mobile para Android. 



### <a name="exchange-online-requirements"></a>Requisitos do Exchange Online 
O Microsoft Exchange armazena os manifestos de complemento no locatário da sua organização. O administrador que está implantando os complementos e os usuários que recebem esses complementos devem estar em uma versão do Exchange Online que oferece suporte à autenticação OAuth. 

Fale com o administrador do Exchange da sua organização para saber qual configuração está sendo usada. A conectividade OAuth por usuário pode ser verificada usando o cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)   PowerShell. 

### <a name="user-and-group-assignments"></a>Atribuições de usuário e grupo
Atualmente, a implantação do add-in tem suporte para a maioria dos grupos com suporte do Azure Active Directory, incluindo grupos do Microsoft 365, listas de distribuição e grupos de segurança. A implantação dá suporte a usuários em grupos de nível superior ou grupos sem grupos pai, mas não usuários em grupos ou grupos aninhados que têm grupos pai. 

> [!NOTE]
> Os grupos de segurança não habilitados por email não têm suporte no momento. 

No exemplo a seguir, Maria, Sheila e o grupo Departamento de Vendas são atribuídos a um complemento. Como o Departamento de Vendas da Costa Oeste é um grupo aninhado, Humberto e Fábio não estão atribuídos a um suplemento. 

![Diagrama do departamento de vendas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Determinar se um grupo contém grupos aninhados

A maneira mais fácil de detectar se um grupo contém grupos aninhados é exibir o cartão de visita do grupo no Outlook. Se você inserir o nome do grupo no campo **Para** de um email e, em seguida, selecionar o nome do grupo quando ele for resolvido, ele mostrará se ele contém usuários ou grupos   aninhados. No exemplo abaixo, a guia **Membros** do cartão de visita do Outlook para o Grupo de Teste não mostra nenhum usuário   e apenas dois sub-grupos. 

![Guia Membros do cartão de visita do Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

É possível fazer a consulta inversa resolvendo o grupo para ver se ele é membro de algum grupo. No exemplo abaixo, você pode <b></b>ver na guia Associação do cartão de visita do Outlook que o Sub Group 1 é membro   do Grupo de Teste. 

![Guia Associação do cartão de visita do Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Observe que você pode usar a API do Azure Active Directory Graph para executar consultas para encontrar a lista de grupos em um grupo. Para obter mais informações, consulte [Operations on groups | Referência da API do Graph](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para a implantação de suplementos do Office 
Para lançar os complementos usando uma abordagem em fases, recomendamos o seguinte: 
1. Distribua o complemento para um pequeno conjunto de membros e participantes comerciais do departamento de TI. Você pode ativar o sinalizador **É uma implantação de teste.** Se a implantação for bem-sucedida, vá para a etapa 2. 

2. Role o complemento para mais pessoas dentro da empresa. Novamente, avalie os resultados e, se bem-sucedido, continue com a implantação completa. 

3. Execute uma adoção completa para todos os usuários. Desativar o sinalizador de **Is this a Test deployment**. 

Dependendo do tamanho do público-alvo, você pode adicionar ou remover etapas de lançamento.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar o complemento do Office usando o centro de administração 

1. No centro de administração, selecione **Configurações** e, em seguida, selecione **Aplicativos integrados.** 

2. Selecione **Obter aplicativos** na parte superior da página. O AppSource será carregado em um formato incorporado. Pesquise um complemento ou encontre-o clicando em Produto na nav esquerda.  Se o complemento tiver sido vinculado pelo ISV a um aplicativo SaaS ou a outros aplicativos e complementos e se o aplicativo SaaS for um aplicativo pago, você receberá uma caixa de diálogo para comprar a licença ou Implantar. Independentemente de você ter comprado a licença ou não, você pode continuar com a implantação. Selecione **Implantar**.  

3. Você verá a página **Configuração** onde todos os aplicativos estão listados. Se você não tiver permissões ou o acesso certo para implantar o aplicativo, as informações respectivas serão realçadas. Você pode selecionar os aplicativos que deseja implantar. Selecionando **Next**, você exibirá a **página Usuários.** Se o complemento não tiver sido vinculado pelo ISV, você será roteado para a página Usuários. 

4. Selecione **Todos**, **Usuários/grupos específicos** ou **Apenas eu** para especificar para quem o complemento é   implantado. Use a caixa Pesquisar para encontrar usuários ou grupos específicos. Se você estiver testando o complemento, selecione **É uma implantação de teste**. 

5. Selecione **Avançar**. Todos os recursos e permissões do aplicativo são exibidos em um único painel juntamente com informações de certificação se o aplicativo tiver a certificação do Microsoft 365. Selecionar o logotipo de certificação permite que o usuário veja mais detalhes sobre a certificação.  

6. Revise e selecione **Concluir implantação**.  

7. Um ícone verde "tick" é exibido quando o complemento é implantado. Siga as instruções na página para testar o complemento. 

> [!NOTE]
> Os usuários podem precisar relançar o Office para exibir o ícone do complemento na faixa de opções do aplicativo. Os complementos do Outlook podem levar até 24 horas para aparecerem nas faixas de opções do aplicativo. 

É uma boa prática informar aos usuários e grupos que o complemento implantado está disponível. Considere enviar um email que descreva quando e como usar o complemento. Inclua ou vincule para ajudar conteúdo ou perguntas frequentes que podem ajudar os usuários se eles têm problemas com o complemento. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um complemento a usuários e grupos 

Administradores globais e administradores do Exchange podem atribuir um complemento a todos ou a usuários e grupos específicos. Cada opção tem implicações: 

- **Todos**   Essa opção atribui o complemento a todos os usuários da organização. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para sua organização. 

- **Usuários**   Se você atribuir um complemento a um usuário individual e, em seguida, implantar o complemento a um novo usuário, primeiro adicione o novo usuário. 

- **Grupos**   Se você atribuir um complemento a um grupo, os usuários adicionados ao grupo serão atribuídos automaticamente ao complemento. Quando um usuário é removido de um grupo, o usuário perde o acesso ao complemento. Em ambos os casos, nenhuma ação adicional é necessária do administrador. 

- **Somente eu**   Se você atribuir um complemento apenas a si mesmo, o complemento será atribuído apenas à sua conta, o que é ideal para testar o complemento. 

A opção certa para sua organização depende da configuração. No entanto, recomendamos fazer atribuições usando grupos. Como administrador, você pode achar mais fácil gerenciar os complementos usando grupos e controlando a associação desses grupos em vez de atribuir usuários individuais a cada vez. Em algumas situações, talvez você queira restringir o acesso a um pequeno conjunto de usuários, fazendo atribuições a usuários específicos atribuindo usuários manualmente. 

### <a name="more-about-office-add-ins-security"></a>Mais sobre segurança de complementos do Office 
Os complementos do Office combinam um arquivo de manifesto XML que contém alguns metadados sobre o complemento, mas o mais importante aponta para um aplicativo Web que contém todo o código e a lógica. Os complementos podem variar em seus recursos. Por exemplo, os complementos podem:
- Exibir dados. 
- Leia o documento de um usuário para fornecer serviços contextuais. 
- Ler e gravar dados de e para o documento de um usuário para fornecer valor a esse usuário.  

Para obter mais informações sobre os tipos e recursos dos complementos do Office, consulte Visão geral da plataforma de [complementos](/office/dev/add-ins/overview/office-add-ins)do Office , especialmente a seção "Anatomia de um Add-in do Office". 

Para interagir com o documento do usuário, o complemento precisa declarar de que permissão ele precisa no manifesto. Um modelo de permissões de acesso para API JavaScript de cinco níveis fornece a base para privacidade e segurança para usuários de complementos do painel de tarefas. A maioria dos complementos na Office Store é de nível ReadWriteDocument com quase todos os complementos que suportam pelo menos o nível ReadDocument. Para obter mais informações sobre os níveis de permissão, consulte Solicitando permissões para uso da API em conteúdo e complementos do painel [de tarefas.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) 

Ao atualizar um manifesto, as alterações típicas são para o ícone e o texto de um complemento. Ocasionalmente, os comandos de complemento mudam. No entanto, as permissões do complemento não mudam. O aplicativo Web onde todo o código e a lógica para as executações do complemento podem mudar a qualquer momento, que é a natureza dos aplicativos Web. 

As atualizações para os complementos ocorrem da seguinte forma: 
- **Complemento de** linha de negócios : Nesse caso, em que um administrador carregou explicitamente um manifesto, o complemento exige que o administrador carregue um novo arquivo de manifesto para dar suporte a alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

- **Add-in** da Office Store : quando um administrador selecionou um complemento da Office Store, se um complemento for atualizado na Office Store, na próxima vez que os aplicativos relevantes do Office começarem, o complemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

> [!NOTE]
> Para o Word, Excel e PowerPoint [](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)usam um Catálogo de Aplicativos SharePoint para implantar os complementos aos usuários em um ambiente local sem conexão com o Microsoft 365 e/ou o suporte para os   SharePoint complementos necessários. Para Outlook use Exchange painel de controle para implantar em um ambiente local sem uma conexão com Microsoft 365.  

## <a name="add-in-states"></a>Estados de complementos
Um complemento pode estar no estado **On**   ou **Off.**   

| Estado | Como o estado ocorre | Impacto |
|:-----|:-----|:-----|
|**Ativo**  <br/> |O administrador carregou o complemento e o atribuiu a usuários ou grupos.  <br/> |Os usuários e grupos atribuídos ao complemento o veem nos clientes relevantes.  <br/> |
|**Desativado**  <br/> |O administrador desativou o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> Se o estado do add-in for alterado para Ativo, os usuários e grupos terão acesso a ele novamente.  <br/> |
|**Excluído**  <br/> |O administrador excluiu o suplemento.  <br/> |Os usuários e grupos atribuídos ao complemento não têm mais acesso a ele.  <br/> |
 
Considere a exclusão de um complemento se ninguém o estiver usando mais. Por exemplo, desligar um complemento pode fazer sentido se um add-in for usado somente durante períodos específicos do ano. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Gerenciar um Office de usuário usando o centro de administração

Após a implantação, os administradores também podem gerenciar o acesso do usuário aos complementos. 

1. No centro de administração, selecione **Configurações**, em seguida, selecione **Aplicativos integrados**. 
2. Na página Aplicativos integrados, ela exibirá uma lista de aplicativos que serão apenas os complementos ou os complementos que foram vinculados a outros aplicativos. 
3. Selecione um aplicativo **com Status** de   Mais **aplicativos disponíveis** para abrir o painel    **Gerenciar.**   O status de **mais aplicativos** disponíveis permite que você saiba que há mais integrações dos ISVs que ainda não   foram implantados. 
4. Na guia **Visão**   Geral, selecione **Implantar**. Alguns aplicativos exigem que você adicione usuários antes de selecionar Implantar. 
5. Selecione **Usuários**, selecione **É uma implantação de teste** e selecione **Toda** a organização, **Usuários/grupos específicos**   ou Apenas **eu**. Você também pode selecionar **Testar implantação** se preferir aguardar para   implantar o aplicativo em toda a organização. Usuários ou grupos específicos podem ser um grupo Microsoft 365, um grupo de segurança ou um grupo de distribuição. 
6. Selecione  **Atualizar**   e selecione **Feito**. Agora você pode selecionar **Implantar** na guia **Visão** Geral. 
7. Revise as informações do aplicativo e selecione **Implantar**.
8. Selecione **Concluído** na página Implantação concluída e revise os detalhes do teste ou implantação   completa na guia **Visão**    geral. 
9. Se o aplicativo tiver um status de  **Atualização** pendente, você poderá clicar no aplicativo para abrir o **painel** Gerenciar e atualizar o aplicativo. 
10. Para atualizar apenas os usuários, selecione a guia **Usuários** e faça a alteração apropriada. Selecione **Atualizar** depois de fazer suas alterações.  

## <a name="delete-an-add-in"></a>Excluir um complemento

Você também pode excluir um complemento que foi implantado.

1. No centro de administração, selecione **Configurações**, em seguida, selecione **Aplicativos integrados** .
2. Selecione qualquer linha para exibir o painel de gerenciamento. 
3. Selecione a **guia Configuração.** 
4. Selecione o complemento que você deseja excluir e selecione **Remover**.  

> [!NOTE]
>  Se o complemento tiver sido implantado por outro administrador, o botão Remover será desabilitado. Somente o administrador que implantou o aplicativo ou um administrador global pode excluir o complemento.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Cenários em que Exchange administrador não pode implantar um add-in 

Há dois casos em que um administrador Exchange não poderá implantar um complemento:
- Se um add-in precisar de permissão para OMs Graph APIs e precisar de consentimento de um administrador global.
- Se um complemento estiver vinculado a dois ou mais complementos e webapps, e pelo menos um desses complementos for implantado por outro administrador (exchange/global) e a atribuição do usuário não for uniforme. Só permitimos a implantação de complementos quando a atribuição do usuário for a mesma para todos os aplicativos já implantados.  


## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Qual função de administrador preciso acessar aplicativos integrados?

Somente administradores globais podem acessar Aplicativos Integrados. Os aplicativos integrados não aparecerão na nav esquerda para outros administradores.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Por que vejo o Add-in no nav esquerdo em Configuração, mas não aplicativos integrados?

Pode haver alguns motivos:

- O administrador conectado é um Exchange administrador.
- O cliente está na nuvem soberana e a experiência de aplicativos integrados ainda está disponível para clientes de nuvem soberanas.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Quais aplicativos posso implantar a partir de aplicativos integrados?

Os aplicativos integrados permitem Teams implantação de aplicativos Web, Teams, Excel, PowerPoint, Word, Outlook e SPFx aplicativos. Para os complementos, os aplicativos integrados suportam a implantação para Exchange caixas de correio online e não caixas de correio Exchange locais.

### <a name="can-administrators-delete-or-remove-apps"></a>Os administradores podem excluir ou remover aplicativos?

Sim. Os administradores globais podem excluir ou remover aplicativos.

- Selecione um aplicativo na exibição de lista. Na guia **Configuração,** selecione quais aplicativos remover.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Os aplicativos integrados estão disponíveis na nuvem soberana?

Não. Os aplicativos integrados não estão disponíveis para clientes de nuvem soberanas.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Os aplicativos integrados estão disponíveis nas nuvens do governo?

Não. Os aplicativos integrados não estão disponíveis para clientes de nuvem do governo.
