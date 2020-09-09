---
title: Recursos de relatório do Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: Saiba mais sobre vários recursos de relatório no Microsoft 365, incluindo o Active Directory do Azure e o Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 59a7569518ad3e4704b3528d175c092b0a19b819
ms.sourcegitcommit: 294a51ef0ff48dddb659c602e047d7fd98f91172
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47407911"
---
# <a name="microsoft-365-reporting-features"></a>Recursos de relatório do Microsoft 365

Os recursos de relatório no Microsoft 365 oferecem vários relatórios de auditoria para o Azure Active Directory (Azure AD), o Exchange Online, o gerenciamento de dispositivos, a análise de supervisão e a prevenção de perda de dados (DLP). Esses relatórios são diferentes e separados dos relatórios de atividades do Microsoft 365.

## <a name="microsoft-365-reports-dashboard"></a>Painel de relatórios do Microsoft 365

O painel de relatórios no centro de administração do Microsoft 365 Preview exibe a atividade de uso no Microsoft 365. Os administradores globais do Microsoft 365 ou um administrador do Exchange Online, do SharePoint Online ou do Skype for Business podem obter informações detalhadas sobre o uso desse serviço. Por exemplo, o número de usuários em um determinado serviço do Microsoft 365, o número de usuários que ativaram os aplicativos da Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus) e o volume de emails que está fluindo pela organização. Os relatórios estão disponíveis para os últimos 7, 30, 90 e 180 dias.

Os seguintes relatórios estão disponíveis:

