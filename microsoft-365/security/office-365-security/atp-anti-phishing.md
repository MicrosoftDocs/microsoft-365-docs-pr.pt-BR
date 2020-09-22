---
title: Recursos antiphishing ATP no Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre os recursos anti-phishing que fazem parte da proteção avançada contra ameaças do Office 365 para oferecer proteção para os ataques de mercadorias phishing de & de Spear.
ms.openlocfilehash: db1587d0cd60dc94e79b1498e000e63aa2a5ceac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199058"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>Recursos antiphishing ATP no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


A ATP anti-phishing é parte da [proteção avançada contra ameaças do Office 365](office-365-atp.md). O anti-phishing da ATP aplica um conjunto de modelos de aprendizagem de máquina em conjunto com algoritmos de detecção de representação nas mensagens de entrada para fornecer proteção contra ataques em commodity e em spear phishing. Todas as mensagens estão sujeitas a um amplo conjunto de modelos de aprendizado de máquina treinados para detectar mensagens de phishing, juntamente com um conjunto de algoritmos avançados usados para proteção contra vários ataques de personificação de domínio e usuário. A ATP anti-phishing protege sua organização de acordo com as políticas definidas pelo seu Office 365 global ou administradores de segurança.
  
Para saber mais, confira [Configurar políticas anti-phishing no Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> A ATP anti-phishing só está disponível na proteção avançada contra ameaças, que é incluída em assinaturas, como [o Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [o Microsoft 365 Business, o](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, o Office 365 Education a5, etc. Se sua organização tiver uma assinatura do Office 365 que não inclua o Office 365 ATP, você poderá comprar ATP como um complemento. Confira mais informações em [planos e preços avançados de proteção contra ameaças do office 365](https://products.office.com/exchange/advance-threat-protection) e a [Descrição do serviço de proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Como a ATP anti-phishing funciona

A ATP anti-phishing verifica mensagens de entrada para indicadores que a mensagem pode ser phishing. Sempre que um usuário é coberto por uma política de ATP (anexos seguros, links seguros ou anti-phishing), a mensagem de entrada é avaliada por vários modelos de aprendizado de máquina que analisam a mensagem para determinar se a política se aplica à mensagem e a ação apropriada é executada, com base na política configurada.
  
A ATP anti-phishing permite que administradores globais do Office 365 ou administradores de segurança definam políticas que oferecem proteção contra ataques de phishing que incluem a representação de usuários ou domínios. (ou ambos). Os administradores globais do Office 365 ou administradores de segurança definem na política quais usuários e domínios devem ser protegidos contra ataques de representação usando uma lista fixa de usuários ou domínios ou usando a inteligência de caixa de correio. O Mailbox Intelligence é uma compreensão avançada dos hábitos de email e contatos pessoais de um usuário. A ATP aprende como cada usuário individual se comunica com outros usuários dentro e fora da organização e cria um mapa dessas relações. Este mapa permite que a ATP entenda mais detalhes sobre como garantir que as mensagens certas sejam identificadas como representação.
  
As políticas de anti-phishing do ATP podem ser aplicadas a um conjunto específico de pessoas ou grupos na sua organização, ou a um domínio inteiro ou a todos os seus domínios personalizados. Para saber mais, confira [Configurar políticas anti-phishing no Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>Como obter anti-phishing do ATP

Os recursos de anti-phishing do ATP fazem parte da [proteção avançada contra ameaças](office-365-atp.md); no entanto, a proteção anti-phishing do ATP se aplica quando políticas anti-phishing são definidas. (Um exemplo é uma política baseada em representação.) Confira [Configurar políticas anti-phishing no Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Como saber se o anti-phishing da ATP está no local

As políticas de anti-phishing do ATP devem ser definidas para que a proteção entre em vigor. Verifique isso primeiro para verificar se a proteção está no local.

Além disso, os relatórios estão disponíveis para mostrar como o serviço está funcionando para sua organização. Para saber mais, confira [exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md).

Para que os modelos de aprendizado de máquina anti-phishing da ATP sejam ativados para um usuário específico, esse usuário deve fazer parte de um [anexo seguro de ATP](atp-safe-attachments.md)definido, dos [links seguros de ATP](atp-safe-links.md)ou da política anti-phishing do ATP. 

A tabela a seguir descreve alguns exemplos de cenários. Em cada um desses exemplos, a organização está usando o Office 365 Enterprise e5, que inclui proteção avançada contra ameaças.

****

|Cenário de exemplo|A ATP anti-phishing se aplica nesse caso?|
|---|---|
|A organização do Luigi tem o Office 365 Enterprise e5, mas ninguém definiu políticas para anexos seguros de ATP, links seguros de ATP ou o phishing avançado da ATP ainda.|Não. Embora o recurso esteja disponível, pelo menos uma política ATP deve ser definida para que os modelos de aprendizado da máquina ATP funcionem. Para representação, uma política anti-phishing do ATP também deve estar no local.|
|Lee é um funcionário no departamento de vendas da contoso. A organização de Lee tem uma política anti-phishing do ATP que se aplica apenas aos funcionários de finanças.|Não. Nesse caso, a ATP anti-phishing (proteção de personificação e modelos de máquina) se aplicaria a funcionários financeiros, mas outros funcionários, incluindo o departamento de vendas, não.|
|Ontem, um administrador do Office 365 na organização de Jean configurou uma política anti-phishing da ATP que se aplica a todos os funcionários. Hoje em dia, Jean recebeu uma mensagem de email que inclui uma representação coberta pela política.|Sim. Neste exemplo, Jean tem uma licença para proteção avançada contra ameaças e uma política anti-phishing do ATP que inclui Jean foi definida. Geralmente, leva cerca de 30 minutos para uma nova política entrar em vigor nos data centers; como um dia passou nesse caso, a política deve estar em vigor.|
|

## <a name="related-topics"></a>Tópicos relacionados

[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
  
[Proteção antiphishing no Office 365](anti-phishing-protection.md)
  
[Configurar políticas anti-phishing no Office 365](set-up-anti-phishing-policies.md)
  
[Links seguros de ATP no Office 365](atp-safe-links.md)
  
[Configurar políticas de links seguros de ATP no Office 365](set-up-atp-safe-links-policies.md)
  
[Anexos seguros de ATP no Office 365](atp-safe-attachments.md)
  
[Configurar políticas de anexos seguros de ATP no Office 365](set-up-atp-safe-attachments-policies.md)
  
[Exibir relatórios de Proteção avançada contra ameaças](view-reports-for-atp.md)
