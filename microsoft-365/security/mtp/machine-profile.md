---
title: Perfil do computador no portal de segurança do Microsoft 365
description: Exibir os níveis de risco e de exposição de um dispositivo em sua organização. Analise as ameaças passadas e apresente e proteja a máquina com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, proteção contra ameaças da Microsoft, MTP, central de segurança, Microsoft defender ATP, Office 365 ATP, Azure ATP, página de máquina, lista de máquina, perfil de máquina
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
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895458"
---
# <a name="machine-profile-page"></a>Página do perfil da máquina

O portal de segurança do Microsoft 365 fornece páginas de perfil de máquina para que você possa avaliar a integridade e o status dos dispositivos na sua rede. Cada página de perfil de máquina contém uma infinidade de informações sobre o dispositivo.

Você pode revisar informações detalhadas sobre qual software é executado, os eventos de segurança e os alertas de segurança passados e apresentar e encontrar links para patches de software relevantes.

Você também pode usar o perfil de máquina para executar tarefas comuns relacionadas à segurança e rapidamente examinar detalhes básicos sobre o dispositivo.

## <a name="navigating-the-machine-profile-page"></a>Navegando na página de perfil de máquina

A página de perfil de máquina é dividida em três seções.

![Imagem da página de perfil da máquina com (1) barra de guias (2) barra lateral e (3) ações realçadas em vermelho](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

A área de conteúdo principal (1) contém sete guias que podem ser alternadas para exibir diferentes tipos de informações sobre a máquina.

A barra lateral (2) lista detalhes básicos sobre o computador.

Há também ações de resposta disponíveis em um cabeçalho (3) antes da barra lateral e das seções de conteúdo principal. Você pode usar as ações neste cabeçalho para executar tarefas comuns relacionadas à segurança.

## <a name="tabs-section"></a>Seção Tabs

As guias de perfil de máquina permitem que você alterne uma visão geral dos detalhes de segurança sobre a máquina e tabelas que contenham uma lista de alertas, uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e faltam KBs (atualizações de segurança).

### <a name="overview-tab"></a>Guia Visão geral

A guia padrão é **visão geral**. Ele fornece uma visão rápida do fato de segurança mais importante sobre o dispositivo.

![Imagem da guia Visão geral do perfil do computador](../../media/mtp-machine-profile/overview.png)

Aqui, você pode encontrar um gráfico do nível de risco e dos alertas ativos do dispositivo, qualquer usuário conectado no momento, uma breve lista de usuários mais e menos frequentes e avaliações de segurança que detalham o nível de exposição do dispositivo, recomendações de segurança, softwares afetados e vulnerabilidades descobertas.

### <a name="alerts-tab"></a>Guia alertas

A guia **alertas** contém uma lista de alertas que foram relatados no dispositivo.

![Imagem da guia alertas para o perfil de máquina](../../media/mtp-machine-profile/alerts.png)

Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item. O comportamento padrão é listar 30 itens por página e ter 11 colunas alternadas para exibir.

As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como o status, o estado de investigação e quem se o alerta foi atribuído.

A coluna de *entidades impactadas* se refere à máquina (entidade) cujo perfil você está exibindo atualmente, além de qualquer outra máquina em sua rede afetada.

Selecionar um item da lista abrirá um link para o alerta selecionado.

Essa lista pode ser filtrada por severidade, status ou destinatário.

### <a name="timeline-tab"></a>Guia linha do tempo

A guia **linha do tempo** inclui um gráfico de eventos interativo e cronológico gerado no dispositivo. Ao mover a área realçada do gráfico, você pode exibir eventos por diferentes intervalos de tempo. Você também pode digitar um intervalo de datas personalizado.

Abaixo do gráfico há uma lista de eventos para o intervalo de datas selecionado.

![Imagem da guia linha do tempo para o perfil do computador](../../media/mtp-machine-profile/timeline.png)

O número de itens exibidos e as colunas na lista podem ser personalizados. As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.

Selecionar um item da lista abrirá um submenu que exibe um gráfico de entidades de evento, mostrando os processos pai e filho que acionaram o evento.

Essa lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do registro ou eventos de tela inteligente.

### <a name="security-recommendations-tab"></a>Guia recomendações de segurança

A guia **recomendações de segurança** lista as ações que você pode tomar para proteger o dispositivo. Selecionar um item nessa lista abrirá um submenu onde você pode obter instruções sobre como aplicar a recomendação.

![Imagem da guia recomendações de segurança para o perfil de máquina](../../media/mtp-machine-profile/security-recs.png)

Como com as guias anteriores, o número de itens exibidos por página e quais colunas estão visíveis podem ser personalizados.

O modo de exibição padrão inclui colunas que detalham as desvantagens de segurança abordadas, a ameaça associada, o componente relacionado ou o software afetado pela ameaça e muito mais. Os itens podem ser filtrados pelo status da recomendação.

### <a name="software-inventory"></a>Inventário de software

A guia **inventário de software** lista o software instalado no dispositivo.

![Imagem da guia Inventário de software para o perfil de máquina](../../media/mtp-machine-profile/software-inventory.png)

O modo de exibição padrão exibe o fornecedor do software, o número da versão instalada, o número de deficiências de software conhecidas, informações sobre ameaças, código do produto e marcas. O número de itens exibidos e quais colunas são exibidas podem ser personalizados.

Selecionar um item dessa lista abre um submenu contendo mais detalhes sobre o software selecionado, bem como o caminho e o carimbo de data/hora da última vez que o software foi encontrado.

Essa lista pode ser filtrada pelo código do produto.

### <a name="discovered-vulnerabilities-tab"></a>Guia vulnerabilidades descobertas

A guia **vulnerabilidades descobertas** lista as vulnerabilidades e explorações comuns (CVEs) que podem afetar o dispositivo.

![Imagem da guia de vulnerabilidades descobertas para o perfil de máquina](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

O modo de exibição padrão lista a gravidade do CVE, a pontuação de vulnerabilidade comum (CVS), o software relacionado ao CVE, quando o CVE foi publicado, quando o CVE foi atualizado pela última vez e ameaças associadas ao CVE.

Assim como as guias anteriores, o número de itens exibidos e as colunas visíveis podem ser personalizados.

Selecionar um item da lista abrirá um submenu que descreve o CVE.

### <a name="missing-kbs"></a>KB ausentes

A guia **KB ausentes** lista as atualizações da Microsoft que ainda devem ser aplicadas ao computador. Os "KBs" em questão são [artigos da base de conhecimento](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Imagem da guia ausente de KB para o perfil de máquina](../../media/mtp-machine-profile/missing-kbs.PNG)

O modo de exibição padrão lista o boletim que contém as atualizações, a versão do sistema operacional, os produtos afetados, os CVEs tratados, o número do KB e as marcas.

O número de itens exibidos por página e quais colunas são exibidas podem ser personalizados.

Selecionar um item abrirá um submenu que vincule à atualização.

## <a name="sidebar"></a>Cepções

Ao lado da área de conteúdo principal da página de perfil de máquina é a barra lateral.

![Imagem da guia de barra lateral para perfil de máquina](../../media/mtp-machine-profile/sidebar.png)

A barra lateral fornece algumas informações básicas importantes em subseções pequenas que podem ser ativadas ou abertas ou fechadas:

* **Marcas** -qualquer marca associada ao dispositivo
* **Informações de segurança** -incidentes de abertura, alertas ativos, nível de exposição e nível de risco
* **Detalhes do dispositivo** -domínio, sistema operacional, grupo de ativos, estado de integridade, confidencialidade de dados e endereços IP
* **Atividade de rede** -carimbos de data/hora pela primeira vez e última vez em que o dispositivo foi visto na rede

Esta seção também inclui o nível de nome e exposição do dispositivo e um ícone para indicar se ele está ativo na rede no momento.

## <a name="response-actions"></a>Ações de resposta

As ações de resposta oferecem uma maneira rápida de se defender e analisar ameaças.

![Imagem da guia de barra lateral para perfil de máquina](../../media/mtp-machine-profile/actions.PNG)

As ações de resposta disponíveis aqui incluem:

* **Manage Tags** – atualiza as marcas personalizadas que você aplicou a este dispositivo.
* **Isolar computador** -isola a máquina da rede da sua organização enquanto a mantém conectada à proteção avançada contra ameaças do Microsoft defender. Você pode optar por permitir que o Outlook, o Teams e o Skype for Business sejam executados enquanto a máquina estiver isolada, para fins de comunicação.
* **Restringir execução de aplicativo** -impede que aplicativos não assinados pela Microsoft sejam executados
* **Execute verificação antivírus** – atualiza as definições do Windows Defender antivírus e executa imediatamente uma verificação antivírus. Escolha entre verificação rápida ou verificação completa.
* **Coletar pacote de investigação** -coleta informações sobre o computador. Quando a investigação estiver concluída, você pode baixá-la.
* **Iniciar sessão de resposta ao vivo** – carrega um shell remoto no computador para [investigações de segurança aprofundadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Iniciar investigação automatizada** - [investiga e corrige ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automaticamente. Embora seja possível disparar manualmente as investigações automatizadas para executar a partir desta página, [determinadas políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) disparam investigações automáticas por conta própria.
* **Central de ações** -exiba o status das ações enviadas. Disponível somente se outra ação já tiver sido selecionada.

## <a name="related-topics"></a>Tópicos relacionados

* [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
* [Habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md)
* [Investigar entidades em máquinas usando resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Investigação e resposta automatizadas (AIR) no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
