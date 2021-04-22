---
title: Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro
description: Saiba como configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro
keywords: policies, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 84d0b37632dc23615a37bbbd73c17fe509dedae5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934676"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Configurar o Microsoft Defender para Ponto de Extremidade em políticas macOS no Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Defender para Ponto de Extremidade no Mac](microsoft-defender-endpoint-mac.md)

Esta página o guiará pelas etapas necessárias para configurar políticas macOS no Jamf Pro.

Você precisará seguir as seguintes etapas:

1. [Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Criar um perfil de configuração no Jamf Pro usando o pacote de integração](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Configurar configurações do Microsoft Defender para Ponto de Extremidade](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Configurar configurações de notificação do Microsoft Defender para Ponto de Extremidade](#step-4-configure-notifications-settings)

5. [Configurar o Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Configurar Extensão de Rede](#step-9-configure-network-extension)

10. [Agendar verificações com o Microsoft Defender para Ponto de Extremidade no macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Implantar o Microsoft Defender para Ponto de Extremidade no macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Etapa 1: Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade

1. No [Centro de Segurança do Microsoft Defender,](https://securitycenter.microsoft.com )navegue até **Configurações > Integração**. 

2. Selecione macOS como o sistema operacional e o Gerenciamento de Dispositivo Móvel /Microsoft Intune como o método de implantação.

    ![Imagem do Centro de Segurança do Microsoft Defender](images/onboarding-macos.png)

3. Selecione **Baixar pacote de integração** (WindowsDefenderATPOnboardingPackage.zip).

4. Extrair `WindowsDefenderATPOnboardingPackage.zip` .

5. Copie o arquivo para o local preferencial. Por exemplo, `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Etapa 2: Criar um perfil de configuração no Jamf Pro usando o pacote de integração

1. Localize o `WindowsDefenderATPOnboarding.plist` arquivo da seção anterior.

   ![Imagem do arquivo WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. No painel Jamf Pro, selecione **Novo**.

    ![Imagem da criação de um novo painel do Jamf Pro](images/jamf-pro-configure-profile.png)

3. Insira os seguintes detalhes:

   **Geral**
   - Nome: integração MDATP para macOS
   - Descrição: integração de EDR MDATP para macOS
   - Categoria: Nenhum
   - Método Distribution: Install Automatically
   - Nível: Nível do computador

4. No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.

    ![Imagem de configuração de aplicativo e configurações personalizadas](images/jamfpro-mac-profile.png)

5. Selecione **Carregar Arquivo (arquivo PLIST)** em **Domínio de Preferência** insira: `com.microsoft.wdav.atp` . 

    ![Imagem do arquivo de carregamento de jamfpro plist](images/jamfpro-plist-upload.png)

    ![Imagem da propriedade De lista de propriedades de arquivo de carregamento](images/jamfpro-plist-file.png)

7. Selecione **Abrir** e selecione o arquivo de integração.

    ![Imagem do arquivo de integração](images/jamfpro-plist-file-onboard.png)

8. Selecione **Carregar**. 

    ![Imagem do carregamento de arquivo plist](images/jamfpro-upload-plist.png)


9. Selecione a **guia Escopo.**

    ![Imagem da guia escopo](images/jamfpro-scope-tab.png)

10. Selecione os computadores de destino.

    ![Imagem de computadores de destino](images/jamfpro-target-computer.png)

    ![Imagem de destinos](images/jamfpro-targets.png) 

11. Selecione **Salvar**.

    ![Imagem de computadores de destino de implantação](images/jamfpro-deployment-target.png)

    ![Imagem dos computadores de destino selecionados](images/jamfpro-target-selected.png)

12. Selecione **Concluído**.

    ![Imagem de computadores de grupo de destino](images/jamfpro-target-group.png)

    ![Lista de perfis de configuração](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Etapa 3: Configurar o Microsoft Defender para configurações de ponto de extremidade

1.  Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:

    - enableRealTimeProtection
    - passiveMode
    
    >[!NOTE]
    >Não está ligado por padrão, se você estiver planejando executar um AV de terceiros para macOS, de defini-lo como `true` .

    - exclusões
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats
    
    >[!NOTE]
    >EICAR está no exemplo, se você estiver passando por uma prova de conceito, remova-o especialmente se estiver testando o EICAR.
        
    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon
    
     Para obter informações, consulte [Lista de propriedades para perfil de configuração jamf](mac-preferences.md#property-list-for-jamf-configuration-profile).

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Salve o arquivo como `MDATP_MDAV_configuration_settings.plist` .


3.  No painel Jamf Pro, selecione **Geral**.

    ![Imagem do novo painel do Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Insira os seguintes detalhes:

    **Geral**
    
    - Nome: configurações MDATP MDAV
    - Descrição:\<blank\>
    - Categoria: Nenhum (padrão)
    - Método Distribution: Install Automatically(default)
    - Nível: Nível do Computador(padrão)

    ![Imagem das configurações MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.

    ![Imagem do aplicativo e configurações personalizadas](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Selecione **Carregar Arquivo (arquivo PLIST)**.

    ![Imagem do arquivo plist de configurações](images/6f85269276b2278eca4bce84f935f87b.png)

7. Em **Domínio preferências**, digite `com.microsoft.wdav` , em seguida, selecione Carregar Arquivo  **PLIST**.

    ![Imagem do domínio de preferências de configurações](images/db15f147dd959e872a044184711d7d46.png)

8. Selecione **Escolher Arquivo**.

    ![Imagem das configurações de configuração escolha arquivo](images/526e978761fc571cca06907da7b01fd6.png)

9. Selecione o **MDATP_MDAV_configuration_settings.plist** e, em seguida, **selecione Abrir**.

    ![Imagem das configurações do mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Selecione **Carregar**.

    ![Imagem de carregamento da configuração de configuração](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Imagem de configurações configurações carregando imagem](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Se você carregar o arquivo do Intune, obterá o seguinte erro:<br>
    >![Imagem das configurações de carregamento de arquivo do intune](images/8e69f867664668796a3b2904896f0436.png)


11. Selecione **Salvar**. 

    ![Imagem das configurações Salvar imagem](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. O arquivo é carregado.

    ![Imagem do arquivo carregado de configurações de configurações](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Imagem do arquivo de configurações de configuração carregado](images/a422e57fe8d45689227e784443e51bd1.png)

13. Selecione a **guia Escopo.**

    ![Imagem do escopo das configurações](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Selecione **Grupo de Máquinas da Contoso.** 

15. Selecione **Adicionar** e, em seguida, **selecione Salvar**.

    ![Imagem das configurações de configuração addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Imagem das configurações salvar adicionar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Selecione **Concluído**. Você verá o novo perfil **de configuração.**

    ![Imagem das configurações configurações config imagem de perfil](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a>Etapa 4: Configurar configurações de notificações

Essas etapas são aplicáveis ao macOS 10.15 (Catalina) ou mais novo.

1. No painel Jamf Pro, selecione **Computadores** e, em seguida, **Perfis de Configuração.**

2. Clique **em Novo** e insira os seguintes detalhes para **Opções**:
    
    - Guia **Geral**: 
        - **Nome**: Configurações de Notificação MDATP MDAV
        - **Descrição**: macOS 10.15 (Catalina) ou mais novo
        - **Categoria**: Nenhum *(padrão)*
        - **Método Distribution**: Instalar Automaticamente *(padrão)*
        - **Nível**: Nível do *computador (padrão)*

        ![Imagem da nova tela de perfil de configuração do macOS](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Notificações **de tabulação,** clique **em Adicionar** e insira os seguintes valores:
        - **ID do pacote:**`com.microsoft.wdav.tray`
        - **Alertas críticos:** clique em **Desabilitar**
        - **Notificações**: Clique em **Habilitar**
        - **Tipo de alerta de faixa**: Selecione **Incluir** **e Temporário** *(padrão)*
        - **Notificações na tela de bloqueio**: Clique em **Ocultar**
        - **Notificações na Central de Notificações**: Clique em **Exibir**
        - **Ícone do aplicativo selo:** clique em **Exibir**

        ![Imagem das configurações configurações bandeja de notificações mdatpmdav](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Notificações **de tabulação**, clique em **Adicionar** mais uma vez, role para baixo até **Novas Configurações de Notificações**
        - **ID do pacote:**`com.microsoft.autoupdate2`
        - Configurar o restante das configurações para os mesmos valores acima

        ![Imagem de configurações configurações mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Observe que agora você tem duas "tabelas" com configurações de notificação, uma para iD do **pacote: com.microsoft.wdav.tray** e outra para iD do **pacote: com.microsoft.autoupdate2**. Embora você possa configurar as configurações de alerta de acordo com seus  **requisitos,** as IDs de pacote devem ser exatamente as mesmas descritas anteriormente, e a opção Incluir deve estar Em **para** Notificações .

3. Selecione a **guia Escopo** e selecione **Adicionar**.

    ![Imagem do escopo de configurações adicionar](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Selecione **Grupo de Máquinas da Contoso.** 

5. Selecione **Adicionar** e, em seguida, **selecione Salvar**.
    
    ![Imagem das configurações contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Imagem de configurações configurações adicionar salvar](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Selecione **Concluído**. Você verá o novo perfil **de configuração.**
    ![Imagem da configuração configuração feita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Etapa 5: Configurar o Microsoft AutoUpdate (MAU)

1. Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Salve-o como `MDATP_MDAV_MAU_settings.plist` .

3. No painel Jamf Pro, selecione **Geral**. 

    ![Imagem da configuração de configuração de imagem geral](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Insira os seguintes detalhes:

    **Geral** 
    
    - Nome: configurações MDATP MDAV MAU
    - Descrição: Configurações do Microsoft AutoUpdate para MDATP para macOS
    - Categoria: Nenhum (padrão)
    - Método Distribution: Install Automatically(default)
    - Nível: Nível do Computador(padrão)

5. No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.

    ![Imagem do aplicativo de configuração e configurações personalizadas](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Selecione **Carregar Arquivo (arquivo PLIST)**.

    ![Imagem da configuração plist de configuração](images/1213872db5833aa8be535da57653219f.png)  

7. In **Preference Domain** enter: , then select Upload `com.microsoft.autoupdate2` **PLIST File**.

    ![Imagem da configuração de configuração de domínio pref](images/1213872db5833aa8be535da57653219f.png)

8. Selecione **Escolher Arquivo**.

    ![Imagem da configuração de configuração choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Selecione **MDATP_MDAV_MAU_settings.plist**.

    ![Imagem de configuração definindo configurações mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Selecione **Carregar**.
    ![Imagem da configuração de configuração de](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Imagem da configuração configurando uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Selecione **Salvar**.

    ![Imagem da configuração saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Selecione a **guia Escopo.**
   
     ![Imagem de escopo de configuração](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Clique em **Adicionar**.
    
    ![Imagem da configuração addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Imagem da configuração addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Imagem da configuração addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Selecione **Concluído**.
    
    ![Imagem da configuração configuração doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Etapa 6: Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade

1. No painel Jamf Pro, selecione **Perfis de Configuração**.

    ![Imagem do perfil de configuração de configuração de configuração](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Selecione **+ Novo**. 

3. Insira os seguintes detalhes:

    **Geral** 
    - Nome: MDATP MDAV - conceder acesso de disco completo a EDR e AV
    - Descrição: no macOS Catalina ou mais novo, o novo Controle de Política de Preferências de Privacidade
    - Categoria: Nenhum
    - Método de distribuição: Instalar Automaticamente
    - Nível: nível do computador


    ![Imagem da configuração geral](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. Em **Configurar o Controle de Política de Preferências de Privacidade,** selecione **Configurar**.

    ![Imagem do controle de política de privacidade de configuração](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. No **Controle de Política de Preferências de Privacidade,** insira os seguintes detalhes:

    - Identificador: `com.microsoft.wdav`
    - Tipo de identificador: ID do pacote
    - Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Imagem de configuração definindo detalhes de controle de política de preferência de privacidade](images/22cb439de958101c0a12f3038f905b27.png)

6. Selecione **+ Adicionar**.

    ![Imagem da configuração de configuração adicionar política do sistema todos os arquivos](images/bd93e78b74c2660a0541af4690dd9485.png)

    - Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**

    - Em "access": Definir como **Permitir**

7. Selecione **Salvar** (não o da parte inferior direita).

    ![Imagem da configuração configuração salvar imagens](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Clique na `+` entrada ao lado do App **Access** para adicionar uma nova entrada.

    ![Imagem da configuração de configuração de acesso ao aplicativo](images/tcc-add-entry.png)

9. Insira os seguintes detalhes:

    - Identificador: `com.microsoft.wdav.epsext`
    - Tipo de identificador: ID do pacote
    - Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Selecione **+ Adicionar**.

    ![Imagem da configuração de configuração tcc epsext entry](images/tcc-epsext-entry.png)

    - Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**

    - Em "access": Definir como **Permitir**

11. Selecione **Salvar** (não o da parte inferior direita).

    ![Imagem da configuração de configuração tcc epsext image2](images/tcc-epsext-entry2.png)

12. Selecione a **guia Escopo.**

    ![Imagem do escopo de configuração](images/2c49b16cd112729b3719724f581e6882.png)

13. Selecione **+ Adicionar**.

    ![Imagem da configuração addimage de configuração](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Selecione **Grupos de >** em **Nome** do Grupo > selecione **MachineGroup da Contoso.** 

    ![Imagem da configuração de configuração contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Clique em **Adicionar**. 

16. Selecione **Salvar**. 
    
17. Selecione **Concluído**.
    
    ![Imagem da configuração donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Imagem da configuração donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

Como alternativa, você pode baixar [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) e enviá-lo para Perfis de Configuração JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Etapa 7: Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade

> [!CAUTION]
> Os dispositivos Apple Silicon (M1) não suportam KEXT. A instalação de um perfil de configuração que consiste em políticas KEXT falhará nesses dispositivos.

1. Nos **Perfis de Configuração,** selecione **+ Novo**.

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Insira os seguintes detalhes:

    **Geral** 
    
    - Nome: Extensão de Kernel MDATP MDAV
    - Descrição: extensão de kernel MDATP (kext)
    - Categoria: Nenhum
    - Método Distribution: Install Automatically
    - Nível: Nível do computador

    ![Imagem das configurações do kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. Em **Configurar Extensões de Kernel Aprovados,** **selecione Configurar**.

    ![Imagem das configurações do kernel ext aprovado](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. Em **Extensões de Kernel Aprovadas** Insira os seguintes detalhes:

    - Nome para exibição: Microsoft Corp.
    - ID da equipe: UBF8T346G9

    ![Imagem das configurações de extensão do kernel do appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Selecione a **guia Escopo.**

    ![Imagem da guia de escopo de configurações img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selecione **+ Adicionar**.

7. Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**

8. Selecione **+ Adicionar**.

    ![Imagem das configurações configurações adicionam imagens](images/0dde8a4c41110dbc398c485433a81359.png)

9. Selecione **Salvar**.

    ![Imagem das configurações saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Selecione **Concluído**.

    ![Imagem das configurações doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

Como alternativa, você pode baixar [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) e enviá-lo para Perfis de Configuração JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Etapa 8: Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade

1. Nos **Perfis de Configuração,** selecione **+ Novo**.

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Insira os seguintes detalhes:

    **Geral**
    
    - Nome: Extensões do Sistema MDATP MDAV
    - Descrição: extensões do sistema MDATP
    - Categoria: Nenhum
    - Método Distribution: Install Automatically
    - Nível: Nível do computador

    ![Imagem das configurações sysext novo prof](images/sysext-new-profile.png)

3. Em **Extensões do Sistema,** selecione **Configurar**.

   ![Imagem de configuração configurações sysext config](images/sysext-configure.png)

4. Em **Extensões do Sistema,** insira os seguintes detalhes:

   - Nome da exibição: Microsoft Corp. Extensões do sistema
   - Tipos de extensão do sistema: Extensões permitidas do sistema
   - Identificador de equipe: UBF8T346G9
   - Extensões de sistema permitidas:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Imagem das configurações sysextconfig2](images/sysext-configure2.png)

5. Selecione a **guia Escopo.**

    ![Imagem de escopo de configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Selecione **+ Adicionar**.

7. Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**

8. Selecione **+ Adicionar**.

   ![Imagem de addima de configurações de configuração](images/0dde8a4c41110dbc398c485433a81359.png)

9. Selecione **Salvar**.

   ![Imagem do escopo sysext das configurações](images/sysext-scope.png)

10. Selecione **Concluído**.

    ![Imagem das configurações sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Etapa 9: Configurar a Extensão de Rede

Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade no macOS inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender. A política a seguir permite que a extensão de rede execute essa funcionalidade.

Essas etapas são aplicáveis ao macOS 10.15 (Catalina) ou mais novo.

1. No painel Jamf Pro, selecione **Computadores** e, em seguida, **Perfis de Configuração.**

2. Clique **em Novo** e insira os seguintes detalhes para **Opções**:

    - Guia **Geral**: 
        - **Nome**: Extensão de Rede do Microsoft Defender ATP
        - **Descrição**: macOS 10.15 (Catalina) ou mais novo
        - **Categoria**: Nenhum *(padrão)*
        - **Método Distribution**: Instalar Automaticamente *(padrão)*
        - **Nível**: Nível do *computador (padrão)*

    - Filtro **de Conteúdo de Tabulação**:
        - **Nome do filtro**: Filtro de Conteúdo do Microsoft Defender ATP
        - **Identificador**: `com.microsoft.wdav`
        - Deixar **Endereço de Serviço,** **Organização,** **Nome de Usuário,** **Senha,** **Certificado** em branco (**Incluir** não *está* selecionado)
        - **Ordem de Filtro**: Inspector
        - **Filtro soquete**: `com.microsoft.wdav.netext`
        - **Requisito designado do filtro de soquete:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Deixar **campos de Filtro de** Rede em branco (**Incluir** não *está* selecionado)

        Observe que **Os valores exatos de Identificador,** **Filtro de Soquete** e Filtro **de Soquete designados,** conforme especificado acima.

        ![Imagem da configuração de configuração mdatpmdav](images/netext-create-profile.png)

3. Selecione a **guia Escopo.**

   ![Guia Descarr da imagem das configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Selecione **+ Adicionar**.

5. Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**

6. Selecione **+ Adicionar**.

    ![Imagem das configurações adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. Selecione **Salvar**.

    ![Imagem das configurações savimg netextscop](images/netext-scope.png)

8. Selecione **Concluído**.

    ![Imagem das configurações netextfinal](images/netext-final.png)

Como alternativa, você pode baixar [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) e carregar nos Perfis de Configuração DO JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Etapa 10: Agendar verificações com o Microsoft Defender para Ponto de Extremidade no macOS
Siga as instruções em [Agendar verificações com o Microsoft Defender para Ponto de Extremidade no macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Etapa 11: Implantar o Microsoft Defender para Ponto de Extremidade no macOS

1. Navegue até onde você salvou `wdav.pkg` .

    ![Imagem do explorador de arquivos wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Renomeie-o para `wdav_MDM_Contoso_200329.pkg` .

    ![Imagem do explorador de arquivos1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Abra o painel Jamf Pro.

    ![Imagem das configurações jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Selecione o computador e clique no ícone de engrenagem na parte superior e selecione **Gerenciamento de Computador**.

    ![Imagem das configurações compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. Em **Pacotes,** selecione **+ Novo**. 
    ![Uma imagem que contém a descrição do pacote gerado automaticamente automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. Em **Novo Pacote** Insira os seguintes detalhes:

    **Guia Geral**
    - Nome da exibição: deixe em branco por enquanto. Porque ele será redefinido quando você escolher seu pkg.
    - Categoria: Nenhum (padrão)
    - Nome do arquivo: Escolher Arquivo

    ![Imagem da guia geral configurações](images/21de3658bf58b1b767a17358a3f06341.png)

    Abra o arquivo e aponte para `wdav.pkg` ou `wdav_MDM_Contoso_200329.pkg` .
    
    ![Uma captura de tela de uma tela do computador Descrição gerada automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Selecione **Abrir**. De definir **o Nome de Exibição** **como Proteção Avançada contra Ameaças do Microsoft Defender e o Microsoft Defender Antivírus**.

    **O Arquivo de Manifesto** não é necessário. O Microsoft Defender para Ponto de Extremidade funciona sem Arquivo de Manifesto.
    
    **Guia Opções**<br> Mantenha valores padrão.

    **Guia Limitações**<br> Mantenha valores padrão.
    
     ![Guia de limitação de configurações da imagem](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. Selecione **Salvar**. O pacote é carregado para o Jamf Pro. 

   ![Imagem das configurações pacote upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   Pode levar alguns minutos para o pacote estar disponível para implantação.
   
   ![Imagem das configurações empacotam upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Navegue até **a página Políticas.**

    ![Imagem das configurações de configurações de polônias](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Selecione **+ Novo** para criar uma nova política.

    ![Imagem das configurações configurações nova política](images/847b70e54ed04787e415f5180414b310.png)


11. Em **Geral** Insira os seguintes detalhes:

    - Nome para exibição: MDATP Onboarding Contoso 200329 v100.86.92 ou posterior

    ![Imagem das configuraçõesmdatponboard ](images/625ba6d19e8597f05e4907298a454d28.png)

12. Selecione **Check-in recorrente**. 
    
    ![Imagem de configurações configurações recorrem à verificação](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. Selecione **Salvar**. 
 
14. Selecione **Pacotes > Configurar**.
 
    ![Imagem do pacote de configurações configurações](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Selecione o **botão Adicionar** ao lado da Proteção Avançada contra Ameaças do Microsoft Defender e do Microsoft **Defender Antivírus.**

    ![Imagem das configurações MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Selecione **Salvar**.

    ![Imagem das configurações de configuraçãossavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Selecione a **guia Escopo.**  

    ![Imagem das configurações scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Selecione os computadores de destino.

    ![Imagem das configurações tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**
    
    Clique em **Adicionar**.
    
    ![Imagem das configurações do ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Imagem das configurações do ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Autoatend**
    
    ![Imagem de autoatendiço de configurações](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Selecione **Concluído**. 

    ![Imagem das configurações do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Imagem das configurações do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




