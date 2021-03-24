---
title: Revisar eventos e erros usando o Visualizador de Eventos
description: Obter descrições e etapas adicionais de solução de problemas (se necessário) para todos os eventos relatados pelo serviço Microsoft Defender for Endpoint.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, cannot start, broken, can't start
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054490"
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
<td>Ocorre durante a iniciação do sistema, o desligar e durante o onbboarding.</td>
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
<td>O serviço não foi a iniciar.</td>
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
<td>O dispositivo não foi a bordo corretamente e não será reportado ao portal.</td>
<td>A integração deve ser executado antes de iniciar o serviço.<br>
Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>7 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao ler os parâmetros de integração. Falha: <code>variable</code> .</td>
<td>Variável = descrição de erro detalhada. O dispositivo não foi a bordo corretamente e não será reportado ao portal.</td>
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
<td><b>Durante a integração:</b> O dispositivo não foi a bordo corretamente e não será reportado ao portal. <br><br><b>Durante o offboard:</b> Falha ao alterar o tipo de início do serviço. O processo de offboarding continua. </td>
<td>Verifique se as configurações e scripts de integração foram implantados corretamente. Tente reimplantar os pacotes de configuração.<br>
Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</td>
</tr>
<tr>
<td>10 </td>
<td>O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter as informações de integração. Código de falha: <code>variable</code> .</td>
<td>O dispositivo não foi a bordo corretamente e não será reportado ao portal.</td>
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
</tbody>
</table>

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10](configure-endpoints.md)
- [Configurar configurações de proxy de dispositivo e conectividade com a Internet](configure-proxy-internet.md)
- [Solucionar problemas do Microsoft Defender para o Ponto de Extremidade](troubleshoot-onboarding.md)
