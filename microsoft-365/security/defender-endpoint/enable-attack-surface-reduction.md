---
title: Habilitar regras da redução da superfície de ataque
description: Habilita as regras de redução de superfície de ataque (ASR) para proteger seus dispositivos contra ataques que usam macros, scripts e técnicas de injeção comuns.
keywords: Redução de superfície de ataque, quadris, sistema de prevenção contra intrusões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, habilitar, ativar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570943"
---
# <a name="enable-attack-surface-reduction-rules"></a>Habilitar regras da redução da superfície de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[As regras de redução de](attack-surface-reduction.md) superfície de ataque (regras ASR) ajudam a evitar ações que o malware geralmente abusa para comprometer dispositivos e redes. Você pode definir regras ASR para dispositivos que executam qualquer uma das seguintes edições e versões do Windows:
- Windows 10 Pro, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows 10 Enterprise, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows Server, [versão 1803 (Canal Semesanuais)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Cada regra ASR contém uma das três configurações:

- Não configurado: desabilitar a regra ASR
- Bloquear: Habilitar a regra ASR
- Auditoria: Avalie como a regra ASR afetaria sua organização se habilitada

É altamente recomendável que você use regras ASR com uma licença do Windows E5 (ou SKU de licenciamento semelhante) para aproveitar os recursos avançados de monitoramento e relatório disponíveis no [Microsoft Defender para Ponto](https://docs.microsoft.com/windows/security/threat-protection) de Extremidade (Defender para Ponto de Extremidade). No entanto, para outras licenças, como o Windows Professional ou o E3 que não têm acesso aos recursos avançados de monitoramento e relatórios, você pode desenvolver suas próprias ferramentas de monitoramento e relatório em cima dos eventos gerados em cada ponto de extremidade quando as regras ASR são acionadas (por exemplo, Encaminhamento de Eventos).

> [!TIP]
> Para saber mais sobre o licenciamento do Windows, consulte [Licenciamento do Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e obter o guia de Licenciamento por [Volume do Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

Você pode habilitar regras de redução de superfície de ataque usando qualquer um desses métodos:

- [Microsoft Intune](#intune)
- [Gerenciamento de Dispositivo Móvel (MDM)](#mdm)
- [Gerenciador de Configuração do Microsoft Endpoint](#microsoft-endpoint-configuration-manager)
- [Política de grupo](#group-policy)
- [PowerShell](#powershell)

É recomendável o gerenciamento no nível empresarial, como o Intune ou o Microsoft Endpoint Manager. O gerenciamento no nível empresarial substituirá qualquer política de grupo conflitante ou configurações do PowerShell na inicialização.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Excluir arquivos e pastas de regras ASR

Você pode excluir arquivos e pastas de serem avaliados pela maioria das regras de redução de superfície de ataque. Isso significa que, mesmo que uma regra ASR determine que o arquivo ou pasta contém comportamento mal-intencionado, ele não impedirá a execução do arquivo. Isso pode permitir que arquivos não seguros executem e infectem seus dispositivos.

Você também pode excluir as regras ASR de disparar com base em hashes de certificado e arquivo, permitindo indicadores de certificado e de arquivo do Defender para Ponto de Extremidade especificados. (Consulte [Gerenciar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> A exclusão de arquivos ou pastas pode reduzir gravemente a proteção fornecida pelas regras ASR. Arquivos excluídos terão permissão para serem executados e nenhum relatório ou evento será gravado.
> Se as regras ASR estão detectando arquivos que você acredita que não devem ser detectados, você deve usar o modo de auditoria [primeiro para testar a regra](evaluate-attack-surface-reduction.md).


Você pode especificar arquivos ou pastas individuais (usando caminhos de pasta ou nomes de recursos totalmente qualificados), mas não pode especificar a quais regras as exclusões se aplicam. Uma exclusão é aplicada somente quando o aplicativo ou serviço excluído é iniciado. Por exemplo, se você adicionar uma exclusão para um serviço de atualização que já está em execução, o serviço de atualização continuará disparando eventos até que o serviço seja interrompido e reiniciado.

As regras ASR suportam variáveis de ambiente e caracteres curinga. Para obter informações sobre como usar caracteres curinga, consulte Use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Os procedimentos a seguir para habilenciar regras ASR incluem instruções sobre como excluir arquivos e pastas.

## <a name="intune"></a>Intune

1. Selecione **Perfis de**  >  **configuração do dispositivo**. Escolha um perfil de proteção de ponto de extremidade existente ou crie um novo. Para criar um novo, selecione **Criar perfil e** insira informações para esse perfil. Para **o tipo de** perfil, selecione Proteção de ponto de **extremidade**. Se você tiver escolhido um perfil existente, selecione **Propriedades** e, em seguida, selecione **Configurações**.

2. No painel **proteção de ponto de** extremidade, selecione Windows Defender Exploit **Guard,** em seguida, **selecione Redução de Superfície de Ataque**. Selecione a configuração desejada para cada regra ASR.

3. Em **Exceções de Redução de Superfície de Ataque,** insira arquivos e pastas individuais. Você também pode selecionar **Importar para** importar um arquivo CSV que contém arquivos e pastas a ser excluído das regras ASR. Cada linha no arquivo CSV deve ser formatada da seguinte forma:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Selecione **OK** nos três painéis de configuração. Em **seguida, selecione** Criar se você estiver criando um novo arquivo de proteção de ponto de extremidade ou **Salvar** se estiver editando um existente.

## <a name="mdm"></a>MDM

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) para habilitar e definir individualmente o modo para cada regra.

A seguir, um exemplo de referência, usando [valores GUID para regras ASR](attack-surface-reduction.md#attack-surface-reduction-rules).

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

Os valores para habilitar, desabilitar ou habilitar no modo de auditoria são:

- Desabilitar = 0
- Bloquear (habilitar regra ASR) = 1
- Auditoria = 2

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) para adicionar exclusões.

Exemplo:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Insira valores OMA-URI sem espaços.

## <a name="microsoft-endpoint-configuration-manager"></a>Gerenciador de Configuração do Microsoft Endpoint

1. No Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard.**

2. Selecione **Home**  >  **Create Exploit Guard Policy**.

3. Insira um nome e uma descrição, selecione **Redução de Superfície de Ataque** e selecione **Próximo**.

4. Escolha quais regras bloquearão ou auditarão ações e selecione **Next**.

5. Revise as configurações e selecione **Próximo** para criar a política.

6. Depois que a política for criada, **Feche**.

## <a name="group-policy"></a>Política de Grupo

> [!WARNING]
> Se você gerenciar seus computadores e dispositivos com o Intune, o Configuration Manager ou outra plataforma de gerenciamento de nível empresarial, o software de gerenciamento substituirá quaisquer configurações conflitantes da Política de Grupo na inicialização.

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender Antivírus**  >  **Redução** de superfície  >  **de ataque do** Microsoft Defender Exploit Guard .

4. Selecione **Configurar regras de redução de superfície de ataque** e selecione **Habilitado**. Em seguida, você pode definir o estado individual para cada regra na seção opções.

   Selecione **Mostrar...** e insira a ID da regra na coluna **Nome do** valor e seu estado escolhido na coluna **Valor** da seguinte forma:

   - Desabilitar = 0
   - Bloquear (habilitar regra ASR) = 1
   - Auditoria = 2

   ![Configuração da política de grupo mostrando uma ID da regra de redução de superfície de ataque em branco e o valor de 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. Para excluir arquivos e pastas de regras  ASR, selecione a configuração Excluir arquivos e caminhos de regras de redução de superfície de ataque e de definir a opção **como Habilitado**. Selecione **Mostrar** e insira cada arquivo ou pasta na coluna **Nome do** valor. Insira **0** na coluna **Valor** para cada item.

> [!WARNING]
> Não use aspas, pois elas não são suportadas para a coluna **Nome do** valor ou para a **coluna Valor.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Se você gerenciar seus computadores e dispositivos com o Intune, o Configuration Manager ou outra plataforma de gerenciamento de nível empresarial, o software de gerenciamento substituirá as configurações conflitantes do PowerShell na inicialização. Para permitir que os usuários definam o valor usando o PowerShell, use a opção "Definido pelo Usuário" para a regra na plataforma de gerenciamento.

1. Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.

2. Insira o seguinte cmdlet:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Para habilitar regras ASR no modo de auditoria, use o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Para desativar as regras ASR, use o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > Você deve especificar o estado individualmente para cada regra, mas pode combinar regras e estados em uma lista separada por vírgulas.
    >
    > No exemplo a seguir, as duas primeiras regras serão habilitadas, a terceira regra será desabilitada e a quarta regra será habilitada no modo de auditoria:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    Você também pode usar o `Add-MpPreference` verbo PowerShell para adicionar novas regras à lista existente.

    > [!WARNING]
    > `Set-MpPreference` sempre substituirá o conjunto de regras existente. Se você quiser adicionar ao conjunto existente, você deve usar `Add-MpPreference` em vez disso.
    > Você pode obter uma lista de regras e seu estado atual usando `Get-MpPreference` .

3. Para excluir arquivos e pastas de regras ASR, use o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Continue a usar `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` para adicionar mais arquivos e pastas à lista.

    > [!IMPORTANT]
    > Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista. O uso `Set-MpPreference` do cmdlet substituirá a lista existente.

## <a name="related-articles"></a>Artigos relacionados

- [Reduzir superfícies de ataque com regras de redução de superfície de ataque](attack-surface-reduction.md)

- [Avaliar a redução de superfície de ataque](evaluate-attack-surface-reduction.md)

- [Perguntas frequentes sobre a redução da superfície de ataque](attack-surface-reduction.md)
