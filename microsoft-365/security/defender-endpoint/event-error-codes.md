---
title: Revisar eventos e erros usando o Visualizador de Eventos
description: Obter descrições e etapas adicionais de solução de problemas (se necessário) para todos os eventos relatados pelo serviço do Microsoft Defender para Ponto de Extremidade.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, can't start, broken, can't start
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
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222643"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Revisar eventos e erros usando o Visualizador de Eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- Visualizador de eventos
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Você pode revisar as IDs de eventos no [Visualizador de](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) Eventos em dispositivos individuais.

Por exemplo, se os dispositivos não aparecerem na lista **Dispositivos,** talvez seja necessário procurar IDs de eventos nos dispositivos. Em seguida, você pode usar essa tabela para determinar outras etapas de solução de problemas.

**Abra o Visualizador de Eventos e encontre o log de eventos de serviço do Microsoft Defender for Endpoint:**

1. Clique **em** Iniciar no menu Windows, digite **Visualizador de** Eventos e pressione **Enter**.

2. Na lista de log, em **Resumo de Log,** role até ver **Microsoft-Windows-SENSE/Operational**. Clique duas vezes no item para abrir o log.

   a.  Você também pode acessar o log expandindo Aplicativos **e Serviços Registra o**  >  **Microsoft**  >  **Windows**  >  **SENSE** e clique em **Operacional**.

   > [!NOTE]
   > SENSE é o nome interno usado para se referir ao sensor comportamental que alimenta o Microsoft Defender para o Ponto de Extremidade.

3. Os eventos gravados pelo serviço serão exibidos no log. Consulte a tabela a seguir para ver uma lista de eventos gravados pelo serviço.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>ID do evento</th>
<th>Mensagem</th>
<th>Descrição</th>
<th>Action</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint service started (Version <code>variable</code> ).</td>
<td>Ocorre durante a inicialização do sistema, o desligar e durante a integração.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>2</td>
<td>Desligamento do serviço do Microsoft Defender para Ponto de Extremidade.</td>
<td>Ocorre quando o dispositivo é desligado ou desligado.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>3</td>
<td>Falha ao iniciar o serviço do Microsoft Defender para Ponto de Extremidade. Código de falha: <code>variable</code> .</td>
<td>O serviço não começou.</td>
<td>Revise outras mensagens para determinar possíveis causas e etapas de solução de problemas.</td>
</tr>
<tr>
<td>4 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade entrou em contato com o servidor em <code>variable</code> .</td>
<td>Variável = URL dos servidores de processamento do Defender for Endpoint.<br>
Essa URL corresponderá às vistas na atividade firewall ou de rede.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>5 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se conectar ao servidor em <code>variable</code> .</td>
<td>Variável = URL dos servidores de processamento do Defender for Endpoint.<br>
O serviço não pôde entrar em contato com os servidores de processamento externos nessa URL.</td>
<td>Verifique a conexão com a URL. Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade não está integrado e nenhum parâmetro de integração foi encontrado.</td>
<td>O dispositivo não entrou corretamente e não estará relatando para o portal.</td>
<td>A integração deve ser executado antes de iniciar o serviço.<br>
Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>7 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao ler os parâmetros de integração. Falha: <code>variable</code> .</td>
<td>Variável = descrição de erro detalhada. O dispositivo não entrou corretamente e não estará relatando para o portal.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>8 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao limpar sua configuração. Código de falha: <code>variable</code> .</td>
<td><b>Durante a integração:</b> O serviço falhou ao limpar sua configuração durante a integração. O processo de integração continua. <br><br> <b>Durante o offboard:</b> O serviço falhou ao limpar sua configuração durante o offboard. O processo de offboarding foi concluído, mas o serviço continua em execução.
 </td>
