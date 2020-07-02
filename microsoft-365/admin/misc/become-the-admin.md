---
title: Executar um administrador interno tomada
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Saiba como verificar sua propriedade de email e domínio para assumir o controle de um locatário não gerenciado no Microsoft 365
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022152"
---
# <a name="perform-an-internal-admin-takeover"></a>Executar um administrador interno tomada

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 

Se você é um administrador e deseja assumir o controle de um locatário não gerenciado criado por uma inscrição de usuário de autoatendimento, é possível fazer isso com um administrador de tomada interno.

> [!NOTE]
> Uma inscrição autoatendimento para qualquer serviço de nuvem que usa o Azure AD adicionará o usuário a um diretório do Azure AD não gerenciado ou "sombra" e criará um locatário não gerenciado. Um locatário não gerenciado é um diretório sem um administrador global. Para determinar se um locatário é gerenciado ou não gerenciado, confira [determinando o tipo de locatário](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Etapa 1: verificar seu endereço de email

> [!NOTE]
> Se o autoatendimento estiver habilitado em seu locatário, os usuários poderão assinar serviços gratuitos, como o Power BI, por conta própria. Essas etapas pressupõem que uma assinatura de usuário de autoatendimento tenha criado o locatário não gerenciado que você deseja assumir como administrador. Na primeira etapa, você cria um contexto de usuário no locatário não gerenciado, usando o Power BI para ilustrar o caminho do tomada de administração.

1. Para se inscrever no Power bi, vá para o [site do Power bi](https://powerbi.com) e selecione **iniciar liberação**gratuita  >  de**inicialização** (na caixa compartilhar com o Power bi pro). 

2. Inscreva-se em uma conta de usuário que usa o nome de domínio da sua organização (como `powerbiadmin@contoso.com` ). Se sua conta já estiver em uso, entre usando sua senha atual.

3. Verifique seu email para o **código de verificação** e insira o código para validar seu endereço de email.
    
## <a name="step-2-create-a-new-account"></a>Etapa 2: criar uma nova conta

1. Ao inserir o código de verificação, você será levado a uma página onde você pode criar uma nova conta. 
    
2. Preencha os campos nome de usuário e senha com a conta que você deseja usar e, em seguida, selecione **Iniciar**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Etapa 3: verificar a propriedade do domínio e tornar-se o administrador

1. O assistente **de administração** será aberto. Se o assistente não for iniciado, procure o bloco **administrador** e selecione-o. 

2. Selecione **Sim, quero ser o administrador**.

3. Verifique se você é o proprietário do domínio que deseja assumir adicionando um registro TXT ao registrador de domínio. O assistente fornecerá o registro TXT a ser adicionado, além de fornecer um link para o site do registrador e um link para as instruções passo a passo.
    
4. Após adicionar o registro TXT ao seu site de registrador, retorne ao assistente e selecione **OK, adicionei o registro**.
    
> [!NOTE]
> A realização do locatário de sombra não afetará nenhuma informação ou serviço existente. No entanto, se qualquer usuário no domínio se inscrever em serviços que exijam uma licença, você será solicitado a comprar licenças para eles como parte da função de administrador. Você pode comprar ou remover licenças quando o processo de instalação administrativa estiver concluído.
  
## <a name="related-articles"></a>Artigos relacionados

YouTube: [3 etapas para fazer um tomada de administração de ti para o Power bi e o Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Tomada de administração no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Obter ajuda com domínios](../get-help-with-domains/get-help-with-domains.md)

[Usando a inscrição de autoatendimento em sua organização](self-service-sign-up.md)
  
[Noções básicas sobre a função de administrador do serviço do Power BI](https://docs.microsoft.com/power-bi/service-admin-role)

