---
title: Ativar a proteção entregue na nuvem no Microsoft Defender Antivírus
description: Adoe a proteção entregue na nuvem para se beneficiar dos recursos de proteção rápidos e avançados.
keywords: Microsoft Defender Antivírus, antimalware, segurança, nuvem, bloquear à primeira vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9f949a4cb54ca5dd64a2648bb05a5cb9ad50e44d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764958"
---
# <a name="turn-on-cloud-delivered-protection"></a>Ativar a proteção fornecida pela nuvem

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> O serviço de nuvem do Microsoft Defender Antivírus é um mecanismo para fornecer proteção atualizada para sua rede e pontos de extremidade. Embora seja chamado de serviço de nuvem, ele não é simplesmente proteção para arquivos armazenados na nuvem; em vez disso, ele usa recursos distribuídos e aprendizado de máquina para oferecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de Inteligência de Segurança.

O Microsoft Defender Antivírus usa várias tecnologias de detecção e prevenção para oferecer proteção precisa, em tempo real e inteligente. [Conheça as tecnologias avançadas no núcleo do Microsoft Defender para Proteção](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)de próxima geração do Endpoint.
![Lista de mecanismos do Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Você pode ativar ou desativar a proteção entregue na nuvem do Microsoft Defender Antivírus de várias maneiras:

- Microsoft Intune
- Gerenciador de Configuração do Microsoft Endpoint
- Política de Grupo
- Cmdlets do PowerShell.

 Você também pode ativos ou desligados em clientes individuais com o aplicativo segurança do Windows.

Consulte [Usar a proteção entregue na nuvem](cloud-protection-microsoft-defender-antivirus.md) da Microsoft para uma visão geral da proteção entregue na nuvem do Microsoft Defender Antivírus.

Para obter mais informações sobre os requisitos específicos de conectividade de rede para garantir que seus pontos de extremidade possam se conectar ao serviço de proteção entregue na nuvem, consulte [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> No Windows 10, não há diferença  entre as opções **básicas** e avançadas de relatório descritas neste tópico. Essa é uma distinção herdada e escolher qualquer configuração resultará no mesmo nível de proteção entregue na nuvem. Não há diferença no tipo ou na quantidade de informações compartilhadas. Para obter mais informações sobre o que coletamos, consulte a [Declaração de Privacidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Usar o Intune para ativar a proteção entregue na nuvem

1. Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.
2. No painel **Home,** selecione Configuração do dispositivo **> Perfis**.
3. Selecione o **tipo de perfil** de restrições de dispositivo que você deseja configurar. Se você precisar criar um novo tipo de perfil **de** restrições de dispositivo, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).
4. Selecione   >  **Configurações de Propriedades: Editar** Microsoft Defender  >  **Antivírus**.
5. Na opção **Proteção entregue na** nuvem, selecione **Habilitar**.
6. No **Prompt users before sample submission** dropdown, select Send all data **automatically**.

Para obter mais informações sobre perfis de dispositivo do Intune, incluindo como criar e configurar suas configurações, consulte O que são perfis de dispositivo [do Microsoft Intune?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Usar o Microsoft Endpoint Manager para ativar a proteção entregue na nuvem

1. Vá para o Centro de administração do Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.
2. Escolha **Endpoint security**  >  **Antivírus**.
3. Selecione um perfil antivírus. (Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).
4. Selecione **Propriedades**. Em seguida, ao lado **das configurações,** escolha **Editar**.
5. Expanda **a proteção na** nuvem e, em seguida, na lista de níveis de proteção entregues na nuvem, selecione um dos seguintes: 
    1. **Alto**: aplica um nível forte de detecção.
    2. **Alta a** mais : usa **o nível** Alto e aplica medidas de proteção adicionais (pode afetar o desempenho do cliente).
    3. **Tolerância zero**: bloqueia todos os executáveis desconhecidos.
6. Selecione **Revisar + salvar** e, em seguida, escolha **Salvar**.

Para obter mais informações sobre como configurar o Microsoft Endpoint Configuration Manager, consulte [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Usar a Política de Grupo para ativar a proteção entregue na nuvem

1. Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do computador**.

3. Selecione **Modelos administrativos**.

4. Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > MAPS**

5. Clique duas vezes em **Ingressar no Microsoft MAPS.** Certifique-se de que a opção está configurada como **MAPAs Básicos** ou **MAPAS Avançados.** Clique em **OK**.

6. Clique duas vezes em **Enviar amostras de arquivo quando uma análise posterior for necessária**. Verifique se a primeira opção está definida como **Habilitado** e se as outras opções estão definidas como:

    1. **Enviar amostras seguras** (1)
    2. **Enviar todos os exemplos** (3)

        >[!NOTE]
        > A **opção Enviar amostras seguras** (1) significa que a maioria das amostras será enviada automaticamente. Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.

        > [!WARNING]
        > Definir a opção como **Always Prompt** (0) diminuirá o estado de proteção do dispositivo. Defini-lo **como Nunca enviar** (2) significa que o recurso [Bloquear](configure-block-at-first-sight-microsoft-defender-antivirus.md) à Primeira Vista do Microsoft Defender para Ponto de Extremidade não funcionará.

7. Clique em **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Usar cmdlets do PowerShell para ativar a proteção entregue na nuvem

Os cmdlets a seguir podem ativar a proteção entregue na nuvem:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)do Microsoft Defender Antivírus e do Defender. [CSP de](/windows/client-management/mdm/policy-csp-defender) política - O Defender também tem mais informações especificamente [sobre -SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Você também pode definir **-SubmitSamplesConsent** como (a configuração `SendSafeSamples` padrão) `NeverSend` ou `AlwaysPrompt` . A `SendSafeSamples` configuração significa que a maioria das amostras será enviada automaticamente. Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.

>[!WARNING]
> Configuração **-SubmitSamplesConsent para** `NeverSend` ou `AlwaysPrompt` diminuirá o nível de proteção do dispositivo. Além disso, defini-lo como significa que o recurso Bloquear à Primeira Vista do Microsoft Defender para Ponto de `NeverSend` Extremidade não [](configure-block-at-first-sight-microsoft-defender-antivirus.md) funcionará.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Use a Instrução de Gerenciamento do Windows (WMI) para ativar a proteção entregue na nuvem

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) para as seguintes propriedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obter mais informações sobre parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Ativar a proteção entregue na nuvem em clientes individuais com o aplicativo segurança do Windows

> [!NOTE]
> Se a **configuração Configurar a** substituição de configuração local  para relatar a Política de Grupo do Microsoft MAPS estiver definida como **Desabilitada,** a configuração de proteção baseada em nuvem nas Configurações do Windows ficará esbabada e indisponível. As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows.

1. Abra o aplicativo segurança do Windows selecionando o ícone de escudo na barra de tarefas ou pesquisando o menu iniciar do **Defender**.

2. Selecione o **&** de proteção contra ameaças (ou o ícone de escudo na barra de **menus** esquerda) e, em seguida, o rótulo de configurações de proteção contra ameaças & vírus:

    ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme se **a Proteção baseada em nuvem** e o envio automático **de** exemplo estão comutado para **On**.

> [!NOTE]
> Se o envio automático de exemplo tiver sido configurado com a Política de Grupo, a configuração ficará acinzenada e indisponível.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar o período de tempo limite de bloqueio da nuvem](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurar o bloco à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usar cmdlets do PowerShell para gerenciar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Ajudar a proteger computadores Windows com a Proteção de Ponto de Extremidade para o Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlets defender](/powershell/module/defender/)
- [Usar a proteção entregue na nuvem da Microsoft no Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md)
- [Como criar e implantar políticas antimalware: serviço de proteção na nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)