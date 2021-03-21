---
title: Perguntas frequentes sobre administração delegada
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem exibir perguntas frequentes e respostas sobre tarefas de administração delegadas no Microsoft 365 para parceiros e revendedores da Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929367"
---
# <a name="delegated-administration-faq"></a>Perguntas frequentes sobre administração delegada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este artigo fornece perguntas e respostas frequentes sobre tarefas de administração delegadas no Microsoft 365 para parceiros e revendedores da Microsoft. A administração delegada inclui a capacidade de gerenciar as configurações do Exchange Online Protection (EOP) para outros locatários (empresas).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Sou um revendedor e preciso gerenciar meus locatários de clientes. Como isso funciona?

Se você for um parceiro ou revendedor da Microsoft e se inscreveu para  ser um consultor da Microsoft, poderá solicitar recursos de administração delegados na organização do Microsoft 365 do cliente.

A administração delegada permite gerenciar o Microsoft 365 (incluindo configurações do EOP) como se você fosse um administrador dentro dessa organização. As etapas para configurar a administração delegada são descritas na lista a seguir:

1. Inscreva-se para ser um [Consultor do Microsoft Office 365](https://partner.microsoft.com/?cloudbenefits).

2. Inscreva-se na administração delegada. Antes de começar a administrar o locatário de um cliente, ele deve autorizar você como administrador delegado. Para obter a aprovação dele, é necessário [enviar primeiro uma oferta para administração delegada](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Você também pode oferecer administração delegada ao seu cliente posteriormente.

3. Crie a conta de administrador delegada usando as etapas em [Adicionar, alterar ou excluir um parceiro de consultor de assinatura](../../admin/misc/add-partner.md).

Visite [Parceiros: crie sua empresa e](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) administro assinatura de parceiro para obter mais informações sobre como configurar a administração delegada.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Sou um cliente, não um revendedor. Como configurar o administrador delegado para meus subtenantes?

A administração delegada só está disponível para revendedores e parceiros. No entanto, há um exemplo de script do PowerShell que ajudará você a aplicar políticas aos seus subtenentes (empresas). Para obter mais informações, consulte [Amostra de script para aplicação de configurações de EOP a vários locatários](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Posso impedir que meu administrador subtenente modifique minha política?

Não. No momento, o Microsoft 365 não tem esse recurso.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Posso obter relatórios consolidados em todos os meus subtenantes?

Relatórios consolidados entre as empresas gerenciadas não estão disponíveis nos relatórios do Centro de administração do Microsoft 365. No entanto, você pode obter relatórios usando o [Microsoft Graph](/graph/overview).