---
title: Criar uma política de DLP a partir de um modelo
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 'A maneira mais fácil e mais comum para começar a usar políticas de DLP é usar um dos modelos incluídos no Office 365. '
ms.openlocfilehash: b101714190879e4bdd1090b05f94f1f36e5d8729
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595658"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Criar uma política DLP com base em um modelo

A maneira mais fácil e mais comum para começar a usar políticas de DLP é usar um dos modelos incluídos no Office 365. Você pode usar um desses modelos como está ou personalizar as regras para atender aos requisitos de conformidade específicos da sua organização.
  
O Office 365 inclui mais de 40 modelos prontos para uso que podem ajudar você a atender a uma grande variedade de necessidades comuns de regulamentação e de política de negócios. Por exemplo, existem modelos de política de DLP para:
  
- Ato Gramm-Leach-Bliley (GLBA)
    
- Padrão de Segurança de Dados da Indústria de cartões de Pagamento (PCI-DSS)
    
- Informações Pessoalmente Identificáveis nos Estados Unidos (U.S. PII)
    
- Ato do Seguro de Saúde (HIPAA) dos EUA
    
Você pode ajustar um modelo modificando uma das regras existentes ou adicionando novas. Por exemplo, você pode adicionar novos tipos de informações confidenciais a uma regra, modificar as contagens em uma regra para torná-la mais difícil ou mais fácil de disparar, permitir que as pessoas substituam as ações em uma regra fornecendo uma justificativa de negócios ou alterar para quem as notificações e os relatórios de incidentes são enviados. Um modelo de política de DLP é um ponto de partida flexível para muitos cenários de conformidade comuns.
  
Você também pode escolher o modelo Personalizado, que não tem nenhuma regra padrão, e configurar sua política de DLP do zero, para atender aos requisitos de conformidade específicos de sua organização.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Exemplo: identificar informações confidenciais em todos os sites do OneDrive for Business e restringir o acesso de pessoas de fora da sua organização

As contas do OneDrive for Business facilitam a colaboração e o compartilhamento de documentos pelas pessoas de sua organização. Mas uma preocupação comum para os responsáveis pela conformidade é que as informações confidenciais armazenadas em contas do OneDrive for Business podem ser inadvertidamente compartilhadas com pessoas de fora da organização. Uma política de DLP pode ajudar a reduzir esse risco.
  
Neste exemplo, você criará uma política de DLP que identifica os dados PII dos EUA, que inclui números de identificação de contribuinte (ITIN), números de seguridade social e números de passaporte dos EUA. Você começará usando um modelo e, em seguida, modificará o modelo para atender aos requisitos de conformidade da sua organização, especificamente:
  
- Adicione alguns tipos de informações confidenciais — números de conta de banco. e números de carteira de motorista dos EUA, para que a política de DLP proteja ainda mais seus dados confidenciais.
    
- Tornar a política mais confidencial, para que uma única ocorrência de informações confidenciais seja suficiente para restringir o acesso de usuários externos.
    
- Permitir que os usuários substituam as ações fornecendo uma justificativa de negócios ou relatando um falso positivo. Dessa forma, sua política de DLP não impedirá que as pessoas em sua organização tenham seus trabalhos concluídos, contanto que tenham uma razão comercial válida para o compartilhamento de informações confidenciais.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Criar uma política DLP com base em um modelo

1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando a sua conta corporativa ou de estudante. Agora você está no centro de conformidade com &amp; segurança do Office 365.
    
