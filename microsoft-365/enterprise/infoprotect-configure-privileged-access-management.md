---
title: 'Etapa 4: Configurar o gerenciamento de acesso privilegiado do Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado do Office 365.
ms.openlocfilehash: 297d8e042c2a22c93b4ea566081d258e7ca0a5ab
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286944"
---
# <a name="step-4-configure-privileged-access-management-for-office-365"></a>Etapa 4: Configurar o gerenciamento de acesso privilegiado do Office 365

*Esta etapa é opcional e se aplica apenas às versões E5 e Advanced Compliance do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso just-in-time a atividades baseadas em tarefas em seu locatário do Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário do Office 365.

Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário do Office 365 e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso baseado em tarefas nos dados e definições de configuração do Office 365 em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização do Office 365:
- Criar um grupo de aprovadores
- Habilitar o acesso privilegiado
- Criar políticas de aprovação

Depois de configurado, o gerenciamento do acesso privilegiado possibilitará que sua organização opere com zero privilégios permanentes e proporcionará uma camada de defesa contra vulnerabilidades surgidas por causa deste acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tem uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas em uma política de aprovação deve solicitar e receber aprovação de acesso para ter as permissões necessárias para executar as tarefas definidas na política.

Para habilitar o gerenciamento do acesso privilegiado no Office 365, confira o tópico [Configurar o gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para saber mais, confira o tópico [Gerenciamento do acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

## <a name="results"></a>Resultados

O resultado esta etapa é que você aumentou a segurança do Office 365, habilitando o controle de acesso just-in-time para dados-chave e as definições de configuração para sua organização.

Como um ponto de verificação provisório, confira os [Critérios de saída](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondentes desta etapa.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de proteção de informações](infoprotect-exit-criteria.md)