---
title: Área de trabalho e ITIL gerenciados da Microsoft
description: Correlaciona as fases de ITIL com artigos e informações da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841430"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Área de trabalho e ITIL gerenciados da Microsoft

Muitas organizações acham valioso estruturar seus serviços de IT ao longo das linhas de um MODELO de Serviço de IT (ITSM) formalizado, como [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

A Área de Trabalho Gerenciada da Microsoft permite que sua organização cumpra vários aspectos importantes desses modelos ITSM formalizados. Usando ITIL como exemplo, este artigo ajuda você a ver as conexões entre fases e processos comuns de ITIL e recursos equivalentes da Área de Trabalho Gerenciada da Microsoft, quando aplicável. Essas informações se aplica somente à parte da Área de Trabalho Gerenciada da Microsoft da sua organização.

Para obter mais informações sobre ITIL e suas fases e processo, consulte a [documentação.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Design de serviço

Esta tabela relaciona as principais fases e processos de ITIL aos recursos da Área de Trabalho Gerenciada da Microsoft, com links para nossa documentação para obter detalhes:



|Processo ITIL |Descrição  |Documentação |
|---------|---------|---------|
|Gerenciamento de nível de serviço     | Os tempos de resposta são definidos para solicitações e incidentes de suporte do administrador.  |  [Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)  |
|Gerenciamento de catálogo de serviços     | A descrição do serviço que detalha os componentes do serviço é mantida verdadeira para o estado do serviço, disponível para todos os clientes atuais e interessados.<br><br>Pré-requisitos detalhados para entender o que é necessário para operar o serviço.  | - [Descrição do serviço da Área de Trabalho Gerenciada da Microsoft](service-description/index.md)<br><br>- [Prepare-se para o registro na Área de Trabalho Gerenciada da Microsoft](get-ready/index.md)  |
|Gerenciamento de segurança da informação     | Informações de segurança, incluindo segurança de informações para o serviço.<br><br> Políticas relacionadas à segurança e outras informações sobre como os dispositivos são configurados.   | - [Segurança na Área de Trabalho Gerenciada da Microsoft](service-description/security.md)<br><br>- [Configuração do dispositivo](service-description/device-policies.md)  |
|Gerenciamento de disponibilidade     |  A Área de Trabalho Gerenciada da Microsoft equilibra a responsabilidade com sua organização para garantir a disponibilidade do serviço.<br><br>Os administradores e usuários têm rotas para o respectivo suporte se houver problemas de serviço ou disponibilidade. | - [Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft](service-description/operations-and-monitoring.md)<br><br>- [Suporte de administrador para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)<br>- [Obter ajuda para usuários](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Transição de serviço


|Processo ITIL |Descrição  |Documentação |
|---------|---------|---------|
|Gerenciamento de alterações     | Equilíbrio definido de responsabilidade, visão geral do processo e tipos relacionados ao gerenciamento de alterações disponíveis.  | [Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft](service-description/operations-and-monitoring.md#change-management) |
|Gerenciamento de lançamento e implantação     |  A Área de Trabalho Gerenciada da Microsoft gerencia atualizações para dispositivos inscritos no serviço.  | [Como as atualizações são tratadas na Área de Trabalho Gerenciada da Microsoft](service-description/updates.md)        |
|Gerenciamento de configuração e ativos de serviço     | As informações sobre a implantação da Área de Trabalho Gerenciada da Microsoft da sua organização estão disponíveis no portal de administração de IT.  | [Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md) |
|Gerenciamento de conhecimento     | As informações sobre o serviço área de trabalho gerenciada da Microsoft são mantidas atualizadas neste site.   | [Histórico de alterações da documentação da Área e Trabalho Gerenciada da Microsoft](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Operação de serviço


|Processo ITIL |Descrição  |Documentação  |
|---------|---------|---------|
|Gerenciamento de eventos     |  Detalhes sobre o monitoramento de dispositivos são fornecidos.<br><br>Procedimentos operacionais padrão para o serviço de Área de Trabalho Gerenciada da Microsoft são detalhados. |  - [Segurança na Área de Trabalho Gerenciada da Microsoft](service-description/security.md)<br>- [Operações e monitoramento da Área de Trabalho Gerenciada da Microsoft](service-description/operations-and-monitoring.md)       |
|Gestão de incidentes  | A Área de Trabalho Gerenciada da Microsoft investigará e agirá em incidentes de acordo com as definições de gravidade definidas.  |  [Definições de severidade de solicitação de suporte](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Gerenciamento de atendimento de solicitações     |  O processo de solicitações de informações e solicitações de alteração relacionadas ao serviço de Área de Trabalho Gerenciada da Microsoft está definido.         |[Administrador de suporte para Área de Trabalho Gerenciada da Microsoft](working-with-managed-desktop/admin-support.md)         |
|Gerenciamento de problemas     | Quaisquer problemas com o serviço devem ser direcionados para sua equipe de conta local no momento. | Documentação em desenvolvimento |
|Gerenciamento de acesso     | Acessar componentes e responsabilidades de gerenciamento para o cliente garantir que a funcionalidade seja detalhada.  | [Gerenciamento de identidades e acesso](service-description/security.md#identity-and-access-management)        |
