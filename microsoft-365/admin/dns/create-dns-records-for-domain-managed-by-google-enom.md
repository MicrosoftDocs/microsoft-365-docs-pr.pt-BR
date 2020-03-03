---
title: Criar registros DNS quando o domínio for gerenciado pelo Google (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Saiba como acessar o eNom e criar o DNS por meio da página de domínios do Google.
ms.openlocfilehash: 566b3990c6cc3080eac9d1367531eea42ab135d1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362496"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a><span data-ttu-id="1734a-103">Criar registros DNS quando o domínio for gerenciado pelo Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="1734a-103">Create DNS records when your domain is managed by Google (eNom)</span></span>

 <span data-ttu-id="1734a-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1734a-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1734a-105">Para migrar suas contas de email para o Office 365, você precisa criar um registro DNS em seu registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="1734a-105">To migrate your mail accounts to Office 365, you need to create a DNS record at your domain registrar.</span></span>
  
<span data-ttu-id="1734a-106">Se você comprou seu domínio pelo Google ao se inscrever para sua conta do **Google Apps for Work** , seus registros DNS são gerenciados pelo Google, mas registrados com o eNom.</span><span class="sxs-lookup"><span data-stu-id="1734a-106">If you purchased your domain through Google while signing up for your **Google Apps for Work** account, your DNS records are managed by Google but registered with eNom.</span></span> 
  
<span data-ttu-id="1734a-107">Você pode acessar o eNom e criar o DNS, através da página de **domínios** do Google.</span><span class="sxs-lookup"><span data-stu-id="1734a-107">You can access eNom, and create DNS, through the Google **Domains** page.</span></span> <span data-ttu-id="1734a-108">Siga as etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="1734a-108">Just follow the steps in this article.</span></span> 
  
## <a name="create-the-dns-record"></a><span data-ttu-id="1734a-109">Criar o registro DNS</span><span class="sxs-lookup"><span data-stu-id="1734a-109">Create the DNS record</span></span>

1. <span data-ttu-id="1734a-110">No [console de administração do Google](https://www.google.com/work/apps/business), selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="1734a-110">At the [Google Admin console](https://www.google.com/work/apps/business), select **Sign In**.</span></span>
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. <span data-ttu-id="1734a-112">Insira seu nome de domínio e selecione **ir**.</span><span class="sxs-lookup"><span data-stu-id="1734a-112">Enter your domain name, and then select **Go**.</span></span>
    
    ![Imagem do botão](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. <span data-ttu-id="1734a-114">Na parte inferior da página, selecione **mais controles**.</span><span class="sxs-lookup"><span data-stu-id="1734a-114">At the bottom of the page, select **More controls**.</span></span>
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. <span data-ttu-id="1734a-116">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="1734a-116">Select **Domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. <span data-ttu-id="1734a-118">Na página **domínios** , selecione **Adicionar/remover domínios**.</span><span class="sxs-lookup"><span data-stu-id="1734a-118">On the **Domains** page, select **Add/remove domains**.</span></span>
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. <span data-ttu-id="1734a-120">Na página **domínios** , selecione **Configurações avançadas de DNS**.</span><span class="sxs-lookup"><span data-stu-id="1734a-120">On the **Domains** page, select **Advanced DNS settings**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1734a-121">Se você não adquiriu um nome de domínio pelo Google ao se inscrever para sua conta do **Google Apps for Work**, você não tem **Configurações Avançadas de DNS** na sua página **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="1734a-121">If you didn't purchase a domain name through Google while signing up for your **Google Apps for Work** account, you won't have **Advanced DNS settings** on your **Domains** page.</span></span> <span data-ttu-id="1734a-122">Em vez disso, você precisa ir diretamente para o site da Web do seu host de domínio para acessar suas configurações de DNS e realizar isso e as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1734a-122">Instead, you must go directly to your domain host's web site to access your DNS settings and to perform this and the following steps.</span></span> <span data-ttu-id="1734a-123">Confira [acessar as configurações de domínio do G Suite](https://support.google.com/a/answer/54693?hl=en) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1734a-123">See [Access your G Suite domain settings](https://support.google.com/a/answer/54693?hl=en) for more information.</span></span> 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. <span data-ttu-id="1734a-125">Na página **configurações de DNS avançadas** , selecione **entrar no console DNS**.</span><span class="sxs-lookup"><span data-stu-id="1734a-125">On the **Advanced DNS settings** page, select **Sign in to DNS Console**.</span></span> <span data-ttu-id="1734a-126">Anote as informações de **Nome de entrada** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="1734a-126">Note the **Sign-in name** and **Password** information.</span></span> <span data-ttu-id="1734a-127">Você precisará delas na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="1734a-127">You'll need it in the next step.</span></span> 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. <span data-ttu-id="1734a-129">Entre no **Gerenciador de Domínios** do Google usando o **Nome de entrada** e a **Senha** da página **Configurações de DNS avançadas**.</span><span class="sxs-lookup"><span data-stu-id="1734a-129">Log in to the Google **Domain Manager** using the **Sign-in name** and **Password** from the **Advanced DNS settings** page.</span></span> 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. <span data-ttu-id="1734a-131">Na página ***domain_name*** , na seção **registros de host** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1734a-131">On the ***domain_name*** page, in the **Host Records** section, select **Edit**.</span></span>
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. <span data-ttu-id="1734a-133">Na seção **registros de host** , selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="1734a-133">In the **Host Records** section, select **Add New**.</span></span>
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. <span data-ttu-id="1734a-135">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="1734a-135">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="1734a-136">**HOST**</span><span class="sxs-lookup"><span data-stu-id="1734a-136">**HOST**</span></span>|<span data-ttu-id="1734a-137">**TXT VALUE**</span><span class="sxs-lookup"><span data-stu-id="1734a-137">**TXT VALUE**</span></span>|<span data-ttu-id="1734a-138">**TIPO DE REGISTRO**</span><span class="sxs-lookup"><span data-stu-id="1734a-138">**RECORD TYPE**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> ||<span data-ttu-id="1734a-139">TXT</span><span class="sxs-lookup"><span data-stu-id="1734a-139">TXT</span></span>  <br/> |

    > [!NOTE]
    > <span data-ttu-id="1734a-140">This is an example.</span><span class="sxs-lookup"><span data-stu-id="1734a-140">This is an example.</span></span> <span data-ttu-id="1734a-141">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="1734a-141">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> 
  
    [<span data-ttu-id="1734a-142">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="1734a-142">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
  
12. <span data-ttu-id="1734a-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1734a-143">Select **Save**.</span></span>
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. <span data-ttu-id="1734a-145">Selecione **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="1734a-145">Select **Save Changes**.</span></span>
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  <span data-ttu-id="1734a-p105">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1734a-p105">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
