---
title: Implantar o Microsoft Defender para endpoint no Linux com Ansible
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para endpoint no Linux usando o Ansible.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, instalação, implantação, desinstalação, fantoche, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572724"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="910b4-104">Implantar o Microsoft Defender para endpoint no Linux com Ansible</span><span class="sxs-lookup"><span data-stu-id="910b4-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="910b4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="910b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="910b4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="910b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="910b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="910b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="910b4-108">Quer experimentar o Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="910b4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="910b4-109">Inscreva-se para um teste gratuito.</span><span class="sxs-lookup"><span data-stu-id="910b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="910b4-110">Este artigo descreve como implantar o Defender para endpoint no Linux usando o Ansible.</span><span class="sxs-lookup"><span data-stu-id="910b4-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="910b4-111">Uma implantação bem-sucedida requer a conclusão de todas as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="910b4-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="910b4-112">Baixe o pacote de onboarding</span><span class="sxs-lookup"><span data-stu-id="910b4-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="910b4-113">Criar arquivos YAML ansible</span><span class="sxs-lookup"><span data-stu-id="910b4-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="910b4-114">Implantação</span><span class="sxs-lookup"><span data-stu-id="910b4-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="910b4-115">References</span><span class="sxs-lookup"><span data-stu-id="910b4-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="910b4-116">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="910b4-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="910b4-117">Antes de começar, consulte [a página principal do Defender for Endpoint no Linux](microsoft-defender-endpoint-linux.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão atual do software.</span><span class="sxs-lookup"><span data-stu-id="910b4-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="910b4-118">Além disso, para implantação da Ansible, você precisa estar familiarizado com tarefas de administração ansible, ter o Ansible configurado e saber como implantar cartilhas e tarefas.</span><span class="sxs-lookup"><span data-stu-id="910b4-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="910b4-119">Ansible tem muitas maneiras de completar a mesma tarefa.</span><span class="sxs-lookup"><span data-stu-id="910b4-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="910b4-120">Estas instruções assumem a disponibilidade de módulos Ansible suportados, como *apto* e *unarchive* para ajudar a implantar o pacote.</span><span class="sxs-lookup"><span data-stu-id="910b4-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="910b4-121">Sua organização pode usar um fluxo de trabalho diferente.</span><span class="sxs-lookup"><span data-stu-id="910b4-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="910b4-122">Consulte a [documentação Ansible](https://docs.ansible.com/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="910b4-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="910b4-123">O Ansible precisa ser instalado em pelo menos um computador (Ansible chama isso de nó de controle).</span><span class="sxs-lookup"><span data-stu-id="910b4-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="910b4-124">O SSH deve ser configurado para uma conta de administrador entre o nó de controle e todos os nós gerenciados (dispositivos que terão o Defender for Endpoint instalado neles), e recomenda-se que seja configurado com autenticação de chave pública.</span><span class="sxs-lookup"><span data-stu-id="910b4-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="910b4-125">O seguinte software deve ser instalado em todos os nós gerenciados:</span><span class="sxs-lookup"><span data-stu-id="910b4-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="910b4-126">cacho</span><span class="sxs-lookup"><span data-stu-id="910b4-126">curl</span></span>
  - <span data-ttu-id="910b4-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="910b4-127">python-apt</span></span>

- <span data-ttu-id="910b4-128">Todos os nós gerenciados devem ser listados no seguinte formato no `/etc/ansible/hosts` arquivo ou relevante:</span><span class="sxs-lookup"><span data-stu-id="910b4-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="910b4-129">Teste de ping:</span><span class="sxs-lookup"><span data-stu-id="910b4-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="910b4-130">Baixe o pacote de onboarding</span><span class="sxs-lookup"><span data-stu-id="910b4-130">Download the onboarding package</span></span>

<span data-ttu-id="910b4-131">Baixe o pacote de onboarding de Central de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="910b4-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="910b4-132">Em Central de Segurança do Microsoft Defender, vá para **Configurações > Gerenciamento de Dispositivos > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="910b4-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="910b4-133">No primeiro menu suspenso, selecione **Linux Server** como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="910b4-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="910b4-134">No segundo menu suspenso, selecione **sua ferramenta de gerenciamento de configuração Linux preferida** como o método de implantação.</span><span class="sxs-lookup"><span data-stu-id="910b4-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="910b4-135">Selecione **Download no pacote de onboarding**.</span><span class="sxs-lookup"><span data-stu-id="910b4-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="910b4-136">Salve o arquivo como WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="910b4-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![captura de tela Central de Segurança do Microsoft Defender](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="910b4-138">A partir de um prompt de comando, verifique se você tem o arquivo.</span><span class="sxs-lookup"><span data-stu-id="910b4-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="910b4-139">Extrair o conteúdo do arquivo:</span><span class="sxs-lookup"><span data-stu-id="910b4-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="910b4-140">Criar arquivos YAML ansible</span><span class="sxs-lookup"><span data-stu-id="910b4-140">Create Ansible YAML files</span></span>

<span data-ttu-id="910b4-141">Crie um subtarefa ou arquivos de papel que contribuam para um livro de jogadas ou tarefa.</span><span class="sxs-lookup"><span data-stu-id="910b4-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="910b4-142">Crie a tarefa de `onboarding_setup.yml` onboarding:</span><span class="sxs-lookup"><span data-stu-id="910b4-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="910b4-143">Adicione o defender para repositório de ponto final e `add_apt_repo.yml` chave:</span><span class="sxs-lookup"><span data-stu-id="910b4-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="910b4-144">O Defender for Endpoint on Linux pode ser implantado a partir de um dos seguintes canais (denotado abaixo como *[canal]*): *insiders-fast,* *insiders-slow* ou *prod*. Cada um desses canais corresponde a um repositório de software Linux.</span><span class="sxs-lookup"><span data-stu-id="910b4-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="910b4-145">A escolha do canal determina o tipo e a frequência das atualizações que são oferecidas ao seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="910b4-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="910b4-146">Dispositivos em *insiders-fast* são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por *insiders-lento e,* finalmente, por *prod*.</span><span class="sxs-lookup"><span data-stu-id="910b4-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="910b4-147">Para visualizar novos recursos e fornecer feedback antecipado, recomenda-se que você configure alguns dispositivos em sua empresa para usar *insiders-fast* ou *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="910b4-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="910b4-148">A comutação do canal após a instalação inicial requer que o produto seja reinstalado.</span><span class="sxs-lookup"><span data-stu-id="910b4-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="910b4-149">Para mudar o canal do produto: desinstalar o pacote existente, reconfigurar o dispositivo para usar o novo canal e seguir as etapas deste documento para instalar o pacote a partir do novo local.</span><span class="sxs-lookup"><span data-stu-id="910b4-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="910b4-150">Observe sua distribuição e versão e identifique a entrada mais próxima para ela em `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="910b4-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="910b4-151">Nos comandos a seguir, *substitua [distro]* e *[versão]* pelas informações identificadas.</span><span class="sxs-lookup"><span data-stu-id="910b4-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="910b4-152">No caso do Oracle Linux, substitua *[distro]* por "rhel".</span><span class="sxs-lookup"><span data-stu-id="910b4-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="910b4-153">Crie os arquivos Ansible install and desinstalem os arquivos YAML.</span><span class="sxs-lookup"><span data-stu-id="910b4-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="910b4-154">Para distribuições baseadas em apt, use o seguinte arquivo YAML:</span><span class="sxs-lookup"><span data-stu-id="910b4-154">For apt-based distributions use the following YAML file:</span></span>

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

    - <span data-ttu-id="910b4-155">Para distribuições baseadas em dnf, use o seguinte arquivo YAML:</span><span class="sxs-lookup"><span data-stu-id="910b4-155">For dnf-based distributions use the following YAML file:</span></span>

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

## <a name="deployment"></a><span data-ttu-id="910b4-156">Implantação</span><span class="sxs-lookup"><span data-stu-id="910b4-156">Deployment</span></span>

<span data-ttu-id="910b4-157">Agora execute os arquivos de tarefas em `/etc/ansible/playbooks/` diretório ou relevante.</span><span class="sxs-lookup"><span data-stu-id="910b4-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="910b4-158">instalação:</span><span class="sxs-lookup"><span data-stu-id="910b4-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="910b4-159">Quando o produto começa pela primeira vez, ele baixa as últimas definições de antimalware.</span><span class="sxs-lookup"><span data-stu-id="910b4-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="910b4-160">Dependendo da sua conexão com a Internet, isso pode levar até alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="910b4-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="910b4-161">Validação/configuração:</span><span class="sxs-lookup"><span data-stu-id="910b4-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="910b4-162">Desinstalação:</span><span class="sxs-lookup"><span data-stu-id="910b4-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="910b4-163">Problemas de instalação de registro</span><span class="sxs-lookup"><span data-stu-id="910b4-163">Log installation issues</span></span>

<span data-ttu-id="910b4-164">Consulte [Problemas de instalação do Log](linux-resources.md#log-installation-issues) para obter mais informações sobre como encontrar o log gerado automaticamente criado pelo instalador quando ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="910b4-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="910b4-165">Atualizações do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="910b4-165">Operating system upgrades</span></span>

<span data-ttu-id="910b4-166">Ao atualizar seu sistema operacional para uma nova versão principal, você deve primeiro desinstalar o Defender para endpoint no Linux, instalar a atualização e, finalmente, reconfigurar o Defender para Endpoint no Linux em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="910b4-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="910b4-167">Referências</span><span class="sxs-lookup"><span data-stu-id="910b4-167">References</span></span>

- [<span data-ttu-id="910b4-168">Adicionar ou remover repositórios YUM</span><span class="sxs-lookup"><span data-stu-id="910b4-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="910b4-169">Gerenciar pacotes com o gerenciador de pacotes dnf</span><span class="sxs-lookup"><span data-stu-id="910b4-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="910b4-170">Adicionar e remover repositórios APT</span><span class="sxs-lookup"><span data-stu-id="910b4-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="910b4-171">Gerenciar pacotes apt</span><span class="sxs-lookup"><span data-stu-id="910b4-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="910b4-172">Confira também</span><span class="sxs-lookup"><span data-stu-id="910b4-172">See also</span></span>
- [<span data-ttu-id="910b4-173">Investigar problemas de integridade do agente</span><span class="sxs-lookup"><span data-stu-id="910b4-173">Investigate agent health issues</span></span>](health-status.md)
