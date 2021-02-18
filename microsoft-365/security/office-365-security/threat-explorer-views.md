---
title: Exibições no Explorador de Ameaças e detecções em tempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como usar o Explorador de Ameaças e o relatório de detecções em tempo real para investigar e responder a ameaças no Centro de Conformidade e Segurança & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290280"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Exibições no Explorador de Ameaças e detecções em tempo real

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


![Explorador de Ameaças](../../media/ThreatExplorerFirstOpened.png)

[O Explorador de](threat-explorer.md) Ameaças (e o relatório de detecções em tempo & real) é uma poderosa ferramenta quase em tempo real para ajudar as equipes de Operações de Segurança a investigar e responder a ameaças no Centro de Conformidade e Segurança. O Explorer (e o relatório de detecções em tempo real) exibe informações sobre malware e phishing suspeitos em emails e arquivos no Office 365, bem como outras ameaças de segurança e riscos à sua organização.

- Se você tiver [o Microsoft Defender para Office 365](office-365-atp.md) Plano 2, terá o Explorer.
- Se você tiver o Microsoft Defender para Office 365 Plano 1, terá detecções em tempo real.

Quando você abre o Explorer pela primeira vez (ou o relatório de detecções em tempo real), a exibição padrão mostra detecções de malware de email dos últimos 7 dias. Esse relatório também pode mostrar detecções do Microsoft Defender for Office 365, como URLs mal-intencionadas detectadas por [Links](atp-safe-links.md)seguros e arquivos mal-intencionados detectados por [Anexos Seguros.](atp-safe-attachments.md) Esse relatório pode ser modificado para mostrar dados dos últimos 30 dias (com uma assinatura paga do Microsoft Defender para Office 365 P2). As assinaturas de avaliação incluirão dados apenas dos últimos sete dias.

****

|Assinatura|Utilitário|Dias de Dados|
|---|---|---|
|Avaliação do Microsoft Defender para Office 365 P1|Detecções em tempo real|7 |
|Microsoft Defender para Office 365 P1 pago|Detecções em tempo real|30|
|Teste pago do Microsoft Defender para Office 365 P1 Defender para avaliação do Office 365 P2|Explorador de Ameaças|7 |
|Avaliação do Microsoft Defender para Office 365 P2|Explorador de Ameaças|7 |
|Microsoft Defender para Office 365 P2 pago|Explorador de Ameaças|30|
|

Use o menu **Exibir** para alterar quais informações são exibidas. As dicas de ferramentas ajudam a determinar qual exibição usar.

![Menu Exibir Explorador de Ameaças](../../media/ThreatExplorerViewMenu.png)

Depois de selecionar uma exibição, você pode aplicar filtros e configurar consultas para realizar análises posteriores. As seções a seguir fornecem uma breve visão geral dos vários visualizações disponíveis no Explorer (ou detecções em tempo real).

## <a name="email--malware"></a>Email > Malware

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Malware de Email.** \>  Esta exibição mostra informações sobre mensagens de email que foram identificadas como contendo malware.

![Exibir dados sobre email identificados como malware](../../media/ExplorerEmailMalwareMenu.png)

Clique **em Remetente para** abrir sua lista de opções de exibição. Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, assunto, tecnologia de detecção, status de proteção e muito mais.

Por exemplo, para ver quais ações foram tomadas em mensagens de email detectadas, escolha **o status proteção** na lista. Selecione uma opção e clique no botão Atualizar para aplicar esse filtro ao relatório.

