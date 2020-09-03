---
title: Solucionar problemas de mobilidade básica e segurança
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
description: Tente estas etapas para rastrear problemas básicos de segurança e mobilidade
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336708"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solucionar problemas de mobilidade básica e segurança

Se você estiver executando problemas ao tentar registrar um dispositivo em mobilidade básica e segurança, tente as etapas aqui para rastrear o problema. Se as etapas gerais não corrigirem o problema, consulte uma das seções posteriores com etapas específicas para o tipo de dispositivo.

## <a name="steps-to-try-first"></a>Etapas para tentar primeiro

Para começar, verifique o seguinte:

- Certifique-se de que o dispositivo ainda não esteja inscrito com outro provedor de gerenciamento de dispositivo móvel, como o Intune.
    
- Certifique-se de que o dispositivo está definido para a data e hora corretas.
    
- Alterne para uma rede WIFI ou de celular diferente no dispositivo.
    
- Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo portal da empresa do Intune no dispositivo. 

## <a name="ios-phone-or-tablet"></a>telefone iOS ou Tablet

- Verifique se você configurou um certificado APNs. Para obter mais informações, consulte [criar um certificado APNs para dispositivos IOS](create-an-apns-certificate-for-ios-devices.md).
    
- Em **configurações**   >  **gerais**de   >  **perfil (ou gerenciamento de dispositivos)**, certifique-se de que um perfil de gerenciamento ainda não esteja instalado. Se estiver, remova-o.
    
- Se você vir a mensagem de erro, "o dispositivo não pôde registrar", entre no Microsoft 365 e certifique-se de que uma licença que inclui o Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.
    
- Se você vir a mensagem de erro, "perfil falhou ao instalar", tente uma das seguintes opções:
    
    - Verifique se o Safari é o navegador padrão no dispositivo e se os cookies não estão desabilitados.
    
    - Reinicialize o dispositivo e navegue até portal.manage.microsoft.com. Entre com sua ID de usuário e senha do Microsoft 365 e tente instalar o perfil manualmente.    

## <a name="windows-rt"></a>Windows RT

- Verifique se o seu domínio está configurado no Microsoft 365 para trabalhar com mobilidade básica e segurança. Para obter mais informações, consulte [Configurar mobilidade básica e segurança](set-up-basic-mobility-and-security.md).
    
- Certifique-se de que o usuário está escolhendo **ativar em**   vez de escolher **ingressar**.    

## <a name="windows-10-pc"></a>PC Windows 10

- Verifique se o seu domínio está configurado no Microsoft 365 para trabalhar com mobilidade básica e segurança. Para obter mais informações, consulte [Configurar mobilidade básica e segurança](set-up-basic-mobility-and-security.md).
    
- A menos que você tenha o Azure Active Directory Premium, certifique-se de que o usuário está escolhendo **registrar somente o gerenciamento de dispositivos**   , em vez de escolher **conectar**.

## <a name="android-phone-or-tablet"></a>Telefone Android ou Tablet

- Verifique se o dispositivo está executando o Android 4,4 ou posterior.
    
- Verifique se o Chrome está atualizado e se está definido como o navegador padrão.
    
- Se você vir a mensagem de erro "não foi possível registrar este dispositivo", entre no Microsoft 365 e certifique-se de que uma licença que inclui o Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.
    
- Verifique a área de notificação no dispositivo para ver se as ações de usuário final necessárias estão pendentes e, se estiverem, concluem as ações.