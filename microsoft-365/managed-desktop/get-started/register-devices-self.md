---
title: Registre novos dispositivos por conta própria
description: Registre os dispositivos de modo que eles possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: e433b10b66b5e4f061227eae7e944c7fd19e2260
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289752"
---
# <a name="register-new-devices-yourself"></a>Registre novos dispositivos por conta própria

A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente). Você pode registrar dispositivos usando o portal de administração de área de trabalho gerenciada da Microsoft.

> [!NOTE]
> Trabalhar com um parceiro para obter dispositivos? Em caso afirmativo, você não precisa se preocupar em obter os hashes de hardware; Eles cuidarão disso para você. Certifique-se de que seu parceiro estabelece uma relação com você no [Partner Center](https://partner.microsoft.com/dashboard). Seu parceiro pode saber mais na [ajuda da central de parceiros](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Depois que esse relacionamento for estabelecido, o seu parceiro simplesmente registrará dispositivos em seu nome, e nenhuma ação será necessária. Se você quiser ver os detalhes ou se o seu parceiro tiver dúvidas, confira [as etapas dos parceiros para registrar dispositivos](register-devices-partner.md). Depois que os dispositivos são registrados, você pode prosseguir com [a verificação da imagem](#check-the-image) e de [fornecer os dispositivos](#deliver-the-device) aos seus usuários.

## <a name="prepare-to-register-brand-new-devices"></a>Preparar-se para registrar dispositivos novos


Após ter os novos dispositivos em mãos, siga estas etapas:

1. [Obtenha o hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Mesclar os dados de hash](#merge-hash-data)
3. [Registre os dispositivos na área de trabalho gerenciada da Microsoft](#register-devices-by-using-the-admin-portal).
4. [Verifique se a imagem está correta.](#check-the-image)
5. [Entregar o dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obter o hash de hardware

A área de trabalho gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência a seu hash de hardware. Você tem três opções para obter essas informações:

- Pergunte ao seu fornecedor de OEM o arquivo de registro do piloto automático, que inclui os hashes de hardware.
- Executar um [script do Windows PowerShell](#powershell-script-method) em cada dispositivo e coletar os resultados em um arquivo.
- Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e [colete os hashes em uma unidade flash removível](#flash-drive-method).

#### <a name="powershell-script-method"></a>Método de script do PowerShell

Você pode usar o script [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell no site da galeria do PowerShell. Para obter mais informações sobre a identificação de dispositivo e o hash de hardware, consulte [adicionando dispositivos ao Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Sejam `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Sejam `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`

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

>[!IMPORTANT]
>Não ligue o dispositivo que você está registrando novamente até concluir o registro. 


### <a name="merge-hash-data"></a>Mesclar dados de hash

Você precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro. Veja um exemplo de script do PowerShell para facilitar:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos usando o portal de administração

No [portal de administração](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecione **dispositivos** no painel de navegação esquerdo. Selecione **+ registrar dispositivos**; o funcionamento é aberto:

[![Entrada após selecionar registrar dispositivos, listando dispositivos com colunas para usuários atribuídos, número de série, status, data do último-observado e idade](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estas etapas:

1. Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.
3. Selecione **registrar dispositivos**. O sistema adicionará os dispositivos à sua lista de dispositivos na **folha de dispositivos**, marcada como **AutopilotRegistrationRequested**. O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário comece a usar o.


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






