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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O explorador de atividade dá o toque final na funcionalidade do recurso de classificação de dados, permitindo que você veja e filtre as ações que os usuários estão executando no conteúdo rotulado.
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921629"
---
# <a name="get-started-with-activity-explorer"></a>Começar a usar o gerenciador de atividades

As guias visão geral de classificação de dados e explorador de conteúdo dão visibilidade ao conteúdo que foi descoberto e rotulado e mostra onde está esse conteúdo. O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado. O explorador de atividades fornece um modo de exibição histórica.

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

 Para obter acesso à guia do explorador de atividades, é necessário atribuir uma conta à participação em qualquer uma dessas funções ou grupos de funções.

**Grupos de funções do Microsoft 365**

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade

## <a name="activity-type"></a>Tipo de atividade

O Microsoft 365 monitora e relata os tipos de atividades em todo o SharePoint Online e OneDrive como:

- rótulo foi aplicado
- rótulo alterado (atualizado, regredido ou removido)
- simulação de rotulação automática

O vantagem de ficar sabendo que ações estão sendo tomadas com o conteúdo rotulado como confidencial é que você pode verificar se os controles que você já colocou em ação, tais como as [políticas de prevenção de perda de dados](data-loss-prevention-policies.md) estão sendo eficazes ou não. Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.

> [!NOTE]
> O explorador de atividades não monitora atualmente as atividades de retenção do Exchange Online.

## <a name="see-also"></a>Confira também
- [Saiba mais sobre rótulos de confidencialidade](sensitivity-labels.md)
- [Saiba mais sobre as políticas de retenção e os rótulos de retenção](retention.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)

