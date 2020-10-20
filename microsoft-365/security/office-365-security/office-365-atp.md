---
title: Proteção Avançada contra Ameaças do Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: A Proteção Avançada contra Ameaças do Office 365 inclui anexos seguros, links seguros, ferramentas antiphishing avançadas, ferramentas de relatório e recursos de inteligência de ameaças.
ms.openlocfilehash: 8acf38cc61f2789c407a80200b97269043bab95e
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600512"
---
# <a name="office-365-advanced-threat-protection-atp"></a>Proteção Avançada contra Ameaças do Office 365 (ATP)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se você estiver usando o Outlook.com, Microsoft 365 Family ou Microsoft 365 Personal, e estiver procurando por informações sobre links ou anexos seguros no Outlook, confira [Segurança avançada do Outlook.com para assinantes do Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

A Proteção Avançada contra Ameaças do Office 365 (ATP) protege sua organização contra ameaças maliciosas, que são enviadas por mensagens de email, links (URLs) e ferramentas de colaboração. A ATP inclui:

- **[Políticas de proteção contra ameaças](#configure-atp-policies)**: defina políticas de proteção contra ameaças para definir o nível de proteção apropriado para a sua organização.

- **[Relatórios](#view-office-365-atp-reports)**: exiba relatórios em tempo real para monitorar o desempenho da ATP na sua organização.

- **[Recursos de investigação e resposta de ameaças](#use-threat-investigation-and-response-capabilities)**: use as ferramentas de ponta para investigar, compreender, simular e prevenir ameaças.

- **[Recursos de investigação e resposta automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: poupe tempo e esforço, investigando e reduzindo as ameaças.

## <a name="getting-started"></a>Introdução

Se você é novo na Proteção Avançada contra Ameaças do Office 365 ou aprende melhor *fazendo*, você pode se beneficiar dividindo a configuração inicial do ATP em blocos, investigando e exibindo relatórios usando este artigo como referência. Aqui estão os blocos de configuração iniciais lógicos:

- Configure tudo com '*anti*' no nome.
    - anti-malware
    - anti-phishing
    - antispam
- Configure tudo com '*seguro*' no nome.
    - links seguros
    - anexos seguros
- Defenda as cargas de trabalho (por exemplo, SharePoint Online, OneDrive e Teams) 
- Proteja com a Limpeza Automática Zero Hora

Para aprender fazendo, [clique neste link](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true). 

> [!NOTE]
> A ATP vem em dois tipos de Planos diferentes. Você pode saber se tem o **Plano 1**, se tiver 'Detecções em tempo real', e o **Plano 2**, se tiver o Explorador de Ameaças. O Plano que você possui influencia as ferramentas que você verá, portanto, certifique-se de estar ciente de seu Plano à medida que aprende.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plano 1 e Plano 2

A tabela a seguir resume o que está incluído em cada plano.

****

|Plano 1 do Office 365 ATP |Plano 2 do Office 365 ATP|
|---|---|
|<br/>Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](atp-safe-attachments.md)</li><li>[Links Seguros](atp-safe-links.md)</li><li>[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Proteção antiphishing ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Plano 1 do Office 365 ATP <br/>---mais---<br/>Recursos de automação, investigação, correção e formação educacional:</li><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Simulador de Ataque](attack-simulator.md)</li></ul>|
|

- O Office 365 ATP Plano 2 está incluído no Office 365 E5, Office 365 A5, Microsoft 365 E5 Security e no Microsoft 365 E5.

- O Plano 1 do Office 365 ATP está incluído no Microsoft 365 Business Premium.

- A ATP do plano 1 do Office 365 e a ATP do plano 2 do Office 365 estão disponíveis cada uma como um complemento para determinadas assinaturas. Para saber mais, confira [Disponibilidade de recursos em planos da ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- O recurso [Documentos Seguros](safe-docs.md) só está disponível para usuários com as licenças de segurança da Microsoft 365 E5 ou do Microsoft 365 E5 Security (não incluída nos planos do Office 365 ATP).

- Se sua assinatura atual não incluir o Office 365 ATP, entre em [contato com vendas para iniciar uma avaliação](https://go.microsoft.com/fwlink/p/?LinkId=518644) e veja como o ATP pode funcionar para sua organização.

## <a name="configure-atp-policies"></a>Configurar políticas de ATP

Com o Office 365 ATP, a equipe de segurança da sua organização pode configurar a proteção, definindo políticas no Centro de conformidade segurança (Vá para [https://protection.office.com](https://protection.office.com) > **Política de gerenciamento de ameaças** > ****.)

> [!TIP]
> Para obter uma lista rápida de políticas a serem definidas, confira [Proteção contra ameaças](protect-against-threats.md).

## <a name="advanced-threat-protection-policies"></a>Políticas da Proteção Avançada contra Ameaças

As políticas definidas para a sua organização determinam o comportamento e o nível de proteção das ameaças predefinidas. As opções de política são extremamente flexíveis. Por exemplo, a equipe de segurança da sua organização pode definir a proteção contra ameaças individualizada no nível do usuário, da organização, do destinatário e do domínio. É importante revisar suas políticas regularmente porque novas ameaças e desafios surgem diariamente.

- **[Anexos Seguros ATP](atp-safe-attachments.md)**: fornece proteção de dia zero ao seu sistema de mensagens, verificando anexos de email em busca de conteúdo mal-intencionado. Ele roteia todas as mensagens e os anexos que não têm uma assinatura de vírus/malware em um ambiente especial e, em seguida, usa técnicas de aprendizagem e análise de máquina para detectar tentativas maliciosas. Se nenhuma atividade suspeita for encontrada, a mensagem será encaminhada para a caixa de correio. Para saber mais, confira [Configurar políticas de Anexos Seguros](set-up-atp-safe-attachments-policies.md).

- **[Links Seguros](atp-safe-links.md)**: fornece verificação instantânea das URLs, por exemplo, em mensagens de email e arquivos do Office. A proteção é contínua e se aplica a suas mensagens e ao ambiente do Office. Os links são verificados em cada clique: links seguros permanecem acessíveis e os links mal-intencionados são bloqueados dinamicamente. Para saber mais, confira [Configurar políticas de Links Seguros](set-up-atp-safe-links-policies.md).

- **[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protege sua organização quando os usuários colaboram e compartilham arquivos, identificando e bloqueando arquivos mal-intencionados em sites de equipe e bibliotecas de documentos. Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[Proteção antiphishing da ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: detecta tentativas de usurpar a identidade de seus usuários e domínios internos ou personalizados. Ela aplica modelos de aprendizagem de computador e algoritmos avançados de detecção de usurpação de identidade para evitar ataques de phishing. Para saber mais, confira [Configurar políticas de antiphishing da ATP no Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Visualizar relatórios do Office 365 ATP

O Office 365 ATP inclui um [painel de relatórios ](view-reports-for-atp.md) avançado para monitorar o desempenho da ATP. Você pode acessá-lo em **Relatórios** > **Painel** no Centro de Segurança e Conformidade.

Os relatórios são atualizados em tempo real, fornecendo as informações mais recentes. Esses relatórios também fornecem recomendações e alertam você sobre ameaças iminentes. Os relatórios predefinidos incluem o seguinte:

- [Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)

- [Relatório de status de proteção contra ameaças](view-reports-for-atp.md#threat-protection-status-report)

- [Relatório de tipos de arquivo da proteção avançada contra ameaças](view-reports-for-atp.md#advanced-threat-protection-file-types-report)

- [Relatório de disposição de mensagens da Proteção Avançada contra Ameaças](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- ... e muito mais.

## <a name="use-threat-investigation-and-response-capabilities"></a>Como funciona a investigação e a resposta a ameaças

O Office 365 ATP Plano 2 inclui uma melhor investigação de [ameaças e ferramentas de resposta](office-365-ti.md) que permitem que a equipe de segurança da sua organização facilite, entenda e impeça ataques mal-intencionados.

- Os **[rastreadores de ameaças](threat-trackers.md)** oferecem a mais recente inteligência sobre como enfrentar problemas de segurança cibernética. Por exemplo, você pode exibir informações sobre o malware mais recente e executar medidas defensivas antes que ele se torne uma ameaça real à sua organização. Os rastreadores disponíveis incluem [rastreadores notáveis](threat-trackers.md#noteworthy-trackers), [rastreadores de tendências](threat-trackers.md#trending-trackers), [consultas controladas ](threat-trackers.md#tracked-queries) e [consultas salvas](threat-trackers.md#saved-queries).

- O **[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)** (também chamado de Explorador) é um relatório em tempo real que permite identificar e analisar ameaças recentes. Você pode configurar o Explorador para mostrar dados de períodos personalizados.

- O **[Simulador de Ataques](attack-simulator.md)** permite que você execute cenários de ataque realistas em sua organização para identificar vulnerabilidades. As simulações de tipos de ataque atuais estão disponíveis, incluindo ataques de coleta para spear phishing e de anexos, ataques de pulverização de senha e de senha de força bruta.

## <a name="save-time-with-automated-investigation-and-response"></a>Poupe tempo com investigação e resposta automatizadas

(**NOVO!**) Ao investigar um ataque cibernético potencial, o tempo é essencial. Quanto antes você puder identificar e reduzir as ameaças, melhor será sua organização. A[Resposta automatizada a investigação](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) inclui um conjunto de medidas de segurança que podem ser iniciadas automaticamente quando um alerta é acionado, ou pode ser iniciadas manualmente a partir de um modo de exibição no Explorador. O AIR pode economizar tempo e esforço da equipe de operações de segurança na redução de ameaças de maneira eficaz e eficiente. Para saber mais, consulte [AIR no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).

## <a name="permissions-required-to-use-atp-features"></a>Permissões necessárias para usar os recursos de ATP

Para acessar os recursos de ATP no Centro de Segurança e Conformidade, você deve ter uma função adequada. A tabela abaixo fornece alguns exemplos:

|Função ou grupo de funções|Recursos para saber mais|
|---|---|
|administrador global (pode ser atribuído no Azure Active Directory ou no Centro de Conformidade e Segurança)|[Sobre as funções de administrador do Microsoft 365 ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|O Administrador de Segurança (pode ser atribuído tanto no Azure Active Directory quanto no Centro de Conformidade e Segurança)|[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)|
|Gerenciamento de Organização do Exchange Online (atribuído no Exchange Online)|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|Pesquisar e Remover (isso só é atribuído no Centro de Conformidade e Segurança)|[Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)|

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Obter o Office 365 ATP

O Office 365 ATP está incluído em determinadas assinaturas, como a Microsoft 365 E5, o Office 365 E5, o Office 365 A5 e o Microsoft 365 Business Premium. Se a sua assinatura não inclui o Office 365 ATP, você poderá comprar a ATP Plano 1 ou a ATP Plano 2 como um complemento para determinadas assinaturas. Para saber mais, confira os seguintes recursos:

- [Disponibilidade da Proteção Avançada contra Ameaças (ATP) do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obter uma lista de assinaturas que incluem planos de ATP.

- [Disponibilidade de recursos em planos de Proteção Avançada contra Ameaças (ATP) ](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obter uma lista dos recursos incluídos no Plano 1 e 2.

- [Obter a Proteção Avançada contra Ameaças do Office 365 apropriada ](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar os planos e comprar o Office 365 ATP.

- [Comece uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Experimentar novos recursos no Office 365 ATP

Novos recursos são adicionados ao Office 365 ATP continuamente. Para saber mais, confira os seguintes recursos:

- O [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) fornece uma lista dos novos recursos que estão em desenvolvimento e em implantação.

- A [Descrição do Serviço de Proteção Avançada contra Ameaças do Office 365 ](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descreve os recursos e a disponibilidade oferecidos nos planos ATP.

## <a name="see-also"></a>Confira também

- [Proteção contra Ameaças da Microsoft](../mtp/microsoft-threat-protection.md)

- [Investigação e resposta automatizadas (AIR) na Proteção contra Ameaças da Microsoft](../mtp/mtp-autoir.md)