![Opções de Status da Proteção contra Ameaças para o Explorador de Ameaças](../../media/ThreatExplorerProtectionStatusOptions.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens específicas. Quando você seleciona um item na lista, um painel de subslagem é aberto, onde você pode saber mais sobre o item selecionado.

![Explorador de Ameaças com o flyout aberto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>Phishing > email

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Phishing de Email.** \>  Esta exibição mostra mensagens de email identificadas como tentativas de phishing.

![Exibir dados sobre email identificados como tentativas de phishing](../../media/ThreatExplorerEmailPhish.png)

Clique **em Remetente para** abrir sua lista de opções de exibição. Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, IP do remetente, domínio da URL, veredito de clique e muito mais.

Por exemplo, para ver quais ações foram tomadas quando as pessoas clicaram  em URLs identificadas como tentativas de phishing, escolha Clique em veredito na lista, selecione uma ou mais opções e clique no botão Atualizar.

![Opções de veredito de clique para o relatório de phishing](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens específicas, cliques de URL, URLs e origem do email.

![URLs detectadas como phishing em mensagens de email](../../media/ThreatExplorerEmailPhishURLs.png)

Quando você seleciona um item na lista, como uma URL que foi detectada, um painel de subsalto é aberto, onde você pode saber mais sobre o item selecionado.

![Detalhes sobre uma URL detectada](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>Envios > email

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \>  \> **Envios de Email.** Esta exibição mostra emails que os usuários relataram como lixo eletrônico, não lixo eletrônico ou phishing.

![Mensagens de email relatadas por usuários](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Clique **em Remetente para** abrir sua lista de opções de exibição. Use essa lista para exibir informações por remetente, destinatários, tipo de relatório (determinação do usuário de que o email era lixo eletrônico, não lixo eletrônico ou phishing) e muito mais.

Por exemplo, para exibir informações sobre mensagens de email que foram relatadas como tentativas de phishing, clique em **Tipo** de Relatório de Remetente, selecione \>  **Phishing** e clique no botão Atualizar.

![Phish selected for Report Type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como linha de assunto, endereço IP do remetente, o usuário que relatou a mensagem como lixo eletrônico, não lixo eletrônico ou phishing e muito mais.

![Mensagens que foram relatadas como tentativas de phishing](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selecione um item na lista para exibir detalhes adicionais.

## <a name="email--all-email"></a>Email > Todos os emails

Para exibir esse relatório, no Explorer, escolha **Exibir** \> **Email** \> **Todos os emails.** Esse modo de exibição mostra uma exibição totalmente atualizada da atividade de email, incluindo emails identificados como mal-intencionados devido a phishing ou malware, bem como todos os emails não mal-intencionados (emails normais, spam e emails em massa).

> [!NOTE]
> Se você receber um erro que lê Dados demais para **exibir,** adicione um filtro e, se necessário, restrição do intervalo de datas que você está exibindo.

Para aplicar um filtro, escolha **Remetente,** selecione um item na lista e clique no botão Atualizar. No nosso exemplo, utilizamos a **tecnologia de detecção** como um filtro (há várias opções disponíveis). Exibir informações por remetente, domínio do remetente, destinatários, assunto, nome de arquivo de anexo, família de malware, status de proteção (ações tomadas pelos recursos e políticas de proteção contra ameaças no Office 365), tecnologia de detecção (como o malware foi detectado) e muito mais.

![Exibir dados sobre emails detectados pela tecnologia de detecção](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como linha de assunto, destinatário, remetente, status e assim por diante.

## <a name="content--malware"></a>Malware > conteúdo

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir** \> **Malware de** \> **Conteúdo.** Esta exibição mostra arquivos que foram identificados como mal-intencionados pelo [Microsoft Defender para Office 365 no SharePoint Online, OneDrive for Business e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Exibir informações por família de malware, tecnologia de detecção (como o malware foi detectado) e carga de trabalho (OneDrive, SharePoint ou Teams).

![Exibir dados sobre malware detectado](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Abaixo do gráfico, veja mais detalhes sobre arquivos específicos, como nome de arquivo do anexo, carga de trabalho, tamanho do arquivo, quem modificou o arquivo pela última vez e muito mais.

## <a name="click-to-filter-capabilities"></a>Recursos de clique para filtrar

Com o Explorer (e detecções em tempo real), você pode aplicar um filtro em um clique. Clique em um item na legenda e esse item se tornará um filtro para o relatório. Por exemplo, suponha que estamos olhando para o exibição malware no Explorer:

![Ir para o Explorador de Gerenciamento de \> Ameaças](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Clicar no **detonação da ATP** neste gráfico resulta em uma exibição como esta:

![Explorer filtrado para exibir apenas os resultados de detonação do Defender para Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

Neste ponto de vista, agora estamos analisando dados de arquivos que foram acionadas por [Anexos Seguros.](atp-safe-attachments.md) Abaixo do gráfico, podemos ver detalhes sobre mensagens de email específicas que tinham anexos detectados por Anexos Seguros.

![Detalhes específicos sobre mensagens de email com anexos detectados](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Selecionar um ou mais itens ativa **o** menu Ações, que oferece várias opções para escolher para os itens selecionados.

![Selecionar um item ativa o menu Ações](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

A capacidade de filtrar em um clique e navegar até detalhes específicos pode economizar muito tempo na investigação de ameaças.

## <a name="queries-and-filters"></a>Consultas e filtros

O Explorer (bem como o relatório de detecções em tempo real) tem vários filtros poderosos e recursos de consulta que permitem detalhar detalhes, como principais usuários direcionados, principais famílias de malware, tecnologia de detecção e muito mais. Cada tipo de relatório oferece várias maneiras de exibir e explorar dados.

> [!IMPORTANT]
> Não use caracteres curinga, como um asterisco ou um ponto de interrogação, na barra de consulta do Explorer (ou detecções em tempo real). Quando você pesquisa  mensagens de email no campo Assunto, o Explorer (ou detecções em tempo real) executa a correspondência parcial e produz resultados semelhantes a uma pesquisa curinga.
