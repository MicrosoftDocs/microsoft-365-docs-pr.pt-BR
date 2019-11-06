---
title: Proteger arquivos em equipes com rótulos de retenção e DLP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumo: aplique rótulos de retenção e políticas DLP (prevenção contra perda de dados) a arquivos em equipes com vários níveis de proteção de informações.'
ms.openlocfilehash: 89320a074d5d52062268a7585081849ac42d2025
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925729"
---
# <a name="protect-files-in-teams-with-retention-labels-and-dlp"></a>Proteger arquivos em equipes com rótulos de retenção e DLP

 
Use as etapas neste artigo para projetar e implantar rótulos de retenção e DLP (prevenção contra perda de dados) em equipes de linha de base, confidenciais e altamente confidenciais e seus sites subjacentes do SharePoint. Para obter mais informações sobre essas três camadas de proteção, confira [Proteção de arquivos no Microsoft Teams](secure-files-in-teams.md).
  
## <a name="how-this-works"></a>Como isso funciona

1. Crie e publique as etiquetas de retenção desejadas. Pode levar até 12 horas para que elas sejam publicadas.
2. Para os sites subjacentes do SharePoint desejados, edite as configurações da biblioteca de documentos para aplicar os rótulos de retenção desejados a itens na biblioteca.
3. Crie políticas DLP para executar ações com base nos rótulos de retenção.

Quando os usuários adicionarem um documento à biblioteca de sites subjacentes do SharePoint da equipe, o documento receberá o rótulo de retenção atribuído por padrão. Os usuários podem alterar o rótulo, se necessário. Quando um usuário compartilha um documento para fora da organização, a DLP verificará se há um rótulo atribuído e agirá se houver uma política DLP que corresponda ao rótulo. A DLP também procurará outras políticas que correspondam, como proteger arquivos com números de cartão de crédito, caso este tipo de política estiver configurado. 

## <a name="retention-labels-for-your-underlying-sharepoint-sites"></a>Rótulos de retenção para sites subjacentes do SharePoint

Há três fases para criar e atribuir rótulos de retenção a sites subjacentes do SharePoint.
  
### <a name="step-1-determine-the-retention-label-names"></a>Etapa 1: determinar os nomes dos rótulos de retenção

Nessa fase, você determina os nomes dos rótulos de retenção para os quatro níveis de proteção de informações aplicados a sites subjacentes do SharePoint. A tabela a seguir lista os nomes recomendados para cada nível.
  
|**nível de proteção de sites subjacentes do SharePoint**|**Nome do rótulo**|
|:-----|:-----|
|Linha de base público  <br/> |Público interno  <br/> |
|Linha de base privado  <br/> |Private  <br/> |
|Confidencial  <br/> |Confidencial  <br/> |
|Altamente Confidencial  <br/> |Altamente Confidencial  <br/> |
   
### <a name="step-2-create-the-retention-labels"></a>Fase 2: criar os rótulos de retenção

Nesta fase, você cria e publica seus rótulos determinados para os diferentes níveis de proteção de informações.
  
1. Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.
    
2. Na guia **Início - Conformidade do Microsoft 365** do navegador, clique em **Classificações > Rótulos**.
    
3. Clique em **Rótulos de retenção > Criar um rótulo**.
    
4. No painel **Atribuir nome ao seu rótulo**, digite o nome do rótulo e uma descrição para administradores e usuários e, em seguida, clique em **Avançar**.

5. No painel **Descritores do planejamento de arquivo**, preencha conforme necessário e clique em **Avançar**.
    
6. No painel **Configurações de rótulo**, se necessário, defina **Retenção** como **Ligado** e faça as configurações de retenção. Clique em **Avançar**.
    
7. No painel **Revise suas configurações**, clique em **Criar o rótulo**.
    
8. Para obter mais rótulos, clique em **Criar um rótulo** e repita as etapas 3-7 deste procedimento conforme necessário.
    

### <a name="publish-your-new-labels"></a>Publique seus novos rótulos

Em seguida, use estas etapas para publicar os novos rótulos de retenção.
  
1. No painel **Rótulos**, clique na guia **Rótulos de retenção** e, em seguida, clique em **Publicar rótulos**.
    
2. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
    
3. No painel **Escolher rótulos**, clique em **Adicionar**, selecione todos os quatro rótulos, clique em **Adicionar**.
    
4. Clique em **Concluído**.
    
5. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Avançar**.
    
7. No painel **Atribuir um nome à política**, digite um nome para o conjunto de rótulos em **Nome** e clique em **Avançar**.
    
8. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.

    
### <a name="step-3-apply-the-retention-labels-to-your-underlying-sharepoint-sites"></a>Etapa 3: aplicar os rótulos de retenção a sites subjacentes do SharePoint

