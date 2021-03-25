---
title: Visão geral do portal do Microsoft Defender para Ponto de Extremidade
description: O Centro de Segurança do Microsoft Defender pode monitorar sua rede corporativa e ajudar a responder a possíveis ameaças persistentes (APT) ou violações de dados.
keywords: Centro de Segurança do Microsoft Defender, portal, inteligência contra ameaças de segurança cibernética, painel, fila de alertas, lista de dispositivos, configurações, gerenciamento de dispositivos, ataques avançados
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186216"
---
# <a name="microsoft-defender-security-center-portal-overview"></a>Visão geral do portal do Centro de Segurança do Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

As equipes de segurança corporativas podem usar o Centro de Segurança do Microsoft Defender para monitorar e ajudar a responder a alertas de possíveis atividades avançadas de ameaças persistentes ou violações de dados.

Você pode usar o [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/) para:

- Exibir, classificar e alertas de triagem de seus pontos de extremidade
- Pesquisar mais informações sobre indicadores observados, como arquivos e endereços IP
- Alterar as configurações do Microsoft Defender para Ponto de Extremidade, incluindo fuso horário e informações de licenciamento de revisão

## <a name="microsoft-defender-security-center"></a>Centro de Segurança do Microsoft Defender

Ao abrir o portal, você verá:

- (1) Painel de navegação (selecione as linhas horizontais na parte superior do painel de navegação para mostrar ou ocultar)
- (2) Pesquisa, Centro da comunidade, Localização, Ajuda e suporte, Feedback

 ![Portal do Microsoft Defender para Ponto de Extremidade](images/mdatp-portal-overview.png)

> [!NOTE]
> As detecções relacionadas a malware só serão exibidas se seus dispositivos estão usando o Microsoft Defender Antivírus como o produto antimalware de proteção em tempo real padrão.

Você pode navegar pelo portal usando as opções de menu disponíveis em todas as seções. Consulte a tabela a seguir para ver uma descrição de cada seção.

Área | Descrição
:---|:---
**(1) Painel de navegação** | Use o painel de navegação para se mover entre Painéis, **Incidentes,** Lista de Dispositivos, Fila de  **Alertas, Investigações** **Automatizadas,** Busca **Avançada,** **Relatórios** **&, APIs** de Parceiros, Gerenciamento de **Vulnerabilidades**& Ameaças, Avaliação e **tutoriais,** **Saúde** do **serviço,** Gerenciamento de configuração e **Configurações.** Selecione as linhas horizontais na parte superior do painel de navegação para mostrar ou ocultar.
**Painéis** | Acesse as investigações automatizadas ativas, alertas ativos, estatísticas de investigações automatizadas, dispositivos em risco, usuários em risco, dispositivos com problemas de sensor, saúde do serviço, fontes de detecção e painéis de relatórios de dispositivos diários.
**Incidentes** | Exibir alertas que foram agregados como incidentes.
**Lista de dispositivos** | Exibe a lista de dispositivos que estão internados no Defender for Endpoint, algumas informações sobre eles e seus níveis de exposição e risco.
**Fila de alertas** | Exibir alertas gerados de dispositivos em suas organizações.
**Investigações automatizadas** | Exibe investigações automatizadas que foram conduzidas na rede, disparando alerta, o status de cada investigação e outros detalhes, como quando a investigação começou e a duração da investigação.
**Busca avançada** | A busca avançada permite que você pesquise e investigue proativamente em toda a sua organização usando uma ferramenta de pesquisa e consulta avançada.
**Relatórios** | Exibir gráficos detalhando a proteção contra ameaças, a conformidade e a saúde do dispositivo, a proteção da Web e a vulnerabilidade.
**Parceiros & APIs** | Exibir conexões de parceiros com suporte, que aprimoram os recursos de detecção, investigação e inteligência contra ameaças da plataforma. Você também pode exibir aplicativos conectados, o explorador de API, a visão geral de uso da API e as configurações de exportação de dados.
**Gerenciamento de & de vulnerabilidades** | Exibir a Pontuação Segura da Microsoft para Dispositivos, a pontuação de exposição, os dispositivos expostos, o software vulnerável e tomar medidas sobre as principais recomendações de segurança.
**Avaliação e tutoriais** | Gerenciar dispositivos de teste, simulações de ataque e relatórios. Aprenda e experimente os recursos do Defender para Ponto de Extremidade por meio de um passo a passo guiado em um ambiente de avaliação.
**Integridade do Serviço** | Fornece informações sobre o status atual do serviço Defender para Ponto de Extremidade. Você poderá verificar se a saúde do serviço está saudável ou se há problemas atuais.
**Gerenciamento de configuração** | Exibe dispositivos a bordo, linha de base de segurança de suas organizações, análise preditiva, cobertura de proteção da Web e permite que você execute o gerenciamento de superfície de ataque em seus dispositivos.
**Settings** | Mostra as configurações selecionadas durante a integração e permite atualizar suas preferências do setor e o período da política de retenção. Você também pode definir outras configurações, como permissões, APIs, regras, gerenciamento de dispositivos, gerenciamento de serviço de TI e avaliações de rede.
**(2) Pesquisa, Centro da comunidade, Localização, Ajuda e suporte, Feedback** | **Pesquisa** - pesquisa por dispositivo, arquivo, usuário, URL, IP, vulnerabilidade, software e recomendação. </br></br> **Centro de comunidade** - Acesse o Centro da Comunidade para aprender, colaborar e compartilhar experiências sobre o produto. </br></br>  **Localização** - Definir fusos horário. </br></br>  **Ajuda e** suporte - Acesse o guia Defender para Ponto de Extremidade, suporte da Microsoft e Microsoft Premier, informações de licença, simulações & tutoriais, laboratório de avaliação do Defender para Ponto de Extremidade, consulte um especialista em ameaças.</br></br> **Comentários** - Forneça comentários sobre o que você gosta ou o que podemos fazer melhor.

