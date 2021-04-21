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
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="bf788-104">Implantar o Defender para Ponto de Extremidade no Linux com Chef</span><span class="sxs-lookup"><span data-stu-id="bf788-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="bf788-105">Antes de começar:</span><span class="sxs-lookup"><span data-stu-id="bf788-105">Before you begin:</span></span>

- <span data-ttu-id="bf788-106">Instale o unzip se ainda não estiver instalado.</span><span class="sxs-lookup"><span data-stu-id="bf788-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="bf788-107">Os componentes do Chefe já estão instalados e existe um repositório do Chefe (chefe gerar repositório ) para armazenar o livro de receitas que será usado para implantar no Defender for Endpoint em servidores Linux gerenciados <reponame> do Chefe.</span><span class="sxs-lookup"><span data-stu-id="bf788-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="bf788-108">Você pode criar um novo livro de receita em seu repositório existente executando o seguinte comando de dentro da pasta de pastas de receitas que está no repositório do seu chefe:</span><span class="sxs-lookup"><span data-stu-id="bf788-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="bf788-109">Este comando criará uma nova estrutura de pastas para o novo livro de receitas chamado mdatp.</span><span class="sxs-lookup"><span data-stu-id="bf788-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="bf788-110">Você também pode usar um livro de receita existente se já tiver um que você gostaria de usar para adicionar a implantação do MDE.</span><span class="sxs-lookup"><span data-stu-id="bf788-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="bf788-111">Depois que o livro de receitas for criado, crie uma pasta de arquivos dentro da pasta do livro de receitas que acabou de ser criada:</span><span class="sxs-lookup"><span data-stu-id="bf788-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="bf788-112">Transfira o arquivo zip de Integração do Servidor Linux que pode ser baixado do portal do Centro de Segurança do Microsoft Defender para essa nova pasta de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bf788-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="bf788-113">Na Estação de Trabalho do Chefe, navegue até a pasta mdatp/recipes.</span><span class="sxs-lookup"><span data-stu-id="bf788-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="bf788-114">Essa pasta é criada quando o livro de receitas foi gerado.</span><span class="sxs-lookup"><span data-stu-id="bf788-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="bf788-115">Use seu editor de texto preferencial (como vi ou nano) para adicionar as seguintes instruções ao final do arquivo default.rb:</span><span class="sxs-lookup"><span data-stu-id="bf788-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="bf788-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="bf788-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="bf788-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="bf788-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="bf788-118">Em seguida, salve e feche o arquivo default.rb.</span><span class="sxs-lookup"><span data-stu-id="bf788-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="bf788-119">Em seguida, crie um novo arquivo de receita chamado install_mdatp.rb na pasta receitas e adicione este texto ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="bf788-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="bf788-120">Você precisará modificar o número de versão, a distribuição e o nome de repo para corresponder à versão que você está implantando e ao canal que você gostaria de implantar.</span><span class="sxs-lookup"><span data-stu-id="bf788-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="bf788-121">Em seguida, você deve criar um arquivo onboard_mdatp.rb na pasta mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="bf788-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="bf788-122">Adicione o seguinte texto a esse arquivo:</span><span class="sxs-lookup"><span data-stu-id="bf788-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="bf788-123">Certifique-se de atualizar o nome do caminho para o local do arquivo de integração.</span><span class="sxs-lookup"><span data-stu-id="bf788-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="bf788-124">Para testar implantá-lo na estação de trabalho do Chefe, basta executar ``sudo chef-client -z -o mdatp`` .</span><span class="sxs-lookup"><span data-stu-id="bf788-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="bf788-125">Após a implantação, você deve considerar a criação e a implantação de um arquivo de configuração nos servidores com base em Definir  [preferências](/linux-preferences.md)do Microsoft Defender para Ponto de Extremidade no Linux .</span><span class="sxs-lookup"><span data-stu-id="bf788-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender for Endpoint on Linux](/linux-preferences.md).</span></span>  
<span data-ttu-id="bf788-126">Depois de criar e testar seu arquivo de configuração, você pode posicioná-lo na pasta cookbook/mdatp/files onde também colocou o pacote de integração.</span><span class="sxs-lookup"><span data-stu-id="bf788-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="bf788-127">Em seguida, você pode criar um arquivo settings_mdatp.rb na pasta mdatp/recipies e adicionar este texto:</span><span class="sxs-lookup"><span data-stu-id="bf788-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="bf788-128">Para incluir essa etapa como parte da receita, basta adicionar include_recipe ':: settings_mdatp' ao seu arquivo default.rb na pasta de receita.</span><span class="sxs-lookup"><span data-stu-id="bf788-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="bf788-129">Você também pode usar o crontab para agendar atualizações automáticas Agendar uma atualização do Microsoft Defender para Ponto de [Extremidade (Linux)](linux-update-MDE-Linux.md).</span><span class="sxs-lookup"><span data-stu-id="bf788-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="bf788-130">Desinstale o livro de receitaS MDATP:</span><span class="sxs-lookup"><span data-stu-id="bf788-130">Uninstall MDATP cookbook:</span></span>

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

