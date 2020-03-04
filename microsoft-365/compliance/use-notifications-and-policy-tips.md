---
title: Enviar notificações por email e mostrar dicas para políticas de DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Uma dica de política é uma notificação ou um aviso que aparece quando alguém está trabalhando com conteúdo que está em conflito com uma política de DLP. Você pode usar notificações por email e dicas de política para aumentar a conscientização e ajudar a ensinar as pessoas sobre as políticas da sua organização. Você também pode conceder às pessoas a opção de substituir a política, para que elas não sejam bloqueadas se tiverem uma necessidade comercial válida ou se a política estiver detectando um falso positivo. '
ms.openlocfilehash: adf9d41fd528b2146ae3b3ee6f61390d61deaabe
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409576"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Enviar notificações por email e mostrar dicas para políticas de DLP

Você pode usar uma política de prevenção contra perda de dados (DLP) para identificar, monitorar e proteger informações confidenciais no Office 365. Você deseja que as pessoas em sua organização que trabalhem com essas informações confidenciais permaneçam em conformidade com suas políticas de DLP, mas não convém bloqueá-las desnecessariamente da realização de seus trabalhos. É aí que as notificações por email e as dicas de política podem ajudar.
  
![Barra de mensagem mostra a dica de política no Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Uma dica de política é uma notificação ou um aviso que aparece quando alguém está trabalhando com conteúdo que está em conflito com uma política de DLP — por exemplo, conteúdo como uma pasta de trabalho do Excel em um site do OneDrive for Business que contém informações de identificação pessoal (PII) e é compartilhado com um usuário externo.
  
Você pode usar notificações por email e dicas de política para aumentar a conscientização e ajudar a ensinar as pessoas sobre as políticas da sua organização. Você também pode conceder às pessoas a opção de substituir a política, para que elas não sejam bloqueadas se tiverem uma necessidade comercial válida ou se a política estiver detectando um falso positivo.
  
No centro de conformidade de &amp; segurança do Office 365, ao criar uma política de DLP, você pode configurar as notificações de usuário para:
  
- Envie uma notificação por email para as pessoas que você escolher que descrevem o problema.
    
- Exibir uma dica de política para o conteúdo que está em conflito com a política de DLP:
    
  - Para email no Outlook na Web e no Outlook 2013 e posterior, a dica de política aparece na parte superior de uma mensagem acima dos destinatários enquanto a mensagem está sendo redigida.
    
  - Para documentos em uma conta do OneDrive for Business ou site do SharePoint Online, a dica de política é indicada por um ícone de aviso que aparece no item. Para exibir mais informações, você pode selecionar um item e, em **** ![seguida, escolher o](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) ícone painel de informações de informações no canto superior direito da página para abrir o painel de detalhes. 
    
  - Para documentos do Excel, PowerPoint e Word que são armazenados em um site do onedrive for Business ou site do SharePoint Online incluído na política de DLP, a dica de política é exibida na barra de mensagens e no modo de exibição Backstage ( \> **informações**do menu de **arquivo** ).
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>Adicionar notificações de usuário a uma política de DLP

Ao criar uma política de DLP, você pode habilitar as **notificações do usuário**. Quando habilitada, o Microsoft 365 envia notificações por email e dicas de política. Você pode personalizar quem os emails de notificação são enviados para o, o texto de email e o texto de dica de política.
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante. Agora você está no centro de conformidade com &amp; segurança do Office 365.
    
3. Na navegação \> à &amp; esquerda centro \> de conformidade de segurança \> **política** \> de **prevenção contra perda de dados** **+ criar uma política**.
    
    ![Botão criar uma política](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Escolha o modelo de política de DLP que protege os tipos de informações confidenciais que \> você precisa **seguir**.
    
    Para começar com um modelo vazio **, escolha** \> **política** \> personalizada personalizada **próxima**.
    
5. Nomeie a política \> **em seguida**.
    
6. Para escolher os locais que você deseja que a política de DLP proteja, siga um destes procedimentos:
    
  - Escolha **todos os locais no Office 365** \> **em seguida**.
    
  - Escolha **deixe-me escolher locais** \> específicos **em seguida**.
    
    Para incluir ou excluir um local inteiro, como todos os emails do Exchange ou todas as contas do OneDrive, altere ou desative o **status** desse local. 
    
    Para incluir apenas sites específicos do SharePoint ou contas do OneDrive, altere o **status** para ativado e clique nos links em **incluir** para escolher sites ou contas específicos. 
    
7. Escolha **usar configurações** \> avançadas **próximo**.
    
8. Escolha **+ nova regra**.
    
9. No editor de regras, em **notificações do usuário**, altere o status para.
    
    ![Seção notificações de usuário do editor de regras](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> As políticas de DLP aplicam-se a todos os documentos que correspondem à política, independentemente de esses documentos serem novos ou existentes. No entanto, uma notificação de email só é gerada quando o novo conteúdo corresponde a uma política de DLP existente. O conteúdo existente é protegido, mas não gerará uma notificação de usuário por email.
  
## <a name="options-for-configuring-email-notifications"></a>Opções para a configuração de notificações por email

Para cada regra de uma política de DLP, você pode:
  
- Enviar a notificação para as pessoas que você escolher. Essas pessoas podem incluir o proprietário do conteúdo, a pessoa que modificou o conteúdo pela última vez, o proprietário do site em que o conteúdo está armazenado ou um usuário específico.
    
- Personalizar o texto que está incluído na notificação usando HTML ou tokens. Confira a seção abaixo para mais informações.
    
> [!NOTE]
>  As notificações por email podem ser enviadas somente para destinatários individuais, não grupos ou listas de distribuição. Apenas o novo conteúdo disparará uma notificação por email. A edição do conteúdo existente disparará dicas de política, mas não uma notificação por email. 
  
![Opções de notificação por email](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>Notificação de email padrão

As notificações têm uma linha de assunto que começa com a ação executada, como "notificação", "mensagem bloqueada" para email ou "acesso bloqueado" para documentos. Se a notificação for sobre um documento, o corpo da mensagem de notificação inclui um link que o leva para o site em que o documento está armazenado e abre a dica de política para o documento, onde você pode resolver problemas (consulte a seção abaixo sobre dicas de política). Se a notificação é sobre uma mensagem, a notificação inclui como um anexo a mensagem que corresponde a uma política de DLP.
  
![Mensagem de notificação](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
Por padrão, as notificações exibem um texto semelhante ao seguinte para um item em um site. O texto de notificação é configurado separadamente para cada regra, para que o texto exibido seja diferente dependendo da regra que for correspondida.

|**Se a regra de política de DLP fizer isso...**|**Em seguida, a notificação padrão para documentos do SharePoint ou do OneDrive for Business diz isso...**|**Em seguida, a notificação padrão para mensagens do Outlook diz isso...**|
|:-----|:-----|:-----|
|Envia uma notificação, mas não permite substituição  <br/> |Este item está em conflito com uma política de sua organização.  <br/> |Sua mensagem de email está em conflito com uma política da sua organização.  <br/> |
|Bloqueia o acesso, envia uma notificação e permite a substituição  <br/> |Este item está em conflito com uma política de sua organização. Se você não resolver esse conflito, o acesso a esse arquivo poderá ser bloqueado.  <br/> |Sua mensagem de email está em conflito com uma política da sua organização. A mensagem não foi entregue a todos os destinatários.  <br/> |
|Bloqueia o acesso e envia uma notificação  <br/> |Este item está em conflito com uma política de sua organização. O acesso a este item está bloqueado para todos, exceto seu proprietário, o último modificador e o administrador de conjunto de site principal.  <br/> |Sua mensagem de email está em conflito com uma política da sua organização. A mensagem não foi entregue a todos os destinatários.  <br/> |
   
### <a name="custom-email-notification"></a>Notificação de email personalizada

Você pode criar uma notificação de email personalizada em vez de enviar a notificação de email padrão aos usuários finais ou administradores. A notificação de email personalizada oferece suporte a HTML e tem um limite de 5.000 caracteres. Você pode usar HTML para incluir imagens, formatação e outras marcações na notificação.
  
Você também pode usar os tokens a seguir para ajudar a personalizar a notificação por email. Esses tokens são variáveis que são substituídas por informações específicas na notificação que é enviada.

|**Token**|**Descrição**|
|:-----|:-----|
|%% AppliedActions%%  <br/> |As ações aplicadas ao conteúdo.  <br/> |
|%% ContentURL%%  <br/> |A URL do documento no site do SharePoint Online ou do OneDrive for Business.  <br/> |
|%%MatchedConditions%%  <br/> |As condições que foram atendidas pelo conteúdo. Use este token para informar pessoas de possíveis problemas com o conteúdo.  <br/> |
   
![Mensagem de notificação mostrando onde os tokens aparecem](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>Opções para configurar dicas de política

Para cada regra de uma política de DLP, você pode configurar as dicas de política para:
  
- Simplesmente notificar a pessoa de que o conteúdo está em conflito com uma política de DLP, para que ela possa executar ações para resolver o conflito. Você pode usar o texto padrão (consulte as tabelas abaixo) ou inserir texto personalizado sobre as políticas específicas da sua organização.
    
- Permita que a pessoa substitua a política de DLP. Opcionalmente, você pode:
    
  - Exigir que a pessoa insira uma justificativa comercial para substituir a política. Essas informações são registradas e você pode exibi-las nos relatórios DLP na seção **relatórios** do centro de &amp; conformidade de segurança. 
    
  - Permitir que a pessoa relate falsos positivos e substitua a política de DLP. Essas informações também são registradas em log para fins de relatório, para que você possa usar falsos positivos para ajustar suas regras.
    
![Opções de dica de política](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
Por exemplo, você pode ter uma política de DLP aplicada a sites do OneDrive for Business que detecta informações de identificação pessoal (PII) e esta política tem três regras:
  
1. Primeira regra: Se menos de cinco instâncias dessas informações confidenciais forem detectadas em um documento e o documento for compartilhado com pessoas de dentro da organização, a ação **Enviar uma notificação** exibe uma dica de política. Para obter dicas de política, nenhuma opção de substituição é necessária porque essa regra está simplesmente notificando as pessoas e não bloqueando o acesso. 
    
2. Segunda regra: Se mais do que cinco instâncias dessas informações confidenciais forem detectadas em um documento e o documento for compartilhado com pessoas dentro da organização, a ação **Revogar acesso ao conteúdo** restringe as permissões para o arquivo e a ação **Enviar uma notificação** permite que as pessoas substituam as ações nesta regra, fornecendo uma justificativa de negócios. Às vezes, os negócios da sua organização exigem que pessoas internas compartilhem dados de PII e você não deseja que sua política de DLP bloqueie esse trabalho. 
    
3. Terceira regra: Se mais do que cinco instâncias dessas informações confidenciais forem detectadas em um documento e o documento for compartilhado com pessoas de fora organização, a ação **Revogar acesso ao conteúdo** restringe as permissões para o arquivo e a ação **Enviar uma notificação** não permite que as pessoas substituam as ações nesta regra, porque as informações são compartilhadas externamente. Sob nenhuma circunstância deve-se permitir que as pessoas em sua organização compartilhem dados de PII fora da organização. 
    
Veja aqui alguns pontos para entender sobre o uso de uma dica de política para substituir uma regra:
  
- A opção de substituição é por regra, e substitui todas as ações na regra (exceto o envio de uma notificação, que não pode ser substituído).
    
- É possível que o conteúdo corresponda a várias regras em uma política de DLP, mas apenas a dica de política da regra mais restritiva e de maior prioridade será mostrada. Por exemplo, uma dica de política de uma regra que bloqueia o acesso ao conteúdo será mostrada em detrimento de uma dica de política de uma regra que simplesmente envia uma notificação. Isso impede que as pessoas vejam uma cascata de dicas de política.
    
- Se as dicas de política na regra mais restritiva permitir que as pessoas substituam a regra, substituir essa regra também substitui quaisquer outras regras que o conteúdo correspondeu.
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Dicas de política nos sites do OneDrive for Business e do SharePoint Online

Quando um documento em um site do OneDrive for Business ou do SharePoint Online corresponde a uma regra em uma política de DLP e essa regra usa dicas de política, as dicas de política exibem ícones especiais no documento:
  
1. Se a regra enviar uma notificação sobre o arquivo, o ícone de aviso é exibido.
    
2. Se a regra bloquear o acesso ao documento, o ícone de bloqueado aparece.
    
![Ícones de dica de política em documentos em uma conta do OneDrive](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
Para executar uma ação em um documento, você pode selecionar um \> item escolha o ícone](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) do painel de informações de **informações** ![no canto superior direito da página para abrir a \> **dica de política de exibição**do painel de detalhes.
  
A dica de política lista os problemas com o conteúdo e se as dicas de política forem configuradas com essas opções, você pode escolher **Resolver** e então **Substituir** a dica de política ou **Relatar** um falso positivo. 
  
![Painel de informações mostrando dica de política](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![Dica de política com opção para substituir](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
As políticas de DLP são sincronizadas para sites e o conteúdo é avaliado em comparação com elas de forma periódica e assíncrona, portanto, pode haver um pequeno atraso entre a hora em que você criar a política de DLP e a hora em que você começar a receber dicas de política. Pode haver um atraso semelhante ao resolver ou substituir uma dica de política em relação a quando o ícone do documento no site desaparece.
  
### <a name="default-text-for-policy-tips-on-sites"></a>Texto padrão para dicas de política em sites

Por padrão, as dicas de política exibem um texto semelhante ao seguinte para um item em um site. O texto de notificação é configurado separadamente para cada regra, para que o texto exibido seja diferente dependendo da regra que for correspondida.

|**Se a regra de política de DLP fizer isso...**|**Em seguida, a dica de política padrão diz isso...**|
|:-----|:-----|
|Envia uma notificação, mas não permite substituição  <br/> |Este item está em conflito com uma política de sua organização.  <br/> |
|Bloqueia o acesso, envia uma notificação e permite a substituição  <br/> |Este item está em conflito com uma política de sua organização. Se você não resolver esse conflito, o acesso a esse arquivo poderá ser bloqueado.  <br/> |
|Bloqueia o acesso e envia uma notificação  <br/> |Este item está em conflito com uma política de sua organização. O acesso a este item está bloqueado para todos, exceto seu proprietário, o último modificador e o administrador de conjunto de site principal.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>Texto personalizado para dicas de política em sites

Você pode personalizar o texto para dicas de política separadamente da notificação por email. Ao contrário do texto personalizado para notificações por email (consulte a seção acima), o texto personalizado para dicas de política não aceita HTML ou tokens. Em vez disso, o texto personalizado para dicas de política é texto sem formatação somente com um limite de 256 caracteres.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Dicas de política no Outlook na Web e no Outlook 2013 e posterior

Ao redigir um novo email no Outlook na Web e no Outlook 2013 e posterior, você verá uma dica de política se adicionar conteúdo que corresponda a uma regra em uma política de DLP e essa regra usar dicas de política. A dica de política é exibida na parte superior da mensagem, acima dos destinatários, enquanto a mensagem está sendo redigida.
  
![Dica de política na parte superior de uma mensagem que está sendo composta](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
Dicas de política funcionam se as informações confidenciais aparecem no corpo da mensagem, na linha de assunto ou até mesmo em um anexo de mensagem, conforme mostrado aqui.
  
![Dica de política mostrando que um anexo está em conflito com uma política de DLP](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
Se as dicas de política estiverem configuradas para permitir substituição, você poderá escolher **Mostrar detalhes** \> **substituir** \> Insira uma justificativa de negócios \> ou relatar uma **substituição**falsa positiva.
  
![Dica de política na mensagem expandida para mostrar a opção substituir](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![Caixa de diálogo dica de política onde você pode substituir a dica de política](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
Observe que, quando você adiciona informações confidenciais a um email, pode haver latência entre quando as informações confidenciais são adicionadas e quando a dica de política é exibida.

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>O Outlook 2013 e posterior oferece suporte para mostrar dicas de política para apenas algumas condições

Atualmente, o Outlook 2013 e versões posteriores dão suporte à exibição de dicas de política somente para essas condições:

- Conteúdo contém
- O conteúdo é compartilhado

Observe que todas essas condições funcionam no Outlook, onde elas corresponderão ao conteúdo e imporão ações de proteção ao conteúdo. Mas Mostrar dicas de política para usuários ainda não tem suporte.
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a>Dicas de política no centro de administração do Exchange versus centro de conformidade &amp; de segurança do Office 365

As dicas de política podem funcionar com políticas de DLP e regras de fluxo de email criadas no centro de administração do Exchange ou com políticas de DLP criadas &amp; no centro de conformidade de segurança do Office 365, mas não em ambos. Isso ocorre porque essas políticas são armazenadas em locais diferentes, mas as dicas de política podem desenhar apenas de um único local.
  
Se você configurou as dicas de política no centro de administração do Exchange, as dicas de política configuradas no &amp; centro de conformidade de segurança do Office 365 não aparecerão aos usuários no Outlook na Web e no Outlook 2013 e posteriores até que você desative as dicas no centro de administração do Exchange. Isso garante que as regras de fluxo de emails atuais do Exchange (também conhecidas como regras de transporte) continuem a funcionar até que você opte por alternar &amp; para o centro de conformidade de segurança do Office 365.
  
Observe que, embora as dicas de política possam desenhar apenas de um único local, as notificações por email são sempre enviadas, mesmo se você estiver usando políticas de DLP &amp; no centro de conformidade de segurança do Office 365 e no centro de administração do Exchange.
  
### <a name="default-text-for-policy-tips-in-email"></a>Texto padrão para dicas de política no email

Por padrão, as dicas de política exibem texto semelhante ao seguinte para email.

|**Se a regra de política de DLP fizer isso...**|**Em seguida, a dica de política padrão diz isso...**|
|:-----|:-----|
|Envia uma notificação, mas não permite substituição  <br/> |Seu email entra em conflito com uma política da sua organização.  <br/> |
|Bloqueia o acesso, envia uma notificação e permite a substituição  <br/> |Seu email entra em conflito com uma política da sua organização.  <br/> |
|Bloqueia o acesso e envia uma notificação  <br/> |Seu email entra em conflito com uma política da sua organização.  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Dicas de política no Excel, PowerPoint e Word

Quando as pessoas trabalham com conteúdo confidencial nas versões de área de trabalho do Excel, PowerPoint e Word, as dicas de política podem notificá-los em tempo real de que o conteúdo está em conflito com uma política de DLP. Isso requer que:
  
- O documento do Office esteja armazenado em um site do OneDrive for Business ou do SharePoint Online.
    
- O site é incluído em uma política de DLP que é configurada para usar dicas de política.
    
Os programas da área de trabalho do Office sincronizam automaticamente políticas DLP diretamente do Office 365 e, em seguida, examinam seus documentos para garantir que eles não entrem em conflito com suas políticas de DLP e exibem dicas de política em tempo real.
  
Dependendo de como você configurar as dicas de política na política de DLP, as pessoas podem optar por simplesmente ignorar a dica de política, substituir a diretiva com ou sem uma justificativa de negócios ou relatar um falso positivo.
  
As dicas de política são exibidas na barra de mensagens.
  
![Barra de mensagem mostra a dica de política no Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
As dicas de política também aparecem no modo de exibição Backstage (na guia **Arquivo**). 
  
![O Backstage mostra a dica de política no Excel 2016](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
Se as dicas de política na política de DLP forem configuradas com essas opções, você pode escolher **Resolver** para **Substituir** uma dica de política ou **Relatar** um falso positivo. 
  
![Opções sobre dicas de política no Backstage no Excel 2016](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
Em cada um desses programas da área de trabalho do Office, as pessoas podem optar por desativar as dicas de política. Se estiverem desativadas, as dicas de política que são simples notificações não aparecerão no modo de exibição Backstage ou Barra de mensagens (na guia **Arquivo**). Entretanto, as dicas de política sobre bloqueio e substituição ainda serão exibidas e ainda receberão a notificação de email. Além disso, desativar dicas de política não isenta o documento de quaisquer políticas de DLP que foram aplicadas a ele. 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Texto padrão para dicas de política no Excel 2016, PowerPoint 2016 e Word 2016

Por padrão, as dicas de política exibem texto semelhante ao seguinte no modo de exibição de Backstage e de Barra de mensagem de um documento aberto. O texto de notificação é configurado separadamente para cada regra, para que o texto exibido seja diferente dependendo da regra que for correspondida.

|**Se a regra de política de DLP fizer isso...**|**Em seguida, a dica de política padrão diz isso...**|
|:-----|:-----|
|Envia uma notificação, mas não permite substituição  <br/> |Este arquivo está em conflito com uma política de sua organização. Vá para o menu **arquivo** para obter mais informações.  <br/> |
|Bloqueia o acesso, envia uma notificação e permite a substituição  <br/> |Este arquivo está em conflito com uma política de sua organização. Se você não resolver esse conflito, o acesso a esse arquivo poderá ser bloqueado. Vá para o menu **arquivo** para obter mais informações.  <br/> |
|Bloqueia o acesso e envia uma notificação  <br/> |Este arquivo está em conflito com uma política de sua organização. Se você não resolver esse conflito, o acesso a esse arquivo poderá ser bloqueado. Vá para o menu **arquivo** para obter mais informações.  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Texto personalizado para dicas de política no Excel, PowerPoint e Word

Você pode personalizar o texto para dicas de política separadamente da notificação por email. Ao contrário do texto personalizado para notificações por email (consulte a seção acima), o texto personalizado para dicas de política não aceita HTML ou tokens. Em vez disso, o texto personalizado para dicas de política é texto sem formatação somente com um limite de 256 caracteres.
  
## <a name="more-information"></a>Mais informações

- [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md)
    
- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
    
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
    
- [O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)
