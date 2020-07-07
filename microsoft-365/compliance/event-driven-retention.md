---
title: Visão geral da retenção controlada por eventos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Normalmente parte de uma solução de gerenciamento de registros, em que você pode configurar um rótulo de retenção para iniciar o período de retenção com base em um evento identificado.
ms.openlocfilehash: f2cf60eac1197ed7be3fd8cbbe69e41a37614f86
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048286"
---
# <a name="overview-of-event-driven-retention"></a>Visão geral da retenção controlada por eventos

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
Exemplos de uso da retenção impulsionada por eventos:
  
- **Funcionários que estão saindo da organização** Suponha que os registros de funcionários devam ser retidos por 10 anos após a data em que o funcionário saiu da organização. Decorrido o prazo de 10 anos, todos os documentos relacionados à contratação, desempenho e demissão desse funcionário precisam ser descartados. O evento que desencadeia o período de retenção de 10 anos é a saída do funcionário da organização. 
    
- **Vencimento de um contrato** Suponha que todos os registros relativos a contratos devam ser retidos por 10 anos após a data de vencimento do contrato. O evento que desencadeia o período de retenção de cinco anos é o vencimento do contrato. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Os rótulos baseados em eventos também costumam classificar o conteúdo como um registro. Para obter mais informações, confira o artigo [Saiba mais sobre registros](records.md).
    
- Um documento classificado como registro cujo evento desencadeador ainda não ocorreu é retido por prazo indeterminado (os registros não podem ser excluídos permanentemente), até que um evento desencadeie seu período de retenção.
    
- Os rótulos de retenção baseados em eventos costumam desencadear uma análise de descarte no final do período de retenção, de modo que um gerente de registros possa analisar e descartar o conteúdo manualmente. Para obter mais informações, confira o artigo [Disposição e descarte de conteúdo](disposition.md).
    
