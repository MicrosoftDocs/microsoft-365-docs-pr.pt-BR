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
description: 'Use o centro de conformidade de & de segurança para obter vários relatórios para sua organização do SharePoint Online e do Exchange Online, além de relatórios do Azure Active Directory.  '
ms.openlocfilehash: 4783c3171f5f49dd50d6da8f5f4835ba243f7ab3
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214703"
---
# <a name="reports-in-the-security--compliance-center"></a>Relatórios no Centro de Conformidade e Segurança

Você pode usar a página **exibir relatórios** no centro de conformidade de & de segurança para acessar rapidamente relatórios de auditoria para suas organizações do SharePoint Online e do Exchange Online. Você também pode acessar os relatórios de entrada do usuário do Azure Active Directory (AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página **exibir relatórios** . Isso ocorre porque sua assinatura paga do Microsoft 365 inclui uma assinatura gratuita para o Microsoft Azure. Na primeira vez que tentar acessar esses relatórios do Azure, você precisará concluir um processo de registro de uma vez. 
  
> [!TIP]
> Para exibir relatórios adicionais sobre a atividade em sua organização, consulte [relatórios de atividades no centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports). 
  
 **Antes de começar**
  
Você precisa das permissões a seguir para exibir relatórios no centro de conformidade de & de segurança.
  
- Você precisa ter a função de leitor de segurança no centro de administração do Exchange (Eat) para exibir relatórios no centro de conformidade do & de segurança. Por padrão, essa função é atribuída aos grupos de função de gerenciamento de organização e leitor de segurança no Eat.
    
- Você precisa ter a função de gerenciamento de conformidade DLP somente para exibição no centro de conformidade de & de segurança para exibir relatórios de DLP no centro de conformidade do & de segurança. Por padrão, essa função é atribuída aos grupos de função Administrador de conformidade, gerenciamento de organização, administrador de segurança e leitor de segurança no centro de conformidade de & de segurança.

- Além disso, você deve receber a função de destinatários somente para exibição no Eat para exibir relatórios de DLP no Eat. Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade, gerenciamento de organização e somente exibição da organização no Eat.
  
 **Para abrir a página exibir relatórios no centro de conformidade de & de segurança:**
  
1. Acesse [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Entre usando as credenciais de uma conta de usuário em sua organização.
    
Na página **exibir relatórios** , você pode exibir os seguintes tipos de relatórios: 
  
- [Relatórios de Auditoria](#auditing-reports)
- [Relatório de análise de supervisão](#supervisory-review-report)
- [Relatórios de prevenção contra perda de dados](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Relatórios de auditoria

A tabela a seguir descreve os relatórios na seção **auditoria** da página **exibir relatórios** no centro de conformidade do & de segurança. 
  
|**Relatório**|**Descrição**|
|:-----|:-----|
|**relatório de log de auditoria** <br/> |Você pode pesquisar o log de auditoria para atividades de usuário e de administrador em sua organização. O relatório contém entradas do usuário e da atividade de administração no Exchange Online, SharePoint Online, OneDrive for Business e Azure Active Directory, que é o serviço de diretório para o Office 365. Para obter mais informações, consulte [Search the Audit Log In The Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Relatórios do Azure AD** <br/> |Para procurar atividades de entrada incomuns ou suspeitas em sua organização, você pode usar os relatórios de entrada e de atividades no Microsoft Azure. Você também pode exibir eventos no log de auditoria do Azure AD. Para exibir relatórios no Azure, basta clicar em **exibir relatórios do Azure ad**. Para saber mais, confira: <br/><br/>[Use sua assinatura gratuita do Azure Active Directory no Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Exibir seus relatórios de uso e acesso](https://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Relatórios de auditoria do Exchange** <br/> | Você pode usar a funcionalidade de auditoria no Microsoft 365 para controlar as alterações feitas na configuração do Exchange Online pelos administradores da sua organização. As alterações feitas na sua organização do Exchange Online por um administrador de data center da Microsoft ou por um administrador delegado também são registradas. Para o Exchange Online, o log de auditoria de administrador é habilitado por padrão, portanto, você não precisa fazer nada para ativá-lo. O Exchange Online também fornece log de auditoria de caixa de correio para permitir que você controle o acesso a caixas de correio por alguém que não seja o proprietário da caixa de correio Você precisa habilitar o log de auditoria de caixas de correio em cada caixa de correio para a qual desejar controlar o acesso de não proprietário.  <br/>  Para obter o log de auditoria de administrador e caixa de correio, você pode executar relatórios de auditoria para exibir as entradas do log de auditoria. Você também pode exportar logs de auditoria de caixa de correio e de administrador, que são enviados para você dentro de 24 horas em um arquivo XML que é anexado à mensagem de email. <br/><br/>Para mais informações sobre os logs de auditoria de exportação, confira:  <br/><br/> [Exportar logs de auditoria de caixas de correio](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Exibir e exportar o log de auditoria do administrador de datacenter](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Pesquisar as alterações do grupo de funções ou logs de auditoria de administrador](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Relatórios de auditoria do Exchange](https://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Relatório de análise de supervisão

Com o relatório de análise de supervisão, você pode ver o status de todas as políticas de análise de supervisão em sua organização. Para saber mais, confira [Configurar políticas de análise de supervisão para sua organização](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Relatórios de prevenção contra perda de dados

Os relatórios de prevenção de perda de dados (DLP) contêm informações sobre as políticas e regras de DLP que foram aplicadas ao conteúdo contêm dados confidenciais em sua organização. Você também pode configurar o relatório para exibir informações sobre as ações de DLP que eram baseados na sua política e nas regras de DLP. Para obter mais informações, consulte [View the Report for Data Loss Prevention](view-the-dlp-reports.md).
