---
title: Privacidade do Microsoft Defender ATP para Mac
description: Controles de privacidade, como configurar configurações de política que impactam a privacidade e informações sobre os dados de diagnóstico coletados no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, privacidade, diagnóstico
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1386809778edeb92521a8656e9ece78591a682a4
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382896"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a>Privacidade do Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


A Microsoft está comprometida em fornecer as informações e controles necessários para fazer escolhas sobre como seus dados são coletados e usados quando você está usando o Microsoft Defender para o Ponto de Extremidade para Mac.

Este tópico descreve os controles de privacidade disponíveis no produto, como gerenciar esses controles com configurações de política e mais detalhes sobre os eventos de dados coletados.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a>Visão geral dos controles de privacidade no Microsoft Defender para Ponto de Extremidade para Mac

Esta seção descreve os controles de privacidade para os diferentes tipos de dados coletados pelo Microsoft Defender para Ponto de Extremidade para Mac.

### <a name="diagnostic-data"></a>Dados de diagnóstico

Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.

Alguns dados de diagnóstico são necessários, enquanto alguns dados de diagnóstico são opcionais. Oferecemos a você a possibilidade de escolher se nos enviará dados de diagnóstico obrigatórios ou opcionais por meio do uso de controles de privacidade, como configurações de políticas para organizações.

Há dois níveis de dados de diagnóstico para software cliente do Microsoft Defender for Endpoint que você pode escolher:

* **Obrigatório**: Os dados mínimos necessários para ajudar a manter o Microsoft Defender para Ponto de Extremidade seguro, atualizado e com desempenho conforme esperado no dispositivo em que ele está instalado.

* **Opcional**: Dados adicionais que ajudam a Microsoft a fazer melhorias no produto e fornece informações aprimoradas para ajudar a detectar, diagnosticar e resolver problemas.

Por padrão, somente os dados de diagnóstico necessários são enviados para a Microsoft.

### <a name="cloud-delivered-protection-data"></a>Dados de proteção entregues na nuvem

A proteção entregue na nuvem é usada para fornecer proteção cada vez mais rápida com acesso aos dados de proteção mais recentes na nuvem.

A habilitação do serviço de proteção entregue na nuvem é opcional, no entanto, é altamente recomendável porque fornece proteção importante contra malware em seus pontos de extremidade e em toda a sua rede.

### <a name="sample-data"></a>Dados de exemplo

Os dados de exemplo são usados para melhorar os recursos de proteção do produto, enviando amostras suspeitas da Microsoft para que possam ser analisadas. Habilenciar o envio automático de exemplo é opcional.

Quando esse recurso está habilitado e o exemplo coletado provavelmente conterá informações pessoais, o usuário será solicitado a consentir.

## <a name="manage-privacy-controls-with-policy-settings"></a>Gerenciar os controles de privacidade com as configurações de política

Se você for um administrador de TI, talvez queira configurar esses controles no nível da empresa. 

