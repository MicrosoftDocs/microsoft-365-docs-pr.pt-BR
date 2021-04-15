---
title: IDs de evento do Microsoft Defender AV e códigos de erro
description: Procure as causas e soluções para IDs e erros de eventos do Microsoft Defender Antivírus
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765810"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Revise logs de eventos e códigos de erro para solucionar problemas com o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Se você encontrar um problema com o Microsoft Defender Antivírus, poderá pesquisar as tabelas neste tópico para encontrar um problema correspondente e uma solução potencial.

A lista de tabelas:

- [IDs](#windows-defender-av-ids) de eventos do Microsoft Defender Antivírus (elas se aplicam ao Windows 10 e ao Windows Server 2016)
- [Códigos de erro do cliente do Microsoft Defender Antivírus](#error-codes)
- [Códigos de erro do cliente interno do Microsoft Defender Antivírus (usados pela Microsoft durante o desenvolvimento e teste)](#internal-error-codes)

> [!TIP]
> Você também pode visitar o site de demonstração do Microsoft Defender para Ponto de Extremidade [no demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que os seguintes recursos estão funcionando:
> 
> - Proteção entregue na nuvem
> - Aprendizado rápido (incluindo Bloquear à primeira vista)
> - Bloqueio de aplicativo potencialmente indesejado

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>IDs de eventos do Microsoft Defender Antivírus

O Microsoft Defender Antivírus registra IDs de eventos no log de eventos do Windows.

Você pode exibir diretamente o log de eventos ou se tiver uma ferramenta siem (gerenciamento de eventos) e informações de segurança de terceiros, também poderá consumir [as IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos do cliente do Microsoft Defender Antivírus para analisar eventos e erros específicos dos pontos de extremidade.

A tabela nesta seção lista as principais IDs de evento do Microsoft Defender Antivírus e, quando possível, fornece soluções sugeridas para corrigir ou resolver o erro. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Para exibir um evento do Microsoft Defender Antivírus

1.  Abra **o Visualizador de Eventos**.
2.  Na árvore de console, expanda **Logs de Aplicativos** e Serviços , em seguida, **Microsoft**, e **Windows**, em seguida, **Windows Defender**.
3.  Clique duas vezes em **Operacional**.
4.  No painel de detalhes, veja a lista de eventos individuais para encontrar seu evento.
5.  Clique no evento para ver detalhes específicos sobre um evento no painel inferior, nas guias **Geral** **e Detalhes.**

<table> 
<tr>
<th colspan="2" >ID do Evento: 1000</th>
</tr>
<tr>
<td>
Nome simbólico:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Uma verificação antimalware foi iniciada. </b>
</td>
</tr>
<tr>
<td >
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Recursos de verificação: &lt; Recursos (como arquivos/diretórios/BHO) que foram &gt; verificados.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1001</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Uma verificação antimalware concluída.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Tempo &gt; </dt>
<dt>de verificação do usuário: a &lt; duração de uma verificação. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1002</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Uma verificação antimalware foi interrompida antes de ser concluída. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Usuário: &lt; Domínio &gt; &amp; lt; Tempo &gt; </dt>
<dt>de verificação do usuário: a &lt; duração de uma verificação. &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1003</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Uma verificação antimalware foi pausada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1004</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Uma verificação antimalware foi retomada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1005</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Falha na verificação de antimalware. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
<dl>
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:<ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:<ul>
<li>Verificação completa</li>
<li>Verificação rápida</li>
<li>Verificação do cliente</li>
</ul>
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
O cliente antivírus encontrou um erro e a verificação atual parou. A verificação pode falhar devido a um problema do lado do cliente. Esse registro de evento inclui a ID de verificação, o tipo de verificação (Microsoft Defender Antivírus, antispyware, antimalware), parâmetros de verificação, o usuário que iniciou a verificação, o código de erro e uma descrição do erro.
Para solucionar problemas deste evento:
<ol>
<li>Execute a verificação novamente.</li>
<li>Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1006</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware encontrou malware ou outro software potencialmente indesejado. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Status do </dt> 
<dt>UAC: Usuário &lt; de &gt; Status:</dt>Domínio
<dt> &lt; &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na versão de assinatura
<dt> &lt; &gt; PID:</dt>Versão
<dt> &lt; &gt; do</dt>mecanismo de
<dt>definição: versão do Mecanismo &lt; antimalware &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1007</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware realizou uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus tomou medidas para proteger esse computador contra malware ou outros softwares potencialmente indesejados. Para obter mais informações, confira o seguinte:
<dl>
<dt>Usuário: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do usuário: ID
<dt> &lt; do &gt; nome</dt>da ameaça: Gravidade da
<dt> &lt; ID &gt; </dt>de 
<dt> Ameaça: &lt; &gt; Severidade , por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt> Ação: &lt; Ação , por &gt; exemplo:<ul>
<li>Clean: o recurso foi limpo</li>
<li>Quarentena: o recurso foi colocado em quarentena</li>
<li>Remover: o recurso foi excluído</li>
<li>Permitir: o recurso teve permissão para executar/existir</li>
<li>User defined: User-defined action that is normally one from this list of actions that the user has specified</li>
<li>Nenhuma ação: nenhuma ação</li>
<li>Bloquear: o recurso foi impedido de executar</li>
</ul>
</dt>
<dt>Status: &lt; Versão &gt; da</dt>
<dt>Assinatura de Status: Versão &lt; &gt; do</dt>mecanismo de
<dt> &lt; &gt; definição: versão do Mecanismo antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1008</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware tentou executar uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado, mas a ação falhou.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tomar medidas em malware ou em outro software potencialmente indesejado. Para obter mais informações, confira o seguinte:
<dl>
<dt>Usuário: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do usuário: ID
<dt> &lt; do &gt; nome</dt>da ameaça: Gravidade da
<dt> &lt; ID &gt; </dt>de 
<dt> Ameaça: &lt; &gt; Severidade , por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Ação &gt; do caminho do</dt> 
<dt> arquivo: Ação , por &lt; &gt; exemplo:<ul>
<li>Clean: o recurso foi limpo</li>
<li>Quarentena: o recurso foi colocado em quarentena</li>
<li>Remover: o recurso foi excluído</li>
<li>Permitir: o recurso teve permissão para executar/existir</li>
<li>User defined: User-defined action that is normally one from this list of actions that the user has specified</li>
<li>Nenhuma ação: nenhuma ação</li>
<li>Bloquear: o recurso foi impedido de executar</li>
</ul>
</dt>
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Status: &lt; Versão &gt; da</dt>
<dt>Assinatura de Status: Versão &lt; &gt; do</dt>mecanismo de
<dt> &lt; &gt; definição: versão do Mecanismo antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1009</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware restaurou um item da quarentena. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus restaurou um item da quarentena. Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Versão &gt; da</dt>
<dt>Assinatura do Usuário: Versão &lt; &gt; do</dt>mecanismo de
<dt>definição: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1010</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware não pôde restaurar um item da quarentena. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar restaurar um item da quarentena. Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1011</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware excluiu um item da quarentena. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus excluiu um item da quarentena.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Versão &gt; da</dt>
<dt>Assinatura do Usuário: Versão &lt; &gt; do</dt>mecanismo de
<dt>definição: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1012</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware não pôde excluir um item da quarentena.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar excluir um item da quarentena.
Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1013</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware excluiu o histórico de malware e outros softwares potencialmente indesejados.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus removeu o histórico de malware e outros softwares potencialmente indesejados.
<dl>
<dt>Hora: a hora em que o evento ocorreu, por exemplo, quando o histórico é limpo. Esse parâmetro não é usado em eventos de ameaça para que não haja confusão em relação ao tempo de correção ou ao tempo de infecção. Para eles, especificamente os chamamos como Tempo de Ação ou Hora de Detecção.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1014</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
A plataforma antimalware não pôde excluir o histórico de malware e outros softwares potencialmente indesejados.
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar remover o histórico de malware e outros softwares potencialmente indesejados.
<dl>
<dt>Hora: a hora em que o evento ocorreu, por exemplo, quando o histórico é limpo. Esse parâmetro não é usado em eventos de ameaça para que não haja confusão em relação ao tempo de correção ou ao tempo de infecção. Para eles, especificamente os chamamos como Tempo de Ação ou Hora de Detecção.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1015</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware detectou comportamento suspeito.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus detectou um comportamento suspeito.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:
<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Status do </dt> 
<dt>UAC: Usuário &lt; de &gt; Status:</dt>Domínio
<dt> &lt; &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na ID de Assinatura
<dt> &lt; &gt; PID:</dt>
<dt>gravidade correspondente à enumeração.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de</dt>
<dt>definição Versão do mecanismo: versão do Mecanismo &lt; &gt; antimalware</dt>
<dt>Fidelity Rótulo:</dt>Nome do arquivo de destino: Nome do
<dt> &lt; &gt; arquivo.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1116</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware detectou malware ou outro software potencialmente indesejado. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus detectou malware ou outro software potencialmente indesejado.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:
<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na versão de assinatura
<dt> &lt; &gt; PID:</dt>Versão
<dt> &lt; &gt; do</dt>mecanismo de
<dt>definição: versão do Mecanismo &lt; antimalware &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O Microsoft Defender Antivírus pode suspender e tomar medidas de rotina sobre essa ameaça. Se você quiser remover a ameaça manualmente, na interface do Microsoft Defender Antivírus, clique em <b>Limpar Computador</b>.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1117</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware realizou uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus tomou medidas para proteger esse computador contra malware ou outros softwares potencialmente indesejados.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:
<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:<ul>
<li>Clean: o recurso foi limpo</li>
<li>Quarentena: o recurso foi colocado em quarentena</li>
<li>Remover: o recurso foi excluído</li>
<li>Permitir: o recurso teve permissão para executar/existir</li>
<li>User defined: User-defined action that is normally one from this list of actions that the user has specified</li>
<li>Nenhuma ação: nenhuma ação</li>
<li>Bloquear: o recurso foi impedido de executar</li>
</ul>
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; &gt;</dt>Versão do mecanismo de definição: versão do Mecanismo
<dt> &lt; &gt; antimalware</dt> OBSERVAÇÃO: sempre que o Microsoft Defender Antivírus, o Microsoft Security Essentials, a Ferramenta de Remoção de Software Mal-Intencionado ou a Proteção do Ponto de Extremidade do System Center detectarem um malware, ele restaurará as seguintes configurações e serviços do sistema que o malware pode ter alterado:<ul>
<li>Configuração padrão do Internet Explorer ou do Microsoft Edge</li>
<li>Configurações do Controle de Acesso para Usuário</li>
<li>Configurações do Chrome</li>
<li>Dados de controle de inicialização</li>
<li>Configurações do Registro do Gerenciador de Tarefas e regedit</li>
<li>Windows Update, Serviço de Transferência Inteligente em Segundo Plano e Serviço de Chamada de Procedimento Remoto</li>
<li>Arquivos do Sistema Operacional Windows</li></ul>
O contexto acima se aplica às seguintes versões de cliente e servidor:
<table>
<tr>
<th>Sistema operacional</th>
<th>Versão do sistema operacional</th>
</tr>
<tr>
<td>
Sistema Operacional Cliente
</td>
<td>
Windows Vista (Service Pack 1 ou Service Pack 2), Windows 7 e posterior
</td>
</tr>
<tr>
<td>
Sistema Operacional do Servidor
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 e Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O Microsoft Defender Antivírus foi removido ou colocado em quarentena como ameaça. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1118</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware tentou executar uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado, mas a ação falhou. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro não crítico ao tomar medidas sobre malware ou outro software potencialmente indesejado.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:
<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:<ul>
<li>Clean: o recurso foi limpo</li>
<li>Quarentena: o recurso foi colocado em quarentena</li>
<li>Remover: o recurso foi excluído</li>
<li>Permitir: o recurso teve permissão para executar/existir</li>
<li>User defined: User-defined action that is normally one from this list of actions that the user has specified</li>
<li>Nenhuma ação: nenhuma ação</li>
<li>Bloquear: o recurso foi impedido de executar</li>
</ul>
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O Microsoft Defender Antivírus falhou ao concluir uma tarefa relacionada à correção de malware. Isso não é uma falha crítica.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1119</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware encontrou um erro crítico ao tentar tomar medidas sobre malware ou outro software potencialmente indesejado. Há mais detalhes na mensagem de evento.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro crítico ao tomar medidas em malware ou em outro software potencialmente indesejado.<br/>Para obter mais informações, confira o seguinte:
<dl>
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:<ul>
<li>Baixo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:
<ul>
<li>Desconhecido</li>
<li>Computador local</li>
<li>Compartilhamento de rede</li>
<li>Internet</li>
<li>Tráfego de entrada</li>
<li>Tráfego de saída</li>
</ul>
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Assinatura dinâmica</li>
</ul>
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:<ul>
<li>Usuário: iniciado pelo usuário</li>
<li>Sistema: iniciado pelo sistema</li>
<li>Em tempo real: componente em tempo real iniciado</li>
<li>IOAV: Downloads do IE e Anexos do Outlook Express iniciados</li>
<li>NIS: Sistema de inspeção de rede</li>
<li>IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</li>
<li>Antimalware de início antecipado (ELAM). Isso inclui malware detectado pela sequência de inicialização</li>
<li>Atestado remoto</li>
</ul>Interface de verificação antimalware (AMSI). Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.
Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:<ul>
<li>Clean: o recurso foi limpo</li>
<li>Quarentena: o recurso foi colocado em quarentena</li>
<li>Remover: o recurso foi excluído</li>
<li>Permitir: o recurso teve permissão para executar/existir</li>
<li>User defined: User-defined action that is normally one from this list of actions that the user has specified</li>
<li>Nenhuma ação: nenhuma ação</li>
<li>Bloquear: o recurso foi impedido de executar</li>
</ul>
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do Mecanismo &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
O cliente do Microsoft Defender Antivírus encontrou esse erro devido a problemas críticos. O ponto de extremidade pode não estar protegido. Revise a descrição do erro e siga as etapas <b>de ação do usuário</b> relevantes abaixo.
<table>
<tr>
<th>Action</th>
<th>Ação do usuário</th>
</tr>
<tr>
<td>
<b>Remover</b>
</td>
<td>
Atualize as definições e verifique se a remoção foi bem-sucedida.
</td>
</tr>
<tr>
<td>
<b>Clean</b>
</td>
<td>
Atualize as definições e verifique se a correção foi bem-sucedida.
</td>
</tr>
<tr>
<td>
<b>Quarentena</b>
</td>
<td>
Atualize as definições e verifique se o usuário tem permissão para acessar os recursos necessários.
</td>
</tr>
<tr>
<td>
<b>Permitir</b>
</td>
<td>
Verifique se o usuário tem permissão para acessar os recursos necessários.
</td>
</tr>
</table>

Se esse evento persistir:<ol>
<li>Execute a verificação novamente.</li>
<li>Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1120</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O Microsoft Defender Antivírus deduziu os hashes de um recurso de ameaça.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O cliente do Microsoft Defender Antivírus está em funcionamento em um estado saudável.
<dl>
<dt>Versão da plataforma atual: &lt; Versão atual &gt; da plataforma</dt>
<dt>Caminho do Recurso de &lt; &gt; Ameaças:</dt>
<dt>Hashes de Caminho: &lt; Hashes &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Observação: esse evento só será registrado se a seguinte política estiver definida: <b>ThreatFileHashLogging não assinado</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 1150</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Se sua plataforma antimalware relata o status para uma plataforma de monitoramento, esse evento indica que a plataforma antimalware está em execução e em um estado saudável. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O cliente do Microsoft Defender Antivírus está em funcionamento em um estado saudável.
<dl>
<dt>Versão da plataforma: &lt; Versão de &gt; assinatura da plataforma atual:</dt>
<dt>Versão &lt; &gt; do</dt>
<dt>mecanismo de &lt; &gt; definição: versão do Mecanismo antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O cliente do Microsoft Defender Antivírus está em um estado saudável. Esse evento é relatado a cada hora.
</td>
</tr>

<tr>
<th colspan="2">ID do Evento: 1151</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Relatório de saúde do cliente de Proteção de Ponto de Extremidade (hora em UTC) </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
Relatório de saúde do cliente antivírus.
<dl>
<dt>Versão da plataforma: &lt; &gt;</dt>Versão do mecanismo da plataforma atual: Versão do mecanismo de
<dt> &lt; &gt; antimalware</dt>Versão do mecanismo de inspeção em tempo real da rede: Versão do mecanismo de inspeção em tempo
<dt> &lt; &gt; real</dt>de rede Versão de assinatura antivírus
<dt> &lt; &gt; Versão</dt>de assinatura
<dt> &lt; antispyware &gt; Versão da</dt>assinatura do Mecanismo de Rede Versão da inspeção em tempo real: Estado da versão RTP da assinatura de Inspeção em Tempo
<dt> &lt; &gt; Real</dt>da Rede: Estado do OA de proteção em tempo
<dt>real &lt; &gt; (habilitado</dt>ou desabilitado) estado do OA: Estado do IOAV no estado do
<dt>Acesso &lt; &gt; (Habilitado</dt>ou Desabilitado) estado IOAV: I Estado BM de Downloads e Anexos do
<dt>Outlook Express &lt; &gt; (Habilitado</dt>ou Desabilitado): Estado de monitoramento de comportamento (habilitado ou
<dt> &lt; &gt; desabilitado)</dt>Idade da assinatura do antivírus: idade da assinatura do antivírus
<dt> &lt; &gt; (em dias)</dt>Idade da assinatura do Antispyware: idade da assinatura do
<dt> &lt; Antispyware &gt; (em dias)</dt>Idade da última verificação rápida: Idade da última verificação rápida
<dt> &lt; &gt; (em dias)</dt>Idade da última verificação completa( em
<dt> &lt; &gt; dias)</dt>Tempo de criação da assinatura do Antivírus:
<dt>? &lt; Tempo de &gt; criação de assinatura antivírus</dt>Hora de criação da assinatura do
<dt>Antispyware: ? &lt; Tempo de criação de &gt; assinatura antispyware</dt>Última hora de início
<dt>da verificação rápida: ? &lt; Última hora de &gt; início da verificação rápida</dt>Última hora de término da verificação
<dt>rápida: ? &lt; Última &gt; hora</dt>de término da verificação rápida Última fonte de verificação rápida: Última fonte de verificação rápida (0 = verificação&#39;não foi executado, 1 = iniciado pelo
<dt> &lt; &gt; usuário, 2 =</dt>iniciado pelo sistema) Última hora de início da verificação
<dt>completa: ? &lt; Última hora de &gt; início de verificação completa</dt>Última hora de término da verificação
<dt>completa: ? &lt; Última hora de &gt; </dt>término de verificação completa Última fonte de verificação completa: Última fonte de verificação completa (0 = verificação&#39;não foi executado, 1 = iniciado pelo
<dt> &lt; &gt; usuário, 2 =</dt>sistema iniciado) Status do produto: Para solução de problemas internos 
<dt>
</dl>
</td>
</tr>

<tr>
<th colspan="2">ID do Evento: 2000</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>As definições antimalware atualizadas com êxito. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A versão de assinatura do antivírus foi atualizada.
<dl>
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt>
<dt>Versão anterior da assinatura: Versão de assinatura &lt; &gt; anterior</dt>Tipo de 
<dt> assinatura: Tipo de assinatura , por &lt; &gt; exemplo: <ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Tipo de atualização: &lt; Tipo de &gt; atualização , Completo ou Delta.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Versão &gt; </dt>
<dt>do Mecanismo Atual do Usuário: Versão anterior &lt; do &gt; </dt>
<dt>mecanismo do mecanismo atual: Versão anterior do &lt; mecanismo &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O cliente do Microsoft Defender Antivírus está em um estado saudável. Esse evento é relatado quando as assinaturas são atualizadas com êxito.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2001</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A atualização de inteligência de segurança falhou. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar atualizar assinaturas.
<dl>
<dt>Nova versão de inteligência de segurança: &lt; Novo número &gt; de versão</dt>
<dt>Versão anterior de inteligência de segurança: Versão &lt; &gt; anterior</dt>Fonte de 
<dt> atualização: Fonte de atualização , por &lt; &gt; exemplo:
<ul>
<li>Pasta de atualização de inteligência de segurança</li>
<li>Servidor de atualização de inteligência de segurança interna</li>
<li>Microsoft Update Server</li>
<li>Compartilhamento de arquivos</li>
<li>Centro de Proteção contra Malware da Microsoft (MMPC)</li>
</ul>
</dt>
<dt>Estágio de atualização: &lt; estágio de atualização , por &gt; exemplo:
<ul>
<li>Pesquisar</li>
<li>Baixar</li>
<li>Instalar</li>
</ul>
</dt>Caminho de origem: Nome do compartilhamento de arquivos para a Convenção De Nomenização Universal (UNC), nome do servidor para o 
<dt>WSUS (Windows Server Update Services)/Microsoft Update/ADL.</dt> 
<dt> Tipo de assinatura: &lt; Tipo de assinatura , por &gt; exemplo: <ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Tipo de atualização: &lt; Tipo de &gt; atualização , Completo ou Delta.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Versão &gt; </dt>
<dt>do Mecanismo Atual do Usuário: &lt; &gt; Versão do mecanismo atual</dt>Versão anterior do mecanismo: Versão
<dt> &lt; &gt; anterior</dt>Código de erro: Código de erro Código de resultado
<dt>associado ao status da &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Esse erro ocorre quando há um problema de atualização de definições.
Para solucionar problemas deste evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Atualize definições</a> e force uma nova varredura diretamente no ponto de extremidade.</li>
<li>Revise as entradas no arquivo %Windir%\WindowsUpdate.log para obter mais informações sobre esse erro.</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2002</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware atualizado com êxito. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A versão do mecanismo do Microsoft Defender Antivírus foi atualizada.
<dl>
<dt>Versão atual do mecanismo: &lt; Versão do &gt; mecanismo atual</dt>
<dt>Versão anterior do mecanismo: &lt; &gt; versão anterior</dt>Tipo de mecanismo: Tipo de mecanismo , mecanismo
<dt> &lt; &gt; antimalware ou mecanismo do Sistema de</dt> Inspeção de Rede. 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O cliente do Microsoft Defender Antivírus está em um estado saudável. Esse evento é relatado quando o mecanismo antimalware é atualizado com êxito.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2003</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A atualização do mecanismo antimalware falhou. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar atualizar o mecanismo.
<dl>
<dt>Nova versão do mecanismo:</dt>
<dt>Versão anterior do mecanismo: &lt; &gt; versão anterior</dt>Tipo de mecanismo: Tipo de mecanismo , mecanismo
<dt> &lt; &gt; antimalware ou</dt> mecanismo do Sistema de Inspeção de Rede. 
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
A atualização do cliente do Microsoft Defender Antivírus falhou. Esse evento ocorre quando o cliente não consegue se atualizar. Esse evento geralmente ocorre devido a uma interrupção na conectividade de rede durante uma atualização.
Para solucionar problemas deste evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Atualize definições</a> e force uma nova varredura diretamente no ponto de extremidade.</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2004</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Houve um problema ao carregar definições de antimalware. O mecanismo antimalware tentará carregar o último bom conjunto de definições conhecido.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar carregar assinaturas e tentará reverter para um conjunto conhecido de assinaturas.
<dl>
<dt>Assinaturas Tentadas: Código</dt>
<dt>de Erro: Código de erro Código de &lt; resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do mecanismo antimalware &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
O cliente do Microsoft Defender Antivírus tentou baixar e instalar o arquivo de definições mais recentes e falhou. Esse erro pode ocorrer quando o cliente encontrar um erro ao tentar carregar as definições ou se o arquivo estiver corrompido. O Microsoft Defender Antivírus tentará reverter para um conjunto conhecido de definições.
Para solucionar problemas deste evento:
<ol>
<li>Reinicie o computador e tente novamente.</li>
<li>Baixe as definições mais recentes do <a href="https://aka.ms/wdsi">site do Microsoft Security Intelligence.</a>
Observação: o tamanho do arquivo de definições baixado do site pode exceder 60 MB e não deve ser usado como uma solução de longo prazo para atualizar definições.
</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2005</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware falhou ao carregar porque a plataforma antimalware está desacorda. A plataforma antimalware carregará o último mecanismo antimalware bom conhecido e tentará atualizar.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus não pôde carregar o mecanismo antimalware porque a versão atual da plataforma não é suportada. O Microsoft Defender Antivírus será revertido para o último mecanismo conhecido e uma atualização de plataforma será tentada.
<dl>
<dt>Versão da plataforma atual: &lt; versão da plataforma atual&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2006</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A atualização da plataforma falhou. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar atualizar a plataforma.
<dl>
<dt>Versão da plataforma atual: &lt; Versão atual &gt; da plataforma</dt>
<dt>Código de Erro: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2007</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Em breve, a plataforma estará desa datada. Baixe a plataforma mais recente para manter a proteção atualizada.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus em breve exigirá uma versão mais recente da plataforma para dar suporte a versões futuras do mecanismo antimalware. Baixe a plataforma mais recente do Microsoft Defender Antivírus para manter o melhor nível de proteção disponível.
<dl>
<dt>Versão da plataforma atual: &lt; versão da plataforma atual&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2010</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware usou o Serviço de Assinatura Dinâmica para obter definições adicionais. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus <i>usou o Serviço</i> de Assinatura Dinâmica para recuperar assinaturas adicionais para ajudar a proteger seu computador.
<dl>
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo: <ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; do mecanismo</dt> 
<dt> Tipo de Assinatura Dinâmica: Tipo de assinatura &lt; dinâmica , por &gt; exemplo:
<ul>
<li>Versão</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
<li>Duration</li>
</ul>
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Tipo de limite de persistência do
<dt> &lt; &gt; timestamp:</dt>tipo de limite de persistência , por 
<dt> &lt; &gt; exemplo:
<ul>
<li>Versão VDM</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
</ul>
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2011</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O Serviço de Assinatura Dinâmica excluiu as definições dinâmicas desatendados. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus <i>usou o Serviço de Assinatura Dinâmica</i> para descartar assinaturas obsoletas.
<dl>
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo: <ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; do mecanismo</dt> 
<dt> Tipo de Assinatura Dinâmica: Tipo de assinatura &lt; dinâmica , por &gt; exemplo:
<ul>
<li>Versão</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
<li>Duration</li>
</ul>
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Motivo da remoção do
<dt> &lt; &gt; timestamp:</dt>Tipo de limite de persistência: tipo de limite de
<dt></dt> 
<dt> &lt; &gt; persistência, por exemplo:
<ul>
<li>Versão VDM</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
</ul>
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Nenhuma ação é necessária. O cliente do Microsoft Defender Antivírus está em um estado saudável. Esse evento é relatado quando o Serviço de Assinatura Dinâmica exclui com êxito definições dinâmicas desatentadas.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2012</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware encontrou um erro ao tentar usar o Serviço de Assinatura Dinâmica. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar usar o <i>Serviço de Assinatura Dinâmica.</i>
<dl>
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo: <ul>
<li>Antivírus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; código de erro</dt>
<dt>do mecanismo: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt> Tipo de Assinatura Dinâmica: &lt; Tipo de assinatura dinâmica , por &gt; exemplo:
<ul>
<li>Versão</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
<li>Duration</li>
</ul>
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Tipo de limite de persistência do
<dt> &lt; &gt; timestamp:</dt>tipo de limite de persistência , por 
<dt> &lt; &gt; exemplo:
<ul>
<li>Versão VDM</li>
<li>Carimbo de data/hora</li>
<li>Sem limite</li>
</ul>
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Verifique suas configurações de conectividade com a Internet.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2013</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O Serviço de Assinatura Dinâmica excluiu todas as definições dinâmicas. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus descartou todas as <i>assinaturas do Serviço</i> de Assinatura Dinâmica.
<dl>
<dt>Versão de assinatura atual: &lt; Versão de assinatura atual&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2020</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware baixou um arquivo limpo. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus baixou um arquivo limpo.
<dl>
<dt>Nomedo arquivo: &lt; Nome do &gt; arquivo Nome do arquivo.</dt> 
<dt>Versão de assinatura atual: &lt; Versão atual &gt; do</dt>
<dt>mecanismo de assinatura atual: versão atual do &lt; mecanismo &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2021</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware falhou ao baixar um arquivo limpo. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar baixar um arquivo limpo.
<dl>
<dt>Nomedo arquivo: &lt; Nome do &gt; arquivo Nome do arquivo.</dt> 
<dt>Versão de assinatura atual: &lt; Versão atual &gt; do</dt>
<dt>mecanismo de assinatura atual: &lt; &gt; Versão atual</dt>do mecanismo Código de erro: Código de erro Código de resultado associado ao status da
<dt> &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Verifique suas configurações de conectividade com a Internet.
O cliente do Microsoft Defender Antivírus encontrou um erro ao usar o Serviço de Assinatura Dinâmica para baixar as definições mais recentes para uma ameaça específica. Esse erro provavelmente é causado por um problema de conectividade de rede. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2030</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware foi baixado e está configurado para ser executado offline na próxima reinicialização do sistema.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus baixou e configurou o antivírus offline para ser executado na próxima reinicialização.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2031</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware não pôde baixar e configurar uma verificação offline.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus encontrou um erro ao tentar baixar e configurar antivírus offline.
<dl>
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2040</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O suporte a antimalware para esta versão do sistema operacional terminará em breve. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O suporte para seu sistema operacional expirará em breve. Executar o Microsoft Defender Antivírus em um sistema operacional sem suporte não é uma solução adequada para proteger contra ameaças.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2041</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O suporte a antimalware para este sistema operacional terminou. Você deve atualizar o sistema operacional para suporte contínuo. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O suporte para seu sistema operacional expirou. Executar o Microsoft Defender Antivírus em um sistema operacional sem suporte não é uma solução adequada para proteger contra ameaças.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 2042</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware não dá mais suporte a esse sistema operacional e não está mais protegendo seu sistema contra malware. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O suporte para seu sistema operacional expirou. O Microsoft Defender Antivírus não tem mais suporte em seu sistema operacional, parou de funcionar e não está protegendo contra ameaças de malware.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 3002</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A proteção em tempo real encontrou um erro e falhou.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O recurso Real-Time Proteção do Microsoft Defender Antivírus encontrou um erro e falhou.
<dl>
<dt>Recurso: &lt; Recurso , por &gt; exemplo:
<ul>
<li>No Access</li>
<li>Downloads do Internet Explorer e anexos do Microsoft Outlook Express</li>
<li>Monitoramento de comportamento</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Motivo: o motivo pelo qual a proteção em tempo real do Microsoft Defender Antivírus reiniciou um recurso.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Você deve reiniciar o sistema e executar uma verificação completa porque&#39;é possível que o sistema não estivesse protegido por algum tempo.
O cliente do Microsoft Defender Antivírus&#39;recurso de proteção em tempo real encontrou um erro porque um dos serviços falhou ao iniciar. Se for seguida por uma ID de evento 3007, a falha foi temporária e o cliente antimalware foi recuperado da falha. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 3007</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>Proteção em tempo real recuperada de uma falha. Recomendamos executar uma verificação completa do sistema quando você vir esse erro. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A Proteção em Tempo Real do Microsoft Defender Antivírus reinicie um recurso. É recomendável executar uma verificação completa do sistema para detectar todos os itens que podem ter sido faltados enquanto esse agente estava inotivo.
<dl>
<dt>Recurso: &lt; Recurso , por &gt; exemplo:
<ul>
<li>No Access</li>
<li>Downloads do IE e anexos do Outlook Express</li>
<li>Monitoramento de comportamento</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Motivo: o motivo pelo qual a proteção em tempo real do Microsoft Defender Antivírus reiniciou um recurso.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
O recurso de proteção em tempo real foi reiniciado. Se esse evento acontecer novamente, entre em contato <a href="https://go.microsoft.com/fwlink/?LinkId=215491">com o Suporte Técnico da Microsoft</a>. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5000</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A proteção em tempo real está habilitada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação de proteção em tempo real do Microsoft Defender Antivírus para malware e outros softwares potencialmente indesejados foi habilitada.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5001</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A proteção em tempo real está desabilitada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação de proteção em tempo real do Microsoft Defender Antivírus para malware e outros softwares potencialmente indesejados foi desabilitada. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5004</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A configuração de proteção em tempo real foi alterada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A configuração do recurso de proteção em tempo real do Microsoft Defender Antivírus foi alterada.
<dl>
<dt>Recurso: &lt; Recurso , por &gt; exemplo:
<ul>
<li>No Access</li>
<li>Downloads do IE e anexos do Outlook Express</li>
<li>Monitoramento de comportamento</li>
<li>Sistema de Inspeção de Rede</li>
</ul>
</dt>
<dt>Configuração: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5007</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A configuração da plataforma antimalware foi alterada.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A configuração do Microsoft Defender Antivírus foi alterada. Se esse for um evento inesperado, você deve revisar as configurações, pois isso pode ser o resultado de malware.
<dl>
<dt>Valor antigo: &lt; Número de valor antigo &gt; Valor de configuração do antivírus antigo.</dt> 
<dt>Novo valor: &lt; Novo número de valor &gt; Novo valor de configuração do antivírus.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5008</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>O mecanismo antimalware encontrou um erro e falhou.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O mecanismo do Microsoft Defender Antivírus foi encerrado devido a um erro inesperado.
<dl>
<dt>Tipo de falha: &lt; Tipo de &gt; falha , por exemplo: Crash ou Hang</dt>Exception
<dt>Code: Código de &lt; &gt; erro</dt>
<dt>Recurso: &lt; Recurso &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
Para solucionar problemas deste evento:<ol>
<li>Tente reiniciar o serviço.<ul>
<li>Para antimalware, antivírus e spyware, em um prompt de comando elevado, digite <b>net stop msmpsvc</b>e digite <b>net start msmpsvc</b> para reiniciar o mecanismo antimalware.</li>
<li>Para o <i></i> <i>Sistema</i>de Inspeção de Rede , em um prompt de comando elevado, digite net start <b>nissrv</b>e digite net start <b>nissrv</b> para reiniciar o mecanismo do Sistema de Inspeção de Rede usando o arquivo NiSSRV.exe.
</li>
</ul>
</li>
<li>Se ele falhar da mesma forma, procure o código de erro acessando o <b></b> Site de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> e inserindo o número de erro na caixa Pesquisa e contate o Suporte Técnico da <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft</a>.</li>
</ol>
</td>
</tr>
<tr>
<td>
Ação do usuário:
</td>
<td >
O mecanismo de cliente do Microsoft Defender Antivírus parou devido a um erro inesperado.
Para solucionar problemas deste evento:
<ol>
<li>Execute a verificação novamente.</li>
<li>Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</li>
<li>Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5009</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A verificação de malware e outros softwares potencialmente indesejados está habilitada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação do Microsoft Defender Antivírus para malware e outros softwares potencialmente indesejados foi habilitada.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5010</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A verificação de malware e outros softwares potencialmente indesejados está desabilitada.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação do Microsoft Defender Antivírus para malware e outros softwares potencialmente indesejados está desabilitada.
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5011</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A verificação de vírus está habilitada.</b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação de vírus do Microsoft Defender Antivírus foi habilitada. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5012</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A verificação de vírus está desabilitada. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
A verificação de vírus do Microsoft Defender Antivírus está desabilitada. 
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5100</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware expirará em breve. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O Microsoft Defender Antivírus entrou em um período de carência e expirará em breve. Após a expiração, este programa desabilitará a proteção contra vírus, spyware e outros softwares potencialmente indesejados.
<dl>
<dt>Motivo da expiração: o motivo pelo qual o Microsoft Defender Antivírus expirará.</dt> 
<dt>Data de expiração: a data em que o Microsoft Defender Antivírus expirará.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID do Evento: 5101</th>
</tr>
<tr><td>
Nome simbólico:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
Mensagem:
</td>
<td >
<b>A plataforma antimalware expirou. </b>
</td>
</tr>
<tr>
<td>
Descrição:
</td>
<td >
O período de carência do Microsoft Defender Antivírus expirou. A proteção contra vírus, spyware e outros softwares potencialmente indesejados está desabilitada.
<dl>
<dt>Motivo da expiração:</dt>
<dt>Data de expiração: Código </dt>de erro: Código de erro Código de resultado associado ao status da 
<dt> &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
## Códigos de erro do cliente do Microsoft Defender Antivírus Se o Microsoft Defender Antivírus tiver algum problema, ele geralmente lhe dará um código de erro para ajudá-lo a solucionar o problema. Na maioria das vezes, um erro significa que houve um problema ao instalar uma atualização.
Esta seção fornece as seguintes informações sobre erros de cliente do Microsoft Defender Antivírus.
-   O código de -   erro O motivo possível para o erro Conselhos sobre o que fazer -   agora

Use as informações nessas tabelas para ajudar a solucionar problemas de códigos de erro do Microsoft Defender Antivírus.


<table> 
<tr>
<th colspan="2">Código de erro: 0x80508007</th>
</tr>
<tr>
<td>Mensagem</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Possível motivo
</td>
<td>
Esse erro indica que você pode ter ficar sem memória. 
</td>
</tr>
<tr>
<td>Resolução</td>
<td>
<ol>
<li>Verifique a memória disponível em seu dispositivo.</li>
<li>Feche todos os aplicativos nãousados que estão sendo executados para liberar memória em seu dispositivo.</li>
<li>Reinicie o dispositivo e execute a verificação novamente. 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x8050800C</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que pode haver um problema com seu produto de segurança.
</td>
</tr><tr><td>Resolução</td><td>
<ol>
<li>Atualize as definições. Qualquer um deles:<ol>
<li>Clique no <b>botão Atualizar definições</b> na guia <b>Atualizar</b> no Microsoft Defender Antivírus. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>Ou
</li>
<li>Baixe as definições mais recentes do <a href="https://aka.ms/wdsi">site do Microsoft Security Intelligence.</a>
Observação: o tamanho do arquivo de definições baixado do site pode exceder 60 MB e não deve ser usado como uma solução de longo prazo para atualizar definições.
</li>
</ol>
</li>
<li>Execute uma verificação completa.
</li>
<li>Reinicie o dispositivo e tente novamente.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508020</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que pode haver um erro de configuração do mecanismo; normalmente, isso está relacionado a dados de entrada que não permitem que o mecanismo funcione corretamente. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x805080211
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que o Microsoft Defender Antivírus falhou ao colocar em quarentena uma ameaça. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508022
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que uma reinicialização é necessária para concluir a remoção de ameaças. 
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que a ameaça pode não estar mais presente na mídia, ou o malware pode estar impedindo a verificação do dispositivo. 
</tr><tr><td>Resolução
</td>
<td>
Execute o <a href="https://www.microsoft.com/security/scanner/default.aspx">Scanner de Segurança</a> da Microsoft e atualize seu software de segurança e tente novamente. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508024 </th></tr>
<tr>
<td>Mensagem</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que uma verificação completa do sistema pode ser necessária. 
</td></tr>
<tr>
<td>Resolução</td><td>
Execute uma verificação completa do sistema. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508025
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que as etapas manuais são necessárias para concluir a remoção de ameaças. 
</td></tr><tr><td>Resolução</td><td>
Siga as etapas de correção manuais descritas na <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Enciclopédia de Proteção contra Malware da Microsoft.</a> Você pode encontrar um link específico de ameaça no histórico de eventos.<br/></td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508026
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que a remoção dentro do tipo contêiner pode não ser suportada. 
</td></tr><tr><td>Resolução</td><td>
O Microsoft Defender Antivírus não é capaz de remediar ameaças detectadas dentro do arquivo morto. Considere remover manualmente os recursos detectados. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508027
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que a remoção de ameaças baixas e médias pode ser desabilitada. 
</td></tr><tr><td>Resolução</td><td>
Verifique as ameaças detectadas e resolva-as conforme necessário. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508029
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que uma nova verificação da ameaça é necessária. 
</td></tr><tr><td>Resolução</td><td>
Execute uma verificação completa do sistema. 
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508030
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que uma verificação offline é necessária. 
</td></tr><tr><td>Resolução</td><td>
Execute o Microsoft Defender Antivírus offline. Você pode ler sobre como fazer isso no artigo <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline do Microsoft Defender Antivírus.</a>
</td>
</tr>
<tr>
<th colspan="2">Código de erro: 0x80508031
</th>
</tr><tr><td>Mensagem</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Possível motivo</td>
<td>
Esse erro indica que o Microsoft Defender Antivírus não dá suporte à versão atual da plataforma e exige uma nova versão da plataforma. 
</td></tr><tr><td>Resolução</td><td>
Você só pode usar o Microsoft Defender Antivírus no Windows 10. Para Windows 8, Windows 7 e Windows Vista, você pode usar o <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a> Os códigos de erro a seguir são usados durante testes internos do Microsoft Defender Antivírus.

Se você vir esses erros, [](manage-updates-baselines-microsoft-defender-antivirus.md) poderá tentar atualizar definições e forçar uma nova varredura diretamente no ponto de extremidade.


<table> 
<tr>
<th colspan="3">Códigos de erro internos</th>
</tr>
<tr>
<th><b>Código de erro</b></th>
<th>Mensagem exibida</th>
<th>Possível motivo para erro e resolução</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
Verifique sua conexão com a Internet e execute a verificação novamente.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
Este é um erro interno. A causa não está claramente definida.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
Este é um erro interno. Ele pode ser acionado quando a remoção de malware não for bem-sucedida. 
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
Este é um erro interno. Ele pode ter disparado quando uma verificação não é concluída. 
</td>
</tr>
</table>

## <a name="related-topics"></a>Tópicos relacionados

- [Relatório sobre a proteção do Microsoft Defender Antivírus](report-monitor-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)