Os recursos dos rótulos de retenção baseados em um evento são os mesmos que os de quaisquer outros rótulos de retenção do Microsoft 365. Para obter mais informações, consulte [Saiba mais sobre rótulos de retenção](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Compreender a relação entre tipos de eventos, rótulos, eventos e IDs de ativos

Para usar a retenção controlada por eventos com êxito, é importante compreender a relação entre tipos de evento, rótulos, eventos e IDs de ativo, conforme ilustrado nos diagramas e explicações a seguir: 
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Você cria rótulos de retenção para diferentes tipos de conteúdo e depois os associa a um tipo de evento. Por exemplo, os rótulos de retenção para diferentes tipos de arquivos e registros de produtos são associados a um tipo de evento denominado Vida útil do produto, pois esses registros devem ser retidos por 10 anos a partir do momento em que o produto atinge o final de sua vida útil.
    
2. Os usuários (normalmente gerenciadores de registros) aplicam esses rótulos de retenção ao conteúdo e (para documentos do SharePoint e OneDrive) inserem uma ID de ativo para cada item. Nesse exemplo, a ID do ativo é um nome ou código de produto usado pela organização. Assim, os registros de cada produto recebem um rótulo de retenção e cada registro tem uma propriedade que contém uma ID de ativo. O diagrama representa **todo o conteúdo** de todos os registros de produtos em uma organização e cada item tem a ID do ativo do produto cujo registro ele pertence. 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - Uma ID de ativo (para documentos do SharePoint e do OneDrive)
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. Depois de criar um evento, a data dele é sincronizada com todo o conteúdo que tem um rótulo desse tipo de evento e que contém a ID ou palavra-chave especificada do ativo. Como qualquer rótulo de retenção, essa sincronização pode levar até sete dias. No diagrama anterior, todos os itens marcados com um círculo vermelho têm o período de retenção desencadeado por esse evento. Em outras palavras, quando esse produto chega ao fim da vida útil, esse evento ativa o período de retenção dos registros desse produto.
    
É importante entender que se você não especificar uma ID de ativos ou palavras-chave para um evento, **todo o conteúdo** com um rótulo desse tipo de evento terá um período de retenção desencadeado pelo evento. Isso significa que, no diagrama anterior, todo o conteúdo começaria a ser retido. Isso pode não ser o que você pretende. 
  
Por fim, lembre-se de que cada rótulo de retenção tem suas próprias configurações de retenção. Neste exemplo, todos eles especificam dez anos, mas é possível que um evento ative rótulos de retenção onde cada rótulo tem um período de retenção diferente.
  
## <a name="how-to-set-up-event-driven-retention"></a>Como configurar a retenção controlada por eventos

Aqui está o fluxo de trabalho de alto nível para a retenção controlada por eventos:
  
![Diagrama de fluxo de trabalho para configurar a retenção controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> Confira [Gerenciar o ciclo de vida dos documentos do SharePoint com rótulos de retenção](auto-apply-retention-labels-scenario.md) para obter um cenário detalhado sobre como usar as propriedades gerenciadas no SharePoint para aplicar automaticamente os rótulos de retenção e implementar a retenção voltada para o evento.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Etapa 1: criar um rótulo cujo período de retenção seja baseado em um evento

Para criar e configurar seu rótulo de retenção, use as instruções do artigo [Criar e configurar os rótulos de retenção](create-retention-labels.md#create-and-configure-retention-labels). Ao ativar a retenção, escolha a opção de reter ou excluir o conteúdo com base em um evento. Essa opção significa que as configurações de retenção somente entrarão em vigor quando você chegar à Etapa 5, em que um evento será criado na página **Eventos**. 
  
De modo geral, a retenção impulsionada por eventos é utilizada para conteúdos que são classificados como registros. Aproveite essa oportunidade e verifique se você também precisa selecionar a opção de marcar um conteúdo como um registro.
  
A retenção impulsionada por eventos requer configurações de retenção que:
  
- Retêm o conteúdo.
    
- Excluem o conteúdo automaticamente, ou acionam uma revisão de disposição ao final do período de retenção.
    
![Opção para basear um rótulo em um evento](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a>Etapa 2: Escolher um tipo de evento para esse rótulo

Nas configurações do rótulo, depois de escolher a opção de basear o rótulo em um **evento** você verá a opção **Escolher um tipo de evento**. Um tipo de evento é uma descrição geral de um evento que você quer associar a um rótulo.
  
Por exemplo, se você criar um tipo de evento chamado Vida útil do produto, criará os rótulos baseados em eventos com nomes que descrevem a quais tipos de conteúdo você deseja aplicar os rótulos, como "Arquivos de desenvolvimento de produto" ou "Registros de decisões comerciais sobre o produto".
  
Após escolher um tipo de evento e salvar o rótulo de retenção, o tipo de evento não poderá mais ser alterado.
  
![Opções para criar ou escolher um tipo de evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Etapa 3: publicar ou aplicar automaticamente os rótulos de retenção com base em eventos

Assim como qualquer rótulo, você precisa [publicar ou aplicar automaticamente](create-retention-labels.md)um rótulo com base em eventos, para que ele seja aplicado manual ou automaticamente ao conteúdo.

> [!NOTE]
> Se você selecionar um rótulo de retenção voltada para a aba**Plano de arquivo** > ** de Gerenciamento de Registros**ou de **Rótulos de dados de Governança ** > **** o botão**aplicar rótulo automaticamente** não estará disponível.
> 
> Em vez disso, use a **Aplicar um rótulo automaticamente**, acima da lista de rótulos ou políticas, de um dos seguintes locais:
> - Aba de políticas de**Gerenciamento de registros** > **de Rótulo **
> - Aba de Rótulos de**Governança de dados ** > **** ou aba de **políticas**


![Opções para publicar ou aplicar automaticamente um rótulo](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Etapa 4: Inserir uma ID de ativo

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- Códigos de produto que você pode usar para reter o conteúdo apenas de um produto específico.
    
- Códigos de projeto que você pode usar para reter o conteúdo apenas de um projeto específico.
    
- IDs de funcionário que você pode usar para reter o conteúdo apenas de uma pessoa específica.
    
A ID de Ativo é, simplesmente, mais uma propriedade do documento no SharePoint e no OneDrive. Sua organização já pode usar outras propriedades e IDs do documento para classificar o conteúdo. Nesse caso, você também pode usar essas propriedades e valores ao criar um evento - consulte a etapa 6 a seguir. O ponto importante é que sua organização deve usar alguma combinação de propriedade:valor nas propriedades do documento para associar esse item a um tipo de evento.
  
![Caixa de texto para inserir uma ID de ativo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Etapa 5: Criar um evento

Quando uma instância específica desse tipo de evento ocorre — como, por exemplo, o fim da vida útil de um produto — vá para a página **Eventos de gerenciamento** > **de registros** no centro de conformidade do Microsoft 365 e crie um evento. Você precisa desencadear um evento manualmente por meio de sua criação.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Etapa 6: Escolher o mesmo tipo de evento usado pelo rótulo na Etapa 2

Ao criar o evento, escolha o mesmo tipo de evento usado pelo rótulo de retenção na etapa 2. Por exemplo, Vida útil do produto. Somente o conteúdo com os rótulos de retenção aplicados a esse tipo de evento terá o período de retenção ativado.
  
![Opção em Configurações de evento para escolher um tipo de evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Etapa 7: Inserir palavras-chave ou IDs de ativo

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
A ID de Ativo é, simplesmente, mais uma propriedade do documento no SharePoint e no OneDrive. Se estiver usando a propriedade ID de ativo, você deverá digitar `ComplianceAssetID:<value>` na caixa para IDs de ativos mostrada abaixo.
  
Sua organização pode ter aplicado outras propriedades e IDs aos documentos relacionados a esse tipo de evento. Por exemplo, se for preciso detectar os registros de um produto específico, a ID pode ser uma combinação entre sua propriedade personalizada ProductID e o valor "XYZ". Nesse caso, você digitaria `ProductID:XYZ` na caixa para as IDs de Ativos mostradas abaixo.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
Por fim, escolha a data em que o evento ocorreu; essa data é usada como o início do período de retenção. Depois de criar um evento, essa data do evento é sincronizada para todo o conteúdo com um rótulo desse tipo de evento, ID do ativo e palavras-chave. Como ocorre com qualquer rótulo de retenção, essa sincronização poderá demorar até sete dias.
  
![Página Configurações de Eventos](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

> [!NOTE]
> Após a criação de um evento, as configurações de retenção entrarão em vigor para o conteúdo que já estiver rotulado e indexado. Se o rótulo de retenção for adicionado a um novo conteúdo após o evento ter sido criado, você precisará criar um novo evento com os mesmos dados.

A exclusão de um evento não cancela as configurações de retenção que já estão em vigor para o conteúdo já rotulado anteriormente. Para este fim, crie um novo evento com os mesmos dados, mas deixe a data em branco. 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo ou ID de ativo específicos

Após a atribuição dos rótulos de retenção ao conteúdo, você pode usar a pesquisa de conteúdo para localizar todo o conteúdo classificado com um rótulo de retenção específico ou que contenha uma ID de ativo específica:
  
- Para localizar todo o conteúdo com um rótulo de retenção específico, escolha a condição **Marca de conformidade** e, em seguida, digite o nome completo do rótulo ou parte dele e use um caractere curinga. 
    
- Para localizar todo o conteúdo com uma ID de ativo específica, digite a propriedade **ComplianceAssetID** e um valor, usando o formato `ComplianceAssetID:<value>`. 
    
Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Permissões

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
Para saber mais, consulte [Dar aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizar eventos usando o PowerShell

O centro de conformidade do Microsoft 365 permite que você crie eventos manualmente e não é compatível com o desencadeamento automático de um evento quando este ocorre. No entanto, você pode usar uma Rest API para desencadear os eventos automaticamente. Para obter mais informações, confira o artigo [Automatizar a retenção baseada em eventos](automate-event-driven-retention.md).

Também é possível usar um script do PowerShell para automatizar a retenção com base em eventos de aplicativos de negócios. Os cmdlets do PowerShell disponíveis para retenção controlada por eventos:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

