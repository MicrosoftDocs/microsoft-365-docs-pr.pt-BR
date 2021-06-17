---
title: Exibir os eventos da redução da superfície de ataque
description: Importe exibições personalizadas para ver eventos de redução de superfície de ataque.
keywords: exibição de eventos, proteção de exploração, auditoria, revisão, eventos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f8de3d8b2d7c07f8d783ecbe85b7e4a9c612aae5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985439"
---
# <a name="view-attack-surface-reduction-events"></a>Exibir os eventos da redução da superfície de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink).

Revise eventos de redução de superfície de ataque no Visualizador de Eventos para monitorar quais regras ou configurações estão funcionando. Você também pode determinar se as configurações são muito "barulhentos" ou afetando seu fluxo de trabalho diário.

Analisar eventos é útil quando você está avaliando os recursos. Você pode habilitar o modo de auditoria para recursos ou configurações e, em seguida, revisar o que teria ocorrido se eles estavam totalmente habilitados.

Este artigo lista todos os eventos, seu recurso ou configuração associados e descreve como criar exibições personalizadas para filtrar para eventos específicos.

Obter relatórios detalhados sobre eventos, blocos e avisos como parte Segurança do Windows se você tiver uma assinatura do E5 e usar [o Microsoft Defender para Ponto](microsoft-defender-endpoint.md)de Extremidade .

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Usar exibições personalizadas para revisar recursos de redução de superfície de ataque

Crie exibições personalizadas no Windows visualizador de eventos para ver apenas eventos para recursos e configurações específicos. A maneira mais fácil é importar um modo de exibição personalizado como um arquivo XML. Você pode copiar o XML diretamente desta página.

Você também pode navegar manualmente até a área de evento que corresponde ao recurso.

### <a name="import-an-existing-xml-custom-view"></a>Importar uma exibição personalizada XML existente

1. Crie um arquivo .txt vazio e copie o XML para a exibição personalizada que você deseja usar no arquivo .txt. Faça isso para cada uma das exibições personalizadas que você deseja usar. Renomeie os arquivos da seguinte forma (certifique-se de alterar o tipo de .txt para .xml):
    - Exibição personalizada de eventos de acesso controlado a pastas: *cfa-events.xml*
    - Exploit protection events custom view: *ep-events.xml*
    - Exibição personalizada de eventos de redução de superfície de *ataque:asr-events.xml*
    - Exibição personalizada de eventos de rede/proteção: *np-events.xml*

2. Digite **o visualizador de** eventos no menu Iniciar e abra o **Visualizador de Eventos**.

3. Selecione **Importar Ação**  >  **Exibição Personalizada...**

  > [!div class="mx-imgBorder"]
  > ![Animação realçando Importar exibição personalizada à esquerda da janela Even viewer](images/events-import.gif)

4. Navegue até onde você extraiu o arquivo XML para a exibição personalizada que deseja e selecione-o.

5. Selecione **Abrir**.

6. Ele criará uma exibição personalizada que filtra apenas os eventos relacionados a esse recurso.

### <a name="copy-the-xml-directly"></a>Copiar o XML diretamente

1. Digite **o visualizador de** eventos no menu Iniciar e abra Windows **Visualizador de Eventos**.

2. No painel esquerdo, em **Ações**, selecione **Criar Exibição Personalizada...**

  > [!div class="mx-imgBorder"]
  > ![Animação realçando a opção criar exibição personalizada na janela Visualizador de eventos](images/events-create.gif)

3. Vá para a guia XML e selecione **Editar consulta manualmente**. Você verá um aviso de que não será possível editar a consulta usando a guia **Filtro** se você usar a opção XML. Selecionar **Sim**.

4. Colar o código XML do recurso de onde você deseja filtrar eventos na seção XML.

