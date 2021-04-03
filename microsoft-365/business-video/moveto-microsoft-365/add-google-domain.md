---
title: Adicionar seu domínio do Espaço de Trabalho do Google
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como mover seu domínio do Google Workspace para o Microsoft 365 para empresas.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578766"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Adicionar seu domínio do Espaço de Trabalho do Google ao Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Adicione seu domínio do Google Workspace ao Microsoft 365 para empresas para que você possa continuar usando seu endereço de email comercial.

## <a name="try-it"></a>Experimente!

1. Vá para o Centro de administração [do Microsoft 365.](https://admin.microsoft.com)
1. No Centro de Administração do Microsoft 365, na nav esquerda, selecione **Mostrar tudo**, **Configurações** e **domínios**.
1. Escolha **Adicionar domínio**, insira seu nome de domínio e selecione Usar este **domínio**. 
1. Escolha, **Adicione um registro TXT** aos registros DNS de domínios, selecione **Continuar** e copie o valor TXT. 
1. Volte para o Console de Administração do [Google,](https://admin.google.com)escolha **Domínios,** Gerenciar **domínios,** **Exibir** Detalhes, **Gerenciar** domínio, **DNS** e, em seguida, role para baixo até Registros de recursos **personalizados.** 
1. Abra o drop-down do tipo de registro, escolha **TXT**, colar o valor TXT que você copiou e selecione **Adicionar**. 

    A atualização geralmente leva um fato dentro de alguns minutos, mas pode levar até 48 horas. 
1. Retorne ao Centro de Administração do Microsoft 365, selecione **Verificar** **e,** em seguida, Fechar . 
1. Para definir seu domínio como o email principal para seus usuários, na nav esquerda, selecione **Usuários**  >  **Ativos usuários**. 
1. Escolha um usuário, selecione Gerenciar nome de usuário e **email,** **Editar,** selecione seu domínio no menu suspenso e selecione **Fazer** e **Salvar alterações**. 
1. Repita esse processo para cada usuário. 

    Quando terminar, você estará pronto para instalar aplicativos do Office e migrar seus itens de email e calendário para o Microsoft 365. 