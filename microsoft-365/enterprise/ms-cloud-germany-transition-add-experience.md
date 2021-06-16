---
title: Atividades pós-migração para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: atividades pós-migração depois de mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930410"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Atividades pós-migração para a migração do Microsoft Cloud Deutschland

As seções a seguir fornecem atividades pós-migração para vários serviços depois de migrar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.

## <a name="azure-ad"></a>Azure Active Directory
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Autenticação federada do Azure AD com o AD FS
**Aplica-se a:** Todos os clientes que usam autenticação federada com o AD FS

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remova as confianças de terceiros confiável do Microsoft Cloud Deutschland AD FS. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa remover a confiança da parte confiável para os pontos de extremidade do Microsoft Cloud Deutschland. Isso só pode ser feito quando nenhum dos aplicativos do cliente aponta para os pontos de extremidade do Microsoft Cloud Deutschland quando o Azure AD é aproveitado como um Provedor de Identidade (IdP). | Organizações de Autenticação Federada | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Aprovações de grupo
**Aplica-se a:** Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração 

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não tiver sido aprovada. | Os clientes do usuário final precisarão usar o painel do Access para enviar uma solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração. |  Como usuário final: <ol><li>Navegue até [o painel do Access](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente durante os 30 dias antes da migração.</li><li>Solicitação para ingressar no grupo do Azure AD novamente.</li></ol> As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam solicitadas novamente após a migração. |
||||

## <a name="custom-dns-updates"></a>Atualizações DNS personalizadas
**Aplica-se a:**  Todos os clientes gerenciando suas próprias zonas DNS

| Step(s) | Descrição | Impacto |
|:------|:-------|:-------|
| Atualize os serviços DNS locais para Office 365 de serviços. | As entradas DNS gerenciadas pelo cliente que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para apontar para os pontos de extremidade Office 365 serviços globais. Consulte [Domínios no centro de](https://admin.microsoft.com/Adminportal/Home#/Domains) administração Microsoft 365 e aplique as alterações em sua configuração DNS. | A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||

## <a name="third-party-services"></a>Serviços de terceiros
**Aplica-se a:** Clientes que usam serviços de terceiros para Office 365 pontos de extremidade de serviços

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualize parceiros e serviços de terceiros para Office 365 de serviços. | <ul><li>Os serviços e parceiros de terceiros que apontam para Office 365 Alemanha precisam ser atualizados para apontar para os pontos de extremidade Office 365 serviços. Exemplo: registre-se de novo, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo de galeria de aplicativos, se disponível. </li><li>Aponte todos os aplicativos personalizados que aproveitam Graph API de `graph.microsoft.de` `graph.microsoft.com` para . Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se usadas. </li><li>Altere todos os aplicativos corporativos não de primeira parte para redirecionar para os pontos de extremidade em todo o mundo. </li></ul>| Ação necessária. A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||