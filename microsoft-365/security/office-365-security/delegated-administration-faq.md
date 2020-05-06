---
title: Perguntas frequentes sobre administração delegada
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Este tópico fornece perguntas frequentes e respostas para os parceiros e revendedores da Microsoft que desejam executar tarefas de administração do Microsoft 365 delegadas.
ms.openlocfilehash: d2411734e583cce2be817793e2b39abba2b186a5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036458"
---
# <a name="delegated-administration-faq"></a>Perguntas frequentes sobre administração delegada

Este tópico fornece perguntas frequentes e respostas para os parceiros e revendedores da Microsoft que desejam executar tarefas de administração delegadas, incluindo a capacidade de gerenciar o Exchange Online Protection (EOP) para outros locatários (empresas).

**P. Sou revendedor e preciso gerenciar os locatários do meu cliente. Como isso funciona?**

R. Se você for um parceiro da Microsoft ou revendedor e se inscrever em um Microsoft Advisor, você pode solicitar permissão para administrar o locatário dentro do centro de administração. Isso é conhecido como administração delegada e permite que você gerencie seus locatários do Microsoft 365 (incluindo as configurações do EOP) como se você fosse um administrador dentro de sua organização. Veja a seguir as etapas para execução da administração delegada:

1. Inscreva-se para ser um [Consultor do Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Inscreva-se para a administração delegada. Para que você possa começar a administrar a conta de um cliente, ele deverá autorizá-lo como um administrador delegado. Para obter a aprovação dele, é necessário [enviar primeiro uma oferta para administração delegada](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (Você também pode oferecer posteriormente a administração delegada ao seu cliente.)

3. Crie a conta de administração delegada usando as etapas em [Adicionar, alterar ou excluir um parceiro de supervisor de assinatura](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visite [parceiros: Construa sua empresa e administre sua assinatura de parceiro](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) para obter mais informações sobre como configurar a administração delegada.

**P. Sou um cliente, não é um revendedor, como posso configurar o administrador delegado para meus sublocatários?**

R. A administração delegada só está disponível para parceiros e revendedores no momento. No entanto, fornecemos um script de amostra do Windows PowerShell que ajudará você a aplicar políticas aos seus sublocatários (empresas). Para obter mais informações, consulte [Amostra de script para aplicação de configurações de EOP a vários locatários](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**P. Posso impedir que a administração de sublocatário modifique minha política?**

R. A Microsoft 365 não tem esse recurso no momento.

**P. Posso obter um relatório consolidado em todos os meus sublocatários?**

R. O relatório consolidado nas empresas que você gerencia não está disponível para os relatórios do centro de administração do Microsoft 365 no momento. No entanto, você pode fazer isso usando [o Microsoft Graph](https://docs.microsoft.com/graph/overview).
