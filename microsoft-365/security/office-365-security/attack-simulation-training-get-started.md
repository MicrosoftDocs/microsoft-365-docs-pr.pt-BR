---
title: Começar a usar o Treinamento de simulação de ataque
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o treinamento de simulação de ataque para executar ataques simulados de phishing e senha em suas Microsoft 365 E5 ou no Microsoft Defender para organizações Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fa10d0d29b76d1631dd349d255b6c386557b5b8
ms.sourcegitcommit: 2266c2da090bc9a6dc1e01dea07f26901d20d57b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53222665"
---
# <a name="get-started-using-attack-simulation-training"></a>Começar a usar o Treinamento de simulação de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)

Se sua organização tiver um Microsoft 365 E5 ou o Microsoft Defender para Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o treinamento de simulação de ataque no portal Microsoft 365 Defender para executar cenários de ataque realistas em sua organização. Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real impacte sua linha inferior. Leia este artigo para saber mais.

> [!NOTE]
> O treinamento de simulação de ataque substitui a experiência antiga do Simulador de Ataque v1 descrita no [Simulador](attack-simulator.md)de Ataques no Microsoft Defender para Office 365 .

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o portal do Microsoft 365 Defender, vá para <https://security.microsoft.com>. Treinamento de simulação de ataque está disponível em Treinamento de **simulação** de ataque e email \> **e colaboração.** Para ir diretamente ao treinamento de simulação de ataque, abra <https://security.microsoft.com/attacksimulator> .

- Para obter mais informações sobre a disponibilidade do treinamento de simulação de ataque em assinaturas Microsoft 365 diferentes, consulte [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Você precisa ter permissões atribuídas no portal Microsoft 365 Defender ou no Azure Active Directory antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa ser membro do **Gerenciamento** da **Organização,** Administrador de Segurança ou uma das seguintes funções:
  - **Administradores do Simulador de Ataques**: Crie e gere todos os aspectos de campanhas de simulação de ataque.
  - **Autores de Carga do Simulador de Ataque**: Crie cargas de ataque que um administrador pode iniciar posteriormente.

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender ou](permissions-microsoft-365-security-center.md) Sobre funções de [administrador](../../admin/add-users/about-admin-roles.md).

- Não há cmdlets correspondentes do PowerShell para treinamento de simulação de ataque.

- Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para Microsoft 365 serviços. Para obter mais informações, [consulte Microsoft 365 data locations](../../enterprise/o365-data-locations.md). A simulação de ataque está disponível nas seguintes regiões: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM e CHE.

- A partir de 15 de junho de 2021, o treinamento de simulação de ataque está disponível GCC. Se sua organização tiver Office 365 G5 GCC ou Microsoft Defender para Office 365 (Plano 2) para Governo, você poderá usar o treinamento de simulação de ataque no portal Microsoft 365 Defender para executar cenários de ataque realistas em sua organização, conforme descrito neste artigo. O treinamento de simulação de ataque ainda não está disponível GCC ambientes High ou DoD.

> [!NOTE]
> O treinamento de simulação de ataque oferece um subconjunto de recursos para clientes do E3 como uma avaliação. A oferta de avaliação contém a capacidade de usar uma carga de Coleta de Credenciais e a capacidade de selecionar experiências de treinamento 'ISA Phishing' ou 'Mass Market Phishing'. Nenhum outro recursos faz parte da oferta de avaliação do E3.

## <a name="simulations"></a>Simulações

*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de senders legítimos ou confiáveis. *Phishing* faz parte de um subconjunto de técnicas que classificamos como _engenharia social._

No treinamento de simulação de ataque, vários tipos de técnicas de engenharia social estão disponíveis:

- **Coleta de credenciais**: um invasor envia ao destinatário uma mensagem que contém uma URL. Quando o destinatário clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha. Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.

- **Anexo de malware**: um invasor envia ao destinatário uma mensagem que contém um anexo. Quando o destinatário abre o anexo, o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.

- **Link in attachment**: Este é um híbrido de uma coleta de credenciais. Um invasor envia ao destinatário uma mensagem que contém uma URL dentro de um anexo. Quando o destinatário abre o anexo e clica na URL, ele é levado para um site que normalmente mostra uma caixa de diálogo que pede ao usuário seu nome de usuário e senha. Normalmente, a página de destino tem como temas representar um site conhecido para criar confiança no usuário.

- **Link para malware**: um invasor envia ao destinatário uma mensagem que contém um link para um anexo em um site de compartilhamento de arquivos conhecido (por exemplo, SharePoint Online ou Dropbox). Quando o destinatário clica na URL, o anexo é aberto e o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a se entrincheirar ainda mais.

- **Drive-by-url**: um invasor envia ao destinatário uma mensagem que contém uma URL. Quando o destinatário clica na URL, ele é levado para um site que tenta executar o código em segundo plano. Esse código em segundo plano tenta coletar informações sobre o destinatário ou implantar código arbitrário em seu dispositivo. Normalmente, o site de destino é um site conhecido que foi comprometido ou um clone de um site conhecido. A familiaridade com o site ajuda a convencer o usuário de que o link é seguro para clicar. Essa técnica também é conhecida como um ataque de _buraco de regua._

> [!NOTE]
> Verifique a disponibilidade da URL de phishing simulada em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing. Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir essas URLs de simulação, nem sempre temos cobertura completa (por exemplo, Google Cofre Navegação). A maioria dos fornecedores fornece orientações que permitem que você sempre permita URLs específicas (por exemplo, <https://support.google.com/chrome/a/answer/7532419> ).

As URLs usadas pelo treinamento de simulação de ataque são descritas na lista a seguir:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Criar uma simulação

Para obter instruções passo a passo sobre como criar e enviar uma nova simulação, consulte [Simular um ataque de phishing](attack-simulation-training.md).

### <a name="create-a-payload"></a>Criar uma carga

Para obter instruções passo a passo sobre como criar uma carga para uso em uma simulação, consulte [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Obter informações

Para obter instruções passo a passo sobre como obter informações com relatórios, consulte Obter informações por meio [do treinamento de simulação de ataque.](attack-simulation-training-insights.md)

> [!NOTE]
> O Simulador de Ataques usa links do Cofre no Defender para Office 365 rastrear com segurança os dados de clique para a URL na mensagem de carga que é enviada a destinatários direcionados de uma campanha de phishing, mesmo que a configuração Não rastrear **cliques** do usuário em Cofre Políticas de Links está conexões.
