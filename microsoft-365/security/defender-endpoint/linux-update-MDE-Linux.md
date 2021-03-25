---
title: Como agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux)
description: Saiba como agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux) para proteger melhor os ativos da sua organização.
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
ms.openlocfilehash: b4c2e4d80628dab40de9e99abb27237176b9f171
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052950"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="5429f-104">Agendar uma atualização do Microsoft Defender para Ponto de Extremidade (Linux)</span><span class="sxs-lookup"><span data-stu-id="5429f-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="5429f-105">Para executar uma atualização no Microsoft Defender para Ponto de Extremidade para Linux, consulte [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span><span class="sxs-lookup"><span data-stu-id="5429f-105">To run an update on Microsoft Defender for Endpoint for Linux, see [Deploy updates for Microsoft Defender for Endpoint for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="5429f-106">O Linux (e o Unix) têm uma ferramenta chamada **crontab** (semelhante ao Agendador de Tarefas) para poder executar tarefas agendadas.</span><span class="sxs-lookup"><span data-stu-id="5429f-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="5429f-107">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="5429f-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="5429f-108">Para obter uma lista de todos os fusos horário, execute o seguinte comando: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="5429f-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="5429f-109">Exemplos de zonas de tempo:</span><span class="sxs-lookup"><span data-stu-id="5429f-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="5429f-110">Para definir o trabalho cron</span><span class="sxs-lookup"><span data-stu-id="5429f-110">To set the Cron job</span></span>
<span data-ttu-id="5429f-111">Use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="5429f-111">Use the following commands:</span></span>

<span data-ttu-id="5429f-112">**Para fazer backup de entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="5429f-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="5429f-113">Onde 201118 == YYMMDD</span><span class="sxs-lookup"><span data-stu-id="5429f-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="5429f-114">Faça isso antes de editar ou remover.</span><span class="sxs-lookup"><span data-stu-id="5429f-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="5429f-115">Para editar o crontab e adicionar um novo trabalho como um usuário raiz:</span><span class="sxs-lookup"><span data-stu-id="5429f-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="5429f-116">O editor padrão é VIM.</span><span class="sxs-lookup"><span data-stu-id="5429f-116">The default editor is VIM.</span></span>

<span data-ttu-id="5429f-117">Você pode ver:</span><span class="sxs-lookup"><span data-stu-id="5429f-117">You might see:</span></span>

<span data-ttu-id="5429f-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="5429f-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="5429f-119">And</span><span class="sxs-lookup"><span data-stu-id="5429f-119">And</span></span>

<span data-ttu-id="5429f-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="5429f-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="5429f-121">Consulte [Agendar verificações com o Microsoft Defender para Ponto de Extremidade (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="5429f-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="5429f-122">Pressione "Inserir"</span><span class="sxs-lookup"><span data-stu-id="5429f-122">Press “Insert”</span></span>

<span data-ttu-id="5429f-123">Adicione as seguintes entradas:</span><span class="sxs-lookup"><span data-stu-id="5429f-123">Add the following entries:</span></span>

<span data-ttu-id="5429f-124">CRON_TZ=América/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="5429f-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="5429f-125">! RHEL e variantes (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="5429f-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="5429f-126">! SLES e variantes</span><span class="sxs-lookup"><span data-stu-id="5429f-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="5429f-127">! Sistemas Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="5429f-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="5429f-128">Nos exemplos acima, estamos definindo-o como 00 minutos, 6 da manhã (hora no formato de 24 horas), em qualquer dia do mês, em qualquer mês, aos domingos. [$(date + d) -le 15] == Não será executado, a menos que seja igual ou inferior ao \% 15º dia (3ª semana).</span><span class="sxs-lookup"><span data-stu-id="5429f-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="5429f-129">Ou seja, será executado a cada 3º domingo(7) do mês às 6:00 da manhã.</span><span class="sxs-lookup"><span data-stu-id="5429f-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="5429f-130">Pacífico (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="5429f-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="5429f-131">Pressione "Esc"</span><span class="sxs-lookup"><span data-stu-id="5429f-131">Press “Esc”</span></span>

<span data-ttu-id="5429f-132">Digite ":wq" w/o das aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="5429f-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="5429f-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="5429f-133">w == write, q == quit</span></span>

<span data-ttu-id="5429f-134">Para exibir seus trabalhos de cron, digite `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="5429f-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="atualizar o MDE linux":::

<span data-ttu-id="5429f-136">Para inspecionar as executações de trabalho de cron: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="5429f-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="5429f-137">Para inspecionar o mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="5429f-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="5429f-138">Para aqueles que usam Ansible, Chef ou Puppet</span><span class="sxs-lookup"><span data-stu-id="5429f-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="5429f-139">Use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="5429f-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="5429f-140">Para definir trabalhos de cron em Ansible</span><span class="sxs-lookup"><span data-stu-id="5429f-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="5429f-141">Confira [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5429f-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="5429f-142">Para definir crontabs em Chefe</span><span class="sxs-lookup"><span data-stu-id="5429f-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="5429f-143">Confira [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5429f-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="5429f-144">Para definir trabalhos de compadrões em Puppet</span><span class="sxs-lookup"><span data-stu-id="5429f-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="5429f-145">Tipo de Recurso: cron</span><span class="sxs-lookup"><span data-stu-id="5429f-145">Resource Type: cron</span></span>

<span data-ttu-id="5429f-146">Confira [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5429f-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="5429f-147">Automatizando com o Puppet: trabalhos de cron e tarefas agendadas</span><span class="sxs-lookup"><span data-stu-id="5429f-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="5429f-148">Confira [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5429f-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="5429f-149">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="5429f-149">Additional information</span></span>

<span data-ttu-id="5429f-150">**Para obter ajuda com crontab**</span><span class="sxs-lookup"><span data-stu-id="5429f-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="5429f-151">**Para obter uma lista de arquivo crontab do usuário atual**</span><span class="sxs-lookup"><span data-stu-id="5429f-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="5429f-152">**Para obter uma lista de arquivo crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="5429f-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="5429f-153">**Para fazer backup de entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="5429f-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="5429f-154">Faça isso antes de editar ou remover.</span><span class="sxs-lookup"><span data-stu-id="5429f-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="5429f-155">**Para restaurar entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="5429f-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="5429f-156">**Para editar o crontab e adicionar um novo trabalho como um usuário raiz**</span><span class="sxs-lookup"><span data-stu-id="5429f-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="5429f-157">**Para editar o crontab e adicionar um novo trabalho**</span><span class="sxs-lookup"><span data-stu-id="5429f-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="5429f-158">**Para editar entradas de crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="5429f-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="5429f-159">**Para remover todas as entradas de crontab**</span><span class="sxs-lookup"><span data-stu-id="5429f-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="5429f-160">**Para remover entradas de crontab de outro usuário**</span><span class="sxs-lookup"><span data-stu-id="5429f-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="5429f-161">**Explicação**</span><span class="sxs-lookup"><span data-stu-id="5429f-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>
