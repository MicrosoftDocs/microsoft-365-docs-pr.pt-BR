---
title: Registrar dispositivos no Microsoft Managed desktop para parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: d743092fdd309c1afd748afa7523f0cc0c6a2fd0
ms.sourcegitcommit: cf77e4bf69e6ae144563f1e764ea3437ed6fc836
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33295877"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a>Registrar dispositivos no Microsoft Managed desktop para parceiros


Este tópico descreve as etapas dos parceiros a serem seguidas para registrar dispositivos. O processo de registro de seus próprios dispositivos está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).



## <a name="prepare-for-registration"></a>Preparar para o registro 
Antes de concluir o registro de um cliente, primeiro você deve estabelecer uma relação com eles no [Partner Center](https://partner.microsoft.com/dashboard). Saiba mais na [ajuda da central de parceiros](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).

Para concluir o registro do cliente, primeiro crie um arquivo CSV.

>[!NOTE]
>Para sua conveniência, é possível baixar um [modelo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) para esta *versão de parceiro* do arquivo CSV.

O arquivo precisa incluir exatamente os **mesmos títulos de coluna** do exemplo um (fabricante, modelo, etc.), mas seus próprios dados para as outras linhas. Se você usar o modelo, abra-o em uma ferramenta de edição de texto, como o bloco de notas, e considere a possibilidade de deixar todos os dados na linha 1 apenas inserindo dados nas linhas 2 e abaixo. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,
  
  
  ```


>[!NOTE]
>Este formato é somente para o processo de parceiro. O processo de auto-registro está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).

>[!IMPORTANT]
>Esses valores devem corresponder exatamente aos valores do fabricante do SMBIOS. Você também deve incluir o *hash de hardware* na primeira linha (mas nenhum valor para ela na segunda linha) a vírgula à direita após o valor de número de *série* na segunda linha.

- Fabricante do dispositivo (exemplo: SpiralOrbit) 
- Modelo de dispositivo (exemplo: ContosoABC)
- Número de série do dispositivo

## <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos usando o portal do Azure

O registro usando o portal do Azure é o mesmo que o de autoatendimento, exceto pelo fato de você acessar o portal de forma diferente. Siga estas etapas:

1. Navegue até a [central de parceiros](https://partner.microsoft.com/dashboard)
2. Selecione **clientes**.
3. Selecione o cliente que você deseja gerenciar.
4. Selecione **Administração de serviço**.
5. Selecione o **Intune**.
6. Procure "MMD" na caixa de pesquisa superior do portal do Azure.
7. Selecione **dispositivos**.
8. Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.
9. Opcionalmente, você pode adicionar uma ID de **pedido** ou de **compra** para seus próprios fins de controle. Não há requisitos de formato para esses valores.
10. Selecione **registrar dispositivos**. O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**. O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário final comece a usá-lo.


Você pode monitorar o progresso do registro de dispositivo na página principal **de dispositivos de área de trabalho gerenciados da Microsoft** . Os Estados possíveis relatados incluem:

| Estado | Descrição |
|---------------|-------------|
| Registro pendente | O registro ainda não foi feito. Verifique novamente mais tarde. |
| Falha no registro | Não foi possível concluir o registro. Consulte [solução de problemas](register-devices-self.md#troubleshooting) para obter mais informações. |
| Pronto para o usuário | O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário final. A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos. |
| Ativo | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. Isso também indica que eles estão usando o dispositivo regularmente. |
| Inativa | O dispositivo foi entregue ao usuário final e foi registrado com seu locatário. No enTanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).  |

## <a name="register-devices-by-using-an-api"></a>Registrar dispositivos usando uma API

O registro por API é o mesmo que autoatendimento, exceto pelo fato de que a propriedade de hash de hardware do conjunto de dispositivos é opcional, conforme descrito na seção CSV. 

## <a name="troubleshooting"></a>Solução de problemas

| Mensagem de erro | Detalhes |
|---------------|-------------|
| Dispositivo não encontrado | Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido. Confirme esses valores com seu fornecedor de dispositivos. |
| Dispositivo não encontrado | Não foi possível cancelar o registro deste dispositivo porque ele não existe em sua organização. Nenhuma ação adicional é necessária. |
| Hash de hardware inválido | O hash de hardware fornecido para este dispositivo não foi formatado corretamente. Verifique novamente o hash de hardware e envie novamente. |
| Dispositivo já registrado | Este dispositivo já está registrado na sua organização. Nenhuma ação adicional é necessária. |
| Dispositivo solicitado por outra organização | Este dispositivo já foi reivindicado por outra organização. Consulte seu fornecedor de dispositivos. |
| Erro inesperado | Sua solicitação não pôde ser processada automaticamente. Entre em contato<support link>com o suporte () e forneça a ID da solicitação:<requestId> |