---
title: Criar registros DNS quando o domínio for gerenciado pelo Google (eNom)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Saiba como acessar o eNom e criar o DNS por meio da página de domínios do Google.
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656850"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Criar registros DNS quando o domínio for gerenciado pelo Google (eNom)

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Para migrar suas contas de email para a Microsoft, você precisa criar um registro DNS no seu registrador de domínio.
  
Se você comprou seu domínio pelo Google ao se inscrever para sua conta do **Google Apps for Work** , seus registros DNS são gerenciados pelo Google, mas registrados com o eNom. 
  
Você pode acessar o eNom e criar o DNS, através da página de **domínios** do Google. Siga as etapas descritas neste artigo. 
  
## <a name="create-the-dns-record"></a>Criar o registro DNS

1. No [console de administração do Google](https://www.google.com/work/apps/business), selecione **entrar**.
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Insira seu nome de domínio e selecione **ir**.
    
    ![Imagem do botão](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Na parte inferior da página, selecione **mais controles**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Escolha **Domínios**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. Na página **domínios** , selecione **Adicionar/remover domínios**.
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Na página **domínios** , selecione **Configurações avançadas de DNS**.
    
    > [!NOTE]
    > Se você não adquiriu um nome de domínio pelo Google ao se inscrever para sua conta do **Google Apps for Work**, você não tem **Configurações Avançadas de DNS** na sua página **Domínios**. Em vez disso, você precisa ir diretamente para o site da Web do seu host de domínio para acessar suas configurações de DNS e realizar isso e as etapas a seguir. Confira [acessar as configurações de domínio do G Suite](https://support.google.com/a/answer/54693?hl=en) para obter mais informações. 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. Na página **configurações de DNS avançadas** , selecione **entrar no console DNS**. Anote as informações de **Nome de entrada** e **Senha**. Você precisará delas na próxima etapa. 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Entre no **Gerenciador de Domínios** do Google usando o **Nome de entrada** e a **Senha** da página **Configurações de DNS avançadas**. 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. Na página **_domain_name_*_, na seção _* registros do host** , selecione **Editar**.
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Na seção **registros de host** , selecione **Adicionar novo**.
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |**HOST**|**TXT VALUE**|**TIPO DE REGISTRO**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. 
  
    [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)
  
12. Selecione **Salvar**.
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Selecione **salvar alterações**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
