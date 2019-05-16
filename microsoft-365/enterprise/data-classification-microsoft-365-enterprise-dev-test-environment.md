---
title: Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar rótulos de retenção do Office 365 em documentos no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072411"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Classificação de dados para seu ambiente de teste do Microsoft 365 Enterprise

Com as instruções deste artigo, você configura a classificação de dados usando rótulos de retenção do Office 365 no ambiente de teste do Microsoft 365 Enterprise.

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise

Se você só quiser configurar rótulos de retenção do Office 365 de uma forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar os rótulos de retenção do Office 365 em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> O teste dos rótulos de retenção do Office 365 não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 

## <a name="phase-2-create-office-365-retention-labels"></a>Fase 2: criar rótulos de retenção do Office 365

Nesta fase, você cria os rótulos de retenção para os diferentes níveis de retenção para pastas de documentos do SharePoint Online.

1. Acesse o [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com sua conta de administrador global.
    
2. Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.
    
3. Clique em **Rótulos de retenção > Criar um rótulo**.
    
4. No painel **Atribuir nome ao seu rótulo** digite **Público interno** em **Atribuir nome ao seu rótulo**, e clique em **Avançar**.

5. No painel **descritores de plano de arquivo**, clique em **próximo**.
    
6. No painel **configurações de etiqueta**, se necessário, defina **retenção** para **no**e, em seguida, clique em **próximo**.
    
7. No painel **Revise suas configurações**, clique em **Criar o rótulo**.
    
8. Repita as etapas 3 a 7 para etiquetas adicionais com esses nomes:
    
  - Private
    
  - Confidencial
    
  - Altamente Confidencial
  
9. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
    
10. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
11. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
    
12. Clique em **Concluído**.
    
13. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
14. No painel **Escolher locais**, clique em **Avançar**.
    
15. No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.
    
16. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.
 
Observe que pode levar alguns minutos para que os rótulos de retenção sejam publicados.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Fase 3: aplicar rótulos de retenção do Office 365 a documentos

Nesta fase, você descobre o comportamento de rótulo de retenção padrão para arquivos na pasta documentos de um site do SharePoint Online e altera manualmente o rótulo de retenção de um documento.

Primeiro, crie um site de equipe do SharePoint Online de nível confidencial:
  
1. Usando um navegador no computador local, entre no [Portal do Office 365](https://portal.office.com) usando sua conta de administrador global.
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na nova guia **SharePoint** no navegador, clique em **criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **nome do site de equipe**, digite **SensitiveFiles**.
    
6. Em **Descrição do site de equipe**, digite **site do SharePoint para arquivos confidenciais**.
    
7.  Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site de equipe do SensitiveFiles para o rótulo de retenção confidencial.
  
1. Na guia **SensitiveFiles** do navegador, clique em **documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações – Aplicar rótulo**, selecione **confidencial** na caixa suspensa e clique em **salvar**.

Em seguida, crie um novo documento no site do SensitiveFiles e altere seu rótulo de retenção.
    
1. Na pasta documentos, clique em **novo documento do Word do >**.
    
2. Digite algum texto no documento em branco. Aguarde o texto ser salvo.
    
3. Na barra de menus, clique em **documentos compartilhados**.
    
4. Clique no ícone do Word ao lado do nome do arquivo **Document. docx** .
    
5. No painel direito, na seção **Propriedades** , em **aplicar rótulo de retenção**, observe que o documento teve o rótulo **confidencial** aplicado automaticamente.
    
6. Clique em **Editar tudo**.
    
7. No painel **Document. docx** , em **aplicar rótulo**, selecione o rótulo **altamente confidencial** e clique em **salvar**.

Consulte a etapa [Configurar a classificação para seu ambiente](infoprotect-configure-classification.md) na fase de **proteção de informações** para obter informações e links sobre como implantar rótulos de retenção do Office 365 em produção.

## <a name="next-step"></a>Próxima etapa

Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 