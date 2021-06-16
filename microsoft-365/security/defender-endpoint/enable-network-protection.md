---
title: Ativar a proteção de rede
description: Habilita a proteção de rede com a Política de Grupo, o PowerShell ou o Gerenciador de Configuração e Gerenciamento de Dispositivo Móvel.
keywords: Proteção do ANetwork, explorações, site mal-intencionado, ip, domínio, domínios, habilitar, ativar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bde97638a39eef4561b898b2cf49e51bed6e77a5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926650"
---
# <a name="turn-on-network-protection"></a>Ativar a proteção de rede

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[A proteção de](network-protection.md) rede ajuda a impedir que os funcionários usem qualquer aplicativo para acessar domínios perigosos que podem hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet. Você pode [auditar](evaluate-network-protection.md) a proteção de rede em um ambiente de teste para exibir quais aplicativos seriam bloqueados antes de habilita-la.

[Saiba mais sobre as opções de configuração de filtragem de rede](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Verificar se a proteção de rede está habilitada

Verifique se a proteção de rede foi habilitada em um dispositivo local usando o editor do Registro.

1. Selecione o **botão Iniciar** na barra de tarefas e digite **regedit** para abrir o editor do Registro

2. Escolha **HKEY_LOCAL_MACHINE** no menu lateral

3. Navegue pelos menus aninhados para **SOFTWARE**  >  **Microsoft**  >  **Windows Defender**  >  **Windows Defender Proteção de**  >   Rede do Exploit Guard

4. Selecione **EnableNetworkProtection** para ver o estado atual da proteção de rede no dispositivo

    * 0 ou **Off**
    * 1 ou **On**
    * 2, ou **Modo de** auditoria
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Habilitar a proteção de rede

Habilita a proteção de rede usando qualquer um desses métodos:

* [PowerShell](#powershell)
* [Gerenciamento de Dispositivo Móvel (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Política de grupo](#group-policy)

### <a name="powershell"></a>PowerShell

1. Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**
2. Insira o seguinte cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Opcional: Habilita o recurso no modo de auditoria usando o seguinte cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Use `Disabled` em vez de ou para desativar o `AuditMode` `Enabled` recurso.

### <a name="mobile-device-management-mdm"></a>Gerenciamento de dispositivos móveis (MDM)

Use o provedor de serviço de configuração [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) (CSP) para habilitar ou desabilitar a proteção de rede ou habilitar o modo de auditoria.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (anteriormente Intune)

1. Entre no centro de Microsoft Endpoint Manager de administração (https://endpoint.microsoft.com)

2. Criar ou editar um perfil [de configuração de proteção de ponto de extremidade](/mem/intune/protect/endpoint-protection-configure)

3. Em **Configuração Configurações** no fluxo de perfil, vá **para** Microsoft Defender Exploit Guard Proteção de rede de filtragem de  >    >    >  rede **habilitar** **ou auditar somente**

### <a name="group-policy"></a>Política de Grupo

Use o procedimento a seguir para habilitar a proteção de rede em computadores ingressados no domínio ou em um computador autônomo.

1. Em um computador autônomo, vá para **Iniciar** e digite e selecione **Editar política de grupo**.

    *-Ou-*

    Em um computador de gerenciamento de Política de Grupo ingressado no domínio, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.

3. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  Windows Defender Proteção de Rede do Exploit **Guard.**  >  

> [!NOTE]
> Em versões mais antigas Windows, o caminho da política de grupo pode dizer "Windows Defender Antivírus" em vez de "Microsoft Defender Antivírus".

4. Clique duas vezes na **configuração Impedir que usuários e aplicativos** acessem sites perigosos e de definir a opção **como Habilitado.** Na seção opções, você deve especificar uma das seguintes opções:
    * **Bloquear** - Os usuários não podem acessar endereços IP mal-intencionados e domínios
    * **Desabilitar (Padrão)** - O recurso de proteção de rede não funcionará. Os usuários não serão impedidos de acessar domínios mal-intencionados
    * **Modo de** Auditoria - Se um usuário visitar um endereço IP ou domínio mal-intencionado, um evento será gravado no log de eventos Windows de eventos mal-intencionados. No entanto, o usuário não será impedido de visitar o endereço.

> [!IMPORTANT]
> Para habilitar totalmente a proteção de  rede, você deve definir a opção Política de Grupo como Habilitada e também selecionar **Bloquear** no menu suspenso opções.

Confirme se a proteção de rede está habilitada em um computador local usando o editor do Registro:

1. Selecione **Iniciar** e digite **regedit** para abrir **o Editor do Registro.**

2. Navegue até **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. Selecione **EnableNetworkProtection** e confirme o valor:
   * 0=Off
   * 1=On
   * 2=Auditoria

## <a name="see-also"></a>Confira também

* [Proteção de rede](network-protection.md)
* [Avaliar a proteção de rede](evaluate-network-protection.md)
* [Solucionar problemas de proteção de rede](troubleshoot-np.md)