<td><b>Integração:</b> Nenhuma ação é necessária. <br><br> <b>Offboarding:</b> Reinicie o sistema.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>9 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar seu tipo de início. Código de falha: <code>variable</code> .</td>
<td><b>Durante a integração:</b> O dispositivo não entrou corretamente e não estará relatando para o portal. <br><br><b>Durante o offboard:</b> Falha ao alterar o tipo de início do serviço. O processo de offboarding continua. </td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>10 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter as informações de integração. Código de falha: <code>variable</code> .</td>
<td>O dispositivo não entrou corretamente e não estará relatando para o portal.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>11</td>
<td>Integração ou rea integração do serviço do Defender for Endpoint concluída.</td>
<td>O dispositivo foi corretamente conectado.</td>
<td>Notificação operacional normal; nenhuma ação necessária.<br>
Pode levar várias horas para que o dispositivo apareça no portal.</td>
</tr>
<tr>
<td>12 </td>
<td>O Microsoft Defender para Ponto de Extremidade falhou ao aplicar a configuração padrão.</td>
<td>O serviço não pôde aplicar a configuração padrão.</td>
<td>Esse erro deve ser resolvido após um curto período de tempo.</td>
</tr>
<tr>
<td>13</td>
<td>A ID do dispositivo Do Microsoft Defender para Ponto de Extremidade foi calculada: <code>variable</code> .</td>
<td>Processo operacional normal.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>15 </td>
<td>O Microsoft Defender para Ponto de Extremidade não pode iniciar o canal de comando com URL: <code>variable</code> .</td>
<td>Variável = URL dos servidores de processamento do Defender for Endpoint.<br>
O serviço não pôde entrar em contato com os servidores de processamento externos nessa URL.</td>
<td>Verifique a conexão com a URL. Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar o local do serviço Experiências do Usuário Conectado e Telemetria. Código de falha: <code>variable</code> .</td>
<td>Ocorreu um erro com o serviço de telemetria do Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.<br>
Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Boas-vindas do Windows) está concluído.</td>
<td>O serviço só será iniciar depois que todas as atualizações do Windows terminarem de instalar.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Boas-vindas do Windows) ainda não foi concluído.</td>
<td>O serviço só será iniciar depois que todas as atualizações do Windows terminarem de instalar.</td>
<td>Notificação operacional normal; nenhuma ação necessária.<br>
Se esse erro persistir após uma reinicialização do sistema, certifique-se de que todas as atualizações do Windows tenham sido instaladas.</td>
</tr>
<tr>
<td>20</td>
<td>Não é possível aguardar a conclusão do OOBE (Boas-vindas do Windows). Código de falha: <code>variable</code> .</td>
<td>Erro interno.</td>
<td>Se esse erro persistir após uma reinicialização do sistema, certifique-se de que todas as atualizações do Windows tenham sido instaladas.</td>
</tr>
<tr>
<td>25</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao redefinir o status de saúde no Registro. Código de falha: <code>variable</code> .</td>
<td>O dispositivo não foi a bordo corretamente.
Ele informará ao portal, no entanto, o serviço pode não aparecer como registrado no SCCM ou no Registro.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>26</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao definir o status de integração no Registro. Código de falha: <code>variable</code> .</td>
<td>O dispositivo não foi a bordo corretamente.<br>
Ele informará ao portal, no entanto, o serviço pode não aparecer como registrado no SCCM ou no Registro.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>27</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao habilitar o modo de conhecimento SENSE no Microsoft Defender Antivírus. Falha no processo de integração. Código de falha: <code>variable</code> .</td>
<td>Normalmente, o Microsoft Defender Antivírus entrará em um estado passivo especial se outro produto antimalware em tempo real estiver sendo executado corretamente no dispositivo e o dispositivo estiver relatando ao Defender para o Ponto de Extremidade.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.<br>
Verifique se a proteção antimalware em tempo real está sendo executado corretamente.</td>
</tr>
<tr>
<td>28</td>
<td>Falha no registro do serviço de Telemetria e experiências de usuário conectados do Microsoft Defender for Endpoint. Código de falha: <code>variable</code> .</td>
<td>Ocorreu um erro com o serviço de telemetria do Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.<br>
Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>29</td>
<td>Falha ao ler os parâmetros de offboarding. Tipo de erro: %1, Código de erro: %2, Descrição: %3 </td>
<td>Esse evento ocorre quando o sistema não&#39;ler os parâmetros de offboarding.</td>
<td>Verifique se o dispositivo tem acesso à Internet e execute todo o processo de offboard novamente. Verifique se o pacote de offboarding não expirou.</td>
</tr>
<tr>
<td>30</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao desabilitar o modo de conhecimento do SENSE no Microsoft Defender Antivírus. Código de falha: <code>variable</code> .</td>
<td>Normalmente, o Microsoft Defender Antivírus entrará em um estado passivo especial se outro produto antimalware em tempo real estiver sendo executado corretamente no dispositivo e o dispositivo estiver relatando ao Defender para o Ponto de Extremidade.</td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a><br>
Verifique se a proteção antimalware em tempo real está sendo executado corretamente.</td>
</tr>
<tr>
<td>31</td>
<td>Falha no microsoft defender para experiências de usuário conectados e serviço de telemetria. Código de falha: <code>variable</code> .</td>
<td>Ocorreu um erro com o serviço de telemetria do Windows durante a integração. O processo de offboarding continua.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Verifique se há erros com o serviço de telemetria do Windows.</a></td>
</tr>
<tr>
<td>32</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao solicitar a interrupção de si mesmo após o processo de offboard. Código de falha: %1</td>
<td>Ocorreu um erro durante o offboarding.</td>
<td>Reinicie o dispositivo.</td>
</tr>
<tr>
<td>33</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter o GUID DO SENSE. Código de falha: <code>variable</code> .</td>
<td>Um identificador exclusivo é usado para representar cada dispositivo que está relatando para o portal.<br>
Se o identificador não persistir, o mesmo dispositivo poderá aparecer duas vezes no portal.</td>
<td>Verifique as permissões do Registro no dispositivo para garantir que o serviço possa atualizar o Registro.</td>
</tr>
<tr>
<td>34</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao adicionar a si mesmo como uma dependência do serviço Experiências de Usuário Conectado e Telemetria, causando falha no processo de integração. Código de falha: <code>variable</code> .</td>
<td>Ocorreu um erro com o serviço de telemetria do Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.<br>
Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>35</td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se remover como uma dependência do serviço Experiências de Usuário Conectado e Telemetria. Código de falha: <code>variable</code> .</td>
<td>Ocorreu um erro com o serviço de telemetria do Windows durante o offboard. O processo de offboarding continua.
</td>
<td>Verifique se há erros com o serviço de dados de diagnóstico do Windows.</td>
</tr>
<tr>
<td>36</td>
<td>O registro de serviço de Telemetria e Experiências de Usuário Conectados do Microsoft Defender for Endpoint foi bem-sucedido. Código de conclusão: <code>variable</code> .</td>
<td>Registrar o Defender para Ponto de Extremidade com o serviço Experiências de Usuário Conectado e Telemetria concluída com êxito.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender para Ponto de Extremidade Um módulo está prestes a exceder sua cota. Módulo: %1, Cota: {%2} {%3}, Porcentagem de utilização da cota: %4.</td>
<td>O dispositivo quase usou sua cota alocada da janela atual de 24 horas. Está prestes a ser acelerada.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>38</td>
<td>A conexão de rede é identificada como baixa. O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto. Conexão com medida: %2, internet disponível: %3, rede gratuita disponível: %4.</td>
<td>O dispositivo está usando uma rede medição/paga e entrará em contato com o servidor com menos frequência.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>39</td>
<td>A conexão de rede é identificada como normal. O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto. Conexão com medida: %2, internet disponível: %3, rede gratuita disponível: %4.</td>
<td>O dispositivo não está usando uma conexão com medição/pagamento e entrará em contato com o servidor como de costume.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>40</td>
<td>O estado da bateria é identificado como baixo. O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto. Estado da bateria: %2.</td>
<td>O dispositivo tem baixo nível de bateria e entrará em contato com o servidor com menos frequência.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>41</td>
<td>O estado da bateria é identificado como normal. O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto. Estado da bateria: %2.</td>
<td>O dispositivo não tem baixo nível de bateria e entrará em contato com o servidor como de costume.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>42</td>
<td>O componente WDATP do Microsoft Defender para Ponto de Extremidade falhou ao executar a ação. Componente: %1, Ação: %2, Tipo de Exceção: %3, Mensagem de exceção: %4</td>
<td>Erro interno. Falha ao iniciar o serviço.</td>
<td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
<td>43</td>
<td>O componente WDATP do Microsoft Defender para Ponto de Extremidade falhou ao executar a ação. Componente: %1, Ação: %2, Tipo de Exceção: %3, Erro de Exceção: %4, Mensagem de exceção: %5</td>
<td>Erro interno. Falha ao iniciar o serviço.</td>
<td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding do Serviço do Defender para Ponto de Extremidade concluído.</td>
<td>O serviço foi desligado.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>45</td>
<td>Falha ao registrar e iniciar a sessão de rastreamento de eventos [%1]. Código de erro: %2</td>
<td>Ocorreu um erro na inicialização do serviço durante a criação da sessão ETW. Isso causou uma falha na iniciação do serviço.</td>
<td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
<td>46</td>
<td>Falha ao registrar e iniciar a sessão de rastreamento de eventos [%1] devido à falta de recursos. Código de erro: %2. Isso é mais provável porque há muitas sessões de rastreamento de eventos ativas. O serviço repetirá em 1 minuto.</td>
<td>Ocorreu um erro na inicialização do serviço ao criar sessão ETW devido à falta de recursos. O serviço foi iniciado e está em execução, mas não relatará nenhum evento de sensor até que a sessão ETW seja iniciada.</td>
<td>Notificação operacional normal; nenhuma ação necessária. O serviço tentará iniciar a sessão a cada minuto.</td>
</tr>
<tr>
<td>47</td>
<td>Registrou com êxito e iniciou a sessão de rastreamento de eventos - recuperada após tentativas anteriores com falha.</td>
<td>Este evento segue o evento anterior após o início com êxito da sessão ETW.</td>
<td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
<td>48</td>
<td>Falha ao adicionar um provedor [%1] à sessão de rastreamento de eventos [%2]. Código de erro: %3. Isso significa que os eventos deste provedor não serão relatados.</td>
<td>Falha ao adicionar um provedor à sessão ETW. Como resultado, os eventos do provedor não são relatados.</td>
<td>Verifique o código de erro. Se o erro persistir, contate Suporte.</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>Comando de configuração de nuvem inválido recebido e ignorado. Versão: %1, status: %2, código de erro: %3, mensagem: %4</td>
   <td>Recebeu um arquivo de configuração inválido do serviço de nuvem que foi ignorado.</td>
   <td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>50</td>
   <td>Nova configuração de nuvem aplicada com êxito. Versão: %1.</td>
   <td>Aplicou com êxito uma nova configuração do serviço de nuvem.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>51</td>
   <td>Falha na aplicação da nova configuração de nuvem, versão: %1. Aplicou com êxito a última boa configuração conhecida, versão %2.</td>
   <td>Recebeu um arquivo de configuração ruim do serviço de nuvem. A última boa configuração conhecida foi aplicada com êxito.</td>
   <td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>52</td>
   <td>Falha na aplicação da nova configuração de nuvem, versão: %1. Também falhou ao aplicar a última boa configuração conhecida, versão %2. Aplicou com êxito a configuração padrão.</td>
   <td>Recebeu um arquivo de configuração ruim do serviço de nuvem. Falha ao aplicar a última boa configuração conhecida e a configuração padrão foi aplicada.</td>
   <td>O serviço tentará baixar um novo arquivo de configuração em 5 minutos. Se você não vir o evento #50 - entre em contato com o Suporte.</td>
