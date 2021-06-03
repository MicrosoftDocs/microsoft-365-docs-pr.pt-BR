---
title: Como agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux)
description: Saiba como agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux) para proteger melhor os ativos da sua organização.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, scans, antivírus, microsoft defender for endpoint (linux)
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
ms.openlocfilehash: 9b7699b1a24e7e1d74a48389d02518e814911ecc
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730865"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux)

Para executar uma atualização no Microsoft Defender para Ponto de Extremidade no Linux, consulte [Deploy updates for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-updates).

O Linux (e o Unix) têm uma ferramenta chamada **crontab** (semelhante ao Agendador de Tarefas) para poder executar tarefas agendadas.

## <a name="pre-requisite"></a>Pré-requisito

> [!NOTE]
> Para obter uma lista de todos os fusos horário, execute o seguinte comando: `timedatectl list-timezones`<br>
> Exemplos de zonas de tempo: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Para definir o trabalho cron
Use os seguintes comandos:

**Para fazer backup de entradas de crontab**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Onde 201118 == YYMMDD

> [!TIP]
> Faça isso antes de editar ou remover. <br>

Para editar o crontab e adicionar um novo trabalho como um usuário raiz: <br>
`sudo crontab -e`

> [!NOTE]
> O editor padrão é VIM.

Você pode ver:

0****/etc/opt/microsoft/mdatp/logrorate.sh

And

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Consulte [Agendar verificações com o Microsoft Defender para Ponto de Extremidade (Linux)](linux-schedule-scan-atp.md)

Pressione "Inserir"

Adicione as seguintes entradas:

CRON_TZ=América/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL e variantes (CentOS e Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES e variantes

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Sistemas Ubuntu e Debian

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> Nos exemplos acima, estamos definindo-o como 00 minutos, 6 da manhã (hora no formato de 24 horas), em qualquer dia do mês, em qualquer mês, aos domingos. [$(date + d) -le 15] == Não será executado, a menos que seja igual ou inferior ao \% 15º dia (3ª semana). Ou seja, será executado a cada 3º domingo(7) do mês às 6:00 da manhã. Pacífico (UTC -8).

Pressione "Esc"

Digite ":wq" w/o das aspas duplas.

> [!NOTE]
> w == write, q == quit

Para exibir seus trabalhos de cron, digite `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="atualizar o MDE linux":::

Para inspecionar as executações de trabalho de cron: `sudo grep mdatp /var/log/cron`

Para inspecionar o mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

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

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

