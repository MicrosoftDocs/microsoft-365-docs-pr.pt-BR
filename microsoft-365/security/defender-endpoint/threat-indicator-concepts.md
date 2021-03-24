---
title: Compreender os conceitos de inteligência contra ameaças no Microsoft Defender para Ponto de Extremidade
description: Criar alertas de ameaça personalizados para sua organização e aprender os conceitos em torno da inteligência contra ameaças no Microsoft Defender para Ponto de Extremidade
keywords: inteligência contra ameaças, definições de alerta, indicadores de comprometimento, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053865"
---
# <a name="understand-threat-intelligence-concepts"></a>Compreender conceitos de inteligência contra ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Os ataques avançados de segurança cibernética incluem vários eventos mal-intencionados complexos, atributos e informações contextuais. Identificar e decidir qual dessas atividades se qualificam como suspeitas pode ser uma tarefa desafiadora. Seu conhecimento de atributos conhecidos e atividades anormais específicas ao seu setor é fundamental para saber quando chamar um comportamento observado como suspeito.

Com o Microsoft Defender para Ponto de Extremidade, você pode criar alertas de ameaça personalizados que podem ajudá-lo a acompanhar as possíveis atividades de ataque em sua organização. Você pode sinalizar eventos suspeitos para reunir pistas e possivelmente parar uma cadeia de ataque. Esses alertas de ameaça personalizados serão exibidos apenas em sua organização e sinalizam eventos que você definiu como acompanhar.

Antes de criar alertas de ameaças personalizados, é importante conhecer os conceitos por trás das definições de alerta e dos indicadores de comprometimento (IOCs) e a relação entre eles.

## <a name="alert-definitions"></a>Definições de alerta
As definições de alerta são atributos contextuais que podem ser usados coletivamente para identificar as primeiras pistas sobre um possível ataque de segurança cibernética. Esses indicadores são geralmente uma combinação de atividades, características e ações tomadas por um invasor para atingir com êxito o objetivo de um ataque. O monitoramento dessas combinações de atributos é fundamental para obter um ponto de vantagem contra ataques e possivelmente interferir na cadeia de eventos antes que o objetivo de um invasor seja atingido.

## <a name="indicators-of-compromise-ioc"></a>Indicadores de comprometimento (IOC)
Os IOCs são eventos mal-intencionados conhecidos individualmente que indicam que uma rede ou dispositivo já foi violado. Ao contrário das definições de alerta, esses indicadores são considerados como evidência de uma violação. Eles geralmente são vistos depois que um ataque já foi executado e o objetivo foi atingido, como a exfiltração. O controle de IOCs também é importante durante investigações forenses. Embora não forneça a capacidade de intervir com uma cadeia de ataque, reunir esses indicadores pode ser útil para criar melhores defesas para possíveis ataques futuros.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relação entre definições de alerta e IOCs
No contexto do Microsoft Defender para Ponto de Extremidade, as definições de alerta são contêineres para IOCs e define o alerta, incluindo os metadados gerados em caso de uma combinação de IOC específica. Vários metadados são fornecidos como parte das definições de alerta. Metadados como o nome da definição de alerta de ataque, gravidade e descrição são fornecidos juntamente com outras opções.

Cada IOC define a lógica de detecção concreta com base em seu tipo e valor, bem como sua ação, que determina como ela é corresponder. Ele está vinculado a uma definição de alerta específica que define como uma detecção é exibida como um alerta no console do Microsoft Defender para Ponto de Extremidade.

Aqui está um exemplo de um IOC:
- Tipo: Sha1
- Valor: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Ação: Igual a

Os IOCs têm uma relação de muitos para um com definições de alerta para que uma definição de alerta possa ter muitos IOCs que correspondam a ela.

## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
[Pull detections to your SIEM tools](configure-siem.md)| Saiba mais sobre diferentes maneiras de puxar detecções.
[Habilitar a integração do SIEM no Microsoft Defender para Endpoint](enable-siem-integration.md)| Saiba mais sobre a habilitação do  recurso de integração siem na página Configurações do portal para que você possa usar e gerar as informações necessárias para configurar as ferramentas SIEM suportadas.
[Configurar o Splunk para puxar o Microsoft Defender para detecções de ponto de extremidade](configure-siem.md)| Saiba mais sobre como instalar o Aplicativo de Entrada Modular da API REST e outras configurações para habilitar o Splunk a puxar o Microsoft Defender para detecções de ponto de extremidade.
[Configurar o HP ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade](configure-arcsight.md)| Saiba mais sobre como instalar o pacote HP ArcSight REST FlexConnector e os arquivos que você precisa configurar arcSight para puxar o Microsoft Defender para detecções de ponto de extremidade.
[Campos de Detecção de Ponto de Extremidade do Microsoft Defender](api-portal-mapping.md) | Entenda quais campos de dados são expostos como parte da API de alertas e como eles mapeiam para o Centro de Segurança do Microsoft Defender.
[Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST](pull-alerts-using-rest-api.md) | Use o fluxo de credenciais do cliente OAuth 2.0 para puxar detecções do Microsoft Defender para Ponto de Extremidade usando a API REST.
[Solucionar problemas de integração de ferramentas SIEM](troubleshoot-siem.md) | Solucionar problemas que você pode encontrar ao usar o recurso de integração SIEM.



## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar indicadores](manage-indicators.md)