Os controles de privacidade para os vários tipos de dados descritos na seção anterior são descritos em detalhes em [Definir preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade para Mac .

Assim como em qualquer nova configuração de política, você deve testá-las cuidadosamente em um ambiente limitado e controlado para garantir que as configurações configuradas tenham o efeito desejado antes de implementar as configurações de política mais amplamente em sua organização.

## <a name="diagnostic-data-events"></a>Eventos de dados de diagnóstico

Esta seção descreve o que é considerado dados de diagnóstico necessários e o que é considerado dados de diagnóstico opcionais, juntamente com uma descrição dos eventos e campos coletados.

### <a name="data-fields-that-are-common-for-all-events"></a>Campos de dados comuns para todos os eventos
Há algumas informações sobre eventos que são comuns a todos os eventos independentemente da categoria ou subtipo de dados. 

Os campos a seguir são considerados comuns para todos os eventos:

| Campo                   | Descrição |
| ----------------------- | ----------- |
| plataforma                | A classificação ampla da plataforma na qual o aplicativo está sendo executado. Permite que a Microsoft identifique em quais plataformas um problema pode estar ocorrendo para que ele possa ser priorizado corretamente. |
| machine_guid            | Identificador exclusivo associado ao dispositivo. Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de instalação e quantos usuários são afetados. |
| sense_guid              | Identificador exclusivo associado ao dispositivo. Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de instalação e quantos usuários são afetados. |
| org_id                  | Identificador exclusivo associado à empresa à que o dispositivo pertence. Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de empresas e quantas empresas são impactadas. |
| hostname                | Nome do dispositivo local (sem sufixo DNS). Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de instalação e quantos usuários são afetados. |
| product_guid            | Identificador exclusivo do produto. Permite que a Microsoft diferencie problemas que impactam diferentes tipos de produto. |
| app_version             | Versão do aplicativo Microsoft Defender para Ponto de Extremidade para Mac. Permite que a Microsoft identifique quais versões do produto estão mostrando um problema para que ele possa ser priorizado corretamente.|
| sig_version             | Versão do banco de dados de inteligência de segurança. Permite que a Microsoft identifique quais versões da inteligência de segurança estão mostrando um problema para que ela possa ser priorizada corretamente. |
| supported_compressions  | Lista de algoritmos de compactação suportados pelo aplicativo, por exemplo `['gzip']` . Permite que a Microsoft entenda quais tipos de compactações podem ser usadas quando se comunicam com o aplicativo. |
| release_ring            | Toque ao lado do dispositivo (por exemplo, Insider Fast, Insider Slow, Production). Permite que a Microsoft identifique em qual anel de lançamento um problema pode estar ocorrendo para que ele possa ser priorizado corretamente. |


### <a name="required-diagnostic-data"></a>Dados de diagnóstico obrigatórios

**Os dados de diagnóstico** necessários são os dados mínimos necessários para ajudar a manter o Microsoft Defender for Endpoint seguro, atualizado e a executar conforme esperado no dispositivo em que está instalado.

Os dados de diagnóstico necessários ajudam a identificar problemas com o Microsoft Defender para Ponto de Extremidade que podem estar relacionados a uma configuração de dispositivo ou software. Por exemplo, ele pode ajudar a determinar se um recurso do Microsoft Defender for Endpoint falha com mais frequência em uma determinada versão do sistema operacional, com recursos recém-introduzidos ou quando determinados recursos do Microsoft Defender para Ponto de Extremidade estão desabilitados. Os dados de diagnóstico necessários ajudam a Microsoft a detectar, diagnosticar e corrigir esses problemas mais rapidamente para que o impacto para usuários ou organizações seja reduzido.

#### <a name="software-setup-and-inventory-data-events"></a>Configuração do software e eventos de dados de inventário

**Instalação/desinstalação do Microsoft Defender para Ponto de Extremidade**

Os seguintes campos são coletados:

| Campo            | Descrição |
| ---------------- | ----------- |
| correlation_id   | Identificador exclusivo associado à instalação. |
| versão          | Versão do pacote. |
| severity         | Gravidade da mensagem (por exemplo, Informações). |
| código             | Código que descreve a operação. |
| texto             | Informações adicionais associadas à instalação do produto. |

**Configuração do Microsoft Defender para Ponto de Extremidade**

Os seguintes campos são coletados:

| Campo                                               | Descrição |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Se a proteção em tempo real está habilitada no dispositivo ou não. |
| antivirus_engine.passive_mode                       | Se o modo passivo está habilitado no dispositivo ou não. |
| cloud_service.enabled                               | Se a proteção entregue na nuvem está habilitada no dispositivo ou não. |
| cloud_service.timeout                               | Tempo de tempo quando o aplicativo se comunica com a nuvem do Microsoft Defender para Ponto de Extremidade. |
| cloud_service.heartbeat_interval                    | Intervalo entre pulsações consecutivas enviadas pelo produto para a nuvem. |
| cloud_service.service_uri                           | URI usado para se comunicar com a nuvem. |
| cloud_service.diagnostic_level                      | Nível de diagnóstico do dispositivo (obrigatório, opcional). |
| cloud_service.automatic_sample_submission           | Se o envio automático de amostra está ou não ligado. |
| edr.early_preview                                   | Se o dispositivo deve executar os recursos de visualização antecipada do EDR. |
| edr.group_id                                        | Identificador de grupo usado pelo componente de detecção e resposta. |
| edr.tags                                            | Marcas definidas pelo usuário. |
| features. \[ nome do recurso opcional\]                  | Lista de recursos de visualização, juntamente com se eles estão habilitados ou não. |

#### <a name="product-and-service-usage-data-events"></a>Produtos e eventos de dados e uso do serviço

**Relatório de atualização de inteligência de segurança**

Os seguintes campos são coletados:

| Campo            | Descrição |
| ---------------- | ----------- |
| from_version     | Versão original de inteligência de segurança. |
| to_version       | Nova versão de inteligência de segurança. |
| status           | Status da atualização indicando sucesso ou falha. |
| using_proxy      | Se a atualização foi feita por meio de um proxy. |
| erro            | Código de erro se a atualização falhar. |
| motivo           | Mensagem de erro se a atualização foi arquivada. |

#### <a name="product-and-service-performance-data-events"></a>Eventos de dados de desempenho de produtos e serviços

**Saída inesperada do aplicativo (falha)**

Coleta informações do sistema e o estado de um aplicativo quando um aplicativo sai inesperadamente.

Os seguintes campos são coletados:

| Campo                          | Descrição |
| ------------------------------ | ----------- |
| v1_crash_count                 | Número de vezes que o processo do mecanismo V1 falha a cada hora na máquina cliente  |
| v2_crash_count                 | Número de vezes que o processo do mecanismo V2 falha a cada hora na máquina cliente  |
| EDR_crash_count                | Número de vezes que o processo EDR cai a cada hora no computador cliente        |

**Estatísticas de extensão do kernel**

Os seguintes campos são coletados:

| Campo            | Descrição |
| ---------------- | ----------- |
| versão          | Versão do Microsoft Defender para Ponto de Extremidade para Mac. |
| instance_id      | Identificador exclusivo gerado na inicialização de extensão do kernel. |
| trace_level      | Nível de rastreamento da extensão do kernel. |
| subsistema        | O subsistema subjacente usado para proteção em tempo real. |
| ipc.connects     | Número de solicitações de conexão recebidas pela extensão do kernel. |
| ipc.rejects      | Número de solicitações de conexão rejeitadas pela extensão do kernel. |
| ipc.connected    | Se há alguma conexão ativa com a extensão do kernel. |

#### <a name="support-data"></a>Dados de suporte

**Logs de diagnóstico**

Os logs de diagnóstico são coletados somente com o consentimento do usuário como parte do recurso de envio de comentários. Os seguintes arquivos são coletados como parte dos logs de suporte:

- Todos os arquivos *em /Library/Logs/Microsoft/mdatp/*
- Subconjunto de arquivos *em /Library/Application Support/Microsoft/Defender/* que são criados e usados pelo Microsoft Defender para Ponto de Extremidade para Mac
- Subconjunto de arquivos *em /Library/Preferências Gerenciadas* que são usados pelo Microsoft Defender para Ponto de Extremidade para Mac
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>Dados de diagnóstico opcionais

**Dados de diagnóstico opcionais** são dados adicionais que ajudam a Microsoft a fazer melhorias no produto e fornece informações aprimoradas para ajudar a detectar, diagnosticar e corrigir problemas.

Se você optar por nos enviar dados de diagnóstico opcionais, os dados de diagnóstico necessários também serão incluídos.

Exemplos de dados de diagnóstico opcionais incluem dados que a Microsoft coleta sobre a configuração do produto (por exemplo, número de exclusões definidas no dispositivo) e o desempenho do produto (medidas agregadas sobre o desempenho dos componentes do produto).

#### <a name="software-setup-and-inventory-data-events"></a>Configuração do software e eventos de dados de inventário

**Configuração do Microsoft Defender para Ponto de Extremidade**

Os seguintes campos são coletados:

| Campo                                              | Descrição |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Tempo de conexão de repetir quando a comunicação com a nuvem. |
| file_hash_cache_maximum                            | Tamanho do cache do produto. |
| crash_upload_daily_limit                           | Limite de logs de falha carregados diariamente. |
| antivirus_engine.exclusions[].is_directory         | Se a exclusão da verificação é um diretório ou não. |
| antivirus_engine.exclusions[].path                 | Caminho que foi excluído da verificação. |
| antivirus_engine.exclusions[].extension            | Extensão excluída da verificação. |
| antivirus_engine.exclusions[].name                 | Nome do arquivo excluído da verificação. |
| antivirus_engine.scan_cache_maximum                | Tamanho do cache do produto. |
| antivirus_engine.maximum_scan_threads              | Número máximo de threads usados para verificação. |
| antivirus_engine.threat_restoration_exclusion_time | Tempo para que um arquivo restaurado da quarentena possa ser detectado novamente. |
| filesystem_scanner.full_scan_directory             | Diretório de verificação completo. |
| filesystem_scanner.quick_scan_directories          | Lista de diretórios usados na verificação rápida. |
| edr.latency_mode                                   | Modo de latência usado pelo componente de detecção e resposta. |
| edr.proxy_address                                  | Endereço proxy usado pelo componente de detecção e resposta. |

**Configuração do Microsoft Auto-Update**

Os seguintes campos são coletados:

| Campo                       | Descrição |
| --------------------------- | ----------- |
| how_to_check                | Determina como as atualizações do produto são verificadas (por exemplo, automáticas ou manuais). |
| channel_name                | Atualize o canal associado ao dispositivo. |
| manifest_server             | Servidor usado para baixar atualizações. |
| update_cache                | Local do cache usado para armazenar atualizações. |

### <a name="product-and-service-usage"></a>Uso de produtos e serviços

#### <a name="diagnostic-log-upload-started-report"></a>Relatório iniciado do upload do log de diagnóstico

Os seguintes campos são coletados:

| Campo            | Descrição |
| ---------------- | ----------- |
| sha256           | Identificador SHA256 do log de suporte. |
| size             | Tamanho do log de suporte. |
| original_path    | Caminho para o log de suporte (sempre em */Library/Application Support/Microsoft/Defender/wdavdiag/*). |
| formato           | Formato do log de suporte. |

#### <a name="diagnostic-log-upload-completed-report"></a>Relatório concluído de carregamento de log de diagnóstico

Os seguintes campos são coletados:

| Campo            | Descrição |
| ---------------- | ----------- |
| request_id       | ID de correlação para a solicitação de carregamento de log de suporte. |
| sha256           | Identificador SHA256 do log de suporte. |
| blob_sas_uri     | URI usado pelo aplicativo para carregar o log de suporte. |

#### <a name="product-and-service-performance-data-events"></a>Eventos de dados de desempenho de produtos e serviços

**Saída inesperada do aplicativo (falha)**

Saídas inesperadas do aplicativo e o estado do aplicativo quando isso acontece.

**Estatísticas de extensão do kernel**

Os seguintes campos são coletados:

| Campo                          | Descrição |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | As propriedades a seguir são valores numéricos agregados, representando a contagem de eventos que aconteceram desde a inicialização da extensão do kernel. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Recursos

- [Privacidade na Microsoft](https://privacy.microsoft.com/)
