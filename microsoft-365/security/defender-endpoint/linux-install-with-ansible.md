---
title: Implantar o Microsoft Defender para Ponto de Extremidade no Linux com Ansible
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no Linux usando Ansible.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 12ff9834e2853c1745c20847f869bc2cba4e082e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114265"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="0fd66-104">Implantar o Microsoft Defender para Ponto de Extremidade no Linux com Ansible</span><span class="sxs-lookup"><span data-stu-id="0fd66-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0fd66-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0fd66-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fd66-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0fd66-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fd66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fd66-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0fd66-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0fd66-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0fd66-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0fd66-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0fd66-110">Este artigo descreve como implantar o Defender para Ponto de Extremidade no Linux usando Ansible.</span><span class="sxs-lookup"><span data-stu-id="0fd66-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="0fd66-111">Uma implantação bem-sucedida requer a conclusão de todas as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="0fd66-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="0fd66-112">Baixar o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="0fd66-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="0fd66-113">Criar arquivos YAML ansible</span><span class="sxs-lookup"><span data-stu-id="0fd66-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="0fd66-114">Implantação</span><span class="sxs-lookup"><span data-stu-id="0fd66-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="0fd66-115">References</span><span class="sxs-lookup"><span data-stu-id="0fd66-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="0fd66-116">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="0fd66-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="0fd66-117">Antes de começar, consulte a página [principal do Defender para Ponto](microsoft-defender-endpoint-linux.md) de Extremidade no Linux para obter uma descrição dos pré-requisitos e dos requisitos do sistema para a versão de software atual.</span><span class="sxs-lookup"><span data-stu-id="0fd66-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="0fd66-118">Além disso, para a implantação ansible, você precisa estar familiarizado com tarefas de administração Ansible, ter Ansible configurado e saber como implantar playbooks e tarefas.</span><span class="sxs-lookup"><span data-stu-id="0fd66-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="0fd66-119">Ansible tem muitas maneiras de concluir a mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="0fd66-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="0fd66-120">Essas instruções pressuem disponibilidade de módulos Ansible com suporte, como *apt* e *unarchive* para ajudar a implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="0fd66-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="0fd66-121">Sua organização pode usar um fluxo de trabalho diferente.</span><span class="sxs-lookup"><span data-stu-id="0fd66-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="0fd66-122">Consulte a [documentação Ansible para](https://docs.ansible.com/) obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="0fd66-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="0fd66-123">Ansible precisa ser instalado em pelo menos um computador (Ansible chama esse nó de controle).</span><span class="sxs-lookup"><span data-stu-id="0fd66-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="0fd66-124">O SSH deve ser configurado para uma conta de administrador entre o nó de controle e todos os nós gerenciados (dispositivos que terão o Defender para Ponto de Extremidade instalado neles) e é recomendável ser configurado com autenticação de chave pública.</span><span class="sxs-lookup"><span data-stu-id="0fd66-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="0fd66-125">O software a seguir deve ser instalado em todos os nós gerenciados:</span><span class="sxs-lookup"><span data-stu-id="0fd66-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="0fd66-126">cache</span><span class="sxs-lookup"><span data-stu-id="0fd66-126">curl</span></span>
  - <span data-ttu-id="0fd66-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="0fd66-127">python-apt</span></span>

- <span data-ttu-id="0fd66-128">Todos os nós gerenciados devem estar listados no seguinte formato no `/etc/ansible/hosts` arquivo ou relevante:</span><span class="sxs-lookup"><span data-stu-id="0fd66-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="0fd66-129">Teste de ping:</span><span class="sxs-lookup"><span data-stu-id="0fd66-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="0fd66-130">Baixar o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="0fd66-130">Download the onboarding package</span></span>

<span data-ttu-id="0fd66-131">Baixe o pacote de integração Central de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="0fd66-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="0fd66-132">Em Central de Segurança do Microsoft Defender, vá para Configurações > Gerenciamento de **Dispositivos > Integração**.</span><span class="sxs-lookup"><span data-stu-id="0fd66-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="0fd66-133">No primeiro menu suspenso, selecione **Servidor Linux como** o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0fd66-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="0fd66-134">No segundo menu suspenso, selecione Sua ferramenta de gerenciamento de configuração **do Linux preferencial** como o método de implantação.</span><span class="sxs-lookup"><span data-stu-id="0fd66-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="0fd66-135">Selecione **Baixar pacote de integração**.</span><span class="sxs-lookup"><span data-stu-id="0fd66-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="0fd66-136">Salve o arquivo como WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="0fd66-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Central de Segurança do Microsoft Defender captura de tela](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="0fd66-138">Em um prompt de comando, verifique se você tem o arquivo.</span><span class="sxs-lookup"><span data-stu-id="0fd66-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="0fd66-139">Extraia o conteúdo do arquivo morto:</span><span class="sxs-lookup"><span data-stu-id="0fd66-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="0fd66-140">Criar arquivos YAML ansible</span><span class="sxs-lookup"><span data-stu-id="0fd66-140">Create Ansible YAML files</span></span>

