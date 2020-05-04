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
ms.openlocfilehash: 1a525117c25a2471ad696ef1447fd7e4ccb6bed0
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011180"
---
# <a name="manage-licenses-for-devices"></a>Gerenciar licenças para dispositivos

Se você tiver aplicativos Microsoft 365 para empresas (dispositivos) ou aplicativos da Microsoft 365 para educação (dispositivo), poderá atribuir licenças a dispositivos usando grupos do Azure AD. Quando um dispositivo tem uma licença, qualquer pessoa que usa o dispositivo pode usar o Microsoft 365 aplicativos para empresas (anteriormente chamado Office 365 ProPlus). Por exemplo, digamos que você tenha 20 laptops e tablets que são usados por pessoas em sua organização. Quando você atribui uma licença a cada dispositivo, cada pessoa que faz logon em um dos dispositivos usa o Microsoft 365 aplicativos para empresas sem a necessidade de sua própria licença.

> [!IMPORTANT]
> O licenciamento baseado em dispositivo para o Microsoft 365 aplicativos para empresas está disponível somente como uma licença complementar para alguns clientes comerciais e alguns clientes de educação. Para clientes comerciais, a licença é *Microsoft 365 Apps for Enterprise (dispositivo)* e está disponível apenas por meio da assinatura do Enterprise Agreement/Enterprise Agreement. Para clientes de educação, a licença é o *Microsoft 365 Apps for Education (dispositivo)* e está disponível somente por meio do registro de soluções de educação (EES). Para obter mais informações, leia a postagem de blog sobre [disponibilidade de educação](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Para disponibilidade comercial, entre em contato com seu representante de conta da Microsoft.

Para começar, você cria um grupo no centro de administração do Azure Active Directory e, em seguida, atribui dispositivos ao grupo. Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos podem ser usados e como configurar o Microsoft 365 aplicativos para empresas para usar o licenciamento de dispositivos, consulte [Licenciamento baseado em dispositivo para o microsoft 365 aplicativos para empresas](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Você deve ser um administrador global para concluir as tarefas neste artigo.

## <a name="assign-licenses-to-devices"></a>Atribuir licenças a dispositivos

Ao atribuir licenças a um grupo, você atribui licenças a todos os dispositivos do grupo. Você só pode atribuir uma assinatura a um único grupo.

1. No centro de administração do Microsoft 365, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .
2. Na página **licenças** , escolha **Microsoft 365 aplicativos para educação (dispositivo)** ou **aplicativos da Microsoft 365 para empresas (dispositivo)**.
3. Na próxima página, escolha uma assinatura e, em seguida, escolha **atribuir licenças**.
4. No painel **atribuir licenças a um grupo** , comece a digitar o nome de um grupo e, em seguida, escolha-o nos resultados para adicioná-lo à lista.
5. Escolha **atribuir**e, em seguida, escolha **fechar**.

## <a name="unassign-licenses-from-devices"></a>Cancelar a atribuição de licenças de dispositivos

Ao cancelar a atribuição de licenças de um grupo, você remove as licenças de todos os dispositivos do grupo. Todos os aplicativos e seus dados associados serão somente leitura.

1. No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .
2. Na página **licenças** , escolha **Microsoft 365 aplicativos para educação (dispositivo)** ou **aplicativos da Microsoft 365 para empresas (dispositivo)**.
3. Na próxima página, escolha uma assinatura, escolha **mais ações**e, em seguida, escolha **cancelar a atribuição de licenças**.
4. Na caixa de diálogo **cancelar a atribuição de licenças** , escolha **Cancelar atribuição**.