---
title: Saiba mais sobre a prevenção contra perda de dados do Microsoft 365 Endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'A prevenção contra perda de dados do Microsoft 365 Endpoint estende o monitoramento de atividades de arquivo e ações de proteção desses arquivos para os pontos de extremidade. Os arquivos do são visíveis nas soluções do Centro de conformidade do Microsoft 365 '
ms.openlocfilehash: 457701a514159e54e932db3e4ad04a7428165fdc
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604311"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365

Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens. Para mais informações sobre a DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).

**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10. Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Atividades do ponto de extremidade que você pode monitorar e executar

O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10. Isso inclui:


|atividade no item |auditável/restringivel  |
|---------|---------|
|criado    | auditável      |
|renomeado    |  auditável       |
|copiado ou criado em mídia removível     |     auditável e restringível|
|copiado para compartilhamento de rede, por exemplo \\my-server\fileshare   |     auditável e restringível    |
|impresso |    auditável e restringível       |
|copiado para a nuvem por meio do Chromium Edge    |   auditável e restringível        |
|acessado por aplicativos e navegadores que não tem permissão de acesso    |  auditável e restringível       |

## <a name="whats-different-in-endpoint-dlp"></a>O que é diferente no Endpoint DLP

Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.

### <a name="enabling-device-management"></a>Habilitar o gerenciamento de dispositivos

O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md). Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.

> [!div class="mx-imgBorder"]
> ![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos. O centro tem scripts personalizados para cada um desses métodos de implantação:

- script local (até 10 máquinas)
- Política de grupo
- System Center Configuration Manager (versão 1610 ou posterior)
- Gerenciamento de dispositivos móveis/Microsoft Intune
- Scripts de integração VDI para máquinas não persistentes

> [!div class="mx-imgBorder"]
> ![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.

Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.

> [!div class="mx-imgBorder"]
> ![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Exibir dados de DLP do Endpoint

 O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada. Neste momento, os seguintes tipos de arquivos são compatíveis:

- Arquivos do Word
- Arquivos do PowerPoint
- Arquivos do Excel
- Arquivos PDF
- Arquivos .csv
- Arquivos .tsv
- Arquivos .txt
- Arquivos .rtf
- Arquivos .c
- Arquivos .class
- Arquivos .cpp
- Arquivos .cs
- Arquivos .h
- Arquivos .java

> [!NOTE]
> O DLP de ponto de extremidade avalia os arquivos de todos os tipos acima em relação à política de DLP e aplica as ações de proteção de acordo. Todos os arquivos que correspondem a uma política DLP são auditados para todas as ações com suporte, mesmo se não forem bloqueadas. Além disso, a atividade de arquivo realizada em qualquer arquivo de Word, PowerPoint, Excel, PDF e .csv é auditado por padrão, independentemente da existência de uma política DLP ou da correspondência desses arquivos.

Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).

![Informações sobre alertas](../media/Alert-info-1.png)

Você também pode visualizar detalhes do evento associado com metadados ricos no mesmo painel

![informações do evento](../media/Event-info-1.png)

Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.

> [!div class="mx-imgBorder"]
> ![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.

Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:

- tipo de atividade
- IP do Cliente
- caminho do arquivo de destino
- carimbo de data/hora ocorrido
- nome do arquivo
- usuário
- extensão do arquivo
- tamanho do arquivo
- tipo de informação confidencial (se aplicável)
- valor SHA1
- valor SHA256
- nome do arquivo anterior
- localização
- primário
- FilePath
- Tipo de local de origem
- plataforma
- nome do dispositivo
- Tipo de local de destino
- aplicativo que executou a cópia
- ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)
- fabricante do dispositivo de mídia removível
- modelo do dispositivo de mídia removível
- número de série do dispositivo de mídia removível

> [!div class="mx-imgBorder"]
> ![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Próximas etapas

Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:

1) [Introdução à prevenção contra perda de dados do ponto de extremidade da Microsoft](endpoint-dlp-getting-started.md)
2) [Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-using.md)

## <a name="see-also"></a>Confira também

- [Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-getting-started.md)
- [Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-using.md)
- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/)
- [Gerenciamento de risco interno](insider-risk-management.md)
