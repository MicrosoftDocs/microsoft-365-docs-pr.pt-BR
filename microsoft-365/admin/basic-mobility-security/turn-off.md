---
title: Desativar a Mobilidade e Segurança Básica
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Remova grupos ou políticas para desativar a Mobilidade Básica e a Segurança.
ms.openlocfilehash: 7ec4ec0d47668c21824d8e01e3845d637b9b0922
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228130"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desativar a Mobilidade e Segurança Básica

Para desativar efetivamente a Mobilidade Básica e a Segurança, remova grupos de pessoas definidas por grupos de segurança das políticas de gerenciamento de dispositivos ou remova as políticas por conta própria.

- Remova grupos de usuários removendo grupos de segurança do usuário das políticas de dispositivo criadas.

- Desabilite a Mobilidade Básica e a Segurança para todos removendo todas as políticas básicas de dispositivos de Mobilidade e Segurança.

Essas opções removem a imposição básica de mobilidade e segurança para dispositivos em sua organização. Infelizmente, você não pode simplesmente "desprovisionar" Basic Mobility and Security depois de configurar.

> [!IMPORTANT]
> Esteja ciente do impacto nos dispositivos dos usuários ao remover grupos de segurança do usuário das políticas ou remover as políticas por conta própria. Por exemplo, perfis de email e emails armazenados em cache podem ser removidos, dependendo do dispositivo. Para obter mais informações, consulte  [O que acontece quando você exclui uma política ou remove um usuário da política?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Remover grupos de segurança do usuário das políticas básicas de dispositivos de mobilidade e segurança

1. No tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione uma política de dispositivo e selecione **Editar política**.

3. Na  **** página   Implantação, selecione **Remover**.

4. Em  **Grupos,** selecione um grupo de segurança.

5. Selecione  **Remover** e selecione **Salvar**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Remover políticas básicas de dispositivos de mobilidade e segurança

1. No tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione uma política de dispositivo e selecione  **Excluir política**.

3. Na caixa de diálogo Aviso, selecione **Sim**.

> [!NOTE]
> Para obter mais etapas para desbloquear dispositivos se os dispositivos da sua organização ainda estão bloqueados, consulte a postagem do blog [Removendo](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)o Controle de Acesso do Gerenciamento de Dispositivo Móvel do Office 365 .
