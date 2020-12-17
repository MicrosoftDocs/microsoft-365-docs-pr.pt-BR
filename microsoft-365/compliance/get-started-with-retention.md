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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Pronto para começar a implementar políticas e rótulos de retenção para administrar os dados da sua organização, mas não sabe por onde começar? Leia algumas orientações práticas para começar.
ms.openlocfilehash: 26568d2a603e447156aead751178555fa400db5e
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682526"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Introdução à políticas de retenção e rótulos de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Pronto para começar a administrar os dados da sua organização, retendo o conteúdo que precisa ser mantido e excluindo o conteúdo que não precisa? Use as seguintes diretrizes de alto nível para começar:

1. **Entenda como funciona a retenção** no Microsoft 365 e identifique se você precisa usar as políticas de retenção, rótulos de retenção ou uma combinação: [Saber mais sobre retenção](retention.md)

2. **Identifique as configurações de retenção e as ações** necessárias para as políticas da organização ou normas do setor.
    
    Como parte dessa avaliação, determine se você usará o [gerenciamento de registros](records-management.md).

3. **Crie políticas e rótulos de retenção** com base nas configurações de retenção e nas ações que você identificou.
    
    Para rótulos de retenção, talvez seja útil usar [plano de arquivo](file-plan-manager.md) para definir e refinar os rótulos de retenção em uma planilha. Em seguida, importe essa planilha para criar seus rótulos.
    
3. **Publique e aplique seus rótulos de retenção**. Enquanto as políticas de retenção são projetadas para a configuração de "configurar e esquecer", os rótulos de retenção são blocos de construção reutilizáveis que podem ser usados em várias políticas e podem ser inseridos nos fluxos de trabalho do usuário. Confira a lista de [cenários comuns](#common-scenarios-for-retention-policies-and-retention-labels) para ajudá-lo a identificar como os rótulos de retenção podem ser usados. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisitos de assinatura e licenciamento para políticas e rótulos de retenção

Várias assinaturas diferentes oferecem suporte à políticas e rótulos de retenção e os requisitos de licenciamento dos usuários dependem dos recursos que você usa.

Para visualizar as opções de licenciamento dos seus usuários para se beneficiar dos recursos de conformidade do Microsoft 365, consulte as [Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD). Para retenção, confira a seção [Gestão de informações](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) e o PDF ou o download do Excel relacionado para obter os requisitos de licenciamento no nível de recurso.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Permissões necessárias para criar e gerenciar políticas e rótulos de retenção

Os membros de sua equipe de conformidade que criarão e gerenciarão políticas e rótulos de retenção precisam de permissões para o [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/). Por padrão, o administrador de locatário (administrador global) terá acesso a esse local e pode dar acesso a outras pessoas e aos responsáveis pela conformidade, sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você adicione usuários ao grupo de função de administrador **Administrador de Conformidade**.

Como alternativa para usar essa função padrão, você pode criar um novo grupo de função e adicionar a função **Gerenciamento de Retenção** a esse grupo. Para uma função somente leitura, use **Gerenciamento de Retenção Somente Para Exibição**. 

Para obter mais informações sobre esses grupos e funções, confira [Permissões no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center#roles-in-the-security--compliance-center).

Para obter instruções sobre como adicionar usuários aos grupos e atribuir funções, confira [Conceder aos usuários acesso ao Centro de Segurança e Conformidade](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Essas permissões são necessárias somente para criar, configurar e aplicar políticas de retenção e rótulos de retenção. A pessoa que configura essas políticas não necessita acesso ao conteúdo.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Cenários comuns para as políticas e rótulos de retenção

Use a tabela a seguir para ajudá-lo a mapear seus requisitos de negócios para cenários de retenção compatíveis com as políticas e rótulos de retenção.

|Eu quero...|Documentação|
|----------------|---------------|
|Defina com eficiência as ações reter e excluir do serviço Microsoft 365: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Grupos do Microsoft 365 <br />- Skype for Business  <br />- Microsoft Teams <br />- Rede do Yammer |[Criar e configurar políticas de retenção](create-retention-policies.md)|
|Permitir que os administradores e usuários apliquem manualmente as ações reter e excluir para documentos e emails: <br />- SharePoint <br />- OneDrive <br />- Outlook e Outlook na Web|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os administradores de site configuram ações reter e excluir padrão para todo o conteúdo em uma biblioteca do Microsoft Office SharePoint Online, pasta ou conjunto de documentos|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os usuários apliquem automaticamente manter e excluam ações para emails usando as regras do Outlook|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Permitir que os administradores se apliquem e excluam ações a um documento entendendo o modelo, para que eles sejam automaticamente aplicados a documentos identificados em uma biblioteca do Microsoft Office SharePoint Online|[Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)|
|Aplicar automaticamente ações reter e excluir a documentos e emails |[Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)|
|Inicie o período de retenção quando um evento ocorrer, por exemplo:  <br />- Funcionários saindo da organização <br />- Expiração dos contratos <br />- Fim da vida útil do produto| [Iniciar a retenção quando um evento ocorrer](event-driven-retention.md)|
|Restringir alterações em políticas para ajudar a atender aos requisitos normativos ou proteger contra administradores não autorizados| [Use o Bloqueio de Preservação para restringir as alterações para políticas de retenção e políticas de rótulo de retenção](retention-preservation-lock.md)
|Certifique-se de que alguém examine e aprove antes que o conteúdo seja excluído ao fim do período de retenção|[Revisões de disposição](disposition.md#disposition-reviews) |
| Monitorar como e onde as configurações reter e excluir são aplicadas aos itens | [Monitorar rótulos de retenção](retention.md#monitoring-retention-labels) |
|Usar uma única solução de gerenciamento de registros para emails e documentos |[Saiba mais sobre o gerenciamento de registros](records-management.md) |

Se você usa rótulos de retenção para o gerenciamento de registros, há outros cenários exclusivos de rótulos de retenção que marcam o conteúdo como um registro. Confira [Cenários comuns para de gerenciamento de registros](get-started-with-records-management.md#common-scenarios-for-records-management).

## <a name="end-user-documentation-for-retention-labels"></a>Documentação do usuário final para rótulos de retenção

Os rótulos de retenção, diferentemente das políticas de retenção, têm uma presença da interface de usuário em aplicativos do Microsoft 365. Certifique-se de fornecer orientações para os usuários finais e para o suporte técnico antes de implantar os rótulos de retenção à sua rede de produção.

A documentação mais eficaz do usuário final será orientação e instruções personalizadas que você fornecerá para os nomes dos rótulos de retenção e às configurações que você escolher. Confira a postagem de blog a seguir para um pacote de download que você pode usar para treinar os usuários e impulsionar a adoção: [Treinamento do Usuário Final para Etiquetas de Retenção no M365 – Como Acelerar a Sua Adoção](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).

Você também encontrará instruções de usuário básicas na seção a seguir: [Aplicar rótulos de retenção manualmente](create-apply-retention-labels.md#manually-apply-retention-labels).
