---
title: Área de trabalho e ITIL gerenciados da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, ITISM
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 05bd5a2ee36633b7ccf9ae61e601988a7268bb2c
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289800"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Área de trabalho e ITIL gerenciados da Microsoft

Muitas organizações acham importante estruturar seus serviços de ti ao longo das linhas de um modelo de serviço de ti formalizado (ITSM), como [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

A área de trabalho gerenciada da Microsoft permite que sua organização cumpra vários aspectos fundamentais dos modelos ITSM formalizados. Usando ITIL como exemplo, este tópico ajuda você a ver as conexões entre as fases e os processos comuns da ITIL e os recursos equivalentes de área de trabalho gerenciada da Microsoft, quando aplicável. Isso aplica-se apenas à parte da área de trabalho gerenciada da Microsoft de sua organização.

Para obter mais informações sobre a ITIL e suas fases e processo, consulte sua [documentação](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Design de serviço

Esta tabela relaciona os principais processos e fases da ITIL aos recursos de área de trabalho gerenciada da Microsoft, com links para a documentação para obter detalhes:



|Processo de ITIL |Descrição  |Documentação |
|---------|---------|---------|
|Gerenciamento de nível de serviço     | Os tempos de resposta são definidos para solicitações de suporte de administração e incidentes.  |  [Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)  |
|Gerenciamento do catálogo de serviços     | Descrição do serviço o detalhamento de componentes do serviço é mantido true para o estado do serviço, disponível para todos os clientes atuais e interessados.<br><br>Pré-requisitos detalhados para entender o que é necessário para operar o serviço.  | - [Descrição do serviço de área de trabalho gerenciada da Microsoft](service-description/index.md)<br><br>- [Prepare-se para o registro na área de trabalho gerenciada da Microsoft](get-ready/index.md)  |
|Gerenciamento de segurança de informações     | Informações de segurança, incluindo segurança de informações para o serviço.<br><br> Políticas relacionadas à segurança e outras informações sobre como os dispositivos são configurados.   | - [Segurança na área de trabalho gerenciada da Microsoft](service-description/security.md)<br><br>- [Configuração do dispositivo](service-description/device-policies.md)  |
|Gerenciamento de disponibilidade     |  A área de trabalho gerenciada da Microsoft equilibra a responsabilidade da sua organização para garantir a disponibilidade do serviço.<br><br>Administradores e usuários têm rotas para o respectivo suporte em caso de problemas de disponibilidade ou serviço. | - [Monitoramento e operações de área de trabalho gerenciada da Microsoft](service-description/operations-and-monitoring.md)<br><br>- [Suporte de administrador para área de trabalho gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)<br>- [Obtendo ajuda para usuários](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transição de serviço


|Processo de ITIL |Descrição  |Documentação |
|---------|---------|---------|
|Gerenciamento de alterações     | Foi definido o equilíbrio de responsabilidade, a visão geral do processo e os tipos relacionados ao gerenciamento de alterações disponível.  | [Monitoramento e operações de área de trabalho gerenciada da Microsoft](service-description/operations-and-monitoring.md#change-management) |
|Gerenciamento de lançamento e implantação     |  O Microsoft Managed desktop gerencia atualizações para dispositivos registrados no serviço.  | [Como as atualizações são tratadas na área de trabalho gerenciada da Microsoft](service-description/updates.md)        |
|Gerenciamento de ativos e configuração de serviços     | As informações sobre a implantação do Microsoft Managed desktop da sua organização estão disponíveis no portal de administração de ti.  | [Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md) |
|Gerenciamento de conhecimento     | As informações sobre o serviço de área de trabalho gerenciado da Microsoft são mantidas atualizadas neste site.   | [Histórico de alterações da documentação da Área e Trabalho Gerenciada da Microsoft](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operação de serviço


|Processo de ITIL |Descrição  |Documentação  |
|---------|---------|---------|
|Gerenciamento de eventos     |  São fornecidos detalhes sobre o monitoramento de dispositivos.<br><br>Os procedimentos operacionais padrão para o serviço de área de trabalho gerenciada da Microsoft são detalhados. |  - [Segurança na área de trabalho gerenciada da Microsoft](service-description/security.md)<br>- [Monitoramento e operações de área de trabalho gerenciada da Microsoft](service-description/operations-and-monitoring.md)       |
|Gerenciamento de incidentes  | O Microsoft Managed desktop investigará e agirá em incidentes por definições de gravidade definidas.  |  [Definições de gravidade de solicitação de suporte](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Gerenciamento de atendimento de solicitação     |  O processo para solicitações de informações e solicitações de alteração relacionadas ao serviço de área de trabalho gerenciada da Microsoft são definidos.         |[Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)         |
|Gerenciamento de problemas     | Qualquer problema com o serviço deve ser direcionado para sua equipe de conta local no momento. | Documentação em desenvolvimento |
|Gerenciamento de acesso     | Os componentes de gerenciamento de acesso e as responsabilidades do cliente para garantir que a funcionalidade sejam detalhadas.  | [Gerenciamento de identidades e acesso](service-description/security.md#identity-and-access-management)        |
