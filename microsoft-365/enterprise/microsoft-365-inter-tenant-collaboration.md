---
title: Colaboração entre locatários do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Saiba como a colaboração do Microsoft 365 funciona em locatários e organizações, permitindo que diferentes organizações trabalhem juntas com segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00eacfc21d3223b5b9a1ad420cd5d1d85bf4ea8e
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384830"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Colaboração entre locatários do Microsoft 365

Suponha que duas organizações, Fabrikam e Contoso, têm um locatário do Microsoft 365 para empresas e querem trabalhar juntas em vários projetos; algumas delas são executados por um tempo limitado e algumas delas estão em andamento. Como a Fabrikam e a Contoso podem permitir que suas pessoas e equipes colaborem com mais eficiência em seus diferentes locatários do Microsoft 365 de maneira segura? O Microsoft 365, em conjunto com a colaboração B2B do Azure Active Directory (Azure AD), oferece várias opções. Este artigo descreve vários cenários importantes que a Fabrikam e a Contoso podem considerar.
  
As opções de colaboração entre locatários do Microsoft 365 incluem o uso de um local central para arquivos e conversas, o compartilhamento de calendários, o uso de IM, chamadas de áudio/vídeo para comunicação e a segurança do acesso a recursos e aplicativos. Use as tabelas a seguir para selecionar soluções e saber mais.
  
