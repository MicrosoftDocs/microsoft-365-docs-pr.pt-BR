---
title: Personalizar o acesso controlado a pastas
description: Adicione outras pastas que devem ser protegidas pelo acesso controlado a pastas ou permita que aplicativos que bloqueem incorretamente as alterações em arquivos importantes.
keywords: Acesso controlado a pastas, windows 10, windows defender, ransomware, proteger, arquivos, pastas, personalizar, adicionar pasta, adicionar aplicativo, permitir, adicionar executável
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199894"
---
# <a name="customize-controlled-folder-access"></a>Personalizar o acesso controlado a pastas

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


O acesso controlado a pastas ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware. O acesso controlado a pastas é suportado nos clientes do Windows Server 2019 e do Windows 10.

Este artigo descreve como personalizar recursos de acesso controlado a pastas e inclui as seguintes seções:

- [Proteger pastas adicionais](#protect-additional-folders)
- [Adicionar aplicativos que devem ter permissão para acessar pastas protegidas](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Permitir que arquivos executáveis assinados acessem pastas protegidas](#allow-signed-executable-files-to-access-protected-folders)
- [Personalizar a notificação](#customize-the-notification)

> [!IMPORTANT]
> O acesso controlado a pastas monitora aplicativos para atividades detectadas como mal-intencionadas. Às vezes, aplicativos legítimos são impedidos de fazer alterações em seus arquivos. Se o acesso controlado a pastas afetar a produtividade da [](audit-windows-defender.md) sua organização, considere executar esse recurso no modo de auditoria para avaliar totalmente o impacto.

## <a name="protect-additional-folders"></a>Proteger pastas adicionais

O acesso controlado a pastas se aplica a várias pastas do sistema e locais padrão, incluindo pastas como **Documentos,** **Imagens** e **Filmes.** Você pode adicionar pastas adicionais a serem protegidas, mas não pode remover as pastas padrão na lista padrão.

Adicionar outras pastas ao acesso controlado a pastas pode ser útil para casos em que você não armazena arquivos nas bibliotecas padrão do Windows ou alterou o local padrão de suas bibliotecas.

Você também pode especificar compartilhamentos de rede e unidades mapeadas. Há suporte para variáveis de ambiente e curingas. Para obter informações sobre como usar caracteres curinga, consulte Use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Você pode usar o aplicativo segurança do Windows, Política de Grupo, cmdlets do PowerShell ou provedores de serviço de configuração de gerenciamento de dispositivo móvel para adicionar e remover pastas protegidas adicionais.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Usar o aplicativo segurança do Windows para proteger pastas adicionais

1. Abra o aplicativo segurança do Windows selecionando o ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.

2. Selecione **Proteção contra & contra vírus** e, em seguida, role para baixo até a seção proteção **ransomware.**

3. Selecione **Gerenciar proteção de ransomware** para abrir o painel de proteção do **Ransomware.**

4. Na seção **Acesso controlado a pastas,** selecione **Pastas protegidas**.

5. Escolha **Sim** no prompt **controle de acesso do** usuário. O **painel Pastas Protegidas** é exibido.

4. Selecione **Adicionar uma pasta protegida** e siga os prompts para adicionar pastas.

### <a name="use-group-policy-to-protect-additional-folders"></a>Usar a Política de Grupo para proteger pastas adicionais

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .

4. Clique duas vezes **em Configurações de pastas protegidas** e de definir a opção como **Habilitado**. Selecione **Mostrar** e insira cada pasta.

### <a name="use-powershell-to-protect-additional-folders"></a>Usar o PowerShell para proteger pastas adicionais

1. Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**

2. Insira o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Repita a etapa 2 até que você tenha adicionado todas as pastas que deseja proteger. As pastas adicionadas ficam visíveis no aplicativo segurança do Windows.

   ![Captura de tela de uma janela do PowerShell com o cmdlet acima inserido](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista. O uso `Set-MpPreference` do cmdlet substituirá a lista existente.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Usar CSPs MDM para proteger pastas adicionais

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Permitir que aplicativos específicos façam alterações em pastas controladas

Você pode especificar se determinados aplicativos são sempre considerados seguros e dar acesso de gravação a arquivos em pastas protegidas. Permitir aplicativos pode ser útil se um aplicativo específico que você conhece e confiança estiver sendo bloqueado pelo recurso de acesso controlado a pastas.

> [!IMPORTANT]
> Por padrão, o Windows adiciona aplicativos considerados amigáveis à lista permitida. Esses aplicativos adicionados automaticamente não são registrados na lista mostrada no aplicativo segurança do Windows ou usando os cmdlets associados do PowerShell. Não é necessário adicionar a maioria dos aplicativos. Adicione apenas aplicativos se eles estão sendo bloqueados e você pode verificar sua confiabilidade.

Ao adicionar um aplicativo, você precisa especificar o local do aplicativo. Somente o aplicativo nesse local terá acesso permitido às pastas protegidas. Se o aplicativo (com o mesmo nome) estiver em um local diferente, ele não será adicionado à lista de autorizações e poderá ser bloqueado pelo acesso controlado a pastas.

Um aplicativo ou serviço permitido só tem acesso de gravação a uma pasta controlada depois que ele é iniciado. Por exemplo, um serviço de atualização continuará disparando eventos depois que ele for permitido até ser interrompido e reiniciado.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Use o aplicativo Windows Defender Segurança para permitir aplicativos específicos

1. Abra o aplicativo segurança do Windows pesquisando o menu iniciar para **Segurança**.

2. Selecione o **&** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione Gerenciar proteção **de ransomware**.

3. Na seção **Acesso controlado a pastas,** selecione **Permitir um aplicativo por meio do acesso controlado a pastas**

4. Selecione **Adicionar um aplicativo permitido** e siga as solicitações para adicionar aplicativos.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Adicionar um botão de aplicativo permitido":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Usar a Política de Grupo para permitir aplicativos específicos

1. Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .

4. Clique duas vezes na **configuração Configurar aplicativos permitidos** e de definir a opção **como Habilitado**. Selecione **Mostrar** e insira cada aplicativo.

### <a name="use-powershell-to-allow-specific-apps"></a>Usar o PowerShell para permitir aplicativos específicos

1. Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**
2. Insira o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Por exemplo, para adicionar  otest.exeexecutável localizado na pasta *C:\apps,* o cmdlet seria o seguinte:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Continue a usar `Add-MpPreference -ControlledFolderAccessAllowedApplications` para adicionar mais aplicativos à lista. Os aplicativos adicionados usando esse cmdlet aparecerão no aplicativo segurança do Windows.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet do PowerShell para permitir um aplicativo":::

> [!IMPORTANT]
> Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista. O uso `Set-MpPreference` do cmdlet substituirá a lista existente.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Usar CSPs MDM para permitir aplicativos específicos

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Permitir que arquivos executáveis assinados acessem pastas protegidas

Os indicadores de certificado e arquivo do Microsoft Defender for Endpoint podem permitir que arquivos executáveis assinados acessem pastas protegidas. Para obter detalhes da implementação, [consulte Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).

> [!Note]
> Isso não se aplica a mecanismos de script, incluindo o Powershell

## <a name="customize-the-notification"></a>Personalizar a notificação

Para obter mais informações sobre como personalizar a notificação quando uma regra é disparada e bloqueia um aplicativo ou arquivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).

## <a name="see-also"></a>Confira também

- [Proteger pastas importantes com acesso controlado a pastas](controlled-folders.md)
- [Habilitar o acesso controlado a pastas](enable-controlled-folders.md)
- [Avaliar regras de redução de superfície de ataque](evaluate-attack-surface-reduction.md)
