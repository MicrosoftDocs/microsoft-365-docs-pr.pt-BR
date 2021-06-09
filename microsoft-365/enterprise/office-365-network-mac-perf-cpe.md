---
title: Microsoft 365 roteamento de rede informado
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 roteamento de rede informado
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717590"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 roteamento de rede informado (visualização)

O roteamento de rede informado é um recurso que integra vários aplicativos Microsoft 365 com soluções de rede definida por software de terceiros (SD-WAN) para otimizar e melhorar sua conectividade de rede com os pontos de extremidade de serviço da Microsoft. A conectividade SD-WAN otimizada pode resultar em experiências e desempenho do usuário aprimorados.

>[!IMPORTANT]
>Microsoft 365 roteamento de rede informado está no status de visualização. Para obter mais informações sobre essa visualização, incluindo diretrizes para receber assistência, consulte Microsoft 365 de roteamento de rede [informado Visualização Pública](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Visão Geral

O roteamento de rede informado fornece um canal de compartilhamento de dados bi-direcional entre a Microsoft e sua solução SD-WAN. Para cada local de escritório e circuito da Internet que você configurar, a Microsoft compartilha periodicamente comentários com a solução SD-WAN sobre a qualidade das experiências de aplicativos selecionados Microsoft 365 tráfego de rede associado a cada circuito específico da Internet. Usando esses comentários, a solução SD-WAN pode, em seguida, tomar ações de recuperação inteligente roteamento Microsoft 365 tráfego de aplicativos por meio de links disponíveis alternativos. 

As degradaçãos de qualidade do serviço no caminho de um determinado circuito da Internet, como latência aumentada ou perda alta de pacotes, são difíceis de detectar em uma base contínua. Essas degradaçãos podem ser prejudiciais para as experiências do usuário para aplicativos como Exchange Online, SharePoint, OneDrive e Microsoft Teams. Os sintomas comuns incluem pesquisa lenta de conteúdo Exchange, tempos de transferência elevados ao interagir com bibliotecas de documentos SharePoint ou OneDrive, ou má qualidade de chamada ou reunião no Microsoft Teams.

O mecanismo de feedback e recuperação dentro do roteamento informado de rede procura detectar dinamicamente esses problemas em tempo real e informa a solução SD-WAN implantada para tomar ações de recuperação automáticas.

O canal de compartilhamento de dados também é usado para receber periodicamente dados ópticos de nível de rede da solução SD-WAN, incluindo informações de configuração e estatísticas de uso associadas ao dispositivo e circuitos anexados. Nenhuma informação pessoal é coletada ou armazenada. Todas as informações coletadas são agregadas a locais de escritório e circuitos conectados à Internet. Essas informações podem ajudar a Microsoft a resolver com mais eficiência e eficácia problemas relatados com o uso de serviços Microsoft 365 aplicativos.

>[!NOTE]
>Microsoft 365 roteamento de rede informado dá suporte a locatários na nuvem comercial da W GCC W, mas não as nuvens Moderadas, GCC Alta, DoD, Alemanha ou China.

## <a name="requirements"></a>Requisitos

### <a name="integrated-sd-wan-solutions"></a>Soluções SD-WAN integradas

A Microsoft está trabalhando com vários parceiros para habilitar a integração com Microsoft 365 roteamento de rede informado. As soluções habilitadas no momento incluem o seguinte:

| Device Maker | Nome da solução | Versão mínima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topologia de rede 

O roteamento de rede informado atualmente identifica o tráfego associado a um local de escritório específico e um circuito da Internet com base no endereço IP público usado para enviar tráfego de rede para a Microsoft. 

No caso em que não houver pelo menos um circuito de rede fornecendo acesso direto à Internet em um local de filial, o roteamento informado da rede pode não fornecer valor significativo.

### <a name="application-usage"></a>Uso do aplicativo

Os dados de experiência do aplicativo (refletidos por meio de métricas de qualidade de rede) são coletados por meio do uso de aplicativos cliente específicos da Microsoft. Exchange métricas refletem o uso do cliente Outlook, bem como algumas Outlook Web App uso. SharePoint e OneDrive refletem o uso dos pontos de extremidade específicos SharePoint locatários, independentemente do aplicativo cliente. Teams métricas refletem o uso do cliente Teams área de trabalho. Outro tráfego de aplicativo não é considerado ao avaliar a saúde de um circuito de rede.

## <a name="enabling-informed-network-routing"></a>Habilitando o roteamento de rede informado

A habilitação do roteamento de rede informado exige várias etapas, algumas das quais precisarão ser executadas na interface de configuração da sua solução SD-WAN. Consulte seu fornecedor de soluções SD-WAN para obter orientações sobre como iniciar o processo de habilitação do roteamento informado de rede na solução SD-WAN antes de prosseguir com a configuração no centro de administração Microsoft 365.

Depois de estar pronto para habilitar o roteamento de rede informado no centro de administração Microsoft 365, certifique-se de ter as permissões de administrador global necessárias.

>[!IMPORTANT]
>Para fornecer o consentimento de permissões de aplicativos de nível de locatário necessários para que a solução SD-WAN selecionada acesse o canal de compartilhamento de dados de roteamento de rede informado, execute as etapas a seguir como administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: Abrir opções de configuração de solução do SD-WAN

No centro [Microsoft 365 de administração,](https://admin.microsoft.com/)selecione **Conectividade de** rede > de rede no painel de navegação à esquerda.

Esta seção do centro de administração fornece métricas de conectividade de rede agregadas para sua organização e orientações sobre como melhorar sua conectividade. Consulte Conectividade de rede no Centro de administração [Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md) para obter informações adicionais sobre esses recursos disponíveis no centro de administração.

Selecione **Configurações > solução SD-WAN para** abrir o painel de configuração de roteamento de rede informado. As outras opções que aparecem em **Configurações** são aplicáveis às diretrizes gerais de conectividade de rede no centro de administração e não são necessárias para habilitar o roteamento de rede informado.

No painel de configuração, selecione **Adicionar sua solução SD-WAN (Visualização)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Etapa 2: selecione a solução SD-WAN e o local de armazenamento de dados

Nas caixas listadas, selecione a solução SD-WAN que você implantou e o local onde deseja ter os dados associados ao roteamento informado da rede armazenados. Consulte a [seção armazenamento de dados](#data-storage) para obter informações adicionais.

Selecione **Avançar**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Etapa 3: Aceitar termos para compartilhamento de dados

Leia e confirme cuidadosamente os termos fornecidos associados ao compartilhamento de dados entre a Microsoft e sua solução SD-WAN selecionada e selecione a caixa de seleção indicada.

Selecione **Avançar**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Etapa 4: Conceder permissões à solução SD-WAN

Esta etapa iniciará uma solicitação de concessão de permissões com Azure Active Directory (Azure AD). Você será solicitado a conceder permissões no nível de locatário que permitem o acesso da solução SD-WAN selecionada ao armazenamento de dados de roteamento de rede informado e às informações de saúde do serviço associadas ao locatário. Essa ação requer permissões de função de administrador global.

Selecione o **link Dar permissão a esse** aplicativo e siga as solicitações do Azure AD.

Depois de concluir a concessão de permissões, selecione **Next**.

### <a name="step-5-confirm-your-configuration-settings"></a>Etapa 5: Confirmar suas configurações

A etapa final na habilitação do roteamento informado da rede para seu locatário é uma página de confirmação que exibe as configurações fornecidas. 

O roteamento de rede informado agora está habilitado para seu locatário.

Selecione **Feito** e feche o painel de configuração da solução SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configurando o roteamento informado da rede

Você executará grande parte da configuração para o roteamento de rede informado em sua solução SD-WAN, como configurar como o tráfego deve ser roteado em circunstâncias normais e os caminhos alternativos que devem ser usados se os problemas são detectados. Consulte seu provedor de soluções SD-WAN para obter detalhes sobre essas etapas de configuração.

Cada local do escritório deve ser configurado no centro de administração Microsoft 365 para que o roteamento de rede informado possa identificar corretamente o tráfego associado aos circuitos de rede que proporcionam conectividade a esses locais.

Office locais podem ser detectados automaticamente como parte da coleção contínua de telemetria de rede da Microsoft. Como resultado, alguns locais podem ser pré-preenchidos no centro de administração do locatário. 

Se esses locais são precisos, você simplesmente precisará habilitar o recurso de roteamento de rede informado para cada local desejado e configurar os circuitos da Internet e seus endereços IP públicos. 

Se os locais detectados automaticamente não são precisos ou não há locais pré-preenchidos em seu locatário, você terá que adicionar ou editar locais manualmente para refletir uma topologia precisa da sua organização.

### <a name="updating-locations"></a>Atualizando locais

Locais para seu locatário podem ser encontrados na **guia Locais.** Os locais podem ser editados diretamente na lista ou atualizados usando um arquivo CSV.

Verifique se cada local do office onde você deseja habilitar o roteamento de rede informado está presente nesta lista.

>[!NOTE]
>As colunas na lista **Locais para** amostras coletadas e outras informações relacionadas à avaliação não estão relacionadas ao recurso de roteamento de rede informado.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitando um local para roteamento de rede informado

1. Na lista **Locais,** selecione **Editar** no menu ações rápidas para abrir o painel de configuração de local.

2. Selecione **Usar Microsoft 365 roteamento de rede informado neste local**.

3. Adicione todos os circuitos de rede que proporcionam conectividade com a Internet a esse local do escritório **nos intervalos** de endereço IP Egress nesta seção de local do escritório. Verifique se cada circuito está associado às sub-redes de endereço IP pública exclusivas que representam o tráfego de rede.

4. Selecione **Salvar** para salvar suas alterações.

## <a name="disabling-network-informed-routing"></a>Desabilitando o roteamento informado da rede

O recurso de roteamento de rede informado pode ser desabilitado para todo o locatário redefinindo suas configurações de solução SD-WAN. Embora isso pare todo o processamento de dados dentro Microsoft 365, você também deve desabilitar o roteamento informado da rede no centro de administração.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: Abrir opções de configuração de solução do SD-WAN

No centro [de Microsoft 365 de administração,](https://admin.microsoft.com/) selecione **Conectividade > Rede** no painel de navegação à esquerda.

Selecione **Configurações > solução SD-WAN para** abrir o painel de configuração de roteamento de rede informado.

O painel de configuração mostra um resumo da solução SD-WAN configurada no momento.

### <a name="step-2-reset-your-configuration"></a>Etapa 2: Redefinir sua configuração

No painel de configuração, selecione **Redefinir suas configurações de solução SD-WAN.**

Suas configurações agora foram redefinidas e o roteamento de rede informado foi desabilitado. Você pode reabilitar a qualquer momento seguindo as etapas em [Habilitar o roteamento de rede informado.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Armazenamento de dados

Os dados trocados entre a Microsoft e o provedor de soluções SD-WAN são armazenados no local de armazenamento de dados selecionado durante a habilitação inicial do roteamento informado da rede. As opções de local de armazenamento de dados representam áreas geográficas que Microsoft Azure regiões onde os dados são armazenados.

>[!NOTE]
>Durante a fase visualização, o único local de armazenamento de dados disponível é a **América do Norte**. Locais de armazenamento de dados adicionais serão disponibilizados antes da disponibilidade geral do roteamento de rede informado.

Os dados são mantidos nesse local por até 30 dias. Quando desabilitado, todos os dados restantes são removidos nesta janela de retenção de 30 dias.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Microsoft 365 de administração (visualização)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Serviços de Localização de Conectividade de Rede (visualização)](office-365-network-mac-location-services.md)
