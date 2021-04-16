---
title: Registrar o Microsoft Defender para o Ponto de Extremidade para dispositivos macOS no Jamf Pro
description: Registrar o Microsoft Defender para o Ponto de Extremidade para dispositivos macOS no Jamf Pro
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
ms.openlocfilehash: e832493159649cb6721320da53c25f57855baa4f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861642"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="2bf3b-104">Registrar o Microsoft Defender para o Ponto de Extremidade em dispositivos macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2bf3b-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2bf3b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2bf3b-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bf3b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2bf3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bf3b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bf3b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2bf3b-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2bf3b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2bf3b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="2bf3b-110">Registrar dispositivos macOS</span><span class="sxs-lookup"><span data-stu-id="2bf3b-110">Enroll macOS devices</span></span>

<span data-ttu-id="2bf3b-111">Há vários métodos de registro no JamF.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="2bf3b-112">Este artigo orientará você sobre dois métodos:</span><span class="sxs-lookup"><span data-stu-id="2bf3b-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="2bf3b-113">Método 1: Convites de Inscrição</span><span class="sxs-lookup"><span data-stu-id="2bf3b-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="2bf3b-114">Método 2: Prestage Enrollments</span><span class="sxs-lookup"><span data-stu-id="2bf3b-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="2bf3b-115">Para ver uma lista completa, consulte [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span><span class="sxs-lookup"><span data-stu-id="2bf3b-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="2bf3b-116">Método de Inscrição 1: Convites para Inscrição</span><span class="sxs-lookup"><span data-stu-id="2bf3b-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="2bf3b-117">No painel do Jamf Pro, navegue até **Inscrições convites**.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Imagem das configurações1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="2bf3b-119">Selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-119">Select **+ New**.</span></span>

    ![Um close-up de um logotipo Descrição gerado automaticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="2bf3b-121">Em **Especificar Destinatários para o >** em **Endereços** de Email insira os endereços de email(es) dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Imagem das configurações2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Imagem das configurações3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="2bf3b-124">Por exemplo: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2bf3b-124">For example: janedoe@contoso.com</span></span>

    ![Imagem das configurações4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="2bf3b-126">Configure a mensagem para o convite.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-126">Configure the message for the invitation.</span></span>

    ![Imagem das configurações5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Imagem das configurações6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Imagem das configurações7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Imagem das configurações8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="2bf3b-131">Método De registro 2: Prestage Enrollments</span><span class="sxs-lookup"><span data-stu-id="2bf3b-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="2bf3b-132">No painel do Jamf Pro, navegue até **Prestage enrollments**.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Imagem das configurações9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="2bf3b-134">Siga as instruções em [Registro de Pré-Etapa do Computador](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span><span class="sxs-lookup"><span data-stu-id="2bf3b-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="2bf3b-135">Registrar dispositivo macOS</span><span class="sxs-lookup"><span data-stu-id="2bf3b-135">Enroll macOS device</span></span>

1. <span data-ttu-id="2bf3b-136">Selecione **Continuar** e instale o certificado ca em uma **janela Preferências do** Sistema.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Imagem do registro do Jamf Pro1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="2bf3b-138">Depois que o certificado ca for instalado, retorne à janela do navegador e selecione **Continuar** e instalar o perfil MDM.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Imagem do registro do Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="2bf3b-140">Selecione **Permitir** downloads do JAMF.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Imagem do registro do Jamf Pro3](images/jamfpro-download.png)

4. <span data-ttu-id="2bf3b-142">Selecione **Continuar** para continuar com a instalação do Perfil MDM.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Imagem do registro do Jamf Pro4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="2bf3b-144">Selecione **Continuar** para instalar o Perfil MDM.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Imagem do registro do Jamf Pro5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="2bf3b-146">Selecione **Continuar**  para concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="2bf3b-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Imagem do registro do Jamf Pro6](images/jamfpro-mdm-profile.png)
