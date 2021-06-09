---
title: Solucionar problemas de integração do Microsoft Defender para pontos de extremidade
description: Solucionar problemas que podem surgir durante a integração de dispositivos ou para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: solucionar problemas de integração, problemas de integração, visualizador de eventos, builds de coleta e visualização de dados, dados do sensor e diagnósticos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b9d6cd374a107a403269bc3babbe4220d69e1cce
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844869"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a>Solucionar problemas de integração do Microsoft Defender para pontos de extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Talvez seja necessário solucionar problemas do processo de integração do Microsoft Defender for Endpoint se encontrar problemas.
Esta página fornece etapas detalhadas para solucionar problemas de integração que podem ocorrer ao implantar com uma das ferramentas de implantação e erros comuns que podem ocorrer nos dispositivos.

## <a name="troubleshoot-issues-with-onboarding-tools"></a>Solucionar problemas com ferramentas de integração

Se você concluiu o processo de integração [](investigate-machines.md) e não vê dispositivos na lista Dispositivos após uma hora, pode indicar um problema de integração ou conectividade.

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a>Solucionar problemas de integração ao implantar com a Política de Grupo

A implantação com a Política de Grupo é feita executando o script de integração nos dispositivos. O console da Política de Grupo não indica se a implantação foi bem-sucedida ou não.

