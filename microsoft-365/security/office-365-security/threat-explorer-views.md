---
title: Modos de exibição no Gerenciador de ameaças e detecções em tempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como usar o Gerenciador de ameaças e o relatório de detecções em tempo real para investigar e responder a ameaças no centro de &amp; conformidade de segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 75286b3fa8319afc9baadbc7ed349e8fe689d11c
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447126"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Modos de exibição no Gerenciador de ameaças e detecções em tempo real

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Explorador de Ameaças](../../media/ThreatExplorerFirstOpened.png)

O [Gerenciador de ameaças](threat-explorer.md) (e o relatório de detecções em tempo real) é uma ferramenta poderosa e quase em tempo real para ajudar as equipes de operações de segurança a investigar e responder a ameaças no centro de conformidade de segurança &amp; . O Explorer (e o relatório de detecções em tempo real) exibe informações sobre o malware e phishing suspeitos em emails e arquivos no Office 365, bem como outras ameaças e riscos de segurança à sua organização.

- Se você tiver o [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) plano 2, você terá o Explorer.
- Se você tiver o Office 365 ATP Plan 1, então você tem detecções em tempo real.

Quando você abre o primeiro Explorer (ou o relatório de detecções em tempo real), o modo de exibição padrão mostra as detecções de malware de email dos últimos 7 dias. Este relatório também pode mostrar detecções de ATP, como URLs mal-intencionadas detectadas por [links seguros](atp-safe-links.md)e arquivos mal-intencionados detectados por [anexos seguros](atp-safe-attachments.md). Esse relatório pode ser modificado para mostrar dados nos últimos 30 dias (com uma assinatura paga do ATP P2). As assinaturas de avaliação incluirão dados apenas nos últimos sete dias.

****

|Assinatura|Utilitário|Dias de dados|
|---|---|---|
|Avaliação da ATP P1|Detecções em tempo real|7 |
|ATP P1 pago|Detecções em tempo real|até|
|ATP P1 pago teste avaliação ATP P2|Explorador de Ameaças|7 |
|Avaliação ATP P2|Explorador de Ameaças|7 |
|ATP P2 pago|Explorador de Ameaças|até|
|

Use o menu **Exibir** para alterar as informações que são exibidas. As dicas de ferramentas ajudam a determinar o modo de exibição a ser usado.

![Menu Exibir do explorador de ameaças](../../media/ThreatExplorerViewMenu.png)

Depois de selecionar um modo de exibição, você pode aplicar filtros e configurar consultas para realizar mais análises. As seções a seguir fornecem uma breve visão geral dos vários modos de exibição disponíveis no Explorer (ou detecções em tempo real).

## <a name="email--malware"></a>Malware de > de email

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir**  >  **Email**  >  **malware**de email. Este modo de exibição mostra informações sobre mensagens de email identificadas como contendo malware.

![Exibir dados sobre email identificados como malware](../../media/ExplorerEmailMalwareMenu.png)

Clique em **remetente** para abrir a lista de opções de exibição. Use essa lista para exibir dados por remetente, destinatários, domínio do remetente, assunto, tecnologia de detecção, status de proteção e muito mais.

Por exemplo, para ver quais ações foram executadas nas mensagens de email detectadas, escolha o **status de proteção** na lista. Selecione uma opção e, em seguida, clique no botão atualizar para aplicar esse filtro ao relatório.

