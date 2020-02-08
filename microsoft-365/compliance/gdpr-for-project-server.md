---
title: RGPD para Project Server
description: Saiba mais sobre como atender aos requisitos de RGPD no Project Server local.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9fff9f085fd42f28801a82c3f83d6bdd1f74ff6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596408"
---
# <a name="gdpr-for-project-server"></a>RGPD para Project Server

O Project Server usa scripts personalizados para exportar e ocultar dados do usuário no Project Web App. O processo básico é o seguinte:

1.  Encontre os sites do Project Web App em seu farm.

2.  Encontre os projetos que contêm o usuário em cada site.

3.  Exporte e verifique os tipos de dados que você deseja analisar.

4.  Oculte os dados conforme for necessário.

Estas etapas são abordadas em detalhes nos seguintes artigos:

- [Exportar dados do usuário do Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Excluir dados do usuário do Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Observe que o Project Server foi criado a partir do SharePoint Server e que ele registra eventos nos logs de ULS do SharePoint e no banco de dados de uso. Consulte [RGPD para SharePoint Server](gdpr-for-sharepoint-server.md) para ter mais informações.