- [Relatório de atividade de email](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Relatório de ativações do Microsoft Office](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Relatório de uso do site do SharePoint Online](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [Relatório de uso do OneDrive for Business](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Relatórios de atividades do Yammer](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Relatório de atividade do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Relatório de atividade ponto a ponto do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Relatório do organizador de conferências do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Relatório atividade de participantes de conferências do Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Para obter mais informações, consulte [Activity reports in the Microsoft 365 Admin Center](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).

## <a name="azure-ad-reports"></a>Relatórios do Azure AD

A Microsoft 365 usa o Azure AD para gerenciamento de identidade e autenticação. Os administradores do Microsoft 365 usam relatórios gerados pelo Azure para identificar atividades incomuns e acesso não autorizado a seus dados. Você pode usar relatórios de acesso e uso no Azure AD para obter visibilidade da integridade e segurança do diretório da sua organização. Com essas informações, você pode identificar e reduzir possíveis riscos de segurança.

Os relatórios do Azure AD podem ser exportados para o Microsoft Excel e correlacionados a outros dados do Microsoft 365. Por exemplo, os resultados de uma pesquisa de log de auditoria podem fornecer informações sobre acesso, autenticação e atividades no nível do aplicativo. Relatórios de anomalia e uso de recursos avançados estão disponíveis com o Azure AD Premium. Esses relatórios avançados ajudam a melhorar a postura de segurança e a ajudá-lo a responder a possíveis ameaças aplicando análises sobre o acesso ao dispositivo e o uso do aplicativo. Para obter mais informações, consulte [Azure Active Directory Reporting](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/).

## <a name="exchange-online-audit-reports"></a>Relatórios de auditoria do Exchange Online

Os relatórios de auditoria do Exchange Online incluem detalhes sobre o acesso à caixa de correio e as alterações feitas por administradores no locatário do Exchange Online. Com a auditoria de caixa de correio, você pode usar as tarefas da tabela a seguir para executar relatórios e exportar logs de auditoria do Exchange Online.

> [!NOTE]
> Você deve habilitar o log de auditoria de caixa de correio para cada caixa de correio para que os eventos auditados sejam salvos no log de auditoria dessa caixa de correio. Se o log de auditoria de caixa de correio não estiver habilitado para uma caixa de correio, os eventos dessa caixa de correio não serão salvos no log de auditoria e não aparecerão nos relatórios de auditoria de caixa de correio Para obter mais informações, consulte [habilitar a auditoria de caixa de correio](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Tarefas | Descrição |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Executar um relatório de acesso não proprietário da caixa de correio](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Exibe a lista de caixas de correio acessadas por alguém que não seja o proprietário da caixa de correio. O relatório contém informações sobre quem acessou a caixa de correio, as ações executadas na caixa de correio e se as ações foram bem-sucedidas. |
| [Exportar logs de auditoria de caixas de correio](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Os logs de auditoria de caixa de correio contêm informações sobre acesso e ações em uma caixa de correio realizada por um usuário diferente do proprietário da caixa de correio. Os administradores podem especificar caixas de correio junto com um intervalo de datas para gerar relatórios. Os logs são exportados em XML, anexados a uma mensagem e enviados a usuários específicos, conforme determinado pelo administrador. |
| [Executar um relatório do grupo de funções do administrador:](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | O grupo de funções de administrador atribui privilégios administrativos aos usuários. Esses privilégios permitem que os usuários realizem tarefas administrativas, como redefinir senhas, criar ou modificar caixas de correio e atribuir privilégios de administrador a outros usuários. O relatório do grupo de funções de administrador mostra alterações nos grupos de função, incluindo a adição ou a remoção de membros. |
| [Exibir o log de auditoria de administrador](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | O relatório de log de auditoria de administrador lista todas as funções de criação, atualização e exclusão executadas por administradores no Exchange Online. As entradas de log fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados. |
| [Pesquisa e retenção de conteúdo de caixa de correio](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Fornece detalhes de todas as alterações feitas nas configurações de descoberta eletrônica in-loco ou bloqueio in-loco nas caixas de correio. |
| [Exportar o log de auditoria de administrador](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | O log de auditoria do administrador registra ações administrativas específicas como criar, atualizar e excluir no Exchange Online. Os resultados do log são exportados para XML e os administradores podem optar por enviar esse log para um conjunto de usuários. |
| [Executar um relatório de suspensão de litígio por caixa de correio](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Fornece detalhes de todas as alterações nas configurações de retenção de litígio nas caixas de correio. |
| [Exibir e exportar o log de auditoria do administrador externo](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Contém detalhes das ações executadas por administradores externos. As entradas fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados e quaisquer ações que criam, modificam ou excluem objetos no Exchange Online. |

## <a name="device-compliance-reports"></a>Relatórios de conformidade do dispositivo

Você gerencia e protege dispositivos móveis conectados à sua assinatura usando mobilidade básica e segurança para o Microsoft 365. Os dispositivos móveis usados para acessar email, calendário, contatos e documentos do trabalho têm uma parte significativa para garantir que os funcionários possam trabalhar a qualquer momento e de qualquer lugar. É fundamental que você proteja as informações da sua organização. Você usa a mobilidade básica e a segurança do Microsoft 365 para definir políticas de segurança de dispositivos e regras de acesso. Se perdido ou roubado, você também usa a mobilidade básica e a segurança do Microsoft 365 para limpar dispositivos móveis.

Relatórios de segurança e mobilidade básica fornecem uma visão geral das políticas configuradas por uma organização para proteger dispositivos móveis que acessam os dados 365 da Microsoft. O relatório permite a filtragem de dispositivos por status de conformidade, violações relatadas, dispositivos bloqueados e quantos dispositivos foram apagados como resultado de políticas de segurança. Para obter mais informações, consulte [Overview of Basic Mobility and Security for Microsoft 365](https://support.microsoft.com/office/overview-of-basic-mobility-and-security-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Prevenção contra perda de dados

As políticas de DLP ajudam a gerenciar a segurança e o fluxo de informações em uma organização. Você pode configurar políticas para bloquear o acesso a conteúdo, criptografar dados ou notificar os usuários sobre violações de política e política usando dicas de política de DLP no aplicativo. Os relatórios de DLP fornecem informações sobre o número de correspondências de políticas e regras, substituições e falsos positivos.

Use o centro de administração do Microsoft 365 para exibir informações sobre o número de mensagens detectadas por suas políticas de DLP. Os relatórios de DLP fornecem informações sobre correspondências de política e de regra para emails enviados e recebidos. Você também pode exibir o número de correspondências, substituições e falsos positivos de cada política nas últimas 24 horas usando o centro de administração do Exchange. Se você baixar um relatório do Excel, poderá exibir ainda mais detalhes, como quem enviou a mensagem, em que dia e que correspondências de política foram acionadas. Para obter mais informações, consulte [exibir relatórios sobre detecções de política DLP](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj889415(v=exchg.150)).

## <a name="auditing-in-yammer-enterprise"></a>Auditoria no Yammer Enterprise

O Yammer Enterprise oferece aos administradores a capacidade de exportar dados de atividade do usuário da sua rede do Yammer por meio da [API de exportação de dados do Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)ou manualmente através da página de administração de rede do Yammer. A capacidade de exportar logs é restrita aos administradores de rede no Yammer. (Todos os administradores globais da Microsoft 365 são administradores de rede do Yammer.)

Os dados a seguir são exportáveis:

| Nome do arquivo | Descrição |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Todos os usuários novos, pendentes e suspensos na rede |
| Messages.csv | Todas as mensagens na rede |
| Files.csv (metadados) | Metadados como nome de arquivo, URL de API de arquivo, ID de Uploader, carregados em, etc. |
| Files.csv (arquivos originais) | Arquivo zip dos arquivos originais carregados por usuários no Yammer |
| Topics.csv | Tópicos criados na rede |
| Pages.csv | Páginas (anotações) criadas por usuários na rede |
| Admins.csv | Todos os administradores verificados na rede |
| Networks.csv | Todas as redes externas do Yammer |

Os dados do Yammer Enterprise também estão disponíveis por meio dos relatórios de atividades do Microsoft 365. Além disso, o Yammer está trabalhando ativamente na exposição de log adicional por meio da API de atividade de gerenciamento do Microsoft 365 e na capacidade de motivo de dados usando o Power BI. Confira o [mapa do Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) para obter mais informações sobre esses recursos.
