---
title: Como implantar o Defender para o ponto de extremidade no Linux com o Chefe
description: Saiba como implantar o Defender para Ponto de Extremidade no Linux com o Chefe
keywords: microsoft, defender, atp, linux, scans, antivírus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903923"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Implantar o Defender para Ponto de Extremidade no Linux com Chef

Antes de começar:

- Instale o unzip se ainda não estiver instalado. Os componentes do Chefe já estão instalados e existe um repositório do Chefe (chefe gerar repositório ) para armazenar o livro de receitas que será usado para implantar no Defender for Endpoint em servidores Linux gerenciados <reponame> do Chefe.

Você pode criar um novo livro de receita em seu repositório existente executando o seguinte comando de dentro da pasta de pastas de receitas que está no repositório do seu chefe:</br>
`chef generate cookbook mdatp`

Este comando criará uma nova estrutura de pastas para o novo livro de receitas chamado mdatp.  Você também pode usar um livro de receita existente se já tiver um que você gostaria de usar para adicionar a implantação do MDE.
Depois que o livro de receitas for criado, crie uma pasta de arquivos dentro da pasta do livro de receitas que acabou de ser criada:

`mkdir mdatp/files`

Transfira o arquivo zip de Integração do Servidor Linux que pode ser baixado do portal Central de Segurança do Microsoft Defender para essa nova pasta de arquivos.

Na Estação de Trabalho do Chefe, navegue até a pasta mdatp/recipes. Essa pasta é criada quando o livro de receitas foi gerado. Use seu editor de texto preferencial (como vi ou nano) para adicionar as seguintes instruções ao final do arquivo default.rb:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

Em seguida, salve e feche o arquivo default.rb.
Em seguida, crie um novo arquivo de receita chamado install_mdatp.rb na pasta receitas e adicione este texto ao arquivo:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

Você precisará modificar o número de versão, a distribuição e o nome de repo para corresponder à versão que você está implantando e ao canal que você gostaria de implantar.
Em seguida, você deve criar um arquivo onboard_mdatp.rb na pasta mdatp/recipies.  Adicione o seguinte texto a esse arquivo:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Certifique-se de atualizar o nome do caminho para o local do arquivo de integração.
Para testar implantá-lo na estação de trabalho do Chefe, basta executar ``sudo chef-client -z -o mdatp`` .
Após a implantação, você deve considerar a criação e a implantação de um arquivo de configuração nos servidores com base em Definir  [preferências](/linux-preferences.md)do Microsoft Defender para Ponto de Extremidade no Linux .  
Depois de criar e testar seu arquivo de configuração, você pode posicioná-lo na pasta cookbook/mdatp/files onde também colocou o pacote de integração.  Em seguida, você pode criar um arquivo settings_mdatp.rb na pasta mdatp/recipies e adicionar este texto:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Para incluir essa etapa como parte da receita, basta adicionar include_recipe ':: settings_mdatp' ao seu arquivo default.rb na pasta de receita.
Você também pode usar o crontab para agendar atualizações automáticas Agendar uma atualização do Microsoft Defender para Ponto de [Extremidade (Linux)](linux-update-MDE-Linux.md).

Desinstale MDATP cookbook:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

