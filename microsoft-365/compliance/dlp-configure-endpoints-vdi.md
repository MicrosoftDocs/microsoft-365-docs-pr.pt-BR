---
title: Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implante o pacote de configuração no dispositivo virtual Desktop Infrastructure (VDI) para que eles sejam integrados ao serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769385"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)

**Aplica-se a:**
- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivos de infraestrutura de área de trabalho virtual (VDI)

>[!WARNING]
> Microsoft 365 Endpoint Data Loss Prevention support for Windows Virtual Desktop suporta cenários de sessão única. Cenários de várias sessões na área de trabalho virtual do Windows atualmente não são suportados.

## <a name="onboard-vdi-devices"></a>Dispositivos VDI integrados

A prevenção de perda de dados de ponto de extremidade do Microsoft 365 suporta integração de sessão VDI não persistente. 

>[!Note]
>Para sessões de VDI não persistente integradas, os dispositivos VDI devem estar no Windows 10 1809 ou superior.

Pode haver desafios associados durante a integração do VDIs. Estes são os desafios típicos para este cenário:

- A integração instantânea antecipada de uma sessão de curta duração, que deve ser integrada à prevenção de perda de dados de ponto de extremidade do Microsoft 365 antes do provisionamento real.
- O nome do dispositivo é normalmente reutilizado para novas sessões.

Os dispositivos VDI podem aparecer no centro de conformidade da Microsoft 365 como:

- Única entrada para cada dispositivo.  
Observe que, nesse caso, o *mesmo* nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônomo.
- Várias entradas para cada dispositivo-um para cada sessão.

As etapas a seguir irão orientá-lo na integração de dispositivos de VDI e destacará as etapas de entradas únicas e múltiplas.

>[!WARNING]
> Para ambientes onde há configurações de poucos recursos, o procedimento de inicialização do VDI pode diminuir a integração do Microsoft 365 Endpoint Data Loss Prevention. 

1.  Abra o arquivo. zip do pacote de configuração VDI ( *DeviceCompliancePackage.zip* ) que você baixou a partir do assistente de integração de serviço.

2.  No painel de navegação, selecione integração de integração do dispositivo de **configuração**  >  **Device onboarding**  >  **Onboarding** .

3. No campo **método de implantação** , selecione **scripts de integração VDI para pontos de extremidade não persistentes** .

5. Clique em **baixar pacote** e salve o arquivo. zip.

6. Copie os arquivos da pasta DeviceCompliancePackage extraídos do arquivo. zip para a `golden/master` imagem sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Se você não estiver implementando uma única entrada para cada dispositivo, copie DeviceComplianceOnboardingScript. cmd.

8. Se você estiver implementando uma única entrada para cada dispositivo, copie Onboard-NonPersistentMachine.ps1 e DeviceComplianceOnboardingScript. cmd.
    
    > [!NOTE]
    > Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta. Você precisará escolher a opção **mostrar pastas e arquivos ocultos** no explorador de arquivos.

9. Abra uma janela do editor de política de grupo local e navegue até **configuração do computador**  >  scripts de **configurações do Windows**  >  **Scripts**  >  **Startup** .

   > [!NOTE]
   > A política de grupo de domínio também pode ser usada para a integração de dispositivos não persistentes de VDI.

4. Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:

   **Para entrada única para cada dispositivo**
   
   Selecione a guia **scripts do PowerShell** e, em seguida, clique em **Adicionar** (o Windows Explorer será aberto diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até script do PowerShell de integração `Onboard-NonPersistentMachine.ps1` .
   
   **Para várias entradas para cada dispositivo** :
   
   Selecione a guia **scripts** e clique em **Adicionar** (o Windows Explorer será aberto diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script de bash de integração `DeviceComplianceOnboardingScript.cmd` .

5. Teste sua solução:

   1. Criar um pool com um dispositivo.
      
   1. Faça logon no dispositivo.
      
   1. Faça logoff do dispositivo.

   1. Faça logon no dispositivo com outro usuário.
      
   1. **Para entrada única para cada dispositivo** : Verifique apenas uma entrada na central de segurança do Microsoft defender.<br>
      **Para várias entradas para cada dispositivo** : marque várias entradas na central de segurança do Microsoft defender.

6. Clique em **lista de dispositivos** no painel de navegação.

7. Use a função de pesquisa inserindo o nome do dispositivo e selecione **dispositivo** como tipo de pesquisa.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Atualizando imagens não persistentes de infraestrutura de área de trabalho virtual (VDI)
Como prática recomendada, recomendamos o uso de ferramentas de serviço offline para corrigir imagens de ouro/Master.<br>
Por exemplo, você pode usar os comandos a seguir para instalar uma atualização enquanto a imagem permanecer offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obter mais informações sobre os comandos DISM e a manutenção offline, consulte os artigos a seguir:
- [Modificar uma imagem do Windows usando o DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opções de Command-Line de gerenciamento de imagem DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reduzir o tamanho do repositório de componentes em uma imagem offline do Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se a manutenção offline não for uma opção viável para seu ambiente de VDI não persistente, as seguintes etapas devem ser seguidas para garantir a consistência e a integridade do sensor:

1. Após a inicialização da imagem mestra para manutenção ou correção online, execute um script de remoção para desativar o sensor de prevenção de perda de dados de ponto de extremidade do Microsoft 365. Para obter mais informações, consulte [externamente dispositivos usando um script local](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

2. Verifique se o sensor foi interrompido executando o comando abaixo em uma janela CMD:

   ```console
   sc query sense
   ```

3. Atender a imagem, conforme necessário.

4. Execute os comandos a seguir usando PsExec.exe (que pode ser baixado de https://download.sysinternals.com/files/PSTools.zip) para limpar o conteúdo da pasta da CyberSource que o sensor pode ter acumulado desde a inicialização:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Lacrar novamente a imagem de ouro/Master como faria normalmente.

## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis](dlp-configure-endpoints-mdm.md)
- [Dispositivos integrados do Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