![Opções de status de proteção contra ameaças para o explorador de ameaças](../../media/ThreatExplorerProtectionStatusOptions.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens específicas. Quando você seleciona um item na lista, um painel de saída é aberto, onde você pode saber mais sobre o item que você selecionou.

![Gerenciador de ameaças com submenu aberto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>Phishing > Phish

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir**  >  **Email**  >  **phishing**de email. Este modo de exibição mostra mensagens de email identificadas como tentativas de phishing.

![Exibir dados sobre email identificados como tentativas de phishing](../../media/ThreatExplorerEmailPhish.png)

Clique em **remetente** para abrir a lista de opções de exibição. Use esta lista para exibir dados por remetente, destinatários, domínio do remetente, IP do remetente, domínio da URL, clique em veredicto e muito mais.

Por exemplo, para ver que ações foram executadas quando pessoas clicaram nas URLs que foram identificadas como tentativas de phishing, escolha **clicar em veredicto** na lista, selecione uma ou mais opções e clique no botão atualizar.

![Clique em opções do veredicto para o relatório de phishing](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens específicas, cliques de URL, URLs e origem de email.

![URLs detectadas como Phish em mensagens de email](../../media/ThreatExplorerEmailPhishURLs.png)

Quando você seleciona um item na lista, como uma URL que foi detectada, um painel de saída é aberto, onde você pode saber mais sobre o item que você selecionou.

![Detalhes sobre uma URL detectada](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>Envios de > de email

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir**  >  **Email**  >  **envios**de email. Este modo de exibição mostra o email que os usuários relataram como lixo eletrônico, não lixo eletrônico ou email de phishing.

![Mensagens de email relatadas por usuários](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Clique em **remetente** para abrir a lista de opções de exibição. Use esta lista para exibir informações por remetente, destinatários, tipo de relatório (a determinação do usuário de que o email era lixo eletrônico, não lixo eletrônico ou Phish) e muito mais.

Por exemplo, para exibir informações sobre mensagens de email relatadas como tentativas de phishing **Sender**, clique em  >  **tipo de relatório**do remetente, selecione **phishing**e clique no botão atualizar.

![Phishing selecionado para o filtro de tipo de relatório](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como a linha de assunto, o endereço IP do remetente, o usuário que informou a mensagem como lixo eletrônico, não lixo eletrônico ou Phish e muito mais.

![Mensagens relatadas como tentativas de phishing](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selecione um item na lista para exibir detalhes adicionais.

## <a name="email--all-email"></a>Email > todos os emails

Para exibir esse relatório, no Explorer, escolha **Exibir**  >  **email**  >  **todos os emails**. Este modo de exibição mostra uma visão detalhada da atividade de email, incluindo emails identificados como mal-intencionados devido a phishing ou malware, bem como todos os emails não-mal-intencionados (emails, spam e emails em massa normais).

> [!NOTE]
> Se você receber um erro que leia **muitos dados a serem exibidos**, adicione um filtro e, se necessário, restrinja o intervalo de datas que você está exibindo.

Para aplicar um filtro, escolha **remetente**, selecione um item na lista e clique no botão atualizar. No nosso exemplo, usamos a **tecnologia de detecção** como um filtro (há várias opções disponíveis). Exibir informações por remetente, domínio do remetente, destinatários, assunto, nome do arquivo de anexo, família de malware, status de proteção (ações executadas por seus recursos e políticas de proteção contra ameaças no Office 365), tecnologia de detecção (como o malware foi detectado) e muito mais.

![Exibir dados sobre o email detectado por tecnologia de detecção](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Abaixo do gráfico, veja mais detalhes sobre mensagens de email específicas, como linha de assunto, destinatário, remetente, status e assim por diante.

## <a name="content--malware"></a>Malware de > de conteúdo

Para exibir esse relatório, no Explorer (ou detecções em tempo real), escolha **Exibir**  >  **Content**  >  **malware**de conteúdo. Este modo de exibição mostra arquivos que foram identificados como mal-intencionados pela [proteção avançada contra ameaças do Office 365 no SharePoint Online, no onedrive for Business e no Microsoft Teams](atp-for-spo-odb-and-teams.md).

Exibir informações pela família de malware, tecnologia de detecção (como o malware foi detectado) e carga de trabalho (OneDrive, SharePoint ou Teams).

![Exibir dados sobre malware detectado](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Abaixo do gráfico, veja mais detalhes sobre arquivos específicos, como o nome do arquivo anexo, carga de trabalho, tamanho do arquivo, que modificou o arquivo e muito mais.

## <a name="click-to-filter-capabilities"></a>Recursos de clique para filtrar

Com o Explorer (e detecções em tempo real), você pode aplicar um filtro em um clique. Clique em um item na legenda e esse item se torna um filtro para o relatório. Por exemplo, vamos supor que estamos examinando o modo de exibição de malware no Explorer:

![Vá para o Gerenciador de gerenciamento de ameaças \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Clicar em **acionamento ATP** neste gráfico resultará em um modo de exibição como este:

![Explorer filtrado para exibir somente os resultados de acionamento ATP](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

Neste modo de exibição, agora estamos examinando dados para arquivos que foram destruídodos por [anexos seguros](atp-safe-attachments.md). Abaixo do gráfico, podemos ver detalhes sobre mensagens de email específicas que tinham anexos detectados por anexos seguros.

![Detalhes específicos sobre mensagens de email com anexos detectados](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Selecionar um ou mais itens ativa o menu **ações** , que oferece várias opções de escolha para os itens selecionados.

![Selecionar um item ativa o menu ações](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

A capacidade de filtrar em um clique e navegar para detalhes específicos pode poupar muito tempo na investigação de ameaças.

## <a name="queries-and-filters"></a>Consultas e filtros

O Explorer (bem como o relatório de detecções em tempo real) tem vários filtros e recursos de consulta avançados que permitem detalhar detalhes, como os principais usuários direcionados, principais famílias de malware, tecnologia de detecção e muito mais. Cada tipo de relatório oferece várias maneiras de exibir e explorar dados.

> [!IMPORTANT]
> Não use caracteres curinga, como um asterisco ou um ponto de interrogação, na barra de consulta para o Explorer (ou detecções em tempo real). Quando você pesquisa o **campo assunto** de mensagens de email, Explorer (ou detecções em tempo real) executará a correspondência parcial e produzirá resultados similares a uma pesquisa curinga.
