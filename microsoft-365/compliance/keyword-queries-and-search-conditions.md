---
title: Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre as propriedades de email e de arquivo que você pode pesquisar no centro de conformidade & segurança do Office 365.
ms.openlocfilehash: 89d3f0c25694f8f3c89fbc27ee857c58cc5937fd
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049799"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo

Este tópico descreve as propriedades de email e de documento que você pode pesquisar em itens de email no Exchange Online e documentos armazenados em sites do SharePoint e do OneDrive for Business usando o recurso de pesquisa de conteúdo no centro de conformidade do & de segurança. Você também pode usar os cmdlets ** \* -ComplianceSearch** no PowerShell do centro de conformidade e segurança & para pesquisar essas propriedades. O tópico também descreve:   
  
- Usando operadores de pesquisa booleanos, condições de pesquisa e outras técnicas de consulta de pesquisa para refinar os resultados da pesquisa.
    
- Pesquisando tipos de dados confidenciais e tipos de dados confidenciais personalizados no SharePoint e no OneDrive for Business.
    
- Pesquisando conteúdo de site compartilhado com usuários fora da sua organização
    
Para obter instruções passo a passo sobre como criar uma pesquisa de conteúdo, consulte [pesquisa de conteúdo no Office 365](content-search.md).

  
> [!NOTE]
> Pesquisa de conteúdo no centro de conformidade e segurança & e os cmdlets do ** \* ComplianceSearch** correspondentes no PowerShell do centro de conformidade e segurança & usam o idioma de consulta de palavra-chave (KQL). Para obter informações mais detalhadas, consulte [referência de sintaxe de linguagem de consulta de palavra-chave](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Propriedades de emails pesquisáveis

A tabela a seguir lista as propriedades de mensagens de email que podem ser pesquisadas usando o recurso de pesquisa de conteúdo no centro de conformidade & segurança ou usando o cmdlet **New-ComplianceSearch** ou **set-ComplianceSearch** . A tabela inclui um exemplo da sintaxe da _Propriedade: Value_ para cada propriedade e uma descrição dos resultados da pesquisa retornados pelos exemplos. Você pode digitar esses `property:value` pares na caixa palavras-chave para uma pesquisa de conteúdo. 

> [!NOTE]
> Ao pesquisar as propriedades de email, não é possível pesquisar itens em que a propriedade especificada está vazia ou em branco. Por exemplo, usando o par *Propriedade: Value* do **assunto: ""** para pesquisar mensagens de email com uma linha de assunto vazia retornará zero resultados. Isso também se aplica ao pesquisar Propriedades de site e de contato.
  
|**Propriedade**|**Descrição da propriedade**|**Exemplos**|**Resultados de pesquisa retornados pelos exemplos**|
|:-----|:-----|:-----|:-----|
|Attachmentnames|Os nomes dos arquivos anexados a uma mensagem de email.|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*` <br/> attachmentnames:.pptx|Mensagens que têm um arquivo anexado chamado relatórioanual.ppt. No segundo exemplo, o uso do caractere curinga retorna mensagens com a palavra "anual" no nome de arquivo de um anexo. O terceiro exemplo retorna todos os anexos com a extensão de arquivo PPTX.|
|Cco|O campo Cco de uma mensagem de email. <sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|Todos os exemplos retornam mensagens com Brenda Fernandes incluída no campo Cco.|
|Categoria| As categorias a serem pesquisadas. As categorias podem ser definidas por usuários usando o Outlook ou o Outlook na Web (anteriormente conhecido como Outlook Web App). Os valores possíveis são:  <br/><br/>  azuis  <br/>  natureza  <br/>  laranja  <br/>  roxa  <br/>  vermelha  <br/>  amarelo|`category:"Red Category"`|Mensagens que foram atribuídas à categoria vermelho nas caixas de correio de origem. |
|Cc|O campo CC de uma mensagem de email. <sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|Em ambos os exemplos, as mensagens com Pilar Fernandes especificadas no campo CC.|
|FolderId|A ID da pasta (GUID) de uma pasta de caixa de correio específica. Se você usar essa propriedade, certifique-se de Pesquisar a caixa de correio na qual a pasta especificada está localizada. Somente a pasta especificada será pesquisada. Todas as subpastas na pasta não serão pesquisadas. Para pesquisar subpastas, você precisa usar a propriedade FolderId da subpasta que você deseja pesquisar.  <br/> Para obter mais informações sobre como Pesquisar a propriedade FolderId e usar um script para obter as IDs de pasta para uma caixa de correio específica, confira [usar a pesquisa de conteúdo para coleções direcionadas](use-content-search-for-targeted-collections.md).|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|O primeiro exemplo retorna todos os itens na pasta de caixa de correio especificada. O segundo exemplo retorna todos os itens na pasta de caixa de correio especificada que foram enviados ou recebidos pelo garthf@contoso.com.|
|From|O remetente de uma mensagem de email. <sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|Mensagens enviadas pelo usuário especificado ou enviadas de um domínio especificado.|
|HasAttachment|Indica se uma mensagem tem um anexo. Use os valores **true** ou **false**.|`from:pilar@contoso.com AND hasattachment:true`|Mensagens enviadas pelo usuário especificado com anexos.|
|Importance|The importance of an email message, which a sender can specify when sending a message. By default, messages are sent with normal importance, unless the sender sets the importance as **high** or **low**.|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|Mensagens marcadas como alta prioridade, prioridade média ou baixa prioridade.|
|IsRead|Indica se as mensagens foram lidas. Use os valores **true** ou **false**.|`isread:true`  <br/> `isread:false`|O primeiro exemplo retorna mensagens com a propriedade IsRead definida como **true**. O segundo exemplo retorna mensagens com a propriedade IsRead definida como **false**.|
|ItemClass|Use esta propriedade para Pesquisar tipos de dados específicos de terceiros que sua organização importou para o Office 365. Use a seguinte sintaxe para esta propriedade:`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|O primeiro exemplo retorna itens do Facebook que contenham a palavra "contoso" na propriedade Subject. O segundo exemplo retorna os itens do Twitter que foram postados por Ana Beebe e que contêm a frase de palavra-chave "Northwind Traders".  <br/> Para obter uma lista completa de valores a serem usados para tipos de dados de terceiros para a propriedade ItemProperty, confira [usar a pesquisa de conteúdo para pesquisar dados de terceiros que foram importados para o Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).|
|Tipo| O tipo de mensagem de email a ser pesquisada. Valores possíveis:  <br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  fax  <br/>  respectiva  <br/>  diários  <br/>  treinamento  <br/>  microsoftteams (retorna itens de chats, reuniões e chamadas no Microsoft Teams)  <br/>  notes  <br/>  postagens  <br/>  rssfeeds  <br/>  tarefas  <br/>  postal|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|O primeiro exemplo retorna mensagens de email que atendem aos critérios de pesquisa. O segundo exemplo retorna mensagens de email, conversas de mensagens instantâneas (incluindo conversas e bate-papos do Skype for Business no Microsoft Teams) e mensagens de voz que atendem aos critérios de pesquisa. O terceiro exemplo retorna itens que foram importados para caixas de correio no Microsoft 365 de fontes de dados de terceiros, como Twitter, Facebook e Cisco Jabber, que atendem aos critérios de pesquisa. Para obter mais informações, consulte [arquivamento de dados de terceiros no Office 365](https://www.microsoft.com/?ref=go).|
|Participante|Todos os campos de pessoas em uma mensagem de email. Esses campos são de, para, CC e Cco.<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|Messages sent by or sent to garthf@contoso.com. The second example returns all messages sent by or sent to a user in the contoso.com domain.|
|Received|A data em que uma mensagem de email foi recebida pelo destinatário.|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|Mensagens recebidas na 15 de abril de 2016. O segundo exemplo retorna todas as mensagens recebidas entre 1º de janeiro de 2016 e 31 de março de 2016.|
|Destinatários|Todos os campos de destinatários em uma mensagem de email. Esses campos são para, CC e Cco.<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|Messages sent to garthf@contoso.com. The second example returns messages sent to any recipient in the contoso.com domain.|
|Sent|A data em que uma mensagem de email foi enviada pelo remetente.|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|Mensagens que foram enviadas na data especificada ou dentro do intervalo de datas especificado.|
|Size|O tamanho de um item, em bytes.|`size>26214400`  <br/> `size:1..1048567`|Mensagens maiores do que 25?? MB. O segundo exemplo retorna mensagens de 1 a 1.048.567 bytes (1 MB) de tamanho.|
|Subject|O texto na linha de assunto de uma mensagem de email.  <br/> **Observação:** Quando você usa a propriedade Subject em uma consulta, a pesquisa retorna todas as mensagens nas quais a linha de assunto contém o texto que você está pesquisando. Em outras palavras, a consulta não retorna apenas as mensagens que têm uma correspondência exata. Por exemplo, se você procurar `subject:"Quarterly Financials"` , seus resultados incluirão mensagens com o assunto "Finanças Trimestralmente 2018".|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|Mensagens que contenham a frase "Finanças trimestrais" em qualquer lugar do texto da linha de assunto. O segundo exemplo retorna todas as mensagens que contêm a palavra northwind na linha de assunto.|
|To|O campo para de uma mensagem de email. <sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|Todos os exemplos retornam mensagens em que Clara Barbosa é especificada na linha Para:.|
|||||
   
> [!NOTE]
> <sup>1</sup> para o valor de uma propriedade de destinatário, você pode usar o endereço de email (também chamado de UPN ou *nome principal de usuário* ), nome de exibição ou alias para especificar um usuário. Por exemplo, você pode usar clarab@contoso.com, clarab ou "Clara Barbosa" para especificar o usuário Clara Barbosa.<br/><br/>Ao pesquisar qualquer uma das propriedades de destinatário (de, para, CC, Cco, participantes e destinatários), o Microsoft 365 tenta expandir a identidade de cada usuário procurando-o no Azure Active Directory.  Se o usuário for localizado no Azure Active Directory, a consulta será expandida para incluir o endereço de email do usuário (ou UPN), o alias, o nome para exibição e LegacyExchangeDN.<br/><br/>Por exemplo, uma consulta como `participants:ronnie@contoso.com` expande para `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` .<br/><br/>Para impedir a expansão do destinatário, você pode adicionar um caractere curinga (asterisco) ao final do endereço de email na consulta de pesquisa; por exemplo, `participants:ronnie@contoso.com*` .

## <a name="searchable-site-properties"></a>Propriedades de sites pesquisáveis

A tabela a seguir lista algumas das propriedades do SharePoint e do OneDrive for Business que podem ser pesquisadas usando o recurso de pesquisa de conteúdo no centro de conformidade de & de segurança ou usando o cmdlet **New-ComplianceSearch** ou **set-ComplianceSearch** . A tabela inclui um exemplo da sintaxe da _Propriedade: Value_ para cada propriedade e uma descrição dos resultados da pesquisa retornados pelos exemplos. 
  
Para obter uma lista completa das propriedades do SharePoint que podem ser pesquisadas, confira [visão geral das propriedades rastreadas e gerenciadas no SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). As propriedades marcadas com um **Sim** na coluna **consultável** podem ser pesquisadas. 
  
|**Propriedade**|**Descrição da propriedade**|**Exemplo**|**Resultados de pesquisa retornados pelos exemplos**|
|:-----|:-----|:-----|:-----|
|Autor|O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário cria um documento e o email para alguém que o carrega para o SharePoint, o documento ainda manterá o autor original. Certifique-se de usar o nome de exibição do usuário para esta propriedade.|`author:"Garth Fort"`|Todos os documentos criados por Paulo Araújo.|
|ContentType|O tipo de conteúdo do SharePoint de um item, como item, documento ou vídeo.|`contenttype:document`|Todos os documentos seriam ser retornados.|
|Criado em|A data em que um item foi criado.|`created>=06/01/2016`|Todos os itens criados em ou após 1º de junho de 2016.|
|CreatedBy|A pessoa que criou ou carregou um item. Certifique-se de usar o nome de exibição do usuário para esta propriedade.|`createdby:"Garth Fort"`|Todos os itens criados ou carregados por Paulo Araújo.|
|DetectedLanguage|O idioma de um item.|`detectedlanguage:english`|Todos os itens em inglês.|
|DocumentLink|O caminho (URL) de uma pasta específica em um site do SharePoint ou do OneDrive for Business. Se você usar essa propriedade, certifique-se de Pesquisar o site no qual a pasta especificada está localizada.  <br/> Para retornar itens localizados em subpastas da pasta que você especificou para a propriedade documentlink, você precisa adicionar/ \* à URL da pasta especificada; por exemplo,`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Para obter mais informações sobre como Pesquisar a propriedade documentlink e usar um script para obter as URLs do documentlink para pastas em um site específico, consulte [usar a pesquisa de conteúdo para coleções direcionadas](use-content-search-for-targeted-collections.md).|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|O primeiro exemplo retorna todos os itens na pasta especificada do OneDrive for Business. O segundo exemplo retorna documentos na pasta de site especificada (e todas as subpastas) que contenham a palavra "confidencial" no nome do arquivo.|
|ExtensãoDeArquivo|A extensão de um arquivo; por exemplo, docx, One, pptx ou xlsx.|`fileextension:xlsx`|Todos os arquivos do Excel (Excel 2007 e posterior)|
|FileName|O nome de um arquivo.|`filename:"marketing plan"`  <br/> `filename:estimate`|The first example returns files with the exact phrase "marketing plan" in the title. The second example returns files with the word "estimate" in the file name.|
|LastModifiedTime|A data em que um item foi alterado pela última vez.|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|O primeiro exemplo retorna itens que foram alterados em ou após 1 de maio de 2016. O segundo exemplo retorna os itens que foram alterados entre 1º de maio de 2016 e 1 de junho de 2016.|
|ModifiedBy|A pessoa que alterou um item pela última vez. Certifique-se de usar o nome de exibição do usuário para esta propriedade.|`modifiedby:"Garth Fort"`|Todos os itens que foram alterados pela última vez por Paulo Araújo.|
|Path|O caminho (URL) de um site específico em um site do SharePoint ou do OneDrive for Business.  <br/> Para retornar itens localizados em pastas no site que você especificar para a propriedade Path, você precisa adicionar/ \* à URL do site especificado; por exemplo,`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **Observação:** O uso da `Path` propriedade para pesquisar os locais do onedrive não retornará arquivos de mídia, como arquivos. png,. TIFF ou. wav, nos resultados da pesquisa. Use uma propriedade de site diferente em sua consulta de pesquisa para pesquisar arquivos de mídia em pastas do OneDrive. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|O primeiro exemplo retorna todos os itens no site do OneDrive for Business especificado. O segundo exemplo retorna documentos no site especificado (e pastas no site) que contenham a palavra "confidencial" no nome do arquivo.|
|SharedWithUsersOWSUser|Documentos que foram compartilhados com o usuário especificado e exibidos na página **compartilhado comigo** no site do onedrive for Business do usuário. Estes são documentos que foram explicitamente compartilhados com o usuário especificado por outras pessoas na sua organização. Quando você exporta documentos que correspondem a uma consulta de pesquisa que usa a propriedade SharedWithUsersOWSUser, os documentos são exportados do local de conteúdo original da pessoa que compartilhou o documento com o usuário especificado. Para obter mais informações, consulte [pesquisando o conteúdo do site compartilhado em sua organização](#searching-for-site-content-shared-within-your-organization).|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|Ambos os exemplos retornam todos os documentos internos que foram explicitamente compartilhados com o Henrique Fort e que aparecem na página **compartilhado comigo** na conta do onedrive for Business do Henrique Fort.|
|Site|A URL de um site ou grupo de sites em sua organização.|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|O primeiro exemplo retorna itens dos sites do OneDrive for Business para todos os usuários da organização. O segundo exemplo retorna itens de todos os sites de equipe.|
|Size|O tamanho de um item, em bytes.|`size>=1`  <br/> `size:1..10000`|The first example returns items larger than 1 byte. The second example returns items from 1 through 10,000 bytes in size.|
|Title|O título do documento. A propriedade Title é metadados especificados em documentos do Microsoft Office. É diferente do nome de arquivo do documento.|`title:"communication plan"`|Qualquer documento que contém a frase "plano de comunicação" na propriedade de metadados Title de um documento do Office.|
|||||
   
## <a name="searchable-contact-properties"></a>Propriedades de contato pesquisáveis

A tabela a seguir lista as propriedades de contato que estão indexadas e que você pode pesquisar usando a pesquisa de conteúdo. Essas são as propriedades disponíveis para que os usuários configurem os contatos (também chamados de contatos pessoais) localizados no catálogo de endereços pessoal da caixa de correio de um usuário. Para pesquisar contatos, você pode selecionar as caixas de correio a serem pesquisadas e, em seguida, usar uma ou mais propriedades de contato na consulta de palavra-chave.
  
> [!TIP]
> Para pesquisar valores que contenham espaços ou caracteres especiais, use aspas duplas ("") para conter a frase; por exemplo, `businessaddress:"123 Main Street"` . 
  
|**Propriedade**|**Descrição da propriedade**|
|:-----|:-----|
|BusinessAddress|O endereço na propriedade **endereço comercial** . A propriedade também é chamada de endereço **comercial** na página de propriedades do contato.|
|BusinessPhone|O número de telefone em qualquer uma das propriedades do número de **telefone comercial** .|
|CompanyName|O nome na propriedade **Company** .|
|Department|O nome na propriedade **Department** .|
|DisplayName|O nome de exibição do contato. Este é o nome na propriedade **nome completo** do contato.|
|EmailAddress|O endereço de qualquer propriedade de endereço de email do contato. Os usuários podem adicionar vários endereços de email para um contato. O uso dessa propriedade retornaria contatos que correspondam a qualquer um dos endereços de email do contato.|
|FileAs|O **arquivo como** propriedade. Essa propriedade é usada para especificar como o contato está listado na lista de contatos do usuário. Por exemplo, um contato pode ser listado como *FirstName, LastName* ou *LastName, FirstName*.|
|GivenName|O nome na propriedade **First Name** .|
|HomeAddress|O endereço em qualquer uma das propriedades de endereço **residencial** .|
|HomePhone|O número de telefone em qualquer uma das propriedades do número de telefone **residencial** .|
|IMAddress|A propriedade de endereço de mensagens instantâneas, que normalmente é um endereço de email usado para mensagens instantâneas.|
|MiddleName|O nome na Propriedade do nome do **meio** .|
|MobilePhone|O número de telefone na Propriedade do número de telefone **celular** .|
|Nickname|O nome na propriedade **nickname** .|
|OfficeLocation|O valor na propriedade local do **Office** ou do **Office** .|
|OtherAddress|O valor da propriedade **outro** endereço.|
|Surname|O nome na propriedade **Last** Name.|
|Title|O título na propriedade **cargo** .|
|||||

## <a name="searchable-sensitive-data-types"></a>Tipos de dados confidenciais pesquisáveis

Você pode usar o recurso de pesquisa de conteúdo no centro de conformidade e segurança para pesquisar dados confidenciais, como números de cartão de crédito ou números de seguridade social, que são armazenados em documentos nos sites do SharePoint e do OneDrive for Business. Você pode fazer isso usando a `SensitiveType` propriedade e o nome de um tipo de informação confidencial em uma consulta de palavra-chave. Por exemplo, a consulta `SensitiveType:"Credit Card Number"` retorna documentos que contenham um número de cartão de crédito. A consulta `SensitiveType:"U.S. Social Security Number (SSN)"` retorna documentos que contenham um número de segurança social dos EUA. Para ver uma lista dos tipos de dados confidenciais que você pode pesquisar, vá para **classificações** de \> **tipos de informações confidenciais** no centro de conformidade de & de segurança. Ou você pode usar o cmdlet **Get-DlpSensitiveInformationType** no PowerShell do centro de conformidade e segurança & para exibir uma lista de tipos de informações confidenciais. 
  
Você também pode usar a `SensitiveType` propriedade para pesquisar o nome de um tipo de informação confidencial personalizado que você (ou outro administrador) criou para sua organização. Você pode usar a coluna **Publisher** na página **tipos de informações confidenciais** no centro de conformidade & segurança (ou na propriedade **Publisher** no PowerShell) para diferenciar entre os tipos de informações confidenciais internos e personalizados. Para obter mais informações, consulte [criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md).
  
Para obter mais informações sobre como criar consultas usando a `SensitiveType` propriedade, consulte [formulário uma consulta para encontrar dados confidenciais armazenados em sites](form-a-query-to-find-sensitive-data-stored-on-sites.md).

> [!NOTE]
> Você não pode usar tipos de dados confidenciais e a `SensitiveType` Propriedade Search para pesquisar dados confidenciais em caixas de correio do Exchange Online. No entanto, você pode usar políticas de DLP (prevenção contra perda de dados) para proteger dados confidenciais de email em trânsito. Para obter mais informações, consulte [visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md) e [pesquisa e localização de dados pessoais](search-for-and-find-personal-data.md).
  
## <a name="search-operators"></a>Operadores de pesquisa

Operadores de pesquisa booleanos, como **e**, **ou**, e **não**, ajudam você a definir pesquisas mais precisas, incluindo ou excluindo palavras específicas na consulta de pesquisa. Outras técnicas, como o uso de operadores de propriedade (como \> = ou..), aspas, parênteses e curingas, ajudam a refinar uma consulta de pesquisa. A tabela a seguir lista os operadores que você pode usar para restringir ou ampliar os resultados de pesquisa. 
  
|**Operator**|**Uso**|**Descrição**|
|:-----|:-----|:-----|
|E|palavra-chave1 AND palavra-chave2|Retorna itens que incluem todas as palavras-chave ou expressões especificadas `property:value` . Por exemplo, `from:"Ann Beebe" AND subject:northwind` retorna todas as mensagens enviadas por Ana Beebe que continham a palavra Northwind na linha de assunto. <sup>duas</sup>|
|+|palavra + palavra-chave2 + keyword3|Retorna itens que contêm *um* `keyword2` ou `keyword3` *e* que também contêm `keyword1` .   Portanto, este exemplo é equivalente à consulta `(keyword2 OR keyword3) AND keyword1` .  <br/> A consulta `keyword1 + keyword2` (com um espaço após o **+** símbolo) não é o mesmo que usar o operador **and** . Essa consulta seria equivalente a `"keyword1 + keyword2"` e retornar itens com a fase exata `"keyword1 + keyword2"` .|
|OU|palavra-chave1 OR palavra-chave2|Retorna itens que incluem uma ou mais palavras-chave ou `property:value` expressões especificadas. <sup>duas</sup>|
|NÃO|palavra-chave1 NOT palavra-chave2  <br/> NOT from:"Clara Barbosa"  <br/> Não tipo: im|Exclui os itens especificados por uma palavra-chave ou uma `property:value` expressão. No segundo exemplo exclui mensagens enviadas por Ana Beebe. O terceiro exemplo exclui conversas de mensagens instantâneas, como conversas do Skype for Business salvas na pasta caixa de correio de histórico de conversas. <sup>duas</sup>|
|-|palavra-palavra-chave2|O mesmo que o operador **NOT**. Portanto, essa consulta retorna itens que contenham `keyword1` e exclua itens que contêm `keyword2` .|
|NEAR|palavra-chave1 NEAR(n) palavra-chave2|Retorna itens com palavras que estão próximas umas das outras, em que n é igual ao número de palavras de distância. Por exemplo, `best NEAR(5) worst` retorna qualquer item em que a palavra "pior" está dentro de cinco palavras de "Best". Se nenhum número for especificado, a distância padrão será de oito palavras. <sup>duas</sup>|
|:|Propriedade: Value|Os dois-pontos (:) na `property:value` sintaxe especifica que o valor da propriedade que está sendo pesquisada contém o valor especificado. Por exemplo, `recipients:garthf@contoso.com` retorna qualquer mensagem enviada para garthf@contoso.com.|
|=|Propriedade = valor|O mesmo que o operador **:** .|
|\<|valor da propriedade \<|Indica que a propriedade que está sendo pesquisada é menor do que o valor especificado.  <sup>1</sup>|
|\>|valor da propriedade \>|Indica que a propriedade que está sendo pesquisada é maior do que o valor especificado. <sup>1</sup>|
|\<=|Propriedade \< = valor|Indica que a propriedade que está sendo pesquisada é menor ou igual a um valor específico. <sup>1</sup>|
|\>=|Propriedade \> = valor|Indica que a propriedade que está sendo pesquisada é maior ou igual a um valor específico. <sup>1</sup>|
|..|Propriedade: value1.. value2|Indica que a propriedade que está sendo pesquisada é maior ou igual a valor1 e menor ou igual a valor2. <sup>1</sup>|
|"  "|"valor justo"  <br/> assunto:"Finanças trimestrais"|Usar aspas duplas ("") para pesquisar uma frase exata ou termo em consultas de palavra-chave e de `property:value` pesquisa.|
|\*|tomografia\*  <br/> subject: Set\*|As pesquisas curinga de prefixo (onde o asterisco é colocado no final de uma palavra) correspondem a zero ou mais caracteres em palavras-chave ou `property:value` consultas. Por exemplo, `title:set*` retorna documentos que contenham a palavra set, setup e setting (e outras palavras que começam com "set") no título do documento.  <br/><br/> **Observação:** Você pode usar apenas pesquisas curinga de prefixo; por exemplo, **Cat \* ** ou **set \* **. Pesquisas de sufixo (** \* Cat** ), pesquisas de refixo (**c \* t**) e pesquisas de subcadeias (** \* Cat \* **) não são suportadas.|
|(  )| (justo OR grátis) AND (from:contoso.com)  <br/>  (IPO OR inicial) AND (ação OR títulos)  <br/>  (finanças trimestrais)|Os parênteses agrupam frases, `property:value` itens e palavras-chave booleanas. Por exemplo, `(quarterly financials)` retorna itens que contêm as palavras trimestrais e financeiras.|
|||||
   
> [!NOTE]
> <sup>1</sup> Use esse operador para propriedades que têm valores de data ou numéricos.<br/> <sup>2</sup> operadores de pesquisa booleanos devem estar em maiúsculas; por exemplo, **e**. Se você usar um operador em minúsculas, como **e**, ele será tratado como uma palavra-chave na consulta de pesquisa. 
  
## <a name="search-conditions"></a>Condições de pesquisa

Você pode adicionar condições a uma consulta de pesquisa para restringir uma pesquisa e retornar um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executada quando você inicia a pesquisa.
  
[Condições para propriedades comuns ](#conditions-for-common-properties)

[Condições para propriedades de email](#conditions-for-mail-properties)

[Condições para propriedades de documentos](#conditions-for-document-properties)

[Operadores usados com condições](#operators-used-with-conditions)

[Diretrizes para o uso de condições](#guidelines-for-using-conditions)

[Exemplos](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condições para propriedades comuns

Crie uma condição usando propriedades comuns ao pesquisar caixas de correio e sites na mesma pesquisa. A tabela a seguir lista as propriedades disponíveis a serem usadas ao adicionar uma condição.
  
|**Condição**|**Descrição**|
|:-----|:-----|
|Data|Para email, a data em que a mensagem foi recebida por um destinatário ou enviada pelo remetente. Para documentos, a data em que um documento foi modificado pela última vez.|
|Remetente/autor|Para email, a pessoa que enviou uma mensagem. Para documentos, a pessoa citada no campo autor de documentos do Office. Você pode digitar mais de um nome, separado por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador **OR**.|
|Tamanho (em bytes)|Para emails e documentos, o tamanho do item (em bytes).|
|Assunto/título|Para email, o texto na linha de assunto de uma mensagem. Para documentos, o título do documento. Como explicado anteriormente, a propriedade Title é Metadata especificado em documentos do Microsoft Office. Você pode digitar o nome de mais de um assunto/título, separados por vírgulas. Dois ou mais valores são logicamente conectadas pelo operador **OR**.|
|Rótulo de conformidade|Para emails e documentos, rótulos de retenção que foram atribuídos a mensagens e documentos automaticamente por políticas de rótulo ou rótulos de retenção que foram atribuídos manualmente pelos usuários. Os rótulos de retenção são usados para classificar emails e documentos para controle de informações e aplicar regras de retenção com base nas configurações definidas pelo rótulo. Você pode digitar parte do nome do rótulo de retenção e usar um caractere curinga ou digitar o nome completo do rótulo. Para obter mais informações, consulte [visão geral dos rótulos de retenção](labels.md).|
|||
  
### <a name="conditions-for-mail-properties"></a>Condições para propriedades de email

Crie uma condição usando as propriedades de email ao pesquisar caixas de correio ou pastas públicas. A tabela a seguir lista as propriedades de email que você pode usar para uma condição. Essas propriedades são um subconjunto das propriedades de email que foram descritas anteriormente. Essas descrições são repetidas para sua conveniência.
  
|**Condição**|**Descrição**|
|:-----|:-----|
|Tipo de mensagem| Tipo de mensagem para pesquisar. Essa propriedade é igual à propriedade de email Kind. Valores possíveis:  <br/><br/>  contacts  <br/>  docs  <br/>  email  <br/>  externaldata  <br/>  fax  <br/>  respectiva  <br/>  diários  <br/>  treinamento  <br/>  microsoftteams  <br/>  notes  <br/>  postagens  <br/>  rssfeeds  <br/>  tarefas  <br/>  postal|
|Participante|Todos os campos de pessoas em uma mensagem de email. Esses campos são de, para, CC e Cco.|
|Tipo|A propriedade da classe Message de um item de email. Esta é a mesma propriedade que a propriedade de email ItemProperty. Também é uma condição de vários valores. Portanto, para selecionar várias classes de mensagens, pressione a tecla **Ctrl** e clique duas ou mais classes de mensagens na lista suspensa que você deseja adicionar à condição. Cada classe de mensagem selecionada na lista será logicamente conectada pelo operador **or** na consulta de pesquisa correspondente.  <br/> Para obter uma lista das classes de mensagem (e sua ID de classe de mensagem correspondente) que são usadas pelo Exchange e que você pode selecionar na lista **classe de mensagens** , consulte [tipos de item e classes de mensagens](https://go.microsoft.com/fwlink/?linkid=848143).|
|Received|A data em que uma mensagem de email foi recebida pelo destinatário. Essa propriedade é igual à propriedade de email Received.|
|Destinatários|Todos os campos de destinatários em uma mensagem de email. Esses campos são para, CC e Cco.|
|Sender|O remetente de uma mensagem de email.|
|Sent|A data em que uma mensagem de email foi enviada pelo remetente. Essa propriedade é igual à propriedade de email Sent.|
|Subject|O texto na linha de assunto de uma mensagem de email.|
|To|O destinatário de uma mensagem de email no campo para.|
|||
  
### <a name="conditions-for-document-properties"></a>Condições para propriedades de documentos

Crie uma condição usando as propriedades do documento ao pesquisar documentos nos sites do SharePoint e do OneDrive for Business. A tabela a seguir lista as propriedades do documento que você pode usar para uma condição. Essas propriedades são um subconjunto das propriedades de site descritas anteriormente. Essas descrições são repetidas para sua conveniência.
  
|**Condição**|**Descrição**|
|:-----|:-----|
|Autor|O campo de autor de documentos do Office, que persiste se um documento é copiado. Por exemplo, se um usuário cria um documento e o email para alguém que o carrega para o SharePoint, o documento ainda manterá o autor original.|
|Title|O título do documento. A propriedade Title consiste em metadados que são especificados em documentos do Office. É diferente do nome de arquivo do documento.|
|Criado em|A data em que um documento foi criado.|
|Última modificação|A data em que um documento foi alterado pela última vez.|
|Tipo de arquivo|A extensão de um arquivo; por exemplo, docx, One, pptx ou xlsx. Essa propriedade é igual à propriedade de site FileExtension.|
|||
  
### <a name="operators-used-with-conditions"></a>Operadores usados com condições

When you add a condition, you can select an operator that is relevant to type of property for the condition. The following table describes the operators that are used with conditions and lists the equivalent that is used in the search query.
  
|**Operator**|**Equivalente de consulta**|**Descrição**|
|:-----|:-----|:-----|
|After|`property>date`|Used with date conditions. Returns items that were sent, received, or modified after the specified date.|
|Before|`property<date`|Used with date conditions. Returns items that were sent, received, or modified before the specified date.|
|Entre|`date..date`|Use com condições de data e tamanho. Quando usado com uma condição de data, retorna itens que foram enviados, recebidos ou modificados no intervalo de datas especificado. Quando usado com uma condição de tamanho, retorna itens cujo tamanho está dentro do intervalo especificado.|
|Contains any of|`(property:value) OR (property:value)`|Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que contêm qualquer parte de um ou mais valores da cadeia de caracteres especificada.|
|Doesn't contain any of|`-property:value`  <br/> `NOT property:value`|Usado com condições para propriedades que especificam um valor de cadeia de caracteres. Retorna itens que não contêm qualquer parte do valor da cadeia de caracteres especificada.|
|Doesn't equal any of|`-property=value`  <br/> `NOT property=value`|Used with conditions for properties that specify a string value. Returns items that don't contain the specific string.|
|Igual a|`size=value`|Retorna itens que são iguais ao tamanho especificado. <sup>1</sup>|
|Igual a qualquer|`(property=value) OR (property=value)`|Used with conditions for properties that specify a string value. Returns items that are an exact match of one or more specified string values.|
|Superior|`size>value`|Retorna itens em que a propriedade especificada é maior do que o valor especificado. <sup>1</sup>|
|Greater or equal|`size>=value`|Retorna itens em que a propriedade especificada é maior ou igual ao valor especificado. <sup>1</sup>|
|Menos|`size<value`|Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
|Less or equal|`size<=value`|Retorna itens que são maiores ou iguais ao valor específico. <sup>1</sup>|
|Not equal|`size<>value`|Retorna itens que não são iguais ao tamanho especificado. <sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> esse operador está disponível somente para condições que usam a propriedade Size. 
  
### <a name="guidelines-for-using-conditions"></a>Diretrizes para o uso de condições

Lembre-se do seguinte ao usar condições de pesquisa.
  
- Uma condição está logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador **AND**. Isso significa que os itens precisam atender à consulta de palavra-chave e à condição para serem incluídos nos resultados. É assim que as condições ajudam a restringir os resultados. 
    
- Se você adicionar duas ou mais condições exclusivas a uma consulta de pesquisa (condições que especificam propriedades diferentes), essas condições serão conectadas logicamente pelo operador **and** . Isso significa que apenas os itens que atenderem a todas as condições (além de qualquer consulta de palavra-chave) serão retornados. 
    
- Se você adicionar mais de uma condição à mesma propriedade, as condições serão logicamente conectadas pelo operador **OR**. Isso significa que os itens que atenderem à consulta de palavra-chave e a qualquer uma das condições serão retornados. Portanto, grupos das mesmas condições são conectados uns aos outros pelo operador **OR**, e conjuntos de condições exclusivas são conectados pelo operador **AND**. 
    
- Se você adicionar vários valores (separados por vírgulas ou pontos-e-vírgulas) a uma única condição, esses valores serão conectados pelo operador **or** . Isso significa que os itens serão retornados se contiverem qualquer um dos valores especificados para a propriedade na condição. 
    
- A consulta de pesquisa criada usando a caixa palavras-chave e condições é exibida na página de **pesquisa** , no painel de detalhes da pesquisa selecionada. Em uma consulta, tudo à direita da notação `(c:c)` indica condições que são adicionadas à consulta. 
    
- As condições apenas adicionam propriedades à consulta de pesquisa; elas não adicionam operadores. É por isso que a consulta exibida no painel de detalhes não mostra os operadores à direita da `(c:c)` notação. A KQL adiciona os operadores lógicos (de acordo com as regras explicadas anteriormente) ao executar a consulta. 
    
- Você pode usar o controle arrastar e soltar para reordenar a ordem das condições. Clique no controle para obter uma condição e movê-la para cima ou para baixo.
    
- Como explicado anteriormente, algumas propriedades de condição permitem digitar vários valores. Cada valor é logicamente conectado pelo operador **OR**. Isso faz com que a mesma lógica tenha várias instâncias da mesma condição, em que cada uma tem um único valor. As ilustrações a seguir mostram um exemplo de uma única condição com vários valores e um exemplo de várias condições (para a mesma propriedade) com um único valor. Os dois exemplos resultam na mesma consulta:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Uma mensagem deve atender a todas as condições da regra. Se você precisar combinar uma condição ou outra, use regras separadas para cada condição. Por exemplo, se quiser adicionar o mesmo aviso de isenção legal a mensagens com anexos e mensagens com conteúdo que corresponde a um padrão, crie uma regra para cada condição. Você pode facilmente copiar uma regra.](../media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Vários critérios de pesquisa para a mesma propriedade](../media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> If a condition accepts multiple values, we recommend that you use a single condition and specify multiple values (separated by commas or semi-colons). This helps ensure the query logic that's applied is what you intend. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Exemplos

Os exemplos a seguir mostram a versão baseada em GUI de uma consulta de pesquisa com condições, a sintaxe de consulta de pesquisa exibida no painel de detalhes da pesquisa selecionada (que também é retornada pelo cmdlet **Get-ComplianceSearch** ) e a lógica da consulta KQL correspondente. 
  
#### <a name="example-1"></a>Exemplo 1

Este exemplo retorna documentos em sites do SharePoint e do OneDrive for Business que contenham um número de cartão de crédito e foram modificados pela última vez antes de 1º de janeiro de 2016.
  
 **GUI**
  
![Primeiro exemplo de critérios de pesquisa](../media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Sintaxe de consulta de pesquisa**
  
 `SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2016-01-01)`
  
 **Lógica de consulta de pesquisa**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>Exemplo 2

This example returns email items or documents that contain the keyword "report", that were sent or created before April 1, 2105, and that contain the word "northwind" in the subject field of email messages or in the title property of documents. The query excludes Web pages that meet the other search criteria.
  
 **GUI**
  
![Segundo exemplo de critérios de pesquisa](../media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Sintaxe de consulta de pesquisa**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **Lógica de consulta de pesquisa**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Exemplo 3

Este exemplo retorna mensagens de email ou reuniões de calendário que foram enviadas entre 12/1/2016 e 11/30/2016 e que contêm palavras que começam com "Phone" ou "smartphone".
  
 **GUI**
  
![Terceiro exemplo de critérios de pesquisa](../media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Sintaxe de consulta de pesquisa**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Lógica de consulta de pesquisa**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="special-characters"></a>Caracteres especiais

Alguns caracteres especiais não estão incluídos no índice de pesquisa e, portanto, não podem ser pesquisados. Isso também inclui os caracteres especiais que representam operadores de pesquisa na consulta de pesquisa. Aqui está uma lista de caracteres especiais substituídos por um espaço em branco na consulta de pesquisa real ou causa um erro de pesquisa.

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>Pesquisar conteúdo de site compartilhado com usuários externos

Você também pode usar o recurso de pesquisa de conteúdo no centro de conformidade de & de segurança para pesquisar documentos armazenados em sites do SharePoint e do OneDrive for Business que foram compartilhados com pessoas de fora da sua organização. Isso pode ajudá-lo a identificar informações confidenciais ou proprietárias que estão sendo compartilhadas fora de sua organização. Você pode fazer isso usando a `ViewableByExternalUsers` propriedade em uma consulta de palavra-chave. Essa propriedade retorna documentos ou sites que foram compartilhados com usuários externos usando um dos seguintes métodos de compartilhamento: 
  
- Um convite de compartilhamento que exige que os usuários entrem em sua organização como um usuário autenticado.
    
- Um link de convidado anônimo, que permite que qualquer pessoa com esse link acesse o recurso sem precisar ser autenticado.
    
Aqui estão alguns exemplos:
  
- A consulta `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` retorna todos os itens que foram compartilhados com pessoas de fora da sua organização e contêm um número de cartão de crédito. 
    
- A consulta `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` retorna uma lista de documentos em todos os sites de equipe da organização que foram compartilhados com usuários externos. 
    
> [!TIP]
> Uma consulta de pesquisa como `ViewableByExternalUsers:true AND ContentType:document` pode retornar muitos arquivos. aspx nos resultados da pesquisa. Para eliminar esses (ou outros tipos de arquivos), você pode usar a `FileExtension` propriedade para excluir tipos de arquivo específicos; por exemplo `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx` . 
  
O que é considerado conteúdo que é compartilhado com pessoas de fora de sua organização? Documentos nos sites do SharePoint e do OneDrive for Business de sua organização que são compartilhados enviando um convite de compartilhamento ou que são compartilhados em locais públicos. Por exemplo, as seguintes atividades de usuário resultarem em conteúdo que pode ser exibido por usuários externos:
  
- Um usuário compartilha um arquivo ou uma pasta com uma pessoa de fora da organização.
    
- Um usuário cria e envia um link de um arquivo compartilhado a uma pessoa de fora da organização. O link permite que o usuário externo exiba (ou edite) o arquivo.
    
- Um usuário envia um convite de compartilhamento ou um link de convidado a uma pessoa de fora da organização para exibir (ou editar) um arquivo compartilhado.
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemas usando a propriedade ViewableByExternalUsers

Enquanto a `ViewableByExternalUsers` propriedade representa o status de um documento ou site compartilhado com usuários externos, há algumas advertências para o que essa propriedade faz e não reflete. Nos cenários a seguir, o valor da `ViewableByExternalUsers` propriedade não será atualizado e os resultados de uma consulta de pesquisa de conteúdo que usa essa propriedade podem ser imprecisos. 
  
- Alterações na política de compartilhamento, como desativar o compartilhamento externo para um site ou para a organização. A propriedade ainda mostrará documentos compartilhados anteriormente como sendo externamente acessíveis, mesmo que o acesso externo possa ter sido revogado.
    
- Alterações na associação de grupo, como adicionar ou remover usuários externos de grupos do Microsoft 365 ou grupos de segurança do Microsoft 365. A propriedade não será atualizada automaticamente para os itens aos quais o grupo tem acesso.
    
- Envio de convites de compartilhamento para usuários externos onde o destinatário não aceitou o convite e, portanto, ainda não tem acesso ao conteúdo.
    
Nesses cenários, a `ViewableByExternalUsers` propriedade não refletirá o status de compartilhamento atual até que o site ou biblioteca de documentos seja rerastreado e reindexado. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Pesquisando o conteúdo do site compartilhado em sua organização

Como explicado anteriormente, você pode usar a `SharedWithUsersOWSUser` propriedade para pesquisar documentos que foram compartilhados entre pessoas da sua organização. Quando uma pessoa compartilha um arquivo (ou pasta) com outro usuário dentro de sua organização, um link para o arquivo compartilhado aparece na página **compartilhado comigo** na conta do onedrive for Business da pessoa com quem o arquivo foi compartilhado. Por exemplo, para pesquisar os documentos que foram compartilhados com o Sara Davis, você pode usar a consulta `SharedWithUsersOWSUser:"sarad@contoso.com"` . Se você exportar os resultados da pesquisa, os documentos originais (localizados no local de conteúdo da pessoa que compartilhou os documentos com o Sara) serão baixados.
  
Os documentos devem ser compartilhados explicitamente com um usuário específico para serem retornados nos resultados da pesquisa ao usar a `SharedWithUsersOWSUser` propriedade. Por exemplo, quando uma pessoa compartilha um documento em sua conta do OneDrive, ela tem a opção de compartilhá-la com qualquer pessoa (dentro ou fora da organização), compartilhá-la somente com pessoas dentro da organização ou compartilhá-la com uma pessoa específica. Aqui está uma captura de tela da janela de **compartilhamento** no onedrive, que mostra as três opções de compartilhamento. 
  
![Somente os arquivos compartilhados com pessoas específicas serão retornados por uma consulta de pesquisa que usa a propriedade SharedWithUsersOWSUser](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Somente os documentos que são compartilhados usando a terceira opção (compartilhada com **pessoas específicas**) serão retornados por uma consulta de pesquisa que usa a `SharedWithUsersOWSUser` propriedade. 

## <a name="searching-for-skype-for-business-conversations"></a>Pesquisando conversas do Skype for Business

Você pode usar a consulta de palavra-chave a seguir para pesquisar especificamente o conteúdo nas conversas do Skype for Business:

```powershell
kind:im
```

A consulta de pesquisa anterior também retorna chats do Microsoft Teams. Para evitar isso, você pode restringir os resultados da pesquisa para incluir apenas conversas do Skype for Business usando a seguinte consulta de palavra-chave:

```powershell
kind:im AND subject:conversation
```

A consulta de palavra-chave anterior exclui chats no Microsoft Teams porque as conversas do Skype for Business são salvas como mensagens de email com uma linha de assunto que começa com a palavra "conversa".

Para pesquisar conversas do Skype for Business que ocorreram em um intervalo de datas específico, use a seguinte consulta de palavra-chave:

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>Dicas e truques de pesquisa

- Pesquisas de palavra-chave não diferenciam maiúsculas de minúsculas. Por exemplo, **gato** e **GATO** retornam os mesmos resultados. 

- Os operadores booleanos **e**, **ou**, **not**e **Near** devem estar em maiúsculas. 

- Um espaço entre duas palavras-chave ou duas `property:value` expressões é o mesmo que usar o **e**o. Por exemplo, `from:"Sara Davis" subject:reorganization` retorna todas as mensagens enviadas por Sara Davis que contenham a palavra reorganization na linha de assunto. 

- Use a sintaxe que corresponde ao `property:value` formato. Os valores não diferenciam maiúsculas de minúsculas e não podem ter um espaço após o operador. Se houver um espaço, seu valor pretendido será uma pesquisa de texto completo. Por exemplo `to: pilarp` , pesquisa "pilarp" como uma palavra-chave, em vez de mensagens que foram enviadas para o pilarp. 

- When searching a recipient property, such as To, From, Cc, or Recipients, you can use an SMTP address, alias, or display name to denote a recipient. For example, you can use pilarp@contoso.com, pilarp, or "Pilar Pinilla".

- Você pode usar apenas pesquisas curinga de prefixo; por exemplo, **Cat \* ** ou **set \* **. Pesquisas de sufixo (** \* Cat**), pesquisas de refixo (**c \* t**) e pesquisas de subcadeias (** \* Cat \* **) não são suportadas.

- Ao pesquisar uma propriedade, use aspas duplas ("") se o valor de pesquisa for composto por várias palavras. Por exemplo `subject:budget Q1` , retorna mensagens que contenham **orçamento** na linha de assunto e que contenham **Q1** em qualquer lugar na mensagem ou em qualquer uma das propriedades da mensagem. Usando `subject:"budget Q1"` retorna todas as mensagens que contêm o **orçamento T1** em qualquer lugar na linha de assunto.

- Para excluir o conteúdo marcado com determinado valor de propriedade dos resultados de pesquisa, coloque um sinal de subtração (-) antes do nome da propriedade. Por exemplo, `-from:"Sara Davis"` exclui todas as mensagens enviadas por Sara Davis.

- Você pode exportar itens com base no tipo de mensagem. Por exemplo, para exportar conversas do Skype e chats no Microsoft Teams, use a sintaxe `kind:im` . Para retornar apenas mensagens de email, você usaria o `kind:email` . Para retornar chats, reuniões e chamadas no Microsoft Teams, use o `kind:microsoftteams` .
