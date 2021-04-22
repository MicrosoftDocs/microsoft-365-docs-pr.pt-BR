---
title: Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no Android com o Microsoft Intune
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, installation, deploy, uninstallation,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f14d79d98bfffda675cd71b96068b179f30f059e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934628"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Saiba como implantar o Defender para Ponto de Extremidade no Android em dispositivos inscritos no Portal da Empresa do Intune. Para obter mais informações sobre o registro do dispositivo Intune, consulte  [Registrar seu dispositivo](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).

> [!NOTE]
> **O Defender para Ponto de Extremidade no Android agora está disponível no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br>
> Você pode se conectar ao Google Play do Intune para implantar o aplicativo Defender para Ponto de Extremidade nos modos de entrolamento do Administrador de Dispositivos e Android Enterprise.
As atualizações para o aplicativo são automáticas por meio do Google Play.

## <a name="deploy-on-device-administrator-enrolled-devices"></a>Implantar em dispositivos inscritos pelo Administrador de Dispositivos

**Implantar o Defender para Ponto de Extremidade no Android no Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos**

Saiba como implantar o Defender para Ponto de Extremidade no Android no Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos. 

### <a name="add-as-android-store-app"></a>Adicionar como aplicativo da Loja do Android

1. No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) acesse  \> **Aplicativos Android Apps** Adicionar aplicativo da Loja \> **do \> Android** e **escolha Selecionar**.

   ![Imagem do Microsoft Endpoint Manager Admin Center add android store application](images/mda-addandroidstoreapp.png)

2. Na página **Adicionar aplicativo** e na seção Informações *do* Aplicativo, insira: 

   - **Nome** 
   - **Descrição**
   - **Publisher** como Microsoft.
   - **URL da Loja de Aplicativos** https://play.google.com/store/apps/details?id=com.microsoft.scmx como (URL do Defender for Endpoint App Google Play Store) 

   Outros campos são opcionais. Selecione **Avançar**.

   ![Imagem do Centro de Administração do Microsoft Endpoint Manager adicionar informações de aplicativo](images/mda-addappinfo.png)

3. Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo.** Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para Ponto de Extremidade no aplicativo Android. Escolha **Selecionar** e, em **seguida, Próximo**.

    >[!NOTE]
    >O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.

    > [!div class="mx-imgBorder"]

    > ![Imagem dos grupos de usuários selecionados do Centro de Administração do Microsoft Endpoint Manager](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.

    Em alguns instantes, o aplicativo Defender para Ponto de Extremidade seria criado com êxito, e uma notificação apareceria no canto superior direito da página.

    ![Imagem da notificação do Centro de Administração do Microsoft Endpoint Manager do aplicativo de ponto de extremidade do defender](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.

    > [!div class="mx-imgBorder"]
    > ![Imagem da instalação do dispositivo do Centro de Administração do Microsoft Endpoint Manager](images/513cf5d59eaaef5d2b5bc122715b5844.png)

### <a name="complete-onboarding-and-check-status"></a>Concluir a integração e verificar o status

1. Depois que o Defender for Endpoint no Android tiver sido instalado no dispositivo, você verá o ícone do aplicativo.

    ![Ícone em dispositivo móvel](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. Toque no ícone de aplicativo do Microsoft Defender para Ponto de Extremidade e siga as instruções na tela para concluir a integração do aplicativo. Os detalhes incluem a aceitação do usuário final das permissões do Android exigidas pelo Defender para Ponto de Extremidade no Android.

3. Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos no Centro de Segurança do Microsoft Defender.

    ![Imagem do dispositivo no portal do Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Implantar em dispositivos inscritos no Android Enterprise

O Defender para Ponto de Extremidade no Android dá suporte a dispositivos inscritos no Android Enterprise.

Para obter mais informações sobre as opções de registro com suporte do Intune, consulte [Opções de Inscrição](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).

**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e registro de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados para implantação.**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Adicionar o Microsoft Defender para Ponto de Extremidade no Android como um aplicativo gerenciado do Google Play

Siga as etapas a seguir para adicionar o aplicativo Microsoft Defender para Ponto de Extremidade ao Google Play gerenciado.

1. No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) acesse  \> **Aplicativos Android Apps** Adicionar e \>  selecione Aplicativo Gerenciado do **Google Play**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do Centro de administração do Microsoft Endpoint Manager gerenciado google play](images/579ff59f31f599414cedf63051628b2e.png)

2. Na página gerenciada do Google Play que é carregada posteriormente, vá até a caixa de pesquisa e procure o **Microsoft Defender.** Sua pesquisa deve exibir o aplicativo Microsoft Defender para Ponto de Extremidade em seu Google Play Gerenciado. Clique no aplicativo Microsoft Defender para Ponto de Extremidade no resultado da pesquisa aplicativos.

    ![Imagem do Centro de administração do Microsoft Endpoint Manager Pesquisa de aplicativos](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. Na página Descrição do aplicativo que vem a seguir, você deve ser capaz de ver detalhes do aplicativo no Defender para Ponto de Extremidade. Revise as informações na página e selecione **Aprovar**.

    > [!div class="mx-imgBorder"]
    > ![Uma captura de tela de um Google Play Gerenciado](images/07e6d4119f265037e3b80a20a73b856f.png)

4. Você será apresentado com as permissões que o Defender for Endpoint obtém para que ele funcione. Revise-os e selecione **Aprovar**.

    ![Uma captura de tela da aprovação do aplicativo de visualização do Defender para Ponto de Extremidade](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. Você será apresentado com a página Configurações de Aprovação. A página confirma sua preferência para lidar com novas permissões de aplicativo que o Defender para Ponto de Extremidade pode solicitar no Android. Revise as opções e selecione sua opção preferida. Selecione **Concluído**.

    Por padrão, o Google Play gerenciado seleciona *Manter aprovado quando o aplicativo solicita novas permissões*

    > [!div class="mx-imgBorder"]
    > ![Imagem da guia notificações](images/ffecfdda1c4df14148f1526c22cc0236.png)

6. Depois que a seleção de manipulação de permissões for feita, selecione **Sincronizar** para sincronizar o Microsoft Defender para o Ponto de Extremidade à sua lista de aplicativos.

    > [!div class="mx-imgBorder"]
    > ![Imagem da página de sincronização](images/34e6b9a0dae125d085c84593140180ed.png)

7. A sincronização será concluída em alguns minutos.

    ![Imagem do aplicativo Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. Selecione o **botão Atualizar** na tela aplicativos Android e o Microsoft Defender para Ponto de Extremidade deve estar visível na lista de aplicativos.

    > [!div class="mx-imgBorder"]
    > ![Imagem da lista de aplicativos Android](images/fa4ac18a6333335db3775630b8e6b353.png)

9. O Defender for Endpoint dá suporte a políticas de configuração de aplicativo para dispositivos gerenciados por meio do Intune. Esse recurso pode ser aproveitado para autograntar as permissões aplicáveis do Android, para que o usuário final não precise aceitar essas permissões.

    1. Na página **Aplicativos,** vá para Política > Políticas de configuração de **aplicativos > Adicionar > dispositivos gerenciados.**

       ![Imagem do Centro de administração do Microsoft Endpoint Manager android managed devices](images/android-mem.png)

    1. Na página **Criar política de configuração do** aplicativo, insira os seguintes detalhes:
    
        - Nome: Microsoft Defender para Ponto de Extremidade.
        - Escolha **Android Enterprise** como plataforma.
        - Escolha **Perfil de Trabalho apenas** como Tipo de Perfil.
        - Clique **em Selecionar Aplicativo,** escolha **Microsoft Defender ATP,** selecione **OK** e, em **seguida, Próximo**.
    
        > [!div class="mx-imgBorder"]
        > ![Imagem da página criar política de configuração de aplicativo](images/android-create-app.png)

    1. Na página **Configurações,** vá para a seção Permissões clique em Adicionar para exibir a lista de permissões com suporte. Na seção Adicionar Permissões, selecione as seguintes permissões:

       - Armazenamento externo (leitura)
       - Armazenamento externo (gravação)

       Em seguida, selecione **OK**.

       > [!div class="mx-imgBorder"]
      > ![Imagem da política de configuração do aplicativo de criação do android](images/android-create-app-config.png)

    1. Agora você deve ver as permissões listadas e agora você pode autograntar ambos escolhendo a autogrant no **drop-down** estado de permissão e, em seguida, selecione **Next**.

       > [!div class="mx-imgBorder"]
       > ![Imagem da concessão automática do android criar política de configuração de aplicativo](images/android-auto-grant.png)

    1. Na página **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo seria atribuída. Clique **em Selecionar grupos para incluir** e selecionar o grupo aplicável e, em seguida, selecione **Next**.  O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android. 

       > [!div class="mx-imgBorder"]
       > ![Imagem da política de configuração do aplicativo criar](images/android-select-group.png)
    

     1. Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**. <br>
    
        A política de configuração do aplicativo para o Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.

        > [!div class="mx-imgBorder"]
        > ![Imagem da revisão do android criar política de configuração de aplicativo](images/android-review-create.png)


10. Selecione **o aplicativo Microsoft Defender ATP** na lista \> **Propriedades** \> **Atribuições** \> **Editar**.

    ![Imagem da lista de aplicativos](images/mda-properties.png)


11. Atribua o aplicativo como *um aplicativo obrigatório* a um grupo de usuários. Ele é instalado automaticamente no perfil *de trabalho* durante a próxima sincronização do dispositivo por meio do aplicativo Portal da Empresa. Essa atribuição pode ser feita navegando até a seção Obrigatório Adicionar  \> **grupo,** selecionando o grupo de usuários e clique em **Selecionar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem da página editar aplicativo](images/ea06643280075f16265a596fb9a96042.png)


12. Na página **Editar Aplicativo,** revise todas as informações inseridas acima. Em seguida, **selecione Revisar + Salvar** e **salvar** novamente para iniciar a atribuição.

### <a name="auto-setup-of-always-on-vpn"></a>Configuração automática da VPN always-on 
O Defender for Endpoint oferece suporte a políticas de configuração de dispositivo para dispositivos gerenciados por meio do Intune. Esse recurso pode ser aproveitado para a configuração automática da **VPN Always-on** em dispositivos inscritos no Android Enterprise, para que o usuário final não precise configurar o serviço VPN durante a integração.
1.  Em **Dispositivos**, selecione **Perfis** de Configuração Criar Plataforma de Perfil Android Enterprise Selecionar Restrições de dispositivo em uma das seguintes  >    >    >   opções, com  base no tipo de registro do dispositivo 
- **Perfil de trabalho totalmente gerenciado, dedicado e Corporate-Owned trabalho**
- **Perfil de Trabalho de propriedade pessoal**

Selecione **Criar**.
 
   > ![Imagem do perfil de configuração de dispositivos Criar](images/1autosetupofvpn.png)
    
2. **Configurações** Forneça um **Nome e** uma **Descrição** para identificar exclusivamente o perfil de configuração. 

   > ![Imagem do perfil de configuração de dispositivos Nome e Descrição](images/2autosetupofvpn.png)
   
 3. Selecione **Conectividade e** configure VPN:
- **Habilita a Instalação de VPN always-on** de um cliente VPN no perfil de trabalho para se conectar e reconectar automaticamente à VPN sempre que possível. Somente um cliente VPN pode ser configurado para VPN sempre on em um determinado dispositivo, portanto, certifique-se de não ter mais de uma política VPN sempre on implantada em um único dispositivo. 
- Selecione **Personalizado na** lista suspenso do cliente VPN A VPN personalizada nesse caso é o Defender for Endpoint VPN, que é usado para fornecer o recurso de Proteção da Web. 
    > [!NOTE]
    > O aplicativo do Microsoft Defender para Ponto de Extremidade deve ser instalado no dispositivo do usuário, para funcionar da configuração automática dessa VPN.

- Insira **a ID do** pacote do aplicativo Microsoft Defender para Ponto de Extremidade na Google Play Store. Para a URL do aplicativo https://play.google.com/store/apps/details?id=com.microsoft.scmx Defender, a ID do pacote **é com.microsoft.scmx**  
- **Modo de bloqueio** Não configurado (Padrão) 

     ![Imagem do perfil de configuração de dispositivos habilita a VPN always-on](images/3autosetupofvpn.png)
   
4. **Atribuição** Na página  **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo   seria atribuída. Clique **em Selecionar grupos** para incluir e selecionar o grupo aplicável e clique em **Próximo**. O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android. 

     ![Imagem do perfil de configuração de dispositivos Atribuição](images/4autosetupofvpn.png)

5. Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**. O perfil de configuração do dispositivo agora é atribuído ao grupo de usuários selecionado.    

    ![Imagem do perfil de configuração de dispositivos Revisão e Criação](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a>Concluir a integração e verificar o status

1. Confirme o status de instalação do Microsoft Defender para Ponto de Extremidade no Android clicando no **Status de Instalação do Dispositivo.** Verifique se o dispositivo é exibido aqui.

    > [!div class="mx-imgBorder"]
    > ![Imagem do status de instalação do dispositivo](images/900c0197aa59f9b7abd762ab2b32e80c.png)


2. No dispositivo, você pode validar o status de integração indo para o perfil **de trabalho**. Confirme se o Defender para Ponto de Extremidade está disponível e se você está inscrito nos dispositivos de **propriedade pessoal com o perfil de trabalho**.  Se você estiver inscrito em um dispositivo de usuário totalmente gerenciado de propriedade **corporativa,** você terá um único perfil no dispositivo onde poderá confirmar se o Defender para Ponto de Extremidade está disponível.

    ![Imagem do aplicativo no dispositivo móvel](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. Quando o aplicativo estiver instalado, abra o aplicativo e aceite as permissões e, em seguida, sua integração deve ser bem-sucedida.

    ![Imagem do dispositivo móvel com o aplicativo Microsoft Defender para Ponto de Extremidade](images/mda-devicesafe.png)

4. Neste estágio, o dispositivo é bem-sucedido no Defender para Ponto de Extremidade no Android. Você pode verificar isso no Centro de Segurança do [Microsoft Defender](https://securitycenter.microsoft.com) navegando até a página **Dispositivos.**

    ![Imagem do portal do Microsoft Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral do Microsoft Defender para Ponto de Extremidade para Android](microsoft-defender-endpoint-android.md)
- [Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android](android-configure.md)
