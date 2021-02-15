---
title: Classificação de dados do ambiente de teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este Guia de Laboratório de Teste para criar e usar rótulos de retenção em documentos em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487727"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Classificação de dados do ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*

Este artigo descreve como configurar a classificação de dados usando rótulos de retenção no ambiente de teste do Microsoft 365 para empresas.

A classificação de dados em seu ambiente de teste envolve três fases:
- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Criar rótulos de retenção](#phase-2-create-retention-labels)
- [Fase 3: Aplicar rótulos de retenção a documentos](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você só quiser configurar rótulos de retenção de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar rótulos de retenção em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste de rótulos de retenção não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação a um grupo e fazer testes com ele em um ambiente que representa uma organização típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Criar rótulos de retenção

Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online:

1. Entre no centro [de segurança do Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.
1. Na página **Home - guia de segurança do Microsoft 365** do navegador, selecione **rótulos de** Retenção de  >  **Classificação.**
1. Selecione **Criar um rótulo**.
1. In the **Name your label** pane, enter Internal **Public** in Name **your label**, and then select **Next**.
1. No painel **descritores de plano de** arquivo, selecione **Próximo**.
1. No painel **de configurações de** Rótulo, se necessário, **de** definida Retenção **como** Em e, em seguida, selecione **Próximo**.
1. No painel **Revisar suas configurações,** selecione **Criar o rótulo.**
1. Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:
  - Private
  - Confidencial
  - Altamente Confidencial
1. No painel **Rótulos de** retenção, selecione **Publicar rótulos.**
1. No painel **Escolher rótulos para publicar,** selecione **Escolher rótulos para publicar.**
1. No painel **Escolher rótulos,** selecione **Adicionar** e selecione todos os quatro rótulos.
1. Selecione **Adicionar** e, em seguida, **Terminar.**
1. On the **Choose labels to publish** pane, select **Next**.
1. No painel **Escolher locais,** selecione **Próximo**.
1. On the **Name your policy** pane, enter Example **organization** in **Name**, and then select **Next**.
1. No painel **Revisar suas configurações,** selecione **Publicar rótulos.**
 
Pode levar alguns minutos para que os rótulos de retenção sejam publicados.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Aplicar rótulos de retenção a documentos

Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta Documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.

Primeiro, crie um site de equipe do SharePoint Online de nível sensível:
  
1. Usando uma instância privada do navegador, entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) usando sua conta de administrador global.
1. Na lista de blocos, selecione **SharePoint**.
1. Na nova guia **Do SharePoint** no navegador, selecione **Criar site.**
1. Na página **Criar um site**, clique em **Site de equipe**.
1. Na caixa **Nome do site de** equipe, insira **SensitiveFiles**.
1. Na caixa **de descrição do site de** equipe, insira o site do **SharePoint para arquivos confidenciais.**
1. Em **Configurações de privacidade**, selecione Privado - somente membros podem acessar este **site** e, em seguida, selecione **Próximo**.
1. In the **Who do you want to add?** pane, select **Finish**.
    
Em seguida, configure a pasta Documentos do site de equipe SensitiveFiles para o rótulo de retenção Sensitive.
  
1. Na guia **SensitiveFiles** do navegador, selecione **Documentos.**
1. Selecione o **ícone Configurações** e, em seguida, selecione **Configurações de biblioteca.**
1. Em **Permissões e Gerenciamento,** selecione **Aplicar rótulo a itens nesta lista ou biblioteca.** Se essa opção não aparecer, seus rótulos de retenção ainda não foram publicados. Tente esta etapa posteriormente.
1. Em **Configurações – Aplicar Rótulo**, selecione **Sensitive** na caixa de lista drop-down e, em seguida, **selecione Salvar**.

Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo de retenção.
    
1. Na pasta documentos, selecione **Novo documento**  >  **do Word.**
1. Insira algum texto no documento em branco. Aguarde até que o texto seja salvo.
1. Na barra de menus, selecione **Documentos Compartilhados.**
1. Ao lado do **Document.docx** nome do arquivo, selecione as reellipses verticais e selecione **Detalhes.**
1. No painel direito, na  seção Propriedades, em Aplicar rótulo de **retenção,** observe que o documento teve o rótulo de retenção Sensitive aplicado automaticamente. 
1. Clique em **Editar Tudo**.
1. No painel **Document.docx,** em Aplicar rótulo de **retenção,** selecione o rótulo Altamente **Confidencial** e selecione **Salvar.**

## <a name="next-step"></a>Próxima etapa

Explore recursos [e funcionalidades adicionais](m365-enterprise-test-lab-guides.md#information-protection) de proteção de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
