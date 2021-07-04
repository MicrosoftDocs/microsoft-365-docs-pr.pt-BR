---
title: Registre novos dispositivos por conta própria
description: Registre os dispositivos por você mesmo para que eles possam ser gerenciados por Área de Trabalho Gerenciada da Microsoft
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: a66ad53faf1b38c3db4ab4446dbc1d175fbd99e4
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289530"
---
# <a name="register-new-devices-yourself"></a>Registre novos dispositivos por conta própria

Área de Trabalho Gerenciada da Microsoft pode trabalhar com dispositivos novos ou você pode reutilizar dispositivos que você já tenha (o que exigirá que você os reimage). Você pode registrar dispositivos com Área de Trabalho Gerenciada da Microsoft no portal Microsoft Endpoint Manager portal.

> [!NOTE]
> Trabalhando com um parceiro para obter dispositivos? Se sim, você não precisa se preocupar em obter os hashes de hardware; Eles cuidarão disso para você. Certifique-se de que seu parceiro estabeleça uma relação com você no [Partner Center](https://partner.microsoft.com/dashboard). Seu parceiro pode saber mais na ajuda [do Partner Center.](/partner-center/request-a-relationship-with-a-customer) Depois que essa relação for estabelecida, seu parceiro simplesmente registrará dispositivos em seu nome – nenhuma ação mais necessária de você. Se você quiser ver os detalhes ou seu parceiro tiver dúvidas, consulte [Etapas para parceiros registrar dispositivos](register-devices-partner.md). Depois que os dispositivos são registrados, você pode continuar verificando [a imagem](#check-the-image) e [entregando os dispositivos](#deliver-the-device) para seus usuários.



## <a name="prepare-to-register-brand-new-devices"></a>Preparar para registrar dispositivos novos


Depois de ter os novos dispositivos em mãos, você seguirá estas etapas:

1. [Obtenha o hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Mesclar os dados de hash](#merge-hash-data)
3. [Registre os dispositivos em Área de Trabalho Gerenciada da Microsoft](#register-devices-by-using-the-admin-portal).
4. [Verifique se a imagem está correta.](#check-the-image)
5. [Entregar o dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obter o hash de hardware

Área de Trabalho Gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência ao hash de hardware. Você tem três opções para obter essas informações:

- Peça ao fornecedor OEM para o arquivo de registro do AutoPilot, que incluirá os hashes de hardware.
- Execute um [Windows PowerShell script em](#powershell-script-method) cada dispositivo e colete os resultados em um arquivo.
- Inicie cada dispositivo, mas não conclua a experiência de instalação Windows e colete os hashes em uma [unidade flash removível.](#flash-drive-method)

#### <a name="powershell-script-method"></a>Método de script do PowerShell

Você pode usar o [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) do PowerShell no site da Galeria do PowerShell. Para obter mais informações sobre a identificação do dispositivo e o hash de hardware, consulte [Adding devices to Windows Autopilot](/mem/autopilot/add-devices#device-identification).

1. Abra um prompt do PowerShell com direitos administrativos.
2. Executar `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Executar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. Execute `powershell -ExecutionPolicy restricted` para impedir a execução de scripts irrestritos subsequentes.

#### <a name="flash-drive-method"></a>Método de unidade flash

1. Em um dispositivo diferente do que você está registrando, insira uma unidade USB.
2. Abra um prompt do PowerShell com direitos administrativos.
3. Executar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. A turn on the device you are registering, *but do not start the setup experience*. Se você iniciar acidentalmente a experiência de instalação, você terá que redefinir ou reajustar o dispositivo.
5. Insira a unidade USB e pressione SHIFT + F10.
6. Abra um prompt do PowerShell com direitos administrativos e execute `cd <pathToUsb>` .
7. Executar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Executar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Remova a unidade USB e desligue o dispositivo executando `shutdown -s -t 0`

> [!IMPORTANT]
> Não a energia no dispositivo que você está registrando novamente até concluir o registro para ele. 

### <a name="merge-hash-data"></a>Mesclar dados de hash

Você precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro. Veja um exemplo de script do PowerShell para facilitar:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos usando o Portal de Administração

Em [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), selecione **Dispositivos** no painel de navegação esquerdo. Procure a seção Área de Trabalho Gerenciada da Microsoft do menu e selecione **Dispositivos**. No espaço de trabalho Área de Trabalho Gerenciada da Microsoft Dispositivos, Selecione **+ Registrar dispositivos**, que abre um fly-in para registrar novos dispositivos.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Execute estas etapas:

1. Em **Carregamento de arquivo,** forneça um caminho para o arquivo CSV que você criou anteriormente.
2. Selecione um [perfil de](../service-description/profiles.md) dispositivo no menu suspenso.
3. Selecione **Registrar dispositivos**. O sistema adicionará os dispositivos à sua lista de dispositivos em **Dispositivos**, marcados como **Registro Pendente**. O registro normalmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo será mostrar como **Pronto** para o usuário, o que significa que ele está pronto e aguardando que um usuário comece a usar.

> [!NOTE]
> Se você alterar manualmente a associação de grupo Azure Active Directory (AAD) de um dispositivo, ela será automaticamente reatribuida ao grupo para seu perfil de dispositivo e removida de todos os grupos conflitantes.

Você pode monitorar o andamento do registro do dispositivo na página principal. Os estados possíveis relatados incluem:

| Estado | Descrição |
|---------------|-------------|
| Registro Pendente | O registro ainda não foi feito. Volte mais tarde. |
| Falha no registro | O registro não pôde ser concluído. Consulte [Troubleshooting device registration para](#troubleshooting-device-registration) obter mais informações. |
| Pronto para usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário. Área de Trabalho Gerenciada da Microsoft os guiará durante a configuração da primeira vez, portanto, não há necessidade de você fazer outras preparações. |
| Ativo | O dispositivo foi entregue ao usuário e ele se registrou com seu locatário. Esse estado também indica que eles estão usando regularmente o dispositivo. |
| Inativo | O dispositivo foi entregue ao usuário e ele se registrou com seu locatário. No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  | 

#### <a name="troubleshooting-device-registration"></a>Solução de problemas de registro de dispositivo

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar esse dispositivo porque não foi possível encontrar uma combinação para o fabricante, modelo ou número de série fornecido. Confirme esses valores com o fornecedor do dispositivo. |
| Hash de hardware não válido | O hash de hardware fornecido para esse dispositivo não foi formatado corretamente. Verifique duas vezes o hash de hardware e, em seguida, reapresente. |
| Dispositivo já registrado | Esse dispositivo já está registrado em sua organização. Nenhuma ação mais necessária. |
| Dispositivo reivindicado por outra organização | Esse dispositivo já foi reivindicado por outra organização. Verifique com o fornecedor do dispositivo. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Contate o Suporte e forneça a ID da Solicitação: <requestId> |

### <a name="check-the-image"></a>Verificar a imagem

Se o dispositivo tiver vindo de um fornecedor Área de Trabalho Gerenciada da Microsoft parceiro, a imagem deverá estar correta.

Você também pode aplicar a imagem por conta própria, se preferir. Para começar, entre em contato com o representante da Microsoft com o que você está trabalhando e eles fornecerão o local e as etapas para aplicar a imagem.

### <a name="autopilot-group-tag"></a>Marca de grupo do piloto automático

Quando você usa o portal administrador para registrar dispositivos, atribuímos automaticamente a marca de grupo **Microsoft365Managed_Autopilot** Autopilot.
O serviço monitora todos os Área de Trabalho Gerenciada da Microsoft diariamente e atribui a marca de grupo a qualquer um que ainda não a tenha.

### <a name="deliver-the-device"></a>Entregar o dispositivo

> [!IMPORTANT]
> Antes de entregar o dispositivo ao usuário, certifique-se de ter obtido e aplicado as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.

Se todas as licenças são aplicadas, você pode preparar seus usuários para usar dispositivos [e,](get-started-devices.md)em seguida, o usuário pode iniciar o dispositivo e prosseguir com a experiência de instalação Windows configuração.
