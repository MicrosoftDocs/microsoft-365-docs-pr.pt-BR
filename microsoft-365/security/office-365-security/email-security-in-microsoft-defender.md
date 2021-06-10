---
title: Segurança de email com o Explorador de Ameaças no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Exibir e investigar tentativas de phishing de malware.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877891"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Segurança de email com o Explorador de Ameaças no Microsoft Defender para Office 365

Neste artigo:

- [Exibir malware detectado no email](#view-malware-detected-in-email)
- [Exibir URL de phishing e clicar em dados de veredito](#view-phishing-url-and-click-verdict-data)
- [Iniciar investigação e resposta automatizadas](#start-automated-investigation-and-response)

> [!NOTE]
> Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las).  Os outros dois artigos desta série são a busca de ameaças no [Explorador](threat-hunting-in-threat-explorer.md) de Ameaças e o Explorador de Ameaças e noções [básicas de detecções em tempo real.](real-time-detections.md) 

Este artigo explica como exibir e investigar tentativas de malware e phishing detectadas por email por Microsoft 365 segurança. 

**Aplica-se a**

- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Exibir malware detectado no email

Para ver malware detectado em emails organizados pela tecnologia Microsoft 365, use o > [Detecções](threat-explorer-views.md#email--malware) de Malware de Email do Explorer (ou detecções em tempo real). Malware é o modo de exibição padrão, portanto, ele pode ser selecionado assim que você abrir o Explorer.

1. No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real).** (Este exemplo usa o Explorer.)

   Se você estiver no portal convergido Microsoft 365 Defender ( ) role para <https://security.microsoft.com> **Email & colaboração**  >  **Explorer**.

   A partir daqui, comece no View, escolha um determinado período de tempo para investigar (se necessário) e concentre seus filtros, conforme a passagem [do Explorer](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).

2. No menu **Exibir,** escolha **Malware de** \> **Email**.

   > [!div class="mx-imgBorder"]
   > ![Menu Exibir para Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Clique **em Remetente** e, em seguida, escolha Tecnologia de **Detecção** \> **Básica**.

   Suas tecnologias de detecção agora estão disponíveis como filtros para o relatório.

   > [!div class="mx-imgBorder"]
   > ![Tecnologias de detecção de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Escolha uma opção. Em seguida, selecione **o botão** Atualizar para aplicar esse filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnologia de detecção selecionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   O relatório é atualizado para mostrar os resultados que o malware detectou no email, usando a opção de tecnologia selecionada. A partir daqui, você pode realizar uma análise mais detalhada. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Exibir URL de phishing e clicar em dados de veredito

Você pode exibir tentativas de phishing por meio de URLs por email, incluindo uma lista de URLs que foram permitidas, bloqueadas e anuladas. Para identificar URLs que foram clicadas, Cofre [links](safe-links.md) devem ser configurados. Certifique-se de configurar as políticas [Cofre Links](set-up-safe-links-policies.md) para proteção de tempo de clique e registro em log de vereditos de clique por Cofre Links.

Para revisar URLs de phishing em mensagens e cliques em URLs em mensagens de phishing, use a exibição [   >  **phishing**](threat-explorer-views.md#email--phish) de email do Explorer ou detecções em tempo real.

1. No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real).** (Este exemplo usa o Explorer.)

2. No menu **Exibir,** escolha **Email** \> **Phish**.

   > [!div class="mx-imgBorder"]
   > ![Menu Exibir para o Explorer no contexto de phishing](../../media/ExplorerViewEmailPhishMenu.png)

3. Clique **em Remetente** e, em seguida, escolha **URLs** \> **Clique em veredito**.

4. Selecione uma ou mais opções, como **Bloqueado** e Bloqueado  **substituído,** e selecione o botão Atualizar na mesma linha que as opções para aplicar esse filtro. (Não atualize a janela do navegador.)

   > [!div class="mx-imgBorder"]
   > ![URLs e clique em vereditos](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   O relatório é atualizado para mostrar duas tabelas de URL diferentes na guia URL no relatório:

   - **As URLs principais** são as URLs nas mensagens que você filtreu para baixo e a ação de entrega de email conta para cada URL. Na exibição de email phishing, essa lista normalmente contém URLs legítimas. Os invasores incluem uma mistura de URLs boas e ruins em suas mensagens para tentar fazê-las entregues, mas fazem com que os links mal-intencionados pareçam mais interessantes. A tabela de URLs é classificação pela contagem total de emails, mas essa coluna está oculta para simplificar o exibição.

   - **Os cliques principais** são os Cofre URLs empacotadas por links que foram clicadas, classificação por contagem total de cliques. Esta coluna também não é exibida, para simplificar o exibição. Contagens totais por coluna indicam Cofre links clicam em contagem de vereditos para cada URL clicada. Na exibição de email phishing, geralmente são URLs suspeitas ou mal-intencionadas. Mas a exibição pode incluir URLs que não são ameaças, mas estão em mensagens de phishing. Os cliques de URL em links não mapeados não aparecem aqui.

   As duas tabelas de URL mostram URLs principais em mensagens de email de phishing por ação de entrega e local. As tabelas mostram cliques de URL que foram bloqueados ou visitados apesar de um aviso, para que você possa ver quais possíveis links inválidos foram apresentados aos usuários e que os usuários clicaram. A partir daqui, você pode realizar uma análise mais detalhada. Por exemplo, abaixo do gráfico, você pode ver as PRINCIPAIS URLs em mensagens de email que foram bloqueadas no ambiente da sua organização.

   > [!div class="mx-imgBorder"]
   > ![URLs do Explorer que foram bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecione uma URL para exibir informações mais detalhadas.

   > [!NOTE]
   > Na caixa de diálogo sobre o sobrevoo de URL, a filtragem em mensagens de email é removida para mostrar a exibição completa da exposição da URL em seu ambiente. Isso permite filtrar as mensagens de email que você está preocupado no Explorer, encontrar URLs específicas que são possíveis ameaças e, em seguida, expandir seu entendimento sobre a exposição de URL em seu ambiente (por meio da caixa de diálogo detalhes da URL) sem precisar adicionar filtros de URL ao próprio exibição do Explorer.

### <a name="interpretation-of-click-verdicts"></a>Interpretação de vereditos de clique

Nos flyouts email ou URL, Top Clicks e em nossas experiências de filtragem, você verá valores de veredito de clique diferentes:

- **Nenhuma:** Não é possível capturar o veredito para a URL. O usuário pode ter clicado na URL.
- **Permitido:** O usuário teve permissão para navegar até a URL.
- **Bloqueado:** O usuário foi impedido de navegar para a URL.
- **Veredito pendente:** O usuário foi apresentado com a página pendente de detonação.
- **Bloqueado substituído:** O usuário foi impedido de navegar diretamente para a URL. Mas o usuário sobrecarregue o bloco para navegar até a URL.
- **Veredito pendente ignorado:** O usuário foi apresentado com a página de detonação. Mas o usuário overrode a mensagem para acessar a URL.
- **Erro:** O usuário foi apresentado com a página de erro ou ocorreu um erro na captura do veredito.
- **Falha:** Ocorreu uma exceção desconhecida durante a captura do veredito. O usuário pode ter clicado na URL.

## <a name="start-automated-investigation-and-response"></a>Iniciar investigação e resposta automatizadas

> [!NOTE]
> Recursos automatizados de investigação e resposta estão disponíveis no Microsoft Defender para Office 365 *Plano 2* e *Office 365 E5*.

[A investigação e a resposta automatizadas](automated-investigation-response-office.md) podem economizar tempo e esforço gastos da equipe de operações de segurança investigando e atenuando ataques cibernéticos. Além de configurar alertas que podem disparar uma playbook de segurança, você pode iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer. Para obter detalhes, consulte [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="other-articles"></a>Outros artigos

[Investigar emails com a página Entidade de Email](mdo-email-entity-page.md)
