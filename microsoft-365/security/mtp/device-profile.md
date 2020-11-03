---
title: Perfil de dispositivo no portal de segurança do Microsoft 365
description: Exibir os níveis de risco e de exposição de um dispositivo em sua organização. Analise as ameaças passadas e apresente e proteja o dispositivo com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, proteção contra ameaças da Microsoft, MTP, central de segurança, Microsoft defender ATP, Office 365 ATP, Azure ATP, página de dispositivo, perfil de dispositivo, página de máquina, perfil de máquina
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843847"
---
# <a name="device-profile-page"></a>Página de perfil de dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


O portal de segurança do Microsoft 365 fornece páginas de perfil de dispositivo para que você possa avaliar rapidamente a integridade e o status dos dispositivos na sua rede.

> [!IMPORTANT]
> A página de perfil de dispositivo pode parecer um pouco diferente, dependendo se o dispositivo está inscrito no Microsoft defender para ponto de extremidade, Microsoft defender para identidade ou ambos.

Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também pode usar a página de perfil de dispositivo para executar algumas tarefas comuns de segurança.

## <a name="navigating-the-device-profile-page"></a>Navegando na página de perfil do dispositivo

A página de perfil é dividida em várias seções abrangentes.

![Imagem da página de perfil do dispositivo com (1) área da guia (2) barra lateral e (3) ações realçadas em vermelho](../../media/mtp-device-profile/hybrid-device-overall.png)

A barra lateral (1) lista detalhes básicos sobre o dispositivo.

A área de conteúdo principal (2) contém guias que você pode alternar para exibir diferentes tipos de informações sobre o dispositivo.

Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também verá uma lista de ações de resposta (3). As ações de resposta permitem que você realize tarefas comuns relacionadas à segurança.

## <a name="sidebar"></a>Cepções

Ao lado da área de conteúdo principal da página de perfil de dispositivo é a barra lateral.

