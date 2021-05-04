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
ms.custom:
- seo-marvel-mar2020
description: Neste artigo, você aprenderá sobre como criar políticas de DLP usando um dos modelos incluídos no Office 365.
ms.openlocfilehash: 0088381698b47b2451f52fde32716a2436e8c073
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113963"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Criar uma política DLP com base em um modelo

A maneira mais fácil e mais comum para começar a usar políticas de DLP é usar um dos modelos incluídos no Office 365. Você pode usar um desses modelos como está ou personalizar as regras para atender aos requisitos de conformidade específicos da sua organização.
  
Microsoft 365 inclui mais de 40 modelos prontos para uso que podem ajudá-lo a atender a uma ampla variedade de necessidades comuns de política regulatória e comercial. Por exemplo, existem modelos de política de DLP para:
  
- Ato Gramm-Leach-Bliley (GLBA)
    
- Padrão de Segurança de Dados da Indústria de cartões de Pagamento (PCI-DSS)
    
- Informações Pessoalmente Identificáveis nos Estados Unidos (U.S. PII)
    
- Ato do Seguro de Saúde (HIPAA) dos EUA
    
Você pode ajustar um modelo modificando uma das regras existentes ou adicionando novas. Por exemplo, você pode adicionar novos tipos de informações confidenciais a uma regra, modificar as contagens em uma regra para torná-la mais difícil ou mais fácil de disparar, permitir que as pessoas substituam as ações em uma regra fornecendo uma justificativa de negócios ou alterar para quem as notificações e os relatórios de incidentes são enviados. Um modelo de política de DLP é um ponto de partida flexível para muitos cenários de conformidade comuns.
  
Você também pode escolher o modelo Personalizado, que não tem nenhuma regra padrão, e configurar sua política de DLP do zero, para atender aos requisitos de conformidade específicos de sua organização.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Exemplo: identifique informações confidenciais em todos os OneDrive for Business sites e restrinja o acesso a pessoas fora da sua organização

OneDrive for Business contas facilitam a colaboração e o compartilhamento de documentos pelas pessoas em toda a organização. Mas uma preocupação comum para os responsáveis pela conformidade é que as informações confidenciais armazenadas em OneDrive for Business contas podem ser compartilhadas inadvertidamente com pessoas de fora da sua organização. Uma política de DLP pode ajudar a reduzir esse risco.
  
Neste exemplo, você criará uma política de DLP que identifica dados de PII dos EUA, que inclui ITIN (Números de Identificação de Contribuinte Individual), Números de Previdência Social e números de passaporte dos EUA. Você será iniciado usando um modelo e modificará o modelo para atender aos requisitos de conformidade da sua organização, especificamente:
  
- Adicione alguns tipos de informações confidenciais — números de contas bancárias dos EUA e números de carteira de motorista dos EUA — para que a política DLP proteja ainda mais os dados confidenciais.
    
- Tornar a política mais sensível, para que uma única ocorrência de informações confidenciais seja suficiente para restringir o acesso para usuários externos.
    
- Permitir que os usuários substituam as ações fornecendo uma justificativa de negócios ou relatando um falso positivo. Dessa forma, sua política de DLP não impedirá que as pessoas em sua organização tenham o trabalho feito, desde que tenham um motivo comercial válido para compartilhar as informações confidenciais.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Criar uma política DLP com base em um modelo

1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta de trabalho ou da escola. Agora você está no Centro de &amp; Conformidade de Segurança.
    
