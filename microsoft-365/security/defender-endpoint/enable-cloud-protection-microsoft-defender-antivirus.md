---
title: Ativar proteção fornecida pela nuvem em Microsoft Defender Antivírus
description: Acotoda a proteção fornecida pela nuvem para se beneficiar de recursos de proteção rápidos e avançados.
keywords: Microsoft Defender Antivírus, antimalware, segurança, nuvem, bloco à primeira vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572052"
---
# <a name="turn-on-cloud-delivered-protection"></a>Ativar a proteção fornecida pela nuvem

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> O serviço de nuvem Microsoft Defender Antivírus é um mecanismo para fornecer proteção atualizada à sua rede e pontos finais. Embora seja chamado de serviço de nuvem, não é simplesmente proteção para arquivos armazenados na nuvem; em vez disso, ele usa recursos distribuídos e aprendizado de máquina para fornecer proteção aos seus pontos finais a uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança.

Microsoft Defender Antivírus usa múltiplas tecnologias de detecção e prevenção para fornecer proteção precisa, em tempo real e inteligente. [Conheça as tecnologias avançadas no núcleo do Microsoft Defender para proteção de próxima geração do Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

Você pode ativar ou desativar Microsoft Defender Antivírus proteção fornecida pela nuvem de várias maneiras:

- Microsoft Intune
- Microsoft Endpoint Manager
- Política de Grupo
- Cmdlets PowerShell.

 Você também pode ligá-lo ou desligá-lo em clientes individuais com o aplicativo Segurança do Windows.

Consulte [Use a proteção fornecida pela Nuvem da Microsoft](cloud-protection-microsoft-defender-antivirus.md) para uma visão geral da proteção fornecida pela nuvem Microsoft Defender Antivírus.

Para obter mais informações sobre os requisitos específicos de conectividade de rede para garantir que seus pontos finais possam se conectar ao serviço de proteção entregue à nuvem, consulte [Configurar e validar conexões de rede](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> Em Windows 10, não há diferença entre as opções **de relatórios Básicos** e **Avançados** descritas neste tópico. Esta é uma distinção legado e escolher qualquer configuração resultará no mesmo nível de proteção fornecida pela nuvem. Não há diferença no tipo ou quantidade de informações que são compartilhadas. Para obter mais informações sobre o que coletamos, consulte a [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Use o Intune para ativar a proteção fornecida pela nuvem

1. Vá para o centro administrativo Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () e faça login.

2. No **painel Home,** selecione **Configuração do dispositivo > Perfis**.

3. Selecione o tipo de perfil **de restrições do dispositivo** que deseja configurar. Se você precisar criar um novo tipo de perfil **de restrições do dispositivo,** consulte [Configurar as configurações de restrição do dispositivo em Microsoft Intune](/intune/device-restrictions-configure).

4. Selecione   >  **configurações de configuração de propriedades: Editar**  >  **Microsoft Defender Antivírus**.

5. No switch **de proteção entregue à Nuvem,** selecione **Ativar**.

6. No **Prompt users antes** da submissão da amostra, selecione **Enviar todos os dados automaticamente**.

Para obter mais informações sobre os perfis dos dispositivos Intune, incluindo como criar e configurar suas configurações, consulte [Quais são Microsoft Intune perfis de dispositivos?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Use Microsoft Endpoint Manager para ativar a proteção fornecida pela nuvem

1. Vá para o centro administrativo Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () e faça login.

2. Escolha **o Antivírus de segurança endpoint**  >  .

3. Selecione um perfil antivírus. (Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configurar as configurações de restrição do dispositivo em Microsoft Intune](/intune/device-restrictions-configure).

4. Selecione **Propriedades**. Em seguida, ao lado **das configurações de configuração,** escolha **Editar**.

5. Expanda a **proteção da nuvem** e, em seguida, na lista **de nível de proteção fornecida pela Nuvem,** selecione um dos seguintes:
   - **Alto:** Aplica um forte nível de detecção.
   - **Alto plus**: Usa o **alto** nível e aplica medidas adicionais de proteção (pode afetar o desempenho do cliente).
   - **Tolerância zero**: Bloqueia todos os executáveis desconhecidos.

6. Selecione **Review + salvar**, e escolha **Salvar**.

Para obter mais informações sobre a configuração Microsoft Endpoint Configuration Manager, consulte [Como criar e implantar políticas antimalware: serviço de proteção de nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Use a Política do Grupo para ativar a proteção fornecida pela nuvem

1. Em seu dispositivo de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**.

2. No **Editor de Gerenciamento de Políticas de Grupo**, vá para **configuração de computador**.

3. Selecione **modelos administrativos**.

4. Expandir a árvore para **Windows componentes > Microsoft Defender Antivírus > MAPS**

5. Clique duas vezes **em "Junte-se ao Microsoft MAPS"**. Certifique-se de que a opção está ligada e definida para **MAPAS Básicos** ou **MAPAS Avançados**. Selecione **OK**.

6. Clique duas vezes **Enviar amostras de arquivos quando for necessária uma análise adicional**. Certifique-se de que a primeira opção está definida como **Habilitada** e que as outras opções estão definidas para qualquer um:

    1. **Enviar amostras seguras** (1)
    2. **Envie todas as amostras** (3)

        >[!NOTE]
        > A opção **Enviar amostras seguras** (1) significa que a maioria das amostras será enviada automaticamente. Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.
        > Definir a opção para **Always Prompt** (0) reduzirá o estado de proteção do dispositivo. Defini-lo para **Nunca enviar** (2) significa que o recurso Block at [First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) do Microsoft Defender for Endpoint não funcionará.

7. Selecione **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Use cmdlets do PowerShell para ativar a proteção fornecida pela nuvem

Os seguintes cmdlets podem ativar a proteção fornecida pela nuvem:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [usar cmdlets do PowerShell para configurar e executar Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e os [cmdlets Defender](/powershell/module/defender/). [Política CSP - Defender](/windows/client-management/mdm/policy-csp-defender) também tem mais informações especificamente sobre [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Você também pode definir **-EnviarSamplesConsent** para `SendSafeSamples` (a configuração padrão) `NeverSend` ou `AlwaysPrompt` . A `SendSafeSamples` configuração significa que a maioria das amostras será enviada automaticamente. Os arquivos que provavelmente contêm informações pessoais ainda solicitarão e exigirão confirmação adicional.

>[!WARNING]
> Configuração **-EnviarSamplesConsent** para `NeverSend` ou `AlwaysPrompt` reduzirá o nível de proteção do dispositivo. Além disso, defini-lo `NeverSend` significa que o recurso Block at First [Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) do Microsoft Defender for Endpoint não funcionará.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Use o WMI (Windows Management Instruction, instrução de gerenciamento de Windows para ativar a proteção fornecida pela nuvem

Use o método [ **Definir** da](/previous-versions/windows/desktop/defender/set-msft-mppreference) classe MSFT_MpPreference para as seguintes propriedades:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Para obter mais informações sobre parâmetros permitidos, consulte [Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Acodou a proteção fornecida pela nuvem em clientes individuais com o aplicativo Segurança do Windows

> [!NOTE]
> Se a **configuração local configurar para relatar** a configuração de política de grupo do Microsoft MAPS for definida como **Desativada,** então a **configuração de proteção baseada** em nuvem em Windows Configurações estará acinzentada e indisponível. As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas configurações do Windows.

1. Abra o aplicativo Segurança do Windows selecionando o ícone do escudo na barra de tarefas ou pesquisando no menu iniciar para **o Defender**.

2. Selecione o **ladrilho de proteção contra ameaças virus &** (ou o ícone do escudo na barra de menu esquerda) e, em seguida, o rótulo de **configurações de proteção contra ameaças do Vírus &:**

    ![Captura de tela do rótulo de configurações da Proteção contra vírus e ameaças no aplicativo de segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme se **a proteção baseada em nuvem** e o envio automático de **amostras** estão ligados **.**

> [!NOTE]
> Se o envio automático da amostra tiver sido configurado com a Política de Grupo, a configuração estará acinzentada e indisponível.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar o período de tempo limite de bloqueio da nuvem](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurar bloco à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usar cmdlets do PowerShell para gerenciar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Ajude a proteger Windows PCs com Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlets defensores](/powershell/module/defender/)
- [Use a proteção fornecida pela Microsoft em Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md)
- [Como criar e implantar políticas antimalware: serviço de proteção à nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