> [!NOTE]
> Para dispositivos com problemas de dimensionamento de DPI de alta resolução, consulte Problemas de dimensionamento do Windows para dispositivos de [alta DPI](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) para possíveis soluções.

## <a name="microsoft-defender-for-endpoint-icons"></a>Ícones do Microsoft Defender para Ponto de Extremidade

A tabela a seguir fornece informações sobre os ícones usados em todo o portal:

Ícone | Descrição
:---|:---
![Ícone de logotipo atp](images/atp-logo-icon.png)| Logotipo do Microsoft Defender para Ponto de Extremidade
![Ícone de alerta](images/alert-icon.png)| Alerta – Indicação de uma atividade correlacionada com ataques avançados.
![Ícone de detecção](images/detection-icon.png)| Detecção – Indicação de uma detecção de ameaças de malware.
![Ícone de ameaça ativa](images/active-threat-icon.png)| Ameaça ativa – Ameaças sendo executadas ativamente no momento da detecção.
![Ícone remediado1](images/remediated-icon.png)| Correção – Ameaça removida do dispositivo.
![Ícone não remediado](images/not-remediated-icon.png)| Não remediada – Ameaça não removida do dispositivo.
![Ícone thunderbolt](images/atp-thunderbolt-icon.png)| Indica eventos que dispararam um alerta na árvore **do processo de alerta.**
![Ícone do dispositivo](images/atp-machine-icon.png)| Ícone do dispositivo
![Ícone de eventos do Microsoft Defender AV](images/atp-windows-defender-av-events-icon.png)| Eventos do Microsoft Defender Antivírus
![Ícone de eventos do Application Guard](images/atp-Application-Guard-events-icon.png)| Windows Defender eventos do Application Guard
![Ícone de eventos do Device Guard](images/atp-Device-Guard-events-icon.png)| Windows Defender eventos do Device Guard
![Ícone de eventos do Exploit Guard](images/atp-Exploit-Guard-events-icon.png)| Windows Defender eventos do Exploit Guard
![Ícone de eventos SmartScreen](images/atp-Smart-Screen-events-icon.png)| Windows Defender eventos SmartScreen
![Ícone de eventos de firewall](images/atp-Firewall-events-icon.png)| Eventos do Firewall do Windows
![Ícone de ação de resposta](images/atp-respond-action-icon.png)| Ação de resposta
![Ícone de eventos de processo](images/atp-process-event-icon.png)| Processar eventos
![Ícone de eventos de comunicação de rede](images/atp-network-communications-icon.png)| Eventos de rede
![Ícone de eventos observados por arquivo](images/atp-file-observed-icon.png)| Eventos de arquivo
![Ícone de eventos do Registro](images/atp-registry-event-icon.png)| Eventos do Registro
![Ícone de eventos DLL de carregamento de módulo](images/atp-module-load-icon.png)| Carregar eventos DLL
![Ícone de outros eventos](images/atp-Other-events-icon.png)| Outros eventos
![Ícone de modificação de token de acesso](images/atp-access-token-modification-icon.png)| Modificação de token de acesso
![Ícone de criação de arquivo](images/atp-file-creation-icon.png)| Criação de arquivos
![Ícone do signator](images/atp-signer-icon.png)| Signer
![Ícone do caminho do arquivo](images/atp-File-path-icon.png)| Caminho do arquivo
![Ícone de linha de comando](images/atp-command-line-icon.png)| Linha de comando
![Ícone de arquivo não assinado](images/atp-unsigned-file-icon.png)| Arquivo não assinado
![Ícone de árvore de processo](images/atp-process-tree.png)| Árvore de processos
![Ícone de alocação de memória](images/atp-memory-allocation-icon.png)| Alocação de memória
![Ícone de injeção de processo](images/atp-process-injection.png)| Injeção de processo
![Ícone de executar comando do Powershell](images/atp-powershell-command-run-icon.png)| Executar o comando do Powershell
![Ícone do Centro de Comunidade](images/atp-community-center.png) | Centro de comunidade
![Ícone de notificações](images/atp-notifications.png) | Notificações
![Nenhuma ameaça encontrada](images/no-threats-found.png) | Investigação automatizada - nenhuma ameaça encontrada
![Ícone com falha](images/failed.png) | Investigação automatizada - falha
![Ícone parcialmente remediado](images/partially-investigated.png) | Investigação automatizada - parcialmente investigada
![Encerrado pelo sistema](images/terminated-by-system.png) | Investigação automatizada - encerrada pelo sistema
![Ícone pendente](images/pending.png) | Investigação automatizada - pendente
![Ícone de execução](images/running.png) | Investigação automatizada - em execução
![Ícone remediado2](images/remediated.png) | Investigação automatizada - correção
![Ícone parcialmente investigado](images/partially_remediated.png) | Investigação automatizada - parcialmente remediada
![Ícone de insights de ameaça](images/tvm_bug_icon.png) | Gerenciamento & de Vulnerabilidades - insights sobre ameaças
![Ícone de alerta ativo possível](images/tvm_alert_icon.png) | Gerenciamento & de Vulnerabilidades - alerta ativo possível
![Ícone de insights de recomendação](images/tvm_insight_icon.png) | Gerenciamento & de Vulnerabilidades - insights de recomendação

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Centro de Segurança do Microsoft Defender](use.md)
- [Exibir o painel de operações de segurança](security-operations-dashboard.md)
- [Exibir o painel gerenciamento de & de vulnerabilidades](tvm-dashboard-insights.md)
- [Exibir o painel de análise de ameaças e tomar ações de mitigação recomendadas](threat-analytics.md)
