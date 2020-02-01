---
title: Compartilhamento de auditoria para localizar recursos compartilhados com usuários externos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 'O compartilhamento é uma atividade importante no SharePoint Online e no OneDrive for Business. Agora, os administradores podem usar a auditoria de compartilhamento no log de auditoria do Office 365 para identificar recursos compartilhados com usuários fora da sua organização. '
ms.openlocfilehash: f979bd9a3b796fc3e9e84872df7e0b6071aefc03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597278"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>Compartilhamento de auditoria para localizar recursos compartilhados com usuários externos

O compartilhamento é uma atividade importante no SharePoint Online e no OneDrive for Business e é amplamente usado nas organizações do Office 365. Os administradores podem usar a auditoria de compartilhamento no log de auditoria do Office 365 para determinar como o compartilhamento é usado em sua organização. 
  
## <a name="the-sharepoint-sharing-schema"></a>O esquema de compartilhamento do SharePoint

O compartilhamento de eventos (não incluindo eventos relacionados à política de compartilhamento e links de compartilhamento) são diferentes dos eventos relacionados a arquivos e pastas de uma maneira principal: um usuário está executando uma ação que tem efeito em outro usuário. Por exemplo, quando um usuário de recurso A dá acesso a um arquivo para o usuário B. Neste exemplo, o usuário A é o *usuário* que está agindo e o usuário B é o *usuário de destino*. No esquema de arquivos do SharePoint, a ação do usuário que está agindo só afeta o próprio arquivo. Quando o usuário A abre um arquivo, as únicas informações necessárias no evento **Fileaccessed** são o usuário que está agindo. Para resolver essa diferença, há um esquema separado, chamado esquema de *compartilhamento do SharePoint*, que captura mais informações sobre o compartilhamento de eventos. Isso garante que os administradores tenham visibilidade de quem compartilhou um recurso e do usuário com o qual o recurso foi compartilhado. 
  
O esquema de compartilhamento fornece dois campos adicionais em um registro de auditoria relacionado aos eventos de compartilhamento: 
  
- **TargetUserOrGroupType:** Identifica se o usuário ou grupo de destino é membro, convidado, grupo do SharePoint, grupo de segurança ou parceiro.

- **TargetUserOrGroupName:** Armazena o UPN ou o nome do usuário ou grupo de destino com o qual um recurso foi compartilhado (usuário B no exemplo anterior). 

Esses dois campos, além de outras propriedades do esquema de log de auditoria do Office 365, como User, Operation e Date, podem informar a história completa sobre *qual* usuário compartilhou *o* recurso com *quem* e *quando*. 
  
Há outra propriedade de esquema que é importante para o texto de compartilhamento. Quando você exporta os resultados da pesquisa de log de auditoria, a coluna **AuditData** no arquivo CSV exportado armazena informações sobre o compartilhamento de eventos. Por exemplo, quando um usuário compartilha um site com outro usuário, isso é feito adicionando-se o usuário de destino a um grupo do SharePoint. A coluna **AuditData** captura essas informações para fornecer contexto para administradores. Consulte a [etapa 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) para obter instruções sobre como analisar as informações na coluna **AuditData** .

## <a name="sharepoint-sharing-events"></a>Eventos de compartilhamento do SharePoint

O compartilhamento é definido pelo quando um usuário (o usuário *agindo* ) deseja compartilhar um recurso com outro usuário (o usuário de *destino* ). Os registros de auditoria relacionados ao compartilhamento de um recurso com um usuário externo (um usuário que está fora da sua organização e não têm uma conta de convidado no Azure Active Directory da sua organização) são identificados pelos seguintes eventos, que são registrados no Office 365 log de auditoria:

- **SharingInvitationCreated:** Um usuário da sua organização tentou compartilhar um recurso (provavelmente um site) com um usuário externo. Isso resulta em um convite de compartilhamento externo enviado para o usuário de destino. Nenhum acesso ao recurso é concedido neste ponto.

- **SharingInvitationAccepted:** O usuário externo aceitou o convite de compartilhamento enviado pelo usuário que está agindo e agora tem acesso ao recurso.

- **AnonymousLinkCreated:** Um link anônimo (também chamado de link "qualquer pessoa") é criado para um recurso. Como um link anônimo pode ser criado e copiado, é razoável supor que qualquer documento que tenha um link anônimo tenha sido compartilhado com um usuário de destino.

- **AnonymousLinkUsed:** Como o nome indica, esse evento é registrado quando um link anônimo é usado para acessar um recurso. 

- **SecureLinkCreated:** Um usuário criou um "link de pessoas específico" para compartilhar um recurso com uma pessoa específica. Este usuário de destino pode ser alguém externo à sua organização. A pessoa com a qual o recurso é compartilhado é identificada no registro de auditoria para o evento **AddedToSecureLink** . Os carimbos de data/hora desses dois eventos são quase idênticos.

- **AddedToSecureLink:** Um usuário foi adicionado a um link de pessoas específico. Use o campo **TargetUserOrGroupName** neste evento para identificar o usuário adicionado ao link pessoas correspondente específico. Este usuário de destino pode ser alguém externo à sua organização.

## <a name="sharing-auditing-work-flow"></a>Fluxo de trabalho de auditoria de compartilhamento
  
Quando um usuário (o usuário agindo) deseja compartilhar um recurso com outro usuário (o usuário de destino), o SharePoint (ou o OneDrive for Business) primeiro verifica se o endereço de email do usuário de destino já está associado a uma conta de usuário no diretório da organização. Se o usuário de destino estiver no diretório (e tiver uma conta de usuário convidado correspondente), o SharePoint fará o seguinte:
  
