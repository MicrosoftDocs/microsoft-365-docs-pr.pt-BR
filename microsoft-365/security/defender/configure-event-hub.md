---
title: Configurar seu Hub de Eventos
description: Saiba como configurar seu Hub de Eventos
keywords: hub de eventos, configurar, insights
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985515"
---
# <a name="configure-your-event-hub"></a>Configurar seu Hub de Eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Saiba como configurar o Hub de Eventos para que ele possa ingerir eventos de Microsoft 365 Defender.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>Configurar o Provedor de Recursos necessário na assinatura do Hub de Eventos


1. Entre no [portal do Azure](https://portal.azure.com).
1. Selecione Assinaturas { Selecione a assinatura que o hub de **eventos será implantado \> ***em***} \> Provedores de recursos**.
1. Verifique se o **Provedor Microsoft.Insights** está registrado. Caso contrário, registre-o.

![Imagem de provedores de recursos no Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Instalação Active Directory do Azure Registro de Aplicativo


>! [OBSERVAÇÃO] Você deve ter a função administrador ou Active Directory do Azure (AAD) deve ser definida para permitir que não-administradores registrem aplicativos. Você também deve ter uma função Proprietário ou Administrador de Acesso ao Usuário para atribuir uma função à entidade de serviço.  
>Para obter mais informações, consulte [Create an Azure AD app & service principal in the portal - plataforma de identidade da Microsoft \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Crie um novo registro (que cria inerentemente uma entidade de serviço) em Active Directory do Azure **registros do aplicativo Novo \> \> registro.**

1. Preencha o formulário apenas com o Nome (nenhum URI de redirecionamento é necessário).

    ![Imagem do registro de um aplicativo](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Imagem das informações de visão geral](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Crie um segredo clicando em Certificados & **segredos Novo segredo do \> cliente:**

    ![Imagem de certificados e segredos](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>Você não poderá acessar o segredo do cliente **novamente, portanto, certifique-se de salvá-lo.**

## <a name="setup-event-hub-namespace"></a>Namespace do Hub de Eventos de Instalação


1. Criar um Namespace do Hub de Eventos:

    Vá **para Hubs \>** de Eventos Adicionar e selecione a camada de preços, unidades de transferência e Inflação Automática (exige preços padrão e recursos) apropriados para a carga que você está esperando.  
    Para obter mais informações, consulte [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > Você pode usar um hub de eventos existente, mas a produtividade e o dimensionamento são definidos no nível do namespace, portanto, é recomendável colocar um hub de eventos em seu próprio namespace.

   ![Imagem do espaço de nome do Hub de Eventos](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. Você também precisará da ID de Recurso deste Namespace do Hub de Eventos. Vá para suas propriedades de namespace de hubs de eventos do \> Azure. Copie o texto em ID do Recurso e grave-o para uso durante a seção Configuração do M365 abaixo. 

    ![Imagem das propriedades](../../media/759498162a4e93cbf17c4130d704d164.png)

1. Depois que o Namespace do Hub de Eventos for criado, você precisará adicionar a Entidade de Serviço de Registro de Aplicativo como Leitor, Receptor de Dados de Hubs de Eventos do Azure e o usuário que fará logon no Microsoft 365 Defender como Colaborador (isso também pode ser feito no nível de Grupo de Recursos ou Assinatura).

    Isso é feito no Controle de Acesso para Namespace de Hubs de Eventos **\> (IAM) \> Adicionar** e verificar em **Atribuições de função**:

    ![Imagem do controle de acesso](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Hub de Eventos de Instalação


**Opção 1:**

Você pode criar um Hub de  Eventos em seu Namespace e todos os Tipos de Eventos (Tabelas) selecionados para exportar serão gravados neste **hub** de eventos.

**Opção 2:**

Em vez de exportar todos os Tipos de Eventos (Tabelas) para um Hub de Eventos, você pode exportar cada tabela para um Hub de Eventos diferente dentro do Namespace do Hub de Eventos (um Hub de Eventos por Tipo de Evento).  

Nesta opção, Microsoft 365 Defender criará Hubs de Eventos para você.  
>[!NOTE]
> Se você estiver usando um Namespace de Hub de Eventos que não faz parte de um Cluster de Hub de Eventos, você só poderá escolher até 10 Tipos de Eventos (Tabelas) para exportar em cada Export Configurações que você definir, devido a uma limitação do Azure de 10 Hubs de Eventos por namespace do Hub de Eventos. 

Por exemplo:

![Imagem do exemplo hub de eventos](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Se você escolher essa opção, poderá ir para a seção Configurar Microsoft 365 Defender [para enviar tabelas de email.](#configure-microsoft-365-defender-to-send-email-tables)

Crie um Hub de Eventos em seu Namespace selecionando **Hubs de Eventos \> + Hub de Eventos**.

A Contagem de Partição permite taxa de transferência adicional por meio do paralelismo, portanto, é recomendável aumentar esse número com base na carga que você está esperando.  
Os valores padrão de Retenção e Captura de Mensagens de 1 e Off são recomendados.

![Imagem de criar Hub de Eventos](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

Para esse Hub de Eventos (não namespace), você precisará configurar uma Política de Acesso Compartilhado com Enviar, Ouvir Declarações. Clique em suas políticas de acesso compartilhado do Hub de Eventos **\> + \> Adicionar** e, em seguida, dê a ele um nome de Política (não usado em outro lugar) e verifique **Enviar** e **Ouvir**.

![Imagem das políticas de acesso compartilhado](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Configurar Microsoft 365 Defender para enviar tabelas de email


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Configuração Microsoft 365 Defender enviar tabelas de email para o Splunk por meio do Hub de Eventos


1. Faça logon Microsoft 365 Defender <https://security.microsoft.com> com uma conta que atenda a todos os seguintes requisitos de função:

    - Função de colaborador no nível de Recurso *de Namespace* do Hub de Eventos ou superior para o Hub de Eventos para o que você exportará. Sem isso, você receberá um erro de exportação ao tentar salvar as configurações.

    - Função de Administrador Global ou Administrador de Segurança no locatário vinculado ao Microsoft 365 Defender e ao Azure.

    ![Imagem do portal de segurança](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Clique em **Exportar Dados Brutos \> +Adicionar**.

    Agora você usará os dados gravados acima.

    **Nome**: isso é local e deve ser o que funciona em seu ambiente.

    **Encaminhar eventos para o hub de eventos**: Selecione essa caixa de seleção.

    **ID do Recurso event-hub:** esta é a ID do Recurso de Namespace do Hub de Eventos que você gravou acima ao configurar o Hub de Eventos.

    **Nome do Hub de** Evento : se você criou um Hub de Eventos dentro do namespace do Hub de Eventos, colar o nome do Hub de Eventos que você gravou acima.

    Se você optar por permitir Microsoft 365 Defender criar Hubs de Eventos por Tipos de Eventos (Tabelas) para você, deixe este campo vazio.

    **Tipos de** evento : selecione as tabelas de Busca Avançada que você deseja encaminhar para o Hub de Eventos e, em seguida, para seu aplicativo personalizado. As tabelas de alerta são Microsoft 365 Defender, as tabelas dispositivos são do Microsoft Defender para Ponto de Extremidade (EDR) e as tabelas de email são do Microsoft Defender para Office 365. Eventos de email registra todas as transações de email. A URL (SafeLinks), Attachment (Cofre Attachments) e Eventos de Pós-Entrega (ZAP) também são gravadas e podem ser ingressada nos Eventos de Email no campo NetworkMessageId.

    ![Imagem das configurações da API de streaming](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Clique em **Enviar**.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Verifique se os eventos estão sendo exportados para o Hub de Eventos


Você pode verificar se os eventos estão sendo enviados para o Hub de Eventos executando uma consulta de Busca Avançada básica. Selecione **Procurar Consulta de Busca \> \> Avançada** e insira a seguinte consulta:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Isso mostrará quantos emails foram recebidos na última hora ingressados em todas as outras tabelas. Ele também mostrará se você estiver vendo eventos que podem ser exportados para o hub de eventos. Se essa contagem mostrar 0, você não verá nenhum dado saindo para o Hub de Eventos.

![Imagem da busca avançada](../../media/c305e57dc6f72fa9eb035943f244738e.png)

Depois de verificar se há dados a exportar, você pode exibir o Hub de Eventos para verificar se as mensagens estão sendo recebidas. Isso pode levar até uma hora. 
 
1. No Azure, vá para Hubs de Eventos Clique nos Hubs de Eventos do **\> Namespace \> Clique no Hub \> de Eventos**.  
1. Em **Visão Geral,** role para baixo e no gráfico Mensagens, você deve ver Mensagens de Entrada. Se você não vir nenhum resultado, não haverá mensagens para seu aplicativo personalizado ingerir.

    ![Imagem da guia visão geral com mensagens](../../media/e88060e315d76e74269a3fc866df047f.png)
