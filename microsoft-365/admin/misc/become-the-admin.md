---
title: Executar uma administração interna
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
description: Saiba como verificar a propriedade do seu email e domínio para assumir um locatário nãomanagedo no Microsoft 365
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658058"
---
# <a name="perform-an-internal-admin-takeover"></a>Executar uma administração interna

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 

Se você for um administrador e quiser assumir um locatário não gerenciada criado por uma assinatura de usuário de autoatendida, você pode fazer isso com uma administração interna.

> [!NOTE]
> Uma assinatura de autoatendado para qualquer serviço de nuvem que use o Azure AD adicionará o usuário a um diretório do Azure AD não-manado ou "sombra" e criará um locatário não-manado. Um locatário não-administrador é um diretório sem um administrador global. Para determinar se um locatário é gerenciado ou não gerenciado, consulte [Determinando o tipo de locatário.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>Etapa 1: verificar seu endereço de email

> [!NOTE]
> Se o autoatendado estiver habilitado em seu locatário, os usuários poderão se inscrever para serviços gratuitos, como o Power BI, por conta própria. Estas etapas presumem que uma assinatura de usuário de autoatendado tenha criado o locatário não gerenciada que você deseja assumir como administrador. Na primeira etapa, você cria um contexto de usuário no locatário não gerenciada, usando o Power BI para ilustrar o caminho de administração do administrador.

1. Para se inscrever no Power BI, vá para o site do [Power BI](https://powerbi.com) e selecione Iniciar avaliação gratuita de Início Gratuito (na caixa Compartilhar com o Power  >   BI Pro). 

2. Inscreva-se com uma conta de usuário que use o nome de domínio da sua organização (como `powerbiadmin@contoso.com` ). Se sua conta já estiver em uso, entre usando sua senha atual.

3. Verifique seu email em busca do **código de verificação** e digite o código para validar seu endereço de email.
    
## <a name="step-2-create-a-new-account"></a>Etapa 2: Criar uma nova conta

1. Ao inserir o código de verificação, você será levado a uma página onde poderá criar uma nova conta. 
    
2. Preencha os campos nome de usuário e senha com a conta que você deseja usar e selecione **Iniciar.** 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Etapa 3: Verificar a propriedade do domínio e tornar-se o administrador

1. O **assistente Tornar-se** o administrador será aberto. Se o assistente não iniciar, procure o **painel** Administrador e selecione-o. 

2. Selecione **Sim, quero ser o administrador.**

3. Verifique se você é o próprio domínio que deseja assumir adicionando um registro TXT ao seu registrador de domínios. O assistente fornecerá o registro TXT a ser acrescentado, além de fornecer um link para o site do registrador e um link para instruções passo a passo.
    
4. Depois de adicionar o registro TXT ao seu site de registrador, retorne ao assistente e selecione **Ok, adicionei o registro.**
    
> [!NOTE]
> Assumir o locatário de sombra não afetará qualquer informação ou serviço existente. No entanto, se algum usuário no domínio se inscreveu em serviços que exigem uma licença, você será solicitado a comprar licenças para eles como parte de assumir a função de administrador. Você pode comprar ou remover licenças depois que o processo de instalação do administrador for concluído.
  
## <a name="related-articles"></a>Artigos relacionados

YouTube: 3 etapas para fazer uma Tomada de Controle de Administração de TI [para o Power BI e o Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Administração no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Usando o autoatendimento inscreva-se na sua instituição](self-service-sign-up.md)
  
[Noções básicas sobre a função de administrador de serviços do Power BI](https://docs.microsoft.com/power-bi/service-admin-role)