## <a name="exchange-online-collaboration-options"></a>Opções de colaboração do Exchange Online

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Compartilhar calendários com outra organização do Microsoft 365 |Os administradores podem configurar diferentes níveis de acesso ao calendário no Exchange Online para permitir que as empresas colaborem com outras empresas e permitir que os usuários compartilhem as agendas (informações de livre/ocupado) com outras pessoas. | <ul><li>[Compartilhamento](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [Relações da organização](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [Criar um relacionamento de organização](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [Modificar um relacionamento de organização ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [Remover uma relação de organização](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [Compartilhar calendários com usuários externos](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd)
 </li></ul> |
|Controlar como os usuários compartilham seus calendários com pessoas de fora da sua organização | Os administradores aplicam políticas de compartilhamento às caixas de correio dos usuários para controlar com quem ele pode ser compartilhado e o nível de acesso concedido |  <ul><li> [Políticas de compartilhamento](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [Criar uma política de compartilhamento](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [Aplicar uma política de compartilhamento a caixas de correio](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [Modificar, desabilitar ou remover uma política de compartilhamento](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|Configurar canais de email seguros e controlar o fluxo de emails com organizações parceiras | Os administradores criam conectores para aplicar segurança a trocas de emails com uma organização parceira ou provedor de serviços. Os conectores impõem a criptografia por meio de TLS (transport layer security), bem como permitem restrições em nomes de domínio ou intervalos de endereços IP de onde seus parceiros enviam emails. |  <ul><li> [Como o Exchange Online usa TLS para proteger conexões de e-mail](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [Configurar o fluxo de emails usando conectores](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [Domínios remotos](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [Configurar conector para fluxo de email seguro com uma organização parceira](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [Práticas recomendadas de fluxo de emails (visão geral)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Opções de colaboração do SharePoint Online e do OneDrive for Business

| Metas de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Compartilhar sites e documentos com usuários externos | Os administradores configuram o compartilhamento no nível do locatário ou do conjunto de sites para contas autenticadas, de contas de trabalho ou de estudante da Microsoft autenticadas ou de convidado |  <ul><li> [Gerenciar compartilhamento externo para o ambiente do SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [Usar o SharePoint Online como uma solução de extranet entre empresas (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Controle e controle do compartilhamento externo para usuários finais | Proprietários de arquivos do OneDrive for Business e usuários finais do SharePoint Online configuram o compartilhamento de sites e documentos e estabelecem notificações para controlar o compartilhamento |  <ul><li> [Configurar notificações para compartilhamento externo do OneDrive for Business](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Compartilhar arquivos ou pastas do Microsoft Office SharePoint Online](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Opções de colaboração do Skype for Business

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Skype for Business Online - IM, chamadas e presença com outros usuários do Skype for Business | Os administradores podem habilitar seus usuários do Skype for Business Online para mensagens de IM, fazer chamadas de áudio/vídeo e ver a presença com usuários em outro locatário do Microsoft 365. | [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype for Business Online - IM, chamadas e presença com usuários do Skype (consumidor) | Os administradores podem habilitar seus usuários do Skype for Business Online para mensagens de IM, fazer chamadas e ver a presença com usuários do Skype (consumidor). | [Permitir que os usuários do Skype for Business adicionem contatos do Skype](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Opções de colaboração do Azure AD B2B

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Colaboração B2B do Azure AD - compartilhamento de conteúdo adicionando usuários externos a um grupo no diretório de uma organização | Um administrador global de um locatário do Microsoft 365 pode convidar pessoas em outro locatário do Microsoft 365 para ingressar em seu diretório, adicionar esses usuários externos a um grupo e conceder acesso ao conteúdo, como sites e bibliotecas do SharePoint para o grupo. |  <ul><li> [O que é a visualização de colaboração B2B do Azure AD?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [B2B do Azure AD: novas atualizações facilitam o collab entre empresas](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Compartilhamento externo e colaboração B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Personalização e API de colaboração B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD e Identity Show: Colaboração B2B do Azure AD (Negócios para Empresas](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Opções de colaboração do Microsoft 365

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Grupos do Microsoft 365 – Email, calendário, OneNote e arquivos compartilhados em um local central | Os grupos são suportados nos planos Business Essentials, Business Premium, Education e Enterprise E1, E3 e E5. As pessoas em um locatário do Microsoft 365 podem criar um grupo e convidar pessoas em outro locatário do Microsoft 365 como usuários convidados. Também se aplica ao Dynamics CRM. |  <ul><li> [Saiba mais sobre os grupos do Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Acesso de convidados nos Grupos do Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Implantar grupos do Microsoft 365](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Opções de colaboração do Yammer

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|Yammer - Colaboração por meio de uma mídia social corporativa | A menos que a capacidade de criar grupos externos seja desabilitada por um administrador do Yammer, os usuários podem criar grupos externos para colaborar no Yammer por meio de conversas, a capacidade de gosta e acompanhar postagens, compartilhar arquivos e conversar online. | [Criar e gerenciar grupos externos no Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Opções de colaboração do Teams

|Meta de compartilhamento|Ação administrativa|Informações de como fazer|
|:-----|:-----|:-----|
|Colaborar no Teams com usuários externos à organização | Um administrador global para o locatário convidado do Microsoft 365 precisa habilitar a colaboração externa no Teams. Os administradores globais e proprietários da equipe agora poderão convidar qualquer pessoa com um endereço de email para colaborar no Teams.  <br/> Os administradores também podem gerenciar e editar Convidados já presentes em seus locatários. |  <ul><li> [Autorizar o acesso de convidados](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Ativar ou desativar o acesso de convidados no Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [Usar o PowerShell para controlar o acesso de convidados](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [Lista de verificação de acesso de convidados](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [Exibir Usuários Convidados](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [Editar informações de usuários convidados](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|Os proprietários da equipe podem convidar e gerenciar como os convidados colaboram em suas equipes.  |Os proprietários de equipe têm controles adicionais sobre o que os convidados podem fazer em suas equipes. |  <ul><li> [Adicionar Convidados](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Adicionar um convidado a uma equipe](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Gerenciar o acesso de convidados no Teams](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [Ver quem está em uma equipe ou em um canal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Convidados de outros locatários podem exibir conteúdo no Teams e colaborar com outros membros | Nenhum. | [A experiência de acesso de convidados](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Opções de colaboração do Power BI

| Meta de compartilhamento | Ação administrativa | Informações de como fazer |
|:-----|:-----|:-----|
|O Power BI permite que usuários convidados externos consumam conteúdo compartilhado por meio de links. Isso permite que os usuários na organização distribuam conteúdo de maneira segura entre organizações.<br/> | O Administrador do Power BI pode controlar se os usuários podem convidar usuários externos para exibir o conteúdo dentro da organização.| [Distribuir conteúdo do Power BI para usuários convidados externos com o Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Aponta para estar ciente da colaboração entre locatários do Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Compartilhamento de contas de usuário, licenças, assinaturas e armazenamento

Cada organização mantém suas próprias contas de usuário, identidades, grupos de segurança, assinaturas, licenças e armazenamento. As pessoas usam os recursos de colaboração no Microsoft 365 juntamente com políticas de compartilhamento e configurações de segurança para fornecer acesso às informações necessárias, mantendo o controle dos ativos da empresa.
  
- **Contas de usuário:** As contas não podem ser compartilhadas ou duplicadas entre os locatários ou partições nos Serviços de Domínio do Active Directory local. 
    
- **Assinaturas de &amp; licenças:** no Microsoft 365, as licenças de planos de licenciamento (também chamados de SKUs ou planos do Microsoft 365) dão aos usuários acesso aos serviços do Microsoft 365 definidos para esses planos. 
    
- **Armazenamento:** Nos planos de licenciamento do Microsoft 365, os limites de software para o SharePoint Online são gerenciados separadamente dos limites de armazenamento da caixa de correio. Os limites de armazenamento de caixa de correio são definidos e gerenciados usando o Exchange Online. Em ambos os cenários, o armazenamento não pode ser compartilhado entre locatários. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Podemos compartilhar namespaces de domínio entre locatários do Microsoft 365?

Não. Os nomes de domínio da organização, como fabrikam.com ou tailspintoys.com, só podem ser associados e usados com um único locatário do Microsoft 365. Cada locatário deve ter seu próprio namespace. Os namespaces UPN, SMTP e SIP não podem ser compartilhados entre locatários.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>E os componentes híbridos e a colaboração entre locatários do Microsoft 365?

Os componentes híbridos locais, como uma organização do Exchange e o Azure AD Connect, não podem ser divididos entre vários locatários.
 

