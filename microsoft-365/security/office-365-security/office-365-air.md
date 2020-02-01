---
title: Investigar e responder automaticamente a ameças no Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Comece a usar os recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 9c17d7219e5dd15404b171fbd6707d00fd788f19
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598758"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Investigar e responder automaticamente a ameças no Office 365

## <a name="overview"></a>Visão Geral

Dependendo da sua assinatura, a [proteção avançada contra ameaças do Office 365](office-365-atp.md) pode incluir recursos de investigação e resposta automatizados que podem economizar tempo e esforço da equipe de operações de segurança em lidar com alertas e ameaças.

- Para começar a usar os recursos de investigação e resposta automatizados no Office 365, use este artigo. 
- Para obter uma visão geral de como ele funciona, consulte [investigação e resposta automatizadas no Office 365](automated-investigation-response-office.md).

> [!TIP]
> Você tem o Microsoft 365 E5 ou Microsoft 365 E3 juntamente com Proteção contra Identidade e Ameaças? Considere a possibilidade de experimentar a [investigação e a resposta automatizadas (Air) na proteção contra ameaças da Microsoft](../mtp/mtp-autoir.md).

Com recursos de investigação e resposta automatizados, quando determinados alertas são acionados, um ou mais guias de segurança são iniciados e o processo de investigação automatizado é iniciado. Durante e após um processo de investigação automatizado, a equipe de segurança pode fazer o seguinte:

- [Exibir os detalhes de uma investigação](#view-details-of-an-investigation)
- [Revisar e aprovar ações como resultado de uma investigação](#review-and-approve-actions) 
- [Exibir detalhes sobre um alerta relacionado a uma investigação](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> Para executar as tarefas descritas neste artigo, você deve ter as permissões apropriadas atribuídas. Confira [as permissões necessárias para usar os recursos de ar](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).

## <a name="view-details-of-an-investigation"></a>Exibir detalhes de uma investigação

1. Vá para [https://protection.office.com](https://protection.office.com) e entre. Isso leva você para o centro de conformidade de & de segurança.

2. Siga um destes procedimentos:

    - Vá para o**painel**de **Gerenciamento** > de ameaças. Isso leva você para o [painel de segurança](security-dashboard.md). Os widgets do AIR aparecem na parte superior do [painel de segurança](security-dashboard.md). Selecione um widget, como o **Resumo de investigações**.

    - Vá para **** > **investigações**de gerenciamento de ameaças. 

    Qualquer um dos métodos o leva a uma lista de investigações.

    ![Página de investigação principal para AIR](../media/air-maininvestigationpage.png) 

3. Na lista de investigações, selecione um item na coluna **ID** . Isso abre a página detalhes da investigação, começando com o gráfico de investigação no modo de exibição.

    ![Página de gráfico de investigação aérea](../media/air-investigationgraphpage.png)

4. Use as várias guias para saber mais sobre a investigação.

## <a name="review-and-approve-actions"></a>Revisar e aprovar ações

No Office 365, as investigações automatizadas normalmente resultam em uma ou mais ações recomendadas. No entanto, nenhuma ação será executada até que sejam aprovadas pela equipe de operações de segurança. Use o procedimento a seguir para revisar e aprovar ações.

1. Vá para [https://protection.office.com](https://protection.office.com) e entre. 

2. Vá para **** > **investigações**de gerenciamento de ameaças.

3. Na lista de investigações, selecione um item na coluna **ID** . 

3. No modo de exibição detalhes da investigação, selecione a guia **ações** . Todas as ações que estão com aprovação pendente são listadas aqui.

4. Selecione um item na lista.

5. Selecione **aprovar** para executar a ação recomendada (ou **rejeitar** para fechar a investigação sem executar a ação).

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Exibir detalhes sobre um alerta relacionado a uma investigação

Determinados tipos de alertas disparam investigação automatizada no Office 365. Para saber mais, confira [alertas](automated-investigation-response-office.md#alerts). Use o procedimento a seguir para exibir detalhes sobre um alerta que está associado a uma investigação automatizada.

1. Vá para [https://protection.office.com](https://protection.office.com) e entre. Isso leva você para o centro de conformidade de & de segurança.

2. Vá para **** > **investigações**de gerenciamento de ameaças.

3. Na lista de investigações, selecione um item na coluna **ID** . 

4. Com detalhes de uma investigação aberta, selecione a guia **alertas** . Todos os alertas que dispararam a investigação estão listados aqui.

5. Selecione um item na lista. Um submenu abre, com detalhes sobre o alerta e links para informações adicionais e ações.

6. Revise as informações no submenu e, dependendo do alerta específico, execute uma ação, como **resolver**, **suprimir**ou **notificar os usuários**. 

    - **Resolver** é equivalente a fechar um alerta
    
    - **Supressão** faz com que uma política não acione alertas por um período de tempo especificado
    
    - **Notificar os usuários sobre** o início de um email com os endereços de email dos usuários já inseridos e permite que sua equipe de operações de segurança digite uma mensagem para esses usuários. (Isso é semelhante ao envio de uma mensagem para destinatários usando o [Explorador de ameaças](threat-explorer.md).)  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Usar a API de atividade de gerenciamento do Office 365 para soluções de relatórios personalizados ou de terceiros

Se sua organização estiver usando uma solução de relatórios personalizada ou de terceiros, você poderá exibir informações sobre investigações automatizadas nessa solução usando a API da atividade de gerenciamento do Office 365.

Use os seguintes recursos para configurar isso:

|Resource  |Descrição  |
|---------|---------|
|[Visão geral das APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure Active Directory.         |
|[Introdução às APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |A API de gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Office 365. Siga as etapas deste artigo para configurá-lo.          |
|[Referência da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Você pode usar a API de atividade de gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure AD. Leia este artigo para saber mais sobre como isso funciona.        |
|[Esquema da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Obtenha uma visão geral do [esquema comum](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e do [Office 365 ATP e o esquema de resposta](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para conhecer os tipos específicos de dados disponíveis por meio da API de atividade de gerenciamento do Office 365.         |

## <a name="next-steps"></a>Próximas etapas

- [Descubra como obter o AIR e ver as permissões necessárias](automated-investigation-response-office.md#how-to-get-air)
- [Saiba mais sobre os alertas](../../compliance/alert-policies.md)
- [Encontre e investigue manualmente emails mal-intencionados que foram entregues no Office 365](investigate-malicious-email-that-was-delivered.md)
- [Saiba mais sobre o AIR no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir](https://www.microsoft.com/microsoft-365/roadmap?filters=)