---
title: Relatórios no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Use o Centro de Conformidade & segurança para obter vários relatórios para sua organização do SharePoint Online e do Exchange Online, além de relatórios do Azure Active Directory.
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926149"
---
# <a name="reports-in-the-security--compliance-center"></a>Relatórios no Centro de Conformidade e Segurança

Você pode usar a página **Exibir relatórios** no Centro de Conformidade & Segurança para acessar rapidamente relatórios de auditoria para suas organizações do SharePoint Online e do Exchange Online. Você também pode acessar relatórios de entrada do usuário do Azure Active Directory (AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página **Exibir relatórios.** Isso porque sua assinatura paga do Microsoft 365 inclui uma assinatura gratuita do Microsoft Azure. Na primeira vez que você tentar acessar esses relatórios do Azure, você terá que concluir um processo de registro único. 
  
> [!TIP]
> Para exibir relatórios adicionais sobre atividades em sua organização, consulte Relatórios de Atividades no Centro de administração [do Microsoft 365.](../admin/activity-reports/activity-reports.md) 
  
 **Antes de começar**
  
Você precisa das seguintes permissões para exibir relatórios no Centro de Conformidade & Segurança.
  
- Você precisa ter a função leitor de segurança no Centro de administração do Exchange (EAC) para exibir relatórios no Centro de Conformidade & Segurança. Por padrão, essa função é atribuída aos grupos de função Gerenciamento da Organização e Leitor de Segurança no EAC.
    
- Você precisa ter a função de Gerenciamento de Conformidade View-Only DLP no Centro de Conformidade & Segurança para exibir relatórios DLP no Centro de Conformidade & Segurança. Por padrão, essa função é atribuída aos grupos de função Administrador de Conformidade, Gerenciamento da Organização, Administrador de Segurança e Leitor de Segurança no Centro de Conformidade & Segurança.

- Além disso, você precisa receber a função View-Only Destinatários no EAC para exibir relatórios de DLP no EAC. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade, Gerenciamento da Organização e View-Only Gerenciamento da Organização no EAC.
  
 **Para abrir a página Exibir relatórios no Centro de Conformidade & Segurança:**
  
1. Acesse [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Entre usando as credenciais de uma conta de usuário em sua organização.
    
Na página **Exibir relatórios,** você pode exibir os seguintes tipos de relatórios: 
  
- [Relatórios de Auditoria](#auditing-reports)
- [Relatório de revisão de supervisão](#supervisory-review-report)
- [Relatórios de prevenção contra perda de dados](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Relatórios de auditoria

A tabela a seguir descreve os relatórios  na seção **Auditoria** na página Exibir relatórios no Centro de Conformidade & Segurança. 
  
|**Relatório**|**Descrição**|
|:-----|:-----|
|**relatório de log de auditoria** <br/> |Você pode pesquisar no log de auditoria a atividade de usuário e administrador em sua organização. O relatório contém entradas atividade de usuário e administrador no Exchange Online, SharePoint Online, OneDrive for Business e Azure Active Directory, que é o serviço de diretório do Office 365. Para obter mais informações, [consulte Pesquisar o log de auditoria no Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Relatórios do Azure AD** <br/> |Para procurar atividades de login incomuns ou suspeitas em sua organização, você pode usar relatórios de login e atividades no Microsoft Azure. Você também pode exibir eventos no log de auditoria do Azure AD. Para exibir relatórios no Azure, basta clicar em Exibir relatórios **do Azure AD.** Para mais informações, confira: <br/><br/>[Use sua assinatura gratuita do Azure Active Directory no Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Exibir seus relatórios de acesso e uso.](/azure/active-directory/reports-monitoring/overview-reports)  <br/> |
|**Relatórios de auditoria do Exchange** <br/> | Você pode usar a funcionalidade de auditoria no Microsoft 365 para acompanhar as alterações feitas na configuração do Exchange Online pelos administradores da sua organização. Alterações feitas na sua organização do Exchange Online por um administrador de data center da Microsoft ou por um administrador delegado também são registradas. Para o Exchange Online, o log de auditoria do administrador está habilitado por padrão, portanto, você não precisa fazer nada para ative-lo. O Exchange Online também fornece log de auditoria de caixa de correio para permitir que você acompanhe o acesso a caixas de correio por alguém que não seja o proprietário da caixa de correio. Você precisa habilitar o log de auditoria de caixas de correio em cada caixa de correio para a qual desejar controlar o acesso de não proprietário.  <br/>  Para obter o log de auditoria de administrador e caixa de correio, você pode executar relatórios de auditoria para exibir as entradas do log de auditoria. Você também pode exportar logs de auditoria de caixa de correio e de administrador, que são enviados para você dentro de 24 horas em um arquivo XML que é anexado à mensagem de email. <br/><br/>Para mais informações sobre os logs de auditoria de exportação, confira:  <br/><br/> [Exportar logs de auditoria de caixas de correio](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [Exibir e exportar o log de auditoria do administrador do datacenter](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [Pesquisar as alterações do grupo de funções ou logs de auditoria de administrador](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Relatórios de auditoria do Exchange](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).  <br/> |
   
## <a name="supervisory-review-report"></a>Relatório de revisão de supervisão

Com o relatório de revisão de supervisão, você pode ver o status de todas as políticas de revisão de supervisão em sua organização. Para obter mais informações, consulte [Configure supervisory review policies for your organization](./communication-compliance-configure.md).
  
## <a name="data-loss-prevention-reports"></a>Relatórios de prevenção contra perda de dados

Os relatórios de prevenção contra perda de dados (DLP) contêm informações sobre as políticas e regras de DLP que foram aplicadas ao conteúdo contêm dados confidenciais em sua organização. Você também pode configurar o relatório para exibir informações sobre as ações de DLP que eram baseados na sua política e nas regras de DLP. Para obter mais informações, [consulte Exibir o relatório para prevenção contra perda de dados](view-the-dlp-reports.md).