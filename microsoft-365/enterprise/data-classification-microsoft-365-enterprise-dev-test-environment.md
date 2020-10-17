---
title: Classificação de dados para o ambiente de teste do Microsoft 365 for Enterprise
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
description: Use este guia de laboratório de teste para criar e usar rótulos de retenção em documentos no ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487727"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Classificação de dados para o ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Este artigo descreve como configurar a classificação de dados usando rótulos de retenção no ambiente de teste do Microsoft 365 for Enterprise.

Classificar dados em seu ambiente de teste envolve três fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: criar rótulos de retenção](#phase-2-create-retention-labels)
- [Fase 3: aplicar rótulos de retenção a documentos](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você só quiser configurar os rótulos de retenção de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar os rótulos de retenção em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> O teste de rótulos de retenção não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: criar rótulos de retenção

Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para as pastas de documentos do SharePoint Online:

1. Entre na central de [segurança do Microsoft 365](https://security.microsoft.com/homepage) com sua conta de administrador global.
1. Na guia **segurança doméstica-Microsoft 365** do navegador, selecione rótulos de **Classification**  >  **retenção**de classificação.
1. Selecione **Criar um rótulo**.
1. No painel **nomear seu rótulo** , digite **público interno** em **nome seu rótulo**e, em seguida, selecione **Avançar**.
1. No painel de **descritores de plano de arquivo** , selecione **Avançar**.
1. No painel **configurações do rótulo** , se necessário, defina **retenção** como **ativado**e, em seguida, selecione **Avançar**.
1. No painel **examinar suas configurações** , selecione **criar o rótulo**.
1. Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:
  - Private
  - Confidencial
  - Altamente Confidencial
1. No painel **Rótulos de retenção** , selecione **publicar rótulos**.
1. No painel **escolher rótulos para publicar** , selecione **escolher rótulos para publicar**.
1. No painel **escolher rótulos** , selecione **Adicionar** e selecione todos os quatro rótulos.
1. Selecione **Adicionar**e, em seguida, selecione **concluído**.
1. No painel **escolher rótulos para publicar** , selecione **Avançar**.
1. No painel **escolher locais** , selecione **Avançar**.
1. No painel **nomear sua política** , digite **organização de exemplo** em **nome**e, em seguida, selecione **Avançar**.
1. No painel **rever suas configurações** , selecione **publicar rótulos**.
 
Pode levar alguns minutos para que os rótulos de retenção sejam publicados.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: aplicar rótulos de retenção a documentos

Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.

Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:
  
1. Usando uma instância privada do navegador, entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando sua conta de administrador global.
1. Na lista de blocos, selecione **SharePoint**.
1. Na nova guia **SharePoint** no navegador, selecione **criar site**.
1. Na página **Criar um site**, clique em **Site de equipe**.
1. Na caixa **nome do site de equipe** , digite **SensitiveFiles**.
1. Na caixa **Descrição do site de equipe** , digite **site do SharePoint para arquivos confidenciais**.
1. Em **configurações de privacidade**, selecione **membros somente privados podem acessar esse site**e, em seguida, selecione **Avançar**.
1. No painel **quem você deseja adicionar?** , selecione **concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.
  
1. Na guia **SensitiveFiles** do navegador, selecione **documentos**.
1. Selecione o ícone **configurações** e, em seguida, selecione **configurações da biblioteca**.
1. Em **permissões e gerenciamento**, selecione **aplicar rótulo a itens nesta lista ou biblioteca**. Se essa opção não for exibida, seus rótulos de retenção ainda não foram publicados. Tente esta etapa mais tarde.
1. Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e, em seguida, selecione **salvar**.

Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.
    
1. Na pasta documentos, selecione **novo**  >  **documento do Word**.
1. Insira algum texto no documento em branco. Aguarde o texto ser salvo.
1. Na barra de menus, selecione **documentos compartilhados**.
1. Ao lado do nome do arquivo **Document.docx** , selecione as reticências verticais e, em seguida, selecione **detalhes**.
1. No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o rótulo de retenção **confidencial** foi aplicado automaticamente ao documento.
1. Clique em **Editar Tudo**.
1. No painel **Document.docx** , em **aplicar rótulo de retenção**, selecione o rótulo **altamente confidencial** e, em seguida, selecione **salvar**.

## <a name="next-step"></a>Próxima etapa

Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