</tr>
<tr>
   <td>53</td>
   <td>Configuração de nuvem carregada do armazenamento persistente, versão: %1.</td>
   <td>A configuração foi carregada do armazenamento persistente na inicialização do serviço.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>55</td>
   <td>Falha ao criar o autologger ETW seguro. Código de falha: %1</td>
   <td>Falha ao criar o madeireiro ETW seguro.</td>
   <td>Reinicie o dispositivo. Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>56</td>
   <td>Falha ao remover o autologger ETW seguro. Código de falha: %1</td>
   <td>Falha ao remover a sessão ETW segura no offboard.</td>
   <td>Contate o Suporte.</td>
</tr>
<tr>
   <td>57</td>
   <td>Capturando um instantâneo do computador para fins de solução de problemas.</td>
   <td>Um pacote de investigação, também conhecido como pacote forense, está sendo coletado.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>59</td>
   <td>Comando inicial: %1</td>
   <td>Iniciando a execução do comando de resposta.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>60</td>
   <td>Falha ao executar o comando %1, erro: %2.</td>
   <td>Falha ao executar o comando de resposta.</td>
   <td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>61</td>
   <td>Os parâmetros de comando da coleção de dados são inválidos: SasUri: %1, compressionLevel: %2.</td>
   <td>Falha ao ler ou analisar os argumentos de comando da coleção de dados (argumentos inválidos).</td>
   <td>Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>62</td>
   <td>Falha ao iniciar o serviço Experiências de Usuário Conectado e Telemetria. Código de falha: %1</td>
   <td>Falha ao iniciar o serviço Experiências do Usuário Conectado e Telemetria (diagtrack). A telemetria que não seja do Microsoft Defender para Ponto de Extremidade não será enviada desse computador.</td>
   <td>Procure mais dicas de solução de problemas no log de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.</td>