![Imagem da guia de barra lateral para perfil de dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

A barra lateral lista o nome completo do dispositivo e o nível de exposição. Ele também fornece algumas informações básicas importantes em subseções pequenas que podem ser ativadas ou abertas ou fechadas, como:

* **Marcas** -qualquer Microsoft defender para ponto de extremidade, Microsoft defender para identidade ou marcas personalizadas associadas ao dispositivo. Marcas do Microsoft defender for Identity não são editáveis.
* **Informações de segurança** -incidentes abertos e alertas ativos. Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibirão o nível de exposição e o nível de risco.

> [!TIP]
> O nível de exposição se relaciona com o quanto o dispositivo está em conformidade com as recomendações de segurança, enquanto o nível de risco é calculado com base em vários fatores, incluindo os tipos e a gravidade dos alertas ativos.

* **Detalhes do dispositivo** -domínio, sistema operacional, carimbo de data/hora para o momento em que o dispositivo foi visto pela primeira vez, endereços IP, recursos. Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibem o estado de integridade. Os dispositivos registrados no Microsoft defender para identidade exibirão o nome SAM e um carimbo de data/hora para quando o dispositivo foi criado pela primeira vez.
* **Atividade de rede** -carimbos de data/hora pela primeira vez e última vez em que o dispositivo foi visto na rede.
* **Dados de diretório** ( *somente para dispositivos registrados no Microsoft defender para identidade* )-sinalizadores de [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)e associações de grupo.

## <a name="response-actions"></a>Ações de resposta

As ações de resposta oferecem uma maneira rápida de se defender e analisar ameaças.

![Imagem da barra de ações para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * As [ações de resposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) só estarão disponíveis se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade.
> * Os dispositivos que estão registrados no Microsoft defender para ponto de extremidade podem exibir números diferentes de ações de resposta, com base no so do dispositivo e no número da versão.

As ações disponíveis na página perfil do dispositivo incluem:

* **Manage Tags** – atualiza as marcas personalizadas que você aplicou a este dispositivo.
* **Isolar dispositivo** -isola o dispositivo da rede da sua organização enquanto o mantém conectado ao Microsoft defender para ponto de extremidade. Você pode optar por permitir que o Outlook, o Teams e o Skype for Business sejam executados enquanto o dispositivo é isolado, para fins de comunicação.
* **Central de ações** -exiba o status das ações enviadas. Disponível somente se outra ação já tiver sido selecionada.
* **Restringir execução de aplicativo** -impede que aplicativos não assinados pela Microsoft sejam executados.
* **Execute verificação antivírus** – atualiza as definições do Windows Defender antivírus e executa imediatamente uma verificação antivírus. Escolha entre verificação rápida ou verificação completa.
* **Coletar pacote de investigação** -coleta informações sobre o dispositivo. Quando a investigação estiver concluída, você pode baixá-la.
* **Iniciar sessão de resposta ao vivo** – carrega um shell remoto no dispositivo para [investigações de segurança aprofundadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Iniciar investigação automatizada** - [investiga e corrige ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automaticamente. Embora seja possível disparar manualmente as investigações automatizadas para executar a partir desta página, [determinadas políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) disparam investigações automáticas por conta própria.
* **Central de ações** -exibe informações sobre as ações de resposta que estão em execução no momento.

## <a name="tabs-section"></a>Seção Tabs

As guias de perfil de dispositivo permitem que você alterne uma visão geral dos detalhes de segurança sobre o dispositivo e tabelas que contenham uma lista de alertas.

Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibirão guias que apresentam uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e os KBs ausentes (atualizações de segurança).

### <a name="overview-tab"></a>Guia Visão geral

A guia padrão é **visão geral**. Ele fornece uma visão rápida do fato de segurança mais importante sobre o dispositivo.

![Imagem da guia Visão geral do perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Aqui, você pode obter uma visão rápida dos alertas ativos do dispositivo e de qualquer usuário conectado no momento.

Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também verá o nível de risco do dispositivo e quaisquer dados disponíveis sobre avaliações de segurança. As avaliações de segurança descrevem o nível de exposição do dispositivo, fornecem recomendações de segurança e listam softwares afetados e vulnerabilidades descobertas.

### <a name="alerts-tab"></a>Guia alertas

A guia **alertas** contém uma lista de alertas que foram gerados no dispositivo, do Microsoft defender for Identity e do Microsoft defender para ponto de extremidade.

![Imagem da guia alertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item. O comportamento padrão é listar trinta itens por página.

As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como o status, o estado de investigação e a quem o alerta foi atribuído.

A coluna de *entidades impactadas* se refere ao dispositivo (entidade) cujo perfil você está exibindo atualmente, além de outros dispositivos na rede que são afetados.

Selecionar um item da lista abrirá um submenu que contém ainda mais informações sobre o alerta selecionado.

Essa lista pode ser filtrada por severidade, status ou quem foi atribuído ao alerta.

### <a name="timeline-tab"></a>Guia linha do tempo

A guia **linha do tempo** inclui um gráfico interativo e cronológico de todos os eventos gerados no dispositivo. Ao mover a área realçada do gráfico para a esquerda ou direita, você pode exibir eventos por diferentes períodos de tempo. Você também pode escolher um intervalo de datas personalizado no menu suspenso entre o gráfico interativo e a lista de eventos.

Abaixo do gráfico há uma lista de eventos para o intervalo de datas selecionado.

![Imagem da guia linha do tempo para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

O número de itens exibidos e as colunas na lista podem ser personalizados. As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.

Selecionar um item da lista abrirá um submenu que exibe um gráfico de entidades de evento, mostrando os processos pai e filho envolvidos no evento.

A lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do registro ou eventos de tela inteligente.

A lista também pode ser exportada para um arquivo CSV para download. Embora o arquivo não seja limitado por número de eventos, o intervalo de tempo máximo que você pode escolher para exportar é de sete dias.

### <a name="security-recommendations-tab"></a>Guia recomendações de segurança

A guia **recomendações de segurança** lista as ações que você pode tomar para proteger o dispositivo. Selecionar um item nessa lista abrirá um submenu onde você pode obter instruções sobre como aplicar a recomendação.

![Imagem da guia recomendações de segurança para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Assim como com as guias anteriores, o número de itens exibidos por página, bem como quais colunas estão visíveis, podem ser personalizados.

O modo de exibição padrão inclui colunas que detalham as desvantagens de segurança abordadas, a ameaça associada, o componente relacionado ou o software afetado pela ameaça e muito mais. Os itens podem ser filtrados pelo status da recomendação.

### <a name="software-inventory"></a>Inventário de software

A guia **inventário de software** lista o software instalado no dispositivo.

![Imagem da guia Inventário de software para o perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

O modo de exibição padrão exibe o fornecedor do software, o número da versão instalada, o número de deficiências de software conhecidas, informações sobre ameaças, código do produto e marcas. O número de itens exibidos e quais colunas são exibidas podem ser personalizados.

Selecionar um item dessa lista abre um submenu contendo mais detalhes sobre o software selecionado, bem como o caminho e o carimbo de data/hora da última vez que o software foi encontrado.

Essa lista pode ser filtrada pelo código do produto.

### <a name="discovered-vulnerabilities-tab"></a>Guia vulnerabilidades descobertas

A guia **vulnerabilidades descobertas** lista as vulnerabilidades e explorações comuns (CVEs) que podem afetar o dispositivo.

![Imagem da guia vulnerabilidades descobertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

O modo de exibição padrão lista a gravidade do CVE, a pontuação de vulnerabilidade comum (CVS), o software relacionado ao CVE, quando o CVE foi publicado, quando o CVE foi atualizado pela última vez e ameaças associadas ao CVE.

Assim como as guias anteriores, o número de itens exibidos e as colunas visíveis podem ser personalizados.

Selecionar um item da lista abrirá um submenu que descreve o CVE.

### <a name="missing-kbs"></a>KB ausentes

A guia **KB ausentes** lista as atualizações da Microsoft que ainda devem ser aplicadas ao dispositivo. Os "KBs" em questão são [artigos da base de conhecimento](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Imagem da guia ausente de KB para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

O modo de exibição padrão lista o boletim que contém as atualizações, a versão do sistema operacional, os produtos afetados, os CVEs tratados, o número do KB e as marcas.

O número de itens exibidos por página e quais colunas são exibidas podem ser personalizados.

Selecionar um item abrirá um submenu que vincule à atualização.

## <a name="related-topics"></a>Tópicos relacionados

* [Visão geral do Microsoft 365 defender](microsoft-threat-protection.md)
* [Ativar o Microsoft 365 defender](mtp-enable.md)
* [Investigar entidades em dispositivos, usando resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Investigação e resposta automatizadas (AIR) no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
