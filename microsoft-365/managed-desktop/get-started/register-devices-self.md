---
title: Registre novos dispositivos por conta própria
description: Registre os dispositivos por conta própria para que eles possam ser gerenciados pela Área de Trabalho Gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840676"
---
# <a name="register-new-devices-yourself"></a>Registre novos dispositivos por conta própria

A Área de Trabalho Gerenciada da Microsoft pode trabalhar com dispositivos novos ou você pode reutilizar dispositivos que talvez já tenha (o que exigirá que você os reimage). Você pode registrar dispositivos com a Área de Trabalho Gerenciada da Microsoft no portal do Microsoft Endpoint Manager.

> [!NOTE]
> Trabalhando com um parceiro para obter dispositivos? Se sim, você não precisa se preocupar em obter os hashes de hardware; eles cuidarão disso para você. Certifique-se de que seu parceiro estabeleça uma relação com você no [Partner Center.](https://partner.microsoft.com/dashboard) Seu parceiro pode saber mais na [ajuda do Partner Center.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Depois que essa relação for estabelecida, seu parceiro simplesmente registrará dispositivos em seu nome– nenhuma outra ação é necessária. Se você quiser ver os detalhes ou seu parceiro tiver dúvidas, consulte Etapas para [parceiros registrar dispositivos.](register-devices-partner.md) Depois que os dispositivos são registrados, você pode prosseguir com a verificação [da imagem](#check-the-image) e a entrega [dos dispositivos](#deliver-the-device) para seus usuários.

## <a name="prepare-to-register-brand-new-devices"></a>Preparar-se para registrar dispositivos novos


Depois de ter os novos dispositivos em mãos, você seguirá estas etapas:

1. [Obtenha o hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Mesclar os dados de hash](#merge-hash-data)
3. [Registre os dispositivos na Área de Trabalho Gerenciada da Microsoft.](#register-devices-by-using-the-admin-portal)
4. [Verifique se a imagem está correta.](#check-the-image)
5. [Entregar o dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obter o hash de hardware

A Área de Trabalho Gerenciada da Microsoft identifica cada dispositivo exclusivamente referenciando seu hash de hardware. Você tem três opções para obter essas informações:

- Peça ao fornecedor do OEM o arquivo de registro do AutoPilot, que incluirá os hashes de hardware.
- Execute um [script do Windows PowerShell](#powershell-script-method) em cada dispositivo e colete os resultados em um arquivo.
- Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e colete [os hashes em uma unidade flash removível.](#flash-drive-method)

#### <a name="powershell-script-method"></a>Método de script do PowerShell

Você pode usar o [ scriptGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell no site da Galeria do PowerShell. Para obter mais informações sobre a identificação do dispositivo e o hash de hardware, consulte [Adicionando dispositivos ao Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Executar `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Executar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Execute `powershell -ExecutionPolicy restricted` para impedir a execução de scripts irrestritos subsequentes.


#### <a name="flash-drive-method"></a>Método de unidade flash

1. Em um dispositivo diferente do que você está registrando, insira uma unidade USB.
2. Abra um prompt do PowerShell com direitos administrativos.
3. Executar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Ligue o dispositivo que você está registrando, mas *não inicie a experiência de instalação.* Se você iniciar acidentalmente a experiência de instalação, terá que redefinir ou reimage o dispositivo.
5. Insira a unidade USB e pressione SHIFT + F10.
6. Abra um prompt do PowerShell com direitos administrativos e `cd <pathToUsb>` execute.
7. Executar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Executar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Remova a unidade USB e desligue o dispositivo executando `shutdown -s -t 0`

>[!IMPORTANT]
>Não a power on the device you are registering again until you've completed registration for it. 


### <a name="merge-hash-data"></a>Mesclar dados de hash

Você precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro. Veja um exemplo de script do PowerShell para facilitar:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos usando o Portal de Administração

No [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/)selecione **Dispositivos** no painel de navegação esquerdo. Procure a seção Área de Trabalho Gerenciada da Microsoft do menu e selecione **Dispositivos.** No espaço de trabalho Dispositivos de Área de Trabalho Gerenciada da Microsoft, Selecione **+ Registrar dispositivos**, que abre um sub-in para registrar novos dispositivos.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estas etapas:

1. Em **Carregamento de arquivo,** forneça um caminho para o arquivo CSV que você criou anteriormente.
3. Selecione **Registrar dispositivos.** O sistema adicionará os dispositivos à sua lista de dispositivos **em** dispositivos , marcado como **Registro Pendente**. O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo é a primeira vez que aparece como Pronto para o usuário, o que significa que ele está pronto e aguardando que um usuário comece a usá-lo. 


Você pode monitorar o progresso do registro do dispositivo na página principal. Os possíveis estados relatados incluem:

| Estado | Descrição |
|---------------|-------------|
| Registro Pendente | O registro ainda não foi feito. Verifique novamente mais tarde. |
| Falha no registro | Não foi possível concluir o registro. Consulte Solução [de problemas de registro de dispositivos](#troubleshooting-device-registration) para obter mais informações. |
| Pronto para o usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário. A Área de Trabalho Gerenciada da Microsoft os orientará durante a configuração pela primeira vez, portanto, não é necessário fazer outras preparações. |
| Ativo | O dispositivo foi entregue ao usuário e ele se registrou em seu locatário. Esse estado também indica que eles estão usando regularmente o dispositivo. |
| Inativo | O dispositivo foi entregue ao usuário e ele se registrou em seu locatário. No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  | 

#### <a name="troubleshooting-device-registration"></a>Solução de problemas de registro de dispositivos

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar esse dispositivo porque não foi possível encontrar uma combinação para o fabricante, o modelo ou o número de série fornecido. Confirme esses valores com o fornecedor do dispositivo. |
| Hash de hardware não válido | O hash de hardware fornecido para esse dispositivo não foi formatado corretamente. Verifique o hash de hardware e, em seguida, resubmita. |
| Dispositivo já registrado | Esse dispositivo já está registrado em sua organização. Nenhuma outra ação é necessária. |
| Dispositivo reivindicado por outra organização | Esse dispositivo já foi reivindicado por outra organização. Verifique com o fornecedor do dispositivo. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Entre em contato com o suporte e forneça a ID da solicitação: <requestId> |

### <a name="check-the-image"></a>Verificar a imagem

Se o dispositivo tiver vindo de um fornecedor de parceiro da Área de Trabalho Gerenciada da Microsoft, a imagem deverá estar correta.

Você também pode aplicar a imagem por conta própria, se preferir. Para começar, entre em contato com o representante da Microsoft com quem você está trabalhando e ele fornecerá o local e as etapas para aplicar a imagem.

### <a name="deliver-the-device"></a>Entregar o dispositivo

> [!IMPORTANT]
> Antes de entregar o dispositivo ao usuário, certifique-se de ter obtido e aplicado as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.

Se todas as licenças são [](get-started-devices.md)aplicadas, você pode preparar seus usuários para usar dispositivos e, em seguida, o usuário pode iniciar o dispositivo e continuar com a experiência de configuração do Windows.





