---
title: Especifique o nível de proteção fornecido na nuvem para Microsoft Defender Antivírus
description: De definir seu nível de proteção entregue na nuvem para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, agressividade, nível de proteção
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274899"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Especificar o nível de proteção fornecida na nuvem

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode especificar seu nível de proteção entregue na nuvem oferecido pelo Microsoft Defender Antivírus usando o Microsoft Endpoint Manager (recomendado) ou a Política de Grupo.

> [!TIP]
> A proteção em nuvem não é simplesmente proteção para arquivos armazenados na nuvem. O Microsoft Defender Antivírus de nuvem é um mecanismo para fornecer proteção atualizada para sua rede e dispositivos (também chamados de pontos de extremidade). A proteção na nuvem com Microsoft Defender Antivírus usa recursos distribuídos e aprendizado de máquina para oferecer proteção aos seus pontos de extremidade em uma taxa muito mais rápida do que as atualizações tradicionais de inteligência de segurança. Microsoft Intune e Microsoft Endpoint Manager agora fazem parte [do Microsoft Endpoint Manager](/mem/endpoint-manager-overview). 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Use Microsoft Endpoint Manager para especificar o nível de proteção entregue na nuvem

1. Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e entre.

2. Escolha **Endpoint security**  >  **Antivírus**.

3. Selecione um perfil antivírus. (Se você ainda não tiver um ou se quiser criar um novo perfil, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).

4. Selecione **Propriedades**. Em seguida, ao lado **das configurações,** escolha **Editar**.

5. Expanda **a proteção na** nuvem e, em seguida, na lista de níveis de proteção entregues na nuvem, selecione um dos seguintes: 

    1. **Alto**: aplica um nível forte de detecção.
    2. **Alta a** mais : usa **o nível** Alto e aplica medidas de proteção adicionais (pode afetar o desempenho do cliente).
    3. **Tolerância zero**: bloqueia todos os executáveis desconhecidos.

6. Escolha **Revisar + salvar** e, em seguida, escolha **Salvar**. 

> [!TIP]
> Precisa de ajuda? Consulte os seguintes recursos:
> - [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Adicionar configurações de proteção de ponto de extremidade no Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Usar a Política de Grupo para especificar o nível de proteção entregue na nuvem

1.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

3.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do Computador  >  **Modelos administrativos.**

4.  Expanda a árvore para **Windows**  >  **Componentes Microsoft Defender Antivírus**  >  **MpEngine**.

5.  Clique duas vezes na **configuração Selecionar nível** de proteção na nuvem e des ajuste-o **como Habilitado**. Selecione o nível de proteção:
    - **O nível de bloqueio padrão** fornece uma detecção forte sem aumentar o risco de detectar arquivos legítimos.
    - **O nível de bloqueio moderado** fornece apenas moderado para detecções de alta confiança
    - **Alto nível de bloqueio** aplica um alto nível de detecção ao otimizar o desempenho do cliente (mas também pode dar uma maior chance de falsos positivos).
    - **Alto + nível de bloqueio** aplica medidas de proteção adicionais (pode afetar o desempenho do cliente e aumentar a chance de falsos positivos).
    - **O nível de bloqueio de tolerância** zero bloqueia todos os executáveis desconhecidos.
    
    > [!WARNING]
    > Embora improvável, definir essa opção como **Alto** ou Alto **+** pode fazer com que alguns arquivos legítimos sejam detectados (embora você tenha a opção de desbloquear ou contestar essa detecção).

6. Clique em **OK**.

7. Implante seu objeto de Política de Grupo atualizado. Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Você está usando Objetos de Política de Grupo no local? Veja como eles se traduzem na nuvem. [Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização . 
  
## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Como criar e implantar políticas antimalware: serviço de proteção na nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)