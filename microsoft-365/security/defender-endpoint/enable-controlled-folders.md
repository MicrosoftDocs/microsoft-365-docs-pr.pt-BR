---
title: Habilitar o acesso controlado a pastas
keywords: Acesso controlado a pastas, windows 10, windows defender, ransomware, proteger, arquivos, pastas, habilitar, ativar, usar
description: Saiba como proteger seus arquivos importantes habilitando o acesso controlado a pastas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861214"
---
# <a name="enable-controlled-folder-access"></a>Habilitar o acesso controlado a pastas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[O acesso controlado a pastas](controlled-folders.md) ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware. O acesso controlado a pastas está incluído no Windows 10 e Windows Server 2019.

Você pode habilitar o acesso controlado a pastas usando qualquer um desses métodos:

* [Segurança do Windows app](#windows-security-app)
* [Microsoft Endpoint Manager](#endpoint-manager)
* [Gerenciamento de Dispositivo Móvel (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Política de grupo](#group-policy)
* [PowerShell](#powershell)

[O modo de](evaluate-controlled-folder-access.md) auditoria permite testar como o recurso funcionaria (e revisar eventos) sem afetar o uso normal do dispositivo.

As configurações da Política de Grupo que desabilitam a mesclação de listas de administradores locais substituirão as configurações de acesso controlado a pastas. Eles também substituem pastas protegidas e permitem aplicativos definidos pelo administrador local por meio de acesso controlado a pastas. Essas políticas incluem:

* Microsoft Defender Antivírus configurar **o comportamento de mesclagem de administrador local para listas**
* System Center Endpoint Protection permitir **que os usuários adicionem exclusões e substituições**

Para obter mais informações sobre como desabilitar a mesclação de listas locais, consulte Prevent or allow users [to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).

## <a name="windows-security-app"></a>Segurança do Windows app

1. Abra o Segurança do Windows aplicativo selecionando o ícone de escudo na barra de tarefas. Você também pode pesquisar o menu iniciar para **Defender**.

2. Selecione o **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione **Proteção contra ransomware**.

3. De definir a opção para **Acesso controlado à pasta** como **On**.

> [!NOTE]
> Se o acesso controlado a pastas estiver configurado com A Política de Grupo, PowerShell ou CSPs MDM, o estado mudará no aplicativo Segurança do Windows após uma reinicialização do dispositivo.
> Se o recurso for definido como **Modo de** Auditoria com qualquer uma dessas ferramentas, o aplicativo Segurança do Windows mostrará o estado como **Off**.
> Se você estiver protegendo dados de perfil de usuário, recomendamos que o perfil de usuário deve estar na unidade de instalação Windows padrão.

## <a name="endpoint-manager"></a>Gerenciador de Pontos de Extremidade

1. Entre no Endpoint Manager [e](https://endpoint.microsoft.com) abra a Segurança do Ponto de **Extremidade.**

2. Vá para **Política de Redução de Superfície de**  >  **Ataque**.

3. Selecione **Plataforma,** escolha **Windows 10 e posterior** e selecione o perfil Regras de Redução de Superfície de **Ataque**  >  **Criar**.

4.  Nomeia a política e adicione uma descrição. Selecione **Avançar**.

5.  Role para baixo até a parte inferior, selecione o menu drop-down **Habilitar Proteção** de Pasta e escolha **Habilitar**.

6.  Selecione **Lista de pastas adicionais que precisam ser protegidas** e adicione as pastas que precisam ser protegidas.

7.  Selecione **Lista de aplicativos que têm acesso** a pastas protegidas e adicione os aplicativos que têm acesso a pastas protegidas.

8.  Selecione **Excluir arquivos e caminhos das regras** de redução de superfície de ataque e adicione os arquivos e caminhos que precisam ser excluídos das regras de redução de superfície de ataque.

9.  Selecione as **atribuições de perfil,** atribua a Todos os **Usuários & Todos os** Dispositivos e selecione **Salvar**.

10.  Selecione **Próximo para** salvar cada folha aberta **e,** em seguida, Criar .

   > [!NOTE]
   > Os curingas são suportados para aplicativos, mas não para pastas. As subpastas não estão protegidas. Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.

## <a name="mobile-device-management-mdm"></a>Gerenciamento de Dispositivo Móvel (MDM)

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Em Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard.**

2. Selecione **Home**  >  **Create Exploit Guard Policy**.

3. Insira um nome e uma descrição, selecione **Acesso controlado a** pastas e selecione **Próximo**.

4. Escolha se bloqueia ou audita alterações, permite outros aplicativos ou adiciona outras pastas e selecione **Next**.
   > [!NOTE]
   > O Wilcard é suportado para aplicativos, mas não para pastas. As subpastas não estão protegidas. Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.

5. Revise as configurações e selecione **Próximo** para criar a política.

6. Depois que a política for criada, **Feche**.

## <a name="group-policy"></a>Política de Grupo

1. Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.

3. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Windows Defender Exploit Guard > acesso controlado à pasta**.

4. Clique duas vezes na **configuração Configurar acesso controlado a** pastas e de definir a opção como **Habilitado**. Na seção opções, você deve especificar uma das seguintes opções:
    * **Habilitar** - Aplicativos mal-intencionados e suspeitos não poderão fazer alterações em arquivos em pastas protegidas. Uma notificação será fornecida no log Windows evento.
    * **Desabilitar (Padrão)** - O recurso de acesso controlado a pastas não funcionará. Todos os aplicativos podem fazer alterações em arquivos em pastas protegidas.
    * **Modo de** Auditoria - As alterações serão permitidas se um aplicativo mal-intencionado ou suspeito tentar fazer uma alteração em um arquivo em uma pasta protegida. No entanto, ele será registrado no log de eventos Windows onde você pode avaliar o impacto em sua organização.
    * **Bloquear somente modificação de** disco - As tentativas por aplicativos não confirmados para gravar em setores de disco serão registradas Windows log de eventos. Esses logs podem ser encontrados em **Logs de** Aplicativos e Serviços > Microsoft > Windows > Windows Defender > ID > ID 1123.
    * **Somente** modificação de disco de auditoria - Somente as tentativas de gravação em setores de disco protegidos serão registradas no log de eventos Windows (em Logs de Aplicativos e Serviços da  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **ID Operacional 1124**). As tentativas de modificar ou excluir arquivos em pastas protegidas não serão gravadas.

      ![Captura de tela da opção de política de grupo Habilitado e Modo de Auditoria selecionado no drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Para habilitar totalmente o acesso controlado a  pastas, você deve definir a opção Política de Grupo como Habilitado e selecionar **Bloquear** no menu suspenso opções.

## <a name="powershell"></a>PowerShell

1. Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.

2. Insira o seguinte cmdlet:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Você pode habilitar o recurso no modo de auditoria especificando em `AuditMode` vez de `Enabled` .

Use `Disabled` para desativar o recurso.

## <a name="see-also"></a>Confira também

* [Proteger pastas importantes com acesso controlado a pastas](controlled-folders.md)
* [Personalizar o acesso controlado a pastas](customize-controlled-folders.md)
* [Avaliar o Microsoft Defender para Ponto de Extremidade](evaluate-mde.md)
