---
title: Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)
description: Implante o pacote de configuração no dispositivo VDI (infraestrutura de área de trabalho virtual) para que eles sejam integrados ao serviço do Microsoft Defender ATP.
keywords: configurar dispositivo VDI (infraestrutura de área de trabalho virtual), vdi, gerenciamento de dispositivos, configurar pontos de extremidade do Windows ATP, configurar o Microsoft Defender para pontos de extremidade do ponto de extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: bf1e706562db06064409cb7cf11441d048ef8db6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445281"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Dispositivos VDI (infraestrutura de área de trabalho virtual)
- Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)

O Defender para Ponto de Extremidade dá suporte à integração de sessão VDI não persistente. 


Pode haver desafios associados ao integração de VDIs. Veja a seguir os desafios típicos para este cenário:

- Integração instantânea inicial de uma sessão de curta duração, que deve ser integrada ao Defender para o Ponto de Extremidade antes do provisionamento real.
- O nome do dispositivo normalmente é reutilizável para novas sessões.

Dispositivos VDI podem aparecer no portal do Defender para Ponto de Extremidade como:

- Entrada única para cada dispositivo.

  > [!NOTE]
  > Nesse caso, o *mesmo nome* de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônoma.

- Várias entradas para cada dispositivo - uma para cada sessão.

As etapas a seguir orientarão você através da integração de dispositivos VDI e destacarão etapas para entradas simples e múltiplas.

>[!WARNING]
> Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode atrasar a integração do sensor Defender para Ponto de Extremidade. 


### <a name="for-windows-10-or-windows-server-2019"></a>Para Windows 10 ou Windows Server 2019

1.  Abra o arquivo .zip do pacote de configuração da VDI *(WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço. Você também pode obter o pacote do [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

    1.  No painel de navegação, selecione **Configurações**  >  **Integração**.

    1. Selecione Windows 10 como o sistema operacional.

    1.  No campo **Método de implantação,** selecione scripts de **integração VDI para pontos de extremidade** não persistentes .

    1. Clique **em Baixar pacote** e salve o arquivo .zip.

2. Copie os arquivos da pasta WindowsDefenderATPOnboardingPackage extraída do arquivo .zip para a imagem `golden/master` sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

    1. Se você não estiver implementando uma única entrada para cada dispositivo, copie WindowsDefenderATPOnboardingScript.cmd.

    1. Se você estiver implementando uma única entrada para cada dispositivo, copie o Onboard-NonPersistentMachine.ps1 e WindowsDefenderATPOnboardingScript.cmd.
    
    > [!NOTE]
    > Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta. Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.

3. Abra uma janela Editor de Política de Grupo Local e navegue até **Configuração** do  >  **Computador Configuração** do Windows  >  **Scripts**  >  **Inicialização**.

   > [!NOTE]
   > A Política de Grupo de Domínio também pode ser usada para a integração de dispositivos VDI não persistentes.

4. Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:

   - Para entrada única para cada dispositivo:
   
     Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração. Não é necessário especificar o outro arquivo, pois ele será disparado automaticamente.
   
   - Para várias entradas para cada dispositivo:
   
     Selecione a **guia Scripts** e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script bash de `WindowsDefenderATPOnboardingScript.cmd` integração.

5. Teste sua solução:

   1. Crie um pool com um dispositivo.
      
   1. Logon no dispositivo.
      
   1. Logoff do dispositivo.

   1. Fazer logon no dispositivo com outro usuário.
      
   1. Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:
   
      - Para entrada única para cada dispositivo: 
    
        Verifique apenas uma entrada no Centro de Segurança do Microsoft Defender.

      - Para várias entradas para cada dispositivo: 
       
        Verifique várias entradas no Centro de Segurança do Microsoft Defender.

6. Clique **na lista Dispositivos** no painel De navegação.

7. Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo como** tipo de pesquisa.


## <a name="for-downlevel-skus"></a>Para SKUs de nível baixo

> [!NOTE]
> O registro a seguir é relevante somente quando o objetivo é alcançar uma "Entrada única para cada dispositivo".

1. De definir o valor do Registro como:

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    ou usando a linha de comando:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. Siga o [processo de integração do servidor](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016). 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Atualizando imagens VDI (infraestrutura de área de trabalho virtual não persistente)
Como prática prática, recomendamos usar ferramentas de manutenção offline para corrigir imagens douradas/mestras.<br>
Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:
- [Modificar uma imagem do Windows usando o DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opções de gerenciamento de imagens Command-Line DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reduzir o tamanho do Armazenamento de Componentes em uma imagem offline do Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:

1. Depois de inicializar a imagem mestra para manutenção ou correção online, execute um script de offboard para desativar o sensor Defender para Ponto de Extremidade. Para obter mais informações, consulte [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Verifique se o sensor é interrompido executando o comando abaixo em uma janela CMD:

   ```console
   sc query sense
   ```

3. Service the image as needed.

4. Execute os comandos abaixo usando PsExec.exe (que podem ser baixados para limpar o conteúdo da pasta cibernética que o sensor pode ter acumulado desde https://download.sysinternals.com/files/PSTools.zip) a inicialização:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Sele a imagem dourada/mestra como normalmente faria.

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando a Política de Grupo](configure-endpoints-gp.md)
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](configure-endpoints-script.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
