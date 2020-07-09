---
title: Saiba mais sobre políticas de retenção para reter ou excluir o conteúdo automaticamente
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
description: Aprenda mais sobre o uso de uma política de retenção para reter ou excluir conteúdo e como aplicar uma única política à organização ou a locais ou usuários específicos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ffd7b644f33e7f432c62c182e2d69e07c8bce730
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818921"
---
# <a name="learn-about-retention-policies"></a>Saiba mais sobre políticas de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:
  
- **Estar em conformidade de forma proativa com as regulamentações do setor e as políticas internas** que exigem a retenção do conteúdo por um período mínimo de tempo, por exemplo, a lei Sarbanes-Oxley, que pode exigir que você guarde determinados tipos de conteúdo por sete anos. 
    
- **Reduzir seu risco em caso de litígio ou violação de segurança** excluindo definitivamente o conteúdo antigo que você não tem mais obrigação de guardar. 
    
- **Ajudar a sua organização a compartilhar conhecimento de maneira eficaz e ser mais ágil** garantindo que seus usuários trabalhem apenas com conteúdo atual e relevante para eles. 
    
A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:
  
- **Reter** conteúdo para que ele não seja excluído permanentemente antes do fim do período de retenção. 
    
- **Excluir** conteúdo permanentemente no final do período de retenção. 
    
Com uma política de retenção, você pode:
  
- Decidir proativamente se deseja reter o conteúdo, excluí-lo ou ambos; reter e depois excluir o conteúdo.
    
- Aplicar uma única política para a organização inteira ou locais ou usuários específicos.
    
- Aplicar uma política a todo o conteúdo ou ao conteúdo que atende condições específicas, por exemplo, como palavras-chave ou [tipos de informações confidenciais](what-the-sensitive-information-types-look-for.md).
    
When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page
  
