---
title: Limites para políticas de retenção e políticas de rótulo de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Entenda o número máximo de políticas e itens por política para políticas de retenção e políticas de rótulos de retenção
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107653"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Limites para políticas de retenção e políticas de rótulo de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Haverá números máximos a serem considerados ao usar [políticas de retenção e políticas de rótulos de retenção](retention.md#retention-policies-and-retention-labels) para reter ou excluir dados automaticamente da organização.

## <a name="maximum-number-of-policies-per-tenant"></a>Número máximo de políticas por locatário

Um único locatário pode ter no máximo 10.000 políticas (qualquer configuração). Esse número máximo inclui as diferentes políticas de retenção e outras políticas de conformidade, tais como políticas DLP.

Número máximo de políticas de retenção por carga de trabalho:

- Exchange Online (qualquer configuração): 1.800
- SharePoint ou OneDrive: (todos os sites incluídos automaticamente): 13
- SharePoint ou OneDrive (locais específicos incluídos ou excluídos): 2.600

## <a name="maximum-number-of-items-per-policy"></a>Número máximo de itens por política

Se você usar a configuração opcional para definir o escopo de suas configurações de retenção para usuários específicos, grupos específicos do Microsoft 365 ou sites específicos, haverá alguns limites por política a serem considerados: 

Número máximo de itens por política de retenção:

  - 1.000 caixas de correio (caixas de correio do usuário ou de grupos)
  - 1.000 grupos do Microsoft 365
  - 1.000 usuários para conversas privadas do Teams
  - 100 sites (OneDrive ou SharePoint)

Como essas limitações são por política, se você precisar usar inclusões ou exclusões específicas que resultem em passar por esses números, você poderá criar políticas de retenção adicionais que tenham as mesmas configurações de retenção. Confira a próxima seção com alguns [cenários de exemplo e soluções](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usam várias políticas de retenção por esse motivo.

No entanto, várias políticas de retenção resultam em maiores sobrecargas administrativas, portanto, sempre se questione se realmente precisa de inclusões e exclusões. Lembre-se de que a configuração padrão que se aplica a todo o local não tem limitações, e essa escolha de configuração pode ser uma solução melhor do que a criação e a manutenção de várias políticas.

> [!TIP]
> Se você precisar criar e manter várias políticas para esse cenário, considere usar o [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para uma configuração mais eficaz.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Exemplos de como usar várias políticas para evitar exceder o número máximo

Os exemplos a seguir fornecem algumas soluções de design para quando você não puder especificar o local de uma política de retenção, e leve em consideração o numero máximo de itens documentados na seção anterior.

Exemplo do Exchange:

- **Requisito**: em uma organização que tenha mais de 40.000 caixas de correio de usuário, a maioria dos usuários deve ter o email mantido por sete anos, mas um subconjunto de usuários identificados (425) deve ter seus emails mantidos por apenas cinco anos.

- **Solução**: crie uma política de retenção para o email do Exchange com um período de retenção de 7 anos e exclua o subconjunto de usuários. Em seguida, crie uma segunda política de retenção para o email do Exchange com um período de retenção de cinco anos e inclua o subconjunto de usuários. 
    
    Em ambos os casos, o número incluído e excluído fica abaixo do número máximo de caixas de correio especificadas para uma única política, e o subconjunto de usuários deve ser explicitamente excluído da primeira política, pois tem um período de retenção [maior](retention.md#the-principles-of-retention-or-what-takes-precedence) do que a segunda política. Se o subconjunto de usuários exigir uma política de retenção maior, não será necessário excluí-los da primeira política.
     
    Com essa solução, se alguém novo ingressar na organização, a caixa de correio será incluída automaticamente na primeira política por sete anos e não haverá impacto nos números máximos suportados. No entanto, novos usuários que exigem o período de retenção de 5 anos seja adicionado aos números de inclusão e exclusão, esse limite seria atingido em 1.000.

Exemplo do SharePoint:

- **Requisito**: uma organização tem milhares de sites do SharePoint, mas somente 2.000 sites exigem um período de retenção de 10 anos e 8.000 os sites exigem um período de retenção de 4 anos.

- **Solução**: criar 20 políticas de retenção para o SharePoint com um período de retenção de 10 anos que inclui 100 sites específicos e criar 80 políticas de retenção para o SharePoint com um período de retenção de 4 anos que inclui 100 sites específicos.
    
    Como não é necessário manter todos os sites do SharePoint, você deve criar políticas de retenção que especificam os sites específicos. Como uma política de retenção não dá suporte a mais de 100 sites especificados, você deve criar várias políticas para os dois períodos de retenção. Essas políticas de retenção têm o número máximo de sites incluídos, para que o próximo novo site que precise da retenção exija uma nova política, independentemente do período de retenção.