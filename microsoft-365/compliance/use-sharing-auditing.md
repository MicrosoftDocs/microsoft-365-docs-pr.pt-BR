---
title: Usar a auditoria de compartilhamento no log de auditoria
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
description: O administrador pode aprender a usar a auditoria de compartilhamento no log de auditoria Microsoft 365 para identificar recursos compartilhados com usuários fora de sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819291"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Usar a auditoria de compartilhamento no log de auditoria

O compartilhamento é uma atividade SharePoint online e OneDrive for Business, e é amplamente usado em organizações. Os administradores podem usar a auditoria de compartilhamento no log de auditoria para determinar como o compartilhamento é usado em sua organização. 
  
## <a name="the-sharepoint-sharing-schema"></a>O SharePoint de compartilhamento

Os eventos de compartilhamento (sem incluir eventos relacionados à política de compartilhamento e links de compartilhamento) são diferentes dos eventos relacionados a arquivos e pastas de uma maneira primária: um usuário está executando uma ação que tem efeito em outro usuário. Por exemplo, quando um recurso User A dá acesso ao Usuário B a um arquivo. Neste exemplo, o Usuário A é o *usuário interino* e o Usuário B é o *usuário de destino.* No esquema SharePoint Arquivo, a ação do usuário em ação afeta apenas o próprio arquivo. Quando o Usuário A abre um arquivo, a única informação necessária no **evento FileAccessed** é o usuário interino. Para resolver essa diferença, há um esquema separado, chamado SharePoint esquema de *compartilhamento,* que captura mais informações sobre eventos de compartilhamento. Isso garante que os administradores tenham visibilidade sobre quem compartilhou um recurso e o usuário com quem o recurso foi compartilhado. 
  
O esquema de compartilhamento fornece dois campos adicionais em um registro de auditoria relacionado a eventos de compartilhamento: 
  
- **TargetUserOrGroupType:** Identifica se o usuário de destino ou grupo é um Membro, Convidado, SharePointGroup, SecurityGroup ou Parceiro.

- **TargetUserOrGroupName:** Armazena o UPN ou o nome do usuário de destino ou grupo com o que um recurso foi compartilhado (Usuário B no exemplo anterior). 

Esses dois campos, além de outras propriedades do esquema de log de auditoria, como Usuário,  Operação  e Data, podem contar a história completa sobre qual usuário compartilhou o recurso com quem e *quando*.  
  
Há outra propriedade de esquema que é importante para o artigo de compartilhamento. Quando você exporta resultados de pesquisa de log de auditoria, a coluna **AuditData** no arquivo CSV exportado armazena informações sobre eventos de compartilhamento. Por exemplo, quando um usuário compartilha um site com outro usuário, isso é feito adicionando o usuário de destino a um SharePoint grupo. A **coluna AuditData** captura essas informações para fornecer contexto para administradores. Consulte [a Etapa 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) para obter instruções sobre como analisar as informações na **coluna AuditData.**

## <a name="sharepoint-sharing-events"></a>SharePoint eventos de compartilhamento

O compartilhamento é definido por quando um usuário (o *usuário* interino) deseja compartilhar um recurso com outro usuário (o *usuário de* destino). Os registros de auditoria relacionados ao compartilhamento de um recurso com um usuário externo (um usuário que está fora da sua organização e não tem uma conta de convidado no Azure Active Directory da sua organização) são identificados pelos seguintes eventos, que são registrados no log de auditoria:

- **SharingInvitationCreated:** Um usuário em sua organização tentou compartilhar um recurso (provavelmente um site) com um usuário externo. Isso resulta em um convite de compartilhamento externo enviado ao usuário de destino. Nenhum acesso ao recurso é concedido neste ponto.

- **SharingInvitationAccepted:** O usuário externo aceitou o convite de compartilhamento enviado pelo usuário interino e agora tem acesso ao recurso.

