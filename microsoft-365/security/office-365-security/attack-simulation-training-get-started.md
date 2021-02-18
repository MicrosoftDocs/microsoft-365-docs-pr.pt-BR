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
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o treinamento de simulação de ataque para executar ataques simulados de phishing e senha em suas organizações do Microsoft 365 E5 ou Microsoft Defender for Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ec5b8175db6eb03e59a31a4dc21d9649c5e7616
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289884"
---
# <a name="get-started-using-attack-simulation-training"></a>Começar a usar o Treinamento de simulação de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Se sua organização tiver o Microsoft 365 E5 ou o Microsoft Defender for Office 365 Plano 2, que inclui recursos de Investigação e Resposta contra [Ameaças,](office-365-ti.md)você poderá usar o treinamento de simulação de ataque na Central de Segurança da Microsoft para executar cenários de ataque realistas em sua organização. Esses ataques simulados podem ajudá-lo a identificar e encontrar usuários vulneráveis antes que um ataque real a impacte seu resultado final. Leia este artigo para saber mais.

> [!NOTE]
> O treinamento de simulação de ataque substitui a experiência antiga do Simulador de Ataque v1 descrita no Simulador de Ataques no [Microsoft Defender para Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir a Central de Segurança da Microsoft, vá para <https://security.microsoft.com/> . O treinamento de simulação de ataque está disponível no **treinamento de simulação** de ataque e email \> **de colaboração.** Para ir diretamente para o treinamento de simulação de ataque, abra <https://security.microsoft.com/attacksimulator> .

- Para obter mais informações sobre a disponibilidade do treinamento de simulação de ataques em diferentes assinaturas do Microsoft 365, consulte a descrição do serviço do [Microsoft Defender for Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Você precisa ter permissões no Centro de Conformidade e Segurança & ou no Azure Active Directory antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa ser membro do **Gerenciamento** da **Organização,** Administrador de Segurança ou uma das seguintes funções:
  - **Administradores do Simulador de** Ataque: criar e gerencia todos os aspectos de campanhas de simulação de ataque.
  - **Autores de Carga do Simulador de Ataque:** Criar cargas de ataque que um administrador pode iniciar mais tarde.

  Para obter mais informações, [consulte Permissões no Centro de Conformidade](permissions-in-the-security-and-compliance-center.md) & segurança ou sobre funções de [administrador.](../../admin/add-users/about-admin-roles.md)

- Não há cmdlets do PowerShell correspondentes para treinamento de simulação de ataque.

- Os dados relacionados à simulação de ataque e treinamento são armazenados com outros dados do cliente para os serviços do Microsoft 365. Para saber mais, confira [locais de dados do Microsoft 365.](/microsoft-365/enterprise/o365-data-locations) No momento, a simulação de ataque não está disponível nas seguintes regiões: SGP, NOR, EMIRADOS, ZAF, GER, REIN e CHE.

## <a name="simulations"></a>Simulações

*Phishing* é um termo genérico para ataques de email que tentam roubar informações confidenciais em mensagens que parecem ser de envios legítimos ou confiáveis. *Phishing* é uma parte de um subconjunto de técnicas que classificamos como _engenharia social._

No treinamento de simulação de ataques, vários tipos de técnicas de engenharia social estão disponíveis:

- **Coleta de credenciais:** um invasor envia ao destinatário uma mensagem que contém uma URL. Quando o destinatário clica na URL, ele é levado a um site que normalmente mostra uma caixa de diálogo que solicita ao usuário seu nome de usuário e senha. Normalmente, a página de destino tem como temas um site conhecido para criar confiança no usuário.

- **Anexo de** malware: um invasor envia ao destinatário uma mensagem que contém um anexo. Quando o destinatário abre o anexo, o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a entrar mais.

- **Link em anexo:** este é um híbrido de uma coleta de credenciais. Um invasor envia ao destinatário uma mensagem que contém uma URL dentro de um anexo. Quando o destinatário abre o anexo e clica na URL, ele é levado a um site que normalmente mostra uma caixa de diálogo que solicita ao usuário seu nome de usuário e senha. Normalmente, a página de destino tem como temas um site conhecido para criar confiança no usuário.

- **Link para malware:** um invasor envia ao destinatário uma mensagem que contém um link para um anexo em um site de compartilhamento de arquivos conhecido (por exemplo, SharePoint Online ou Dropbox). Quando o destinatário clica na URL, o anexo é aberto e o código arbitrário (por exemplo, uma macro) é executado no dispositivo do usuário para ajudar o invasor a instalar código adicional ou a entrar mais.

- **Drive-by-url:** um invasor envia ao destinatário uma mensagem que contém uma URL. Quando o destinatário clica na URL, ele é levado para um site que tenta executar código em segundo plano. Esse código em segundo plano tenta coletar informações sobre o destinatário ou implantar código arbitrário em seu dispositivo. Normalmente, o site de destino é um site conhecido que foi comprometido ou um clone de um site conhecido. A familiaridade com o site ajuda a convencer o usuário de que é seguro clicar no link. Essa técnica também é conhecida como um ataque _de buraco de água._

> [!NOTE]
> Verifique a disponibilidade da URL de phishing simulada em seus navegadores da Web com suporte antes de usar a URL em uma campanha de phishing. Embora trabalhemos com muitos fornecedores de reputação de URL para sempre permitir essas URLs de simulação, nem sempre temos cobertura total (por exemplo, Navegação Segura do Google). A maioria dos fornecedores fornece orientações que permitem sempre permitir URLs específicas (por exemplo, <https://support.google.com/chrome/a/answer/7532419> ).

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

Para obter instruções passo a passo sobre como criar e enviar uma nova simulação, consulte [Simular um ataque de phishing.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Criar uma carga

Para obter instruções passo a passo sobre como criar uma carga para uso em uma simulação, consulte Criar uma carga personalizada para treinamento de [simulação de ataque.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Obter informações

Para obter instruções passo a passo sobre como obter informações com relatórios, consulte Obter informações por meio [do treinamento de simulação de ataque.](attack-simulation-training-insights.md)
