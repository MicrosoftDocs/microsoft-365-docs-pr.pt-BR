---
title: Classificação de dados para seu Microsoft 365 para ambiente de teste empresarial
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
description: Use este Guia de Laboratório de Teste para criar e usar rótulos de retenção em documentos em seu Microsoft 365 para ambiente de teste empresarial.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919183"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Classificação de dados para seu Microsoft 365 para ambiente de teste empresarial

*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*

Este artigo descreve como configurar a classificação de dados usando rótulos de retenção em seu Microsoft 365 ambiente de teste empresarial.

A classificação de dados em seu ambiente de teste envolve três fases:
- [Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Criar rótulos de retenção](#phase-2-create-retention-labels)
- [Fase 3: aplicar rótulos de retenção a documentos](#phase-3-apply-retention-labels-to-documents)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial

Se você deseja apenas configurar rótulos de retenção de maneira leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar rótulos de retenção em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Os rótulos de retenção de teste não exigem o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Criar rótulos de retenção

Nesta fase, crie os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos SharePoint Online:

1. Entre no centro de [segurança Microsoft 365 com](https://security.microsoft.com/homepage) sua conta de administrador global.
1. Na guia **Home - Microsoft 365 de segurança** do navegador, selecione **Rótulos de** Retenção de  >  **Classificação.**
1. Selecione **Criar um rótulo**.
1. No painel **Nomear seu rótulo,** insira **Público Interno** em **Nome do** rótulo e selecione **Próximo**.
1. No painel **Descritores de plano de** arquivo, selecione **Próximo**.
1. No painel **Configurações de** rótulo, se necessário, desem conjunto **Retenção** como **Em** e selecione **Próximo**.
1. No painel **Revisar suas configurações,** selecione **Criar o rótulo**.
1. Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:
  - Private
  - Confidencial
  - Altamente Confidencial
1. No painel **Rótulos de retenção,** selecione **Publicar rótulos**.
1. No painel **Escolher rótulos para publicar,** selecione **Escolher rótulos para publicar**.
1. No painel **Escolher rótulos,** selecione **Adicionar** e selecione todos os quatro rótulos.
1. Selecione **Adicionar** e, em seguida, selecione **Feito**.
1. No painel **Escolher rótulos para publicar,** selecione **Próximo**.
1. No painel **Escolher locais,** selecione **Próximo**.
1. No painel **Nomear sua política,** digite **Exemplo de organização** em **Nome** e selecione **Próximo**.
1. No painel **Revisar suas configurações,** selecione **Publicar rótulos**.
 
Pode levar alguns minutos para que os rótulos de retenção sejam publicados.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: aplicar rótulos de retenção a documentos

Nesta fase, você descobre o comportamento padrão do rótulo de retenção para arquivos na pasta Documentos de um site SharePoint Online e altera manualmente o rótulo de retenção de um documento.

Primeiro, crie um site de equipe de nível SharePoint Online:
  
1. Usando uma instância privada do navegador, entre no centro de administração Microsoft 365 [usando](https://admin.microsoft.com) sua conta de administrador global.
1. Na lista de blocos, selecione **SharePoint**.
1. Na nova guia **SharePoint** no navegador, selecione **Criar site**.
1. Na página **Criar um site**, clique em **Site de equipe**.
1. Na caixa **Nome do site de** equipe, digite **SensitiveFiles**.
1. Na caixa **Descrição do site de** equipe, **insira SharePoint site para arquivos confidenciais.**
1. Em **Configurações de Privacidade**, selecione Privado - somente membros podem acessar este **site** e, em seguida, selecione **Next**.
1. No painel **Who você deseja adicionar?** selecione **Concluir**.
    
Em seguida, configure a pasta Documentos do site de equipe SensitiveFiles para o rótulo de retenção Sensitive.
  
1. Na guia **SensitiveFiles** do navegador, selecione **Documentos**.
1. Selecione o **Configurações** e, em seguida, selecione **Configurações de biblioteca**.
1. Em **Permissões e Gerenciamento,** selecione **Aplicar rótulo a itens nesta lista ou biblioteca.** Se essa opção não aparecer, seus rótulos de retenção ainda não foram publicados. Tente esta etapa posteriormente.
1. Em **Configurações-Aplicar Rótulo,** selecione **Confidenciais** na caixa de seleção e selecione **Salvar**.

Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo de retenção.
    
1. Na pasta documentos, selecione **Novo documento**  >  **do Word**.
1. Insira algum texto no documento em branco. Aguarde até que o texto seja salvo.
1. Na barra de menus, selecione **Documentos Compartilhados**.
1. Ao lado do **nomeDocument.docx** arquivo, selecione a releição vertical e selecione **Detalhes**.
1. No painel direito, na seção **Propriedades,** em **Aplicar** rótulo de retenção, observe que o documento teve o **rótulo** de retenção Sensitive aplicado automaticamente.
1. Clique em **Editar Tudo**.
1. No painel **Document.docx,** em **Aplicar** rótulo de retenção, selecione o rótulo **Altamente** Confidencial e selecione **Salvar**.

## <a name="next-step"></a>Próxima etapa

Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)