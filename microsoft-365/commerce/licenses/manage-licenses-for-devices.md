---
title: Gerenciar licenças para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Saiba como atribuir licenças a grupos para uso com dispositivos.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237348"
---
# <a name="manage-licenses-for-devices"></a>Gerenciar licenças para dispositivos

Se você tiver o Office 365 ProPlus for Education (dispositivo), poderá atribuir licenças aos dispositivos usando grupos do Azure AD. Quando um dispositivo tem uma licença, qualquer pessoa que use o dispositivo pode usar o Office 365. Por exemplo, digamos que você tenha 20 laptops e tablets que são usados por pessoas em sua organização. Quando você atribui uma licença a cada dispositivo, cada pessoa que faz logon em um dos dispositivos usa o Office 365 sem a necessidade de sua própria licença.

> [!IMPORTANT]
> O Office 365 ProPlus for Education (dispositivo) só está disponível para os clientes de licenciamento por volume a3 e a5.

Para começar, você cria um grupo no centro de administração do Azure Active Directory e, em seguida, atribui dispositivos ao grupo. Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos podem ser usados e como configurar o Office 365 PROPLUS para usar o licenciamento de dispositivos, consulte [Device Licensing for Office 365 ProPlus for Education Customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Você deve ser um administrador global para concluir as tarefas neste artigo.

## <a name="assign-licenses-to-devices"></a>Atribuir licenças a dispositivos

Ao atribuir licenças a um grupo, você atribui licenças a todos os dispositivos do grupo. Você só pode atribuir uma assinatura a um único grupo.

1. No centro de administração do Microsoft 365, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .
2. Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)**.
3. Na página **Office 365 ProPlus for Education (dispositivo)** , escolha uma assinatura e, em seguida, escolha **atribuir licenças**.
4. No painel **atribuir licenças a um grupo** , comece a digitar o nome de um grupo e, em seguida, escolha-o nos resultados para adicioná-lo à lista.
6. Escolha **atribuir**e, em seguida, escolha **fechar**.

## <a name="unassign-licenses-from-devices"></a>Cancelar a atribuição de licenças de dispositivos

Ao cancelar a atribuição de licenças de um grupo, você remove as licenças de todos os dispositivos do grupo. Todos os aplicativos e seus dados associados serão somente leitura.

1. No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .
2. Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)**.
3. Na página **Office 365 ProPlus for Education (dispositivo)** , escolha uma assinatura, escolha **mais ações**e, em seguida, escolha **Cancelar atribuição de licenças**.
5. Na caixa de diálogo **cancelar a atribuição de licenças** , escolha **Cancelar atribuição**.