Use estas etapas para aplicar os rótulos de retenção às pastas de documentos dos sites subjacentes do SharePoint.
  
1.  Na equipe, clique em **Arquivos** e em **Abrir no SharePoint**.

2. Na nova guia de site do SharePoint do navegador, clique em **Documentos**.
    
3. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
    
4. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
    
5. Em **Configurações – Aplicar Rótulo**, selecione o rótulo de retenção adequado e clique em **Salvar**.
    
6. Feche a guia do site do SharePoint.
    
7. Repita as etapas 1-6 para atribuir rótulos de retenção a sites subjacentes do SharePoint adicionais.
    
Esta é a configuração resultante.
  
![Rótulos de retenção para os quatro tipos de sites subjacentes do SharePoint.](../media/retention-labels.png)
  
## <a name="dlp-policies-for-your-underlying-sharepoint-sites"></a>Políticas DLP para os sites subjacentes do SharePoint

Use estas etapas para configurar uma política DLP que notifique os usuários quando eles compartilharem um documento em um site subjacente do SharePoint fora da organização.

1. Entre no [portal de conformidade do Microsoft 365](https://compliance.microsoft.com/) com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa.
    
2. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
3. No painel **Início > Prevenção de perda de dados**, clique em **Criar uma política**.
    
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e, em seguida, clique em **Avançar**.
    
5. No painel **Atribuir um nome à política**, digite o nome da política DLP de nível confidencial em **Nome** e clique em **Avançar**.
    
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
7. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
8. No painel **Personalizar o tipo de conteúdo que você deseja proteger**, clique em **Editar**.
    
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
10. No painel **Rótulos de retenção**, clique em ** Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **personalizar um tipo de conteúdo que deseja proteger**, clique em **próxima**.

13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole uma das seguintes dicas:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
  - Arquivos altamente confidenciais são protegidos com criptografia. Somente usuários externos que recebam permissões do seu departamento de TI para esses arquivos poderão lê-los.
    
    Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.
    
16. Clique em **OK**.
    
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Avançar**.
    
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
    
Estas são as configurações resultantes para equipes confidenciais.
  
![Política DLP para equipe confidencial usando o rótulo de retenção Confidencial](../media/retention-labels-sensitive-dlp.png)
  
Depois, siga estas etapas para configurar uma política DLP que impeça os usuários de compartilhar um documento em um site subjacente do SharePoint fora da organização.
  
1. Na nova guia **conformidade do Microsoft 365** em seu navegador, clique em**Políticas > Prevenção de perda de dados**.
    
2. No painel **Prevenção de perda de dados**, clique em **Criar uma política**.
    
3. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
    
4. No painel **Atribuir um nome à política**, digite o nome da política DLP de nível altamente confidencial em **Nome** e clique em **Avançar**.
    
5. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
    
6. Na lista de locais, desabilite os locais **email do Exchange**, **contas do OneDrive** e **Mensagens do canal e do chat do Teams** e, em seguida, clique em **Avançar**.
    
7. No painel **Personalizar os tipos de informações confidenciais que deseja proteger**, clique em **Editar**.
    
8. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e, em seguida, clique em **Rótulos de retenção**.
    
9. No painel **Rótulos de retenção**, clique em **Adicionar**, selecione o rótulo **Altamente Confidencial**, clique em **Adicionar** e, em seguida, clique em **Concluído**.
    
10. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
    
12. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
    
13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
    
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
    
15. Na caixa de texto, digite ou cole o seguinte:
    
  - Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
    
    Como alternativa, digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.
    
16. Clique em **OK**.
    
17. Na caixa **O que você deseja fazer se detectarmos informações confidenciais?**, em **Detectar quando uma quantidade específica de informações confidenciais está sendo compartilhada ao mesmo tempo**, clique em **Restringir acesso ou criptografar o conteúdo** e, em seguida, clique em **Avançar**.
    
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Sim** para ativá-la imediatamente e clique em **Avançar**.
    
19. No painel **Examine as configurações**, clique em **Criar** e em **Fechar**.
    
Esta é a configuração resultante para a equipe de alta confidencialidade.
  
![Política DLP para uma equipe de alta confidencialidade usando o rótulo de retenção Altamente Confidencial](../media/retention-labels-highly-confidential-dlp.png)
  
## <a name="next-step"></a>Próxima etapa

[Proteger arquivos em equipes com rótulos de confidencialidade](deploy-teams-sensitivity-labels.md)
    
## <a name="see-also"></a>Confira também

[Proteger arquivos no Microsoft Teams](secure-files-in-teams.md)
  
[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


