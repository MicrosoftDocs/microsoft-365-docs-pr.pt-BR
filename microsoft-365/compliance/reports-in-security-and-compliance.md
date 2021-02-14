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
ms.openlocfilehash: 8762c1bbb23d2b9f3840076f0ffa465cf7ab264b
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936174"
---
# <a name="reports-in-the-security--compliance-center"></a>Relatórios no Centro de Conformidade e Segurança

Você pode usar **a** página Exibir relatórios no Centro de Conformidade e Segurança & para acessar rapidamente os relatórios de auditoria para suas organizações do SharePoint Online e do Exchange Online. Você também pode acessar relatórios de entrada do usuário do Azure Active Directory (AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página Exibir **relatórios.** Isso porque sua assinatura paga do Microsoft 365 inclui uma assinatura gratuita do Microsoft Azure. Na primeira vez que tentar acessar esses relatórios do Azure, você terá que concluir um processo de registro único. 
  
> [!TIP]
> Para exibir relatórios adicionais sobre atividades em sua organização, consulte [Relatórios de Atividades no Centro de administração do Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports) 
  
 **Antes de começar**
  
Você precisa das permissões a seguir para exibir relatórios no Centro de Conformidade & segurança.
  
- Você precisa ter a função Leitor de Segurança no Centro de administração do Exchange (EAC) para exibir relatórios no Centro de Conformidade e & Segurança. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Leitor de Segurança no EAC.
    
- Você precisa ter a função de Gerenciamento de Conformidade View-Only DLP no Centro de Conformidade de & de Segurança para exibir relatórios de DLP no Centro de Conformidade & Segurança. Por padrão, essa função é atribuída aos grupos de funções Administrador de Conformidade, Gerenciamento da Organização, Administrador de Segurança e Leitor de Segurança no Centro de Conformidade & Segurança.

- Além disso, você precisa ter a função View-Only destinatários no EAC para exibir relatórios de DLP no EAC. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade, Gerenciamento da Organização View-Only Gerenciamento da Organização no EAC.
  
 **Para abrir a página Exibir relatórios no Centro de Conformidade e & Segurança:**
  
1. Acesse [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Entre usando as credenciais de uma conta de usuário em sua organização.
    
Na página **Exibir relatórios,** você pode exibir os seguintes tipos de relatórios: 
  
- [Relatórios de Auditoria](#auditing-reports)
- [Relatório de revisão de supervisão](#supervisory-review-report)
- [Relatórios de prevenção contra perda de dados](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Relatórios de auditoria

A tabela a seguir descreve os relatórios  da seção **Auditoria** na página Exibir relatórios no Centro de & Conformidade e Segurança. 
  
|**Relatório**|**Descrição**|
|:-----|:-----|
|**relatório de log de auditoria** <br/> |Você pode pesquisar no log de auditoria a atividade de usuários e administradores em sua organização. O relatório contém entradas de atividade de usuários e administradores no Exchange Online, no SharePoint Online, no OneDrive for Business e no Azure Active Directory, que é o serviço de diretório do Office 365. Para obter mais informações, [consulte Pesquisar o log de auditoria no Office 365.](search-the-audit-log-in-security-and-compliance.md)  <br/> |
|**Relatórios do Azure AD** <br/> |Para procurar atividades de login incomuns ou suspeitas em sua organização, você pode usar relatórios de login e atividades no Microsoft Azure. Você também pode exibir eventos no log de auditoria do Azure AD. Para exibir relatórios no Azure, basta clicar em Exibir relatórios do **Azure AD.** Para saber mais, confira: <br/><br/>[Use sua assinatura gratuita do Azure Active Directory no Office 365.](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [Exibir seus relatórios de acesso e uso.](https://go.microsoft.com/fwlink/p/?LinkId=506902)  <br/> |
|**Relatórios de auditoria do Exchange** <br/> | Você pode usar a funcionalidade de auditoria no Microsoft 365 para controlar as alterações feitas na configuração do Exchange Online pelos administradores da sua organização. Alterações feitas na sua organização do Exchange Online por um administrador de data center da Microsoft ou por um administrador delegado também são registradas. Para o Exchange Online, o log de auditoria do administrador está habilitado por padrão, portanto, você não precisa fazer nada para ative-lo. O Exchange Online também fornece o log de auditoria de caixa de correio para permitir que você controle o acesso a caixas de correio por alguém que não seja o proprietário da caixa de correio. Você precisa habilitar o log de auditoria de caixas de correio em cada caixa de correio para a qual desejar controlar o acesso de não proprietário.  <br/>  Para obter o log de auditoria de administrador e caixa de correio, você pode executar relatórios de auditoria para exibir as entradas do log de auditoria. Você também pode exportar logs de auditoria de caixa de correio e de administrador, que são enviados para você dentro de 24 horas em um arquivo XML que é anexado à mensagem de email. <br/><br/>Para mais informações sobre os logs de auditoria de exportação, confira:  <br/><br/> [Exportar logs de auditoria de caixas de correio](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Exibir e exportar o log de auditoria do administrador do datacenter](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Pesquisar as alterações do grupo de funções ou logs de auditoria de administrador](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Relatórios de auditoria do Exchange.](https://go.microsoft.com/fwlink/p/?LinkID=395232)  <br/> |
   
## <a name="supervisory-review-report"></a>Relatório de revisão de supervisão

Com o relatório de análise de supervisão, você pode ver o status de todas as políticas de revisão de supervisão em sua organização. Para obter mais informações, [consulte Configurar políticas de revisão de supervisão para sua organização.](configure-supervision-policies.md)
  
## <a name="data-loss-prevention-reports"></a>Relatórios de prevenção contra perda de dados

Os relatórios de prevenção contra perda de dados (DLP) contêm informações sobre as políticas e regras de DLP que foram aplicadas ao conteúdo que contém dados confidenciais em sua organização. Você também pode configurar o relatório para exibir informações sobre as ações de DLP que eram baseados na sua política e nas regras de DLP. Para obter mais informações, consulte [Exibir o relatório de prevenção contra perda de dados.](view-the-dlp-reports.md)
