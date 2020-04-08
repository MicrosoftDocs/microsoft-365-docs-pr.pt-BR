---
title: Gerenciar a implantação de suplementos do Office 365 no centro de administração
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba como implantar suplementos para usuários e grupos em sua organização usando a implantação centralizada no centro de administração.
ms.openlocfilehash: 74c1ceb8e9d2193e7ad7afd2b339d29d54780517
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189005"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a>Gerenciar a implantação de suplementos do Office 365 no Centro de administração do Microsoft 365

Os suplementos do Office ajudam você a personalizar seus documentos e simplificar a forma como você acessa as informações na Web (Confira [começar a usar o suplemento do Office](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Como administrador, você pode implantar suplementos do Office para os usuários em sua organização. Você pode fazer isso usando o recurso de implantação centralizado no centro de administração do Microsoft 365.
  
A implantação centralizada é a maneira recomendada e mais rica de recursos para a maioria dos administradores implantar suplementos para usuários e grupos em uma organização. Para obter mais informações sobre como determinar se sua organização pode dar suporte à implantação centralizada, consulte [determinar se a implantação centralizada de suplementos funciona para sua organização do Office 365](centralized-deployment-of-add-ins.md).
  
A implantação centralizada oferece os seguintes benefícios:
  
- Um administrador global pode atribuir um suplemento diretamente a um usuário, a vários usuários por meio de um grupo ou a todos no locatário.
    
- Quando o aplicativo do Office relevante é iniciado, o suplemento é automaticamente baixado para o usuário. Se o suplemento suportar comandos de suplemento, o suplemento aparecerá automaticamente na faixa de opções no aplicativo do Office.
    
- Os suplementos não aparecerão mais para os usuários se o administrador desativar ou excluir o suplemento ou se o usuário for removido do Azure Active Directory ou de um grupo ao qual o suplemento está atribuído.
    
> [!NOTE]
>  Para o Word, Excel e PowerPoint, use um [Catálogo de aplicativos do SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implantar suplementos para usuários em um ambiente local sem conexão com o Office 365 e/ou suporte para suplementos do SharePoint necessários. > para o Outlook use o painel de controle do Exchange para implantar em um ambiente local sem uma conexão com o Office 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Abordagem recomendada para implantar suplementos do Office

Considere a possibilidade de implantar suplementos em uma abordagem em fases para ajudar a garantir que a implantação do suplemento fique tranqüila. Recomendamos o plano a seguir:
  
1. Distribua o suplemento para um pequeno conjunto de participantes e membros de negócios do departamento de ti. Avalie se a implantação foi bem-sucedida e, em caso afirmativo, vá para a etapa 2.
    
2. Reverta para um conjunto maior de pessoas dentro da empresa que usará o suplemento. Novamente, avaliar os resultados e, se tudo tiver sido bem, vá para a próxima etapa de uma implantação completa.
    
3. Distribuição completa para o público-alvo dos usuários.
    
Dependendo do tamanho do público-alvo, talvez você queira adicionar ou remover etapas de distribuição.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implantar um suplemento do Office usando o centro de administração

Antes de começar, confira [determinar se a implantação centralizada de suplementos funciona para sua organização do Office 365](centralized-deployment-of-add-ins.md).

  
1. No centro de administração do Microsoft 365, vá para a página **configurações** > **de suplementos.**
    
2. Selecione **implantar suplemento** na parte superior da página. Na página Visão geral, selecione **Avançar**.
    
3. Selecione uma opção e siga as instruções.
  
4. Se você selecionou a opção para adicionar um suplemento da Office Store, agora você pode fazer a seleção do seu suplemento. Observe que você pode exibir os suplementos disponíveis por meio das categorias **sugeridos para você**, **classificação**ou **nome**. Somente suplementos gratuitos estão disponíveis para adicionar da Office Store. Atualmente, não há suporte para suplementos pagos. Depois de ter selecionado o suplemento, você precisará concordar com alguns termos e condições adicionais para continuar. <br/><br/> Observação: com a opção da Office Store, as atualizações e aprimoramentos do suplemento serão disponibilizadas automaticamente para os usuários sem a intervenção.

5. Na próxima página, selecione **todos**, **usuários/grupos específicos** ou **apenas eu** para especificar quem o suplemento será implantado. Use a caixa Pesquisar para localizar os usuários ou grupos nos quais você deseja implantar o suplemento. <br/>Observação: Saiba mais sobre os outros Estados que se aplicam a um suplemento. Confira [Estados de suplementos](#add-in-states) mais adiante neste tópico.
  
6. Selecione **Implantar**.
  
7. Um tique verde será exibido quando o suplemento tiver sido implantado. Você pode seguir as instruções na página para testar se o suplemento foi implantado com êxito.

> [!NOTE]
> Talvez os usuários precisem reiniciar o Office para ver o ícone do suplemento exibido na faixa de opções do aplicativo. Os suplementos do Outlook podem levar até 24 horas para serem exibidos nas faixas de opções dos usuários.
    
8. Quando terminar, selecione **Avançar**. Se você implantou para si mesmo, é possível selecionar **alterar quem tem acesso ao suplemento** para implantar para mais usuários.



Se você implantou o suplemento para membros da sua organização que não é a si, siga as instruções exibidas para anunciar efetivamente a implantação do suplemento. <br/>Você verá o suplemento juntamente com outros aplicativos no Office 365.
  
É uma boa ideia informar os usuários e grupos que você implantou o suplemento para que eles saibam que ele está disponível. Considere enviar um email para eles, que descreve quando e como usar o suplemento e explica como o suplemento pode ajudá-lo a realizar seus trabalhos melhor. Incluir ou vincular a um conteúdo de ajuda relevante ou perguntas frequentes que podem ajudar se os usuários tiverem problemas com o suplemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerações ao atribuir um suplemento aos usuários e grupos

Os administradores podem atribuir um suplemento a todos ou a usuários e grupos específicos. Cada opção tem implicações:
  
- **Todos**: como o nome sugere, essa opção atribui o suplemento a todos os usuários no locatário. Use essa opção com cautela e apenas para suplementos que sejam realmente universais para a sua organização. 
    
- **Usuários**: se você atribuir um suplemento a um usuário individual, para implantar o suplemento em um novo usuário, será necessário primeiro adicionar esse usuário. O mesmo se aplica à remoção de usuários. 
    
- **Grupos**: Se você atribuir um suplemento a um grupo, os usuários adicionados ao grupo serão atribuídos automaticamente ao suplemento. E, quando um usuário é removido de um grupo, o usuário perde o acesso ao suplemento. Em ambos os casos, nenhuma ação adicional é necessária de você como administrador. 

- **Apenas eu**: se você atribuir um suplemento a si mesmo, o atribui o suplemento somente à sua conta. Isso é ideal se você deseja testar o suplemento primeiro.
    
A opção adequada para sua organização depende da sua configuração. No entanto, recomendamos fazer atribuições por meio de grupos. Como administrador, você pode achar mais fácil gerenciar suplementos usando grupos e controlar a associação desses grupos em vez de alterar os usuários atribuídos a cada vez. Por outro lado, em algumas situações, talvez você queira restringir o acesso a um conjunto muito pequeno de usuários e, portanto, fazer atribuições a usuários específicos. Como resultado, será necessário gerenciar os usuários atribuídos manualmente.
  
### <a name="add-in-states"></a>Estados de suplementos

Os administradores podem ativar ou desativar os suplementos implantados para todos os usuários do centro de administração do Microsoft 365.

1.    No centro de administração, vá para a página **configurações** > **de suplementos.** 
2.    Selecione o suplemento implantado. 
3.    Clique **no botão** **de alternância para ativar ou** **desativar**o suplemento. 
4.    Salve as alterações.  

Um dos três Estados de suplementos também está disponível.
 
|**State**|**Como o estado ocorre**|**Impacto**|
|:-----|:-----|:-----|
|**Active**  <br/> |O administrador carregou o suplemento e o atribuiu a usuários ou grupos.  <br/> |Os usuários e grupos atribuídos ao suplemento o vêem nos clientes relevantes.  <br/> |
|**Desativado**  <br/> |O administrador desativou o suplemento.  <br/> |Os usuários e grupos atribuídos ao suplemento não têm mais acesso a ele.  <br/> Se o estado do suplemento for alterado para **ativo**, os usuários e grupos terão acesso a ele novamente.  <br/> |
|**Excluído**  <br/> |O administrador excluiu o suplemento.  <br/> |Os usuários e grupos atribuídos ao suplemento não têm mais acesso a ele.  <br/> |
   
Considere excluir um suplemento se ninguém o estiver usando. A desativação de um suplemento pode fazer sentido se um suplemento for usado somente durante horários específicos do ano.
  
### <a name="security-of-office-add-ins"></a>Segurança de suplementos do Office

Os suplementos do Office combinam um arquivo de manifesto XML que contém alguns metadados sobre o suplemento, mas que, mais importante, apontam para um aplicativo Web que contém todo o código e a lógica. Os suplementos podem variar em seus recursos. Por exemplo, os suplementos podem:
  
- Dados de exibição.
    
- Leia o documento de um usuário para fornecer serviços contextuais.
    
- Ler e gravar dados de e para o documento de um usuário para fornecer valor a esse usuário.
    
Para obter mais informações sobre os tipos e recursos dos suplementos do Office, confira [visão geral da plataforma](https://go.microsoft.com/fwlink/p/?linkid=846362)de suplementos do Office, especialmente a seção "Anatomia de um suplemento do Office."
  
Para interagir com o documento do usuário, o suplemento precisa declarar a permissão necessária no manifesto. Um modelo de permissões de acesso à API JavaScript de cinco níveis fornece a base para privacidade e segurança para usuários de suplementos do painel de tarefas. A maioria dos suplementos na Office Store são de nível ReadWriteDocument com quase todos os suplementos que suportam pelo menos o nível de ReadDocument. Para obter mais informações sobre os níveis de permissão, consulte [solicitando permissões para uso da API em suplementos de conteúdo e de painel de tarefas](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
Ao atualizar um manifesto, as alterações típicas são o ícone e o texto de um suplemento. Ocasionalmente, os comandos de suplemento são alterados. No entanto, as permissões do suplemento não são alteradas. O aplicativo Web em que todo o código e a lógica para o suplemento é executado pode mudar a qualquer momento, que é a natureza dos aplicativos Web.
  
As atualizações para suplementos acontecem da seguinte maneira:
  
- **Suplemento de linha de negócios:** Nesse caso, onde um administrador carregou explicitamente um manifesto, o suplemento requer que o administrador carregue um novo arquivo de manifesto para dar suporte às alterações de metadados. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

    > [!NOTE]
    > O administrador não precisa remover um suplemento LOB para fazer uma atualização.   Na seção suplementos, o administrador pode simplesmente clicar no suplemento LOB e escolher o **botão atualizar** no canto inferior direito. A atualização funcionará somente se a versão do novo suplemento for maior do que a do suplemento existente.   
    
- **Suplemento da Office Store:** Quando um administrador selecionou um suplemento da Office Store, se um suplemento for atualizado na Office Store, o suplemento será atualizado posteriormente na implantação centralizada. Na próxima vez que os aplicativos relevantes do Office iniciarem, o suplemento será atualizado. O aplicativo Web pode mudar a qualquer momento. 

### <a name="edit-add-in-access"></a>Editar acesso de suplemento

Pós-implantação, os administradores também podem modificar o acesso do usuário a suplementos.

1. No centro de administração, vá para a página **configurações** > de **&** de suplementos.

2. Selecione o suplemento implantado.

3. Clique em **Editar** em **quem tem acesso**.
4. Salve as alterações.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir downloads de suplementos desativando a Office Store em todos os clientes (exceto Outlook)

> [!NOTE]
> A instalação do suplemento do Outlook é gerenciada por um [processo diferente](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Como uma organização, talvez você queira impedir o download de novos suplementos do Office da Office Store. Isso pode ser usado em conjunto com a implantação centralizada para garantir que apenas os suplementos aprovados pela organização sejam implantados para os usuários da sua organização.
  
Para desativar a aquisição de suplementos:
  
1. No centro de administração, vá para a página **Configurações** \> [Serviços&amp; suplementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Selecione **aplicativos e serviços de Propriedade do usuário**.
    
4. Desmarque a opção para permitir que os usuários acessem a Office Store.

Isso impedirá que todos os usuários adquiram os seguintes suplementos do repositório.
  
- Suplementos para Word, Excel e PowerPoint 2016 de:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aquisições começando no **AppSource**
    
- Suplementos no Office 365
    
Um usuário que tentar acessar o repositório verá a seguinte mensagem: **infelizmente, o Office 365 foi configurado para impedir a aquisição individual de suplementos da Office Store.**
  
O suporte à desativação da Office Store está disponível nas seguintes versões:
  
- Windows: 16.0.9001-disponível no momento.
    
- Mac: 16.10.18011401-disponível no momento.
    
- iOS: 2.9.18010804-disponível no momento.
    
- A Web-disponível no momento.
    
Isso não impede que um administrador use a implantação centralizada para atribuir um suplemento da Office Store.
  
Para impedir que um usuário entre com uma conta da Microsoft, você pode restringir o logon para usar apenas a conta organizacional. Para obter mais informações, consulte [aqui](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores e aquisição de suplementos da loja

A regulamentação geral de proteção de dados (RGPD) é uma regulamentação de União Européia que se torna efetiva 25 de maio de 2018. Ele fornece direitos e proteção de seus dados aos usuários. Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados a partes que seu pai ou guardião não aprovou. A idade específica definida como um secundário depende da região onde o indivíduo está localizado.
  
Regiões que têm regulamentações estatutárias sobre o consentimento dos pais incluem Estados Unidos, Coréia do Sul, Reino Unido e União Européia. Para essas regiões, um pequeno será bloqueado (por meio do Azure Active Directory) para obter qualquer suplemento novo do Office a partir da loja e executar suplementos que foram adquiridos anteriormente. Para países sem regulamentações legais, não haverá restrições de download.
  
Um usuário é determinado como um secundário com base nos dados especificados no Azure Active Directory. O administrador do locatário é responsável por declarar o grupo de idades legais e o consentimento do responsável para esse usuário.
  
Se o pai/guardião for enviado a um secundário usando um suplemento específico, o administrador do locatário poderá usar a implantação centralizada para implantar esse suplemento em todos os menores que tiverem consentimento.
  
Ser compatível com o RGPD para menores que você precisa para garantir que uma das seguintes versões do Office seja implantada em sua escola/organização.
  
 **Para Word, Excel, PowerPoint e Project**: 
  
|||
|:-----|:-----|
|**Plataforma** <br/> |**Número de compilação** <br/> |
|Office 2016 ProPlus mensal para Windows  <br/> |9001,2138   <br/> |
|Office 2016 ProPlus semestral  <br/> |8431,2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para a Web  <br/> |Não disponível  <br/> |
   
 **Para o Outlook**: 
  
|||
|:-----|:-----|
|**Plataforma** <br/> |**Número de compilação** <br/> |
|Outlook 2016 para Windows (MSI)  <br/> |Compilação não TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Não disponível  <br/> |
   
 **Requisitos do Office 2013**
  
O Word, o Excel e o PowerPoint 2013 para Windows oferecerão suporte às mesmas verificações secundárias se a ADAL (biblioteca de autenticação do Active Directory) estiver habilitada. Há duas opções de conformidade, conforme explicado a seguir.
  
- **Habilitar Adal**. Este artigo explica como habilitar a ADAL para o Office 2013: [usando a autenticação moderna do office 365 com clientes do Office](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).<br/>Você também precisa definir as chaves do registro para habilitar a ADAL, conforme explicado em [habilitar a autenticação moderna para o Office 2013 em dispositivos Windows](../security-and-compliance/enable-modern-authentication.md).<br/>Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:
    
  - [Descrição da atualização de segurança para o Office 2013:10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, atualização para o Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Não habilite a Adal**. Se você não conseguir habilitar a ADAL no Office 2013, nossa recomendação é usar a política de grupo para desativar o repositório para os clientes do Office. As informações sobre como desativar as configurações de aplicativo para Office estão localizadas [aqui](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Experiência do usuário final com suplementos

Agora que você implantou o suplemento, os usuários finais podem começar a usá-lo em seus aplicativos do Office (Confira [começar a usar o suplemento do Office](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). O suplemento será exibido em todas as plataformas compatíveis com o suplemento.
  
Se o suplemento suportar comandos de suplemento, os comandos serão exibidos na faixa de opções do Office. No exemplo a seguir, a **citação de pesquisa** de comando aparece para o suplemento de **citações** . 

![Faixa de opções do Office com citações de pesquisa](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Se o suplemento implantado não oferecer suporte a comandos de suplemento ou se você quiser exibir todos os suplementos implantados, poderá exibi-los por meio **de meus**suplementos. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>No Word 2016, no Excel 2016 ou no PowerPoint 2016

1. Selecione **Inserir \> meus**suplementos. 
    
2. Selecione a guia **Administração gerenciada** na janela suplementos do Office. 
    
3. Clique duas vezes no suplemento que você implantou anteriormente (neste exemplo, **citações** ). <br/>![Guia Administração gerenciada da página de suplementos do Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>No Outlook

1. Na faixa de opções **página inicial** , selecione **obter suplementos**.<br/>![Botão armazenar no Outlook](../../media/getaddinsicon.png)
  
2. Selecione **Administração gerenciada** no painel de navegação esquerdo.

## <a name="delete-the-add-in"></a>Excluir o suplemento

Você também pode excluir um suplemento implantado.

1. No centro de administração, vá para a página **configurações** > de **&** de suplementos.

2. Selecione o suplemento implantado.

3. Clique em **excluir suplemento**. Remova o botão do suplemento no canto inferior direito.
4. Valide suas seleções e escolha **remover suplemento**.
  
## <a name="learn-more"></a>Saiba mais

Saiba mais sobre a criação e [a criação de suplementos do Office](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Use cmdlets do PowerShell de implantação centralizada para gerenciar suplementos](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).
  
[Solução de problemas: o usuário não está vendo suplementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
