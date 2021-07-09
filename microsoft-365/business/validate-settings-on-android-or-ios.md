---
title: Validar configurações de proteção de aplicativos em dispositivos Android ou iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Saiba como validar as configurações Microsoft 365 Business Premium proteção do aplicativo em seus dispositivos Android ou iOS.
ms.openlocfilehash: 43e74b548711550090021c39096b1647cee9e039
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339321"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Validar configurações de proteção de aplicativos em dispositivos Android ou iOS

Siga as instruções nas seções a seguir para validar as configurações de proteção de aplicativos em dispositivos Android ou iOS.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verifique se as configurações de proteção do aplicativo estão funcionando em dispositivos de usuário

Depois de [definir configurações de aplicativo para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas. 
  
Primeiro, certifique-se de que a política se aplique ao aplicativo no qual você irá validá-la.
  
1. No centro de Microsoft 365 Business Premium [de administração,](https://admin.microsoft.com)vá para **Política Editar** \> **política**.
    
2. Escolha **Política de aplicativo** para Android para as configurações criadas na instalação ou outra política que você criou e verifique se ela é imposta para Outlook, por exemplo. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Validar Exigir um PIN ou uma impressão digital para acessar aplicativos do Office

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.
  
![Certifique-se de que a opção Exigir um PIN ou impressão digital para acessar Office aplicativos está definida como On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.
    
2. Você também será solicitado a inserir um PIN ou usar uma impressão digital.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar Redefinir PIN após algumas tentativas fracassadas

No painel **Editar** política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda **Gerenciar como** os usuários acessam arquivos Office em dispositivos móveis e certifique-se de que **Redefinir PIN** após o número de tentativas com falha seja definido como algum número. Isso é 5 por padrão. 
  
1. No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.
    
2. Insira um PIN incorreto o número de vezes especificado pela política. Você verá um prompt informando limite de tentativa **de PIN atingido** para redefinir o PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Pressione **Redefinir PIN**. Você será solicitado a entrar com as credenciais de Microsoft 365 Business Premium do usuário e, em seguida, será necessário definir um novo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Abra um email que contenha um anexo e toque no ícone de seta para baixo ao lado das informações do anexo.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    Você verá Não **é possível salvar no dispositivo** na parte inferior da tela. 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > A opção para salvar no OneDrive for Business não está habilitada para o Android neste momento, portanto, só é possível ver que salvar localmente está bloqueado. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado

No  painel Editar política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda Gerenciar como  os usuários acessam arquivos **Office** em dispositivos móveis e certifique-se de exigir que os usuários entre novamente depois que os aplicativos Office estão ociosos por algum número de minutos. Por padrão, são 30 minutos. 
  
1. No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo Android ocioso sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.
    
3. Acesse Outlook no dispositivo Android novamente.
    
4. Você será solicitado a inserir seu PIN antes de poder acessar Outlook novamente.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar Proteger arquivos de trabalho com criptografia

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.
  
1. No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Abra um email que contém alguns anexos de arquivo de imagem.
    
3. Toque no ícone de seta para baixo ao lado das informações do anexo para salvá-lo.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Você poderá ser solicitado a permitir que o Outlook acesse arquivos, mídia e fotos em seu dispositivo. Toque em **Permitir**.
    
5. Na parte inferior da tela, escolha **Salvar no Dispositivo** e, em seguida, abra o aplicativo **Galeria**. 
    
6. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) na lista. Ela poderá aparecer na lista Imagens como um quadrado cinza com um ponto de exclamação branco dentro de um círculo branco no centro do quadrado cinza.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário

Depois de [definir configurações de aplicativo para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas. 
  
Primeiro, certifique-se de que a política se aplique ao aplicativo no qual você irá validá-la.
  
1. No centro de Microsoft 365 Business Premium [de administração,](https://admin.microsoft.com)vá para **Política Editar** \> **política**.
    
2. Escolha **Política de aplicativo para iOS** para as configurações criadas na instalação ou outra política que você criou e verifique se ela é imposta para Outlook por exemplo. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Validar Exigir um PIN para acessar aplicativos do Office

No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.
  
![Certifique-se de que a opção Exigir um PIN ou impressão digital para acessar Office aplicativos está definida como On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.
    
2. Você também será solicitado a inserir um PIN ou usar uma impressão digital.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Validar Redefinir PIN após algumas tentativas fracassadas

No painel **Editar** política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda **Gerenciar como** os usuários acessam arquivos Office em dispositivos móveis e certifique-se de que **Redefinir PIN** após o número de tentativas com falha seja definido como algum número. Isso é 5 por padrão. 
  
1. No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.
    
2. Insira um PIN incorreto o número de vezes especificado pela política. Você verá um prompt informando limite de tentativa **de PIN atingido** para redefinir o PIN. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Pressione **OK**. Você será solicitado a entrar com as credenciais de Microsoft 365 Business Premium do usuário e, em seguida, será necessário definir um novo PIN.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Abra um email que contenha um anexo, abra o anexo e escolha **Salvar** na parte inferior da tela. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. Você só verá uma opção para o OneDrive for Business. Se não, toque **em Adicionar Conta** e selecione **OneDrive for Business** na tela **Adicionar Armazenamento** Conta. Forneça ao usuário final Microsoft 365 Business Premium entrar quando solicitado. 
    
    Toque em **Salvar** e selecione **OneDrive for Business**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado

No  painel Editar política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda Gerenciar como  os usuários acessam arquivos **Office** em dispositivos móveis e certifique-se de exigir que os usuários entre novamente depois que os aplicativos Office estão ociosos por algum número de minutos. Por padrão, são 30 minutos. 
  
1. No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo iOS sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.
    
3. Acesse Outlook no dispositivo iOS novamente.
    
4. Você será solicitado a inserir seu PIN antes de poder acessar Outlook novamente.
    
### <a name="validate-protect-work-files-with-encryption"></a>Validar Proteger arquivos de trabalho com criptografia

No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.
  
1. No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.
    
2. Abra um email que contém alguns anexos de arquivo de imagem.
    
3. Toque no anexo e, em seguida, toque na opção **Salvar** abaixo dele. 
    
4. Abra o aplicativo **Fotos** na tela inicial. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) salva, mas criptografada. 
    
---