3. Na navegação \> à &amp; esquerda centro \> de conformidade de segurança \> **política** \> de **prevenção contra perda de dados** **+ criar uma política**.
    
    ![Botão criar uma política](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Escolha o modelo de política de DLP que protege os tipos de informações confidenciais que \> você precisa **seguir**.
    
    Neste exemplo, você selecionará dados de **privacidade** \> **de informações de identificação pessoal (PII) dos EUA** , porque já inclui a maioria dos tipos de informações confidenciais que você deseja proteger, você adicionará alguns mais tarde. 
    
    Quando você seleciona um modelo, pode ler a descrição à direita para saber quais tipos de informações confidenciais o modelo protege.
    
    ![Página para escolher um modelo de política de DLP](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nomeie a política \> **em seguida**.
    
6. Para escolher os locais que você deseja que a política de DLP proteja, siga um destes procedimentos:
    
  - Escolha **todos os locais no Office 365** \> **em seguida**.
    
  - Escolha **deixe-me escolher locais** \> específicos **em seguida**. Para este exemplo, escolha esta.
    
    Para incluir ou excluir um local inteiro, como todos os emails do Exchange ou todas as contas do OneDrive, altere ou desative o **status** desse local. 
    
    Para incluir apenas sites específicos do SharePoint ou contas do OneDrive for Business, altere o **status** para ativado e clique nos links em **incluir** para escolher sites ou contas específicos. Quando você aplicar uma política a um site, as regras configuradas nessa política são aplicadas automaticamente a todos os subsites do site. 
    
    ![Opções para locais onde uma política DLP pode ser aplicada](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    Neste exemplo, para proteger as informações confidenciais armazenadas em todas as contas do OneDrive for Business, desative o **status** do **email do Exchange** e dos **sites do SharePoint**e deixe o **status** em **contas do onedrive**.
    
7. Escolha **usar configurações** \> avançadas **próximo**.
    
8. Um modelo de política de DLP contém regras predefinidas com condições e ações que detectam e agem sobre tipos específicos de informações confidenciais. Você pode editar, excluir ou desativar qualquer uma das regras existentes ou adicionar novas. Quando terminar, clique em **Avançar**.
    
    ![Regras expandidas no modelo de política PII dos EUA](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    Neste exemplo, o modelo de dados PII dos EUA inclui duas regras predefinidas:
    
  - **Baixo volume de conteúdo detectado PII dos EUA** Esta regra procura arquivos que contenham entre 1 e 10 ocorrências de cada um dos três tipos de informações confidenciais (números de passaporte ITIN, SSN e U.S.), onde os arquivos são compartilhados com pessoas de fora da organização. Se for encontrado, a regra enviará uma notificação por email ao administrador principal do conjunto de sites, ao proprietário do documento e à pessoa que modificou o documento pela última vez. 
    
  - **Alto volume de conteúdo detectado PII dos EUA** Esta regra procura arquivos que contenham 10 ou mais ocorrências de cada um dos mesmos três tipos de informações confidenciais, onde os arquivos são compartilhados com pessoas de fora da organização. Se encontrado, essa ação também enviará uma notificação por email, além de restringir o acesso ao arquivo. Para o conteúdo em uma conta do OneDrive for Business, isso significa que as permissões para o documento são restritas a todos exceto o administrador principal do conjunto de sites, o proprietário do documento e a pessoa que modificou o documento pela última vez. 
    
    Para atender aos requisitos específicos da sua organização, talvez você queira tornar as regras mais fáceis de disparar, para que uma única ocorrência de informações confidenciais seja suficiente para bloquear o acesso de usuários externos. Depois de examinar essas regras, você entende que não precisa de regras de contagem baixa e alta — você precisa apenas de uma única regra que bloqueia o acesso se qualquer ocorrência de informações confidenciais for encontrada.
    
    Portanto, você expande a regra chamada **baixo volume de conteúdo detectado pela regra de exclusão de PII** \> **** dos EUA.
    
    ![Botão excluir regra](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. Agora, neste exemplo, você precisa adicionar dois tipos de informações confidenciais (números de contas bancárias dos EUA e números de carteira de motorista dos EUA), permitir que as pessoas substituam uma regra e altere a contagem para qualquer ocorrência. Você pode fazer tudo isso editando uma regra, portanto, selecione **alto volume de conteúdo detectado** \> como **regra de edição**PII dos EUA.
    
    ![Botão Editar regra](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Para adicionar um tipo de informação confidencial, na **** seção \> condições, **adicione ou altere tipos**. Em seguida, **em Adicionar ou alterar tipos** \> , escolha **Adicionar** \> selecionar **número de conta bancária dos EUA** e número \> de carteira **de motorista dos EUA** **Adicionar** \> **concluído**.
    
    ![Opção para adicionar ou alterar tipos](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Adicionar ou alterar painel de tipos](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Para alterar a contagem (o número de instâncias de informações confidenciais necessárias para acionar a regra), em **contagem** \> de instâncias, escolha o valor **mínimo** para cada tipo \> digite 1. A contagem mínima não pode estar vazia. A contagem máxima pode estar vazia; um valor **máximo** vazio é convertido em **qualquer**.
    
    Quando terminar, a contagem mínima de todos os tipos de informações confidenciais deverá ser **1** e a contagem máxima deverá ser **qualquer**. Em outras palavras, qualquer ocorrência desse tipo de informação confidencial atenderá a essa condição.
    
    ![Contagens de instância para tipos de informações confidenciais](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Para a personalização final, você não quer que suas políticas de DLP impeçam que as pessoas façam seus trabalhos quando eles tiverem uma justificativa de negócios válida ou se encontrarem um falso positivo, portanto, você deseja que a notificação do usuário inclua opções para substituir a ação de bloqueio.
    
    Na seção **notificações do usuário** , você pode ver que as notificações por email e dicas de política estão ativadas por padrão para esta regra no modelo. 
    
    Na seção **User Overrides** , você pode ver que as substituições para uma justificativa comercial estão ativadas, mas substituições para relatar falsos positivos não são. Escolha **substituir a regra automaticamente se relatá-la como falso positivo**.
    
    ![Seção de notificações do usuário e substituição de usuário](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Na parte superior do editor de regras, altere o nome dessa regra a partir do **alto volume de conteúdo que detectou o PII dos EUA** para **qualquer conteúdo detectado com o PII dos EUA** , pois ele agora é disparado por qualquer ocorrência de seus tipos de informações confidenciais. 
    
14. Na parte inferior do editor \> de regras, **salve**.
    
15. Revise as condições e ações para esta \> regra **em seguida**.
    
    À direita, observe a opção de **status** da regra. Se você desativar uma política inteira, todas as regras contidas na política também serão desativadas. No entanto, você pode desativar uma regra específica sem desativar toda a política. Isso pode ser útil quando você precisar investigar uma regra que está gerando um grande número de falsos positivos. 
    
16. Na próxima página, leia e entenda o seguinte e, em seguida, escolha se deseja ativar ou \> **testar primeiro a**regra.
    
     Depois de criar as políticas de DLP, você deve considerar a implementação gradual delas para avaliar o impacto e testar a eficácia delas antes de as impor completamente. Por exemplo, você não deseja que uma nova política de DLP bloqueie acidentalmente o acesso a milhares de documentos que as pessoas precisam para realizar o trabalho. 
    
    Se estiver criando políticas DLP com um grande impacto em potencial, é recomendável seguir esta sequência:
    
17. Iniciar no modo de teste sem Dicas de Política e, em seguida, usar os relatórios de DLP para avaliar o impacto. Você pode usar relatórios de DLP para exibir o número, o local, o tipo e a gravidade das correspondências de política. Com base nos resultados, você pode ajustar as regras conforme necessário. No modo de teste, as políticas de DLP não afetarão a produtividade das pessoas que trabalham na sua organização. 
    
18. Mover para o modo de teste com Dicas de Política e notificações para que você possa começar a ensinar os usuários sobre suas políticas de conformidade e prepará-los para as regras que serão aplicadas. Nesse estágio, você também pode pedir aos usuários para relatar falsos positivos para que você possa refinar as regras.
    
19. Ative as políticas para que as regras sejam aplicadas e o conteúdo seja protegido. Continue a monitorar os relatórios de DLP e qualquer relatório de incidente ou notificações para se certificar de que os resultados sejam os desejados. 
    
    ![Opções para usar o modo de teste e ativar a política](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Revise suas configurações para esta \> política, escolha **criar**.
    
Depois de criar e ativar uma política de DLP, ela é implantada em qualquer fonte de conteúdo que ela inclui, como sites do SharePoint Online ou contas do OneDrive for Business, onde a política começa a impor automaticamente suas regras no conteúdo.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Exibir o status de uma política de DLP

A qualquer momento, você pode exibir o status de suas políticas de DLP na página **política** , na seção **prevenção de perda de dados** do &amp; centro de conformidade de segurança. Nessa página, você encontra informações importantes, por exemplo, se uma política foi habilitada ou desabilitada com êxito e se a política está no modo de teste. 
  
Eis aqui os diferentes status e o que eles significam.
  
|**Status**|**Explicação**|
|:-----|:-----|
|**Ativando…** <br/> |A política está sendo implantada nas fontes de conteúdo incluídas. A política ainda não foi imposta para todas as fontes.  <br/> |
|**Testando, com notificações** <br/> |A política está no modo de teste. As ações em uma regra não são aplicadas, mas as correspondências de política são coletadas e podem ser visualizadas usando os relatórios de DLP. As notificações sobre correspondências de política são enviadas aos destinatários especificados.  <br/> |
|**Testando, sem notificações** <br/> |A política está no modo de teste. As ações em uma regra não são aplicadas, mas as correspondências de política são coletadas e podem ser visualizadas usando os relatórios de DLP. As notificações sobre correspondências de política não são enviadas aos destinatários especificados.  <br/> |
|**On** <br/> |A política está ativa e imposta. A política foi implantada com êxito a todas as suas fontes de conteúdo.  <br/> |
|**Desativando...** <br/> |A política está sendo removida para as fontes de conteúdo incluídas. A política ainda pode estar ativa e imposta em algumas fontes. Desativando uma política pode levar até 45 minutos.  <br/> |
|**Desabilitado** <br/> |A política não está ativa e não foi imposta. As configurações da política (fontes, palavras-chave, duração, etc.) são salvas.  <br/> |
|**Excluindo...** <br/> |A política está sendo excluída. A política não está ativa e não foi imposta. Normalmente, leva uma hora para que uma política seja delet <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Desativar uma política de DLP

Você pode editar ou desativar uma política de DLP a qualquer momento. Desativar uma política desabilita todas as regras da política.
  
Para editar ou desativar uma política de DLP, na página **** \> política, selecione a política \> de **edição**de política.
  
![Botão Editar política](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Além disso, você pode desativar cada regra individualmente editando a política e, em seguida, alternando o **status** dessa regra, conforme descrito acima. 
  
## <a name="more-information"></a>Mais informações

- [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md)
    
- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)
    
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
    
- [Inventário de tipos de informações confidenciais](what-the-sensitive-information-types-look-for.md)
    