<span data-ttu-id="0fd66-141">Crie uma subtarefa ou arquivos de função que contribuam para um playbook ou tarefa.</span><span class="sxs-lookup"><span data-stu-id="0fd66-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="0fd66-142">Crie a tarefa de integração, `onboarding_setup.yml` :</span><span class="sxs-lookup"><span data-stu-id="0fd66-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="0fd66-143">Adicione o repositório do Defender para Ponto de Extremidade e a chave.</span><span class="sxs-lookup"><span data-stu-id="0fd66-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="0fd66-144">O Defender para Ponto de Extremidade no Linux pode ser implantado de um dos seguintes canais (denotado abaixo como *[canal]*): *insiders-fast,* *insiders-slow* ou *prod*. Cada um desses canais corresponde a um repositório de software Linux.</span><span class="sxs-lookup"><span data-stu-id="0fd66-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="0fd66-145">A escolha do canal determina o tipo e a frequência de atualizações oferecidas ao seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0fd66-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="0fd66-146">Os *dispositivos em insiders-fast* são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por *insiders-slow* e por *último por prod*.</span><span class="sxs-lookup"><span data-stu-id="0fd66-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="0fd66-147">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para usar *insiders-fast* ou *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="0fd66-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="0fd66-148">Alternar o canal após a instalação inicial exige que o produto seja reinstalado.</span><span class="sxs-lookup"><span data-stu-id="0fd66-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="0fd66-149">Para alternar o canal do produto: desinstale o pacote existente, configure novamente seu dispositivo para usar o novo canal e siga as etapas deste documento para instalar o pacote no novo local.</span><span class="sxs-lookup"><span data-stu-id="0fd66-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="0fd66-150">Observe sua distribuição e versão e identifique a entrada mais próxima para ela em `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="0fd66-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="0fd66-151">Nos comandos a seguir, substitua *[distro]* e *[version]* pela informação que você identificou.</span><span class="sxs-lookup"><span data-stu-id="0fd66-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0fd66-152">No caso do Oracle Linux, substitua *[distro]* por "remos".</span><span class="sxs-lookup"><span data-stu-id="0fd66-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="0fd66-153">Crie os arquivos YAML de instalação e desinstalação ansible.</span><span class="sxs-lookup"><span data-stu-id="0fd66-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="0fd66-154">Para distribuições baseadas em apt, use o seguinte arquivo YAML:</span><span class="sxs-lookup"><span data-stu-id="0fd66-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="0fd66-155">Para distribuições baseadas em dnf, use o seguinte arquivo YAML:</span><span class="sxs-lookup"><span data-stu-id="0fd66-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="0fd66-156">Implantação</span><span class="sxs-lookup"><span data-stu-id="0fd66-156">Deployment</span></span>

<span data-ttu-id="0fd66-157">Agora execute os arquivos de tarefas em `/etc/ansible/playbooks/` ou diretório relevante.</span><span class="sxs-lookup"><span data-stu-id="0fd66-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="0fd66-158">Instalação:</span><span class="sxs-lookup"><span data-stu-id="0fd66-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="0fd66-159">Quando o produto é iniciado pela primeira vez, ele baixa as definições antimalware mais recentes.</span><span class="sxs-lookup"><span data-stu-id="0fd66-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="0fd66-160">Dependendo da conexão com a Internet, isso pode levar até alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="0fd66-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="0fd66-161">Validação/configuração:</span><span class="sxs-lookup"><span data-stu-id="0fd66-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="0fd66-162">Desinstalação:</span><span class="sxs-lookup"><span data-stu-id="0fd66-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="0fd66-163">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="0fd66-163">Log installation issues</span></span>

<span data-ttu-id="0fd66-164">Consulte [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span><span class="sxs-lookup"><span data-stu-id="0fd66-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="0fd66-165">Atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="0fd66-165">Operating system upgrades</span></span>

<span data-ttu-id="0fd66-166">Ao atualizar o sistema operacional para uma nova versão principal, primeiro você deve desinstalar o Defender para o Ponto de Extremidade no Linux, instalar a atualização e, finalmente, reconfigurar o Defender para Ponto de Extremidade no Linux em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0fd66-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="0fd66-167">Referências</span><span class="sxs-lookup"><span data-stu-id="0fd66-167">References</span></span>

- [<span data-ttu-id="0fd66-168">Adicionar ou remover repositórios YUM</span><span class="sxs-lookup"><span data-stu-id="0fd66-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="0fd66-169">Gerenciar pacotes com o gerenciador de pacotes dnf</span><span class="sxs-lookup"><span data-stu-id="0fd66-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="0fd66-170">Adicionar e remover repositórios APT</span><span class="sxs-lookup"><span data-stu-id="0fd66-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="0fd66-171">Gerenciar pacotes de apt</span><span class="sxs-lookup"><span data-stu-id="0fd66-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
