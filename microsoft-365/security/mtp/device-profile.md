---
title: Perfil de dispositivo no portal de segurança do Microsoft 365
description: Exibir níveis de risco e exposição para um dispositivo em sua organização. Analise ameaças passadas e presentes e proteja o dispositivo com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, Proteção contra Ameaças da Microsoft, MTP, central de segurança, Microsoft Defender ATP, Office 365 ATP, Azure ATP, página do dispositivo, perfil do dispositivo, página do computador, perfil do computador
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929569"
---
# <a name="device-profile-page"></a>Página de perfil do dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


O portal de segurança do Microsoft 365 fornece páginas de perfil de dispositivo, para que você possa avaliar rapidamente a saúde e o status dos dispositivos em sua rede.

> [!IMPORTANT]
> A página de perfil do dispositivo pode parecer um pouco diferente, dependendo se o dispositivo está inscrito no Microsoft Defender para Ponto de Extremidade, No Microsoft Defender para Identidade ou ambos.

Se o dispositivo estiver inscrito no Microsoft Defender para o Ponto de Extremidade, você também poderá usar a página de perfil do dispositivo para executar algumas tarefas de segurança comuns.

## <a name="navigating-the-device-profile-page"></a>Navegando na página de perfil do dispositivo

A página de perfil é dividida em várias seções amplas.

![Imagem da página de perfil de dispositivo com (1) Área de guia (2) Barra lateral e (3) Ações realçadas em vermelho](../../media/mtp-device-profile/hybrid-device-overall.png)

A barra lateral (1) lista detalhes básicos sobre o dispositivo.

A área de conteúdo principal (2) contém guias que você pode alternar para exibir diferentes tipos de informações sobre o dispositivo.

Se o dispositivo estiver inscrito no Microsoft Defender para o Ponto de Extremidade, você também verá uma lista de ações de resposta (3). As ações de resposta permitem executar tarefas comuns relacionadas à segurança.

## <a name="sidebar"></a>Barra lateral

Ao lado da área de conteúdo principal da página de perfil de dispositivo está a barra lateral.