Se você tiver concluído o processo de integração [](investigate-machines.md) e não vir dispositivos na lista Dispositivos após uma hora, poderá verificar a saída do script nos dispositivos. Para obter mais informações, consulte [Solucionar problemas de integração ao implantar com um script](#troubleshoot-onboarding-when-deploying-with-a-script).

Se o script for concluído com êxito, consulte [Solucionar](#troubleshoot-onboarding-issues-on-the-device) problemas de integração nos dispositivos para obter erros adicionais que possam ocorrer.

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a>Solucionar problemas de integração ao implantar com Microsoft Endpoint Configuration Manager

Ao integrar dispositivos usando as seguintes versões do Configuration Manager:

- Microsoft Endpoint Configuration Manager
- System Center Configuration Manager 2012
- Gerenciador de Configurações do System Center 2012 R2

A implantação com as versões mencionadas acima do Configuration Manager é feita executando o script de integração nos dispositivos. Você pode acompanhar a implantação no Console do Configuration Manager.

Se a implantação falhar, você poderá verificar a saída do script nos dispositivos.

Se a integração for concluída com êxito,  mas os dispositivos não aparecerem na lista Dispositivos após uma hora, consulte [Solucionar](#troubleshoot-onboarding-issues-on-the-device) problemas de integração no dispositivo para obter erros adicionais que possam ocorrer.

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a>Solucionar problemas de integração ao implantar com um script

**Verifique o resultado do script no dispositivo:**

1. Clique **em Iniciar,** digite **Visualizador de Eventos** e pressione **Enter**.

2. Vá para **o Windows Logs**  >  **Application**.

3. Procure um evento da **fonte de eventos WDATPOnboarding.**

Se o script falhar e o evento for um erro, você poderá verificar a ID do evento na tabela a seguir para ajudá-lo a solucionar o problema.

> [!NOTE]
> As IDs de evento a seguir são específicas apenas para o script de integração.

ID de evento | Tipo de erro | Etapas de resolução
:---:|:---|:---
 `5` | Os dados de offboard foram encontrados, mas não puderam ser excluídos | Verifique as permissões no Registro, especificamente<br> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
`10` | Os dados de integração não puderam ser gravados no Registro |  Verifique as permissões no Registro, especificamente<br> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.<br>Verifique se o script foi executado como administrador.
`15` |  Falha ao iniciar o serviço SENSE |Verifique a saúde do serviço ( `sc query sense` comando). Certifique-se de que ele não está em um estado intermediário (*'Pending_Stopped'*, *'Pending_Running'*) e tente executar o script novamente (com direitos de administrador). <br> <br> Se o dispositivo estiver executando Windows 10, a versão 1607 e a execução do comando `sc query sense` `START_PENDING` retornarão , reinicie o dispositivo. Se a reinicialização do dispositivo não resolver o problema, atualize para KB4015217 e tente integração novamente.
`15` | Falha ao iniciar o serviço SENSE | Se a mensagem do erro for: Erro do sistema 577 ou erro 1058, você precisará habilitar o driver ELAM do Microsoft Defender Antivírus, consulte Ensure that Microsoft Defender Antivírus is not [disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.
`30` |  O script falhou ao aguardar que o serviço começasse a ser executado | O serviço pode ter levado mais tempo para iniciar ou encontrou erros ao tentar iniciar. Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).
`35` |  O script falhou ao encontrar o valor necessário do registro de status de integração | Quando o serviço SENSE é iniciado pela primeira vez, ele grava o status de integração no local do Registro<br>`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.<br> O script falhou ao encontrá-lo após vários segundos. Você pode testá-lo manualmente e verificar se ele está lá. Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).
`40` | O status de integração do serviço SENSE não está definido como **1** | O serviço SENSE falhou ao fazer a integração adequadamente. Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).
`65` | Privilégios insuficientes| Execute o script novamente com privilégios de administrador.

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a>Solucionar problemas de integração usando Microsoft Intune

Você pode usar Microsoft Intune para verificar códigos de erro e tentar solucionar o problema.

Se você configurou políticas no Intune e elas não são propagadas em dispositivos, talvez seja necessário configurar o registro MDM automático.

Use as tabelas a seguir para entender as possíveis causas de problemas durante a integração:

- Microsoft Intune códigos de erro e OMA-URIs tabela
- Problemas conhecidos com tabela de não conformidade
- Tabela de logs de eventos do Gerenciamento de Dispositivo Móvel (MDM)

Se nenhum dos logs de eventos e as etapas  de solução de problemas funcionarem, baixe o script Local da seção Gerenciamento de dispositivos do portal e execute-o em um prompt de comando elevado.

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a>Microsoft Intune códigos de erro e OMA-URIs

Hex de código de erro | Dec de código de erro | Descrição do erro | OMA-URI | Possíveis etapas de causa e solução de problemas
:---:|:---|:---|:---|:---
0x87D1FDE8 | -2016281112 | Falha na correção | Integração <br> Offboarding | **Causa possível:** A integração ou o offboarding falharam em um blob errado: assinatura errada ou campos PreviousOrgIds ausentes. <br><br> **Etapas de solução de problemas:** <br> Verifique as IDs de evento na seção Exibir erros de integração do agente [no log de eventos do](#view-agent-onboarding-errors-in-the-device-event-log) dispositivo. <br><br> Verifique os logs de eventos MDM na tabela a seguir ou siga as instruções em [Diagnostic MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).
 | | | | Integração <br> Offboarding <br> SampleSharing | **Causa possível:** A chave do Registro da Política de Ponto de Extremidade do Microsoft Defender não existe ou o cliente do OMA DM não tem permissões para gravar nele. <br><br> **Etapas de solução de problemas:** Verifique se a seguinte chave do Registro existe: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <br> <br> Se ele não existir, abra um comando elevado e adicione a chave.
 | | | | SenseIsRunning <br> OnboardingState <br> OrgId |  **Causa possível:** Uma tentativa de correção por propriedade somente leitura. A integração falhou. <br><br> **Etapas de solução de problemas:** Verifique as etapas de solução de problemas em [Solucionar problemas de integração no dispositivo](#troubleshoot-onboarding-issues-on-the-device). <br><br> Verifique os logs de eventos MDM na tabela a seguir ou siga as instruções em [Diagnostic MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).
 | | | | Todos | **Causa possível:** Tente implantar o Microsoft Defender para Ponto de Extremidade em SKU/Platform sem suporte, especialmente SKU holográfico. <br><br> Plataformas com suporte no momento:<br> Enterprise, Educação e Professional.<br> O servidor não tem suporte.
 0x87D101A9 | -2016345687 |SyncML(425): O comando solicitado falhou porque o remetente não tem permissões adequadas de controle de acesso (ACL) no destinatário. | Todos |  **Causa possível:** Tente implantar o Microsoft Defender para Ponto de Extremidade em SKU/Platform sem suporte, especialmente SKU holográfico.<br><br> Plataformas com suporte no momento:<br>  Enterprise, Educação e Professional.

#### <a name="known-issues-with-non-compliance"></a>Problemas conhecidos com falta de conformidade

A tabela a seguir fornece informações sobre problemas de não conformidade e como você pode resolver os problemas.

Caso | Sintomas | Possíveis etapas de causa e solução de problemas
:---:|:---|:---
 `1` | O dispositivo é compatível com SenseIsRunning OMA-URI. Mas não é compatível com OrgId, Onboarding e OnboardingState OMA-URIs. | **Causa possível:** Verifique se o usuário passou o OOBE após Windows instalação ou atualização. Durante a integração OOBE não foi possível concluir, mas o SENSE já está em execução.<br><br> **Etapas de solução de problemas:** Aguarde a conclusão do OOBE.
 `2` |  O dispositivo é compatível com OrgId, Onboarding e OnboardingState OMA-URIs, mas não é compatível com SenseIsRunning OMA-URI. |  **Causa possível:** O tipo de inicialização do serviço Sense é definido como "Início Atrasado". Às vezes, isso faz com que Microsoft Intune servidor do Microsoft Intune reporte o dispositivo como não compatível com SenseIsRunning quando a sessão de DM ocorre no início do sistema. <br><br> **Etapas de solução de problemas:** O problema deve ser corrigido automaticamente dentro de 24 horas.
 `3` | O dispositivo não é compatível | **Etapas de solução de problemas:** Verifique se as políticas de integração e de offboard não são implantadas no mesmo dispositivo ao mesmo tempo.

#### <a name="mobile-device-management-mdm-event-logs"></a>Logs de eventos do Gerenciamento de Dispositivo Móvel (MDM)

Exibir os logs de eventos MDM para solucionar problemas que podem surgir durante a integração:

Nome do log: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider

Nome do canal: Admin

ID | Severity | Descrição do Evento | Etapas para a solução de problemas
:---|:---|:---|:---
1819 | Error | CSP do Microsoft Defender para Ponto de Extremidade: Falha ao definir o valor do nó. NodeId: (%1), TokenName: (%2), Resultado: (%3). | Baixe a [Atualização Cumulativa para Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).

## <a name="troubleshoot-onboarding-issues-on-the-device"></a>Solucionar problemas de integração no dispositivo

Se as ferramentas de implantação usadas não indicarem um erro no processo de integração, mas os dispositivos ainda não aparecerem na lista de dispositivos em uma hora, consulte os tópicos de verificação a seguir para verificar se ocorreu um erro com o agente do Microsoft Defender para Ponto de Extremidade.

- [Exibir erros de integração do agente no log de eventos do dispositivo](#view-agent-onboarding-errors-in-the-device-event-log)
- [Verifique se o serviço de dados de diagnóstico está habilitado](#ensure-the-diagnostics-service-is-enabled)
- [Verifique se o serviço está definido para iniciar](#ensure-the-service-is-set-to-start)
- [Verifique se o dispositivo tem uma conexão com a Internet](#ensure-the-device-has-an-internet-connection)
- [Verifique se Microsoft Defender Antivírus não está desabilitado por uma política](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a>Exibir erros de integração do agente no log de eventos do dispositivo

1. Clique **em Iniciar,** digite **Visualizador de Eventos** e pressione **Enter**.

2. No painel Visualizador de Eventos **(Local),** expanda **Logs de** Aplicativos e Serviços  >  **da Microsoft**  >  **Windows**  >  **SENSE**.

   > [!NOTE]
   > SENSE é o nome interno usado para se referir ao sensor comportamental que alimenta o Microsoft Defender para o Ponto de Extremidade.

3. Selecione **Operacional** para carregar o log.

4. No painel **Ação,** clique em **Filtrar log atual.**

5. Na guia **Filtro,** em **Nível de evento:** selecione **Crítico,** **Aviso** e **Erro** e clique em **OK**.

   ![Imagem do filtro de log do Visualizador de Eventos](images/filter-log.png)

6. Os eventos que podem indicar problemas serão exibidos no **painel** Operacional. Você pode tentar solucionar problemas com base nas soluções na tabela a seguir:

ID do evento | Mensagem | Etapas de resolução
:---:|:---|:---
 `5` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se conectar ao servidor em _variável_ | [Verifique se o dispositivo tem acesso à Internet.](#ensure-the-device-has-an-internet-connection)
 `6` | O serviço do Microsoft Defender para Ponto de Extremidade não está integrado e nenhum parâmetro de integração foi encontrado. Código de falha: _variável_ | [Execute o script de integração novamente](configure-endpoints-script.md).
 `7` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao ler os parâmetros de integração. Código de falha: _variável_ | [Verifique se o dispositivo tem acesso à Internet](#ensure-the-device-has-an-internet-connection)e execute todo o processo de integração novamente.
 `9` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar seu tipo de início. Código de falha: variável | Se o evento aconteceu durante a integração, reinicie e tente executar o script de integração. Para obter mais informações, consulte [Executar o script de integração novamente](configure-endpoints-script.md). <br><br>Se o evento ocorreu durante o offboard, contate o suporte.
`10` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter as informações de integração. Código de falha: variável | Se o evento aconteceu durante a integração, tente executar o script de integração. Para obter mais informações, consulte [Executar o script de integração novamente](configure-endpoints-script.md). <br><br>Se o problema persistir, contate o suporte.
`15` | O Microsoft Defender para Ponto de Extremidade não pode iniciar o canal de comando com URL: _variável_ | [Verifique se o dispositivo tem acesso à Internet.](#ensure-the-device-has-an-internet-connection)
`17` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar o local do serviço Experiências do Usuário Conectado e Telemetria. Código de falha: variável | [Execute o script de integração novamente](configure-endpoints-script.md). Se o problema persistir, contate o suporte.
`25` | O serviço do Microsoft Defender para Ponto de Extremidade falhou ao redefinir o status de saúde no Registro. Código de falha: _variável_ | Fale com o suporte.
`27` | Falha ao habilitar o Microsoft Defender para o modo Ponto de Extremidade Windows Defender. Falha no processo de integração. Código de falha: variável | Fale com o suporte.
`29` | Falha ao ler os parâmetros de offboarding. Tipo de erro: %1, Código de erro: %2, Descrição: %3 | Verifique se o dispositivo tem acesso à Internet e execute todo o processo de offboard novamente.
`30` | Falha ao desabilitar o modo $(build.sense.productDisplayName) no Microsoft Defender para Ponto de Extremidade. Código de falha: %1 | Fale com o suporte.
`32` | $ serviço $(build.sense.productDisplayName) falhou ao solicitar para parar a si mesmo após o processo de offboard. Código de falha: %1 | Verifique se o tipo de início do serviço é manual e reinicie o dispositivo.
`55` | Falha ao criar o autologger ETW seguro. Código de falha: %1 | Reinicie o dispositivo.
`63` | Atualizando o tipo de início do serviço externo. Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4 | Identifique o que está causando alterações no tipo de início do serviço mencionado. Se o código de saída não for 0, corrige o tipo de início manualmente para o tipo de início esperado.
`64` | Iniciando o serviço externo interrompido. Nome: %1, código de saída: %2 | Contate o suporte se o evento continuar a aparecer.
`68` | O tipo de início do serviço é inesperado. Nome do serviço: %1, tipo de início real: %2, tipo de início esperado: %3 | Identifique o que está causando alterações no tipo de início. Corrigir o tipo de início de serviço mencionado.
`69` | O serviço é interrompido. Nome do serviço: %1 | Inicie o serviço mencionado. Contate o suporte se persistir.

<br />

Há componentes adicionais no dispositivo de que o agente do Microsoft Defender for Endpoint depende para funcionar corretamente. Se não houver erros relacionados à integração no log de eventos do agente do Microsoft Defender for Endpoint, prossiga com as etapas a seguir para garantir que os componentes adicionais sejam configurados corretamente.

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a>Verifique se o serviço de dados de diagnóstico está habilitado

Se os dispositivos não estão relatando corretamente, talvez seja necessário verificar se o serviço Windows 10 de dados de diagnóstico está definido para iniciar automaticamente e está sendo executado no dispositivo. O serviço pode ter sido desabilitado por outros programas ou alterações na configuração do usuário.

Primeiro, você deve verificar se o serviço está definido para ser iniciado automaticamente quando o Windows for iniciado, em seguida, verifique se o serviço está em execução no momento (e inicie-o se não estiver).

### <a name="ensure-the-service-is-set-to-start"></a>Verifique se o serviço está definido para iniciar

**Use a linha de comando para verificar o tipo Windows 10 de inicialização** do serviço de dados de diagnóstico:

1. Abra um prompt de linha de comando elevada no dispositivo:

   a. Clique **em Iniciar,** **digite cmd** e pressione **Enter**.

   b. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   ```text
   sc qc diagtrack
   ```

   Se o serviço estiver habilitado, o resultado deverá ter a seguinte captura de tela:

   ![Resultado do comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)

   Se o `START_TYPE` não estiver definido como , você precisará definir o serviço para iniciar `AUTO_START` automaticamente.

**Use a linha de comando para definir o serviço Windows 10 de dados de diagnóstico para iniciar automaticamente:**

1. Abra um prompt de linha de comando elevada no dispositivo:

   a. Clique **em Iniciar,** **digite cmd** e pressione **Enter**.

   b. Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.

2. Insira o seguinte comando e pressione **Enter**:

   ```text
   sc config diagtrack start=auto
   ```

3. Uma mensagem de sucesso é exibida. Verifique a alteração inserindo o seguinte comando e pressione **Enter**:

   ```text
   sc qc diagtrack
   ```

4. Inicie o serviço.

   a. No prompt de comando, digite o seguinte comando e pressione **Enter**:

   ```text
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a>Verifique se o dispositivo tem uma conexão com a Internet

O sensor Microsoft Defender ATP requer o Microsoft Windows HTTP (WinHTTP) para relatar os dados do sensor e se comunicar com o serviço Microsoft Defender ATP.

O WinHTTP é independente das configurações de proxy de navegação na Internet e de outros aplicativos de contexto de usuário e deve ser capaz de detectar os servidores proxy que estão disponíveis em seu ambiente específico.

Para garantir que o sensor tenha conectividade de serviço, siga as etapas descritas no tópico Verificar a conectividade do cliente com o [Microsoft Defender para URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) de serviço de ponto de extremidade.

Se a verificação falhar e seu ambiente estiver usando um proxy para se conectar à Internet, siga as etapas descritas em [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a>Verifique se Microsoft Defender Antivírus não está desabilitado por uma política

> [!IMPORTANT]
> O seguinte só se aplica  a dispositivos que ainda não receberam a atualização de agosto de 2020 (versão 4.18.2007.8) para Microsoft Defender Antivírus.
>
> A atualização garante que o Microsoft Defender Antivírus não possa ser desligado em dispositivos cliente por meio da política do sistema.

**Problema**: o serviço do Microsoft Defender para Ponto de Extremidade não começa após a integração.

**Sintoma**: a integração é concluída com êxito, mas você vê o erro 577 ou o erro 1058 ao tentar iniciar o serviço.

**Solução**: se seus dispositivos estão executando um cliente antimalware de terceiros, o agente do Microsoft Defender for Endpoint precisa do driver ELAM (Antimalware de Início Antecipado) para ser habilitado. Você deve garantir que ele não está desligado por uma política do sistema.

- Dependendo da ferramenta que você usa para implementar políticas, você precisará verificar se as seguintes políticas Windows Defender estão limpas:

  - DisableAntiSpyware
  - DisableAntiVirus

  Por exemplo, na Política de Grupo, não deve haver entradas como os seguintes valores:

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> A configuração é descontinuada e será ignorada em todos os dispositivos clientes, a partir da atualização de agosto de `disableAntiSpyware` 2020 (versão 4.18.2007.8) para Microsoft Defender Antivírus.

- Depois de limpar a política, execute as etapas de integração novamente.

- Você também pode verificar os valores de chave do Registro anterior para verificar se a política está desabilitada, abrindo a chave do Registro `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .

    ![Imagem da chave do Registro para Microsoft Defender Antivírus](images/atp-disableantispyware-regkey.png)

   > [!NOTE]
   > Todos os Windows Defender (wdboot, wdfilter, wdnisdrv, wdnissvc e windefend) devem estar em seu estado padrão. Alterar a inicialização desses serviços não é compatível e pode forçar você a reimagear seu sistema.
   >
   > Exemplo de configurações padrão para WdBoot e WdFilter:
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues-on-a-server"></a>Solucionar problemas de integração em um servidor

Se você encontrar problemas durante a integração de um servidor, vá pelas etapas de verificação a seguir para resolver possíveis problemas.

- [Verifique se Microsoft Monitoring Agent (MMA) está instalado e configurado para relatar dados do sensor ao serviço](configure-server-endpoints.md)
- [Verifique se o proxy do servidor e as configurações de conectividade com a Internet estão configuradas corretamente](configure-server-endpoints.md)

Você também pode precisar verificar o seguinte:

- Verifique se há um Serviço do Microsoft Defender para Ponto de Extremidade em execução na guia **Processos** no **Gerenciador de Tarefas.** Por exemplo:

    ![Imagem de exibição de processo com o Microsoft Defender para Serviço de Ponto de Extremidade em execução](images/atp-task-manager.png)

- Verifique **o Gerenciador de** Operações de Logs de Aplicativos e Serviços do Visualizador de Eventos para ver se há algum  >    >   erro.

- Em **Serviços,** verifique se o **Microsoft Monitoring Agent** está sendo executado no servidor. Por exemplo,

    ![Imagem dos Serviços](images/atp-services.png)

- Em **Microsoft Monitoring Agent**  >  **Análise de Log do Azure (OMS),** verifique os Espaços de Trabalho e verifique se o status está em execução.

    ![Imagem de Microsoft Monitoring Agent Propriedades](images/atp-mma-properties.png)

- Verifique se os dispositivos são refletidos na lista **Dispositivos** no portal.

## <a name="confirming-onboarding-of-newly-built-devices"></a>Confirmando a integração de dispositivos recém-construídos

Pode haver instâncias em que a integração é implantada em um dispositivo recém-criado, mas não concluída.

As etapas a seguir fornecem orientações para o seguinte cenário:

- O pacote de integração é implantado em dispositivos recém-construídos
- O sensor não inicia porque a experiência inicial (OOBE) ou o primeiro logon do usuário não foi concluído
- O dispositivo é desligado ou reiniciado antes que o usuário final execute um primeiro logon
- Nesse cenário, o serviço SENSE não iniciará automaticamente, mesmo que o pacote de integração tenha sido implantado

> [!NOTE]
> As etapas a seguir só são relevantes ao usar Microsoft Endpoint Configuration Manager. Para obter mais detalhes sobre a integração usando Microsoft Endpoint Configuration Manager, consulte [Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).

1. Crie um aplicativo em Microsoft Endpoint Configuration Manager.

    ![Imagem de Microsoft Endpoint Configuration Manager configuração1](images/mecm-1.png)

2. Selecione **Especificar manualmente as informações do aplicativo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 2](images/mecm-2.png)

3. Especifique informações sobre o aplicativo e selecione **Next**.

    ![Imagem da Microsoft Endpoint Configuration Manager 3](images/mecm-3.png)

4. Especifique informações sobre o centro de software e selecione **Next**.

    ![Imagem da Microsoft Endpoint Configuration Manager 4](images/mecm-4.png)

5. Em **Tipos de implantação,** **selecione Adicionar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 5](images/mecm-5.png)

6. Selecione **Especificar manualmente as informações de tipo de implantação** e, em seguida, **selecione Next**.

    ![Imagem da Microsoft Endpoint Configuration Manager 6](images/mecm-6.png)

7. Especifique informações sobre o tipo de implantação e selecione **Next**.

    ![Imagem da Microsoft Endpoint Configuration Manager 7](images/mecm-7.png)

8. Em **Programa de** Instalação de  >  **Conteúdo,** especifique o comando: `net start sense` .

    ![Imagem da Microsoft Endpoint Configuration Manager 8](images/mecm-8.png)

9. No **método Detection,** selecione **Configurar regras para detectar a** presença desse tipo de implantação e, em seguida, selecione Adicionar **Cláusula**.

    ![Imagem da Microsoft Endpoint Configuration Manager 9](images/mecm-9.png)

10. Especifique os seguintes detalhes da regra de detecção e selecione **OK**:

    ![Imagem da Microsoft Endpoint Configuration Manager 10](images/mecm-10.png)

11. No **método Detection,** selecione **Next**.

    ![Imagem da Microsoft Endpoint Configuration Manager 11](images/mecm-11.png)

12. Na **Experiência do Usuário,** especifique as seguintes informações e selecione **Next**:

    ![Imagem da Microsoft Endpoint Configuration Manager 12](images/mecm-12.png)

13. Em **Requisitos,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 13](images/mecm-13.png)

14. Em **Dependências,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 14](images/mecm-14.png)

15. Em **Resumo,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 15](images/mecm-15.png)

16. Em **Conclusão,** selecione **Fechar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 16](images/mecm-16.png)

17. Em **Tipos de implantação,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager configuração17](images/mecm-17.png)

18. Em **Resumo,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 18](images/mecm-18.png)

    Em seguida, o status é exibido: ![ Imagem da Microsoft Endpoint Configuration Manager configuração19](images/mecm-19.png)

19. Em **Conclusão,** selecione **Fechar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 20](images/mecm-20.png)

20. Agora você pode implantar o aplicativo clicando com o botão direito do mouse no aplicativo e selecionando **Implantar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 21](images/mecm-21.png)

21. Em **Geral,** **selecione Distribuir automaticamente conteúdo para dependências** e **Procurar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 22](images/mecm-22.png)

22. Em **Conteúdo,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 23](images/mecm-23.png)

23. Em **Configurações de implantação,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 24](images/mecm-24.png)

24. Em **Agendamento** selecione Assim que possível após o horário **disponível,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 25](images/mecm-25.png)

25. Na **experiência do usuário,** selecione Confirma as alterações no prazo ou durante uma janela de **manutenção (requer reinicializações)** e selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 26](images/mecm-26.png)

26. Em **Alertas,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 27](images/mecm-27.png)

27. Em **Resumo,** selecione **Próximo**.

    ![Imagem da Microsoft Endpoint Configuration Manager 28](images/mecm-28.png)

    Em seguida, o status é exibido ![ Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)

28. Em **Conclusão,** selecione **Fechar**.

    ![Imagem da Microsoft Endpoint Configuration Manager 30](images/mecm-30.png)


## <a name="related-topics"></a>Tópicos relacionados

- [Solucionar problemas do Microsoft Defender para Ponto de Extremidade](troubleshoot-mdatp.md)
- [Integração de dispositivos](onboard-configure.md)
- [Definir as configurações de proxy de dispositivo e conectividade com a Internet](configure-proxy-internet.md)
