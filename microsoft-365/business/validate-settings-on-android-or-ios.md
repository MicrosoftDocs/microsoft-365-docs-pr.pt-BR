---
title: Validar configurações de proteção do aplicativo em dispositivos Android ou iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 19a7ce48e8df5c80964a250b0bc087591a0530c1
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287866"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Validar configurações de proteção do aplicativo em dispositivos Android ou iOS

Siga as instruções nas guias para validar as configurações de proteção do aplicativo em dispositivos Android ou iOS.
  
## <a name="androidtab"></a>[Android](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário

Depois de [definir configurações de aplicativo para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas. 
  
Em primeiro lugar, certifique-se de que a política se aplica ao aplicativo no qual você a validará.
  
1. No [centro de administração](https://portal.office.com) do Microsoft 365 Business, acesse **Políticas** \> **Editar política**.
    
2. Escolha **Política de aplicativo para Android** para verificar as configurações que você criou na instalação ou outra política que você tenha criado e verifique se ela é aplicada, por exemplo, no Outlook. 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Validar Exigir um PIN ou uma impressão digital para acessar aplicativos do Office

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.
    
2. Você também deverá digitar um PIN ou usar uma impressão digital.
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar Redefinir PIN após algumas tentativas fracassadas

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Redefinir PIN após algumas tentativas fracassadas** está definida com algum número; o padrão é 5. 
  
1. No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.
    
2. Insira um PIN incorreto o número de vezes especificado pela política. Você verá um aviso informando **Limite de tentativa do PIN alcançado** para redefinir o PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Pressione **Redefinir PIN**. Você será solicitado a entrar com as credenciais do Microsoft 365 Business do usuário e configurar um novo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Abra um email que contenha um anexo e toque no ícone de seta para baixo ao lado das informações do anexo.
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Você verá **Não é possível salvar no dispositivo** na parte inferior da tela. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > A opção para salvar no OneDrive for Business não está habilitada para o Android neste momento, portanto, só é possível ver que salvar localmente está bloqueado. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado** está definida com algum número de minutos; o padrão é 30. 
  
1. No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo Android ocioso sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.
    
3. Acesse novamente o Outlook no dispositivo Android.
    
4. Você será solicitado a inserir seu PIN para poder acessar o Outlook novamente.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar Proteger arquivos de trabalho com criptografia

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.
  
1. No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Abra um email que contenha alguns arquivos de imagem em anexo.
    
3. Toque no ícone de seta para baixo ao lado das informações do anexo para salvá-lo.
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Você poderá ser solicitado a permitir que o Outlook acesse arquivos, mídia e fotos em seu dispositivo. Toque em **Permitir**.
    
5. Na parte inferior da tela, escolha **Salvar no Dispositivo** e, em seguida, abra o aplicativo **Galeria**. 
    
6. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) na lista. Ela poderá aparecer na lista Imagens como um quadrado cinza com um ponto de exclamação branco dentro de um círculo branco no centro do quadrado cinza.
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[iOS](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário

Depois de [definir configurações de aplicativo para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas. 
  
Em primeiro lugar, certifique-se de que a política se aplica ao aplicativo no qual você a validará.
  
1. No [centro de administração](https://portal.office.com) do Microsoft 365 Business, acesse **Políticas** \> **Editar política**.
    
2. Escolha **Política de aplicativo para iOS** para verificar as configurações que você criou na instalação ou outra política que você tenha criado e verifique se ela é aplicada, por exemplo, no Outlook. 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Validar Exigir um PIN para acessar aplicativos do Office

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.
    
2. Você também deverá digitar um PIN ou usar uma impressão digital.
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar Redefinir PIN após algumas tentativas fracassadas

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Redefinir PIN após algumas tentativas fracassadas** está definida com algum número; o padrão é 5. 
  
1. No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.
    
2. Insira um PIN incorreto o número de vezes especificado pela política. Você verá um aviso informando **Limite de tentativa do PIN alcançado** para redefinir o PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Pressione **OK**. Você será solicitado a entrar com as credenciais do Microsoft 365 Business do usuário e configurar um novo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Abra um email que contenha um anexo, abra o anexo e escolha **Salvar** na parte inferior da tela. 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Você só verá uma opção para o OneDrive for Business. Caso contrário, toque em **Adicionar Conta** e escolha **OneDrive for Business** na tela **Adicionar Conta de Armazenamento**. Forneça o Microsoft 365 Business do usuário final para entrar quando solicitado. 
    
    Toque em **Salvar** e selecione **OneDrive for Business**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado** está definida com algum número de minutos; o padrão é 30. 
  
1. No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo iOS sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.
    
3. Acesse novamente o Outlook no dispositivo iOS.
    
4. Você será solicitado a inserir seu PIN para poder acessar o Outlook novamente.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar Proteger arquivos de trabalho com criptografia

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.
  
1. No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.
    
2. Abra um email que contenha alguns arquivos de imagem em anexo.
    
3. Toque no anexo e, em seguida, toque na opção **Salvar** abaixo dele. 
    
4. Abra o aplicativo **Fotos** na tela inicial. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) salva, mas criptografada. 
    
---

