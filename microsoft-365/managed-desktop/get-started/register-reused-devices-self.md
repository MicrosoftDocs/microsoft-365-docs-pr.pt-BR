---
title: Registre dispositivos existentes por conta própria
description: Registrar os dispositivos reutilizados que você já pode ter para que eles possam ser gerenciados pelo Microsoft Managed desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289134"
---
# <a name="register-existing-devices-yourself"></a>Registre dispositivos existentes por conta própria

>[!NOTE]
>Este tópico descreve as etapas para reutilizar os dispositivos que você já tem e registrá-los na área de trabalho gerenciada da Microsoft. Se você estiver trabalhando com dispositivos novos, siga as etapas em [registrar novos dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md) em seu lugar.

O processo para parceiros está documentado em [etapas para que os parceiros registrem dispositivos](register-devices-partner.md).

A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente). Você pode registrar dispositivos usando o portal de administração de área de trabalho gerenciada da Microsoft.

## <a name="prepare-to-register-existing-devices"></a>Preparar-se para registrar dispositivos existentes


Para registrar dispositivos existentes, siga estas etapas:

1. [Obtenha o hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Mesclar os dados de hash](#merge-hash-data)
3. [Registre os dispositivos na área de trabalho gerenciada da Microsoft](#register-devices-by-using-the-admin-portal).
4. [Verifique se a imagem está correta.](#check-the-image)
5. [Entregar o dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obter o hash de hardware

A área de trabalho gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência a seu hash de hardware. Você tem quatro opções para obter essas informações de dispositivos que você já está usando:

- Pergunte ao seu fornecedor de OEM o arquivo de registro do piloto automático, que inclui os hashes de hardware.
- Coletar informações no [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Executar um script do Windows PowerShell, usando o [Active Directory](#active-directory-powershell-script-method) ou [manualmente](#manual-powershell-script-method) em cada dispositivo, e coletar os resultados em um arquivo.
- Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e [colete os hashes em uma unidade flash removível](#flash-drive-method).

#### <a name="microsoft-endpoint-configuration-manager"></a>Gerenciador de Configuração do Microsoft Endpoint

Você pode usar o Microsoft Endpoint Configuration Manager para coletar os hashes de hardware de dispositivos existentes que você deseja registrar com a área de trabalho gerenciada da Microsoft.

> [!IMPORTANT]
> Todos os dispositivos para os quais você deseja obter essas informações devem estar executando o Windows 10, versão 1703 ou posterior. 

Se você atendeu a todos esses pré-requisitos, você está pronto para coletar as informações seguindo estas etapas:

1. No console do Gerenciador de configurações, selecione **monitoramento**. 
2. No espaço de trabalho monitoramento, expanda o nó **relatórios** , expanda **relatórios**e selecione o nó **hardware-geral** . 
3. Execute o relatório, **as informações do dispositivo piloto automático do Windows**e exibir os resultados.
4. No Visualizador de relatórios, selecione o ícone **Exportar** e escolha a opção **CSV (delimitado por vírgulas)** .
5. Depois de salvar o arquivo, você precisará filtrar os resultados apenas para os dispositivos que pretende registrar na área de trabalho gerenciada da Microsoft e carregar os dados para o [portal de administração](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecionar **dispositivos** no painel de navegação esquerdo. Selecione **+ registrar dispositivos**; o funcionamento é aberto:


Consulte [registrar dispositivos usando o portal de administração](#register-devices-by-using-the-admin-portal) para obter mais informações.


#### <a name="active-directory-powershell-script-method"></a>Método de script do PowerShell do Active Directory

Em um ambiente do Active Directory, você pode usar o `Get-WindowsAutoPilotInfo` cmdlet do PowerShell para coletar remotamente as informações de dispositivos nos grupos do Active Directory usando o WinRM. Você também pode usar o `Get-AD Computer` cmdlet e obter resultados filtrados para um determinado nome de modelo de hardware incluído no catálogo. Para fazer isso, primeiro confirme esses pré-requisitos e prossiga com as etapas:

- O WinRM está habilitado.
- Os dispositivos que você deseja registrar estão ativos na rede (ou seja, eles não são desconectados ou desativados).
- Verifique se você tem um parâmetro de credencial de domínio que tenha permissão para executar remotamente nos dispositivos.
- Verifique se o Firewall do Windows permite acesso ao WMI. Para fazer isso, siga estas etapas:

    1. Abra o painel de controle do **Windows Defender firewall** e selecione **permitir um aplicativo ou recurso por meio do Windows Defender firewall**.
    
    2. Encontre **Instrumentação de gerenciamento do Windows (WMI)** na lista, habilite para **privado e público**e, em seguida, selecione **OK**.

1.  Abra um prompt do PowerShell com direitos administrativos.

2.  Execute *um* destes scripts:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Acessar os diretórios em que pode haver entradas para os dispositivos. Remova as entradas de cada dispositivo de *todos os* diretórios, incluindo os serviços de domínio do Active Directory do Windows Server e o Azure Active Directory. Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.

4. Serviços de gerenciamento de acesso onde podem existir entradas para os dispositivos. Remova as entradas de cada dispositivo de *todos os* serviços de gerenciamento, incluindo o Microsoft Endpoint Configuration Manager, o Microsoft Intune e o Windows AutoPilot. Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.

Agora você pode prosseguir para [registrar dispositivos](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Método de script do PowerShell manual

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Sejam `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Sejam `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Mesclar os dados de hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Método de unidade flash

1. Em um dispositivo diferente daquele que você está registrando, insira uma unidade USB.
2. Abra um prompt do PowerShell com direitos administrativos.
3. Sejam `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Ative o dispositivo que você está registrando, mas *não inicie a experiência de instalação*. Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.
5. Insira a unidade USB e, em seguida, pressione SHIFT + F10.
6. Abra um prompt do PowerShell com direitos administrativos e, em seguida, execute `cd <pathToUsb>` .
7. Sejam `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Sejam `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Remova a unidade USB e desligue o dispositivo executando `shutdown -s -t 0`
10. [Mesclar os dados de hash.](#merge-hash-data)

>[!IMPORTANT]
>Não ligue o dispositivo que você está registrando novamente até concluir o registro. 



### <a name="merge-hash-data"></a>Mesclar dados de hash

Se você coletou os dados de hash de hardware pelos métodos manuais do PowerShell ou unidade flash, agora precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro. Veja um exemplo de script do PowerShell para facilitar:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Com os dados de hash mesclados em um arquivo CSV, agora você pode prosseguir para [registrar os dispositivos](#register-devices-by-using-the-admin-portal).


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos usando o portal de administração

No [portal de administração](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecione **dispositivos** no painel de navegação esquerdo. Selecione **+ registrar dispositivos**; o funcionamento é aberto:

[![Entrada após selecionar registrar dispositivos, listando dispositivos com colunas para usuários atribuídos, número de série, status, data do último-observado e idade](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estas etapas:

1. Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.

1. Selecione **registrar dispositivos**. O sistema adicionará os dispositivos à sua lista de dispositivos na **folha de dispositivos**, marcada como **AutopilotRegistrationRequested**. O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário comece a usar o.


Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** . Os Estados possíveis relatados incluem:

| Estado | Descrição |
|---------------|-------------|
| AutopilotRegistrationRequested | O registro ainda não foi feito. Verifique novamente mais tarde. |
| Falha no registro | Não foi possível concluir o registro. Consulte [Solucionando problemas de registro de dispositivo](#troubleshooting-device-registration) para obter mais informações. |
| Pronto para o usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário. A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos. |
| Ativo | O dispositivo foi entregue ao usuário e foi registrado com seu locatário. Isso também indica que eles estão usando o dispositivo regularmente. |
| Inativa | O dispositivo foi entregue ao usuário e foi registrado com seu locatário. No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  | 

#### <a name="troubleshooting-device-registration"></a>Solucionando problemas de registro do dispositivo

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido. Confirme esses valores com seu fornecedor de dispositivos. |
| Hash de hardware inválido | O hash de hardware fornecido para este dispositivo não foi formatado corretamente. Verifique novamente o hash de hardware e envie novamente. |
| Dispositivo já registrado | Este dispositivo já está registrado na sua organização. Nenhuma ação adicional é necessária. |
| Dispositivo solicitado por outra organização | Este dispositivo já foi reivindicado por outra organização. Consulte seu fornecedor de dispositivos. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Entre em contato com o suporte e forneça a ID da solicitação: <requestId> |

### <a name="check-the-image"></a>Verificar a imagem

Se o seu dispositivo vier de um fornecedor de parceiros de área de trabalho gerenciada da Microsoft, a imagem deve estar correta.

Você também poderá aplicar a imagem sozinho, se preferir. Para começar, entre em contato com o representante da Microsoft com o qual você está trabalhando e forneça o local e as etapas para a aplicação da imagem.

### <a name="deliver-the-device"></a>Entregar o dispositivo

> [!IMPORTANT]
> Antes de entregar o dispositivo ao usuário, verifique se você obteve e aplicou as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.

Se todas as licenças forem aplicadas, você poderá preparar [seus usuários para usar dispositivos](get-started-devices.md)e o usuário poderá iniciar o dispositivo e prosseguir com a experiência de instalação do Windows.









