---
title: Registrar dispositivos no Microsoft Managed desktop sozinho
description: Registre os dispositivos de modo que eles possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857294"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Registrar dispositivos na área de trabalho gerenciada da Microsoft

>[!NOTE]
>Este tópico descreve as etapas para você registrar dispositivos por conta própria. O processo para parceiros está documentado em [registrar dispositivos no Microsoft Managed desktop para parceiros](register-devices-partner.md).

A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente). Você pode registrar dispositivos usando a área de trabalho gerenciada da Microsoft no portal do Azure ou ganhar flexibilidade usando uma API.

## <a name="prepare-to-register-devices"></a>Preparar para registrar dispositivos

Se você ainda não tiver obtido os dispositivos que deseja usar, verifique os [dispositivos de área de trabalho gerenciada da Microsoft](../service-description/device-list.md) e trabalhe com um parceiro de dispositivo para adquirir dispositivos compatíveis.

Se você estiver trabalhando com dispositivos totalmente novos ou reutilizar os existentes, para registrá-los com a área de trabalho gerenciada da Microsoft, será necessário preparar um **arquivo separado por vírgula (CSV)**. Esse arquivo deve incluir as seguintes informações para cada dispositivo:

>[!NOTE]
>Este formato é somente para registro de autoatendimento. O formato que os parceiros devem usar está documentado em [registrar dispositivos no Microsoft Managed desktop para parceiros](register-devices-partner.md).

Esses valores são usados para fins de exibição e não precisam corresponder as propriedades do dispositivo exatamente.
- Fabricante do dispositivo (exemplo: SpiralOrbit) 
- Modelo de dispositivo (exemplo: ContosoABC)
- Número de série do dispositivo

O hash de hardware deve ser uma correspondência exata.
- Hash de hardware

Para obter o hash de hardware, você pode solicitar ajuda do seu OEM ou parceiro ou seguir estas etapas para cada dispositivo:

1.  Abra um prompt do PowerShell com direitos administrativos.
2.  Sejam`Install-Script -Name Get-MMDRegistrationInfo`
3.  Sejam`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`


Como alternativa, você pode seguir estas etapas em um dispositivo novo (antes de passar pelo OOBE pela primeira vez):

1. Em um dispositivo diferente, insira uma unidade USB.
2. Abra um prompt do PowerShell com direitos administrativos.
3. Sejam`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Ative o dispositivo de destino, mas não inicie a experiência de instalação. Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.
5. Insira a unidade USB e, em seguida, pressione SHIFT + F10.
6. Abra um prompt do PowerShell com direitos administrativos e, em `cd <pathToUsb>`seguida, execute.
7. Sejam`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Sejam`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
3. Remova a unidade USB e desligue o dispositivo executando`shutdown -s -t 0`

>[!IMPORTANT]
>Não ligue o dispositivo de destino novamente até concluir o registro. 

>[!NOTE]
>Para sua conveniência, é possível baixar um [modelo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para esse arquivo CSV.

O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas. Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Se você esquecer de alterar qualquer um dos dados de exemplo, o registro falhará.   


## <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos usando o portal do Azure

No [portal do Azure](https://aka.ms/mmdportal)de área de trabalho gerenciada da Microsoft, selecione **dispositivos** no painel de navegação esquerdo. Selecione **+ registrar dispositivos**; o funcionamento é aberto:

[![Surgir após selecionar registrar dispositivos](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


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
| Falha no registro | Não foi possível concluir o registro. Consulte [solução de problemas](register-devices-self.md#troubleshooting) para obter mais informações. |
| Pronto para o usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final. A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos. |
| Ativo | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. Isso também indica que eles estão usando o dispositivo regularmente. |
| Inativa | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  | 


## <a name="register-devices-by-using-an-api"></a>Registrar dispositivos usando uma API

Uma API REST está disponível para permitir maior flexibilidade e repetição com registros de dispositivo separados frequentes. Atualmente, para usar a API, peça ajuda ao seu contato da Microsoft para participar de uma prévia desse recurso.



## <a name="troubleshooting"></a>Solução de problemas

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido. Confirme esses valores com seu fornecedor de dispositivos. |
| Dispositivo não encontrado | Não foi possível cancelar o registro deste dispositivo porque ele não existe em sua organização. Nenhuma ação adicional é necessária. |
| Hash de hardware inválido | O hash de hardware fornecido para este dispositivo não foi formatado corretamente. Verifique novamente o hash de hardware e envie novamente. |
| Dispositivo já registrado | Este dispositivo já está registrado na sua organização. Nenhuma ação adicional é necessária. |
| Dispositivo solicitado por outra organização | Este dispositivo já foi reivindicado por outra organização. Consulte seu fornecedor de dispositivos. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Entre em contato com o suporte e forneça a ID da solicitação:<requestId> |




