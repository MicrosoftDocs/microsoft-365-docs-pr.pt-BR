---
title: Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Saiba como localizar e usar relatórios de segurança de email da sua organização. Relatórios de segurança de email estão disponíveis no &amp; centro de conformidade de segurança.
ms.openlocfilehash: 70eceb8d7afa227027b71d475aa22b2151f2dea6
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112295"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança

Vários relatórios estão disponíveis no [centro de conformidade de &amp; segurança](https://protection.office.com) para ajudá-lo a ver como os recursos de segurança de email, como os recursos antispam, Antimalware e de criptografia no Office 365 estão protegendo sua organização. Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de conformidade &amp; de segurança acessando o **painel**de **relatórios** \> .
  
![Painel em que você vê como a proteção avançada contra ameaças está funcionando](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Os relatórios de segurança de email incluem o seguinte:
- [Relatório de criptografia](#encryption-report) (novo!)
- [Relatório de Status da Proteção contra Ameaças](#threat-protection-status-report) 
- [Relatório de detecções de malware](#malware-detections-report) 
- [Relatório de malware superior](#top-malware-report)
- [Relatório de principais remetentes e destinatários](#top-senders-and-recipients-report)
- [Relatório de detecções falsas](#spoof-detections-report)
- [Relatório de detecções de spam](#spam-detections-report)
- [Relatório de email enviado e recebido](#sent-and-received-email-report)
- [Relatório de mensagens relatadas pelo usuário](#user-reported-messages-report)
    
## <a name="encryption-report"></a>Relatório de criptografia

(**Novo!**) O **relatório de criptografia** mostra informações sobre as mensagens de email que foram criptografadas, seja por meio das políticas da sua organização ou por meio de controles de usuário final. A equipe de segurança da sua organização pode usar informações neste relatório para identificar padrões e aplicar proativamente ou ajustar políticas para mensagens de email confidenciais.

Para exibir esse relatório, no centro de conformidade & de segurança, vá para **relatório de criptografia**de **painel** \> de **relatórios** \> .

![Relatório de criptografia](../media/encryptionreport-defaultview.png) 

Quando o relatório for aberto pela primeira vez, você verá dados sobre os métodos de criptografia usados em mensagens de email dos últimos sete (7) dias. Você pode alterar o intervalo de datas e os detalhes que são exibidos no relatório clicando em **filtros** no canto superior direito da tela.

![Filtros de relatório de criptografia](../media/encryptionreport-filters.png)   

Você também pode usar o menu **dividir por** para exibir dados por modelo de criptografia (ou método).

![Método ou modelo de criptografia](../media/encryptionreport-breakdownby.png)

E você pode usar o menu **exibir dados por** para alterar o modo de exibição para ver as contagens de mensagens criptografadas para os cinco domínios de destinatários principais.

![Dados de exibição do relatório de criptografia por menu](../media/encryptionreport-viewdataby.png)

Com a flexibilidade do novo relatório de criptografia, você pode exibir tendências e tomar as ações apropriadas. Por exemplo, se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso. (Para obter ajuda com isso, consulte [definir regras de fluxo de email para criptografar mensagens de email no Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Como outro exemplo, se você tiver vários modelos de criptografia disponíveis, mas nenhum estiver usando, você poderá explorar se os usuários precisam de treinamento para esse recurso. 

Use este relatório permite que a equipe de segurança e conformidade da sua organização monitore a forma como a criptografia de mensagens está sendo usada e se as ações serão necessárias. Para saber mais sobre criptografia, confira [criptografia de email no Office 365](../../compliance/email-encryption.md).

## <a name="threat-protection-status-report"></a>Relatório de Status da Proteção contra Ameaças

O relatório de **status de proteção contra ameaças** é um relatório inteligente que mostra emails mal-intencionados que foram detectados e bloqueados pela proteção do Exchange Online. Este relatório é útil para exibir emails identificados como malware ou uma tentativa de phishing ao longo do tempo (até 90 dias) e permite que administradores de segurança identifiquem tendências ou determinem se as políticas precisam de ajustes.

> [!NOTE]
> Um relatório de status de proteção contra ameaças está disponível para clientes que tenham o [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) ou o [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); no entanto, as informações exibidas no relatório de status de proteção contra ameaças para clientes ATP provavelmente conterão dados diferentes do que os clientes do EOP podem ver. Por exemplo, os clientes do EOP podem exibir informações sobre malware detectado no email, mas não informações sobre [arquivos mal-intencionados detectados no SharePoint Online, no onedrive ou no Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), um recurso específico de ATP. ([Saiba mais sobre os relatórios de ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para o **painel** \> **relatórios** \> **status de proteção contra ameaças**.
  
![Relatório de Status da Proteção contra Ameaças](../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
Quando você abre o relatório de status de proteção contra ameaças pela primeira vez, o relatório mostra os dados dos últimos sete dias por padrão; no entanto, você pode clicar em **filtros** e alterar o intervalo de datas para até 90 dias de detalhes. (Se estiver usando uma assinatura de avaliação, você poderá estar limitado a 30 dias de dados.)

Este relatório é útil para ver a eficácia e o impacto dos recursos de [proteção do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)da sua organização e para tendência de longo prazo. 
  
![Filtros de relatório de status de proteção contra ameaças](../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
Você também pode escolher se deseja exibir dados para emails identificados como mal-intencionados, emails identificados como tentativas de phishing ou emails identificados como contendo malware.
  
![Opções de exibição do relatório de status de proteção contra ameaças](../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>Relatório de detecções de malware

O relatório de **detecções de malware** mostra quantas mensagens de entrada e saída foram detectadas como contendo malware para sua organização. 
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatórios de **malware**de **painel** \> de **relatórios** \> .
  
![Exemplo de relatório de detecções de malware](../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
Semelhante a outros relatórios, como o [relatório de status de proteção contra ameaças](#threat-protection-status-report), o relatório exibe dados dos últimos sete dias por padrão. No entanto, você pode escolher **filtros** para alterar o intervalo de datas. 
  
## <a name="top-malware-report"></a>Relatório de malware superior

O relatório de **malware superior** mostra os vários tipos de malware detectados pelo [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features). 
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para **painel** \> de **relatórios** \> de **malware superior**.
  
![Malware EOP superior](../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.
  
Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.
  
![Este relatório mostra o malware superior detectado para sua organização](../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
Abaixo do gráfico, você verá uma lista de malware detectado e quantas mensagens foram detectadas como tendo esse malware.
  
## <a name="top-senders-and-recipients-report"></a>Relatório de principais remetentes e destinatários

O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes de email. 
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para **painel** \> de **relatórios** \> **principais remetentes e destinatários**.
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> painel \> de relatórios principais remetentes e destinatários](../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.
  
Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.
  
Use a lista **Mostrar dados de** para escolher se deseja exibir dados para os remetentes principais, receptores, destinatários de spam e destinatários de malware. Você também pode ver quem recebeu o malware que foi detectado pela [proteção do Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop). 
  
![Use a lista Mostrar dados para exibir informações específicas](../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
Abaixo do gráfico, você verá quem os principais remetentes ou destinatários de emails foram, juntamente com uma contagem de mensagens enviadas ou recebidas pelo período de tempo especificado.
  
## <a name="spoof-detections-report"></a>Relatório de detecções falsas

O relatório de **detecções falsas** mostra quantas mensagens de email de falsificação foram detectadas, e dessas, quais foram consideradas "boas" (emails falsos realizados por motivos de negócios legítimos). 
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatório de **falsificação**de **painel** \> de **relatórios** \> .
  
![No centro de &amp; conformidade de segurança, vá para \> o \> painel relatórios email de spoof](../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
Ao passar o mouse sobre um dia no gráfico, você pode ver quantas mensagens de email de falsificação foram recebidas.
  
Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório. Para saber mais sobre proteção contra falsificação, confira [proteção contra falsificação no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).
  
## <a name="spam-detections-report"></a>Relatório de detecções de spam

O relatório **detecções de spam** mostra todo o conteúdo de spam bloqueado pelo Exchange Online. As mensagens são contadas por mensagem e não por destinatário. Por exemplo, se uma mensagem de email foi enviada a 100 destinatários em sua organização, ela será contada como uma mensagem.
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para relatórios de **spam**de **painel** \> de **relatórios** \> .
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> painel \> de relatórios EOP detecções de spam](../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
Ao passar o mouse sobre um dia no gráfico, você pode ver quantos itens foram bloqueados naquele dia, bem como os itens são categorizados. Por exemplo, você pode ver quantas mensagens de spam foram filtradas e quantos itens vieram de um endereço IP bloqueado.
  
Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.
  
![O relatório de detecções de spam informa quantas mensagens de spam foram bloqueadas ou filtradas](../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
Abaixo do gráfico, você verá uma lista de itens de spam que foram detectados. Selecione um item para exibir informações adicionais, como se o item de spam era de entrada ou de saída, sua ID de mensagem e seu destinatário. Para saber mais sobre proteção antispam, confira [proteção antispam de email do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).
  
## <a name="sent-and-received-email-report"></a>Relatório de email enviado e recebido

O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom". 
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), vá para o **painel** \> **relatórios** \> **enviado e recebido emails**.
  
![Para exibir esse relatório, no centro de &amp; conformidade de segurança, vá para \> o \> painel relatórios enviado e recebido email](../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
Ao passar o mouse sobre um dia no gráfico, você pode ver quantas mensagens vieram e como essas mensagens são categorizadas. Por exemplo, você pode ver quantas mensagens foram detectadas como contendo malware e quantas foram identificadas como spam.
  
Clique (ou toque) no relatório para abri-lo em uma nova janela do navegador, onde você pode obter uma visão mais detalhada do relatório.
  
Você pode usar a lista **dividir por** para exibir informações por tipo ou por direção (entrada e saída). 
  
![Use a lista dividir por para exibir informações por tipo ou direção](../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
Abaixo do gráfico, você verá uma lista de categorias de email, como **GoodMail**, **SpamContentFiltered**e assim por diante. Selecione uma categoria para exibir informações adicionais, como ações que foram tomadas para malware e se o email era de entrada ou saída.
  
![Este relatório informa sobre o anti-malware, antispam e outras detecções de mensagens](../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

Para saber mais sobre inteligência de email, consulte [inteligência de fluxo de emails no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).
  
## <a name="user-reported-messages-report"></a>Relatório de mensagens relatadas pelo usuário

O relatório de **mensagens relatadas pelo usuário** mostra informações sobre as mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails de boa qualidade usando o [suplemento de mensagem de relatório](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).
  
Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, como uma exceção de política de spam ou uma regra de fluxo de email configurada para sua organização. Para exibir detalhes, selecione um item na lista relatórios do usuário e, em seguida, exiba as informações nas guias **Resumo** e **detalhes** . 
  
![O relatório mensagens relatadas pelo usuário mostra as mensagens que os usuários rotularam como lixo eletrônico, não lixo eletrônico ou tentativas de phishing.](../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
Para exibir esse relatório, no [centro de &amp; conformidade de segurança](https://protection.office.com), siga um destes procedimentos:
  
- Vá para o **painel** \> **Gerenciamento** \> **de ameaças mensagens relatadas pelo usuário**.
    
- Vá para **Gerenciamento** \> de ameaças **revise** \> **mensagens relatadas pelo usuário**.
    
![No centro de &amp; conformidade de segurança, escolha revisão \> \> de gerenciamento de ameaças mensagens relatadas pelo usuário](../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> Para que o relatório de mensagens relatadas pelo usuário funcione corretamente, o **log de auditoria deve estar ativado** para o seu ambiente do Office 365. Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online. Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria do Office 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off). 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quais permissões são necessárias para exibir esses relatórios?

Para exibir e usar os relatórios descritos neste artigo, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.

- Para o centro &amp; de conformidade de segurança, você deve ter uma das seguintes funções atribuídas:
    - Gerenciamento de Organização
    - Administrador de segurança (isso pode ser atribuído no centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()
    - Leitor de segurança

- Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Gerenciamento de Organização
    - Gerenciamento de Organização Somente para Exibição
    - Função de Destinatários Somente para Exibição
    - Gerenciamento de Conformidade

Para saber mais, confira os seguintes recursos:

- [Permissions in the Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não estiverem mostrando dados?

Se você não estiver vendo dados nos seus relatórios, verifique se as suas políticas estão configuradas corretamente. Para saber mais, confira [proteger contra ameaças no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
  
## <a name="related-topics"></a>Tópicos relacionados

[Proteção anti-spam de emails do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[Relatórios e insights no centro de conformidade de &amp; segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[Criar um cronograma para um relatório no centro de &amp; conformidade de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[Configurar e baixar um relatório personalizado no centro de conformidade &amp; de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

