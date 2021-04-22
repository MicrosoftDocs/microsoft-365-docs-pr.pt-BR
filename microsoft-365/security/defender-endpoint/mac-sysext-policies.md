---
title: Novos perfis de configuração para macOS Catalina e versões mais recentes do macOS
description: Este tópico descreve as alterações que devem ser feitas para se beneficiar das extensões do sistema, que são uma substituição para extensões de kernel no macOS Catalina e versões mais recentes do macOS.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, kernel, sistema, extensões, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932734"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="1181f-104">Novos perfis de configuração para macOS Catalina e versões mais recentes do macOS</span><span class="sxs-lookup"><span data-stu-id="1181f-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1181f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1181f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1181f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1181f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1181f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1181f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1181f-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1181f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1181f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1181f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1181f-110">Em alinhamento com a evolução do macOS, estamos preparando um Microsoft Defender para Endpoint na atualização do macOS que aproveita extensões do sistema em vez de extensões de kernel.</span><span class="sxs-lookup"><span data-stu-id="1181f-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on macOS update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="1181f-111">Essa atualização só será aplicável ao macOS Catalina (10.15.4) e versões mais recentes do macOS.</span><span class="sxs-lookup"><span data-stu-id="1181f-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="1181f-112">Se você implantou o Microsoft Defender para o Ponto de Extremidade no macOS em um ambiente gerenciado (por meio de JAMF, Intune ou outra solução MDM), você deve implantar novos perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="1181f-112">If you have deployed Microsoft Defender for Endpoint on macOS in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="1181f-113">A falha ao executar essas etapas fará com que os usuários receberem prompts de aprovação para executar esses novos componentes.</span><span class="sxs-lookup"><span data-stu-id="1181f-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="1181f-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="1181f-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="1181f-115">Política de Extensões do Sistema</span><span class="sxs-lookup"><span data-stu-id="1181f-115">System Extensions Policy</span></span>

