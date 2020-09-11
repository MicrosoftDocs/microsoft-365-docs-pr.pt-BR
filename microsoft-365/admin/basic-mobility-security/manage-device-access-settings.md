---
title: Gerenciar as configurações de acesso de dispositivo na mobilidade básica e segurança
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Mobilidade e segurança básica podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: e66465d312c4268aca82677fa4e517aaeb822ce3
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430056"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>Gerenciar as configurações de acesso de dispositivo na mobilidade básica e segurança

Se você estiver usando mobilidade básica e segurança, pode haver dispositivos que você não pode gerenciar com mobilidade básica e segurança. Em caso afirmativo, você deve bloquear o acesso do aplicativo Exchange ActiveSync ao email do Microsoft 365 para dispositivos móveis que não são suportados pela mobilidade básica e segurança. Isso ajuda a proteger as informações da sua organização em mais dispositivos.

Siga estas etapas:

1. Entre no Microsoft 365 com sua conta de administrador global.
    
2. No navegador, digite:  [https://protection.office.com](https://protection.office.com/) .    

    >[!IMPORTANT]
    >Se esta é a primeira vez que você está usando o MDM para o Microsoft 365 Business Standard, ative-o aqui: [ativar o gerenciamento de dispositivos móveis](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Após ativá-la, gerencie seus dispositivos com o [Office 365 Security & Compliance](https://protection.office.com/).

3. Vá para prevenção de perda de  **Device management**dados >  >  **políticas de dispositivos**de gerenciamento de dispositivos e selecione **gerenciar configurações de acesso de dispositivo para toda a organização**.
    
4. Selecione **Bloquear**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Caixa de seleção mobilidade básica e acesso de bloqueio de segurança":::

5. Selecione **salvar**. 

Para saber quais dispositivos são compatíveis com mobilidade e segurança básica, confira [recursos de mobilidade básica e segurança](capabilities.md).