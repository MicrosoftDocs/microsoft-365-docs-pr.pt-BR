---
title: Exibir relatórios para proteção avançada contra ameaças
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Encontre e use relatórios para a proteção avançada contra ameaças do Office 365 no centro de conformidade de segurança &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: af5844cf05d14e34059a26291d2034187439ec56
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208484"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Exibir relatórios para a proteção avançada contra ameaças do Office 365

Se sua organização tiver a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP) e você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-the-atp-reports), poderá usar vários relatórios de ATP no centro de conformidade de segurança &amp; . (Ir para **relatórios** \> **Painel**.)

![O painel do centro de conformidade de segurança &amp; pode ajudá-lo a ver onde a proteção avançada contra ameaças está funcionando](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

Os relatórios ATP incluem o seguinte:

- [Relatório de Status da Proteção contra Ameaças](#threat-protection-status-report)
- [Relatório de Tipos de Arquivo ATP](#atp-file-types-report)
- [Relatório de Disposição de Mensagem ATP](#atp-message-disposition-report)
- [detecções ou Explorer em tempo real](threat-explorer.md) (dependendo se você tem o plano ATP 1 ou 2 do Office 365)
- ... [e muito mais](#additional-reports-to-view).

Leia este artigo para obter uma visão geral dos relatórios ATP e como usá-los.

## <a name="threat-protection-status-report"></a>Relatório de Status da Proteção contra Ameaças

O relatório de **status de proteção contra ameaças** é um modo de exibição único que reúne informações sobre conteúdo mal-intencionado e email mal-intencionado detectado e bloqueado pela [proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e pelo [Office 365 ATP](office-365-atp.md). Este relatório é útil para exibir detecções ao longo do tempo (até 90 dias) e permite que os administradores de segurança identifiquem tendências ou determinem se as políticas precisam de ajustes.

O relatório fornece uma contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado, como arquivos ou endereços de sites (URLs) que foram bloqueados pelo Mecanismo Antimalware, [limpeza automática de zero-hora (zap)](zero-hour-auto-purge.md)e recursos de ATP, como [links seguros de ATP](atp-safe-links.md), [anexos seguros de ATP](atp-safe-attachments.md)e [anti-phishing ATP](set-up-anti-phishing-policies.md).

Filtros e divisões das informações permitem categorizações mais granulares das informações deste relatório. Especificamente, há um menu "dividir por" incluído para o phishing de **email** \> **Phish** e os modos de exibição de malware de **email** \> **Malware views**. Ele dividirá os dados em:

|||
|---|---|
|Por tipo de detecção|Qual política ajudou a atrair essas ameaças?|
|Por tecnologia de detecção|Qual tecnologia subjacente da Microsoft capturou a ameaça?|
|Por status de entrega|O que aconteceu com as mensagens de email detectadas como ameaças?|
|

> [!TIP]
> O email > Phish | Os modos de exibição de malware têm detalhamentos granulares para as tecnologias de detecção mostradas, com categorias como *reputação de arquivo gerado por ATP*, *arquivo acionamento*, *URL acionamento*, *antifalsificação: falha de DMARC*, por exemplo, útil para identificar exatamente qual recurso levou sua organização a detectar ameaças.

![Proteção contra ameaças relatório de status menu suspenso mostrando ' dividir por '.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

Esses modos de exibição oferecem a opção de exportação, por meio de um clique de botão (em phishing de **email** \> **Phish**, malware de **email** \> **Malware**e modos de exibição de malware de **conteúdo** \> **Malware** ). Os dados agregados exportados para o seu computador podem ser abertos no Excel.

![Este gráfico mostra a exportação como uma opção no menu para o modo de exibição de malware, diretamente entre criar agendamento e relatório de solicitação.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

**Observação**: o número máximo de entradas que podem ser exportadas para **phishing** e **Malware** está apenas abaixo de 10000. Se você exportar um modo de exibição, somente as entradas 10000 mais recentes serão exportadas.

Os modos de exibição de visão geral e email exibirão informações em horas de processamento, e não em 24 horas (demanda re. velocidades maiores aqui foram um sinal claro)!

> [!NOTE]
> Um relatório de status de proteção contra ameaças está disponível para clientes que tenham o [Office 365 ATP](office-365-atp.md) ou o [Exchange Online Protection](exchange-online-protection-overview.md)(EOP); no entanto, as informações exibidas no relatório de status de proteção contra ameaças para clientes ATP provavelmente conterão dados diferentes do que os clientes do EOP podem ver. Por exemplo, o relatório de status de proteção contra ameaças para clientes ATP conterá informações sobre [arquivos mal-intencionados detectados no SharePoint Online, no onedrive ou no Microsoft Teams](atp-for-spo-odb-and-teams.md). Essas informações são específicas para a ATP, para que os clientes que tenham o EOP, mas não a ATP, não vejam esses detalhes no relatório de status de proteção contra ameaças.

Para exibir o relatório de status de proteção contra ameaças, no [ &amp; centro de conformidade de segurança](https://protection.office.com), vá para o painel **relatórios** \> **Dashboard** \> **status de proteção contra ameaças**.

![Relatório de status de proteção contra ameaças ATP](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

Para obter o status detalhado de um dia, passe o mouse sobre o gráfico.

![Dados de status de proteção de ameaças ATP por um dia](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

Por padrão, o relatório de status de proteção contra ameaças mostra os dados dos últimos sete dias. No entanto, você pode escolher **filtros** e alterar o intervalo de datas para exibir dados de até 90 dias. (Se estiver usando uma assinatura de avaliação, você poderá estar limitado a 30 dias de dados.)

![Filtros de status de proteção contra ameaças ATP](../../media/4f703369-642b-402b-9758-b9c828283410.png)

Você também pode usar o menu **exibir dados por** para alterar quais informações são exibidas no relatório.

![Opções de exibição do relatório de status de proteção contra ameaças ATP](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a>Relatório de status de proteção de URL

Este relatório é baseado em dados coletados e ameaças detectadas, por clique (enquanto a maioria dos outros relatórios relacionados a ameaças de email são por dados de mensagem). Este relatório foi projetado para mostrar ameaças provenientes de hiperlinks em mensagens de email e documentos, por clique. Há dois modos de exibição:

|||
|---|---|
|URL clique em ação de proteção|Confira o número de URLs bloqueadas, bloqueadas, mas substituídas por um clique em um usuário, substituídas por um clique em um usuário, e permitidas.|
|URL clique por aplicativo|Consulte o aplicativo no qual a URL foi clicada.|
|

Na tabela detalhes, você poderá ver mais informações sobre o clique em tempo e informações do usuário. Por fim, tenha em mente que o relatório de status de proteção de URL mostra a proteção do recurso de links seguros de ATP, para que somente os clientes que tenham habilitados os links seguros de ATP vejam os dados refletidos nesse relatório.

> [!NOTE]
> Este é um *relatório de tendências de proteção*, o que significa que os dados representam tendências em um conjunto de dados maior. Como resultado, os dados no modo de exibição de agregação não estão disponíveis em tempo real aqui, mas os dados no modo de exibição de tabela detalhes são, portanto, você pode ver uma pequena discrepância entre as duas exibições.

## <a name="atp-file-types-report"></a>Relatório de Tipos de Arquivo ATP

O relatório de **tipos de arquivo ATP** mostra o tipo de arquivos detectados como mal-intencionados por [anexos seguros de ATP](atp-safe-attachments.md).

Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para tipos de **Reports** \> **Dashboard** \> **arquivos ATP**de painel de relatórios.

![Relatório de Tipos de Arquivo ATP](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Ao passar o mouse sobre um determinado dia, você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros de ATP](atp-safe-attachments.md) e [ &amp; proteção Antimalware anti-spam](anti-spam-and-anti-malware-protection.md).
  
![Dados de relatório de tipos de arquivo ATP por um dia](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a>Relatório de Disposição de Mensagem ATP

O relatório de **disposição de mensagens ATP** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.

Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para painel de **Reports** \> **Dashboard** \> **mensagens ATP**de painel de relatórios.

![Relatório de disposição de mensagens ATP](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

Ao passar o mouse sobre uma barra no gráfico, você pode ver quais ações foram executadas para o email detectado nesse dia.

![Dados de relatório de disposição de mensagens ATP por dia](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a>Relatórios adicionais para exibir

Além dos relatórios ATP descritos neste artigo, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:

|||
|---|---|
|**Relatório (s)**|**Detalhes**|
|**Navegadores** ou **detecções em tempo real**: (os clientes do plano 2 do Office 365 ATP têm o Explorer; O Office 365 ATP Plan 1 clientes têm detecções em tempo real.|[Explorador de Ameaças (e detecções em tempo real)](threat-explorer.md)|
|**Relatórios de segurança de email**, como um relatório superior de remetentes e destinatários, um relatório de email de falsificação e um relatório de detecções de spam.|[Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança](view-email-security-reports.md)|
|**Rastreamento de URL de links seguros de ATP**: (este é um relatório que você gera usando o PowerShell.) Este relatório mostra os resultados das ações de links seguros de ATP nos últimos sete (7) dias.|[Referência do cmdlet Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|**Resultados de EOP e ATP**: (este é um relatório personalizado que você gera usando o PowerShell). Este relatório contém informações, como o domínio, a data, o tipo de evento, a direção, a ação e a contagem de mensagens.|[Referência do cmdlet Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|**Detecções de EOP e ATP**: (este é um relatório personalizado que você gera usando o PowerShell). Este relatório contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras ameaças potenciais em emails ou arquivos.|[Referência do cmdlet Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Quais permissões são necessárias para exibir os relatórios ATP?

Para exibir e usar os relatórios descritos neste artigo, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.

- Para o centro de conformidade de segurança &amp; , você deve ter uma das seguintes funções atribuídas:

  - Gerenciamento de Organização
  - Administrador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Operador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Leitor de segurança

- Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):

  - Gerenciamento de Organização
  - Gerenciamento de Organização Somente para Exibição
  - Função de Destinatários Somente para Exibição
  - Gerenciamento de Conformidade

Para saber mais, confira os seguintes recursos:

- [Permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md)

- [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não estiverem mostrando dados?

Se você não estiver vendo dados em seus relatórios ATP, verifique se as políticas estão configuradas corretamente. Sua organização deve ter [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) e [políticas de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md) definidos para que a proteção ATP esteja funcionando. Consulte também [anti-spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios e insights no centro de &amp; conformidade de segurança](reports-and-insights-in-security-and-compliance.md)
  
[Criar um cronograma para um relatório no centro de &amp; conformidade de segurança](create-a-schedule-for-a-report.md)

[Configurar e baixar um relatório personalizado no centro de conformidade de segurança &amp;](set-up-and-download-a-custom-report.md)

[Permissões de função (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
