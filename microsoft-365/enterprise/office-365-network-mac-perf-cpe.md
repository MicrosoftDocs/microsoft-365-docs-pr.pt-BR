---
title: Roteamento de rede informado do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Roteamento de rede informado do Microsoft 365
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749546"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Roteamento de rede informado do Microsoft 365 (visualização)

O roteamento de rede informado é um recurso que integra vários aplicativos do Microsoft 365 com soluções de rede definida por software de terceiros (SD-WAN) para otimizar e melhorar a conectividade de rede com os pontos de extremidade de serviço da Microsoft. A conectividade otimizada do SD-WAN pode resultar em experiências e desempenho do usuário aprimorados.

>[!IMPORTANT]
>O roteamento de rede informado do Microsoft 365 está atualmente no status de visualização. Para obter mais informações sobre essa visualização, incluindo orientações para receber assistência, consulte [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Visão Geral

O roteamento de rede informado fornece um canal de compartilhamento de dados bi-direcional entre a Microsoft e sua solução SD-WAN. Para cada local do escritório e circuito da Internet que você configurar, a Microsoft compartilha periodicamente comentários com a solução SD-WAN sobre a qualidade das experiências de aplicativos do Microsoft 365 selecionadas para o tráfego de rede associado a cada circuito específico da Internet. Usando esses comentários, a solução SD-WAN pode então tomar ações de recuperação inteligente roteamento do tráfego de aplicativos do Microsoft 365 por meio de links alternativos disponíveis. 

As degradaçãos da qualidade do serviço no caminho de um determinado circuito da Internet, como maior latência ou perda de pacotes alta, são difíceis de detectar continuamente. Essas degradaçãos podem ser prejudiciais às experiências do usuário para aplicativos como o Exchange Online, o SharePoint, o OneDrive e o Microsoft Teams. Os sintomas comuns incluem pesquisa lenta de conteúdo do Exchange, tempos de transferência altos ao interagir com bibliotecas de documentos do SharePoint ou do OneDrive ou baixa qualidade de chamada ou reunião no Microsoft Teams.

O mecanismo de feedback e recuperação no roteamento informado na rede procura detectar dinamicamente esses problemas quase em tempo real e informa a solução SD-WAN implantada para tomar ações de recuperação automática.

O canal de compartilhamento de dados também é usado para receber periodicamente dados de ótica no nível de rede da solução SD-WAN, incluindo informações de configuração e estatísticas de uso associadas ao dispositivo e circuitos conectados. Nenhuma informação pessoal é coletada ou armazenada. Todas as informações coletadas são agregadas a locais de escritório e circuitos de Internet conectados. Essas informações podem ajudar a Microsoft a resolver problemas relatados com mais eficiência e eficiência com o uso dos serviços e aplicativos do Microsoft 365.

>[!NOTE]
>O roteamento de rede informado do Microsoft 365 dá suporte a locatários na nuvem comercial do WW, mas não nas nuvens GCC Moderada, GCC Alta, DoD, Alemanha ou China.

## <a name="requirements"></a>Requisitos

### <a name="integrated-sd-wan-solutions"></a>Soluções SD-WAN integradas

A Microsoft está trabalhando com vários parceiros para habilitar a integração com o roteamento de rede informado do Microsoft 365. As soluções habilitadas no momento incluem o seguinte:

| Device Maker | Nome da solução | Versão mínima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topologia de rede 

O roteamento de rede informado atualmente identifica o tráfego associado a um local específico do escritório e circuito da Internet com base no endereço IP público usado para enviar tráfego de rede para a Microsoft. 

No caso em que não haja pelo menos um circuito de rede fornecendo acesso direto à Internet em um local de filial, o roteamento informado pela rede pode não fornecer valor significativo.

### <a name="application-usage"></a>Uso do aplicativo

Os dados de experiência do aplicativo (refletidos por meio de métricas de qualidade de rede) são coletados por meio do uso do Microsoft Outlook em dispositivos que executam o Windows, o Teams, o SharePoint e o OneDrive. Outro tráfego de aplicativo não é considerado ao avaliar a saúde de um circuito de rede.

## <a name="enabling-informed-network-routing"></a>Habilitando o roteamento de rede informado

A habilitação do roteamento de rede informado exige várias etapas, algumas das quais precisarão ser executadas na interface de configuração da solução SD-WAN. Consulte o fornecedor da solução SD-WAN para obter orientação sobre como iniciar o processo de habilitação do roteamento informado pela rede na solução SD-WAN antes de prosseguir com a configuração no Centro de administração do Microsoft 365.

Quando estiver pronto para habilitar o roteamento de rede informado no Centro de administração do Microsoft 365, verifique se você tem as permissões de administrador global necessárias.

>[!IMPORTANT]
>Para fornecer o consentimento de permissões de aplicativos no nível do locatário necessários para que a solução SD-WAN selecionada acesse o canal de compartilhamento de dados de roteamento de rede informado, você deve executar as seguintes etapas como um administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: Abrir opções de configuração de solução SD-WAN

No Centro [de administração do Microsoft 365,](https://admin.microsoft.com/)selecione Health > Network **connectivity** in the left-hand navigation pane.

Esta seção do centro de administração fornece métricas de conectividade de rede agregadas para sua organização e orientações sobre como melhorar sua conectividade. Consulte Conectividade de rede no Centro de administração do [Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md) para obter informações adicionais sobre esses recursos disponíveis no centro de administração.

Selecione **Configurações > solução SD-WAN para** abrir o painel de configuração de roteamento de rede informado. As outras opções  que aparecem em Configurações são aplicáveis às diretrizes gerais de conectividade de rede no centro de administração e não são necessárias para habilitar o roteamento de rede informado.

No painel de configuração, selecione **Adicionar sua solução SD-WAN (Visualização).**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Etapa 2: Selecione a solução SD-WAN e o local de armazenamento de dados

Nas caixas de lista, selecione a solução SD-WAN que você implantou e o local onde você deseja que os dados associados ao roteamento informado na rede armazenados. Consulte a [seção de armazenamento de](#data-storage) dados para obter informações adicionais.

Selecione **Avançar**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Etapa 3: Aceitar termos para compartilhamento de dados

Leia e confirme cuidadosamente os termos fornecidos associados ao compartilhamento de dados entre a Microsoft e sua solução SD-WAN selecionada e marque a caixa de seleção indicada.

Selecione **Avançar**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Etapa 4: Conceder permissões à solução SD-WAN

Esta etapa iniciará uma solicitação de concessão de permissões com o Azure Active Directory (Azure AD). Você será solicitado a conceder permissões no nível do locatário que permitem que sua solução SD-WAN selecionada acesse o armazenamento de dados de roteamento de rede informado e as informações de saúde do serviço associadas ao seu locatário. Essa ação requer permissões de função de administrador global.

Selecione o **link Dar permissão para este aplicativo** e siga as solicitações do Azure AD.

Depois de concluir a concessão de permissões, selecione **Próximo**.

### <a name="step-5-confirm-your-configuration-settings"></a>Etapa 5: Confirmar suas definições de configuração

A etapa final na habilitação do roteamento informado pela rede para seu locatário é uma página de confirmação que exibe as configurações que você forneceu. 

O roteamento de rede informado agora está habilitado para seu locatário.

Selecione **Feito e** feche o painel de configuração da solução SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configurando o roteamento informado pela rede

Você executará grande parte da configuração para o roteamento de rede informado em sua solução SD-WAN, como configurar como o tráfego deve ser roteado em circunstâncias normais e os caminhos alternativos que devem ser usados se problemas são detectados. Consulte seu provedor de soluções SD-WAN para obter detalhes sobre essas etapas de configuração.

Cada local do escritório deve ser configurado no Centro de administração do Microsoft 365 para que o roteamento de rede informado possa identificar corretamente o tráfego associado aos circuitos de rede que proporcionam conectividade a esses locais.

Os locais do Office podem ser detectados automaticamente como parte da coleção contínua de telemetria de rede da Microsoft. Como resultado, alguns locais podem ser pré-preenchidos no centro de administração do seu locatário. 

Se esses locais são precisos, basta habilitar o recurso de roteamento de rede informado para cada local desejado e configurar os circuitos de Internet e seus endereços IP públicos. 

Se os locais detectados automaticamente não são precisos ou não há locais pré-preenchidos em seu locatário, você terá que adicionar ou editar locais manualmente para refletir uma topologia precisa da sua organização.

### <a name="updating-locations"></a>Atualizando locais

Locais para seu locatário podem ser encontrados na guia **Locais.** Os locais podem ser editados diretamente na lista ou atualizados usando um arquivo CSV.

Certifique-se de que cada local de escritório onde você deseja habilitar o roteamento de rede informado está presente nesta lista.

>[!NOTE]
>As colunas na lista **Locais** dos exemplos coletados e outras informações relacionadas à avaliação não estão relacionadas ao recurso de roteamento de rede informado.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitando um local para roteamento de rede informado

1. Na lista **Locais,** selecione **Editar** no menu ações rápidas para abrir o painel de configuração de local.

2. Selecione Usar o roteamento de rede informado **do Microsoft 365 neste local.**

3. Adicione todos os circuitos de rede que proporcionam conectividade com a Internet a esse local de escritório nos intervalos de **Endereços IP** de Saída nesta seção de local do escritório. Verifique se cada circuito está associado às sub-redes de endereço IP pública exclusivas que representam o tráfego de rede.

4. Clique em **Salvar** para salvar suas alterações.

## <a name="disabling-network-informed-routing"></a>Desabilitando o roteamento informado pela rede

O recurso de roteamento de rede informado pode ser desabilitado para todo o locatário redefinindo suas configurações de solução SD-WAN. Embora isso pare todo o processamento de dados no Microsoft 365, você também deve desabilitar o roteamento informado na rede no centro de administração.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: Abrir opções de configuração de solução SD-WAN

No Centro [de administração do Microsoft 365,](https://admin.microsoft.com/) selecione Health > Network **connectivity** in the left-hand navigation pane.

Selecione **Configurações > solução SD-WAN para** abrir o painel de configuração de roteamento de rede informado.

O painel de configuração mostra um resumo da solução SD-WAN configurada no momento.

### <a name="step-2-reset-your-configuration"></a>Etapa 2: Redefinir sua configuração

No painel de configuração, selecione **Redefinir as configurações da solução SD-WAN.**

Suas configurações foram redefinidas e o roteamento de rede informado foi desabilitado. Você pode reabilitar a qualquer momento seguindo as etapas em [Habilitar o roteamento de rede informado.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Armazenamento de dados

Os dados trocados entre a Microsoft e o provedor de soluções SD-WAN são armazenados no local de armazenamento de dados selecionado durante a habilitação inicial do roteamento informado pela rede. As opções de local de armazenamento de dados representam áreas geográficas que contêm regiões do Microsoft Azure onde os dados são armazenados.

>[!NOTE]
>Durante a fase de visualização, o único local de armazenamento de dados disponível é a **América do Norte.** Locais de armazenamento de dados adicionais serão disponibilizados antes da disponibilidade geral do roteamento de rede informado.

Os dados são mantidos nesse local por até 30 dias. Quando desabilitado, todos os dados restantes são removidos dentro dessa janela de retenção de 30 dias.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no centro de administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)
