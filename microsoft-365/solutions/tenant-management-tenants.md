---
title: Etapa 1. Seu Microsoft 365 para locatários corporativos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implante e gerencie locatários do Microsoft 365 simples ou múltiplos, com opções para locais multi-geo e móveis.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406379"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Etapa 1. Seu Microsoft 365 para locatários corporativos

Uma de suas primeiras decisões de locatários é quantas ter. Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365. O locatário correspondente do Azure AD também é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.

## <a name="single-tenant"></a>Locatário único
Ter um único locatário simplifica muitos aspectos do uso do Microsoft 365 pela sua organização. Um único locatário significa um único locatário do Azure AD com um único conjunto de contas, grupos e políticas. As permissões e o compartilhamento de recursos em toda a sua organização podem ser feitas por meio deste provedor de identidade central.

Um único locatário fornece a experiência de produtividade e colaboração mais rica em recursos e simplificada para seus usuários.

Aqui está um exemplo mostrando o local padrão e o locatário do Azure AD de um locatário do Microsoft 365.

![Um único locatário do Microsoft 365 com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Vários locatários

Há muitos motivos pelos quais sua organização pode ter vários locatários:

- Isolamento administrativo
- IT descentralizada
- Decisões históricas
- Fusões, aquisições ou desinvestções
- Limpar a separação de identidade visual para organizações de multinacionais
- Locatários de pré-produção, teste ou área de trabalho

Aqui está um exemplo de uma organização que tem dois locatários (Locatário A e Locatário B) no mesmo datacenter padrão geo. Cada locatário como um locatário separado do Azure AD.

![Vários locatários do Microsoft 365 com seus próprios locatários do Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Quando você tem vários locatários, há restrições e considerações adicionais ao gere-los e fornecer serviços aos seus usuários.

### <a name="inter-tenant-collaboration"></a>Colaboração entre locatários

Se você quiser que seus usuários colaborem de forma mais eficiente em diferentes locatários do Microsoft 365 de forma segura, as opções de colaboração entre locatários incluem o uso de um local central para arquivos e conversas, compartilhamento de calendários, uso de mensagens de IM, chamadas de áudio/vídeo para comunicação e acesso a recursos e aplicativos.

Para obter mais informações, consulte Colaboração entre locatários do [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Migração de caixa de correio entre locatários (visualização)

Antes da migração de caixa de correio entre locatários (em visualização), ao mover caixas de correio do Exchange Online entre locatários, você precisa deslocar completamente uma caixa de correio de usuário de seu locatário atual (o locatário de origem) para o local e, em seguida, abordá-las para um novo locatário (o locatário de destino). Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários em locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais. Isso remove a necessidade de retirada e integração de caixas de correio.

Aqui estão dois locatários de exemplo e suas caixas de correio antes da migração de caixa de correio entre locatários.

![Vários locatários do Microsoft 365 e suas caixas de correio](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

Nesta ilustração, dois locatários separados têm seus próprios domínios e um conjunto de caixas de correio do Exchange.

Aqui está o locatário de destino (Locatário A) após a migração de caixa de correio entre locatários.

![O locatário de destino após a migração de caixa de correio entre locatários](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

Nesta ilustração, um único locatário tem domínios e ambos os conjuntos de caixas de correio do Exchange.

Para obter mais informações, consulte Migração de caixa [de correio entre locatários](../enterprise/cross-tenant-mailbox-migration.md).

### <a name="tenant-to-tenant-migrations"></a>Migrações de locatário-para-locatário

Há várias abordagens de arquitetura para fusões, aquisições, desinvestres e outros cenários que podem levar você a migrar um locatário existente do Microsoft 365 para um novo locatário. 

Para obter orientações detalhadas, consulte Migrações de locatário [para locatário do Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo para um locatário

Com o Microsoft 365 Multi-Geo, você pode provisionar e armazenar dados em repouso nos outros locais geo do datacenter que você escolheu para atender aos requisitos de residência de dados e, ao mesmo tempo, desbloquear sua versão global de experiências de produtividade modernas para seus funcionários.

Em um ambiente Multi-Geo, seu locatário do Microsoft 365 consiste em um local padrão ou central onde sua assinatura do Microsoft 365 foi originalmente criada e um ou mais locais de satélite. Em um locatário multi-geo, as informações sobre localizações geográficas, grupos e informações do usuário são dominadas em um locatário global do Azure AD. Como as informações do locatário são dominadas centralmente e sincronizadas em cada localização geográfica, as experiências de colaboração envolvendo qualquer pessoa da sua empresa são compartilhadas entre os locais.

Aqui está um exemplo de uma organização que tem sua localização padrão na Europa e um local de satélite na América do Norte. Ambos os locais compartilham o mesmo locatário global do Azure AD para o único locatário do Microsoft 365.

![Exemplo de um locatário multi-geo do Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Para mais informações, consulte [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Mover dados principais para um novo datacenter geo

A Microsoft continua a abrir novas geos do datacenter para serviços do Microsoft 365. Esses novos geos do datacenter adicionam capacidade e recursos de computação para dar suporte à nossa demanda e ao crescimento de uso do cliente em andamento. Além disso, os novos geos do datacenter oferecem residência de dados no geo para dados principais do cliente.

Embora abrir um novo datacenter geo não impacte você e seus dados principais armazenados em um datacenter já existente, a Microsoft permite que você solicite uma migração antecipada dos dados principais do cliente da sua organização em repouso para um novo datacenter geo.

Aqui está um exemplo no qual um locatário do Microsoft 365 foi movido do datacenter da União Europeia (UE) geo para aquele localizado no Reino Unido (Reino Unido).

![Exemplo de movimentação de um locatário do Microsoft 365 entre geos do datacenter](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Para obter mais informações, consulte Movendo dados principais para novas geos do [datacenter do Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Produtos e licenças para um locatário

Seu locatário do Microsoft 365 é criado quando você compra seu primeiro produto, como o Microsoft 365 E3. Junto com o produto estão licenças, que são cobradas uma taxa mensal ou anual. Em seguida, um administrador atribui uma licença disponível de um de seus produtos a uma conta de usuário, diretamente ou por meio da associação ao grupo. Dependendo das necessidades comerciais da sua organização, você pode ter um conjunto de produtos, cada um com seu próprio pool de licenças. 

Determinar o conjunto de produtos e o número de licenças para cada um requer algum planejamento para:

- Verifique se você tem licenças suficientes para as contas de usuário que precisam de recursos avançados.
- Impedir que você se esvaia de licenças ou ter muitas licenças não atribuídas, com base em alterações no pessoal em sua organização.


## <a name="results-of-step-1"></a>Resultados da Etapa 1

Para seus locatários do Microsoft 365 para empresas, você determinou:

- Quantos locatários você tem ou precisa.
- Para cada locatário, quais produtos e licenças devem ser comprados.
- Se um locatário precisa ser Multi-Geo para atender aos requisitos de residência de dados.
- Se você precisa configurar a colaboração entre locatários.
- Se você precisa migrar um locatário para outro.
- Se você precisa mover os dados principais de um datacenter geo para um novo.

Aqui está um exemplo de um novo locatário.

![Exemplo de um novo locatário](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

Nesta ilustração, o locatário tem:

- Um local padrão correspondente a um datacenter do Microsoft 365 geo.
- Um conjunto de produtos e licenças.
- O conjunto de aplicativos de produtividade na nuvem, alguns dos quais são específicos para produtos.
- Um locatário do Azure AD que contém contas de administrador global e um nome de domínio DNS inicial.

Conforme passamos pelas etapas adicionais dessa solução, criaremos essa figura.

## <a name="ongoing-maintenance-for-tenants"></a>Manutenção contínua para locatários

Em uma base contínua, talvez seja necessário:

- Adicione um novo locatário.
- Adicione novos produtos a um locatário com um número inicial de licenças.
- Altere o conjunto de licenças de um produto em um locatário para ajustar para alterar os requisitos da equipe.
- Mova seus dados principais de um locatário para uma nova localização geográfica do datacenter.
- Adicione Multi-Geo para requisitos de residência de dados.
- Configurar a colaboração entre locatários.

## <a name="next-step"></a>Próxima etapa

[![Etapa 2. Otimizar seu locatário para acesso à rede](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Continue com [a rede](tenant-management-networking.md) para fornecer uma rede ideal de seus funcionários para os serviços de nuvem do Microsoft 365.
