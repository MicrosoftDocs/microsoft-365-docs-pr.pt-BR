---
title: O que há de novo no centro de conformidade da Microsoft 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Assim como os recursos do centro de conformidade da Microsoft 365, nosso conteúdo da ajuda está sempre evoluindo. Estamos constantemente criando novos artigos, atualizando os existentes e fazendo alterações com base em seus comentários. Descubra o que é novo e atualizado este mês.
ms.openlocfilehash: d610ab37312a1305809d740a9353822293c48df0
ms.sourcegitcommit: 3a632d8ec009abf1aac57363eaf78aeeda5db136
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37376126"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Atualizações recentes para o conteúdo de conformidade do Microsoft 365

Assim como os recursos do centro de conformidade da Microsoft 365, nosso conteúdo da ajuda está sempre evoluindo. Estamos constantemente criando novos artigos, atualizando os existentes e fazendo alterações com base em seus comentários. Veja o que há de novo e atualizado neste mês.

> [!TIP]
> Para se manter atualizado sobre as atualizações de recursos mais recentes no centro de conformidade do Microsoft 365, confira [o que há de novo no centro de conformidade da microsoft 365](whats-new.md).

## <a name="september"></a>Setembro

### <a name="ediscovery"></a>Descoberta eletrônica

[Investigar, solucionar problemas e resolver problemas comuns de descoberta eletrônica](ediscovery-troubleshooting-common-issues.md) (novo)<br> Inclui etapas básicas de solução de problemas que podem ser tomadas para identificar e resolver problemas que você pode encontrar durante uma pesquisa de descoberta eletrônica ou em qualquer outro lugar no processo de descoberta eletrônica.

### <a name="supervision"></a>Supervisão

[Configurar políticas de supervisão para sua organização](configure-supervision-policies.md) (atualizado)<br>Removidos detalhes sobre como usar o Outlook para executar revisões. Em vez disso, use as opções de revisão e marcação que estão disponíveis na interface de usuário de supervisão.

## <a name="august-2019"></a>Agosto de 2019

### <a name="auditing"></a>Auditoria

[Gerenciar auditoria de caixa de correio](enable-mailbox-auditing.md#more-information) (atualizado)<br>Adicionado detalhes sobre como os eventos de log de auditoria de caixa de correio estão disponíveis somente para usuários com licenças E5 ou caixas de correio em que a auditoria de caixa de correio foi ativada manualmente por um administrador. Além disso, novas orientações sobre como usar o cmdlet **Search-MailboxAuditLog** no PowerShell do Exchange Online para pesquisar o log de auditoria de caixa de correio para usuários sem licenças e5.

[Pesquisar o log de auditoria do Office 365 para solucionar problemas de cenários comuns](auditing-troubleshooting-scenarios.md#investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization) (atualizado)<br>Nova seção sobre como usar a autenticação de passagem para investigar os logons bem-sucedidos por usuários externos.

### <a name="content-search--ediscovery"></a>Pesquisa de conteúdo & descoberta eletrônica

[Configurar filtragem de permissões para pesquisa de conteúdo](permissions-filtering-for-content-search.md#using-a-filters-list-to-combine-filter-types) (atualizado)<br>Adicionados detalhes sobre como usar uma lista de filtros, que permite adicionar um filtro de caixa de correio e de site a um único filtro de permissões de pesquisa.

[Pesquisa de conteúdo no Office 365](content-search.md#searching-disconnected-or-de-licensed-mailboxes) (atualizado)<br>Adicionados detalhes sobre como Pesquisar caixas de correio desconectadas ou deslicenciadas.

[Pesquisa de conteúdo no Office 365](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment) (atualizado)<br>
[Configurar limites de conformidade para investigações de descoberta eletrônica no Office 365](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments) (atualizado)<br>Adicionados detalhes aos dois artigos sobre pesquisa de conteúdo em ambientes multigeográfico do SharePoint.

### <a name="data-governance"></a>Governança de dados

[Visão geral do arquivamento ilimitado no Office 365](unlimited-archiving.md#how-auto-expanding-archiving-works) (atualizado)<br>Foram adicionados detalhes sobre como o Office 365 adiciona um máximo de 20 arquivos auxiliares para um total de 1 TB de armazenamento adicional.

### <a name="data-investigations"></a>Investigações de dados

[Excluir itens de seu local original (visualização)](delete-items-from-original-locations.md) (novo)<br>Agora disponível na visualização, você pode selecionar itens em um conjunto de evidências e, em seguida, excluí-los de forma reversível de seus locais originais no Exchange, no SharePoint e no OneDrive.

[Gerenciar um incidente de derramamento de dados no Microsoft 365](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) (atualizado)<br>Adicionados detalhes sobre como usar o recurso novo ' excluir itens do seu local original ' para excluir dados derramados.

### <a name="permissions"></a>Permissões

[Permissões no centro de conformidade da microsoft 365 e centro de segurança do microsoft 365](../security/office-365-security/permissions-microsoft-365-compliance-security.md) (novo)<br>Novos grupos de função do Azure Active Directory foram lançados para visualização pública.

### <a name="records-management"></a>Gerenciamento de registros

[Visão geral do Gerenciador de planos de arquivo (atualizado)](file-plan-manager.md#export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews)<br>Adicionada uma tabela que lista os valores válidos a serem usados no modelo do Excel.

### <a name="supervision"></a>Supervisão

[Políticas de supervisão no Office 365](supervision-policies.md) (atualizado)<br>Esclarecido suporte ao grupo e à lista de distribuição do Office 365, adicionado orientações para correspondências de palavras-chave em emails e anexos, e esclarecidos o suporte do Outlook em canais do teams.

### <a name="windows-information-protection"></a>Proteção de Informações do Windows

[Lista de aplicativos da Microsoft habilitados para uso com a proteção de informações do Windows (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/enlightened-microsoft-apps-and-wip) (atualizado) <br>O visualizador 3D da Microsoft agora é um aplicativo esclarecido.
