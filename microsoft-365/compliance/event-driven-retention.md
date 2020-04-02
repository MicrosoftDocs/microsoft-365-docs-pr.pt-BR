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
description: Com os rótulos de retenção, você pode basear um período de retenção no momento que um tipo específico de evento ocorre. O evento dispara o início do período de retenção, e todo o conteúdo com um rótulo de retenção aplicado para esse tipo de evento recebe as ações de retenção do rótulo. A retenção controlada por eventos é usada como parte de um processo de gerenciamento de registros.
ms.openlocfilehash: 4389f3639de3e9e036491026455ce62a9e258432
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105618"
---
# <a name="overview-of-event-driven-retention"></a>Visão geral da retenção controlada por eventos

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Quando você retém o conteúdo, o período de retenção normalmente é baseado na idade desse conteúdo. Por exemplo, você pode reter os documentos por sete anos após a criação e, depois disso, excluí-los. Porém, com os rótulos de retenção no Office 365, também é possível basear um período de retenção no momento em quando um tipo específico de evento ocorre. O evento dispara o início do período de retenção, e todo o conteúdo com um rótulo de retenção aplicado para esse tipo de evento recebe as ações de retenção do rótulo.
  
Por exemplo, você pode usar rótulos com a retenção controlada por eventos para:
  
- **Funcionários que estão saindo da organização** Vamos supor que os registros devam ser retidos por dez anos após um funcionário sair da organização. Decorridos os dez anos, é necessário descartar todos os documentos relacionados à contratação, desempenho e rescisão desse funcionário. O evento que aciona o período de retenção de dez anos é a saída do funcionário da organização. 
    
- **Expiração do contrato** Suponhamos que todos os registros relacionados aos contratos precisem ser retidos por cinco anos a partir da expiração do contrato. O evento que dispara o período de retenção de cinco anos é a expiração do contrato. 
    
- **Vida útil do produto** Talvez sua organização tenha exigências de retenção relacionadas à última data de produção de produtos para determinados conteúdos, como especificações técnicas. Nesse caso, a última data de produção é o evento que dispara o período de retenção. 
    
Normalmente, a retenção controlada por eventos é usada como parte de um processo de gerenciamento de registros. Isso significa que:
  
