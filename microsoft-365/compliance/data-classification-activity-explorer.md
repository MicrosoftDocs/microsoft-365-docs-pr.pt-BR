---
title: Começar a usar o gerenciador de atividades
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O explorador de atividade dá o toque final na funcionalidade do recurso de classificação de dados, permitindo que você veja e filtre as ações que os usuários estão executando no conteúdo rotulado.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114003"
---
# <a name="get-started-with-activity-explorer"></a>Começar a usar o gerenciador de atividades

A visão geral [](data-classification-content-explorer.md) da [classificação](data-classification-overview.md) de dados e as guias do explorador de conteúdo dão visibilidade de qual conteúdo foi descoberto e rotulado e onde está esse conteúdo. O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado. O explorador de atividades fornece uma exibição histórica das atividades em seu conteúdo rotulado. As informações de atividade são coletadas Microsoft 365 logs de auditoria unificados, transformados e disponibilizados na interface do usuário do Explorador de Atividades. 

![Visão geral da captura de tela do Explorador de atividades](../media/data-classification-activity-explorer-1.png)

Há mais de 30 filtros diferentes disponíveis para uso, alguns são:

- intervalo de datas
- tipo de atividade
- localização
- usuário
- rótulo de confidencialidade
- rótulo de retenção
- caminho do arquivo
- Política de DLP



## <a name="prerequisites"></a>Pré-requisitos

Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:

- Microsoft 365 (E5)
- Office 365 (E5)
- Complemento de Conformidade Avançada (E5)
- Complemento Avançado de Inteligência contra Ameaças (E5)
- Microsoft 365 E5/A5 Proteção e Governança da Informação
- Conformidade Microsoft 365 E5/A5

### <a name="permissions"></a>Permissões

 Para obter acesso à guia explorador de atividades, uma conta deve ser atribuída explicitamente à associação em qualquer um desses grupos de função ou explicitamente concedida à função.

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Grupos de funções do Microsoft 365**

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade

**Microsoft 365 funções**

- Administrador de conformidade
- Administrador de segurança

## <a name="activity-types"></a>Tipos de atividade

O explorador de atividades coleta informações de atividade dos logs de auditoria em várias fontes de atividades. Para obter informações mais detalhadas sobre qual atividade de rotulagem o torna no Explorador de Atividades, consulte [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).

**Atividades de** rótulo  de sensibilidade e atividades de rotulagem de retenção de aplicativos nativos do Office, do add-in da Proteção de Informações do Azure, SharePoint Online, Exchange Online (somente rótulos de sensibilidade) e OneDrive. Alguns exemplos:

- rótulo foi aplicado
- rótulo alterado (atualizado, regredido ou removido)
- simulação de rotulação automática
- leitura de arquivo 

**Scanner e clientes AIP (Proteção de Informações do Azure)**

- proteção aplicada
- protection changed
- protection removed
- arquivos descobertos 

O Explorador de Atividades também coleta a política **de DLP** que corresponde a eventos de Exchange Online, SharePoint Online, OneDrive, chat e canal do Teams (visualização), pastas e bibliotecas do SharePoint local e compartilhamentos de arquivos locais e dispositivos Windows 10 via **DLP (prevenção** contra perda de dados do ponto de extremidade). Alguns exemplos de eventos de Windows 10 dispositivos são o arquivo:

- exclusões
- criações
- copiado para área de transferência
- modificadas
- leitura
- impresso
- renomeado
- copiado para compartilhamento de rede
- acessado por aplicativo não reatado 

O valor de entender quais ações estão sendo tomadas com seu conteúdo rotulado confidenciais é que [](dlp-learn-about-dlp.md) você pode ver se os controles que você já colocou em vigor, como a prevenção de perda de dados são efetivos ou não. Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.

> [!NOTE]
> O explorador de atividades não monitora atualmente as atividades de retenção do Exchange Online.

## <a name="see-also"></a>Confira também

- [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md)
- [Saiba mais sobre as políticas de retenção e os rótulos de retenção](retention.md)
- [Aprenda sobre os tipos de informações confidenciais](sensitive-information-type-learn-about.md)
- [Saiba mais sobre a classificação de dados](data-classification-overview.md)
