---
title: Registrar dispositivos existentes sozinho
description: Registrar os dispositivos reutilizados que você já pode ter para que eles possam ser gerenciados pelo Microsoft Managed desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250441"
---
# <a name="register-existing-devices-yourself"></a>Registrar dispositivos existentes sozinho

>[!NOTE]
>Este tópico descreve as etapas para reutilizar os dispositivos que você já tem e registrá-los na área de trabalho gerenciada da Microsoft. Se você estiver trabalhando com dispositivos novos, siga as etapas em [registrar novos dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md) em seu lugar.

O processo para parceiros está documentado em [etapas para que os parceiros registrem dispositivos](register-devices-partner.md).

A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente). Você pode registrar dispositivos usando a área de trabalho gerenciada da Microsoft no portal do Azure.

## <a name="prepare-to-register-existing-devices"></a>Preparar-se para registrar dispositivos existentes


Para registrar dispositivos existentes, siga estas etapas:

1. [Obtenha o hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Mesclar os dados de hash](#merge-hash-data)
3. [Registre os dispositivos na área de trabalho gerenciada da Microsoft](#register-devices).
4. [Verifique se a imagem está correta.](#check-the-image)
5. [Entregar o dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obter o hash de hardware

A área de trabalho gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência a seu hash de hardware. Você tem quatro opções para obter essas informações de dispositivos que você já está usando:

- Pergunte ao seu fornecedor de OEM o arquivo de registro do piloto automático, que inclui os hashes de hardware.
- Criar um relatório personalizado no [Gerenciador de configurações](#configuration-manager).
- Executar um script do Windows PowerShell, usando o [Active Directory](#active-directory-powershell-script-method) ou [manualmente](#manual-powershell-script-method) em cada dispositivo, e coletar os resultados em um arquivo.
- Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e [colete os hashes em uma unidade flash removível](#flash-drive-method).

#### <a name="configuration-manager"></a>Configuration Manager

Você pode usar o Microsoft Endpoint Configuration Manager para coletar os hashes de hardware de dispositivos existentes que você deseja registrar com a área de trabalho gerenciada da Microsoft.

> [!IMPORTANT]
> Todos os dispositivos para os quais você deseja obter essas informações devem estar executando o Windows 10, versão 1703 ou posterior. Você também precisa de um dispositivo que seja um cliente do Configuration Manager conectado ao site do Configuration Manager (Branch atual). Você também precisa da função de sistema de site do ponto de relatório configurada em seu ambiente com o SQL Server Reporting Services habilitado. 

Se você atendeu a todos esses pré-requisitos, você está pronto para coletar as informações seguindo estas etapas:

1. No console do Gerenciador de configurações, selecione **monitoramento**. 
2. No espaço de trabalho monitoramento, expanda **relatórios**e selecione **relatórios**. 
3. Na guia **página inicial** , na seção **criar** , selecione **criar relatório** para abrir o assistente para criar relatório. 
4. Na página **informações** , defina estas configurações: 
    - **Nome:** Especifique um nome para o relatório. 
    - **Descrição:** Especifique uma descrição para o relatório. 
    - **Servidor:** Exibe o nome do servidor de relatório no qual você está criando o relatório. 
    - **Caminho:** Selecione **procurar** para especificar uma pasta na qual você deseja armazenar o relatório. 
5. Selecione **Avançar**. 
6. Na página **Resumo** , revise as configurações. Selecione **anterior** para alterar as configurações ou selecione **Avançar** para criar o relatório no Gerenciador de configurações. 
7. Na página **conclusão** , selecione **fechar** para sair do assistente e abrir o **Construtor de relatórios** para inserir as configurações de relatório. Insira sua conta de usuário e sua senha, se for solicitado e selecione **OK.** Se o construtor de relatórios não estiver instalado no dispositivo, você será solicitado a instalá-lo. Selecione **Executar para instalar o construtor de relatórios**, o que é necessário para modificar e criar relatórios. 


**No Microsoft Report Builder**, forneça a instrução SQL para o relatório e siga estas etapas:

1. No painel esquerdo, selecione **datadatasets**e clique com o botão direito do mouse para **Adicionar DataSet**.
2. Vá para a guia **consulta** e, em seguida, insira o nome como *DataSet0*. 
3. Selecione **usar um conjunto de um DataSet inserido em meu relatório**; O construtor de relatórios é aberto.
4. No **Construtor de relatórios**, selecione **fonte de dados:**. Selecione a fonte de dados padrão, que deve começar com "AutoGen". 
5. Escolha **tipo de consulta como texto**e, em seguida, insira esta consulta:




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. Navegue até a guia **campo** , os valores de wehre para o **nome do campo** e a origem do **campo** já devem estar preenchidos. Se não estiverem, selecione **Adicionar**e, em seguida, selecione **campo de consulta**. Insira o **nome do campo** e a **origem do campo**.
6. Repita o procedimento para cada um destes valores: 
    - Fabricantes 
    - Modelo 
    - Serial_Number 
    - HardwareHash
7. Selecione **OK**.

**Em seguida, defina a exibição do relatório e crie o relatório** seguindo estas etapas:

1. Selecionar **tabela ou matriz**; um novo assistente será aberto.
2. Em **escolher um conjunto de um**, selecione **escolher um conjunto de um existente neste relatório ou um conjunto de um compartilhado**.  
3. Selecione **DataSet0** (o padrão) e, em seguida, selecione **Avançar**.
4. Arraste o **fabricante**, o **modelo**e o **número de série** para a caixa grupos de **linhas** . Arraste **HardwareHash** para a caixa **valores** e selecione **Avançar**.
5. Desmarque as caixas de seleção **Mostrar Subtotais e totais gerais** e **expandir/recolher grupos**. Selecione **Avançar**.
6. Selecione **Concluir**.
7. Selecione **executar** para executar o relatório. Verifique se o relatório fornece as informações que você espera. Se necessário, selecione **design** para retornar ao modo de design para modificar o relatório.
8. Selecione **salvar** para salvar o relatório no servidor de relatório. Você pode executar o novo relatório no nó relatórios no espaço de trabalho de monitoramento. 

**Por fim, exporte o relatório e use-o para registrar dispositivos** seguindo estas etapas. (Você só precisará seguir as etapas 1 e 2 desta seção se tiver navegado após as etapas anteriores.):

1. No console do Gerenciador de configurações, selecione **monitoramento**.
2. Em **monitoramento**, expanda **relatórios**e selecione **relatórios**.
3. Localize o relatório usando o nome que você criou anteriormente.
4. Clique com o botão direito do mouse no relatório e selecione **executar**.
5. Na caixa de diálogo que é aberta, selecione **Exportar** e, em seguida, selecione **salvar como CSV**.
6. Esta versão do relatório extrai hashes de todos os dispositivos Windows 10 aos quais o Gerenciador de configuração se comunica. Você precisará filtrar os resultados apenas nos dispositivos que planeja registrar com a área de trabalho gerenciada da Microsoft.


> [!IMPORTANT]
> A consulta no Gerenciador de configurações não permite espaços em nomes de coluna exportados; é por isso que as etapas tinham que inserir "Serial_Number" e "HardwareHash". Agora que você tem o arquivo CSV exportado, você deve editar os cabeçalhos de relatório para ler o *número de série* e o *hash de hardware* , conforme mostrado aqui antes de prosseguir com o registro do dispositivo.

Agora você pode prosseguir para [registrar dispositivos usando o portal do Azure](#register-devices-by-using-the-azure-portal).


#### <a name="active-directory-powershell-script-method"></a>Método de script do PowerShell do Active Directory

Em um ambiente do Active Directory, você pode usar `Get-MMDRegistrationInfo` o cmdlet do PowerShell para coletar remotamente as informações de dispositivos nos grupos do Active Directory usando o WinRM. Você também pode usar o `Get-AD Computer` cmdlet e obter resultados filtrados para um determinado nome de modelo de hardware incluído no catálogo. Para fazer isso, primeiro confirme esses pré-requisitos e prossiga com as etapas:

- O WinRM está habilitado.
- Os dispositivos que você deseja registrar estão ativos na rede (ou seja, eles não são desconectados ou desativados).
- Verifique se você tem um parâmetro de credencial de domínio que tenha permissão para executar remotamente nos dispositivos.
- Verifique se o Firewall do Windows permite acesso ao WMI. Para fazer isso, siga estas etapas:
    1. Abra o painel de controle do **Windows Defender firewall** e selecione **permitir um aplicativo ou recurso por meio do Windows Defender firewall**.
    2. Encontre **Instrumentação de gerenciamento do Windows (WMI)** na lista, habilite para **privado e público**e, em seguida, selecione **OK**.

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Execute *um* destes scripts:
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. Acessar os diretórios em que pode haver entradas para os dispositivos. Remova as entradas de cada dispositivo de *todos os* diretórios, incluindo os serviços de domínio do Active Directory do Windows Server e o Azure Active Directory. Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.
4. Serviços de gerenciamento de acesso onde podem existir entradas para os dispositivos. Remova as entradas de cada dispositivo de *todos os* serviços de gerenciamento, incluindo o Microsoft Endpoint Configuration Manager, o Microsoft Intune e o Windows AutoPilot. Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.

Agora você pode prosseguir para [registrar dispositivos](#register-devices).

#### <a name="manual-powershell-script-method"></a>Método de script do PowerShell manual

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Sejam`Install-Script -Name Get-MMDRegistrationInfo`
3.  Sejam`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
4. [Mesclar os dados de hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Método de unidade flash

1. Em um dispositivo diferente daquele que você está registrando, insira uma unidade USB.
2. Abra um prompt do PowerShell com direitos administrativos.
3. Sejam`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Ative o dispositivo que você está registrando, mas *não inicie a experiência de instalação*. Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.
5. Insira a unidade USB e, em seguida, pressione SHIFT + F10.
6. Abra um prompt do PowerShell com direitos administrativos e, em `cd <pathToUsb>`seguida, execute.
7. Sejam`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Sejam`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Remova a unidade USB e desligue o dispositivo executando`shutdown -s -t 0`
10. [Mesclar os dados de hash.](#merge-hash-data)

>[!IMPORTANT]
>Não ligue o dispositivo que você está registrando novamente até concluir o registro. 



### <a name="merge-hash-data"></a>Mesclar dados de hash

Se você coletou os dados de hash de hardware pelos métodos manuais do PowerShell ou unidade flash, agora precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro. Veja um exemplo de script do PowerShell para facilitar:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

Com os dados de hash mesclados em um arquivo CSV, agora você pode prosseguir para [registrar os dispositivos](#register-devices).

### <a name="register-devices"></a>Registrar dispositivos

O arquivo CSV deve estar em um formato específico para o registro. Se você coletou os dados nas etapas anteriores, o arquivo já deve estar no formato correto; Se você obtiver o arquivo de um fornecedor, talvez seja necessário ajustar o formato.

>[!NOTE]
>Para sua conveniência, é possível baixar um [modelo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para esse arquivo CSV.

O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas. Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Se você esquecer de alterar qualquer um dos dados de exemplo, o registro falhará.

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos usando o portal do Azure

No [portal do Azure](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecione **dispositivos** no painel de navegação esquerdo. Selecione **+ registrar dispositivos**; o funcionamento é aberto:

[![Entrada após selecionar registrar dispositivos, listando dispositivos com colunas para usuários atribuídos, número de série, status, data do último-observado e idade](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Infelizmente, isso não é verdadeiro. Podemos remover esta anotação, mas deixá-la agora até que haja uma oportunidade de conversar sobre ela.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estas etapas:

1. Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.
2. Opcionalmente, você pode adicionar uma ID de **pedido** ou de **compra** para seus próprios fins de controle. Não há requisitos de formato para esses valores.
3. Selecione **registrar dispositivos**. O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**. O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário final comece a usá-lo.


Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** . Os Estados possíveis relatados incluem:

| Estado | Descrição |
|---------------|-------------|
| Registro pendente | O registro ainda não foi feito. Verifique novamente mais tarde. |
| Falha no registro | Não foi possível concluir o registro. Consulte [Solucionando problemas de registro de dispositivo](#troubleshooting-device-registration) para obter mais informações. |
| Pronto para o usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final. A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos. |
| Ativo | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. Isso também indica que eles estão usando o dispositivo regularmente. |
| Inativa | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  | 

#### <a name="troubleshooting-device-registration"></a>Solucionando problemas de registro do dispositivo

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido. Confirme esses valores com seu fornecedor de dispositivos. |
| Hash de hardware inválido | O hash de hardware fornecido para este dispositivo não foi formatado corretamente. Verifique novamente o hash de hardware e envie novamente. |
| Dispositivo já registrado | Este dispositivo já está registrado na sua organização. Nenhuma ação adicional é necessária. |
| Dispositivo solicitado por outra organização | Este dispositivo já foi reivindicado por outra organização. Consulte seu fornecedor de dispositivos. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Entre em contato com o suporte e forneça a ID da solicitação:<requestId> |

### <a name="check-the-image"></a>Verificar a imagem

Se o seu dispositivo vier de um fornecedor de parceiros de área de trabalho gerenciada da Microsoft, a imagem deve estar correta.

Você também poderá aplicar a imagem sozinho, se preferir. Para começar, entre em contato com o representante da Microsoft com o qual você está trabalhando e forneça o local e as etapas para a aplicação da imagem.

### <a name="deliver-the-device"></a>Entregar o dispositivo

> [!IMPORTANT]
> Antes de entregar o dispositivo ao usuário, verifique se você obteve e aplicou as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.

Se todas as licenças forem aplicadas, você poderá preparar [seus usuários para usar dispositivos](get-started-devices.md)e o usuário poderá iniciar o dispositivo e prosseguir com a experiência de instalação do Windows.