![Imagem da guia da barra lateral do perfil do dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

A barra lateral lista o nome completo do dispositivo e o nível de exposição. Ele também fornece algumas informações básicas importantes em subseções pequenas que podem ser alternadas abertas ou fechadas, como:

* **Marcas** - Qualquer Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade ou marcas personalizadas associadas ao dispositivo. As marcas do Microsoft Defender para Identidade não são editáveis.
* **Informações de** segurança - Abrir incidentes e alertas ativos. Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibirão o nível de exposição e o nível de risco.

> [!TIP]
> O nível de exposição se relaciona com o quanto o dispositivo está em conformidade com as recomendações de segurança, enquanto o nível de risco é calculado com base em vários fatores, incluindo os tipos e a gravidade dos alertas ativos.

* **Detalhes do** dispositivo - Domínio, sistema operacional, data e hora de quando o dispositivo foi visto pela primeira vez, endereços IP, recursos. Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibem o estado de saúde. Os dispositivos inscritos no Microsoft Defender para Identidade exibirão o nome SAM e um timestamp de quando o dispositivo foi criado pela primeira vez.
* **Atividade de** rede - Timestamps pela primeira e última vez em que o dispositivo foi visto na rede.
* **Dados de** diretório (*somente para dispositivos* inscritos no Microsoft Defender para Identidade ) - sinalizadores [UAC,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)e associações de grupo.

## <a name="response-actions"></a>Ações de resposta

As ações de resposta oferecem uma maneira rápida de se defender contra e analisar ameaças.

![Imagem da barra de ações para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [As ações de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) resposta só estarão disponíveis se o dispositivo estiver inscrito no Microsoft Defender para o Ponto de Extremidade.
> * Os dispositivos que estão inscritos no Microsoft Defender para o Ponto de Extremidade podem exibir números diferentes de ações de resposta, com base no sistema operacional e no número de versão do dispositivo.

As ações disponíveis na página de perfil de dispositivo incluem:

* **Gerenciar marcas** – atualiza as marcas personalizadas que você aplicou a este dispositivo.
* **Isolar dispositivo** - isola o dispositivo da rede da sua organização, mantendo-o conectado ao Microsoft Defender para o ponto de extremidade. Você pode optar por permitir que o Outlook, o Teams e o Skype for Business seja executado enquanto o dispositivo está isolado, para fins de comunicação.
* **Central de Ações** - Exibir o status das ações enviadas. Disponível somente se outra ação já tiver sido selecionada.
* **Restringir a execução do** aplicativo - Impede que aplicativos não assinados pela Microsoft sejam executados.
* **Executar a verificação antivírus** - atualiza as definições do Windows Defender Antivírus e executa imediatamente uma verificação antivírus. Escolha entre a Verificação Rápida ou a Verificação Completa.
* **Coletar pacote de investigação** - Coleta informações sobre o dispositivo. Quando a investigação for concluída, você poderá baixá-la.
* **Iniciar Sessão de Resposta Ao** Vivo - Carrega um shell remoto no dispositivo para [investigações de segurança aprofundadas.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* **Iniciar investigação automatizada** - Investiga [e remedia automaticamente ameaças.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Embora você possa disparar manualmente investigações automatizadas para executar a partir desta [página,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) determinadas políticas de alerta disparam investigações automáticas por conta própria.
* **Central de Ações** - Exibe informações sobre quaisquer ações de resposta que estão sendo executados no momento.

## <a name="tabs-section"></a>Seção Tabs

As guias de perfil de dispositivo permitem que você alterne uma visão geral dos detalhes de segurança sobre o dispositivo e tabelas que contêm uma lista de alertas.

Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibirão guias que apresentam uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e KBs ausentes (atualizações de segurança).

### <a name="overview-tab"></a>Guia Visão geral

A guia padrão é Visão **geral.** Ele fornece uma rápida olhada no fato de segurança mais importante sobre o dispositivo.

![Imagem da guia visão geral do perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Aqui, você pode ver rapidamente os alertas ativos do dispositivo e os usuários conectados no momento.

Se o dispositivo estiver inscrito no Microsoft Defender para o Ponto de Extremidade, você também verá o nível de risco do dispositivo e quaisquer dados disponíveis em avaliações de segurança. As avaliações de segurança descrevem o nível de exposição do dispositivo, fornecem recomendações de segurança e listam softwares afetados e vulnerabilidades descobertas.

### <a name="alerts-tab"></a>Guia Alertas

A **guia Alertas** contém uma lista de alertas que foram gerados no dispositivo, do Microsoft Defender para Identidade e do Microsoft Defender para Ponto de Extremidade.

![Imagem da guia alertas do perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item. O comportamento padrão é listar trinta itens por página.

As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como o status, o estado de investigação e a quem o alerta foi atribuído.

A *coluna de entidades* afetada refere-se ao dispositivo (entidade) cujo perfil você está visualizando no momento, além de quaisquer outros dispositivos em sua rede afetados.

Selecionar um item dessa lista abrirá um flyout contendo ainda mais informações sobre o alerta selecionado.

Essa lista pode ser filtrada por gravidade, status ou a quem o alerta foi atribuído.

### <a name="timeline-tab"></a>Guia Linha do tempo

A **guia Linha** do Tempo inclui um gráfico interativo e cronológica de todos os eventos gerados no dispositivo. Movendo a área realçada do gráfico para a esquerda ou para a direita, você pode exibir eventos em diferentes períodos de tempo. Você também pode escolher um intervalo personalizado de datas no menu suspenso entre o gráfico interativo e a lista de eventos.

Abaixo do gráfico há uma lista de eventos para o intervalo de datas selecionado.

![Imagem da guia linha do tempo do perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

O número de itens exibidos e as colunas na lista podem ser personalizadas. As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.

Selecionar um item dessa lista abrirá um flyout exibindo um gráfico de entidades de evento, mostrando os processos pai e filho envolvidos no evento.

A lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do Registro ou Eventos de Tela Inteligente.

A lista também pode ser exportada para um arquivo CSV, para download. Embora o arquivo não seja limitado pelo número de eventos, o intervalo máximo de tempo que você pode optar por exportar é de sete dias.

### <a name="security-recommendations-tab"></a>Guia Recomendações de segurança

A **guia Recomendações de** segurança lista ações que você pode tomar para proteger o dispositivo. Selecionar um item nessa lista abrirá um flyout onde você pode obter instruções sobre como aplicar a recomendação.

![Imagem da guia recomendações de segurança para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Assim como nas guias anteriores, o número de itens exibidos por página, bem como as colunas visíveis, podem ser personalizados.

O modo de exibição padrão inclui colunas que detalham os pontos fracos de segurança abordados, a ameaça associada, o componente ou software relacionado afetado pela ameaça e muito mais. Os itens podem ser filtrados pelo status da recomendação.

### <a name="software-inventory"></a>Inventário de software

A **guia Inventário de** software lista o software instalado no dispositivo.

![Imagem da guia inventário de software para perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

O modo de exibição padrão exibe o fornecedor do software, o número de versão instalado, o número de pontos fracos conhecidos do software, as informações sobre ameaças, o código do produto e as marcas. O número de itens exibidos e quais colunas são exibidas podem ser personalizadas.

Selecionar um item dessa lista abre um flyout contendo mais detalhes sobre o software selecionado, bem como o caminho e o timestamp da última vez em que o software foi encontrado.

Essa lista pode ser filtrada por código de produto.

### <a name="discovered-vulnerabilities-tab"></a>Guia Vulnerabilidades descobertas

A **guia Vulnerabilidades descobertas** lista todas as vulnerabilidades comuns e explorações (CVEs) que podem afetar o dispositivo.

![Imagem da guia vulnerabilidades descobertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

O modo de exibição padrão lista a gravidade do CVE, a Pontuação de Vulnerabilidade Comum (CVS), o software relacionado ao CVE, quando o CVE foi publicado, quando o CVE foi atualizado pela última vez e as ameaças associadas ao CVE.

Assim como nas guias anteriores, o número de itens exibidos e quais colunas estão visíveis podem ser personalizados.

Selecionar um item dessa lista abrirá um flyout que descreve o CVE.

### <a name="missing-kbs"></a>KBs ausentes

A **guia KBs ausentes** lista todas as Atualizações da Microsoft que ainda devem ser aplicadas ao dispositivo. Os "KBs" em questão são [artigos da Base de](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) Dados de Conhecimento que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Imagem da guia kbs ausente para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

O modo de exibição padrão lista o boletim que contém as atualizações, a versão do sistema operacional, os produtos afetados, os CVEs endereçados, o número KB e as marcas.

O número de itens exibidos por página e quais colunas são exibidas podem ser personalizadas.

Selecionar um item abrirá um flyout que se vincula à atualização.

## <a name="related-topics"></a>Tópicos relacionados

* [Visão geral do Microsoft 365 Defender](microsoft-threat-protection.md)
* [Ativar o Microsoft 365 Defender](mtp-enable.md)
* [Investigar entidades em dispositivos usando resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Investigação e resposta automatizadas (AIR) no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
