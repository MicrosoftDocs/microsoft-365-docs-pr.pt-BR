---
title: Plano do Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Saiba mais sobre o Microsoft 365 Multi-Geo, como a funcionalidade multigeográfica funciona e quais localizações geográficas estão disponíveis para armazenar dados.
ms.openlocfilehash: 1924141b86ba3e1c16e4760e0f40d61b6f47ce69
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687170"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Plano do Microsoft 365 Multi-Geo

Este guia foi projetado para os administradores de empresas multinacionais (MNCs) que estão preparando o locatário do Microsoft 365 para ser expandido para outras regiões de acordo com a presença da empresa para atender aos requisitos da residência dos dados.

Em uma configuração de várias regiões, o locatário do Microsoft 365 consiste de um local central e uma ou mais localizações por satélite. Este é um locatário único que se estende em várias localizações geográficas. Suas informações de locatário, incluindo localizações geográficas, são armazenadas no Azure Active Directory (AAD).

Vejamos alguns termos chave da multigeografia que o ajudarão a entender os conceitos básicos da configuração:

-   **Locatário** – A representação de uma organização no Microsoft 365 que normalmente possui um ou mais domínios associados à ela (por exemplo: https://contoso.sharepoint.com). 

-   **Localizações geográficas** – Localizações geográficas disponíveis para hospedar os dados em um locatário do Microsoft 365.

-   **Localizações por satélite** – Localizações geográficas adicionais configuradas para hospedar dados no seu locatário do Microsoft 365. Locatários multigeográficos abrangem mais do que uma localização geográfica, por exemplo, América do Norte e Europa.

-   **Local de Dados Preferencial (PDL)** – A localização geográfica onde os dados do OneDrive e do usuário individual do Exchange são armazenados. Isso pode ser definido pelo administrador, m qualquer localização geográfica configurada para o locatário. Observe que se você alterar a PDL para um usuário que já tenha um site do OneDrive, seus dados do OneDrive não serão movidos para a nova localização geográfica automaticamente. Confira [Mover uma biblioteca do OneDrive para uma localização geográfica diferente](move-onedrive-between-geo-locations.md) para saber mais. Se houver uma caixa de correio do Exchange, a caixa de correio é movida para o novo local de dados preferencial automaticamente.

Habilitar a multigeografia requer quatro etapas principais:

1.  Trabalhe com sua equipe de conta para adicionar os _Recursos de várias áreas geográficas no plano de serviço do Microsoft 365_.

2.  Escolha a(s) localização(ões) geográfica(s) satélite(s) desejada(s) e adicione-a(s) ao seu locatário.

3.  Defina o local preferencial dos dados dos usuários para a localização de satélite desejada. Quando um novo site do OneDrive ou caixa de correio do Exchange está provisionada para um usuário, está provisionado para sua PDL.

4.  Migre os seus sites existentes do OneDrive dos usuários do local central para o local de dados preferencial conforme necessário. (As caixas de correio do Exchange são migradas automaticamente quando você define o PDL do usuário.)

Consulte [Configurar o Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md) para obter detalhes de cada uma dessas etapas.

> [!IMPORTANT]
> Observe que o Microsoft 365 Multi-Geo não foi projetado para a otimização de desempenho, ele foi projetado para atender aos requisitos da residência de dados. Para obter mais informações sobre a otimização de desempenho do Microsoft 365, consulte [Planejamento de rede e ajuste de desempenho do Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) ou entre em contato com seu grupo de suporte.

Você pode configurar qualquer uma das seguintes localizações para ser de satélite onde você pode hospedar o OneDrive, sites do SharePoint e caixas de correio do Exchange. Ao planejar a região geográfica, faça uma lista dos locais que quer adicionar ao seu locatário do Microsoft 365. Recomendamos começar com um ou dois locais de satélite e expandir gradualmente para mais localizações geográficas, se necessário.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Ao configurar a multigeografia, considere aproveitar a oportunidade para consolidar sua infraestrutura local ao migrar para o Microsoft 365. Por exemplo, se você tiver fazendas locais em Cingapura e na Malásia, poderá consolidá-las na localização por satélite da APC, pois os requisitos da residência de dados fornecidos permitem que você faça isso.

## <a name="best-practices"></a>Práticas recomendadas

Recomendamos que você crie um usuário de teste no Microsoft 365 para fazer alguns testes iniciais. Analisaremos algumas etapas de testes e de verificação com esse usuário antes de passar aos usuários da produção integrada do Microsoft 365 Multi-Geo.

Depois de concluir os testes com o usuário de teste, selecione um grupo piloto – talvez do departamento de TI – para ser o primeiro a usar o OneDrive e o Exchange em uma nova localização geográfica. Para esse primeiro grupo, selecione os usuários que ainda não tem do OneDrive. É recomendável não mais do que cinco pessoas neste grupo inicial e expanda-o gradualmente seguindo uma abordagem de implantação em lote.

Cada usuário deve ter um *local de dados preferido* (PDL) definido para que o Microsoft 365 possa determinar em qual local geográfico provisionar seu OneDrive. O local de dados preferido do usuário deve corresponder a uma das localizações por satélite escolhidas ou ao local central. Embora o campo PDL não seja obrigatório, recomendamos que um PDL seja definido para todos os usuários. As cargas de trabalho de um usuário sem uma PDL serão provisionadas no local central.

Crie uma lista dos seus usuários e inclua o nome UPN e o código de local para o local de dados preferencial adequado. Inclua o seu usuário de teste e o seu grupo piloto inicial para começar. Você precisará dessa lista para os procedimentos de configuração.

Se os usuários serão sincronizados com um sistema do Active Directory local ao Azure Active Directory, você deve definir o local de dados preferencial como um atributo Active Directory e sincronizá-lo usando o Azure Active Directory Connect. Você não pode configurar o local de dados preferencial diretamente para os usuários sincronizados usando o Azure AD PowerShell. As etapas para configurar a PDL no Active Directory e sincronizá-lo são abordadas na sincronização do [Azure Active Directory Connect: Configurar o local de dados preferido dos recursos do Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

A administração de um locatário multigeográfico pode variar de um locatário que não seja de multigeografia, pois muitos dos serviços e configurações do SharePoint e do OneDrive detectam a multigeografia. Recomendamos que leia [Administrar um ambiente multigeográfico](administering-a-multi-geo-environment.md) antes de prosseguir com a configuração.

Leia em [Experiência do usuário em um ambiente multigeográfico](multi-geo-user-experience.md) detalhes sobre a experiência dos usuários finais em um ambiente multigeográfico.

Para obter mais detalhes sobre a experiência do Teams em um locatário do Microsoft 365 Multi-Geo, consulte [Experiência do Teams em um local multigeográfico habilitado do Microsoft 365 OneDrive e do SharePoint Online](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo).

Para começar a configurar o Microsoft 365 Multi-Geo, consulte [Configurar o Microsoft 365 Multi-Geo](multi-geo-tenant-configuration.md).

Depois de concluir a configuração, lembre-se de [migrar as bibliotecas do OneDrive dos seus usuários](move-onedrive-between-geo-locations.md) conforme necessário para que os usuários possam trabalhar dos locais de dados preferenciais.
