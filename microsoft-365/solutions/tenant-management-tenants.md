---
title: Etapa 1. Seus locatários do Microsoft 365 para empresas
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
ms.custom:
- Ent_Solutions
description: Implante e gerencie um ou vários locatários do Microsoft 365, com opções para localizações multi-geográficas e móveis.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908440"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Etapa 1. Seus locatários do Microsoft 365 para empresas

Uma de suas primeiras decisões de locatário é quantas ter. Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365. O locatário correspondente do Azure AD também é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.

## <a name="single-tenant"></a>Locatário único
Ter um único locatário simplifica muitos aspectos do uso do Microsoft 365 pela sua organização. Um único locatário significa um único locatário do Azure AD com um único conjunto de contas, grupos e políticas. As permissões e o compartilhamento de recursos em toda a organização podem ser feitos por meio deste provedor de identidade central.

Um único locatário fornece a melhor experiência de colaboração e produtividade de recursos e simplificada para seus usuários.

Veja um exemplo mostrando o local padrão e o locatário do Azure AD de um locatário do Microsoft 365.

![Um único locatário do Microsoft 365 com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Vários locatários

Há muitos motivos para sua organização ter vários locatários:

- Isolamento administrativo
- IT descentralizado
- Decisões históricas
- Fusões, aquisições ou destitures
- Separação clara da identidade visual para organizações de conglomerados
- Locatários de pré-produção, teste ou área de trabalho

Aqui está um exemplo de uma organização que tem dois locatários (Locatário A e Locatário B) na mesma área geográfica de datacenter padrão. Cada locatário como um locatário separado do Azure AD.

![Vários locatários do Microsoft 365 com seus próprios locatários do Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Quando você tem vários locatários, há restrições e considerações adicionais ao gere-los e fornecer serviços aos seus usuários.

### <a name="inter-tenant-collaboration"></a>Colaboração entre locatários

Se você quiser que os usuários colaborem com mais eficiência em diferentes locatários do Microsoft 365 de maneira segura, as opções de colaboração entre locatários incluem o uso de um local central para arquivos e conversas, o compartilhamento de calendários, o uso de mensagens de IM, chamadas de áudio/vídeo para comunicação e a segurança do acesso a recursos e aplicativos.

Para saber mais, confira a colaboração entre locatários do [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Migração de caixa de correio entre locatários (visualização)

Antes da migração de caixa de correio entre locatários (na visualização), ao mover caixas de correio do Exchange Online entre locatários, você precisa desemocarcar completamente uma caixa de correio de usuário de seu locatário atual (o locatário de origem) para o local e, em seguida, abordá-las a um novo locatário (o locatário de destino). Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais. Isso elimina a necessidade de remoção e integração de caixas de correio.

Aqui estão dois locatários de exemplo e suas caixas de correio antes da migração de caixa de correio entre locatários.

![Vários locatários do Microsoft 365 e suas caixas de correio](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

Nesta ilustração, dois locatários separados têm seus próprios domínios e conjunto de caixas de correio do Exchange.

Aqui está o locatário de destino (Locatário A) após a migração de caixa de correio entre locatários.

![O locatário de destino após a migração de caixa de correio entre locatários](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

Nesta ilustração, um único locatário tem domínios e ambos os conjuntos de caixas de correio do Exchange.

Para obter mais informações, consulte [Migração de caixa de correio entre locatários.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Migrações de locatário-para-locatário

Há várias abordagens arquitetônicas para fusões, aquisições, desaquetes e outros cenários que podem levar você a migrar um locatário existente do Microsoft 365 para um novo locatário. 

Para obter orientações detalhadas, confira migrações de locatário para locatário do [Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo para um locatário

Com o Microsoft 365 Multi-Geo, você pode provisionar e armazenar dados em repouso em outras localizações geográficas do datacenter que escolheu para atender aos requisitos de residência de dados e, ao mesmo tempo, desbloquear sua lançamento global de experiências modernas de produtividade para seus funcionários.

Em um ambiente multi-geo, seu locatário do Microsoft 365 consiste em um local padrão ou central onde sua assinatura do Microsoft 365 foi originalmente criada e um ou mais locais de satélite. Em um locatário multi-geo, as informações sobre localizações geográficas, grupos e informações do usuário são mestre em um locatário global do Azure AD. Como as informações do locatário são centralmente e sincronizadas em cada localização geográfica, as experiências de colaboração envolvendo qualquer pessoa da sua empresa são compartilhadas entre os locais.

Aqui está um exemplo de uma organização que tem sua localização padrão na Europa e uma localização satélite na América do Norte. Ambos os locais compartilham o mesmo locatário global do Azure AD para o único locatário do Microsoft 365.

![Exemplo de um locatário multi-geo do Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Para mais informações, consulte [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Movendo os dados principais para uma nova área geográfica de datacenter

A Microsoft continua a abrir novas áreas geográficas de datacenter para os serviços do Microsoft 365. Essas novas áreas geográficas de datacenter adicionam capacidade e recursos de computação para dar suporte à demanda contínua do cliente e ao crescimento do uso. Além disso, as novas áreas geográficas do datacenter oferecem residência de dados na área geográfica para dados principais do cliente.

Embora abrir uma nova área geográfica de datacenter não a impacte e seus dados principais armazenados em uma área geográfica de datacenter já existente, a Microsoft permite que você solicite uma migração antecipada dos principais dados do cliente da sua organização em repouso para uma nova área geográfica de datacenter.

Aqui está um exemplo em que um locatário do Microsoft 365 foi movido do datacenter da União Europeia (UE) para aquele localizado no Reino Unido (REINO UNIDO).

![Exemplo de movimentação de um locatário do Microsoft 365 entre a área geográfica do datacenter](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Para saber mais, confira Movendo os dados principais para a nova área geográfica do [datacenter do Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Produtos e licenças para um locatário

O locatário do Microsoft 365 é criado quando você compra seu primeiro produto, como o Microsoft 365 E3. Junto com o produto estão licenças, que são cobradas uma taxa mensal ou anual. Em seguida, um administrador atribui uma licença disponível de um de seus produtos a uma conta de usuário, diretamente ou por meio da associação a um grupo. Dependendo das necessidades comerciais da sua organização, você pode ter um conjunto de produtos, cada um com seu próprio pool de licenças. 

Determinar o conjunto de produtos e o número de licenças para cada um requer algum planejamento para:

- Verifique se você tem licenças suficientes para as contas de usuário que precisam de recursos avançados.
- Impedir que você ficar sem licenças ou ter muitas licenças não atribuídas, com base nas alterações no pessoal da sua organização.


## <a name="results-of-step-1"></a>Resultados da Etapa 1

Para os locatários do Microsoft 365 para empresas, você determinou:

- Quantos locatários você tem ou precisa.
- Para cada locatário, quais produtos e licenças devem ser comprados.
- Se um locatário precisa ser multi-geo para atender aos requisitos de residência de dados.
- Se você precisa configurar a colaboração entre locatários.
- Se você precisa migrar um locatário para outro.
- Se você precisa mover os dados principais de uma área geográfica de datacenter para uma nova.

Aqui está um exemplo de um novo locatário.

![Exemplo de um novo locatário](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

Nesta ilustração, o locatário tem:

- Um local padrão correspondente a uma área geográfica de datacenter do Microsoft 365.
- Um conjunto de produtos e licenças.
- O conjunto de aplicativos de produtividade na nuvem, alguns dos quais são específicos de produtos.
- Um locatário do Azure AD que contém contas de administrador global e um nome de domínio DNS inicial.

À medida que avançarmos pelas etapas adicionais desta solução, criaremos essa figura.

## <a name="ongoing-maintenance-for-tenants"></a>Manutenção contínua para locatários

Em uma base contínua, talvez seja necessário:

- Adicione um novo locatário.
- Adicione novos produtos a um locatário com um número inicial de licenças.
- Altere o conjunto de licenças de um produto em um locatário para ajustar para alterar os requisitos da equipe.
- Mova seus dados principais de um locatário para uma nova localização geográfica do datacenter.
- Adicione multi-geo para requisitos de residência de dados.
- Configurar a colaboração entre locatários.

## <a name="next-step"></a>Próxima etapa

[![Etapa 2. Otimizar seu locatário para rede para acesso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Continue com [a rede](tenant-management-networking.md) para fornecer rede ideal de seus funcionários para os serviços de nuvem do Microsoft 365.