- Geralmente, os rótulos baseados em eventos também classificam o conteúdo como registro. Para saber mais, consulte [Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo de retenção específico aplicado](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Um documento declarado como um registro, mas cujo gatilho de evento ainda não aconteceu, é retido indefinidamente (registros não podem ser excluídos permanentemente), até que um evento dispare o período de retenção desse documento.
    
- Rótulos com base em eventos frequentemente disparam uma revisão de disposição ao final do período de retenção, para que um gerente de registros possa revisar e descartar manualmente o conteúdo. Para saber mais, consulte [Visão geral das revisões de disposição](disposition-reviews.md).
    
Um rótulo baseado em um evento tem os mesmos recursos que qualquer rótulo no Office 365. Para saber mais, consulte [Visão geral dos rótulos](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Compreender a relação entre tipos de eventos, rótulos, eventos e IDs de ativos

Para usar a retenção controlada por eventos, é importante compreender a relação entre tipos de evento, rótulos, eventos e IDs de ativo, conforme ilustrado aqui. Veja uma explicação após o diagrama.
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Crie rótulos para tipos diferentes de conteúdo e associe-os a um tipo de evento. Por exemplo, rótulos para tipos diferentes de arquivos e registros de produtos são associados a um tipo de evento chamado Tempo de vida do produto, pois esses registros devem ser retidos por 10 anos a partir do momento em que o produto atinge o final da vida útil.
    
2. Os usuários (normalmente gerentes de registros) aplicam esses rótulos ao conteúdo e, para documentos do SharePoint e do OneDrive, inserem uma ID de ativo para cada item. Neste exemplo, a ID de ativo é um nome ou um código de produto usado pela organização. Dessa forma, os registros de cada produto recebem um rótulo, e cada registro tem uma propriedade que contém uma ID de ativo. O diagrama representa **todo o conteúdo** de todos os registros de produtos em uma organização, e cada item contém a ID de ativo do produto no qual está o registro. 
    
3. Tempo de vida do produto é o tipo de evento; um produto específico que chega ao fim da vida útil é um evento. Quando ocorre um evento desse tipo, neste caso, quando um produto atinge o final da vida útil, você cria um evento que especifica:
    
  - Uma ID de ativo (para documentos do SharePoint e do OneDrive)
    
  - Palavras-chave (para itens do Exchange). Neste exemplo, a organização usa um código de produto em mensagens que contêm registros de produto, assim, a palavra-chave para itens do Exchange é igual à ID de ativos de documentos do SharePoint e do OneDrive.
    
  - A data de ocorrência do evento. Essa data é utilizada como o início do período de retenção. Essa data pode ser a atual, do passado ou futura.
    
4. Após a criação de um evento, a data do evento é sincronizada com todo o conteúdo que apresenta um rótulo desse tipo de evento e que contém a ID de ativo ou uma palavra-chave especificadas. Como ocorre com qualquer rótulo, essa sincronização pode demorar até sete dias. No diagrama acima, o período de retenção de todos os itens marcados em vermelho é acionado, ou seja, quando este produto atinge o final da vida útil, esse evento aciona o período de retenção para registros do produto.
    
É importante entender que se você não especificar uma ID de ativo ou palavras-chave para um evento, o período de retenção de **todo o conteúdo** com um rótulo desse tipo de evento será disparado pelo evento. Isso significa que, no diagrama acima, todo o conteúdo seria retido. Talvez essa não seja sua intenção. 
  
Por fim, lembre-se de que cada rótulo tem suas próprias configurações de retenção. Neste exemplo, todos especificam 10 anos, mas é possível que um evento acione rótulos com períodos de retenção diferentes.
  
## <a name="how-to-set-up-event-driven-retention"></a>Como configurar a retenção controlada por eventos

Este é o fluxo de trabalho de nível superior para retenção controlada por eventos. Consulte etapas mais detalhadas abaixo.
  
![Diagrama de fluxo de trabalho para configurar a retenção controlada por eventos](../media/161146d9-e0fc-4248-abc1-a18045eaad5c.png)
  
> [!TIP]
> Consulte [Gerenciar o ciclo de vida dos documentos do SharePoint com rótulos de retenção](auto-apply-retention-labels-scenario.md) para obter um cenário detalhado sobre como usar as propriedades gerenciadas no SharePont para aplicar automaticamente os rótulos de retenção e implementar a retenção voltada para o evento.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Etapa 1: Criar um rótulo cujo período de retenção seja baseado em um evento

Na central de conformidade do Microsoft 365, na central de segurança do Microsoft 365 ou na Central de Conformidade de&amp; Segurança do Office 365, na navegação à esquerda, escolha **Classificações** > **Rótulos de retenção** > **Rótulos** guia > **Criar um rótulo**.
  
Ao criar o rótulo, ative a retenção e escolha a opção exibida abaixo para reter ou excluir o conteúdo com base em um evento. Isso significa que as configurações de retenção não entrarão em vigor até a Etapa 5, quando você criar um evento na página **Eventos**. 
  
Observe que a retenção controlada por eventos geralmente é usada para o conteúdo classificado como registro. Por esse motivo, ao criar rótulos com base em um evento, você normalmente escolhe a opção **Usar rótulo para classificar o conteúdo como um "Registro"**.
  
Saiba também que a retenção controlada por eventos exige configurações de retenção que:
  
- Retêm o conteúdo.
    
- Excluem o conteúdo automaticamente, ou acionam uma revisão de disposição ao final do período de retenção.
    
![Opção para basear um rótulo em um evento](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Etapa 2: Escolher um tipo de evento para esse rótulo

Nas configurações de rótulo, após escolher a opção para basear o rótulo em **um evento**, você verá a opção **Escolher um tipo de evento**. Um tipo de evento é simplesmente uma descrição geral de um evento ao qual você deseja associar um rótulo.
  
Por exemplo, se você criar um evento chamado Tempo de vida do produto, criará os rótulos baseados em eventos com nomes que descrevem a quais tipos de conteúdo você deseja aplicar os rótulos, como "Arquivos de desenvolvimento de produto" ou "Registros de decisões comerciais sobre o produto".
  
Observe que após escolher um tipo de evento e criar o rótulo, o tipo de evento não pode ser alterado.
  
![Opções para criar ou escolher um tipo de evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-label"></a>Etapa 3: Publicar ou aplicar automaticamente o rótulo

Assim como qualquer rótulo, você precisa publicar ou aplicar automaticamente um rótulo com base em eventos, para que ele seja aplicado manual ou automaticamente ao conteúdo. Você pode fazer isso na página **Rótulos de** > **retenção** de classificação.
  
![Opções para publicar ou aplicar automaticamente um rótulo](../media/options-to-publish-auto-apply-retention-label.png)

### <a name="step-4-enter-an-asset-id"></a>Etapa 4: Inserir uma ID de ativo

Após a aplicação de um rótulo controlado por evento ao conteúdo, você pode inserir uma ID de ativo para cada item. Por exemplo, sua organização pode usar:
  
- Códigos de produto que você pode usar para reter o conteúdo apenas de um produto específico.
    
- Códigos de projeto que você pode usar para reter o conteúdo apenas de um projeto específico.
    
- IDs de funcionário que você pode usar para reter o conteúdo apenas de uma pessoa específica.
    
Compreenda que a ID de ativo é simplesmente outra propriedade do documento no SharePoint e no OneDrive for Business. Talvez sua organização já use outras propriedades e IDs de documento para classificar o conteúdo. Se este for o caso, você também pode usar essas propriedades e valores ao criar um evento; consulte a Etapa 6 abaixo. O importante é que sua organização deve usar uma combinação de propriedade e valor nas propriedades do documento para associar esse item a um tipo de evento.
  
![Caixa de texto para inserir uma ID de ativo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Etapa 5: Criar um evento

Quando uma instância específica desse tipo de evento ocorrer, por exemplo, um produto chega ao fim de sua vida útil, acesse a página **Eventos de gerenciamento** > **de registros** no Centro &amp; de conformidade de segurança e crie um evento. Você precisa acionar manualmente um evento ao criá-lo.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Etapa 6: Escolher o mesmo tipo de evento usado pelo rótulo na Etapa 2

Ao criar o evento, escolha o mesmo tipo de evento usado pelo rótulo na Etapa 2. Por exemplo, Tempo de vida de produto. Somente o conteúdo com rótulos desse tipo de evento aplicados terão o período de retenção acionado.
  
![Opção em Configurações de evento para escolher um tipo de evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Etapa 7: Inserir palavras-chave ou IDs de ativo

Agora, restrinja o escopo do conteúdo especificando as IDs de ativo para o conteúdo do SharePoint e do OneDrive ou palavras-chave para conteúdo do Exchange. Para IDs de ativo, a retenção será imposta somente no conteúdo com o par de propriedade:valor especificado. Se uma ID de ativo não for inserida, **todo o conteúdo** com rótulos desse tipo de evento receberá a mesma data de retenção. 
  
Compreenda que a ID de ativo é simplesmente outra propriedade de documento no SharePoint e no OneDrive for Business. Se você estiver usando a propriedade ID de ativo, digite ComplianceAssetID:\<valor\> na caixa de IDs de ativo mostrada abaixo.
  
Talvez sua organização tenha aplicado outras propriedades e IDs aos documentos relacionados a esse tipo de evento. Por exemplo, se você precisar detectar os registros de um produto específico, a ID poderá ser uma combinação de sua propriedade personalizada, ProductID, e o valor "XYZ". Nesse caso, você digitaria ProductID:XYZ na caixa de IDs de ativo mostrada abaixo.
  
Para itens do Exchange, você pode incluir palavras-chave. Refine a consulta usando os operadores de pesquisa E, OU e NÃO. Para saber mais sobre operadores, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).
  
Por fim, escolha a data de ocorrência do evento; essa data é usada como o início do período de retenção. Após a criação de um evento, essa data de evento é sincronizada com todo o conteúdo que tem um rótulo desse tipo de evento, ID de ativo e palavras-chave. Como ocorre com qualquer rótulo, essa sincronização pode demorar até sete dias.
  
![Página Configurações de evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo ou ID de ativo específicos

Após a atribuição dos rótulos ao conteúdo, você pode usar a pesquisa de conteúdo para localizar todo o conteúdo classificado com um rótulo específico ou que contenha uma ID de ativo específica.
  
Ao criar uma pesquisa de conteúdo:
  
- Para localizar todo o conteúdo com um rótulo específico, escolha a condição **Marca de conformidade** e, em seguida, insira o nome completo do rótulo ou parte do nome do rótulo e use um caractere curinga. 
    
- Para localizar todo o conteúdo com uma ID de ativo específica, insira a propriedade **ComplianceAssetID** e um valor, por exemplo, ComplianceAssetID:\<valor\>. 
    
Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Permissões

Para acessar a página **Eventos**, os revisores devem ser membros de um grupo com a função **Gerenciamento de disposição** e a função **Logs de auditoria somente para exibição**. Recomendamos criar um novo grupo de funções denominado Revisores de disposição, adicionar essas duas funções a esse grupo e incluir membros ao grupo de funções. 
  
Para saber mais, consulte [Dar aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizar eventos usando o PowerShell

No Centro de administração, você só pode criar eventos manualmente; não é possível acionar automaticamente um evento. No entanto, você pode usar uma API de REST para acionar eventos automaticamente; para saber mais, confira [Automatizar a retenção baseada em eventos](automate-event-driven-retention.md).

Também é possível usar um script do PowerShell para automatizar a retenção com base em eventos de aplicativos de negócios. Estes são os cmdlets do PowerShell disponíveis para retenção controlada por eventos:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

