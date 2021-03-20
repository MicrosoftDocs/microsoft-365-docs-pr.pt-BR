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
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911469"
---
# <a name="manage-licenses-for-devices"></a>Gerenciar licenças para dispositivos

Se você tiver Aplicativos do Microsoft 365 para empresas (dispositivo) ou Aplicativos do Microsoft 365 para Educação (dispositivo), poderá atribuir licenças a dispositivos usando grupos do Azure AD. Quando um dispositivo tem uma licença, qualquer pessoa que usa esse dispositivo pode usar o Microsoft 365 Apps para empresas (anteriormente chamado office 365 ProPlus). Por exemplo, digamos que você tenha 20 laptops e tablets usados por pessoas em sua organização. Quando você atribui uma licença a cada dispositivo, cada pessoa que faz login em um dos dispositivos usa o Microsoft 365 Apps para empresas sem a necessidade de sua própria licença.

> [!IMPORTANT]
> O licenciamento baseado em dispositivo para Aplicativos do Microsoft 365 para empresas está disponível apenas como uma licença de complemento para alguns clientes comerciais e alguns clientes de educação. Para clientes comerciais, a licença é *o Microsoft 365 Apps for enterprise (dispositivo)* e está disponível somente por meio de Contrato Enterprise/Contrato Enterprise Assinatura. Para clientes de educação, a licença é *o Microsoft 365 Apps for Education (dispositivo)* e está disponível somente por meio do Registro para Soluções de Educação (EES). Para obter mais informações, leia a postagem do blog sobre disponibilidade [educacional.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Para disponibilidade comercial, entre em contato com seu representante de conta da Microsoft.

Para começar, crie um grupo no centro de administração do Azure Active Directory e atribua dispositivos ao grupo. Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos você pode usar e como configurar o Microsoft 365 Apps para empresas para usar o licenciamento de dispositivos, consulte Licenciamento baseado em dispositivo para Aplicativos do [Microsoft 365](/deployoffice/device-based-licensing)para empresas .

> [!IMPORTANT]
> Você deve ser um administrador global para concluir as tarefas neste artigo.

## <a name="assign-licenses-to-devices"></a>Atribuir licenças a dispositivos

Quando você atribui licenças a um grupo, atribui licenças a todos os dispositivos do grupo. Você só pode atribuir uma assinatura a qualquer grupo único.

1. No Centro de administração do Microsoft 365, vá para a página   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps for Education (dispositivo)** ou **Microsoft 365 Apps for enterprise (device)**.
3. Na próxima página, escolha uma assinatura e escolha **Atribuir licenças**.
4. No painel **Atribuir licenças a** um grupo, comece a digitar um nome de grupo e escolha-o entre os resultados para adicioná-lo à lista.
5. Escolha **Atribuir** e, em seguida, **escolha Fechar**.

## <a name="unassign-licenses-from-devices"></a>Unassign licenses from devices

Quando você desaigna licenças de um grupo, você remove as licenças de todos os dispositivos dentro do grupo. Todos os aplicativos e seus dados associados são, em seguida, somente leitura.

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps for Education (dispositivo)** ou **Microsoft 365 Apps for enterprise (device)**.
3. Na próxima página, escolha uma assinatura, escolha **Mais ações** e, em seguida, **escolha Unassign licenses**.
4. Na caixa **de diálogo Licenças não assinadas,** escolha **Unassign**.