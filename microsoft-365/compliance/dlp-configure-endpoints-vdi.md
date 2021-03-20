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
description: Implante o pacote de configuração no dispositivo VDI (infraestrutura de área de trabalho virtual) para que eles sejam integrados ao serviço de prevenção contra perda de dados do Microsoft 365 Endpoint.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917947"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)

**Aplica-se a:**
- [Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)](./endpoint-dlp-learn-about.md)

- Dispositivos VDI (infraestrutura de área de trabalho virtual)

>[!WARNING]
> O suporte para prevenção contra perda de dados do Microsoft 365 Endpoint para a Área de Trabalho Virtual do Windows oferece suporte a cenários de sessão única. Cenários de várias sessões na Área de Trabalho Virtual do Windows não são suportados no momento.

## <a name="onboard-vdi-devices"></a>Dispositivos VDI de integração

A prevenção contra perda de dados do Microsoft 365 Endpoint dá suporte à integração de sessão VDI não persistente. 

>[!Note]
>Para fazer a integração de sessões VDI não persistentes, os dispositivos VDI devem estar no Windows 10 1809 ou superior.

Pode haver desafios associados ao integração de VDIs. Veja a seguir os desafios típicos para este cenário:

- Integração instantânea inicial de uma sessão de curta duração, que deve ser integrada à prevenção contra perda de dados do Ponto de Extremidade do Microsoft 365 antes do provisionamento real.
- O nome do dispositivo normalmente é reutilizável para novas sessões.

Dispositivos VDI podem aparecer no Centro de Conformidade do Microsoft 365 como:

- Entrada única para cada dispositivo.  
Observe que, nesse caso, *o* mesmo nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônoma.
- Várias entradas para cada dispositivo - uma para cada sessão.

As etapas a seguir orientarão você através da integração de dispositivos VDI e destacarão etapas para entradas simples e múltiplas.

>[!WARNING]
> Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode atrasar a integração da prevenção contra perda de dados do Microsoft 365 Endpoint. 

1.  Abra o arquivo .zip do pacote de configuração da VDI *(DeviceCompliancePackage.zip*) que você baixou do assistente de integração do serviço.

2.  No painel de navegação, selecione **Configurações**  >  **Integração do dispositivo** de  >  **integração**.

3. No campo **Método de implantação,** selecione scripts de **integração VDI para pontos de extremidade** não persistentes .

5. Clique **em Baixar pacote** e salve o arquivo .zip.

6. Copie os arquivos da pasta DeviceCompliancePackage extraída do arquivo .zip para a `golden/master` imagem sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` . 

7. Se você não estiver implementando uma única entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.

8. Se você estiver implementando uma única entrada para cada dispositivo, copie o Onboard-NonPersistentMachine.ps1 e DeviceComplianceOnboardingScript.cmd.
    
    > [!NOTE]
    > Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta. Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.

9. Abra uma janela Editor de Política de Grupo Local e navegue até **Configuração** do  >  **Computador Configuração** do Windows  >  **Scripts**  >  **Inicialização**.

   > [!NOTE]
   > A Política de Grupo de Domínio também pode ser usada para a integração de dispositivos VDI não persistentes.

4. Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:

   **Para entrada única para cada dispositivo**
   
   Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração.
   
   **Para várias entradas para cada dispositivo**:
   
   Selecione a **guia Scripts** e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente). Navegue até o script bash de `DeviceComplianceOnboardingScript.cmd` integração.

5. Teste sua solução:

   1. Crie um pool com um dispositivo.
      
   1. Logon no dispositivo.
      
   1. Logoff do dispositivo.

   1. Fazer logon no dispositivo com outro usuário.
      
   1. **Para entrada única para cada dispositivo**: Verifique apenas uma entrada no Centro de Segurança do Microsoft Defender.<br>
      **Para várias entradas para cada dispositivo**: Verifique várias entradas no Centro de Segurança do Microsoft Defender.

6. Clique **na lista Dispositivos** no painel De navegação.

7. Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo como** tipo de pesquisa.

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>Atualizando imagens VDI (infraestrutura de área de trabalho virtual não persistente)
Como prática prática, recomendamos usar ferramentas de manutenção offline para corrigir imagens douradas/mestras.<br>
Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:
- [Modificar uma imagem do Windows usando o DISM](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [Opções de gerenciamento de imagens Command-Line DISM](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [Reduzir o tamanho do Armazenamento de Componentes em uma imagem offline do Windows](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:

1. Depois de inicializar a imagem mestra para manutenção ou correção online, execute um script de offboard para desativar o sensor de prevenção contra perda de dados do Microsoft 365 Endpoint. Para obter mais informações, consulte [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).

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
- [Integração de dispositivos Windows 10 usando a Política de Grupo](dlp-configure-endpoints-gp.md)
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md)
- [Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)