-  O atribui imediatamente as permissões de usuário de destino para acessar o recurso adicionando o usuário de destino ao grupo apropriado do SharePoint e registra um evento **AddedToGroup** . 
    
- Envia uma notificação de compartilhamento para o endereço de email do usuário de destino.
    
- Registra um evento **sharingset** . Esse evento tem um nome amigável de "arquivo compartilhado, pasta ou site" em **atividades de compartilhamento e acesso de solicitação** no seletor de atividades da ferramenta de pesquisa de log de auditoria. Veja a captura de tela na [etapa 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Se uma conta de usuário para o usuário de destino não estiver no diretório, o SharePoint fará o seguinte: 
    
   - Registra um dos eventos a seguir com base em como o recurso é compartilhado:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (esse evento é registrado somente quando o recurso compartilhado é um site)
    
   - Quando o usuário de destino aceita o convite de compartilhamento que é enviado a eles (clicando no link no convite), o SharePoint registra um evento **SharingInvitationAccepted** e atribui as permissões de usuário de destino para acessar o recurso. Se o usuário de destino for enviado um link anônimo, o evento **AnonymousLinkUsed** será registrado depois que o usuário de destino usar o link para acessar o recurso. Para links seguros, um evento **Fileaccessd** é registrado quando um usuário externo usa o link para acessar o recurso.

Informações adicionais sobre o usuário de destino também são registradas, como a identidade do usuário para o qual o convite se destina e o usuário que aceita o convite. Em alguns casos, esses usuários (ou endereços de email) podem ser diferentes. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Como identificar recursos compartilhados com usuários externos

Um requisito comum para administradores é criar uma lista de todos os recursos que foram compartilhados com usuários fora da organização. Usando a auditoria de compartilhamento no Office 365, os administradores podem gerar essa lista. Veja como.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Etapa 1: Pesquisar eventos de compartilhamento e exportar os resultados para um arquivo CSV

A primeira etapa é Pesquisar o log de auditoria do Office 365 para eventos de compartilhamento. Para obter mais informações (incluindo as permissões necessárias) sobre pesquisa no log de auditoria, consulte [Pesquisar o log de auditoria no centro de conformidade de & de segurança](search-the-audit-log-in-security-and-compliance.md).
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante.
    
3. No painel esquerdo do centro de conformidade & segurança, clique em ****  > **pesquisa de log de auditoria**de pesquisa.
    
    É exibida a página **Pesquisa de log de auditoria**. 
    
4. Em **atividades**, clique em **compartilhar e acessar as atividades de solicitação** para pesquisar eventos relacionados ao compartilhamento. 
    
    ![Em atividades, selecione compartilhar e acessar atividades de solicitação](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selecione um intervalo de data e hora para localizar os eventos de compartilhamento que ocorreram dentro desse período. 
    
6. Clique em **Pesquisar** para executar a pesquisa. 
    
7. Quando a pesquisa é concluída e os resultados são exibidos, clique em **Exportar resultados** \> **baixar todos os resultados**.
    
    Após selecionar a opção Exportar, uma mensagem na parte inferior da janela solicitará que você abra ou salve o arquivo CSV.
    
8. Clique em **salvar** \> **salvar como** e salve o arquivo CSV em uma pasta no computador local. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Etapa 2: usar o editor PowerQuery para formatar o log de auditoria exportado

A próxima etapa é usar o recurso transformação JSON no editor do Power Query no Excel para dividir cada propriedade na coluna **AuditData** (que consiste em um objeto JSON de várias propriedades) em sua própria coluna. Isso permite que você filtre colunas para exibir registros relacionados ao compartilhamento

Para obter instruções passo a passo, consulte "etapa 2: Formatar o log de auditoria exportado usando o editor de consulta de alimentação" em [exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Etapa 3: filtrar o arquivo CSV para recursos compartilhados com usuários externos

A próxima etapa é filtrar o CSV para os diferentes eventos relacionados a compartilhamento que foram descritos anteriormente na seção [eventos de compartilhamento do SharePoint](#sharepoint-sharing-events) . Como alternativa, você pode filtrar a coluna **TargetUserOrGroupType** para exibir todos os registros onde o valor dessa propriedade é **Guest**. 

Depois de seguir as instruções da etapa anterior para preparar o arquivo CSV usando o editor PowerQuery, faça o seguinte:
    
1. Abra o arquivo do Excel que você criou na etapa 2. 

2. Na guia **página inicial** , clique em **classificar & filtro**e, em seguida, clique em **Filtrar**.
    
3. Na lista suspensa **classificar & filtro** na coluna **operações** , desmarque todas as seleções e selecione um ou mais dos seguintes eventos relacionados a compartilhamento e clique em **OK**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    O Excel exibe as linhas dos eventos que você selecionou.
    
4. Vá até a coluna chamada **TargetUserOrGroupType** e selecione-a. 
    
5. Na lista suspensa **classificar & filtro** , desmarque todas as seleções e, em seguida, selecione **TargetUserOrGroupType: convidado**e clique em **OK**.
    
    Agora o Excel exibe as linhas para o compartilhamento de eventos e onde o usuário de destino está fora da sua organização, porque usuários externos são identificados pelo valor **TargetUserOrGroupType: Guest**. 
  
> [!TIP]
> Para os registros de auditoria exibidos, a coluna **ObjectID** identifica o recurso que foi compartilhado com o usuário de destino; por exemplo `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
