---
title: Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento.
keywords: exportação de dados brutos, API de streaming, API, Hubs de Eventos, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 656387e60bac90c7e9de4852779948dabce0efe3
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029652"
---
# <a name="configure-microsoft-365-defender-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para sua conta de Armazenamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de começar

1. Crie uma [conta de armazenamento](/azure/storage/common/storage-account-overview) em seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.Insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos

1. Faça logon no portal do Microsoft 365 Defender ( ) como <https://security.microsoft.com> um * Administrador **Global** _ ou _* Administrador _de Segurança_**.

2. Vá para **Configurações** da API de Streaming do \> **Microsoft 365** \> Defender. Para ir diretamente para a página **api de streaming,** use <https://security.microsoft.com/settings/mtp_settings/raw_data_export> .

3. Clique em **Adicionar**.

4. No **flyout Adicionar novas configurações de API de Streaming exibidas,** configure as seguintes configurações:
   1. **Nome**: escolha um nome para suas novas configurações.
   2. Selecione **Encaminhar eventos para o Armazenamento do Azure.**
   3. Na caixa **ID do Recurso** de Conta de Armazenamento exibida, digite sua **ID** de Recurso de Conta de Armazenamento . Para obter sua **ID** de Recurso de Conta de Armazenamento, abra o portal do Azure em , clique em Contas de armazenamento vá para a guia Propriedades copiar o texto em <https://portal.azure.com>  \> \> **ID** de Recurso da Conta de Armazenamento .

      ![Imagem da ID do recurso do hub de eventos1](../defender-endpoint/images/storage-account-resource-id.png)

   4. De volta ao **flyout Adicionar novas configurações de API de Streaming,** escolha **os tipos de** evento que você deseja transmitir.

   Quando terminar, clique em **Enviar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>O esquema dos eventos na conta de armazenamento

- Um contêiner blob será criado para cada tipo de evento:

  ![Imagem da ID do recurso do hub de eventos2](../defender-endpoint/images/storage-account-event-schema.png)

- O esquema de cada linha em um blob é o seguinte JSON:

  ```JSON
  {
          "time": "<The time Microsoft 365 Defender received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <Microsoft 365 Defender Advanced Hunting event as Json> }
  }
  ```

- Cada blob contém várias linhas.

- Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".

- Para obter mais informações sobre o esquema dos eventos do Microsoft 365 Defender, consulte [Advanced Hunting overview](../defender/advanced-hunting-overview.md).

## <a name="data-types-mapping"></a>Mapeamento de tipos de dados

Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:

1. Faça logoff no portal do Microsoft 365 Defender ( ) e <https://security.microsoft.com> vá para **Hunting** \> **Advanced hunting**. Para ir diretamente para a **página De busca** avançada, use <security.microsoft.com/advanced-hunting>.

2. Na **guia Consulta,** execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento:

   ```text
   {EventType}
   | getschema
   | project ColumnName, ColumnType
   ```

- Veja um exemplo para o evento Informações do Dispositivo:

  ![Imagem da ID do recurso do hub de eventos3](../defender-endpoint/images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da Busca Avançada](../defender/advanced-hunting-overview.md)
- [Microsoft 365 Defender Streaming API](streaming-api.md)
- [Transmitir eventos do Microsoft 365 Defender para sua conta de armazenamento do Azure](streaming-api-storage.md)
- [Documentação da Conta de Armazenamento do Azure](/azure/storage/common/storage-account-overview)
