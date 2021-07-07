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
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314411"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365

Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens. Para obter mais informações sobre DLP, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md).

**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10. Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).

> [!TIP]
> Se você estiver procurando controle de dispositivo para repositório removível, consulte [Controle de acesso para repositório removível do controle de dispositivo do Microsoft Defender para Ponto de Extremidade](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Atividades do ponto de extremidade que você pode monitorar e executar

O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.

|Atividade |Descrição  | Auditável/restringivel|
|---------|---------|---------|
|carregar para o serviço de nuvem ou acessar por navegadores não permitidos    | Detecta quando um usuário tenta carregar um item em um domínio de serviço restrito ou acessar um item por meio de um navegador.  Se eles estiverem usando um navegador listado na DLP como um navegador não permitido, a atividade de carregamento será bloqueada e o usuário será redirecionado para usar o Edge Chromium. O Edge Chromium permitirá ou bloqueará o carregamento ou o acesso com base na configuração da política DLP         |auditável e restringível|
|copiar para outro aplicativo    |Detecta quando um usuário tenta copiar informações de um item protegido e, em seguida, colá-las em outro aplicativo, processo ou item. A cópia e a colagem de informações dentro do mesmo aplicativo, processo ou item não é detectada por essa atividade.         | auditável e restringível|
|copiar para mídia removível USB |Detecta quando um usuário tenta copiar um item ou informação para uma mídia removível ou dispositivo USB.         | auditável e restringível|
|Copiar para um compartilhamento de rede    |Detecta quando um usuário tenta copiar um item para um compartilhamento de rede ou unidade de rede mapeada         |auditável e restringível|
|imprimir um documento    |Detecta quando um usuário tenta imprimir um item protegido em uma impressora local ou de rede.| auditável e restringível         |
|copiar para uma sessão remota|Detecta quando um usuário tenta copiar um item para uma sessão remota da área de trabalho |  auditável e restringível|
|copiar para um dispositivo Bluetooth|Detecta quando um usuário tenta copiar um item para um aplicativo Bluetooth não conectado (conforme definido na lista de aplicativos Bluetooth não relacionados nas configurações de DLP do ponto de extremidade).| auditável e restringível|
|criar um Item|Detecta quando um usuário cria um item| auditável|
|renomear um item|Detecta quando um usuário renomeia um item| auditável|

## <a name="monitored-files"></a>Arquivos monitorados

Endpoint DLP oferece suporte ao monitoramento destes tipos de arquivo:

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

Por padrão, o DLP do endpoint audita as atividades para esses tipos de arquivo, mesmo se não houver uma correspondência de política. Se quiser apenas monitorar dados de correspondências de política, você pode desligar **Sempre auditar atividade de arquivo para dispositivos** nas configurações globais de DLP do endpoint. Se esta configuração estiver ativada, as atividades em qualquer arquivo do Word, PowerPoint, Excel, PDF e .CSV serão sempre auditadas, mesmo que o dispositivo não seja direcionado por nenhuma política.

O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada.

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

Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.

> [!div class="mx-imgBorder"]
> ![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Exibir dados de DLP do Endpoint

Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).

> [!div class="mx-imgBorder"]
> ![Informações sobre alertas](../media/Alert-info-1.png)

Você também pode exibir os detalhes do evento associado com metadados ricos no mesmo painel

> [!div class="mx-imgBorder"]
> ![informações do evento](../media/Event-info-1.png)

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

1. [Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-getting-started.md)
2. [Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-using.md)

## <a name="see-also"></a>Confira também

- [Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-getting-started.md)
- [Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-using.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/)
- [Gerenciamento de risco interno](insider-risk-management.md)
