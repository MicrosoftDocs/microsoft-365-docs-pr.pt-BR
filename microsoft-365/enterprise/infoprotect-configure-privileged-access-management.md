---
title: 'Etapa 7: configurar o gerenciamento de acesso privilegiado'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636983"
---
# <a name="step-7-configure-privileged-access-management"></a>Etapa 7: configurar o gerenciamento de acesso privilegiado

*Esta etapa é opcional e se aplica apenas às versões E5 e Advanced Compliance do Microsoft 365 Enterprise*

![Fase 6: Proteção de Informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

O gerenciamento de acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time para atividades com base em tarefas em seu locatário. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso à dados confidenciais ou acesso a definições de configuração crítica. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer aprovação explícita para acessar e alterar as configurações de caixa de correio de organização em seu locatário.

Nesta etapa, você habilitará o gerenciamento de acesso privilegiado no locatário e configurará políticas de acesso privilegiado que forneçam segurança adicional para acesso baseado em tarefa a dados e definições de configuração para sua organização. Há três etapas básicas para começar a usar o acesso privilegiado em sua organização:
- Criar um grupo de aprovadores
- Habilitar o acesso privilegiado
- Criar políticas de aprovação

Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.

Para habilitar o gerenciamento de acesso privilegiado, consulte o tópico [Configurar gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .

Para obter mais informações, consulte o tópico [Gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .


|||
|:-------|:-----|
|![Guias de laboratório de teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para praticar essa configuração em um ambiente de laboratório de testes, confira o [Guia de laboratório de testes de gerenciamento de acesso privilegiado](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step7) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de proteção de informações](infoprotect-exit-criteria.md)
