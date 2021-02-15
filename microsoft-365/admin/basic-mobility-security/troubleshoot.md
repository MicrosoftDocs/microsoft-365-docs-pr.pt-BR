---
title: Solucionar problemas básicos de mobilidade e segurança
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
description: Experimente estas etapas para rastrear problemas básicos de mobilidade e segurança
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876847"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solucionar problemas básicos de mobilidade e segurança

Se você tiver problemas ao tentar registrar um dispositivo no Basic Mobility and Security, tente as etapas aqui para rastrear o problema. Se as etapas gerais não corrigirem o problema, consulte uma das seções posteriores com etapas específicas para o tipo de dispositivo.

## <a name="steps-to-try-first"></a>Etapas para tentar primeiro

Para começar, verifique o seguinte:

- Certifique-se de que o dispositivo ainda não está inscrito em outro provedor de gerenciamento de dispositivo móvel, como o Intune.

- Certifique-se de que o dispositivo está definido para a data e a hora corretas.

- Alternar para uma rede WIFI ou celular diferente no dispositivo.

- Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo portal da empresa do Intune no dispositivo. 

## <a name="ios-phone-or-tablet"></a>Telefone ou tablet iOS

- Certifique-se de que você tenha definido um certificado APNs. Para obter mais informações, [consulte Criar um certificado APNs para dispositivos iOS.](create-an-apns-certificate-for-ios-devices.md)

- Em **Configurações** Perfil Geral (ou Gerenciamento   >  ****   >  **de Dispositivo),** certifique-se de que um Perfil de Gerenciamento ainda não está instalado. Se estiver, remova-o.

- Se você vir a mensagem de erro "O dispositivo falhou ao se inscrever", entre no Microsoft 365 e certifique-se de que uma licença que inclua o Exchange Online tenha sido atribuída ao usuário conectado ao dispositivo.

- Se você vir a mensagem de erro "Falha na instalação do perfil", tente uma das seguintes:

    - Certifique-se de que o Safari seja o navegador padrão no dispositivo e que os cookies não estão desabilitados.

    - Reinicialize o dispositivo e navegue até portal.manage.microsoft.com. Entre com sua ID de usuário e senha do Microsoft 365 e tente instalar o perfil manualmente.

## <a name="windows-rt"></a>Windows RT

- Certifique-se de que seu domínio está definido no Microsoft 365 para trabalhar com Mobilidade e Segurança Básica. Para obter mais informações, [consulte Configurar Mobilidade Básica e Segurança.](set-up.md)
    
- Certifique-se de que o usuário está escolhendo **Ativar em** vez de   escolher **Ingressar.**

## <a name="windows-10-pc"></a>Computador Windows 10

- Certifique-se de que seu domínio está definido no Microsoft 365 para trabalhar com Mobilidade e Segurança Básica. Para obter mais informações, [consulte Configurar Mobilidade Básica e Segurança.](set-up.md)
    
- A menos que você tenha o Azure Active Directory Premium, certifique-se de que o usuário esteja escolhendo Registrar-se no Gerenciamento de **Dispositivos** apenas em   vez de escolher **Conectar.**

## <a name="android-phone-or-tablet"></a>Telefone Ou tablet Android

- Certifique-se de que o dispositivo está executando o Android 4.4 ou posterior.

- Certifique-se de que o Chrome está atualizado e está definido como o navegador padrão.

- Se você vir a mensagem de erro "Não foi possível registrar este dispositivo", entre no Microsoft 365 e certifique-se de que uma licença que inclua o Exchange Online tenha sido atribuída ao usuário conectado ao dispositivo.

- Verifique a Área de Notificação no dispositivo para ver se alguma ação necessária do usuário final está pendente e, se estiver, conclua as ações.