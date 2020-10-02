---
title: Introdução ao gerenciamento de registros no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Precisa de uma solução de gerenciamento de registros para o Microsoft 365 que gerencie o conteúdo de alto valor para obrigações legais, comerciais ou normativas, mas não sabe onde começar? Leia algumas orientações práticas para começar.
ms.openlocfilehash: fd3e3368b7a23cb31a8df4953268576de2419f89
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333847"
---
# <a name="get-started-with-records-management"></a>Começar a usar o gerenciamento de registros

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Pronto para começar a gerenciar o conteúdo de alto valor da sua organização para obrigações legais, comerciais ou normativas usando uma solução de gerenciamento de registros no Microsoft 365? Use as seguintes diretrizes de alto nível para começar:

1. **Compreenda a solução de gerenciamento de registros** e quais ações são permitidas ou bloqueadas quando os documentos e emails são registros declarados: [Saber mais sobre o gerenciamento de registros](records-management.md). 

2. **Compreenda os rótulos de retenção e a forma como a retenção funciona** para o SharePoint e o Exchange, pois os rótulos de retenção são usados para declarar registros: [Saiba mais sobre as políticas de retenção e os rótulos de retenção](retention.md)

3. **Crie o seu plano de arquivo para as configurações de retenção e ações** ao [importar um plano existente](file-plan-manager.md#import-retention-labels-into-your-file-plan ) se você tiver um ou criar [novos rótulos de retenção que declarem registros](declare-records.md).

4. **Publique e aplique seus rótulos de retenção**. Os rótulos de retenção são blocos de construção reutilizáveis que podem ser usados em várias políticas e podem ser inseridos em fluxos de trabalho do usuário: 
    
    - [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
    - [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Requisitos de assinatura e licenciamento para o gerenciamento de registros

Várias assinaturas diferentes permitem o gerenciamento de registros e os requisitos de licenciamento para os usuários dependem dos recursos que você usa.

Para visualizar as opções de licenciamento dos seus usuários para se beneficiar dos recursos de conformidade do Microsoft 365, consulte as [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD). Para o gerenciamento de registros, confira a seção [Gerenciamento de Registros](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) e o PDF relacionado ou o download do Excel para atender aos requisitos de licenciamento no nível de recurso.

## <a name="permissions-required-for-records-management"></a>Permissões necessárias para o gerenciamento de registros

Os membros da sua equipe de conformidade que são responsáveis pelo gerenciamento de registros precisam de permissões para o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/). Por padrão, o administrador de locatários (administrador global) tem acesso a esse local e pode conceder acesso aos gerentes de conformidade e a outras pessoas sem conceder a eles todas as permissões de um administrador de locatários. Para conceder permissões para essa administração limitada, recomendamos que você adicione usuários ao grupo de função de administrador **Gerenciamento de Registros**, que concede a função **RecordManagement**.

As permissões incluídas neste grupo de função não incluem as permissões necessárias para a [revisão de disposição e verificação](disposition.md), e até mesmo um administrador global não tem essa permissão por padrão. Para gerenciar a disposição, use a função **Disposition Management** criando um grupo de funções personalizado ou usando um grupo de função padrão que inclui essa função (como **Administrador de Conformidade**).

Para obter mais informações sobre esses grupos e funções, confira [Permissões no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center#roles-in-the-security--compliance-center).

Para obter instruções sobre como adicionar usuários aos grupos e atribuir funções, confira [Conceder aos usuários acesso ao Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Essas permissões são necessárias somente para criar, configurar e aplicar rótulos de retenção que declarem registros, e gerenciar disposição. A pessoa que configura esses rótulos não exige acesso ao conteúdo.

## <a name="common-scenarios-for-records-management"></a>Cenários comuns de gerenciamento de registros

Use a tabela a seguir para ajudá-lo a mapear seus requisitos de negócios para os cenários com suporte para o gerenciamento de registros.

> [!NOTE]
> Como o gerenciamento de registros usa rótulos de retenção para marcar um item como um registro, muitos cenários nesta tabela também são listados como [cenários comuns para políticas de retenção e rótulos de retenção](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Eu quero...|Documentação|
|----------------|---------------|
|Declarar um registro |[Declarar registros usando rótulos de retenção](declare-records.md)|
|Atualizar um registro |[Usar a versão de registro para atualizar registros armazenados no SharePoint ou no OneDrive](record-versioning.md)|
|Permitir que os administradores e usuários apliquem manualmente as ações reter e excluir para documentos e emails: <br />- SharePoint <br />- OneDrive <br />- Outlook e Outlook na Web|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os administradores de site configuram ações reter e excluir padrão para todo o conteúdo em uma biblioteca do Microsoft Office SharePoint Online, pasta ou conjunto de documentos|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os usuários apliquem automaticamente manter e excluam ações para emails usando as regras do Outlook|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os administradores se apliquem e excluam ações a um documento entendendo o modelo, para que eles sejam automaticamente aplicados a documentos identificados em uma biblioteca do Microsoft Office SharePoint Online|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Aplicar automaticamente ações reter e excluir a documentos e emails |[Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)|
|Inicie o período de retenção quando um evento ocorrer, por exemplo:  <br />- Funcionários saindo da organização <br />- Expiração dos contratos <br />- Fim da vida útil do produto| [Iniciar a retenção quando um evento ocorrer](event-driven-retention.md)|
|Gerenciar o ciclo de vida de diferentes tipos de documentos no Microsoft Office SharePoint Online| [Use os rótulos de retenção para gerenciar o ciclo de vida dos documentos armazenados no SharePoint](auto-apply-retention-labels-scenario.md)|
|Certifique-se de que alguém examine e aprove antes que o conteúdo seja excluído permanentemente no final do período de retenção|[Revisões de disposição](disposition.md#disposition-reviews) |
|Ter uma prova de eliminação para o conteúdo que é excluído permanentemente no final do período de retenção|[Disposição de conteúdo](disposition.md#disposition-of-records) |
|Monitorar como e onde as configurações reter e excluir são aplicadas aos itens | [Monitorar rótulos de retenção](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Documentação do usuário final para registros

Os rótulos de retenção usados para o gerenciamento de registros têm uma presença da interface de usuário em aplicativos do Microsoft 365. Certifique-se de fornecer orientações para os usuários finais e para o suporte técnico antes de implantar os rótulos de retenção à sua rede de produção.

A documentação mais eficaz do usuário final será orientação e instruções personalizadas que você fornecerá para os nomes dos rótulos de retenção e às configurações que você escolher. No entanto, você pode usar as seguintes informações para obter instruções básicas:

- [Aplicar manualmente os rótulos de retenção](create-apply-retention-labels.md#manually-apply-retention-labels)
