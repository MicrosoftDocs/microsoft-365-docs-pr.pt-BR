---
title: Integração usando o Microsoft Endpoint Manager
description: Saiba como integrar o Microsoft Defender para Ponto de Extremidade usando o Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e744262cfd63383e69abf02be9fbf91d2d229db2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935252"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Integração usando o Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este artigo faz parte do guia implantação e age como um exemplo de método de integração. 

No tópico [Planejamento,](deployment-strategy.md) havia vários métodos fornecidos para os dispositivos de integração ao serviço. Este tópico aborda a arquitetura nativa da nuvem. 

![Imagem da arquitetura nativa da nuvem ](images/cloud-native-architecture.png)
 *Diagrama de arquiteturas de ambiente*

Embora o Defender para Ponto de Extremidade suporte à integração de vários pontos de extremidade e ferramentas, este artigo não os abrange. Para obter informações sobre a integração geral usando outras ferramentas e métodos de implantação com suporte, consulte [Onboarding overview](onboarding.md).


[O Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) é uma plataforma de solução que unifica vários serviços. Ele inclui o [Microsoft Intune para](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) gerenciamento de dispositivos baseado em nuvem.


Este tópico orienta os usuários em:
- Etapa 1: Integrando dispositivos ao serviço criando um grupo no Microsoft Endpoint Manager (MEM) para atribuir configurações em
- Etapa 2: Configurando o Defender para recursos de ponto de extremidade usando o Microsoft Endpoint Manager

Essas diretrizes de integração orientarão você pelas seguintes etapas básicas que você precisa seguir ao usar o Microsoft Endpoint Manager:

