---
title: Adicionar seu domínio do Espaço de Trabalho do Google
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como mover seu domínio do Google Workspace para o Microsoft 365 para empresas.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49924997"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Adicionar seu domínio do Google Workspace ao Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Adicione seu domínio do Google Workspace ao Microsoft 365 para empresas para que você possa continuar usando seu endereço de email comercial.

## <a name="try-it"></a>Experimente!

1. Vá para o [Centro de administração do Microsoft 365.](https://admin.microsoft.com)
1. No Centro de Administração do Microsoft 365, no painel de administração esquerdo, selecione **Mostrar tudo** **,** Configurações e **domínios.**
1. Choose **Add domain**, enter your domain name then select Use this **domain**. 
1. Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value. 
1. Volte para o [Google Admin Console](https://admin.google.com), escolha **Domínios**, **Gerenciar domínios** **,** Exibir Detalhes **,** Gerenciar domínio , **DNS** e role para baixo até Registros de **recurso personalizados**. 
1. Abra o drop-down de tipo de registro, escolha **TXT**, colar o valor TXT que você copiou e selecione **Adicionar**. 

    A atualização geralmente leva um fato dentro de alguns minutos, mas pode levar até 48 horas. 
1. Retorne ao Centro de Administração do Microsoft 365, selecione **Verificar** e **Feche.** 
1. Para definir seu domínio como o email principal para seus usuários, na nav esquerda, selecione **Usuários**  >  **ativos.** 
1. Escolha um usuário, selecione Gerenciar nome de usuário e **email,** **Editar**, selecione seu domínio na lista suspenso e selecione **Alterações** Feitas **e Salvar.** 
1. Repita esse processo para cada usuário. 

    Quando terminar, você estará pronto para instalar os aplicativos do Office e migrar seus itens de email e calendário para o Microsoft 365. 