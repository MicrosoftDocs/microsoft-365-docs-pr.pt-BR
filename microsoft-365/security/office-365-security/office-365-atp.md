---
title: Proteção Avançada contra Ameaças do Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: A Proteção Avançada contra Ameaças do Office 365 inclui anexos seguros, links seguros, ferramentas antiphishing avançadas, ferramentas de relatório e recursos de inteligência de ameaças.
ms.openlocfilehash: ba7395c29a700039e29c066daa942687e610e4aa
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813761"
---
# <a name="office-365-advanced-threat-protection"></a>Proteção Avançada contra Ameaças do Office 365

> [!IMPORTANT]
> Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se você estiver usando o Outlook.com, o Office 365 Home ou o Office 365 Personal, e estiver procurando por informações sobre links seguros no Outlook, confira [Segurança avançada do Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Visão geral

A Proteção Avançada contra Ameaças do Office 365 (ATP) protege sua organização contra ameaças maliciosas, que são enviadas por mensagens de email, links (URLs) e ferramentas de colaboração. A ATP inclui:

- [Políticas de proteção contra ameaças](#configure-atp-policies): defina políticas de proteção contra ameaças para definir o nível de proteção apropriado para a sua organização. 

- [Relatórios](#view-office-365-atp-reports): exiba relatórios em tempo real para monitorar o desempenho da ATP na sua organização. 

- [Recursos de investigação e resposta de ameaças](#use-threat-investigation-and-response-capabilities): use as ferramentas de ponta para investigar, compreender, simular e prevenir ameaças. 

- [Recursos de resposta automatizada a incidentes](#save-time-with-automated-incident-response): economize tempo e trabalho ao empregar essa ferramenta para investigar e reduzir as ameaças.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plano 1 e Plano 2

A ATP está incluída no Office 365 E5; no entanto, a ATP do Office 365 Plan 1 e a ATP do Office 365 Plan 2 estão disponíveis cada uma como um complemento para determinadas assinaturas. Para saber mais, confira [Disponibilidade de recursos em planos da ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

> [!TIP]
> Se você não possui o Office 365 ATP, você pode [iniciar uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279).


## <a name="configure-atp-policies"></a>Configurar políticas de ATP

Com o Office 365 ATP, a equipe de segurança da sua organização pode configurar as medidas de proteção definindo políticas no Centro de Conformidade e Segurança do Office 365 (vá para [https://protection.office.com](https://protection.office.com) > **Gerenciamento de ameaças** > **Política**.) 

> [!TIP]
> Para obter uma lista rápida de políticas a serem definidas, confira [Proteção contra ameaças](protect-against-threats.md).

As políticas definidas para a sua organização determinam o comportamento e o nível de proteção das ameaças predefinidas. As opções de política são extremamente flexíveis. Por exemplo, a equipe de segurança da sua organização pode definir a proteção contra ameaças individualizada no nível do usuário, da organização, do destinatário e do domínio. É importante revisar suas políticas regularmente porque novas ameaças e desafios surgem diariamente.  

- **[Anexos Seguros ATP](atp-safe-attachments.md)**: fornece proteção de dia zero ao seu sistema de mensagens, verificando anexos de email em busca de conteúdo mal-intencionado. Ele roteia todas as mensagens e os anexos que não têm uma assinatura de vírus/malware em um ambiente especial e, em seguida, usa técnicas de aprendizagem e análise de máquina para detectar tentativas maliciosas. Se nenhuma atividade suspeita for encontrada, a mensagem será encaminhada para a caixa de correio. Para saber mais, confira [Configurar políticas de Anexos Seguros ATP do Office 365](set-up-atp-safe-attachments-policies.md).

- **[Links Seguros ATP](atp-safe-links.md)**: fornece verificação de tempo de clique das URLs, por exemplo, em mensagens de email e arquivos do Office. A proteção é contínua e se aplica a suas mensagens e ao ambiente do Office. Os links são verificados em cada clique: links seguros permanecem acessíveis e os links mal-intencionados são bloqueados dinamicamente. Para saber mais, confira [Configurar políticas de Links Seguros ATP do Office 365](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- **[ATP para SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protege sua organização quando os usuários colaboram e compartilham arquivos, identificando e bloqueando arquivos mal-intencionados em sites de equipe e bibliotecas de documentos. Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- **[Proteção anti-phishing da ATP](atp-anti-phishing.md)**: detecta tentativas de usurpar a identidade de seus usuários e domínios personalizados. Ela aplica modelos de aprendizagem de computador e algoritmos avançados de detecção de usurpação de identidade para evitar ataques de phishing. Para saber mais, confira [ Configurar políticas antiphishing e antiphishing da ATP do Office 365](set-up-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Visualizar relatórios do Office 365 ATP

O Office 365 ATP inclui um [painel de relatórios ](view-reports-for-atp.md) avançado para monitorar o desempenho da ATP. Você pode acessá-lo em **Relatórios** > **Painel** no Centro de Segurança e Conformidade. 

Os relatórios são atualizados em tempo real, fornecendo as informações mais recentes. Esses relatórios também fornecem recomendações e alertam você sobre ameaças iminentes. Os relatórios predefinidos incluem o seguinte: 

- [Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)

- [Relatório de Status da Proteção contra Ameaças](view-reports-for-atp.md#threat-protection-status-report)

- [Relatório de Tipos de Arquivo ATP](view-reports-for-atp.md#atp-file-types-report)

- [Relatório de Disposição de Mensagem ATP](view-reports-for-atp.md#atp-message-disposition-report)

- ... e muito mais. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Como funciona a investigação e a resposta a ameaças

O Office 365 ATP Plano 2 inclui uma melhor investigação de [ameaças e ferramentas de resposta](office-365-ti.md) que permitem que a equipe de segurança da sua organização facilite, entenda e impeça ataques mal-intencionados. 

- Os **[rastreadores de ameaças](threat-trackers.md)** oferecem a mais recente inteligência sobre como enfrentar problemas de segurança cibernética. Por exemplo, você pode exibir informações sobre o malware mais recente e executar medidas defensivas antes que ele se torne uma ameaça real à sua organização. Os rastreadores disponíveis incluem [rastreadores notáveis](threat-trackers.md#noteworthy-trackers), [rastreadores de tendências](threat-trackers.md#trending-trackers), [consultas controladas ](threat-trackers.md#tracked-queries) e [consultas salvas](threat-trackers.md#saved-queries).

- O **[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)** (também chamado de Explorador) é um relatório em tempo real que permite identificar e analisar ameaças recentes. Você pode configurar o Explorador para mostrar dados de períodos personalizados.

- O **[Simulador de Ataques](attack-simulator.md)** permite que você execute cenários de ataque realistas em sua organização para identificar as vulnerabilidades. As simulações de tipos de ataque atuais estão disponíveis, incluindo um [ataque de nome para exibição e spear-phishing](attack-simulator.md#display-name-spear-phishing-attack), um [ataque de pulverização de senha](attack-simulator.md#password-spray-attack), um [ataque de senha de força bruta](attack-simulator.md#brute-force-password-attack), e mais.
    
## <a name="save-time-with-automated-incident-response"></a>Poupe tempo usando a resposta automatizada a incidentes

(**NOVO!**) Ao investigar um ataque cibernético potencial, o tempo é essencial. Quanto antes você puder identificar e reduzir as ameaças, melhor será sua organização. A[Resposta automatizada a incidentes](automated-investigation-response-office.md)(AIR) inclui um conjunto de medidas de segurança que podem ser iniciadas automaticamente quando um alerta é acionado, ou pode ser iniciadas manualmente a partir de um modo de exibição no Explorador. O AIR pode economizar tempo e esforço da equipe de operações de segurança na redução de ameaças de maneira eficaz e eficiente. Para saber mais, consulte [AIR no Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Permissões necessárias para usar os recursos de ATP

Para acessar os recursos de ATP no Centro de Segurança e Conformidade, você deve ter uma função adequada. A tabela abaixo fornece alguns exemplos:

|Função ou grupo de funções  |Recursos para saber mais  |
|---------|---------|
|O Administrador Global do Office 365 (pode ser atribuído no Azure Active Directory ou no Centro de Conformidade e Segurança do Office 365) |[Sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|O Administrador de Segurança (pode ser atribuído no Azure Active Directory ou no Centro de Conformidade e Segurança do Office 365) |[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)|
|Gerenciamento de Organização do Exchange Online (atribuído no Exchange Online)|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|
|Pesquisar e Remover (só está atribuído no Centro de Conformidade e Segurança do Office 365) |[Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md) |

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Obter o Office 365 ATP

O Office 365 ATP está incluído em determinadas assinaturas, como as do Microsoft 365 E5, do Office 365 E5, do Office 365 A5 e do Microsoft 365 Business. Se a sua assinatura não inclui o Office 365 ATP, você poderá comprar a ATP Plano 1 ou a ATP Plano 2 como um complemento para determinadas assinaturas. Para saber mais, confira os seguintes recursos:

- [Disponibilidade da Proteção Avançada contra Ameaças (ATP) do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obter uma lista de assinaturas que incluem planos de ATP.

- [Disponibilidade de recursos em planos de Proteção Avançada contra Ameaças (ATP) ](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obter uma lista dos recursos incluídos no Plano 1 e 2.

- [Obter a Proteção Avançada contra Ameaças do Office 365 apropriada ](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar os planos e comprar o Office 365 ATP.

- [Comece uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Experimentar novos recursos no Office 365 ATP

Novos recursos são adicionados ao Office 365 ATP continuamente. Para saber mais, confira os seguintes recursos:

- O [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) fornece uma lista dos novos recursos que estão em desenvolvimento e em implantação.

- A [Descrição do Serviço de Proteção Avançada contra Ameaças do Office 365 ](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descreve os recursos e a disponibilidade oferecidos nos planos ATP.