</tr>
<tr>
   <td>63</td>
   <td>Atualizando o tipo de início do serviço externo. Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4</td>
   <td>Tipo de início atualizado do serviço externo.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>64</td>
   <td>Iniciando o serviço externo interrompido. Nome: %1, código de saída: %2</td>
   <td>Iniciando um serviço externo.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>65</td>
   <td>Falha ao carregar o driver de Minifiltro de Componente de Eventos de Segurança da Microsoft. Código de falha: %1</td>
   <td>Falha ao carregar MsSecFlt.sys minifiltro de sistema de arquivos.</td>
   <td>Reinicie o dispositivo. Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>66</td>
   <td>Atualização de política: modo de latência - %1</td>
   <td>A C# de frequência de conexão do C&C foi atualizada.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>68</td>
   <td>O tipo de início do serviço é inesperado. Nome do serviço: %1, tipo de início real: %2, tipo de início esperado: %3</td>
   <td>Tipo de início de serviço externo inesperado.</td>
   <td>Correção do tipo de início do serviço externo.</td>
</tr>
<tr>
   <td>69</td>
   <td>O serviço é interrompido. Nome do serviço: %1</td>
   <td>O serviço externo é interrompido.</td>
   <td>Inicie o serviço externo.</td>
</tr>
<tr>
   <td>70</td>
   <td>Atualização de política: Permitir coleta de amostras - %1</td>
   <td>A política de coleta de exemplo foi atualizada.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>71</td>
   <td>Com êxito para executar o comando: %1</td>
   <td>O comando foi executado com êxito.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>72</td>
   <td>Tentou enviar o primeiro relatório de perfil completo do computador. Código do resultado: %1</td>
   <td>Somente informações.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>73</td>
   <td>Sentido de início da plataforma: %1</td>
   <td>Somente informações.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>74</td>
   <td>A marca de dispositivo no Registro excede o limite de comprimento. Nome da marca: %2. Limite de comprimento: %1.</td>
   <td>A marca do dispositivo excede o limite de comprimento.</td>
   <td>Use uma marca de dispositivo mais curta.</td>
