---
title: Registrar o Microsoft Defender ATP para dispositivos macOS no Jamf Pro
description: Registrar o Microsoft Defender ATP para dispositivos macOS no Jamf Pro
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ef6e387d4e945afb71f1fa6ecef9d78ba2d74a55
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185678"
---
# <a name="enroll-microsoft-defender-for-endpoint-for-macos-devices-into-jamf-pro"></a>Registrar o Microsoft Defender para o Ponto de Extremidade para dispositivos macOS no Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Registrar dispositivos macOS

Há vários métodos de registro no JamF.

Este artigo orientará você sobre dois métodos:

- [Método 1: Convites de Inscrição](#enrollment-method-1-enrollment-invitations)
- [Método 2: Prestage Enrollments](#enrollment-method-2-prestage-enrollments)

Para ver uma lista completa, consulte [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).


## <a name="enrollment-method-1-enrollment-invitations"></a>Método de Inscrição 1: Convites para Inscrição

1. No painel do Jamf Pro, navegue até **Inscrições convites**.

    ![Imagem das configurações1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Selecione **+ Novo**.

    ![Um close-up de um logotipo Descrição gerado automaticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. Em **Especificar Destinatários para o >** em **Endereços** de Email insira os endereços de email(es) dos destinatários.

    ![Imagem das configurações2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Imagem das configurações3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Por exemplo: janedoe@contoso.com

    ![Imagem das configurações4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Configure a mensagem para o convite.

    ![Imagem das configurações5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Imagem das configurações6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Imagem das configurações7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Imagem das configurações8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Método De registro 2: Prestage Enrollments

1. No painel do Jamf Pro, navegue até **Prestage enrollments**.

    ![Imagem das configurações9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Siga as instruções em [Registro de Pré-Etapa do Computador](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>Registrar dispositivo macOS

1. Selecione **Continuar** e instale o certificado ca em uma **janela Preferências do** Sistema.

    ![Imagem do registro do Jamf Pro1](images/jamfpro-ca-certificate.png)

2. Depois que o certificado ca for instalado, retorne à janela do navegador e selecione **Continuar** e instalar o perfil MDM. 

    ![Imagem do registro do Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. Selecione **Permitir** downloads do JAMF.

    ![Imagem do registro do Jamf Pro3](images/jamfpro-download.png)

4. Selecione **Continuar** para continuar com a instalação do Perfil MDM. 

    ![Imagem do registro do Jamf Pro4](images/jamfpro-install-mdm.png)

5. Selecione **Continuar** para instalar o Perfil MDM.

    ![Imagem do registro do Jamf Pro5](images/jamfpro-mdm-unverified.png)

6. Selecione **Continuar**  para concluir a configuração. 

    ![Imagem do registro do Jamf Pro6](images/jamfpro-mdm-profile.png)
