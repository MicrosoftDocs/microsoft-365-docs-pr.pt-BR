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
description: Os administradores podem aprender sobre como administrar serviços SharePoint e OneDrive em um ambiente multi-geo.
ms.openlocfilehash: 9ef22a34881ef5c9c2ed72835bc88c1dbfe835b5
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363938"
---
# <a name="administering-a-multi-geo-environment"></a>Administrar um ambiente multigeográfico

A seguir, veja como os serviços do Microsoft 365 funcionam em um ambiente com várias regiões geográficas.

## <a name="administrator-experience"></a>Experiência do administrador

O [SharePoint de](https://admin.microsoft.com/sharepoint) administração tem uma guia **Localizações** geográficas na navegação à esquerda, que apresenta um mapa de localizações geográficas onde você pode exibir e gerenciar suas localizações geográficas. Use esta página para adicionar ou excluir localizações geográficas para seu locatário.

## <a name="audit-log-search"></a>Pesquisa de log de auditoria

Um [Log de auditoria](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificado para todas as localizações por satélite está disponível na página de pesquisa do log de auditoria do Microsoft 365. Você pode ver todas as entradas do log de auditoria nas localizações geográficas, por exemplo, atividades dos usuários das localizações NAM e EUR serão exibidos em um modo de exibição de organograma e você poderá aplicar os filtros existentes para ver atividades de usuários específicos.

## <a name="bcs-secure-store-apps"></a>BCS, Repositório Seguro, Aplicativos

A BCS, o Repositório Seguro e os Aplicativos têm instâncias geográficas em cada localização satélite e portanto, o administrador do SharePoint Online deve gerenciar e configurar esses serviços separadamente para cada localização satélite.

## <a name="compliance-admin-center"></a>Centro de administração de conformidade

Há um centro de conformidade central para um locatário multi-geo: Microsoft 365 [Centro de administração de Conformidade.](https://compliance.microsoft.com/)

## <a name="ediscovery"></a>Descoberta eletrônica

Por padrão, um Administrador ou Gerente de Descoberta Eletrônica de um locatário multigeográfico só poderá realizar a descoberta eletrônica na localização central desse locatário. O administrador global do Office 365 deve atribuir permissões de gerente de Descoberta Eletrônica para permitir que outras pessoas possam realizá-la e atribuir o parâmetro "Região" no Filtro de Segurança e Conformidade deles, para especificar a região como uma localização no satélite para a realização da Descoberta. Caso contrário, a Descoberta Eletrônica não será realizada para nenhuma localização no satélite. Para configurar o Filtro de Segurança de Conformidade para uma Região, consulte [Configurar a Descoberta Eletrônica Multigeográfica do Office 365](multi-geo-ediscovery-configuration.md).

## <a name="exchange-mailboxes"></a>Caixas de correio do Exchange

As caixas de correio dos usuários do Exchange são movidas automaticamente se sua PDL for alterado. Quando uma nova caixa de correio é criada, ela está provisionada ao PDL do usuário ou à localização central se nenhum valor foi definido para o PDL do usuário.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Política de Prevenção contra Perda de Dados (DLP) de Proteção de Informações (IP)

Você pode definir sua política DLP IP para o OneDrive for Business, SharePoint e Exchange no centro de Segurança e Conformidade políticas de definição de escopo, conforme necessário, para todo locatário ou para os usuários aplicáveis. Por exemplo: se você quiser selecionar uma política para um usuário em uma localização via satélite, selecione para aplicar a política para o OneDrive específico e insira a url do OneDrive do usuário. Confira [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) para instruções gerais ao criar políticas DLP.

As políticas de DLP são sincronizadas automaticamente de acordo com a aplicabilidade delas a cada localização geográfica.

A implementação de políticas de Prevenção contra Perda de Dados e Proteção da Informação para todos os usuários em uma localização geográfica não é uma opção disponível na IU. Em vez disso, é preciso selecionar as contas em que se deseja aplicar a política ou aplicá-la de modo global a todas as contas.

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

PowerApps criados para localização via satélite usarão o ponto de extremidade localizado na localização central do locatário. Microsoft PowerApps não é um serviço Multigeográfico. 

## <a name="power-automate"></a>Power Automate

Fluxos criados para localização via satélite usarão o ponto de extremidade localizado na localização geográfica padrão do locatário.  Power Automate não é um serviço Multi-Geo. 

## <a name="sharepoint-storage-quota"></a>Cota de armazenamento do SharePoint

Por padrão, todas as localizações geográficas de um ambiente multigeográfico compartilham a cota de armazenamento disponível do locatário.  Também é possível gerenciar a cota de armazenamento alocando uma cota específica de uma localização geográfica específica. Para saber mais, confira [Cotas de armazenamento do SharePoint em ambientes de multigeográfico](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Compartilhamento

Os administradores podem configurar e gerenciar políticas de compartilhamento para cada localização. Os OneDrive e SharePoint em cada localização geográfica irão honrar apenas as configurações de compartilhamento geo-específicas correspondentes. (Por exemplo, você pode permitir o [compartilhamento externo](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) para a localização central, mas não a localização via satélite ou vice-versa.) Observe que as configurações de compartilhamento não permitem configurar limitações de compartilhamento entre localizações geográficas.

## <a name="stream"></a>Stream

Os vídeos carregados no Stream em um chat 1:1 são armazenados no OneDrive da pessoa carregando. As gravações de reunião são armazenadas no OneDrive de cada participante que registra a reunião.

## <a name="taxonomy"></a>Taxonomia

Suportamos uma [taxonomia unificada](/sharepoint/managed-metadata) para metadados gerenciados pela empresa em localizações geográficas, com o mestre hospedado no local central da sua empresa. Recomendamos que você gerencie sua taxonomia global de uma localização central e apenas adicione termos específicos de localização para a Taxonomia da localização via satélite. Termos de taxonomia global serão sincronizadas para as ocalizações via satélite.

Confira [Gerenciar metadados em um locatário multigeográfico](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) para saber mais e para obter instruções do desenvolvedor.

## <a name="user-profile-application"></a>Aplicativo de Perfil de Usuário

Há um [aplicativo de perfil de usuário](/sharepoint/manage-user-profiles) em cada localização geográfica. As informações de perfil de cada usuário estão hospedadas na localização geográfica dele e ficam disponíveis para o administrador daquela localização.

Se houver propriedades de perfil personalizadas, recomendamos que você use o mesmo esquema de perfil nas localizações e popule as propriedades personalizadas em cada uma delas ou nas que forem necessárias.  Para obter instruções sobre como preencher dados de perfil de usuário de forma programática, confira a [API de Atualização de Perfil de Usuário em Massa](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).

Confira [Trabalhar com perfis de usuários em um locatário multigeográfico](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) para saber mais e para obter instruções do desenvolvedor.

## <a name="yammer"></a>Yammer

Yammer não é uma carga de trabalho Multi-Geo. Yammer threads armazenados Yammer serão colocados no local central do locatário. Yammer está implantando uma alteração de armazenamento de arquivo que armazenará Yammer arquivos no SharePoint. Yammer arquivos armazenados SharePoint serão colocados no site SharePoint associado ao Yammer grupo. SharePoint de grupo são baseados na lógica PDL conforme descrito [em SharePoint Sites e Grupos.](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)