Além disso, algumas organizações devem estar em conformidade com as regulamentações, como a Regra 17a-4 da Securities and Exchange Commission (SEC). Essa regulamentação exige que, após a ativação de uma política de retenção, ela não possa ser desativada ou tornada menos restritiva. Para atender a esse requisito, você pode usar o **Bloqueio de Preservação**. Após uma política de retenção ser bloqueada, ninguém (incluindo o administrador) poderá desativar a política de retenção ou torná-la menos restritiva. Para obter mais informações, confira a seção [Usar o Bloqueio de Preservação para atender aos requisitos regulamentares](#use-preservation-lock-to-comply-with-regulatory-requirements) nesta página.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>Como funciona uma política de retenção com conteúdo in-loco

Quando você inclui um local, como um site ou uma caixa de correio, em uma política de retenção, seu conteúdo permanece na localização original. As pessoas podem continuar a trabalhar com seus documentos ou emails como se nada tivesse mudado. Porém, se elas editarem ou excluírem o conteúdo incluído na política de retenção, uma cópia dele será mantida no estado antes da aplicação da política.
  
- Para sites do SharePoint e do OneDrive: a cópia é retida na **Biblioteca de Retenção para Preservação**. Esteja ciente de que a Biblioteca de Retenção para Preservação consome uma cota de armazenamento para o site.

- Para pastas de email e públicas: a cópia é mantida na pasta **Itens Recuperáveis**. 

- Para conteúdo do Teams: a cópia é mantida na pasta **Itens Recuperáveis** do Exchange.

- Para grupos do Microsoft 365 ([anteriormente grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)): 
    - A caixa de correio do grupo é mantida na pasta **Itens Recuperáveis** do Exchange.
    - Qualquer conteúdo do site é retido na **Biblioteca de Retenção para Preservação**.

> [!NOTE]
> A Biblioteca de Retenção para Preservação consome armazenamento que não está isento da cota de armazenamento de um site. Pode ser necessário aumentar o armazenamento ao usar políticas de retenção para o SharePoint e os Grupos do Microsoft 365.
> 
Esses locais seguros e o conteúdo retido não ficam visíveis para a maioria das pessoas. Com uma política de retenção, as pessoas nem sequer precisam saber que o conteúdo está sujeito à política.

Para obter informações mais detalhadas sobre como as políticas de retenção funcionam com diferentes cargas de trabalho, confira os seguintes artigos:

- [Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre as políticas de retenção do Microsoft Teams](retention-policies-teams.md)
- [Saiba mais sobre as políticas de retenção do Exchange](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Os princípios de retenção ou o que tem precedência?

É possível ou até mesmo provável que o conteúdo tenha várias políticas de retenção aplicadas a ele, cada uma com uma ação diferente (reter, excluir ou reter e excluir) e o período de retenção. O que tem precedência? No nível mais alto, esteja certo de que o conteúdo retido por uma política de retenção não pode ser excluído permanentemente por outra política de retenção.
  
![Diagrama dos princípios de retenção](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Para entender como as diferentes políticas de retenção são aplicadas ao conteúdo, lembre-se destes princípios de retenção:
  
1. **A retenção prevalece sobre a exclusão.** Suponha que uma política de retenção esteja configurada para excluir o email do Exchange após três anos, mas que outra política de retenção esteja configurada para manter o email do Exchange por cinco anos e depois excluí-lo. Qualquer conteúdo com três anos será excluído e ocultado dos usuários, mas ainda será mantido na pasta Itens Recuperáveis até que o conteúdo complete cinco anos, quando será permanentemente excluído. 
    
2. **O período de retenção mais longo prevalece.** Se o conteúdo estiver sujeito a várias políticas de retenção que retêm o conteúdo, ele será mantido até o fim do período de retenção mais longo. 
    
3. **A inclusão explícita prevalece sobre a inclusão implícita.** Isso significa que: 
    
    1. Se um rótulo de retenção com configurações de retenção for atribuído manualmente por um usuário a um item, como um email do Exchange ou documento do OneDrive, esse rótulo de retenção terá precedência sobre uma política de retenção atribuída no nível do site ou da caixa de correio e um rótulo de retenção padrão atribuído pelo biblioteca de documentos. Por exemplo, se o rótulo de retenção explícito estiver configurado para reter o conteúdo por 10 anos, mas a política de retenção atribuída ao site estiver configurada para reter o conteúdo por apenas cinco anos, o rótulo de retenção terá precedência. Os rótulos de retenção de aplicação automática são considerados implícitos, não explícitos, pois são aplicados automaticamente pelo Microsoft 365.
    
    2. Se uma política de retenção incluir um local específico, como a caixa de correio de um usuário específico ou conta OneDrive, essa política de retenção terá precedência sobre outra política de retenção que se aplica a caixas de correio de todos os usuários ou contas do OneDrive, mas não incluirá especificamente essa caixa de correio do usuário.
    
4. **O período de exclusão mais curto tem precedência.** Da mesma forma, se o conteúdo estiver sujeito a várias políticas de retenção que excluem o conteúdo sem um período de retenção, esse conteúdo será excluído ao fim do período de retenção mais curto. 
    
Entenda que os princípios de retenção funcionam como um fluxo de desempate de cima para baixo: se as regras aplicadas por todas as políticas de retenção ou rótulos de retenção forem as mesmas em um nível, o fluxo se moverá para baixo até o próximo nível para determinar a precedência para a qual a regra será aplicada.
  
Por fim, uma política de retenção ou um rótulo de retenção não pode excluir permanentemente qualquer conteúdo que esteja em espera para Descoberta Eletrônica. Quando a retenção for liberada, o conteúdo estará novamente qualificado para o processo de limpeza descrito acima.

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Usar o Bloqueio de Preservação para atender aos requisitos regulamentares

Algumas organizações talvez precisem cumprir regras definidas por órgãos regulamentadores, como a Regra 17a-4 da Securities and Exchange Commission (SEC), que exige que após uma política de retenção ser ativada, ela não pode ser desativada ou se tornar menos restritiva. 

O Bloqueio de Preservação garante que sua organização possa atender a esses requisitos regulamentares, pois bloqueia uma política de retenção para que ninguém, incluindo o administrador, possa desativar a política ou torná-la menos restritiva.
  
Quando uma política de retenção está bloqueada:

- Ninguém pode desativá-la
- Locais podem ser adicionados, mas não removidos 
- O conteúdo sujeito à política não pode ser modificado ou excluído durante o período de retenção
- Você pode estender um período de retenção, mas não reduzi-lo

Em resumo, uma política de retenção bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.
  
> [!IMPORTANT]
> Antes de bloquear uma política de retenção, é fundamental que você entenda seu impacto e confirme se ela é necessária para a sua organização atender aos requisitos de conformidade.

## <a name="releasing-a-retention-policy"></a>Como liberar uma política de retenção

Desde que sua política de retenção não tenha um Bloqueio de Preservação, você pode desativar ou excluir uma política de retenção a qualquer momento. 

Quando você faz isso, todo o conteúdo do SharePoint ou do OneDrive que está sendo mantido na biblioteca de retenção de preservação não é excluído imediata e permanentemente. Em vez disso, para ajudar a evitar a perda acidental de dados, há um período de cortesia de 30 dias, durante o qual a expiração de conteúdo dessa política não acontece na biblioteca de retenção para preservação para que você possa restaurar todo o conteúdo de lá, se necessário. Além disso, não é possível excluir manualmente esse conteúdo durante o período de cortesia.

Você também pode ativar a política de retenção novamente durante o período de cortesia e nenhum conteúdo será excluído para essa política.

O período de cortesia de 30 dias no SharePoint e no OneDrive corresponde à retenção por atraso de 30 dias no Exchange. Para saber mais, confira [Gerenciar caixas de correios em retenção por atraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="use-a-retention-policy-instead-of-older-features"></a>Usar uma política de retenção em vez de recursos mais antigos

Uma única política de retenção pode ser facilmente aplicada a uma organização inteira e a locais por todo o Microsoft 365, incluindo o Exchange Online, o SharePoint Online, o OneDrive e Grupos do Microsoft 365. Caso você precise manter ou excluir conteúdo em qualquer lugar no Microsoft 365, é recomendável usar uma política de retenção e, opcionalmente, complementá-la com [rótulos de retenção](labels.md).
  
Se você já usou outras configurações para reter ou excluir conteúdo no Microsoft 365, elas continuarão a funcionar lado a lado com políticas e rótulos de retenção. No entanto, recomendamos que, daqui para frente, você use políticas de retenção e rótulos de retenção. Eles fornecem um único mecanismo para gerenciar centralmente a retenção e a exclusão de conteúdo no Microsoft 365.

Recursos mais antigos que você pode ter usado:
  
**Recursos mais antigos do Exchange Online:**

- [Bloqueio In-loco e a Retenção de Litígio](https://go.microsoft.com/fwlink/?linkid=846124) (Retenção de Descoberta Eletrônica) 

- [Como identificar o tipo de retenção de uma caixa de correio do Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Marcas de retenção e políticas de retenção](https://go.microsoft.com/fwlink/?linkid=846125), também conhecidas como [gerenciamento de registros de mensagens (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (apenas exclusão)
    
Confira também [Baixa das ferramentas de Descoberta Eletrônica herdadas](legacy-ediscovery-retirement.md).


**Recursos mais antigos do SharePoint e do OneDrive:**

- [Adicionar conteúdo a uma ocorrência e colocar fontes em retenção na Descoberta Eletrônica](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (Retenção de Descoberta Eletrônica) 
    
- [Políticas de exclusão documento](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (apenas exclusão)
    
- [Como configurar o gerenciamento de registros no local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (apenas retenção) 
    
- [Usar políticas de fechamento de site e exclusão](https://support.microsoft.com/pt-BR/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (apenas exclusão) 
    
- [Políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md) (apenas exclusão)
     
Se tiver usado anteriormente qualquer um dos bloqueios de descoberta eletrônica para fins de governança de informações, use uma política de retenção para conformidade proativa. Use a Descoberta Eletrônica para apenas bloqueios.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Políticas de retenção e políticas de tipo de conteúdo do SharePoint ou políticas de gerenciamento de informações

Se você configurou sites do SharePoint para políticas de tipo de conteúdo ou políticas de gerenciamento de informações para reter o conteúdo de uma lista ou biblioteca, essas políticas serão ignoradas enquanto uma política de retenção estiver em vigor. 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>As políticas de preservação são convertidas em políticas de retenção

Se você estava usando uma política de preservação para reter dados em caixas de correio, sites do SharePoint ou do OneDrive, ou pastas públicas: essa política foi convertida automaticamente em uma política de retenção que usa apenas a ação de retenção, a política não excluirá o conteúdo. As alterações não são necessárias para o mesmo resultado da política de preservação configurada.

Você pode encontrar quaisquer políticas de preservação configuradas na página **Políticas** no [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com/) ou na página **Retenção**, em **Governança de informações**, no [Centro de Conformidade&amp; e Segurança](https://protection.office.com/). Você pode editar uma política de preservação para alterar o período de retenção, mas não pode fazer outras alterações, como adicionar ou remover locais. 


## <a name="related-information"></a>Informações relacionadas

- [Saiba mais sobre rótulos de retenção](labels.md)
- [Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limites e especificações para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Cumprir com a Regra 17a-4 da SEC](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Próximas etapas

Se você estiver pronto para criar políticas de retenção, confira [Criar e configurar políticas de retenção](create-retention-policies.md).

