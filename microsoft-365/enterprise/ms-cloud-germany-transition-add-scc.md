---
title: Informações sobre a experiência de Descoberta e Durante a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: etapas de migração de Descoberta EDiscovery para a migração do Microsoft Cloud Deutschland.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592127"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Informações sobre a experiência de Descoberta e durante a migração do Microsoft Cloud Deutschland
As seções a seguir fornecem informações adicionais sobre a experiência de Descoberta Online ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.

## <a name="ediscovery-administration-until-phase-4"></a>Administração de Descoberta e até a fase 4
Até a fase 4, o Centro de Segurança e Conformidade estará totalmente disponível. Todo o conteúdo ainda permanece no Microsoft Cloud Germany e é gerenciável pelo Centro de Conformidade e Segurança do Microsoft Cloud Germany ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>Experiência de Descoberta e Entre a fase 4 até o final da fase 9
Desde o início da fase 4 até a conclusão da fase 9, as pesquisas de Descoberta Virtual falharão ou retornarão 0 resultados para os locais do SharePoint Online, do OneDrive for Business e do Exchange Online que foram migrados.

> [!NOTE]
> Durante [a](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)migração, os clientes podem continuar a criar casos, regiões, pesquisas e exportações no Centro de Conformidade & Segurança, incluindo [Pesquisa de Conteúdo.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) No entanto, as pesquisas em locais do SharePoint Online, do OneDrive for Business e do Exchange Online migrados retornarão 0 resultados ou produzirão um erro.

Caso uma pesquisa retorne zero resultados ou um erro durante a migração, faça a seguinte ação para o SharePoint Online: 
- Baixe sites diretamente do site do SharePoint Online ou do OneDrive for Business seguindo as instruções em Baixar arquivos e pastas [do OneDrive ou do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Este método exigirá permissões de administrador do SharePoint Online ou permissões somente leitura no site.
- Se os limites são excedido, conforme explicado em Baixar arquivos e pastas do OneDrive ou [do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), os clientes poderão usar o cliente de sincronização do OneDrive for Business seguindo as diretrizes em Sincronizar arquivos do [SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)e do Teams com seu computador.

- Para obter mais informações, consulte  [In-Place eDiscovery in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery).


## <a name="ediscovery-administration-after-phase-9"></a>Administração de Descobertas EDiscovery após a fase 9

**Aplica-se a:** Todos os clientes que usam a Descoberta Bancária

Na fase 9, as etapas finais para mover para a nova região do datacenter alemão serão concluídas. Nesta fase, todos os componentes de serviço restantes serão migrados. Após a fase 9, o uso do Centro de Segurança e Conformidade no Microsoft Cloud Germany (protection.office.de) não é mais suportado. Em vez disso, use o novo [Centro de Segurança](https://security.microsoft.com/) ou Centro de [Conformidade.](https://compliance.microsoft.com/) Todos os dados foram migrados para os novos portais de administração. 

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
|  Todos os locais do SharePoint Online, do OneDrive for Business e do Exchange Online foram migrados juntamente com o Centro de Segurança e Conformidade (SCC). | Todas as atividades de Descoberta Externa devem ser executados do locatário em todo o mundo. As pesquisas agora terão 100% de êxito. Quaisquer falhas ou erros devem seguir os canais de suporte normais. | Nenhum |
||||

### <a name="ediscovery-retention-policy"></a>Política de Retenção de Descoberta Externa
**Aplica-se a:**  Todos os clientes que aplicaram uma política de retenção como parte das etapas de pré-migração

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remover políticas de retenção em toda a organização que foram criadas durante etapas de pré-migração | Os clientes podem remover as políticas de retenção em toda a organização que foram criadas durante o trabalho de pré-migração dos clientes. | Nenhum |
||||