</tr>
<tr>
   <td>81</td>
   <td>Falha ao criar um Windows Defender etlogger ETW da Proteção Avançada contra Ameaças. Código de falha: %1</td>
   <td>Falha ao criar a sessão ETW.</td>
   <td>Reinicie o dispositivo. Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>82</td>
   <td>Falha ao remover o Windows Defender etlogger ETW da Proteção Avançada contra Ameaças. Código de falha: %1</td>
   <td>Falha ao excluir a sessão ETW.</td>
   <td>Contate o Suporte.</td>
</tr>
<tr>
   <td>84</td>
   <td>Definir Windows Defender modo de execução antivírus. Forçar o modo passivo: %1, código de resultado: %2.</td>
   <td>Definir o modo de execução do defender (ativo ou passivo).</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>85</td>
   <td>Falha ao disparar Windows Defender proteção avançada contra ameaças executável. Código de falha: %1</td>
   <td>Falha no executável SenseIR estrelado.</td>
   <td>Reinicie o dispositivo. Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>86</td>
   <td>A partida novamente interrompeu o serviço externo que deveria estar para cima. Nome: %1, código de saída: %2</td>
   <td>Iniciando o serviço externo novamente.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>87</td>
   <td>Não é possível iniciar o serviço externo. Nome: %1</td>
   <td>Falha ao iniciar o serviço externo.</td>
   <td>Contate o Suporte.</td>
