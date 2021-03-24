---
title: Implantação manual do Microsoft Defender ATP para macOS
description: Instale o Microsoft Defender ATP para macOS manualmente, na linha de comando.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 382abd78ffa5e30c79804f9eaed211dffba7589c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052906"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a>Implantação manual do Microsoft Defender para Ponto de Extremidade para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Este tópico descreve como implantar o Microsoft Defender para Ponto de Extremidade para macOS manualmente. Uma implantação bem-sucedida requer a conclusão de todas as etapas a seguir:
- [Baixar pacotes de instalação e integração](#download-installation-and-onboarding-packages)
- [Instalação do aplicativo (macOS 10.15 e versões anteriores)](#application-installation-macos-1015-and-older-versions)
- [Instalação do aplicativo (macOS 11 e versões mais recentes)](#application-installation-macos-11-and-newer-versions)
- [Configuração do cliente](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a>Pré-requisitos e requisitos do sistema

Antes de começar, consulte a página principal do Microsoft Defender para Ponto de Extremidade para [macOS](microsoft-defender-endpoint-mac.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.

## <a name="download-installation-and-onboarding-packages"></a>Baixar pacotes de instalação e integração

Baixe os pacotes de instalação e integração do Centro de Segurança do Microsoft Defender:

1. No Centro de Segurança do Microsoft Defender, acesse **Configurações > Gerenciamento de Dispositivos > Integração**.
2. Na Seção 1 da página, de definir o sistema operacional como **macOS** e o método Deployment como **script local**.
3. Na Seção 2 da página, selecione **Baixar pacote de instalação**. Salve-o como wdav.pkg em um diretório local.
4. Na Seção 2 da página, selecione **Baixar pacote de integração**. Salve-o como WindowsDefenderATPOnboardingPackage.zip no mesmo diretório.

    ![Captura de tela do Centro de Segurança do Microsoft Defender](images/atp-portal-onboarding-page.png)

5. Em um prompt de comando, verifique se você tem os dois arquivos.
    
## <a name="application-installation-macos-1015-and-older-versions"></a>Instalação do aplicativo (macOS 10.15 e versões anteriores)

Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.

1. Navegue até o wdav.pkg baixado no Finder e abra-o.

    ![Captura de tela de instalação do aplicativo1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.

    ![Captura de tela de instalação do aplicativo2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > Você será solicitado a permitir que um driver da Microsoft seja instalado ("Bloqueio de Extensão do Sistema" ou "Instalação está em espera" ou ambos. O driver deve ter permissão para ser instalado.

   ![Captura de tela de instalação do aplicativo3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. Selecione **Abrir Preferências de Segurança** ou Abrir **Preferências do Sistema > Segurança & Privacidade**. Selecione **Permitir**:

    ![Captura de tela de janela de segurança e privacidade](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   A instalação continua.

   > [!CAUTION]
   > Se você não selecionar **Permitir**, a instalação prosseguirá após 5 minutos. O Microsoft Defender para Ponto de Extremidade será carregado, mas alguns recursos, como proteção em tempo real, serão desabilitados. Consulte [Solucionar problemas de extensão do kernel](mac-support-kext.md) para obter informações sobre como resolver isso.

> [!NOTE]
> O macOS pode solicitar a reinicialização do dispositivo na primeira instalação do Microsoft Defender para Ponto de Extremidade. A proteção em tempo real não estará disponível até que o dispositivo seja reiniciado.

## <a name="application-installation-macos-11-and-newer-versions"></a>Instalação do aplicativo (macOS 11 e versões mais recentes)

Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.

1. Navegue até o wdav.pkg baixado no Finder e abra-o.

    ![Captura de tela de instalação do aplicativo4](images/big-sur-install-1.png)

2. Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.

3. No final do processo de instalação, você será promovido a aprovar as extensões do sistema usadas pelo produto. Selecione **Abrir Preferências de Segurança**.

    ![Aprovação de extensão do sistema](images/big-sur-install-2.png)

4. Na janela **Segurança & Privacidade,** selecione **Permitir**.

    ![Preferências de segurança de extensão do sistema1](images/big-sur-install-3.png)

5. Repita as etapas 3 & 4 para todas as extensões do sistema distribuídas com o Microsoft Defender para Ponto de Extremidade para Mac.

6. Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade para Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender. Quando solicitado a conceder permissões do Microsoft Defender para o Ponto de Extremidade para filtrar o tráfego de rede, selecione **Permitir**.

    ![Preferências de segurança de extensão do sistema2](images/big-sur-install-4.png)

7. Abra **Preferências do** Sistema Segurança & Privacidade e navegue até a guia Privacidade. Conceda permissão de Acesso em Disco Completo para o Microsoft Defender ATP e a Extensão de Segurança do Ponto de Extremidade do  >   Microsoft Defender **ATP.**   

    ![Acesso em disco completo](images/big-sur-install-5.png)

## <a name="client-configuration"></a>Configuração do cliente

1. Copie wdav.pkg e MicrosoftDefenderATPOnboardingMacOs.py para o dispositivo onde você implanta o Microsoft Defender para Ponto de Extremidade para macOS.

    O dispositivo cliente não está associado a orgId. Observe que o *atributo orgId* está em branco.

    ```bash
    mdatp health --field org_id
    ```

2. Execute o script Python para instalar o arquivo de configuração:

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. Verifique se o dispositivo agora está associado à sua organização e relata uma *orgId válida*:

    ```bash
    mdatp health --field org_id
    ```

Após a instalação, você verá o ícone do Microsoft Defender na barra de status do macOS no canto superior direito.

   ![Ícone do Microsoft Defender na captura de tela da barra de status](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a>Como permitir o acesso total ao disco

> [!CAUTION]
> O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade. A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito. Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.

Para conceder consentimento, abra Preferências do Sistema -> Segurança & Privacidade -> Privacidade -> Acesso total em disco. Clique no ícone de bloqueio para fazer alterações (parte inferior da caixa de diálogo). Selecione Microsoft Defender para Ponto de Extremidade.

## <a name="logging-installation-issues"></a>Problemas de instalação de log

Consulte [Log de problemas de](mac-resources.md#logging-installation-issues) instalação para obter mais informações sobre como encontrar o log gerado automaticamente que é criado pelo instalador quando ocorre um erro.

## <a name="uninstallation"></a>Desinstalação

Consulte [Desinstalar](mac-resources.md#uninstalling) para obter detalhes sobre como remover o Microsoft Defender for Endpoint para macOS de dispositivos cliente.
