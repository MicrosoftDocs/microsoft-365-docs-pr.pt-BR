---
title: Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)
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
description: Implante o pacote de configuração no dispositivo VDI (virtual desktop infrastructure) para que eles sejam integrados ao serviço de prevenção contra perda de dados do ponto de extremidade do Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769385"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)

**Aplica-se a:**
- [Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

- Dispositivos VDI (virtual desktop infrastructure)

>[!WARNING]
> Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios. Cenários de várias sessões na Área de Trabalho Virtual do Windows não são suportados no momento.

## <a name="onboard-vdi-devices"></a>Dispositivos VDI onboard

A prevenção contra perda de dados do ponto de extremidade do Microsoft 365 dá suporte à integração de sessão VDI não persistente. 

>[!Note]
>Para fazer a integração de sessões VDI não persistentes, os dispositivos VDI devem estar no Windows 10 1809 ou superior.

Pode haver desafios associados ao integração de VDIs. Veja a seguir os desafios típicos para este cenário:

- Integração antecipada instantânea de sessões de curta duração, que devem ser integradas à prevenção contra perda de dados do ponto de extremidade do Microsoft 365 antes do provisionamento real.
- O nome do dispositivo normalmente é reutilizável para novas sessões.

Os dispositivos VDI podem aparecer no Centro de Conformidade do Microsoft 365 como:

- Entrada única para cada dispositivo.  
Observe que, nesse  caso, o mesmo nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônomo.
- Várias entradas para cada dispositivo, uma para cada sessão.

As etapas a seguir orientarão você durante a integração de dispositivos VDI e destacarão as etapas para entradas individuais e múltiplas.

>[!WARNING]
> Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode retardar a integração da prevenção contra perda de dados do Ponto de Extremidade do Microsoft 365. 

1.  Abra o arquivo .zip do pacote de configuração *VDI (DeviceCompliancePackage.zip)* que você baixou do assistente de integração de serviço.

2.  No painel de navegação, selecione **Configurações**  >  **integração do dispositivo à**  >  **integração.**

3. No campo **do método de** implantação, selecione scripts de integração VDI para pontos de extremidade não **persistentes.**

5. Clique **em Baixar pacote** e salve o arquivo .zip.

6. Copie os arquivos da pasta DeviceCompliancePackage extraída do arquivo .zip para a `golden/master` imagem no `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` caminho. 

7. Se você não estiver implementando uma única entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

8. Se você estiver implementando uma única entrada para cada dispositivo, copie Onboard-NonPersistentMachine.ps1 e DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela pode estar oculta. Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.

9. Abra uma janela do Editor de Política de Grupo Local e navegue **até** a Inicialização de Scripts de Configurações do  >  **Windows**  >  **de Configuração do**  >  **Computador.**

   > [!NOTE]
   > A Política de Grupo de Domínio também pode ser usada para integração de dispositivos VDI não persistentes.

4. Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:

   **Para entrada única para cada dispositivo**
   
   Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração.
   
   **Para várias entradas para cada dispositivo:**
   
   Selecione a **guia Scripts** e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script bash de `DeviceComplianceOnboardingScript.cmd` integração.

5. Teste sua solução:

   1. Crie um pool com um dispositivo.
      
   1. Logon no dispositivo.
      
   1. Fazer logoff do dispositivo.

   1. Fazer logon no dispositivo com outro usuário.
      
   1. **Para uma entrada única para cada dispositivo:** verifique apenas uma entrada na Central de Segurança do Microsoft Defender.<br>
      **Para várias entradas para cada dispositivo:** verifique várias entradas na Central de Segurança do Microsoft Defender.

6. Clique **na lista Dispositivos** no painel de navegação.

7. Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo** como tipo de pesquisa.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Atualizando imagens de VDI (infraestrutura de área de trabalho virtual) não persistente
Como prática recomendável, recomendamos usar ferramentas de manutenção offline para corrigir imagens de ouro/mestre.<br>
Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:
- [Modificar uma imagem do Windows usando o DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opções de gerenciamento de imagens Command-Line DISM](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reduzir o tamanho do armazenamento de componentes em uma imagem offline do Windows](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:

1. Depois de inicializar a imagem mestra para manutenção online ou correção, execute um script de redução de memória para desativar o sensor de prevenção contra perda de dados do ponto de extremidade do Microsoft 365. Para obter mais informações, consulte [Dispositivos offboard usando um script local.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. Verifique se o sensor está parado executando o comando abaixo em uma janela CMD:

   ```console
   sc query sense
   ```

3. Manutenção da imagem conforme necessário.

4. Execute os comandos a seguir usando PsExec.exe (que podem ser baixados para limpar o conteúdo da pasta cibernética que o sensor pode ter acumulado desde https://download.sysinternals.com/files/PSTools.zip) a inicialização:

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. Sele a imagem "ouro/mestre" como faria normalmente.

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando Política de Grupo](dlp-configure-endpoints-gp.md)
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
