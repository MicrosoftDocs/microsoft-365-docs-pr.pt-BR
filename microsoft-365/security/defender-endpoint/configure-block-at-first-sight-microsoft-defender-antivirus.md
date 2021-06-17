---
title: Habilite o recurso bloquear à primeira vista para detectar malware em segundos
description: Habilite o recurso bloquear à primeira vista para detectar e bloquear malware em segundos.
keywords: verificar, bloquear à primeira vista, malware, primeira vista, nuvem, defender, antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/15/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3a5f766e21afcb29d3503345a49637061b5f0e38
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964694"
---
# <a name="turn-on-block-at-first-sight"></a>Ativar o recurso bloquear à primeira vista

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Este artigo descreve um recurso do antivírus/antimalware conhecido como "bloquear à primeira vista" e descreve como habilitar o recurso bloquear à primeira vista para sua organização. 

> [!TIP]
> Este artigo se destina a administradores corporativos e Profissionais de TI que gerenciam configurações de segurança para organizações. Se você não é um administrador corporativo ou Profissional de TI, mas tem dúvidas sobre o recurso bloquear à primeira vista, consulte a seção [Não sou um administrador corporativo ou Profissional de TI?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>O que é "bloquear à primeira vista"?

Bloquear à primeira vista é um recurso de proteção de última geração contra ameaças que detecta novos malwares e os bloqueia em segundos. O recurso bloquear à primeira vista é habilitado quando certas configurações de segurança são habilitadas. Essas configurações incluem:

- Proteção fornecida pela nuvem; 
- Um tempo limite específico para envio de amostras (por exemplo, 50 segundos); e 
- Um alto nível de bloqueio de arquivos. 

Na maioria das organizações empresariais, as configurações necessárias para habilitar o recurso bloquear à primeira vista são definidas com as implantações do Microsoft Defender Antivirus. 

## <a name="how-it-works"></a>Como funciona

Quando o Microsoft Defender Antivirus encontra um arquivo suspeito, mas não detectado, ele consulta nosso back-end de proteção em nuvem. O back-end da nuvem aplica heurística, aprendizado de máquina e análise automatizada do arquivo para determinar se os arquivos são maliciosos ou não são uma ameaça.

O Microsoft Defender Antivirus utiliza várias tecnologias de detecção e prevenção para fornecer uma proteção precisa, inteligente e em tempo real. 

![Lista de motores AV do Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Para saber mais, consulte [ (Blog) Conheça as tecnologias avançadas no núcleo do Microsoft Defender para Ponto de Extremidade para proteção de última geração](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Algumas coisas para saber sobre o recurso bloquear à primeira vista

- No Windows 10, versão 1803 ou posterior, o recurso bloquear à primeira vista pode bloquear arquivos executáveis não portáteis (como JS, VBS ou macros) e arquivos executáveis.

- O recurso bloquear à primeira vista usa apenas o back-end de proteção em nuvem para arquivos executáveis e arquivos executáveis não portáteis baixados da Internet ou originados da zona da Internet. Um valor do hash do arquivo .exe é verificado por meio do back-end da nuvem para determinar se o arquivo é um arquivo não detectado anteriormente.

- Se o back-end da nuvem não for capaz de fazer uma determinação, o Microsoft Defender Antivirus bloqueará o arquivo e carregará uma cópia para a nuvem. A nuvem realizará mais análises para chegar a uma determinação antes de permitir que o arquivo seja executado ou bloqueado em todos os encontros futuros, dependendo se ela determinará o arquivo como sendo malicioso ou como não sendo uma ameaça.

- Em muitos casos, esse processo pode reduzir o tempo de resposta para um novo malware de horas para segundos.

- Você pode [especificar por quanto tempo um arquivo deve ser impedido de ser executado](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) enquanto o serviço de proteção baseado em nuvem analisa o arquivo. E você pode [personalizar a mensagem exibida na área de trabalho dos usuários](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) quando um arquivo for bloqueado. Você pode alterar o nome da empresa, informações de contato e URL da mensagem.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Ative o recurso bloquear à primeira vista com o Microsoft Intune

> [!TIP]
> O Microsoft Intune agora faz parte do Microsoft Endpoint Manager.

1. No Centro de administração do Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navegue até **Dispositivos** > **Perfis de configuração**.

2. Selecione ou crie um perfil usando o tipo de perfil **Restrições do dispositivo**.

3. Em **Definições de configuração** para o perfil de restrições de Dispositivo, defina ou confirme as seguintes configurações em **Microsoft Defender Antivirus**:

   - **Proteção fornecida pela nuvem**: Habilitada
   - **Nível de Bloqueio de Arquivo**: Alto
   - **Extensão de tempo para verificação de arquivos pela nuvem**: 50
   - **Avisar os usuários antes do envio da amostra**: Enviar todos os dados sem avisar

   ![Configuração do Intune](images/defender/intune-block-at-first-sight.png)

4. Salvar suas configurações.

> [!TIP]
> - Definir o nível de bloqueio de arquivo como **Alto** aplica um nível forte de detecção. No caso improvável de o bloqueio de arquivos causar uma detecção de falso positivo de arquivos legítimos, sua equipe de operações de segurança pode [restaurar os arquivos em quarentena](./restore-quarantined-files-microsoft-defender-antivirus.md).
> - Para obter mais informações sobre como configurar as restrições do dispositivo Microsoft Defender Antivirus no Intune, consulte [Definir configurações de restrição do dispositivo no Microsoft Intune](/intune/device-restrictions-configure).
> - Para obter uma lista de restrições de dispositivo do Microsoft Defender Antivirus no Intune, consulte [Restrição do dispositivo para configurações do Windows 10 (e mais recentes) no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Ative o recurso bloquear à primeira vista com o Microsoft Endpoint Manager

> [!TIP]
> Se você está procurando o Gerenciador de Configurações do Microsoft Endpoint, agora ele faz parte do Microsoft Endpoint Manager.

1. No Microsoft Endpoint Manager ([ https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vá para **Segurança do ponto de extremidade** > **Antivirus**.

2. Selecione uma política existente ou crie uma nova utilizando o tipo de perfil **Microsoft Defender Antivirus**.

3. Defina ou confirme as seguintes configurações:

   - **Ativar a proteção fornecida pela nuvem**: Sim
   - **Nível de proteção fornecido pela nuvem**: Alto
   - **Tempo limite estendido do Defender Cloud em segundos**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Configurações do recurso bloquear à primeira vista no Endpoint Manager ":::

4. Aplique o perfil do Microsoft Defender Antivirus a um grupo, como **Todos os usuários**, **Todos os dispositivos** ou **Todos os usuários e dispositivos**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Ative o recurso bloquear à primeira vista com a Política de Grupo

> [!NOTE]
> Recomendamos o uso do Intune ou do Microsoft Endpoint Manager para ativar o recurso bloquear à primeira vista. 

1. No computador de gerenciamento de Política de Grupo, abra o [ Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**. 

2. Usando o **Editor de Gerenciamento de Política de Grupo**, vá até **Configuração do computador** > **Modelos administrativos** > **Componentes do Windows** > **Microsoft Defender Antivirus** > **MAPS**. 

3. Na seção MAPS, clique duas vezes em **Configurar o recurso 'Bloquear na primeira vista'**, defina-o como **Ativado** e selecione **OK**.

    > [!IMPORTANT]
    > Definir para **Sempre solicitar (0)** diminuirá o estado de proteção do dispositivo. Definir como **Nunca enviar (2)** significa que o recurso bloquear à primeira vista não funcionará.

4. Na seção MAPS, clique duas vezes em **Enviar amostras do arquivo quando uma análise adicional for necessária** e defina-o como **Habilitado**. Em **Enviar amostras do arquivo quando análises adicionais forem necessárias**, selecione **Enviar todas as amostras** e, em seguida, selecione **OK**.

5. Reimplante seu Objeto de Política de Grupo na sua rede como de costuma.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Confirme se o recurso bloquear à primeira vista está ativado nos dispositivos clientes individuais

Você pode confirmar se o recurso bloquear à primeira vista está habilitado nos dispositivos clientes individuais usando o aplicativo de Segurança do Windows. O recurso bloquear à primeira vista é ativado automaticamente, desde que a **Proteção fornecida pela Nuvem** e o **Envio automático de amostras** estejam ambos ativados.

1. Abra o aplicativo Segurança do Windows.

2. Selecione **Proteção contra vírus e ameaças** e, em **Configurações de proteção contra vírus e ameaças**, selecione **Gerenciar Configurações**.

   ![Captura de tela do rótulo de configurações da Proteção contra vírus e ameaças no aplicativo de segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme se a **Proteção fornecida pela nuvem** e o **Envio automático de amostra** estão ativados.

> [!NOTE]
> - Se as configurações de pré-requisito forem definidas e implantadas usando a Política de Grupo, as configurações descritas nesta seção ficarão esmaecidas e indisponíveis para uso em pontos de extremidade individuais. 
> - As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas configurações do Windows.

## <a name="validate-block-at-first-sight-is-working"></a>Validar se o recurso bloquear à primeira vista está funcionando

Para validar se o recurso está funcionando, baixe o [arquivo de exemplo Bloquear à primeira vista](https://demo.wd.microsoft.com/Page/BAFS). Para baixar o arquivo, você precisará de uma conta no Azure AD que tenha a função administrador de segurança ou administrador global atribuída.

Para validar se a proteção habilitada para nuvem está funcionando, siga as diretrizes em [Validar conexões entre sua rede e a nuvem](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud). 

## <a name="turn-off-block-at-first-sight"></a>Desativar o recurso bloquear à primeira vista

> [!CAUTION]
> Desativar o recurso bloquear à primeira vista diminuirá o estado de proteção do(s) seu(s) dispositivo(s) e da sua rede.

Você pode optar por desabilitar o recurso bloquear à primeira vista se quiser manter as configurações de pré-requisito sem realmente usar a proteção do recurso bloquear à primeira vista. Você pode desativar temporariamente o recurso bloquear à primeira vista para ver como esse recurso afetará sua rede. No entanto, não recomendamos desativar permanentemente a proteção do recurso bloquear à primeira vista.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Desativar o recurso bloquear à primeira vista com o Microsoft Endpoint Manager

1. Vá para o Centro de administração do Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e entre.

2. Vá para **Segurança do ponto de extremidade** > **Antivírus** e selecione a política do Microsoft Defender Antivirus.

3. Em **Gerenciar**, escolha **Propriedades**.

4. Ao lado de **Definições de configuração**, escolha **Editar**.

5. Altere uma ou mais das seguintes configurações:

   - Defina **Ativar proteção fornecida pela nuvem** como **Não** ou **Não configurado**.
   - Defina o **Nível de proteção fornecida pela nuvem** como **Não configurado**.
   - Desmarque a caixa de seleção para **Tempo Limite Estendido do Defender Cloud em Segundos**.

6. Revise e salve suas configurações.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Desativar o recurso bloquear à primeira vista com a Política de Grupo

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e selecione **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo** vá para **Configuração do computador** e selecione **Modelos administrativos**.

3. Expanda a árvore por meio dos **Componentes do Windows** > **Microsoft Defender Antivirus** > **MAPS**.

4. Clique duas vezes em **Configurar o recurso 'Bloquear à primeira Vista'** e defina a opção como **Desativado**.

    > [!NOTE]
    > Desativar o recurso bloquear à primeira vista não desativa ou altera as políticas de grupo de pré-requisito.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Não é um administrador corporativo ou profissional de TI?

Se você não é um administrador corporativo ou profissional de TI, mas tem dúvidas sobre o recurso bloquear à primeira vista, esta seção é para você. Bloquear à primeira vista é um recurso de proteção contra ameaças que detecta e bloqueia malware em segundos. Embora não haja uma configuração específica chamada "Bloquear à primeira vista", o recurso é habilitado quando certas configurações são definidas no seu dispositivo.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Como gerenciar o recurso bloquear à primeira vista ativado ou desativado em seu próprio dispositivo

Se você tiver um dispositivo pessoal que não é gerenciado por uma organização, pode estar se perguntando como ativar ou desativar o recurso bloquear à primeira vista. Você pode usar o aplicativo Windows Security para gerenciar o recurso bloquear à primeira vista.

1. No seu computador com Windows 10, abra o aplicativo Segurança do Windows.

2. Select **Proteção contra vírus e ameaças**.

3. Em **Configurações de Proteção contra vírus e ameaças**, selecione **Gerenciar configurações**.

4. Siga uma destas etapas:

   - Para ativar o recurso bloquear à primeira vista, certifique-se de que a **Proteção fornecida pela nuvem** e o **Envio automático de amostras** estejam ativados.

   - Para desativar o recurso bloquear à primeira vista, desative **Proteção fornecida pela nuvem** ou **Envio automático de amostras**. <br/>
    
     > [!CAUTION]
     > Desativar o recurso bloquear à primeira vista reduz o nível de proteção do seu dispositivo. Não recomendamos desabilitar permanentemente o recurso bloquear à primeira vista. 


## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Permaneça protegido com a Segurança do Windows](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