-   [Identificar dispositivos de destino ou usuários](#identify-target-devices-or-users)

    -   Criando um grupo do Azure Active Directory (Usuário ou Dispositivo)

-   [Criando um Perfil de Configuração](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   No Microsoft Endpoint Manager, vamos orientá-lo na criação de uma política separada para cada recurso.





## <a name="resources"></a>Recursos


Aqui estão os links necessários para o restante do processo:

-   [Portal de MEM](https://aka.ms/memac)

-   [Central de Segurança](https://securitycenter.windows.com/)

-   [Linhas de base de segurança do Intune](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Para obter mais informações sobre o Microsoft Endpoint Manager, confira estes recursos:
- [Página do Microsoft Endpoint Manager](https://docs.microsoft.com/mem/)
- [Postagem de blog sobre convergência do Intune e ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Vídeo de introdução no MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Etapa 1: Integrando dispositivos criando um grupo no MEM para atribuir configurações em
### <a name="identify-target-devices-or-users"></a>Identificar dispositivos de destino ou usuários
Nesta seção, criaremos um grupo de teste para atribuir suas configurações.

>[!NOTE]
>O Intune usa grupos do Azure Active Directory (Azure AD) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às suas necessidades organizacionais.<br>
Para obter mais informações, [consulte Adicionar grupos para organizar usuários e dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### <a name="create-a-group"></a>Criar um grupo

1.  Abra o portal MEM.

2.  Abra **Grupos > Novo Grupo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Insira detalhes e crie um novo grupo.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Adicione seu usuário de teste ou dispositivo.

5.  No painel **Grupos > Todos os** grupos, abra seu novo grupo.

6.  Selecione  **Membros > Adicionar membros**.

7.  Encontre seu usuário de teste ou dispositivo e selecione-o.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  Seu grupo de teste agora tem um membro para testar.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Etapa 2: Criar políticas de configuração para configurar o Microsoft Defender para recursos do Ponto de Extremidade
Na seção a seguir, você criará várias políticas de configuração.

Em primeiro lugar, uma política de configuração para selecionar quais grupos de usuários ou dispositivos serão integrados ao Defender para Ponto de Extremidade:

- [Detecção de ponto de extremidade e resposta](#endpoint-detection-and-response) 

Em seguida, você continuará criando vários tipos diferentes de políticas de segurança do ponto de extremidade:

- [Proteção de próxima geração](#next-generation-protection)
- [Redução de superfície de ataque](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Detecção de ponto de extremidade e resposta

1.  Abra o portal MEM.

2.  Navegue **até Endpoint security > Endpoint detection and response**. Clique em **Criar Perfil**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  Em **Plataforma, selecione Windows 10 e Posterior, Perfil - Detecção** e resposta do ponto de extremidade > Criar .

4.  Insira um nome e uma descrição e selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Selecione configurações conforme necessário e selecione  **Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > Nesse caso, isso foi preenchido automaticamente, pois o Defender para Ponto de Extremidade já foi integrado ao Intune. Para obter mais informações sobre a integração, consulte [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).
    > 
    > A imagem a seguir é um exemplo do que você verá quando o Microsoft Defender for Endpoint não estiver integrado ao Intune:
    >
    > ![Imagem do Microsoft Endpoint Manager portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  Adicione marcas de escopo, se necessário, em seguida, selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Adicione grupo de teste clicando em **Selecionar grupos para incluir** e escolher seu grupo e selecione  **Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Revise e aceite e selecione  **Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  Você pode exibir sua política concluída.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Proteção de próxima geração

1.  Abra o portal MEM.

2.  Navegue **até Endpoint security > Antivírus > Criar Política**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Selecione **Plataforma - Windows 10 e Posterior - Windows e Perfil – Microsoft Defender Antivírus > Criar**.

4.  Insira o nome e a descrição e selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  Na página **Configuração configurações:** de definir as configurações necessárias para o Microsoft Defender Antivírus (Proteção na Nuvem, Exclusões, Real-Time Proteção e Correção).

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  Adicione marcas de escopo, se necessário, em seguida, selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Selecione grupos para incluir, atribua ao grupo de teste e selecione  **Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Revise e crie e selecione  **Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  Você verá a política de configuração criada.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Redução de Superfície de Ataque – Regras de redução de superfície de ataque

1.  Abra o portal MEM.

2.  Navegue **até Endpoint security > Redução de superfície de ataque**.

3.  Selecione  **Criar Política**.

4.  Selecione **Plataforma - Windows 10 e Posterior – Perfil - Regras de redução de superfície de ataque > Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Insira um nome e uma descrição e selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  Na página **Configuração de configuração:** de definir as configurações necessárias para regras de redução de superfície de ataque e selecione  **Próximo**.

    > [!NOTE]
    > Configuraremos todas as regras de redução de superfície de ataque para Auditoria.
    > 
    > Para obter mais informações, consulte [Regras de redução de superfície de ataque](attack-surface-reduction.md).

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Adicione Marcas de Escopo conforme necessário e selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selecione grupos para incluir e atribuir ao grupo de teste e selecione  **Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Revise os detalhes e selecione  **Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Exibir a política.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Redução de superfície de ataque – Proteção da Web

1.  Abra o portal MEM.

2.  Navegue **até Endpoint security > Redução de superfície de ataque**.

3.  Selecione  **Criar Política**.

4.  Selecione **Windows 10 e Posterior – Proteção da Web > Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Insira um nome e uma descrição e selecione  **Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  Na página **Configuração configurações:** de definir as configurações necessárias para a Proteção da Web e selecione  **Próximo**.

    > [!NOTE]
    > Estamos configurando a Proteção da Web para Bloquear.
    > 
    > Para obter mais informações, consulte [Web Protection](web-protection-overview.md).

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Adicione **marcas de escopo conforme necessário > Next**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Selecione **Atribuir ao grupo de teste > Próximo**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Selecione **Revisar e Criar > Criar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Exibir a política.

    > [!div class="mx-imgBorder"]
    > ![Imagem do portal do Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Validar configurações


### <a name="confirm-policies-have-been-applied"></a>Confirmar políticas foram aplicadas


Depois que a política de configuração tiver sido atribuída, levará algum tempo para ser aplicada.

Para obter informações sobre o tempo, consulte [Informações de configuração do Intune.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Para confirmar se a política de configuração foi aplicada ao dispositivo de teste, siga o processo a seguir para cada política de configuração.

1.  Abra o portal do MEM e navegue até a política relevante, conforme mostrado nas etapas acima. O exemplo a seguir mostra as configurações de proteção de próxima geração.

    > [!div class="mx-imgBorder"]
    > [![Imagem do portal do Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Selecione a **Política de Configuração** para exibir o status da política.

    > [!div class="mx-imgBorder"]
    > [![Imagem do portal do Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Selecione  **Status do Dispositivo** para ver o status.

    > [!div class="mx-imgBorder"]
    > [![Imagem do portal do Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Selecione  **Status do Usuário** para ver o status.

    > [!div class="mx-imgBorder"]
    > [![Imagem do portal do Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Selecione  **Status por configuração** para ver o status.

    >[!TIP]
    >Essa exibição é muito útil para identificar as configurações que conflitam com outra política.

    > [!div class="mx-imgBorder"]
    > [![Imagem do portal do Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Detecção de ponto de extremidade e resposta


1.  Antes de aplicar a configuração, o serviço Defender for Endpoint Protection não deve ser iniciado.

    > [!div class="mx-imgBorder"]
    > [![Painel Imagem dos Serviços1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  Após a aplicação da configuração, o Defender for Endpoint Protection Service deve ser iniciado.

    > [!div class="mx-imgBorder"]
    > [![Painel Imagem dos Serviços2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  Depois que os serviços são executados no dispositivo, o dispositivo aparece no Centro de Segurança do Microsoft Defender.

    > [!div class="mx-imgBorder"]
    > [![Imagem do Centro de Segurança do ](images/df0c64001b9219cfbd10f8f81a273190.png) Microsoft Defender](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Proteção de próxima geração

1.  Antes de aplicar a política em um dispositivo de teste, você deve ser capaz de gerenciar manualmente as configurações, conforme mostrado abaixo.

    > [!div class="mx-imgBorder"]
    > ![Imagem da configuração page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  Depois que a política tiver sido aplicada, você não poderá gerenciar manualmente as configurações.

    > [!NOTE]
    > Na imagem a **seguir, a proteção** a ser exibida na nuvem e Ativar a proteção em **tempo real** estão sendo mostradas como gerenciadas.

    > [!div class="mx-imgBorder"]
    > ![Imagem da configuração page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Redução de Superfície de Ataque – Regras de redução de superfície de ataque


1.  Antes de aplicar a política em um dispositivo de teste, penite uma Janela do PowerShell e digite `Get-MpPreference` .

2.  Isso deve responder com as seguintes linhas sem conteúdo:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Imagem da linha de comando1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  Depois de aplicar a política em um dispositivo de teste, abra um Windows do PowerShell e digite `Get-MpPreference` .

4.  Isso deve responder com as seguintes linhas com conteúdo, conforme mostrado abaixo:

    ![Imagem da linha de comando2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Redução de superfície de ataque – Proteção da Web

1.  No dispositivo de teste, abra um Windows do PowerShell e digite `(Get-MpPreference).EnableNetworkProtection` .

2.  Isso deve responder com um 0 conforme mostrado abaixo.

    ![Imagem da linha de comando3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  Depois de aplicar a política, abra um Windows do PowerShell e digite `(Get-MpPreference).EnableNetworkProtection` .

4.  Isso deve responder com um 1, conforme mostrado abaixo.

    ![Imagem da linha de comando4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
