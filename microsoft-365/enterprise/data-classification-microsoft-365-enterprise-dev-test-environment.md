---
title: Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para criar e usar o Office 365 rótulos em documentos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865293"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente de teste de classificação de dados para a sua empresa de 365 da Microsoft

Com as instruções deste artigo, você deve configurar a classificação de dados usando o Office 365 rótulos em seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja configurar rótulos de Office 365 de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar rótulos do Office 365 em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Teste o Office 365 rótulos não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 

## <a name="phase-2-create-office-365-labels"></a>Fase 2: Criar rótulos do Office 365

Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas de documentos do SharePoint Online.
  
1. Se necessário, use uma instância particular do seu navegador da Internet e entrar no portal do Office 365 com sua conta de administrador global. Para obter ajuda, consulte [Where entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na guia **Microsoft Office Home**, clique no bloco **Administração**.
    
3. Na nova guia **Centro de Administração do Office** do navegador, clique em **Centros de Administração > Segurança&amp; e Conformidade**.
    
4. Na nova guia **Início – Segurança &amp;e Conformidade** do navegador, clique em **Classificações > Rótulos**.
    
5. No painel **Início > Rótulos**, clique em **Criar um rótulo**.
    
6. No painel **Atribuir nome ao seu rótulo**, digite **Público interno** e clique em **Avançar**.
    
7. No painel **Configurações de rótulo**, clique em **Avançar**.
    
8. No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.
    
9. Repita as etapas de 5 a 8 para os rótulos adicionais:
    
  - Private
    
  - Confidencial
    
  - Altamente Confidencial
    
10. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
    
11. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
12. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
    
13. Clique em **Concluído**.
    
14. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
15. No painel **Escolher locais**, clique em **Avançar**.
    
16. No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.
    
17. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.

Observe que poderá levar alguns minutos para que os rótulos sejam publicados.

## <a name="phase-3-apply-office-365-labels-to-documents"></a>Fase 3: Aplicar rótulos do Office 365 a documentos

Nesta fase, você pode descobrir o comportamento padrão de rótulo para arquivos na pasta de documentos de um site do SharePoint Online e altera manualmente o rótulo de um documento.

Primeiro, crie um site de equipe do SharePoint Online confidenciais nível:
  
1. Usando um navegador no computador local, entre no Portal do Office 365 usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na lista de blocos, clique em **SharePoint**.
    
3. Na guia **SharePoint** de novo no seu navegador, clique em **Criar site**.
    
4. Na página **Criar um site**, clique em **Site de equipe**.
    
5. Em **nome do site de equipe**, digite **SensitiveFiles**.
    
6. Na **Descrição do site de equipe**, digite o **site do SharePoint para arquivos confidenciais**.
    
7.  Em **Configurações de privacidade**, escolha **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
    
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
    
Em seguida, configure a pasta de documentos do site da equipe SensitiveFiles para o rótulo de confidencial.
  
1. Na guia **SensitiveFiles** do seu navegador, clique em **documentos**.
    
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
4. Em **Configurações se aplicam rótulo**, selecione **confidenciais** na caixa suspensa e clique em **Salvar**.

Em seguida, crie um novo documento no site SensitiveFiles e altere seu rótulo.
    
1. Na pasta de documentos, clique em **New > documento do Word**.
    
2. Digite um texto do documento em branco. Aguarde até que o texto seja salvo.
    
3. Na barra de menus, clique em **Documentos compartilhados**.
    
4. Clique no ícone do Word ao lado do nome de arquivo **Document.docx** .
    
5. No painel direito, na seção **Propriedades** , em **Aplicar rótulo**, observe que o documento teve o rótulo **confidenciais** automaticamente aplicado.
    
6. Clique em **Editar todos**.
    
7. No painel **Document.docx** , em **Aplicar rótulo**, selecione o rótulo **Altamente confidenciais** e clique em **Salvar**.

Consulte a etapa de [classificação de Configure para seu ambiente](data-classification-microsoft-365-enterprise-dev-test-environment.md) na fase de **proteção de informações** para obter informações e links para os rótulos do Office 365 em produção.

## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 