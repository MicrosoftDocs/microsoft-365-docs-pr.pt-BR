---
title: Como agendar verificações com o Microsoft Defender para Ponto de Extremidade (Linux)
description: Saiba como agendar um tempo de verificação automática para o Microsoft Defender for Endpoint (Linux) para proteger melhor os ativos da sua organização.
keywords: microsoft, defender, atp, linux, scans, antivírus, microsoft defender for endpoint (linux)
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d3f5d4c490e28c7985a0420fa5013a8e0f51a167
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053775"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Agendar verificações com o Microsoft Defender para Ponto de Extremidade (Linux)

Para executar uma verificação para Linux, consulte [Comandos com Suporte.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

O Linux (e o Unix) têm uma ferramenta chamada **crontab** (semelhante ao Agendador de Tarefas) para poder executar tarefas agendadas.

## <a name="pre-requisite"></a>Pré-requisito

> [!NOTE]
> Para obter uma lista de todos os fusos horário, execute o seguinte comando: `timedatectl list-timezones`<br>
> Exemplos de zonas de tempo:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para definir o trabalho cron
Use os seguintes comandos:

**Para fazer backup de entradas de crontab**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Onde 200919 == YRMMDD

> [!TIP]
> Faça isso antes de editar ou remover. <br>

Para editar o crontab e adicionar um novo trabalho como um usuário raiz: <br>
`sudo crontab -e`

> [!NOTE]
> O editor padrão é VIM.

Você pode ver:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Pressione "Inserir"

Adicione as seguintes entradas:

CRON_TZ=América/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>Neste exemplo, definimos como 00 minutos, 2 da manhã. (hora no formato de 24 horas), em qualquer dia do mês, em qualquer mês, aos sábados. Ou seja, ele será executado aos sábados às 2:00 da manhã. Pacífico (UTC –8).

Pressione "Esc"

Digite ":wq" sem aspas duplas.

> [!NOTE]
> w == write, q == quit

Para exibir seus trabalhos de cron, digite `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**Para inspecionar as executações de trabalho de cron**

`sudo grep mdatp /var/log/cron`

**Para inspecionar o mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Para aqueles que usam Ansible, Chef ou Puppet

Use os seguintes comandos:
### <a name="to-set-cron-jobs-in-ansible"></a>Para definir trabalhos de cron em Ansible

`cron – Manage cron.d and crontab entries`

Confira [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obter mais informações.

### <a name="to-set-crontabs-in-chef"></a>Para definir crontabs em Chefe
`cron resource`

Confira [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obter mais informações.

### <a name="to-set-cron-jobs-in-puppet"></a>Para definir trabalhos de compadrões em Puppet
Tipo de Recurso: cron

Confira [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obter mais informações.

Automatizando com o Puppet: trabalhos de cron e tarefas agendadas

Confira [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obter mais informações.

## <a name="additional-information"></a>Informações adicionais

**Para obter ajuda com crontab**

`man crontab`

**Para obter uma lista de arquivo crontab do usuário atual**

`crontab -l`

**Para obter uma lista de arquivo crontab de outro usuário**

`crontab -u username -l`

**Para fazer backup de entradas de crontab**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Faça isso antes de editar ou remover. <br>

**Para restaurar entradas de crontab**

`crontab /var/tmp/cron_backup.dat`

**Para editar o crontab e adicionar um novo trabalho como um usuário raiz**

`sudo crontab -e`

**Para editar o crontab e adicionar um novo trabalho**

`crontab -e`

**Para editar entradas de crontab de outro usuário**

`crontab -u username -e`

**Para remover todas as entradas de crontab**

`crontab -r`

**Para remover entradas de crontab de outro usuário**

`crontab -u username -r`

**Explicação**

+—————- minuto (valores: 0 – 59) (caracteres especiais: , – * /)  <br>
| +————- hora (valores: 0 – 23) (caracteres especiais: , – * /) <br>
| | +———- dia do mês (valores: 1 – 31) (caracteres especiais: , – * / L W C)  <br>
| | | +——- mês (valores: 1 a 12) (caracteres especiais: ,- * / )  <br>
| | | | +—- dia da semana (valores: 0 – 6) (domingo=0 ou 7) (caracteres especiais: , – * / L W C) <br>
| | | | |*****comando a ser executado


