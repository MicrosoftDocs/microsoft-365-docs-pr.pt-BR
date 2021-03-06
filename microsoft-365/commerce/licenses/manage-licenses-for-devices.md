---
title: Gerenciar licenças para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Saiba como atribuir licenças a grupos para uso com dispositivos.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535657"
---
# <a name="manage-licenses-for-devices"></a>Gerenciar licenças para dispositivos

Se você tiver Microsoft 365 Apps para Grandes Empresas (dispositivo) ou Microsoft 365 Apps para Educação (dispositivo), poderá atribuir licenças a dispositivos usando grupos do Azure AD. Quando um dispositivo tem uma licença, qualquer pessoa que usa esse dispositivo pode usar Microsoft 365 Apps para Grandes Empresas (anteriormente chamado Office 365 ProPlus). Por exemplo, digamos que você tenha 20 laptops e tablets usados por pessoas em sua organização. Quando você atribui uma licença a cada dispositivo, cada pessoa que faz o login em um dos dispositivos usa Microsoft 365 Apps para Grandes Empresas sem a necessidade de sua própria licença.

> [!IMPORTANT]
> O licenciamento baseado em dispositivo para Microsoft 365 Apps para Grandes Empresas está disponível apenas como uma licença de complemento para alguns clientes comerciais e alguns clientes de educação. Para clientes comerciais, a licença é *Microsoft 365 Apps para Grandes Empresas (dispositivo)* e está disponível somente por meio Enterprise Agreement/Enterprise Agreement Assinatura. Para clientes de educação, a licença é Microsoft 365 Apps para Educação *(dispositivo)* e está disponível somente por meio do Registro para Soluções de Educação (EES). Para obter mais informações, leia a postagem do blog sobre disponibilidade [educacional.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education) Para disponibilidade comercial, entre em contato com seu representante de conta da Microsoft.

Para começar, crie um grupo no centro de administração Azure Active Directory e atribua dispositivos ao grupo. Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos você pode usar e como configurar o Microsoft 365 Apps para Grandes Empresas para usar o licenciamento de dispositivo, consulte [Licenciamento](/deployoffice/device-based-licensing)baseado em dispositivo para Microsoft 365 Apps para Grandes Empresas .

> [!IMPORTANT]
> Você deve ser um administrador global para concluir as tarefas neste artigo.

## <a name="assign-licenses-to-devices"></a>Atribuir licenças a dispositivos

Quando você atribui licenças a um grupo, atribui licenças a todos os dispositivos do grupo. Você só pode atribuir uma assinatura a qualquer grupo único.

1. No centro Microsoft 365 de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** **ou Microsoft 365 Apps para Grandes Empresas (dispositivo).**
3. Na próxima página, escolha uma assinatura e escolha **Atribuir licenças**.
4. No painel **Atribuir licenças a** um grupo, comece a digitar um nome de grupo e escolha-o entre os resultados para adicioná-lo à lista.
5. Escolha **Atribuir** e, em seguida, **escolha Fechar**.

## <a name="unassign-licenses-from-devices"></a>Unassign licenses from devices

Quando você desaigna licenças de um grupo, você remove as licenças de todos os dispositivos dentro do grupo. Todos os aplicativos e seus dados associados são, em seguida, somente leitura.

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** **ou Microsoft 365 Apps para Grandes Empresas (dispositivo).**
3. Na próxima página, escolha uma assinatura, selecione os três pontos (mais ações) e escolha **Unassign licenses**.
4. Na caixa **de diálogo Licenças não assinadas,** escolha **Unassign**.
