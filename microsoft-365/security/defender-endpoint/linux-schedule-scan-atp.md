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
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="a6162-104">Agendar verificações com o Microsoft Defender para Ponto de Extremidade (Linux)</span><span class="sxs-lookup"><span data-stu-id="a6162-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="a6162-105">Para executar uma verificação para Linux, consulte [Comandos com Suporte.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="a6162-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="a6162-106">O Linux (e o Unix) têm uma ferramenta chamada **crontab** (semelhante ao Agendador de Tarefas) para poder executar tarefas agendadas.</span><span class="sxs-lookup"><span data-stu-id="a6162-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="a6162-107">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="a6162-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="a6162-108">Para obter uma lista de todos os fusos horário, execute o seguinte comando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="a6162-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="a6162-109">Exemplos de zonas de tempo:</span><span class="sxs-lookup"><span data-stu-id="a6162-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="a6162-110">Para definir o trabalho cron</span><span class="sxs-lookup"><span data-stu-id="a6162-110">To set the Cron job</span></span>
<span data-ttu-id="a6162-111">Use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a6162-111">Use the following commands:</span></span>

<span data-ttu-id="a6162-112">**Para fazer backup de entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="a6162-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="a6162-113">Onde 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="a6162-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="a6162-114">Faça isso antes de editar ou remover.</span><span class="sxs-lookup"><span data-stu-id="a6162-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="a6162-115">Para editar o crontab e adicionar um novo trabalho como um usuário raiz:</span><span class="sxs-lookup"><span data-stu-id="a6162-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="a6162-116">O editor padrão é VIM.</span><span class="sxs-lookup"><span data-stu-id="a6162-116">The default editor is VIM.</span></span>

<span data-ttu-id="a6162-117">Você pode ver:</span><span class="sxs-lookup"><span data-stu-id="a6162-117">You might see:</span></span>

<span data-ttu-id="a6162-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="a6162-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="a6162-119">Pressione "Inserir"</span><span class="sxs-lookup"><span data-stu-id="a6162-119">Press “Insert”</span></span>

<span data-ttu-id="a6162-120">Adicione as seguintes entradas:</span><span class="sxs-lookup"><span data-stu-id="a6162-120">Add the following entries:</span></span>

<span data-ttu-id="a6162-121">CRON_TZ=América/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="a6162-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="a6162-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="a6162-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="a6162-123">Neste exemplo, definimos como 00 minutos, 2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="a6162-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="a6162-124">(hora no formato de 24 horas), em qualquer dia do mês, em qualquer mês, aos sábados.</span><span class="sxs-lookup"><span data-stu-id="a6162-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="a6162-125">Ou seja, ele será executado aos sábados às 2:00 da manhã.</span><span class="sxs-lookup"><span data-stu-id="a6162-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="a6162-126">Pacífico (UTC –8).</span><span class="sxs-lookup"><span data-stu-id="a6162-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="a6162-127">Pressione "Esc"</span><span class="sxs-lookup"><span data-stu-id="a6162-127">Press “Esc”</span></span>

<span data-ttu-id="a6162-128">Digite ":wq" sem aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="a6162-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="a6162-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="a6162-129">w == write, q == quit</span></span>

<span data-ttu-id="a6162-130">Para exibir seus trabalhos de cron, digite `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="a6162-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="a6162-132">**Para inspecionar as executações de trabalho de cron**</span><span class="sxs-lookup"><span data-stu-id="a6162-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="a6162-133">**Para inspecionar o mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="a6162-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="a6162-134">Para aqueles que usam Ansible, Chef ou Puppet</span><span class="sxs-lookup"><span data-stu-id="a6162-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="a6162-135">Use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a6162-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="a6162-136">Para definir trabalhos de cron em Ansible</span><span class="sxs-lookup"><span data-stu-id="a6162-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="a6162-137">Confira [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a6162-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="a6162-138">Para definir crontabs em Chefe</span><span class="sxs-lookup"><span data-stu-id="a6162-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="a6162-139">Confira [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a6162-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="a6162-140">Para definir trabalhos de compadrões em Puppet</span><span class="sxs-lookup"><span data-stu-id="a6162-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="a6162-141">Tipo de Recurso: cron</span><span class="sxs-lookup"><span data-stu-id="a6162-141">Resource Type: cron</span></span>

<span data-ttu-id="a6162-142">Confira [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a6162-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="a6162-143">Automatizando com o Puppet: trabalhos de cron e tarefas agendadas</span><span class="sxs-lookup"><span data-stu-id="a6162-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="a6162-144">Confira [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a6162-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="a6162-145">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="a6162-145">Additional information</span></span>

<span data-ttu-id="a6162-146">**Para obter ajuda com crontab**</span><span class="sxs-lookup"><span data-stu-id="a6162-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="a6162-147">**Para obter uma lista de arquivo crontab do usuário atual**</span><span class="sxs-lookup"><span data-stu-id="a6162-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="a6162-148">**Para obter uma lista de arquivo crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="a6162-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="a6162-149">**Para fazer backup de entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="a6162-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="a6162-150">Faça isso antes de editar ou remover.</span><span class="sxs-lookup"><span data-stu-id="a6162-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="a6162-151">**Para restaurar entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="a6162-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="a6162-152">**Para editar o crontab e adicionar um novo trabalho como um usuário raiz**</span><span class="sxs-lookup"><span data-stu-id="a6162-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="a6162-153">**Para editar o crontab e adicionar um novo trabalho**</span><span class="sxs-lookup"><span data-stu-id="a6162-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="a6162-154">**Para editar entradas de crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="a6162-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="a6162-155">**Para remover todas as entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="a6162-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="a6162-156">**Para remover entradas de crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="a6162-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="a6162-157">**Explicação**</span><span class="sxs-lookup"><span data-stu-id="a6162-157">**Explanation**</span></span>

<span data-ttu-id="a6162-158">+—————- minuto (valores: 0 – 59) (caracteres especiais: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="a6162-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="a6162-159">| +————- hora (valores: 0 – 23) (caracteres especiais: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="a6162-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="a6162-160">| | +———- dia do mês (valores: 1 – 31) (caracteres especiais: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="a6162-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="a6162-161">| | | +——- mês (valores: 1 a 12) (caracteres especiais: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="a6162-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="a6162-162">| | | | +—- dia da semana (valores: 0 – 6) (domingo=0 ou 7) (caracteres especiais: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="a6162-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="a6162-163">| | | | |\*\*\*\*\*comando a ser executado</span><span class="sxs-lookup"><span data-stu-id="a6162-163">| | | | |\*\*\*\*\*command to be executed</span></span>


