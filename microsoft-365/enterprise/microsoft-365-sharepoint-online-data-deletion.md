---
title: Exclusão de dados do SharePoint Online da Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Saiba como a exclusão de dados funciona no SharePoint Online, como onde o conteúdo excluído é armazenado e por quanto tempo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687351"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>Exclusão de dados do SharePoint Online no Microsoft 365

O SharePoint Online armazena objetos como código abstrato em bancos de dados de aplicativos. Quando um usuário carrega um arquivo no SharePoint Online, esse arquivo é desmontado e traduzido no código do aplicativo e armazenado em várias tabelas em vários bancos de dados. No SharePoint Online, todo o conteúdo que um cliente carrega é dividido em partes, criptografadas (potencialmente com várias chaves AES de 256 bits) e distribuídas no datacenter. Para obter detalhes específicos sobre o processo de fragmentação e criptografia, consulte [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview). 

No SharePoint Online, os itens são mantidos por 93 dias a partir do momento em que você os exclui do local original. Eles permanecem na lixeira do site o horário inteiro, a menos que alguém os exclua ou esvazia essa lixeira. Nesse caso, os itens vão para a lixeira do conjunto de sites, onde eles permanecem no restante dos 93 dias. Para obter informações sobre como restaurar itens excluídos, consulte [restaurar itens na lixeira de um site do SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [restaurar itens excluídos da](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)lixeira do conjunto de sites. O tempo de retenção da lixeira não é configurável no SharePoint Online.

Ao excluir um conjunto de sites, você também está excluindo a hierarquia de sites na coleção e todos os conteúdos dentro deles:

- Documentos e bibliotecas de documentos
- Lista e dados de lista
- Definições de configuração do site
- Informações de função e segurança relacionadas ao site ou seus subsites
- Subsites do site de nível superior, seu conteúdo e informações de usuário

Se você excluir acidentalmente um conjunto de sites, ele poderá ser restaurado por um administrador global ou do SharePoint usando o centro de administração do SharePoint.

Os conjuntos de sites excluídos são mantidos por 93 dias. Após 93 dias, sites e todo o conteúdo e as configurações serão excluídos permanentemente, incluindo listas, bibliotecas, páginas e subsites.

A exclusão fixa ocorre quando um usuário limpa itens excluídos da lixeira do conjunto de sites, quando os períodos de retenção e backup expiram ou quando um administrador exclui permanentemente um conjunto de sites usando o [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando um usuário exclui (permanentemente exclui ou limpa) o conteúdo do SharePoint Online, todas as chaves de criptografia dos blocos excluídos também são excluídas. Os blocos nos discos que armazenaram anteriormente os fragmentos excluídos são marcados como não usados e estão disponíveis para reutilização.
