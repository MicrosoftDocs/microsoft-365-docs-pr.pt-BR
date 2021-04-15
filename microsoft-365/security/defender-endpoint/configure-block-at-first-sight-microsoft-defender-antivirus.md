---
title: Habilitar o bloqueio à primeira vista para detectar malware em segundos
description: A turn on the block at first sight feature to detect and block malware within seconds.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765750"
---
# <a name="turn-on-block-at-first-sight"></a>Ativar o bloqueio à primeira vista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Bloquear à primeira vista fornece uma maneira de detectar e bloquear um novo malware em segundos. Essa proteção é habilitada por padrão quando determinadas configurações de pré-requisito estão habilitadas. Essas configurações incluem proteção entregue na nuvem, um tempo máximo de envio de amostra especificado (como 50 segundos) e um nível alto de bloqueio de arquivos. Na maioria das organizações corporativas, essas configurações são habilitadas por padrão com implantações do Microsoft Defender Antivírus. 

Você pode [especificar por quanto tempo um arquivo deve ser](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) impedido de ser executado enquanto o serviço de proteção baseado em nuvem analisa o arquivo. E, você pode [personalizar a mensagem exibida nos desktops dos](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuários quando um arquivo é bloqueado. Você pode alterar o nome da empresa, as informações de contato e a URL da mensagem.

>[!TIP]
>Visite o site de demonstração do Microsoft Defender para Ponto de Extremidade [no](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com para confirmar se os recursos estão funcionando e ver como eles funcionam.

## <a name="how-it-works"></a>Como funciona

Quando o Microsoft Defender Antivírus encontra um arquivo suspeito, mas não detectado, ele consulta nosso back-end de proteção de nuvem. O back-back da nuvem aplica heurística, aprendizado de máquina e análise automatizada do arquivo para determinar se os arquivos são mal-intencionados ou não uma ameaça.

O Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, inteligente e em tempo real. Para saber mais, confira este blog: Conheça as tecnologias avançadas no núcleo do [Microsoft Defender para Endpoint de proteção de próxima geração.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Lista de mecanismos do Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

No Windows 10, versão 1803 ou posterior, o bloqueio à primeira vista pode bloquear arquivos executáveis não portáteis (como JS, VBS ou macros), bem como arquivos executáveis.

O bloqueio à primeira vista usa apenas o back-end de proteção de nuvem para arquivos executáveis e arquivos executáveis não portáteis baixados da Internet ou que se originam da zona da Internet. Um valor de hash do arquivo .exe é verificado por meio do back-end da nuvem para determinar se o arquivo é um arquivo não detectado anteriormente.

Se o back-back da nuvem não puder fazer uma determinação, o Microsoft Defender Antivírus bloqueia o arquivo e carrega uma cópia na nuvem. A nuvem executa análises adicionais para chegar a uma determinação antes de permitir que o arquivo seja executado ou o bloqueia em todos os futuros encontros, dependendo de determinar se o arquivo é mal-intencionado ou seguro.

Em muitos casos, esse processo pode reduzir o tempo de resposta para o novo malware de horas para segundos.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Ativar bloqueio à primeira vista com o Microsoft Intune

> [!TIP]
> O Microsoft Intune agora faz parte do Microsoft Endpoint Manager.

1. No Centro de administração do Microsoft Endpoint Manager ( ), navegue até [https://endpoint.microsoft.com](https://endpoint.microsoft.com) **Perfis**  >  **de Configuração de Dispositivos.**

2. Selecione ou crie um perfil usando o tipo **de perfil restrições** de dispositivo.

3. Nas **configurações do** perfil restrições de dispositivo, de definir ou confirmar as seguintes configurações em **Microsoft Defender Antivírus**:

   - **Proteção entregue na nuvem**: Habilitada
   - **Nível de bloqueio de arquivos**: alto
   - **Extensão de tempo para verificação de arquivos pela nuvem**: 50
   - **Solicitar aos usuários antes do envio de exemplo**: Enviar todos os dados sem solicitar

   ![Config do Intune](images/defender/intune-block-at-first-sight.png)

4. Salve suas configurações.

> [!TIP]
> - Definir o nível de bloqueio de arquivo **como Alto** aplica um nível forte de detecção. No caso improvável de que o bloqueio de arquivos cause uma detecção de falsos positivos de arquivos legítimos, você pode [restaurar arquivos em quarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Para obter mais informações sobre como configurar restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).
> - Para ver uma lista de restrições de dispositivo do Microsoft Defender Antivírus no Intune, consulte Restrição de dispositivo para configurações do [Windows 10 (e mais novas) no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Ativar o bloqueio à primeira vista com o Microsoft Endpoint Manager

> [!TIP]
> Se você estiver procurando o Microsoft Endpoint Configuration Manager, ele agora faz parte do Microsoft Endpoint Manager.

1. No Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), acesse **Endpoint security**  >  **Antivírus**.

2. Selecione uma política existente ou crie uma nova política usando o tipo de **perfil do Microsoft Defender Antivírus.**

3. De definir ou confirmar as seguintes configurações:

   - **Ativar a proteção entregue na nuvem**: Sim
   - **Nível de proteção entregue na nuvem**: Alto
   - **Tempo de tempo estendido da** nuvem do Defender em segundos : 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear as configurações à primeira vista no Endpoint Manager":::

4. Aplique o perfil do Microsoft Defender Antivírus a um grupo, como **Todos** os usuários , **Todos** os dispositivos ou **Todos os usuários e dispositivos**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Ativar o bloqueio à primeira vista com a Política de Grupo

> [!NOTE]
> Recomendamos usar o Intune ou o Microsoft Endpoint Manager para ativar o bloqueio à primeira vista. 

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**. 

2. Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração** do computador  >  **Modelos administrativos**  >  **Componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**. 

3. Na seção MAPAs, clique duas vezes em Configurar o recurso **"Bloquear** à Primeira Vista", des configurá-lo como Habilitado **e** selecione **OK**.

    > [!IMPORTANT]
    > A **configuração como Sempre prompt (0)** diminuirá o estado de proteção do dispositivo. Definir como **Nunca enviar (2)** significa que o bloqueio à primeira vista não funcionará.

4. Na seção MAPAs, clique duas vezes em **Enviar amostras** de arquivo quando outra análise for necessária e desdeixá-la **como Habilitado**. Em **Enviar amostras de arquivo quando uma análise** posterior for necessária, selecione Enviar todos os **exemplos** e clique em **OK**.

5. Se você tiver alterado qualquer configuração, reimplante o Objeto de Política de Grupo em toda a rede para garantir que todos os pontos de extremidade sejam cobertos.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>Confirmar que o bloqueio à primeira vista está habilitado em clientes individuais

Você pode confirmar que o bloqueio à primeira vista está habilitado em clientes individuais usando configurações de segurança do Windows.

O bloqueio à primeira vista é  habilitado automaticamente, desde que a proteção entregue na nuvem e o envio **automático** de exemplo sejam ativados.

1. Abra o aplicativo segurança do Windows.

2. Selecione **Proteção contra &** contra vírus e, em Configurações de proteção contra & vírus, selecione Gerenciar **Configurações**. 

   ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme se **a proteção entregue na nuvem** e o envio **automático** de exemplo estão ambos a ligado.

> [!NOTE]
> - Se as configurações de pré-requisitos são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais. 
> - As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows.

## <a name="validate-block-at-first-sight-is-working"></a>Validar bloco à primeira vista está funcionando

Para validar se o recurso está funcionando, siga as orientações em Validar conexões [entre sua rede e a nuvem](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).

## <a name="turn-off-block-at-first-sight"></a>Desativar o bloco à primeira vista

> [!CAUTION]
> Desligar o bloco à primeira vista diminuirá o estado de proteção de seus dispositivos e de sua rede.

Você pode optar por desabilitar o bloqueio à primeira vista se quiser manter as configurações de pré-requisito sem realmente usar a proteção de bloqueio à primeira vista. Você pode desativar temporariamente o bloqueio à primeira vista se estiver enfrentando problemas de latência ou quiser testar o impacto do recurso em sua rede. No entanto, não recomendamos desabilitar o bloco à primeira vista permanentemente.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Desativar o bloco à primeira vista com o Microsoft Endpoint Manager

1. Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e entre.

2. Vá para **o Antivírus de segurança** do ponto de extremidade e selecione sua política do Microsoft Defender  >  Antivírus.

3. Em **Gerenciar**, escolha **Propriedades**.

4. Ao lado **das configurações,** escolha **Editar**.

5. Altere uma ou mais das seguintes configurações:

   - Definir **Ativar a proteção entregue na nuvem** como **Não** ou **Não configurado.**
   - Definir **o nível de proteção entregue na nuvem** como Não **configurado**.
   - Limpe a **caixa Tempo Decoro Estendido da** Nuvem do Defender em Segundos.

6. Revise e salve suas configurações.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Desativar o bloco à primeira vista com a Política de Grupo

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore por meio **de componentes do Windows** Microsoft Defender  >    >  **Antivírus MAPS**.

4. Clique duas vezes **em Configurar o recurso "Bloquear à Primeira Vista"** e de definir a opção como **Desabilitada**.

    > [!NOTE]
    > Desabilitar o bloco à primeira vista não desabilita ou altera as políticas de grupo de pré-requisitos.

## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)