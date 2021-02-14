---
title: Administrar um ambiente multigeográfico
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
description: Os administradores podem saber mais sobre como administrar os serviços do SharePoint e do OneDrive em um ambiente multi-geo.
ms.openlocfilehash: 1b6d2cb1cb9511677f717f0e58553abc4473e1ad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686916"
---
# <a name="administering-a-multi-geo-environment"></a>Administrar um ambiente multigeográfico

A seguir, veja como os serviços do Microsoft 365 funcionam em um ambiente com várias regiões geográficas.

## <a name="audit-log-search"></a>Pesquisa de log de auditoria

Um [Log de auditoria](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificado para todas as localizações por satélite está disponível na página de pesquisa do log de auditoria do Microsoft 365. Você pode ver todas as entradas do log de auditoria nas localizações geográficas, por exemplo, atividades dos usuários das localizações NAM e EUR serão exibidos em um modo de exibição de organograma e você poderá aplicar os filtros existentes para ver atividades de usuários específicos.

## <a name="bcs-secure-store-apps"></a>BCS, Repositório Seguro, Aplicativos

A BCS, o Repositório Seguro e os Aplicativos têm instâncias geográficas em cada localização satélite e portanto, o administrador do SharePoint Online deve gerenciar e configurar esses serviços separadamente para cada localização satélite.

## <a name="ediscovery"></a>Descoberta eletrônica 

Por padrão, um Administrador ou Gerente de Descoberta Eletrônica de um locatário multigeográfico só poderá realizar a descoberta eletrônica na localização central desse locatário. O administrador global do Office 365 deve atribuir permissões de gerente de Descoberta Eletrônica para permitir que outras pessoas possam realizá-la e atribuir o parâmetro "Região" no Filtro de Segurança e Conformidade deles, para especificar a região como uma localização no satélite para a realização da Descoberta. Caso contrário, a Descoberta Eletrônica não será realizada para nenhuma localização no satélite. Para configurar o Filtro de Segurança de Conformidade para uma Região, consulte [Configurar a Descoberta Eletrônica Multigeográfica do Office 365](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Caixas de correio do Exchange

As caixas de correio dos usuários do Exchange são movidas automaticamente se sua PDL for alterado. Quando uma nova caixa de correio é criada, ela está provisionada ao PDL do usuário ou à localização central se nenhum valor foi definido para o PDL do usuário.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Política de Prevenção contra Perda de Dados (DLP) e Proteção da Informação (IP). 

Você pode definir sua política DLP IP para o OneDrive for Business, SharePoint e Exchange no centro de Segurança e Conformidade políticas de definição de escopo, conforme necessário, para todo locatário ou para os usuários aplicáveis. Por exemplo: se você quiser selecionar uma política para um usuário em uma localização via satélite, selecione para aplicar a política para o OneDrive específico e insira a url do OneDrive do usuário. Confira [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) para instruções gerais ao criar políticas DLP.

As políticas de DLP são sincronizadas automaticamente de acordo com a aplicabilidade delas a cada localização geográfica.

A implementação de políticas de Prevenção contra Perda de Dados e Proteção da Informação para todos os usuários em uma localização geográfica não é uma opção disponível na IU. Em vez disso, é preciso selecionar as contas em que se deseja aplicar a política ou aplicá-la de modo global a todas as contas.

## <a name="microsoft-flow"></a>Microsoft Flow

Fluxos criados para localização via satélite usarão o ponto de extremidade localizado na localização geográfica padrão do locatário.  Microsoft Flow não é um serviço Multigeográfico. 

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps criados para localização via satélite usarão o ponto de extremidade localizado na localização central do locatário. Microsoft PowerApps não é um serviço Multigeográfico. 

## <a name="onedrive-administrator-experience"></a>Experiência de Administrador do OneDrive

O [Centro de Administração do OneDrive](https://admin.onedrive.com) tem uma guia de **localizações geográficas** na navegação à esquerda, que apresenta um mapa com os locais onde é possível exibir e gerenciar suas localizações geográficas. Use essa página para adicionar ou excluir as localizações geográficas de seu locatário.

## <a name="security-and-compliance-admin-center"></a>Centro de Administração de Conformidade e Segurança

Há um centro de conformidade central para um locatário multigeográfico: [Centro de conformidade e segurança do Microsoft 365](https://protection.office.com/?rfr=AdminCenter\#/homepage).

## <a name="sharepoint-storage-quota"></a>Cota de armazenamento do SharePoint

Por padrão, todas as localizações geográficas de um ambiente multigeográfico compartilham a cota de armazenamento disponível do locatário.  Também é possível gerenciar a cota de armazenamento alocando uma cota específica de uma localização geográfica específica. Para saber mais, confira [Cotas de armazenamento do SharePoint em ambientes de multigeográfico](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Compartilhamento

Os administradores podem configurar e gerenciar políticas de compartilhamento para cada localização. Os sites do OneDrive e do SharePoint em cada localização geográfica aceita apenas as configurações de compartilhamen específica da área geográfica correspondente. (Por exemplo, você pode permitir o [compartilhamento externo](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) para a localização central, mas não a localização via satélite ou vice-versa.) Observe que as configurações de compartilhamento não permitem configurar limitações de compartilhamento entre localizações geográficas.

## <a name="taxonomy"></a>Taxonomia

Oferecemos suporte para uma visão completa [taxonomia](https://docs.microsoft.com/sharepoint/managed-metadata) para metadados gerenciados por empresas em localizações geográficas com o mestre hospedado na localização central da sua empresa. Recomendamos que você gerencie sua taxonomia global de uma localização central e apenas adicione termos específicos de localização para a Taxonomia da localização via satélite. Termos de taxonomia global serão sincronizadas para as ocalizações via satélite.

Confira [Gerenciar metadados em um locatário multigeográfico](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-managedmetadata) para saber mais e para obter instruções do desenvolvedor.

## <a name="user-profile-application"></a>Aplicativo de Perfil de Usuário

Há um [aplicativo de perfil de usuário](https://docs.microsoft.com/sharepoint/manage-user-profiles) em cada localização geográfica. As informações de perfil de cada usuário estão hospedadas na localização geográfica dele e ficam disponíveis para o administrador daquela localização.

Se houver propriedades de perfil personalizadas, recomendamos que você use o mesmo esquema de perfil nas localizações e popule as propriedades personalizadas em cada uma delas ou nas que forem necessárias.  Para obter instruções sobre como preencher dados de perfil de usuário de forma programática, confira a [API de Atualização de Perfil de Usuário em Massa](https://docs.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Confira [Trabalhar com perfis de usuários em um locatário multigeográfico](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) para saber mais e para obter instruções do desenvolvedor.

## <a name="video-portal"></a>Portal de Vídeo

Em um locatário multigeográfico, o Portal de Vídeo do O365 só é disponibilizado para a localização geográfica padrão e todos os usuários serão redirecionados para essa url portal central. Dessa forma, os Serviços de Mídia Remoto (RMS) para essa região serão usados, da seguinte forma, com base em uma localização central.

Atualmente, este aplicativo está disponível nas seguintes regiões:

- América do Norte, hospedada nos Estados Unidos 
- Europa
- Pacífico Asiático

Porém, atualmente, o Stream ainda não está disponível nas seguintes regiões com suporte para o Microsoft 365 Video, portanto, para essas instâncias locais, usaremos o RMS que está na região suportada mais próxima.

- Austrália
- Canadá
- Índia
- Reino Unido

## <a name="yammer"></a>Yammer

O Yammer não é uma carga de trabalho multi-geográfica. Os threads do Yammer armazenados no Yammer serão colocados no local central do locatário. O Yammer está lançando uma alteração de armazenamento de arquivos que armazenará arquivos do Yammer no SharePoint. Os arquivos do Yammer armazenados no SharePoint serão colocados no site do SharePoint associado ao grupo do Yammer. Os sites de grupo do SharePoint são baseados na lógica PDL, conforme descrito em [Sites e Grupos do SharePoint.](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)
