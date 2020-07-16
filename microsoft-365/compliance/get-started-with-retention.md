---
title: Introdução à políticas de retenção e rótulos de retenção
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
description: Pronto para começar a implementar políticas e rótulos de retenção para administrar os dados da sua organização, mas não sabe por onde começar? Leia algumas orientações práticas para começar.
ms.openlocfilehash: 415313ac31fe4ad56f9a476576f14b90d7dd97f4
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127548"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Introdução à políticas de retenção e rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Pronto para começar a administrar os dados da sua organização, retendo o conteúdo que precisa ser mantido e excluindo o conteúdo que não precisa? Use as seguintes diretrizes de alto nível para começar:

1. **Entenda como funciona a retenção** no Microsoft 365 e identifique se você precisa usar as políticas de retenção, rótulos de retenção ou uma combinação: [Saber mais sobre retenção](retention.md)

2. **Identifique as configurações de retenção e as ações** necessárias para as políticas da organização ou normas do setor.
    
    Como parte dessa avaliação, determine se você usará o [gerenciamento de registros](records-management.md).

3. **Crie políticas e rótulos de retenção**com base nas configurações de retenção e nas ações que você identificou.
    
    Para rótulos de retenção, talvez seja útil usar [plano de arquivo](file-plan-manager.md) para definir e refinar os rótulos de retenção em uma planilha. Em seguida, importe essa planilha para criar seus rótulos.
    
3. **Publique e aplique seus rótulos de retenção**. Enquanto as políticas de retenção são projetadas para a configuração de "configurar e esquecer", os rótulos de retenção são blocos de construção reutilizáveis que podem ser usados em várias políticas e podem ser inseridos nos fluxos de trabalho do usuário. Confira a lista de [cenários comuns](#common-scenarios-for-retention-policies-and-retention-labels) para ajudá-lo a identificar como os rótulos de retenção podem ser usados. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisitos de assinatura e licenciamento para políticas e rótulos de retenção

Várias assinaturas diferentes oferecem suporte à políticas e rótulos de retenção e os requisitos de licenciamento dos usuários dependem dos recursos que você usa.

Para visualizar as opções de licenciamento dos seus usuários para se beneficiar dos recursos de conformidade do Microsoft 365, consulte as [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD). Para retenção, confira a seção [Gestão de informações](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) e o PDF ou o download do Excel relacionado para obter os requisitos de licenciamento no nível de recurso.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Permissões necessárias para criar e gerenciar políticas e rótulos de retenção

Os membros de sua equipe de conformidade que criarão e gerenciarão políticas e rótulos de retenção precisam de permissões para o [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/). Por padrão, o administrador de locatário (administrador global) terá acesso a esse local e pode dar acesso a outras pessoas e aos responsáveis pela conformidade, sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você adicione usuários ao grupo de função de administrador **Administrador de Conformidade**. Para obter instruções, confira [Fornecer aos usuários acesso ao Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Essas permissões são necessárias somente para criar e aplicar uma política de retenção. A pessoa que configura a política de retenção não exige acesso ao conteúdo.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Cenários comuns para as políticas e rótulos de retenção

Use a tabela a seguir para ajudá-lo a mapear seus requisitos de negócios para cenários de retenção compatíveis com as políticas e rótulos de retenção.

|Eu quero...|Documentação|
|----------------|---------------|
|Defina com eficiência as ações reter e excluir para a organização ou por local: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Grupos do Microsoft 365 <br />- Skype for Business  <br />- Teams  |[Criar e configurar políticas de retenção](create-retention-policies.md)|
|Permita que os administradores e os usuários apliquem manualmente um conjunto de ações de retenção e exclusão de documentos e emails: <br />- SharePoint <br />- OneDrive <br />- Outlook e Outlook na Web|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Deixe que os administradores do site apliquem um rótulo de retenção padrão a todo o conteúdo em uma biblioteca, pasta ou conjunto de documentos do SharePoint|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permita que os usuários apliquem automaticamente um rótulo de retenção a emails usando as regras do Outlook|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Automaticamente aplique um conjunto de ações de retenção e exclusão de documentos e emails |[Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)|
|Inicie o período de retenção quando um evento ocorrer, por exemplo:  <br />- Funcionários saindo da organização <br />- Expiração dos contratos <br />- Fim da vida útil do produto| [Iniciar a retenção quando um evento ocorrer](event-driven-retention.md)|
|Use uma única solução de gerenciamento de registros para documentos e emails |[Gerenciamento de registros no Microsoft 365](records-management.md) |
|Cumprir com a Regra SEC 17a-4|[Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma SEC 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|Certifique-se de que alguém examine e aprove antes que o conteúdo seja excluído ao fim do período de retenção|[Revisões de disposição](disposition.md#disposition-reviews) |
|Tenha a prova de disposição para o conteúdo excluído ao fim do seu período de retenção|[Disposição de conteúdo](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>Documentação do usuário final para rótulos de retenção

Os rótulos de retenção, diferentemente das políticas de retenção, têm uma presença da interface de usuário em aplicativos do Microsoft 365. Certifique-se de fornecer orientações para os usuários finais e para o suporte técnico antes de implantar os rótulos de retenção à sua rede de produção.

A documentação mais eficaz do usuário final será orientação e instruções personalizadas que você fornecerá para os nomes dos rótulos de retenção e às configurações que você escolher. No entanto, você pode usar as seguintes informações para obter instruções básicas:

- [Aplicar manualmente os rótulos de retenção](create-apply-retention-labels.md#manually-apply-retention-labels)
