---
title: Roteamento de rede Microsoft 365 informado
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
description: Roteamento de rede Microsoft 365 informado
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749546"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Roteamento de rede informado da Microsoft 365 (versão prévia)

O roteamento de rede informado é um recurso que integra vários aplicativos da Microsoft 365 com soluções de rede (SD-WAN) de terceiros definidas para otimizar e aprimorar a conectividade de rede para pontos de extremidade de serviço da Microsoft. A conectividade SD-WAN otimizada pode resultar em experiências e desempenho aprimorados do usuário.

>[!IMPORTANT]
>O roteamento de rede Microsoft 365 informado está atualmente no status de visualização. Para obter mais informações sobre esta visualização, incluindo orientações para receber assistência, consulte [Microsoft 365 informative Routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Visão Geral

O roteamento de rede informado fornece um canal de compartilhamento de dados bidirecional entre a Microsoft e sua solução SD-WAN. Para todos os locais do Office e o circuito da Internet que você configura, a Microsoft compartilha periodicamente comentários com a solução SD-WAN na qualidade das experiências de aplicativo do Microsoft 365 selecionadas para o tráfego de rede associado a cada circuito de Internet específico. Usando esse feedback, a solução SD-WAN pode realizar ações de recuperação inteligentes ao rotear o tráfego do aplicativo Microsoft 365 através de links alternativos disponíveis. 

É difícil detectar a qualidade das degradações de serviço no caminho de um circuito de Internet específico, como latência maior ou perda alta de pacotes. Essas degradações podem ser prejudiciais às experiências do usuário para aplicativos como o Exchange Online, o SharePoint, o OneDrive e o Microsoft Teams. Sintomas comuns incluem pesquisa lenta de conteúdo do Exchange, tempos de transferência altos quando interagindo com bibliotecas de documentos do SharePoint ou do OneDrive ou qualidade de chamada ou de reunião ruim no Microsoft Teams.

O mecanismo de comentários e recuperação dentro do roteamento informado pela rede busca detectar dinamicamente esses problemas praticamente em tempo real e informa a solução implantada do SD-WAN para executar ações de recuperação automática.

O canal de compartilhamento de dados também é usado para receber periodicamente dados de ópticos de nível de rede da solução SD-WAN, incluindo informações de configuração e estatísticas de uso associadas ao dispositivo e circuitos anexados. Nenhuma informação pessoal é coletada ou armazenada. Todas as informações coletadas são agregadas a locais do Office e circuitos conectados à Internet. Essas informações podem ajudar a Microsoft a solucionar com mais eficiência e eficácia problemas relatados com o uso de serviços e aplicativos do Microsoft 365.

>[!NOTE]
>O Microsoft 365 roteamento de rede informado oferece suporte a locatários na nuvem comercial mundial, mas não às nuvens GCC moderada, GCC alta, DoD, Alemanha ou China.

## <a name="requirements"></a>Requisitos

### <a name="integrated-sd-wan-solutions"></a>Soluções integradas SD-WAN

A Microsoft está trabalhando com vários parceiros para habilitar a integração com o roteamento de rede informado pelo Microsoft 365. As soluções atualmente habilitadas incluem o seguinte:

| Criador de dispositivos | Nome da solução | Versão mínima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topologia de rede 

O roteamento de rede informado atualmente identifica o tráfego associado a um local específico do Office e ao circuito de Internet com base no endereço IP público usado para enviar o tráfego de rede para a Microsoft. 

No caso em que não há pelo menos um circuito de rede fornecendo acesso direto à Internet em um local de filial, o roteamento informado pela rede pode não fornecer um valor significativo.

### <a name="application-usage"></a>Uso do aplicativo

Dados de experiência do aplicativo (refletidas por meio de métricas de qualidade de rede) são coletados através do uso do Microsoft Outlook em dispositivos que executam o Windows, o Teams, o SharePoint e o OneDrive Outro tráfego de aplicativos não é considerado durante a avaliação da integridade de um circuito de rede.

## <a name="enabling-informed-network-routing"></a>Habilitando roteamento de rede informado

Habilitar o roteamento de rede informado requer várias etapas, algumas das quais precisarão ser realizadas na interface de configuração da sua solução SD-WAN. Consulte seu fornecedor de soluções de SD-WAN para obter orientação sobre como iniciar o processo de habilitar o roteamento de rede informada dentro da solução SD-WAN antes de prosseguir com a configuração no centro de administração do Microsoft 365.

Quando estiver pronto para habilitar o roteamento de rede informado no centro de administração do Microsoft 365, verifique se você tem as permissões de administrador global necessárias.

>[!IMPORTANT]
>Para fornecer as permissões de aplicativos em nível de locatário necessárias para a solução SD-WAN selecionada para acessar o canal de compartilhamento de dados de roteamento de rede informado, você deve executar as etapas a seguir como um administrador global.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: abrir as opções de configuração da solução SD-WAN

No [centro de administração do Microsoft 365](https://admin.microsoft.com/), selecione **integridade > conectividade de rede** no painel de navegação à esquerda.

Esta seção do centro de administração fornece métricas de conectividade de rede agregadas para sua organização e orientações sobre como melhorar sua conectividade. Consulte [conectividade de rede no centro de administração do Microsoft 365 (versão prévia)](office-365-network-mac-perf-overview.md) para obter informações adicionais sobre esses recursos disponíveis no centro de administração.

Selecione **configurações > solução SD-Wan** para abrir o painel de configuração de roteamento de rede informado. As outras opções que aparecem em **configurações** são aplicáveis à orientação geral de conectividade de rede no centro de administração e não são necessárias para habilitar o roteamento de rede informado.

No painel configuração, selecione **adicionar sua solução SD-WAN (visualização)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Etapa 2: selecionar sua solução SD-WAN e o local de armazenamento de dados

Nas caixas suspensas, selecione a solução SD-WAN que você implantou e o local em que deseja ter os dados associados ao roteamento de rede informado armazenado. Consulte a seção [armazenamento de dados](#data-storage) para obter informações adicionais.

Selecione **Avançar**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Etapa 3: aceitar termos para compartilhamento de dados

Leia atentamente e confirme os termos fornecidos associados ao compartilhamento de dados entre a Microsoft e a sua solução SD-WAN selecionada e, em seguida, selecione a caixa de seleção indicada.

Selecione **Avançar**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Etapa 4: conceder permissões à solução SD-WAN

Esta etapa iniciará uma solicitação de concessão de permissões com o Azure Active Directory (Azure AD). Você será solicitado a conceder permissões no nível do locatário que permitam que sua solução de SD-WAN seja acessada para o armazenamento de dados de roteamento de rede informado e as informações de integridade do serviço associadas ao seu locatário. Esta ação requer permissões de função de administrador global.

Selecione o link **conceder permissão para este aplicativo** e siga as solicitações do Azure AD.

Depois de concluir a concessão de permissões, selecione **Avançar**.

### <a name="step-5-confirm-your-configuration-settings"></a>Etapa 5: confirmar suas definições de configuração

A etapa final ao habilitar o roteamento de rede informada para seu locatário é uma página de confirmação que exibe as configurações que você forneceu. 

O roteamento de rede informado agora está habilitado para seu locatário.

Selecione **concluído** e feche o painel de configuração de soluções SD-Wan.

## <a name="configuring-network-informed-routing"></a>Configurando o roteamento de rede

Você executará grande parte da configuração do roteamento de rede informado em sua solução SD-WAN, como configurar como o tráfego deve ser roteado sob circunstâncias normais e os caminhos alternativos que devem ser usados se forem detectados problemas. Consulte seu provedor de soluções SD-WAN para obter detalhes sobre essas etapas de configuração.

Cada localização do Office deve ser configurada no centro de administração do Microsoft 365 para que o roteamento de rede informado possa identificar corretamente o tráfego associado aos circuitos de rede fornecendo conectividade a esses locais.

Os locais do Office podem ser detectados automaticamente como parte do conjunto contínuo de telemetria de rede da Microsoft. Como resultado, alguns locais podem ser preenchidos previamente no centro de administração para o locatário. 

Se esses locais forem precisos, você só precisará habilitar o recurso de roteamento de rede informado para cada local desejado e configurar os circuitos da Internet e seus endereços IP públicos. 

Se os locais detectados automaticamente não forem precisos ou se não houver locais previamente preenchidos no locatário, você terá que adicionar ou editar locais manualmente para refletir uma topologia precisa da sua organização.

### <a name="updating-locations"></a>Atualizando locais

Os locais para o seu locatário podem ser encontrados na guia **locais** . Os locais podem ser editados diretamente na lista ou atualizados usando um arquivo CSV.

Certifique-se de que cada local do escritório onde você deseja habilitar o roteamento de rede informado está presente nesta lista.

>[!NOTE]
>As colunas na lista de **locais** de exemplos coletados e outras informações relacionadas à avaliação não estão relacionadas ao recurso de roteamento de rede informado.

### <a name="enabling-a-location-for-informed-network-routing"></a>Habilitando um local para roteamento de rede informado

1. Na lista **locais** , selecione **Editar** no menu ações rápidas para abrir o painel configuração de local.

2. Selecione **usar o Microsoft 365 roteamento de rede informado neste local**.

3. Adicione todos os circuitos de rede que fornecem conectividade com a Internet a este local do Office na seção **intervalos de endereços IP de egresso nesta localização do escritório** . Certifique-se de que cada circuito está associado às sub-redes exclusivas de endereço IP, representando o tráfego de rede.

4. Clique em **Salvar** para salvar suas alterações.

## <a name="disabling-network-informed-routing"></a>Desabilitando roteamento de rede informado

O recurso de roteamento de rede informado pode ser desabilitado para todo o locatário redefinindo suas configurações de solução SD-WAN. Embora isso pare todo o processamento de dados no Microsoft 365, você também deve desabilitar o roteamento de rede informada no centro de administração.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Etapa 1: abrir as opções de configuração da solução SD-WAN

No [centro de administração do Microsoft 365](https://admin.microsoft.com/) , selecione **integridade > conectividade de rede** no painel de navegação do lado esquerdo.

Selecione **configurações > solução SD-Wan** para abrir o painel de configuração de roteamento de rede informado.

O painel de configuração mostra um resumo de sua solução SD-WAN configurada no momento.

### <a name="step-2-reset-your-configuration"></a>Etapa 2: redefinir sua configuração

No painel configuração, selecione **redefinir suas configurações de solução SD-Wan**.

Suas configurações foram redefinidas e o roteamento de rede informado foi desabilitado. Você pode habilitá-lo novamente a qualquer momento, seguindo as etapas de [habilitação de roteamento de rede informado](#enabling-informed-network-routing).

## <a name="data-storage"></a>Armazenamento de dados

Dados trocados entre a Microsoft e o provedor de soluções SD-WAN são armazenados no local de armazenamento de dados selecionado durante a habilitação inicial de roteamento de rede informada. As opções de local de armazenamento de dados representam áreas geográficas contendo regiões do Microsoft Azure onde os dados são armazenados.

>[!NOTE]
>Durante a fase de visualização, o único local de armazenamento de dados disponível é **América do Norte**. Locais de armazenamento de dados adicionais ficarão disponíveis antes da disponibilidade geral do roteamento de rede informado.

Os dados são mantidos nesse local por até 30 dias. Quando desabilitado, todos os dados restantes são removidos dentro da janela de retenção de 30 dias.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no centro de administração do Microsoft 365 (versão prévia)](office-365-network-mac-perf-overview.md)

[Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)](office-365-network-mac-location-services.md)