5. Selecione **OK**. Especifique um nome para o filtro. Isso cria uma exibição personalizada que filtra apenas os eventos relacionados a esse recurso.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML para eventos de regra de redução de superfície de ataque

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML para eventos de acesso controlado a pastas

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML para eventos de proteção de exploração

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML para eventos de proteção de rede

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Lista de eventos de redução de superfície de ataque

Todos os eventos de redução de superfície de ataque estão localizados em Logs de Aplicativos e Serviços > **microsoft > Windows** e, em seguida, a pasta ou provedor conforme listado na tabela a seguir.

Você pode acessar esses eventos Windows visualizador de eventos:

1. Abra o menu **Iniciar** e digite **o visualizador** de eventos e selecione o resultado **do Visualizador de** Eventos.
2. Expanda **logs de aplicativos e serviços > microsoft > Windows** e vá para a pasta listada em **Provedor/fonte** na tabela abaixo.
3. Clique duas vezes no sub item para ver eventos. Role pelos eventos para encontrar o que você está procurando.

   ![Animação mostrando usando o Visualizador de Eventos](images/event-viewer.gif)

Recurso | Provedor/origem | ID do Evento | Descrição
:-|:-|:-:|:-
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 1 | Auditoria do ACG
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 2 | Imposição do ACG
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 3 | Não permitir auditoria de processos filho
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 4  | Não permitir bloqueio de processos filho
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 5  | Bloquear a auditoria de imagens de baixa integridade
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 6  | Bloquear o bloco de imagens de baixa integridade
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 7  | Bloquear a auditoria de imagens remotas
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 8  | Bloquear o bloco de imagens remotas
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 9  | Desativar as chamadas do sistema win32k
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 10  | Desativar o bloco de chamadas do sistema win32k
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 11 | Auditoria de proteção da integridade do código
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 12  | Bloquear a proteção da integridade do código
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 13 | Auditoria da EAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 14  | Imposição da EAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 15 | Auditoria + EAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 16  | Imposição + EAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 17  | Auditoria da IAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 18  | Imposição da IAF
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 19 | Auditoria do ROP StackPivot
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 20 | Imposição do ROP StackPivot
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) |  21  | Auditoria do ROP CallerCheck
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 22 | Imposição do ROP CallerCheck
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 23 | Auditoria do ROP SimExec
Proteção de exploração | Security-Mitigations (Modo kernel/modo de usuário) | 24 | Imposição do SimExec ROP
Proteção de exploração | Diagnóstico do WER | 5  | Bloco CFG
Proteção de exploração | Win32K (Operacional) | 260 | Fonte Não Confiável
Proteção de rede | Windows Defender (Operacional) | 5007 | Evento quando as configurações são alteradas
Proteção de rede | Windows Defender (Operacional) | 1125 | Evento quando a proteção de rede é ativas no modo de auditoria
Proteção de rede | Windows Defender (Operacional) | 1126 | Evento quando a proteção de rede é a incêndio no modo de bloqueio
Acesso controlado a pastas | Windows Defender (Operacional) | 5007 | Evento quando as configurações são alteradas
Acesso controlado a pastas | Windows Defender (Operacional) | 1124 | Evento de acesso controlado a pastas auditadas
Acesso controlado a pastas | Windows Defender (Operacional) | 1123 | Evento de acesso controlado a pastas bloqueadas
Acesso controlado a pastas | Windows Defender (Operacional) | 1127 | Evento bloqueado de bloqueio de gravação do setor de acesso controlado a pastas
Acesso controlado a pastas | Windows Defender (Operacional) | 1128 | Evento de bloqueio de gravação do setor de acesso controlado a pastas auditadas
Redução de superfície de ataque | Windows Defender (Operacional) | 5007 | Evento quando as configurações são alteradas
Redução de superfície de ataque | Windows Defender (Operacional) | 1122 | Evento quando a regra é a disparar no modo de auditoria
Redução de superfície de ataque | Windows Defender (Operacional) | 1121 | Evento quando a regra é a disparar no modo de bloqueio
