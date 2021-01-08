---
title: Obter o Microsoft Defender para Office 365
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
description: O Microsoft Defender para Office 365 inclui anexos seguros, links seguros, ferramentas anti-phishing avançadas, ferramentas de relatórios e recursos de inteligência de ameaças.
ms.openlocfilehash: 34011780241ae3a669fe32aa5fad00f9836d5570
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780303"
---
# <a name="microsoft-defender-for-office-365"></a>Obter o Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se você estiver usando o Outlook.com, Microsoft 365 Family ou Microsoft 365 Personal, e estiver procurando por informações sobre links ou anexos seguros no Outlook, confira [Segurança avançada do Outlook.com para assinantes do Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

O Microsoft Defender para Office 365 protege sua organização contra ameaças maliciosas representadas por mensagens de email, links (URLs) e ferramentas de colaboração. O Defender for Office 365 inclui:

- **[Políticas de proteção contra ameaças](#configure-microsoft-defender-for-office-365-policies)**: defina políticas de proteção contra ameaças para definir o nível de proteção apropriado para a sua organização.

- **[Relatórios](#view-microsoft-defender-for-office-365-reports)**: Exibi relatórios em tempo real para monitorar o desempenho do Defender for Office 365 na organização.

- **[Recursos de investigação e resposta de ameaças](#use-threat-investigation-and-response-capabilities)**: use as ferramentas de ponta para investigar, compreender, simular e prevenir ameaças.

- **[Recursos de investigação e resposta automatizadas](office-365-air.md)**: poupe tempo e esforço, investigando e reduzindo as ameaças.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Guia interativo para o Microsoft Defender para Office 365
Neste guia interativo, você aprenderá a proteger sua organização com o Microsoft Defender para Office 365. Você verá como o Defender para Office 365 pode ajudar a definir políticas de proteção, analisar ameaças à sua organização e responder a ataques.

> [!VIDEO https://aka.ms/MSDO-IG]

## <a name="getting-started"></a>Introdução

Se você é novo no Microsoft Defender para Office 365 ou aprende melhor *fazendo*, pode se beneficiar dividindo a configuração inicial do Defender para Office 365 em blocos, investigando e visualizando relatórios usando este artigo como referência. Aqui estão os blocos de configuração iniciais lógicos:

- Configure tudo com '*anti*' no nome.
  - anti-malware
  - anti-phishing
  - antispam
- Configure tudo com '*seguro*' no nome.
  - links seguros
  - anexos seguros
- Defenda as cargas de trabalho (por exemplo, SharePoint Online, OneDrive e Teams)
- Proteja com a Limpeza Automática Zero Hora

Para aprender fazendo, [clique neste link](protect-against-threats.md).

> [!NOTE]
> O Microsoft Defender para Office 365 vem em dois tipos de Planos diferentes. Você pode saber se tem o **Plano 1**, se tiver 'Detecções em tempo real', e o **Plano 2**, se tiver o Explorador de Ameaças. O Plano que você possui influencia as ferramentas que você verá, portanto, certifique-se de estar ciente de seu Plano à medida que aprende.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender para Office 365 Plano 1 e Plano 2

A tabela a seguir resume o que está incluído em cada plano.

****

|Plano 1 do Microsoft Defender para Office 365|Plano 2 do Microsoft Defender para Office 365|
|---|---|
|Capacidade de configuração, proteção e detecção: <ul><li>[Anexos Seguros](atp-safe-attachments.md)</li><li>[Links Seguros](atp-safe-links.md)</li><li>[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Anti-phishing no Defender para proteção do Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecções em tempo real](threat-explorer.md)</li></ul>|Recursos do Microsoft Defender para Office 365 Plano 1 <br>---mais---<br> Recursos de automação, investigação, correção e formação educacional:<ul><li>[Controladores de Ameaças](threat-trackers.md)</li><li>[Explorador de Ameaças](threat-explorer.md)</li><li>[Resposta e investigação automatizadas](office-365-air.md)</li><li>[Simulador de Ataque](attack-simulator.md)</li><li>[Modos de Exibição de Campanha](campaigns.md)</li></ul>|
|

- O Microsoft Defender para Office 365 Plano 2 está incluído no Office 365 E5, Office 365 A5, Microsoft 365 E5 Security e Microsoft 365 E5.

- O Microsoft Defender para Office 365 Plano 1 está incluído no Microsoft 365 Business Premium.

- O Microsoft Defender para Office 365 Plano 1 e o Microsoft Defender para Office 365 Plano 2 estão disponíveis como complemento para certas assinaturas. Para saber mais, confira [Disponibilidade de recursos nos planos do Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- O recurso [Documentos Seguros](safe-docs.md) está disponível apenas para usuários com as licenças Microsoft 365 E5 ou Microsoft 365 E5 Security (não incluídas nos planos Microsoft Defender para Office 365).

- Se sua assinatura atual não inclui o Microsoft Defender para Office 365, [entre em contato com a equipe de vendas para iniciar uma avaliação](https://go.microsoft.com/fwlink/p/?LinkId=518644) e confira como o Defender para Office 365 pode funcionar para sua organização.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Configurar politicas do Microsoft Defender para Office 365

Com o Microsoft Defender para Office 365, a equipe de segurança da sua organização pode configurar a proteção definindo políticas no Centro de Conformidade e Segurança (Vá para <https://protection.office.com> \> **Política de gerenciamento de** \> **ameaças**.)

> [!TIP]
> Para obter uma lista rápida de políticas a serem definidas, confira [Proteção contra ameaças](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Políticas do Defender for Office 365

As políticas definidas para a sua organização determinam o comportamento e o nível de proteção das ameaças predefinidas. As opções de política são extremamente flexíveis. Por exemplo, a equipe de segurança da sua organização pode definir a proteção contra ameaças individualizada no nível do usuário, da organização, do destinatário e do domínio. É importante revisar suas políticas regularmente porque novas ameaças e desafios surgem diariamente.

- **[Anexos Seguros ATP](atp-safe-attachments.md)**: fornece proteção de dia zero ao seu sistema de mensagens, verificando anexos de email em busca de conteúdo mal-intencionado. Ele roteia todas as mensagens e os anexos que não têm uma assinatura de vírus/malware em um ambiente especial e, em seguida, usa técnicas de aprendizagem e análise de máquina para detectar tentativas maliciosas. Se nenhuma atividade suspeita for encontrada, a mensagem será encaminhada para a caixa de correio. Para saber mais, confira [Configurar políticas de Anexos Seguros](set-up-atp-safe-attachments-policies.md).

- **[Links Seguros](atp-safe-links.md)**: fornece verificação instantânea das URLs, por exemplo, em mensagens de email e arquivos do Office. A proteção é contínua e se aplica a suas mensagens e ao ambiente do Office. Os links são verificados em cada clique: links seguros permanecem acessíveis e os links mal-intencionados são bloqueados dinamicamente. Para saber mais, confira [Configurar políticas de Links Seguros](set-up-atp-safe-links-policies.md).

- **[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protege sua organização quando os usuários colaboram e compartilham arquivos, identificando e bloqueando arquivos mal-intencionados em sites de equipe e bibliotecas de documentos. Para saber mais, confira [Ativar o Defender para Office 365 para Microsoft Office SharePoint Online, Microsoft OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[Proteção antiphishing no Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: detecta tentativas de usurpar a identidade dos seus usuários e domínios internos ou personalizados. Ela aplica modelos de aprendizagem de computador e algoritmos avançados de detecção de usurpação de identidade para evitar ataques de phishing. Para saber mais, confira [Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Exibir relatórios do Microsoft Defender para Office 365

O Microsoft Defender para Office 365 inclui um [painel de relatórios](view-reports-for-atp.md) avançado para monitorar o desempenho do Defender for Office 365. É possível acessá-lo em **Relatórios** \> **Painel** no Centro de Segurança e Conformidade.

Os relatórios são atualizados em tempo real, fornecendo as informações mais recentes. Esses relatórios também fornecem recomendações e alertam você sobre ameaças iminentes. Os relatórios predefinidos incluem o seguinte:

- [Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)

- [Relatório de status de proteção contra ameaças](view-reports-for-atp.md#threat-protection-status-report)

- [Relatório de tipos de arquivo do Defender for Office 365](view-reports-for-atp.md#defender-for-office-365-file-types-report)

- [Relatório de disposição de mensagens do Defender for Office 365](view-reports-for-atp.md#defender-for-office-365-message-disposition-report)

- ... e muito mais.

## <a name="use-threat-investigation-and-response-capabilities"></a>Como funciona a investigação e a resposta a ameaças

O Microsoft Defender para Office 365 Plano 2 inclui as melhores [ferramentas de investigação e resposta de ameaças](office-365-ti.md) que habilita a equipe de segurança da sua organização para antecipar, entender e evitar ataques maliciosos.

- Os **[rastreadores de ameaças](threat-trackers.md)** oferecem a mais recente inteligência sobre como enfrentar problemas de segurança cibernética. Por exemplo, você pode exibir informações sobre o malware mais recente e executar medidas defensivas antes que ele se torne uma ameaça real à sua organização. Os rastreadores disponíveis incluem [rastreadores notáveis](threat-trackers.md#noteworthy-trackers), [rastreadores de tendências](threat-trackers.md#trending-trackers), [consultas controladas ](threat-trackers.md#tracked-queries) e [consultas salvas](threat-trackers.md#saved-queries).

- O **[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)** (também chamado de Explorador) é um relatório em tempo real que permite identificar e analisar ameaças recentes. Você pode configurar o Explorador para mostrar dados de períodos personalizados.

- O **[Simulador de Ataques](attack-simulator.md)** permite que você execute cenários de ataque realistas em sua organização para identificar vulnerabilidades. As simulações de tipos de ataque atuais estão disponíveis, incluindo ataques de coleta para spear phishing e de anexos, ataques de pulverização de senha e de senha de força bruta.

## <a name="save-time-with-automated-investigation-and-response"></a>Poupe tempo com investigação e resposta automatizadas

(**NOVO!**) Ao investigar um ataque cibernético potencial, o tempo é essencial. Quanto antes você puder identificar e reduzir as ameaças, melhor será sua organização. A[Resposta automatizada a investigação](office-365-air.md)(AIR) inclui um conjunto de medidas de segurança que podem ser iniciadas automaticamente quando um alerta é acionado, ou pode ser iniciadas manualmente a partir de um modo de exibição no Explorador. O AIR pode economizar tempo e esforço da equipe de operações de segurança na redução de ameaças de maneira eficaz e eficiente. Para saber mais, consulte [AIR no Office 365](office-365-air.md).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Permissões necessárias para usar os recursos do Microsoft Defender para Office 365

Para acessar os recursos do Microsoft Defender para Office 365 no Centro de Conformidade e Segurança, você deve receber uma função apropriada. A tabela abaixo fornece alguns exemplos:

|Função ou grupo de funções|Recursos para saber mais|
|---|---|
|administrador global (pode ser atribuído no Azure Active Directory ou no Centro de Conformidade e Segurança)|[Sobre as funções de administrador do Microsoft 365 ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|O Administrador de Segurança (pode ser atribuído tanto no Azure Active Directory quanto no Centro de Conformidade e Segurança)|[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)|
|Gerenciamento de Organização do Exchange Online (atribuído no Exchange Online)|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|Pesquisar e Remover (isso só é atribuído no Centro de Conformidade e Segurança)|[Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)|

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-microsoft-defender-for-office-365"></a>Obter o Microsoft Defender para Office 365

O Microsoft Defender para Office 365 está incluído em certas assinaturas, como Microsoft 365 E5, Office 365 E5, Office 365 A5 e Microsoft 365 Business Premium. Se a sua assinatura não incluir o Defender for Office 365, você pode comprar o Defender for Office 365 Plano 1 ou o Defender for Office 365 Plano 2 como um complemento para certas assinaturas. Para saber mais, confira os seguintes recursos:

- [Disponibilidade do Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para uma lista de assinaturas que incluem os planos Defender for Office 365.

- [Disponibilidade de recursos nos planos do Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obter uma lista de recursos incluídos nos Planos 1 e 2.

- [Obtenha o Microsoft Defender para Office 365 certo](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar planos e adquirir o Defender for Office 365.

- [Comece uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Novos recursos no Microsoft Defender para Office 365

Novos recursos são adicionados ao Microsoft Defender para Office 365 continuamente. Para saber mais, confira os seguintes recursos:

- O [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) fornece uma lista dos novos recursos que estão em desenvolvimento e em implantação.

- A [Descrição do Serviço do Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descreve os recursos e a disponibilidade dos planos do Defender for Office 365.

## <a name="see-also"></a>Confira também

- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

- [Investigação e resposta automatizadas (AIR) no Microsoft 365 Defender](../mtp/mtp-autoir.md)