3. No Centro de Conformidade de Segurança à esquerda navegação Política de prevenção contra perda &amp; \> de \>  \> **dados** \> **+ Criar uma política**.
    
    ![Criar um botão de política](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Escolha o modelo de política de DLP que protege os tipos de informações confidenciais que você precisa de \> **Next**.
    
    Neste exemplo, você selecionará **Dados** de Informações de Identificação Pessoal \> **(PII)** dos EUA, pois já inclui a maioria dos tipos de informações confidenciais que você deseja proteger, você adicionará alguns mais tarde. 
    
    Ao selecionar um modelo, você pode ler a descrição à direita para saber quais tipos de informações confidenciais o modelo protege.
    
    ![Página para escolher um modelo de política DLP](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nomeia a política \> **Next**.
    
6. Para escolher os locais que você deseja que a política DLP proteja, faça um dos seguintes:
    
  - Escolha **Todos os locais no Office 365** \> **Próximo**.
    
  - Choose **Let me choose specific locations** \> **Next**. Para este exemplo, escolha isso.
    
    Para incluir ou excluir um local inteiro, como todos os Exchange email ou todas as contas OneDrive, alternar o **Status** desse local para cima ou para fora. 
    
    Para incluir apenas sites SharePoint ou contas OneDrive for Business, alternar o **Status** para e  clique nos links em Incluir para escolher sites ou contas específicos. Quando você aplicar uma política a um site, as regras configuradas nessa política são aplicadas automaticamente a todos os subsites do site. 
    
    ![Opções para locais onde uma política DLP pode ser aplicada](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    Neste exemplo, para proteger informações confidenciais armazenadas em todas as contas OneDrive for Business, desativar o **Status** para sites de email Exchange **e** **SharePoint** e deixar o **Status** para contas OneDrive **.**
    
7. Escolha **Usar configurações avançadas** \> **Avançar**.
    
8. Um modelo de política de DLP contém regras predefinidas com condições e ações que detectam e agem sobre tipos específicos de informações confidenciais. Você pode editar, excluir ou desativar qualquer uma das regras existentes ou adicionar novas. Quando terminar, clique em **Próximo.**
    
    ![Regras expandidas no modelo de política PII dos EUA](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    Neste exemplo, o modelo de dados PII dos EUA inclui duas regras predefinida:
    
  - **Baixo volume de conteúdo detectado PII dos EUA** Esta regra procura por arquivos que contenham entre 1 e 10 ocorrências de cada um dos três tipos de informações confidenciais (números de itin, SSN e passaporte dos EUA), onde os arquivos são compartilhados com pessoas de fora da organização. Se for encontrada, a regra enviará uma notificação por email para o administrador principal do conjunto de sites, proprietário do documento e pessoa que modificou o documento pela última vez. 
    
  - **Alto volume de conteúdo detectado pii** dos EUA Esta regra procura por arquivos que contenham 10 ou mais ocorrências de cada um dos mesmos três tipos de informações confidenciais, onde os arquivos são compartilhados com pessoas de fora da organização. Se for encontrada, essa ação também enviará uma notificação por email, além de restringir o acesso ao arquivo. Para conteúdo em uma conta OneDrive for Business, isso significa que as permissões para o documento são restritas para todos, exceto o administrador principal do conjunto de sites, o proprietário do documento e a pessoa que modificou o documento pela última vez. 
    
    Para atender aos requisitos específicos da sua organização, talvez você queira tornar as regras mais fáceis de disparar, para que uma única ocorrência de informações confidenciais seja suficiente para bloquear o acesso para usuários externos. Depois de olhar para essas regras, você entende que não precisa de regras de contagem baixa e alta— você precisa apenas de uma única regra que bloqueia o acesso se qualquer ocorrência de informações confidenciais for encontrada.
    
    Assim, você expande a regra chamada Baixo volume de conteúdo detectado regra de Exclusão **de PII** \> **dos EUA**.
    
    ![Botão Excluir regra](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. Agora, neste exemplo, você precisa adicionar dois tipos de informações confidenciais (números de conta bancária dos EUA e números de carteira de motorista dos EUA), permitir que as pessoas substituam uma regra e altere a contagem para qualquer ocorrência. Você pode fazer tudo isso editando uma regra, portanto, selecione Alto volume de conteúdo detectado regra de Edição **de PII** \> **dos EUA**.
    
    ![Botão Editar regra](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Para adicionar um tipo de  informação sensível, na seção \> **Condições, adicione ou altere tipos**. Em Seguida, **em Adicionar ou alterar tipos** escolha Adicionar selecione Número de Conta Bancária dos EUA e Número de Carteira de Motorista dos EUA \>  \>   \> **Adicionar** \> **Feito**.
    
    ![Opção para Adicionar ou alterar tipos](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Painel Adicionar ou alterar tipos](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Para alterar a contagem (o número de instâncias de informações confidenciais necessárias para disparar a regra), em **Contagem** de instâncias, escolha o valor mínimo para \> cada tipo digite  \> 1. A contagem mínima não pode estar vazia. A contagem máxima pode estar vazia; um valor **máximo** vazio convertido em **qualquer**.
    
    Quando concluída, a contagem mínima de todos os tipos de informações confidenciais deve ser **1** e a contagem máxima deve **ser qualquer**. Em outras palavras, qualquer ocorrência desse tipo de informação sensível atenderá a essa condição.
    
    ![Contagens de instância para tipos de informações confidenciais](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Para a personalização final, você não deseja que suas políticas DLP bloqueiem as pessoas de fazer seu trabalho quando elas têm uma justificativa comercial válida ou encontram um falso positivo, portanto, você deseja que a notificação do usuário inclua opções para substituir a ação de bloqueio.
    
    Na seção **Notificações do usuário,** você pode ver que as notificações por email e as dicas de política estão ativas por padrão para essa regra no modelo. 
    
    Na seção **Substituições de** usuário, você pode ver que as substituições de uma justificativa comercial estão ativas, mas as substituições para relatar falsos positivos não são. Escolha **Substituir a regra automaticamente se ela for relatada como um falso positivo**.
    
    ![Seção Notificações do usuário e Seção Substituições de usuário](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Na parte superior do editor de regras, altere o nome dessa regra do **piI** americano padrão alto volume de conteúdo detectado para Qualquer conteúdo detectado com **PII** dos EUA porque agora é disparado por qualquer ocorrência de seus tipos de informações confidenciais. 
    
14. Na parte inferior do editor de regras \> **Salvar**.
    
15. Revise as condições e ações para esta regra \> **Next**.
    
    À direita, observe a **opção Status** da regra. Se você desativar uma política inteira, todas as regras contidas na política também serão desligadas. No entanto, aqui você pode desativar uma regra específica sem desativar toda a política. Isso pode ser útil quando você precisar investigar uma regra que está gerando um grande número de falsos positivos. 
    
16. Na próxima página, leia e entenda o seguinte e escolha se deve ativar a regra ou testá-la primeiro \> **Em Seguida.**
    
     Depois de criar as políticas de DLP, você deve considerar a implementação gradual delas para avaliar o impacto e testar a eficácia delas antes de as impor completamente. Por exemplo, você não deseja que uma nova política de DLP bloqueie sem querer o acesso a milhares de documentos que as pessoas exigem para fazer seu trabalho. 
    
    Se estiver criando políticas DLP com um grande impacto em potencial, é recomendável seguir esta sequência:
    
17. Iniciar no modo de teste sem Dicas de Política e, em seguida, usar os relatórios de DLP para avaliar o impacto. Você pode usar relatórios de DLP para exibir o número, o local, o tipo e a gravidade das correspondências de política. Com base nos resultados, você pode ajustar as regras conforme necessário. No modo de teste, as políticas de DLP não afetarão a produtividade das pessoas que trabalham na sua organização. 
    
18. Mover para o modo de teste com Dicas de Política e notificações para que você possa começar a ensinar os usuários sobre suas políticas de conformidade e prepará-los para as regras que serão aplicadas. Nesse estágio, você também pode pedir aos usuários para relatar falsos positivos para que você possa refinar as regras.
    
19. A turn on the policies so that the rules are enforced and the content's protected. Continue a monitorar os relatórios de DLP e qualquer relatório de incidente ou notificações para se certificar de que os resultados sejam os desejados. 
    
    ![Opções para usar o modo de teste e ativar a política](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Revise suas configurações para esta política \> escolha **Criar**.
    
Depois de criar e ativar uma política de DLP, ela é implantada em todas as fontes de conteúdo que ela inclui, como sites do SharePoint Online ou contas OneDrive for Business, onde a política começa a impor automaticamente suas regras a esse conteúdo.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Exibir o status de uma política de DLP

A qualquer momento, você pode exibir o status  de suas  políticas de DLP na página Política na seção Prevenção contra perda de dados do Centro &amp; de Conformidade e Segurança. Nessa página, você encontra informações importantes, por exemplo, se uma política foi habilitada ou desabilitada com êxito e se a política está no modo de teste. 
  
Eis aqui os diferentes status e o que eles significam.
  
|**Status**|**Explicação**|
|:-----|:-----|
|**Ativando…** <br/> |A política está sendo implantada nas fontes de conteúdo incluídas. A política ainda não foi imposta para todas as fontes.  <br/> |
|**Testando, com notificações** <br/> |A política está no modo de teste. As ações em uma regra não são aplicadas, mas as correspondências de política são coletadas e podem ser visualizadas usando os relatórios de DLP. As notificações sobre correspondências de política são enviadas aos destinatários especificados.  <br/> |
|**Testando, sem notificações** <br/> |A política está no modo de teste. As ações em uma regra não são aplicadas, mas as correspondências de política são coletadas e podem ser visualizadas usando os relatórios de DLP. As notificações sobre correspondências de política não são enviadas aos destinatários especificados.  <br/> |
|**On** <br/> |A política está ativa e imposta. A política foi implantada com êxito a todas as suas fontes de conteúdo.  <br/> |
|**Desativando...** <br/> |A política está sendo removida para as fontes de conteúdo incluídas. A política ainda pode estar ativa e imposta em algumas fontes. Desativando uma política pode levar até 45 minutos.  <br/> |
|**Desabilitado** <br/> |A política não está ativa e não foi imposta. As configurações da política (fontes, palavras-chave, duração, etc.) são salvas.  <br/> |
|**Excluir...** <br/> |A política está sendo excluída. A política não está ativa e não foi imposta. Normalmente, uma política leva uma hora para ser delet <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Desativar uma política de DLP

Você pode editar ou desativar uma política DLP a qualquer momento. Desativar uma política desabilita todas as regras da política.
  
Para editar ou desativar uma política de DLP, na página **Política,** selecione a \> política Editar \> **política**.
  
![Botão Editar política](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Além disso, você pode desativar cada regra individualmente editando a política e, em seguida, desligando o **Status** dessa regra, conforme descrito acima. 
  
## <a name="more-information"></a>Mais informações

- [Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade](dlp-learn-about-dlp.md)
- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](protect-documents-that-have-fci-or-other-properties.md)
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