</tr>
<tr>
   <td>88</td>
   <td>Atualizando o tipo de início do serviço externo novamente. Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4</td>
   <td>Atualizou o tipo de início do serviço externo.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>89</td>
   <td>Não é possível atualizar o tipo de início do serviço externo. Nome: %1, tipo de início real: %2, tipo de início esperado: %3</td>
   <td>Não é possível atualizar o tipo de início do serviço externo.</td>
   <td>Contate o Suporte.</td>
</tr>
<tr>
   <td>90</td>
   <td>Falha ao configurar o System Guard Runtime Monitor para se conectar ao serviço de nuvem na região geográfica %1. Código de falha: %2</td>
   <td>O System Guard Runtime Monitor não enviará dados de atestado para o serviço de nuvem.</td>
   <td>Verifique as permissões no caminho do registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Se nenhum problema for detectado, entre em contato com o Suporte.</td>
</tr>
<tr>
   <td>91</td>
   <td>Falha ao remover informações de região geográfica do Monitor de Tempo de Execução do System Guard. Código de falha: %1</td>
   <td>O System Guard Runtime Monitor não enviará dados de atestado para o serviço de nuvem.</td>
   <td>Verifique as permissões no caminho do registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Se nenhum problema for detectado, entre em contato com o Suporte.</td>
</tr>
<tr>
   <td>92</td>
   <td>Interromper o envio da cota de dados cibernéticos do sensor porque a cota de dados é excedida. Retomará o envio depois que o período de cota passar. Máscara de Estado: %1</td>
   <td>Exceder o limite de limitação.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>93</td>
   <td>Retomando o envio de dados cibernéticos do sensor. Máscara de Estado: %1</td>
   <td>Retomar o envio de dados cibernéticos.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>94</td>
   <td>Windows Defender executável da Proteção Avançada contra Ameaças foi iniciado</td>
   <td>O executável SenseCE foi iniciado.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>95</td>
   <td>Windows Defender executável da Proteção Avançada contra Ameaças terminou</td>
   <td>O executável SenseCE foi encerrado.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>96</td>
   <td>Windows Defender proteção avançada contra ameaças init chamou. Código do resultado: %2</td>
   <td>O executável SenseCE chamou a inicialização do MCE.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>97</td>
   <td>Há problemas de conectividade com a Nuvem para o cenário de DLP</td>
   <td>Há problemas de conectividade de rede que afetam o fluxo de classificação de DLP.</td>
   <td>Verifique a conectividade de rede.</td>
</tr>
<tr>
   <td>98</td>
   <td>A conectividade com a Nuvem para o cenário DLP foi restaurada</td>
   <td>A conectividade com a rede foi restaurada e o fluxo de classificação DLP pode continuar.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>99</td>
   <td>Sense encontrou o seguinte erro ao se comunicar com o servidor: (%1). Resultado: (%2)</td>
   <td>Ocorreu um erro de comunicação.</td>
   <td>Verifique os seguintes eventos no log de eventos para obter mais detalhes.</td>
</tr>
<tr>
   <td>100</td>
   <td>Windows Defender executável da Proteção Avançada contra Ameaças falhou ao iniciar. Código de falha: %1</td>
   <td>O executável SenseCE falhou ao iniciar.</td>
   <td>Reinicie o dispositivo. Se esse erro persistir, contate o Suporte.</td>
</tr>
<tr>
   <td>102</td>
   <td>Windows Defender a Detecção Avançada de Rede de Proteção contra Ameaças e o executável de resposta foi iniciado</td>
   <td>O executável SenseNdr foi iniciado.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
<tr>
   <td>103</td>
   <td>Windows Defender detecção avançada de rede de proteção contra ameaças e a resposta executável terminou</td>
   <td>O executável SenseNdr foi encerrado.</td>
   <td>Notificação operacional normal; nenhuma ação necessária.</td>
</tr>
</tbody>
</table>

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10](configure-endpoints.md)
- [Configurar configurações de proxy de dispositivo e conectividade com a Internet](configure-proxy-internet.md)
- [Solucionar problemas do Microsoft Defender para o Ponto de Extremidade](troubleshoot-onboarding.md)
