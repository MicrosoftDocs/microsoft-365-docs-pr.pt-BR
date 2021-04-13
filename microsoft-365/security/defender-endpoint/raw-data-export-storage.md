---
title: Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de Armazenamento
description: Saiba como configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua conta de Armazenamento.
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
ms.openlocfilehash: 19fe0c9c3dc6f2e4226a4aa9a6cd983bc95bae3a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688784"
---
# <a name="configure-microsoft-defender-for-endpoint-to-stream-advanced-hunting-events-to-your-storage-account"></a>Configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para sua conta de Armazenamento

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="before-you-begin"></a>Antes de começar:

1. Crie uma [conta de armazenamento](https://docs.microsoft.com/azure/storage/common/storage-account-overview) em seu locatário.

2. Faça logoff no locatário do [Azure,](https://ms.portal.azure.com/)acesse Assinaturas > Sua assinatura > Provedores de Recursos **> Registrar no Microsoft.insights**.

## <a name="enable-raw-data-streaming"></a>Habilitar o streaming de dados brutos:

1. Faça logon [no portal do Microsoft Defender para Ponto de Extremidade](https://securitycenter.windows.com) como um * Administrador **Global** _ ou _* Administrador _de Segurança_**.

2. Vá para [a página Configurações de exportação de dados](https://securitycenter.windows.com/interoperability/dataexport) no Centro de Segurança do Microsoft Defender.

3. Clique em **Adicionar configurações de exportação de dados.**

4. Escolha um nome para suas novas configurações.

5. Escolha **Encaminhar eventos para o Armazenamento do Azure.**

6. Digite sua **ID de Recurso de Conta de Armazenamento**. Para obter a **ID** do Recurso de Conta de Armazenamento, vá para a página Conta de Armazenamento na guia propriedades do portal do [Azure](https://ms.portal.azure.com/) > > para copiar o texto em **ID** do recurso da conta de armazenamento:

   ![Imagem da ID do recurso do hub de eventos1](images/storage-account-resource-id.png)

7. Escolha os eventos que deseja transmitir e clique em **Salvar**.

## <a name="the-schema-of-the-events-in-the-storage-account"></a>O esquema dos eventos na conta de armazenamento:

- Um contêiner blob será criado para cada tipo de evento: 

  ![Imagem da ID do recurso do hub de eventos2](images/storage-account-event-schema.png)

- O esquema de cada linha em um blob é o seguinte JSON: 

  ```
  {
          "time": "<The time WDATP received the event>"
          "tenantId": "<Your tenant ID>"
          "category": "<The Advanced Hunting table name with 'AdvancedHunting-' prefix>"
          "properties": { <WDATP Advanced Hunting event as Json> }
  }               
  ```

- Cada blob contém várias linhas.

- Cada linha contém o nome do evento, a hora em que o Defender for Endpoint recebeu o evento, o locatário que ele pertence (você só receberá eventos do seu locatário) e o evento no formato JSON em uma propriedade chamada "properties".

- Para obter mais informações sobre o esquema do Microsoft Defender para eventos do Ponto de Extremidade, consulte [Visão geral de Busca Avançada](advanced-hunting-overview.md).

- Em Busca Avançada, a tabela **DeviceInfo** tem uma coluna chamada **MachineGroup** que contém o grupo do dispositivo. Aqui todos os eventos também serão decorados com esta coluna. Confira [Grupos de Dispositivos](machine-groups.md) para obter mais informações.

## <a name="data-types-mapping"></a>Mapeamento de tipos de dados:

Para obter os tipos de dados para nossas propriedades de eventos, faça o seguinte:

1. Faça logoff no [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com) e acesse a página Busca [Avançada.](https://securitycenter.windows.com/hunting-package)

2. Execute a seguinte consulta para obter o mapeamento de tipos de dados para cada evento: 

   ```
   {EventType}
   | getschema
   | project ColumnName, ColumnType 
   ```

- Veja um exemplo para o evento Informações do Dispositivo: 

  ![Imagem da ID do recurso do hub de eventos3](images/machine-info-datatype-example.png)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [API de streaming do Microsoft Defender para Ponto de Extremidade](raw-data-export.md)
- [Transmitir eventos do Microsoft Defender para Ponto de Extremidade para sua conta de armazenamento do Azure](raw-data-export-storage.md)
- [Documentação da Conta de Armazenamento do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
