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
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Implantar o Microsoft Defender para endpoint no Linux com Ansible

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Quer experimentar o Defender for Endpoint? [Inscreva-se para um teste gratuito.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Este artigo descreve como implantar o Defender para endpoint no Linux usando o Ansible. Uma implantação bem-sucedida requer a conclusão de todas as seguintes tarefas:

- [Baixe o pacote de onboarding](#download-the-onboarding-package)
- [Criar arquivos YAML ansible](#create-ansible-yaml-files)
- [Implantação](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>Pré-requisitos e requisitos do sistema

Antes de começar, consulte [a página principal do Defender for Endpoint no Linux](microsoft-defender-endpoint-linux.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão atual do software.

Além disso, para implantação da Ansible, você precisa estar familiarizado com tarefas de administração ansible, ter o Ansible configurado e saber como implantar cartilhas e tarefas. Ansible tem muitas maneiras de completar a mesma tarefa. Estas instruções assumem a disponibilidade de módulos Ansible suportados, como *apto* e *unarchive* para ajudar a implantar o pacote. Sua organização pode usar um fluxo de trabalho diferente. Consulte a [documentação Ansible](https://docs.ansible.com/) para obter detalhes.

- O Ansible precisa ser instalado em pelo menos um computador (Ansible chama isso de nó de controle).
- O SSH deve ser configurado para uma conta de administrador entre o nó de controle e todos os nós gerenciados (dispositivos que terão o Defender for Endpoint instalado neles), e recomenda-se que seja configurado com autenticação de chave pública.
- O seguinte software deve ser instalado em todos os nós gerenciados:
  - cacho
  - python-apt

- Todos os nós gerenciados devem ser listados no seguinte formato no `/etc/ansible/hosts` arquivo ou relevante:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Teste de ping:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Baixe o pacote de onboarding

Baixe o pacote de onboarding de Central de Segurança do Microsoft Defender:

1. Em Central de Segurança do Microsoft Defender, vá para **Configurações > Gerenciamento de Dispositivos > Onboarding**.
2. No primeiro menu suspenso, selecione **Linux Server** como o sistema operacional. No segundo menu suspenso, selecione **sua ferramenta de gerenciamento de configuração Linux preferida** como o método de implantação.
3. Selecione **Download no pacote de onboarding**. Salve o arquivo como WindowsDefenderATPOnboardingPackage.zip.

    ![captura de tela Central de Segurança do Microsoft Defender](images/atp-portal-onboarding-linux-2.png)

4. A partir de um prompt de comando, verifique se você tem o arquivo. Extrair o conteúdo do arquivo:

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

## <a name="create-ansible-yaml-files"></a>Criar arquivos YAML ansible

Crie um subtarefa ou arquivos de papel que contribuam para um livro de jogadas ou tarefa.

- Crie a tarefa de `onboarding_setup.yml` onboarding:

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

- Adicione o defender para repositório de ponto final e `add_apt_repo.yml` chave:

    O Defender for Endpoint on Linux pode ser implantado a partir de um dos seguintes canais (denotado abaixo como *[canal]*): *insiders-fast,* *insiders-slow* ou *prod*. Cada um desses canais corresponde a um repositório de software Linux.

    A escolha do canal determina o tipo e a frequência das atualizações que são oferecidas ao seu dispositivo. Dispositivos em *insiders-fast* são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por *insiders-lento e,* finalmente, por *prod*.

    Para visualizar novos recursos e fornecer feedback antecipado, recomenda-se que você configure alguns dispositivos em sua empresa para usar *insiders-fast* ou *insiders-slow*.

    > [!WARNING]
    > A comutação do canal após a instalação inicial requer que o produto seja reinstalado. Para mudar o canal do produto: desinstalar o pacote existente, reconfigurar o dispositivo para usar o novo canal e seguir as etapas deste documento para instalar o pacote a partir do novo local.

    Observe sua distribuição e versão e identifique a entrada mais próxima para ela em `https://packages.microsoft.com/config/` .

    Nos comandos a seguir, *substitua [distro]* e *[versão]* pelas informações identificadas.

    > [!NOTE]
    > No caso do Oracle Linux, substitua *[distro]* por "rhel".

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

- Crie os arquivos Ansible install and desinstalem os arquivos YAML.

    - Para distribuições baseadas em apt, use o seguinte arquivo YAML:

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

    - Para distribuições baseadas em dnf, use o seguinte arquivo YAML:

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

## <a name="deployment"></a>Implantação

Agora execute os arquivos de tarefas em `/etc/ansible/playbooks/` diretório ou relevante.

- instalação:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Quando o produto começa pela primeira vez, ele baixa as últimas definições de antimalware. Dependendo da sua conexão com a Internet, isso pode levar até alguns minutos.

- Validação/configuração:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Desinstalação:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Problemas de instalação de registro

Consulte [Problemas de instalação do Log](linux-resources.md#log-installation-issues) para obter mais informações sobre como encontrar o log gerado automaticamente criado pelo instalador quando ocorre um erro.

## <a name="operating-system-upgrades"></a>Atualizações do sistema operacional

Ao atualizar seu sistema operacional para uma nova versão principal, você deve primeiro desinstalar o Defender para endpoint no Linux, instalar a atualização e, finalmente, reconfigurar o Defender para Endpoint no Linux em seu dispositivo.

## <a name="references"></a>Referências

- [Adicionar ou remover repositórios YUM](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [Gerenciar pacotes com o gerenciador de pacotes dnf](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [Adicionar e remover repositórios APT](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [Gerenciar pacotes apt](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Confira também
- [Investigar problemas de integridade do agente](health-status.md)