<span data-ttu-id="1181f-116">Para aprovar as extensões do sistema, crie a seguinte carga:</span><span class="sxs-lookup"><span data-stu-id="1181f-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="1181f-117">Em **Computadores > Perfis de Configuração** selecione **Opções > Extensões do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="1181f-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="1181f-118">Selecione **Extensões de Sistema Permitidos** **na** listada tipos de extensão do sistema.</span><span class="sxs-lookup"><span data-stu-id="1181f-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="1181f-119">Use **UBF8T346G9** para id de equipe.</span><span class="sxs-lookup"><span data-stu-id="1181f-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="1181f-120">Adicione os seguintes identificadores de pacote à lista **Extensões de Sistema Permitidos:**</span><span class="sxs-lookup"><span data-stu-id="1181f-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="1181f-121">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="1181f-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="1181f-122">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="1181f-122">**com.microsoft.wdav.netext**</span></span>

    ![Captura de tela de extensões do sistema aprovadas](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="1181f-124">Controle de Política de Preferências de Privacidade</span><span class="sxs-lookup"><span data-stu-id="1181f-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="1181f-125">Adicione a seguinte carga JAMF para conceder Acesso total em disco ao Microsoft Defender para Extensão de Segurança do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1181f-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="1181f-126">Esta política é um pré-requisito para executar a extensão em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1181f-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="1181f-127">Selecione **Opções**  >  **Controle de Política de Preferências de Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="1181f-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="1181f-128">Use `com.microsoft.wdav.epsext` como o **Identificador e** como tipo de `Bundle ID` **pacote**.</span><span class="sxs-lookup"><span data-stu-id="1181f-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="1181f-129">Definir Requisito de Código como `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="1181f-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="1181f-130">Definir **aplicativo ou serviço como** **SystemPolicyAllFiles** e acesso a **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="1181f-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![Controle de Política de Preferências de Privacidade](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="1181f-132">Política de Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="1181f-132">Network Extension Policy</span></span>

<span data-ttu-id="1181f-133">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade no macOS inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1181f-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="1181f-134">A política a seguir permite que a extensão de rede execute essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="1181f-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="1181f-135">O JAMF não tem suporte integrado para políticas de filtragem de conteúdo, que são um pré-requisito para habilitar as extensões de rede que o Microsoft Defender para Ponto de Extremidade instala no macOS no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1181f-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint on macOS installs on the device.</span></span> <span data-ttu-id="1181f-136">Além disso, o JAMF às vezes altera o conteúdo das políticas que estão sendo implantadas.</span><span class="sxs-lookup"><span data-stu-id="1181f-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="1181f-137">Dessa forma, as etapas a seguir fornecem uma solução alternativa que envolve a assinatura do perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="1181f-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="1181f-138">Salve o seguinte conteúdo em seu dispositivo como `com.microsoft.network-extension.mobileconfig` usando um editor de texto:</span><span class="sxs-lookup"><span data-stu-id="1181f-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. <span data-ttu-id="1181f-139">Verifique se o arquivo acima foi copiado corretamente executando o `plutil` utilitário no Terminal:</span><span class="sxs-lookup"><span data-stu-id="1181f-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="1181f-140">Por exemplo, se o arquivo foi armazenado em Documentos:</span><span class="sxs-lookup"><span data-stu-id="1181f-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="1181f-141">Verifique se o comando saídas `OK` .</span><span class="sxs-lookup"><span data-stu-id="1181f-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="1181f-142">Siga as instruções nesta [página](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) para criar um certificado de assinatura usando a autoridade de certificação do JAMF.</span><span class="sxs-lookup"><span data-stu-id="1181f-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="1181f-143">Depois que o certificado for criado e instalado em seu dispositivo, execute o seguinte comando do Terminal para assinar o arquivo:</span><span class="sxs-lookup"><span data-stu-id="1181f-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="1181f-144">Por exemplo, se o nome do certificado for **SigningCertificate** e o arquivo assinado for armazenado em Documentos:</span><span class="sxs-lookup"><span data-stu-id="1181f-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="1181f-145">No portal JAMF, navegue até **Perfis de Configuração** e clique no **botão Carregar.**</span><span class="sxs-lookup"><span data-stu-id="1181f-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="1181f-146">Selecione `com.microsoft.network-extension.signed.mobileconfig` quando solicitado para o arquivo.</span><span class="sxs-lookup"><span data-stu-id="1181f-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="1181f-147">Intune</span><span class="sxs-lookup"><span data-stu-id="1181f-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="1181f-148">Política de Extensões do Sistema</span><span class="sxs-lookup"><span data-stu-id="1181f-148">System Extensions Policy</span></span>

<span data-ttu-id="1181f-149">Para aprovar as extensões do sistema:</span><span class="sxs-lookup"><span data-stu-id="1181f-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="1181f-150">No Intune, abra **Gerenciar**  >  **configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1181f-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1181f-151">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="1181f-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="1181f-152">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="1181f-152">Choose a name for the profile.</span></span> <span data-ttu-id="1181f-153">Alterar **Platform=macOS** para **Profile type=Extensions**.</span><span class="sxs-lookup"><span data-stu-id="1181f-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="1181f-154">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="1181f-154">Select **Create**.</span></span>
3. <span data-ttu-id="1181f-155">Na `Basics` guia, dê um nome a esse novo perfil.</span><span class="sxs-lookup"><span data-stu-id="1181f-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="1181f-156">Na `Configuration settings` guia, adicione as seguintes entradas na `Allowed system extensions` seção:</span><span class="sxs-lookup"><span data-stu-id="1181f-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="1181f-157">Identificador de pacote</span><span class="sxs-lookup"><span data-stu-id="1181f-157">Bundle identifier</span></span>         | <span data-ttu-id="1181f-158">Identificador de equipe</span><span class="sxs-lookup"><span data-stu-id="1181f-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="1181f-159">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="1181f-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="1181f-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="1181f-160">UBF8T346G9</span></span>
    <span data-ttu-id="1181f-161">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="1181f-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="1181f-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="1181f-162">UBF8T346G9</span></span>

    ![Captura de tela de perfis de configuração do sistema](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="1181f-164">Na `Assignments` guia, atribua esse perfil a **Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1181f-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="1181f-165">Revise e crie esse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="1181f-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="1181f-166">Criar e implantar o Perfil de Configuração Personalizado</span><span class="sxs-lookup"><span data-stu-id="1181f-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="1181f-167">O perfil de configuração a seguir habilita a extensão de rede e concede acesso total em disco à extensão do sistema de Segurança do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1181f-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="1181f-168">Salve o seguinte conteúdo em um arquivo chamado **sysext.xml**:</span><span class="sxs-lookup"><span data-stu-id="1181f-168">Save the following content to a file named **sysext.xml**:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="1181f-169">Verifique se o arquivo acima foi copiado corretamente.</span><span class="sxs-lookup"><span data-stu-id="1181f-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="1181f-170">No Terminal, execute o seguinte comando e verifique se ele `OK` saída :</span><span class="sxs-lookup"><span data-stu-id="1181f-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="1181f-171">Para implantar esse perfil de configuração personalizado:</span><span class="sxs-lookup"><span data-stu-id="1181f-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="1181f-172">No Intune, abra **Gerenciar**  >  **configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1181f-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="1181f-173">Selecione **Gerenciar**  >    >  **Perfis Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="1181f-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="1181f-174">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="1181f-174">Choose a name for the profile.</span></span> <span data-ttu-id="1181f-175">Alterar **Platform=macOS** e **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="1181f-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="1181f-176">Selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1181f-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="1181f-177">Abra o perfil de configuração e carregue **sysext.xml**.</span><span class="sxs-lookup"><span data-stu-id="1181f-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="1181f-178">Esse arquivo foi criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="1181f-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="1181f-179">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1181f-179">Select **OK**.</span></span>

    ![Extensão do sistema no Intune captura de tela](images/mac-system-extension-intune.png)

5. <span data-ttu-id="1181f-181">Na `Assignments` guia, atribua esse perfil a **Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1181f-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="1181f-182">Revise e crie esse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="1181f-182">Review and create this configuration profile.</span></span>
