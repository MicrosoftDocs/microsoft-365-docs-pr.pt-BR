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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem exibir perguntas frequentes e respostas sobre tarefas de administração delegadas no Microsoft 365 para parceiros e revendedores da Microsoft.
ms.openlocfilehash: 3efadc8793778bfabe10922e8e29044747d60ad0
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866690"
---
# <a name="delegated-administration-faq"></a>Perguntas frequentes sobre administração delegada

Este artigo fornece perguntas frequentes e respostas sobre tarefas de administração delegadas no Microsoft 365 para parceiros e revendedores da Microsoft. A administração delegada inclui a capacidade de gerenciar as configurações do Exchange Online Protection (EOP) para outros locatários (empresas).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Sou um revendedor e preciso gerenciar meus locatários do cliente. Como isso funciona?

Se você é um parceiro ou revendedor da Microsoft e se inscreveu em um Microsoft Advisor, você pode solicitar recursos de _administração delegada_ na sua organização do Microsoft 365 do cliente.

A administração delegada permite que você gerencie o Microsoft 365 (incluindo as configurações do EOP) como se você fosse um administrador dentro dessa organização. As etapas para configurar a administração delegada são descritas na lista a seguir:

1. Inscreva-se para ser um [Consultor do Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Inscreva-se para a administração delegada. Para que você possa começar a administrar o locatário de um cliente, ele deve autorizar você como um administrador delegado. Para obter a aprovação dele, é necessário [enviar primeiro uma oferta para administração delegada](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Você também pode oferecer a administração delegada ao cliente mais tarde.

3. Crie a conta de administração delegada usando as etapas em [Adicionar, alterar ou excluir um parceiro de supervisor de assinatura](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Visite [parceiros: Construa sua empresa e administre sua assinatura de parceiro](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) para obter mais informações sobre como configurar a administração delegada.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Sou um cliente, não um revendedor. Como o administrador delegado pode ser configurado para meus sublocatários?

A administração delegada só está disponível para os revendedores e parceiros. No entanto, há um exemplo de script do PowerShell que o ajudará a aplicar políticas aos seus sublocatários (empresas). Para obter mais informações, consulte [Amostra de script para aplicação de configurações de EOP a vários locatários](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Posso impedir que meu administrador de sublocatário modifique minha política?

Não. A Microsoft 365 não tem esse recurso no momento.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Posso obter relatórios consolidados em todos os meus sublocatários?

Os relatórios consolidados nas empresas que você gerencia não estão disponíveis nos relatórios do centro de administração do Microsoft 365. No entanto, você pode obter relatórios usando [o Microsoft Graph](https://docs.microsoft.com/graph/overview).
