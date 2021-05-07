---
title: Saiba mais sobre a Extensão de Conformidade da Microsoft (prévia)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: A Extensão de Conformidade da Microsoft estende o monitoramento e controle de atividades de arquivo e ações de proteção para o navegador Google Chrome
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113377"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a>Saiba mais sobre a Extensão de Conformidade da Microsoft (prévia)

[A Prevenção contra Perda de Dados de Ponto de Extremidade (ponto de extremidade DLP)](endpoint-dlp-learn-about.md) estende os recursos de monitoramento de atividade e proteção da [prevenção contra perda de dados (DLP) do Microsoft 365](dlp-learn-about-dlp.md) para itens confidenciais que estão em dispositivos Windows 10. Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).

Depois que a Extensão de Conformidade da Microsoft é instalada em um dispositivo Windows 10, as organizações podem monitorar quando um usuário tenta acessar ou fazer upload de um item confidencial para um serviço em nuvem usando o Google Chrome e aplicar ações de proteção via DLP.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Atividades que você pode monitorar e realizar

A extensão de Conformidade da Microsoft permite que você audite e gerencie os seguintes tipos de atividades que os usuários realizam em itens confidenciais em dispositivos que executam o Windows 10.

atividade |descrição  | ações de política apoiadas|
|---------|---------|---------|
|arquivo copiado para nuvem  | Detecta quando um usuário tenta fazer upload de um item confidencial para um domínio de serviço restrito por meio do navegador Chrome |auditoria, bloquear|
|arquivo impresso  |Detecta quando um usuário tenta imprimir um item confidencial que está aberto no navegador Chrome em uma impressora local ou de rede |auditoria, bloquear com substituição, bloquear|
|O arquivo foi copiado para a área de transferência |Detecta quando um usuário tenta copiar informações de um item confidencial que está sendo visualizado no navegador Chrome e, em seguida, colá-lo em outro aplicativo, processo ou item. |auditoria, bloquear com substituição, bloquear|
|arquivo copiado para armazenamento removível    | Detecta quando um usuário tenta copiar um item confidencial ou informação de um item confidencial que está aberto no navegador Chrome para uma mídia removível ou dispositivo USB |auditoria, bloquear com substituição, bloquear|
|arquivo copiado para compartilhamento de rede  |Detecta quando um usuário tenta copiar um item confidencial ou informação de um item confidencial que está aberto no navegador Chrome para um compartilhamento de rede ou unidade de rede mapeada.|auditoria, bloquear com substituição, bloquear |

## <a name="deployment-process"></a>Processo de implantação
1. [Comece a usar a prevenção contra Perda de Dados de Ponto de Extremidade](endpoint-dlp-getting-started.md)
2. [Ferramentas e métodos de integração para dispositivos Windows 10](dlp-configure-endpoints.md)
3. [Instale a extensão em seus dispositivos Windows 10](dlp-chrome-get-started.md)
4. [Crie ou edite políticas de DLP](create-test-tune-dlp-policy.md) que restrinjam o upload para o serviço em nuvem ou o acesso por meio de ações não permitidas de navegadores e aplique-as aos seus dispositivos Windows 10

## <a name="next-steps"></a>Próximas etapas

Confira [Primeiros passos com a Extensão de Conformidade da Microsoft](dlp-chrome-get-started.md) para procedimentos e cenários completos de implantação.

## <a name="see-also"></a>Confira também

- [Comece a usar a Extensão de Conformidade da Microsoft](dlp-chrome-get-started.md)
- [Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade do Microsoft 365](endpoint-dlp-learn-about.md)
- [Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-getting-started.md)
- [Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft](endpoint-dlp-using.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/)
- [Gerenciamento de risco interno](insider-risk-management.md)