- **AnonymousLinkCreated:** Um link anônimo (também chamado de link "Qualquer pessoa" é criado para um recurso. Como um link anônimo pode ser criado e copiado, é razoável supor que qualquer documento que tenha um link anônimo tenha sido compartilhado com um usuário de destino.

- **AnonymousLinkUsed:** Como o nome sugere, esse evento é registrado quando um link anônimo é usado para acessar um recurso. 

- **SecureLinkCreated:** Um usuário criou um "link de pessoas específicas" para compartilhar um recurso com uma pessoa específica. Esse usuário de destino pode ser alguém externo à sua organização. A pessoa com a quem o recurso é compartilhado é identificada no registro de auditoria do **evento AddedToSecureLink.** Os carimbos de data/hora desses dois eventos são quase idênticos.

- **AddedToSecureLink:** Um usuário foi adicionado a um link de pessoas específico. Use o **campo TargetUserOrGroupName** neste evento para identificar o usuário adicionado ao link de pessoas específicas correspondente. Esse usuário de destino pode ser alguém externo à sua organização.

## <a name="sharing-auditing-work-flow"></a>Compartilhamento de fluxo de trabalho de auditoria
  
Quando um usuário (o usuário interino) deseja compartilhar um recurso com outro usuário (o usuário de destino), o SharePoint (ou OneDrive for Business) primeiro verifica se o endereço de email do usuário de destino já está associado a uma conta de usuário no diretório da organização. Se o usuário de destino estiver no diretório (e tiver uma conta de usuário convidado correspondente), SharePoint faça as seguintes coisas:
  
-  Atribui imediatamente as permissões de usuário de destino para acessar o recurso adicionando o usuário de destino ao grupo de SharePoint apropriado e registra um **evento AddedToGroup.** 
    
- Envia uma notificação de compartilhamento para o endereço de email do usuário de destino.
    
- Registra um **evento SharingSet.** Este evento tem um nome amigável de "Arquivo  compartilhado, pasta ou site" em Atividades de Compartilhamento e solicitação de acesso no selador de atividades da ferramenta de pesquisa de log de auditoria. Consulte a captura de tela [na Etapa 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Se uma conta de usuário para o usuário de destino não estiver no diretório, SharePoint faça o seguinte: 
    
   - Registra um dos seguintes eventos, com base em como o recurso é compartilhado:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (esse evento é registrado somente quando o recurso compartilhado é um site)
    
   - Quando o usuário de destino aceita o convite de compartilhamento enviado a eles (clicando no link no convite), SharePoint registra um evento **SharingInvitationAccepted** e atribui ao usuário de destino permissões para acessar o recurso. Se o usuário de destino for enviado um link anônimo, o evento **AnonymousLinkUsed** será registrado depois que o usuário de destino usar o link para acessar o recurso. Para links seguros, um **evento FileAccessed** é registrado quando um usuário externo usa o link para acessar o recurso.

Informações adicionais sobre o usuário de destino também são registradas, como a identidade do usuário a que o convite está e o usuário que aceita o convite. Em alguns casos, esses usuários (ou endereços de email) podem ser diferentes. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Como identificar recursos compartilhados com usuários externos

Um requisito comum para administradores é criar uma lista de todos os recursos que foram compartilhados com usuários fora da organização. Usando a auditoria de compartilhamento Office 365, os administradores podem gerar essa lista. Veja como.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Etapa 1: Pesquisar eventos de compartilhamento e exportar os resultados para um arquivo CSV

A primeira etapa é pesquisar o log de auditoria para eventos de compartilhamento. Para obter mais informações (incluindo as permissões necessárias) sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md)
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. No painel esquerdo do Centro de Conformidade e Segurança, clique em **Pesquisar**  > **Pesquisa de log de auditoria**.
    
    É exibida a página **Pesquisa de log de auditoria**. 
    
4. Em **Atividades**, clique **em Atividades de compartilhamento e de** solicitação de acesso para pesquisar eventos relacionados ao compartilhamento. 
    
    ![Em Atividades, selecione Atividades de compartilhamento e solicitação de acesso](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selecione um intervalo de data e hora para encontrar os eventos de compartilhamento que ocorreram nesse período. 
    
6. Clique **em Pesquisar** para executar a pesquisa. 
    
7. Quando a pesquisa terminar de executar e os resultados são exibidos, clique em **Exportar resultados** Baixar todos \> **os resultados**.
    
    Depois de selecionar a opção de exportação, uma mensagem na parte inferior da janela solicita que você abra ou salve o arquivo CSV.
    
8. Clique **em Salvar** Salvar \> **como** e salve o arquivo CSV em uma pasta em seu computador local. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Etapa 2: Usar o Editor do PowerQuery para formatar o log de auditoria exportado

A próxima etapa é usar o recurso de transformação JSON no Editor de Consulta do Power em Excel para dividir cada propriedade na coluna **AuditData** (que consiste em um objeto JSON de várias propriedades) em sua própria coluna. Isso permite filtrar colunas para exibir registros relacionados ao compartilhamento

Para obter instruções passo a passo, consulte "Etapa 2: formatar o registro de auditoria exportado usando o Power Query Editor" em [Exportar, configurar e visualizar registros de registro de auditoria](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Etapa 3: filtrar o arquivo CSV para recursos compartilhados com usuários externos

A próxima etapa é filtrar o CSV para os diferentes eventos relacionados ao compartilhamento descritos anteriormente na seção SharePoint [eventos de](#sharepoint-sharing-events) compartilhamento. Como alternativa, você pode filtrar a **coluna TargetUserOrGroupType** para exibir todos os registros onde o valor dessa propriedade é **Convidado**. 

Depois de seguir as instruções na etapa anterior para preparar o arquivo CSV usando o editor do PowerQuery, faça o seguinte:
    
1. Abra o Excel que você criou na Etapa 2. 

2. Na guia **Página** Base, clique em **Classificar & Filtro** e clique em **Filtrar**.
    
3. Na lista **suspenso Classificar & Filtro** na  coluna Operações, desempacole todas as seleções e selecione um ou mais dos seguintes eventos relacionados ao compartilhamento e clique em **Ok**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel exibe as linhas dos eventos selecionados.
    
4. Vá até a coluna chamada **TargetUserOrGroupType** e selecione-a. 
    
5. Na lista **suspenso Classificar & Filtro,** desempare todas as seleções e selecione **TargetUserOrGroupType:Guest** e clique em **Ok**.
    
    Agora Excel exibe as linhas para eventos de compartilhamento E onde o usuário de destino está fora da sua organização, porque os usuários externos são identificados pelo valor **TargetUserOrGroupType:Guest**. 
  
> [!TIP]
> Para os registros de auditoria exibidos, a coluna **ObjectId** identifica o recurso que foi compartilhado com o usuário de destino; por exemplo  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
