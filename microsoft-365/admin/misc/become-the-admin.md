---
title: Executar uma aquisição interna do administrador
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Saiba como verificar sua propriedade de email e domínio para assumir um locatário não-funcionário no Microsoft 365
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914841"
---
# <a name="perform-an-internal-admin-takeover"></a>Executar uma aquisição interna do administrador

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 

Se você for um administrador e quiser assumir um locatário não gerenciada criado por uma assinatura de usuário autônomo, você pode fazer isso com uma aquisição interna do administrador.

> [!NOTE]
> Uma assinatura de autoatenduro para qualquer serviço de nuvem que use o Azure AD adicionará o usuário a um diretório do Azure AD sem gestão ou "sombra" e criará um locatário não-autônomo. Um locatário sem gestão é um diretório sem um administrador global. Para determinar se um locatário é gerenciado ou não gerenciado, consulte [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Etapa 1: Verificar seu endereço de email

> [!NOTE]
> Se o self-service estiver habilitado em seu locatário, os usuários poderão se inscrever em serviços gratuitos, como o Power BI, por conta própria. Estas etapas presumem que uma assinatura de usuário de autoatendados tenha criado o locatário não gerenciado que você deseja assumir como administrador. Na primeira etapa, você cria um contexto de usuário no locatário não gerenciado, usando o Power BI para ilustrar o caminho de aquisição do administrador.

1. Para se inscrever no Power BI, acesse o [site do Power BI](https://powerbi.com) e selecione Iniciar avaliação gratuita de Início Livre (na caixa Compartilhar com o Power BI   >   Pro). 

2. Inscreva-se em uma conta de usuário que usa o nome de domínio da sua organização (como `powerbiadmin@contoso.com` ). Se sua conta já estiver em uso, entre usando sua senha atual.

3. Verifique seu email para o código **de verificação e** insira o código para validar seu endereço de email.
    
## <a name="step-2-create-a-new-account"></a>Etapa 2: Criar uma nova conta

1. Quando você digitar o código de verificação, você será trazido para uma página onde poderá criar uma nova conta. 
    
2. Preencha os campos nome de usuário e senha com a conta que você deseja usar e selecione **Iniciar**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Etapa 3: Verificar a propriedade do domínio e se tornar o administrador

1. O **assistente Tornar-se o** administrador será aberto. Se o assistente não for acionado, procure o **painel** Administrador e selecione-o. 

2. Selecione **Sim, quero ser o administrador**.

3. Verifique se você possui o domínio que deseja assumir adicionando um registro TXT ao registrador de domínios. O assistente fornecerá o registro TXT a ser acrescentado, bem como fornecerá um link para o site do registrador e um link para instruções passo a passo.
    
4. Depois de adicionar o registro TXT ao site do registrador, retorne ao assistente e selecione **Ok,** adicionei o registro .
    
> [!NOTE]
> Assumir o locatário de sombra não afetará quaisquer informações ou serviços existentes. No entanto, se qualquer usuário no domínio tiver se inscreveu para serviços que exigem uma licença, você será solicitado a comprar licenças para eles como parte de assumir a função de administrador. Você pode comprar ou remover licenças depois que o processo de instalação do administrador for concluído.
  
## <a name="related-articles"></a>Artigos relacionados

YouTube: 3 etapas para fazer uma Tomada de Administração de TI [para Power BI e Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Administração de aquisição no Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Usando o autoatendimento inscreva-se na sua instituição](self-service-sign-up.md)
  
[Noções básicas sobre a função de administrador de serviço do Power BI](/power-bi/service-admin-role)