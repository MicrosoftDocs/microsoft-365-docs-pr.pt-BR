---
title: Gerenciar licenças para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638178"
---
# <a name="manage-licenses-for-devices"></a>Gerenciar licenças para dispositivos

Se você tiver o Microsoft 365 Apps para empresas (dispositivo) ou o Microsoft 365 Apps para Educação (dispositivo), poderá atribuir licenças a dispositivos usando grupos do Azure AD. Quando um dispositivo tem uma licença, qualquer pessoa que usa esse dispositivo pode usar o Microsoft 365 Apps para empresas (anteriormente chamado de Office 365 ProPlus). Por exemplo, digamos que você tenha 20 laptops e tablets usados por pessoas em sua organização. Quando você atribui uma licença a cada dispositivo, cada pessoa que faz login em um dos dispositivos usa o Microsoft 365 Apps para empresas sem a necessidade de sua própria licença.

> [!IMPORTANT]
> O licenciamento baseado em dispositivo para o Microsoft 365 Apps para empresas está disponível apenas como uma licença de complemento para alguns clientes comerciais e alguns clientes de educação. Para clientes comerciais, a licença é do *Microsoft 365 Apps para empresas (dispositivo)* e está disponível somente por meio de Assinatura de Contrato Empresarial/Contrato Empresarial. Para clientes da área de educação, a licença é do *Microsoft 365 Apps para Educação (dispositivo)* e está disponível somente por meio do Registro para Soluções de Educação (EES). Para obter mais informações, leia a postagem do blog sobre [disponibilidade educacional.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Para disponibilidade comercial, entre em contato com o representante da conta Microsoft.

Para começar, crie um grupo no centro de administração do Azure Active Directory e atribua dispositivos ao grupo. Para saber mais sobre o licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos você pode usar e como configurar o Microsoft 365 Apps para empresas para usar o licenciamento de dispositivos, consulte Licenciamento baseado em dispositivo para o [Microsoft 365 Apps](https://go.microsoft.com/fwlink/p/?linkid=2094216)para empresas.

> [!IMPORTANT]
> Você deve ser um administrador global para concluir as tarefas neste artigo.

## <a name="assign-licenses-to-devices"></a>Atribuir licenças a dispositivos

Ao atribuir licenças a um grupo, você atribui licenças a todos os dispositivos do grupo. Você só pode atribuir uma assinatura a qualquer grupo único.

1. No Centro de administração do Microsoft 365, vá para a **página**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** ou **Aplicativos do Microsoft 365** para empresas (dispositivo).
3. Na próxima página, escolha uma assinatura e, em seguida, escolha **Atribuir licenças.**
4. No painel **Atribuir licenças a** um painel de grupo, comece a digitar um nome de grupo e escolha-o nos resultados para adicioná-lo à lista.
5. Choose **Assign**, then choose **Close**.

## <a name="unassign-licenses-from-devices"></a>Desa designar licenças de dispositivos

Quando você desa designa licenças de um grupo, remove as licenças de todos os dispositivos dentro do grupo. Todos os aplicativos e seus dados associados são, então, somente leitura.

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** ou **Aplicativos do Microsoft 365** para empresas (dispositivo).
3. Na próxima página, escolha uma assinatura, escolha **Mais ações** e, em seguida, **desaignar licenças.**
4. In the **Unassign licenses dialog** box, choose **Unassign**.