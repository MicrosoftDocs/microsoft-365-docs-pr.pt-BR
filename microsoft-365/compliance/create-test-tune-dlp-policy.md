---
title: Criar, testar e ajustar uma política DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
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
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: Neste artigo, você aprenderá como criar, testar e ajustar uma política de DLP de acordo com suas necessidades organizacionais.
ms.openlocfilehash: 3b7f74605c8a825bb03244f3a861ad3cca8f550d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572568"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Criar, testar e ajustar uma política DLP

A prevenção de perda de dados (DLP) ajuda a evitar o compartilhamento não intencional ou acidental de informações confidenciais.

O DLP examina mensagens de e-mail e arquivos para obter informações confidenciais, como um número de cartão de crédito. Usando dLP, você pode detectar informações confidenciais e tomar medidas como:

- Registre o evento para fins de auditoria
- Exiba um aviso para o usuário final que está enviando o e-mail ou compartilhando o arquivo
- Bloqueie ativamente o compartilhamento de e-mails ou arquivos de ocorrer

## <a name="permissions"></a>Permissões

Os membros da sua equipe de conformidade que irão criar políticas de DLP precisam de permissões ao Centro de Conformidade. Por padrão, seu administrador inquilino terá acesso pode dar aos oficiais de conformidade e outras pessoas acesso. Siga estas etapas:
  
1. Crie um grupo no Microsoft 365 e adicione os responsáveis pela conformidade.
    
2. Criar um grupo de funções na página **Permissões** do Centro de Conformidade &amp; Segurança. 

3. Ao criar o grupo de funções, use a seção **Escolher funções** para adicionar a seguinte função ao grupo de funções: **DLP Compliance Management**.
    
4. Use a seção **Escolher membros** para adicionar o grupo Microsoft 365 que você criou anteriormente ao grupo de função.

Use a função **De gerenciamento de conformidade DLP somente para** criar grupo de papéis com privilégios somente de visualização para as políticas DLP e relatórios DLP.

Para saber mais, consulte [Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Essas permissões são necessárias para criar e aplicar uma política DLP para não aplicar políticas.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Como as informações confidenciais são detectadas pela DLP

O DLP encontra informações confidenciais por correspondência de padrões de expressão regular (RegEx), em combinação com outros indicadores, como a proximidade de certas palavras-chave aos padrões correspondentes. Por exemplo, um número de cartão de crédito VISA tem 16 dígitos. Mas, esses dígitos podem ser escritos de diferentes maneiras, como 1111-1111-1111, 1111 1111 1111 1111, ou 11111111111.

Qualquer string de 16 dígitos não é necessariamente um número de cartão de crédito, pode ser um número de bilhete de um sistema de help desk, ou um número de série de um pedaço de hardware. Para dizer a diferença entre um número de cartão de crédito e uma sequência inofensiva de 16 dígitos, um cálculo é realizado (checksum) para confirmar que os números correspondem a um padrão conhecido das várias marcas de cartão de crédito.

Se a DLP encontrar palavras-chave como "VISA" ou "AMEX", valores de data próximas que podem ser a data de validade do cartão de crédito, a DLP também usa esses dados para ajudá-lo a decidir se a string é um número de cartão de crédito ou não.

Em outras palavras, o DLP é inteligente o suficiente para reconhecer a diferença entre essas duas sequências de texto em um e-mail:

- "Você pode me pedir um laptop novo. Use meu visa número 1111-1111-1111-1111, expirado 22/11, e me envie a data estimada de entrega quando você tiver."
- "Meu número de série do laptop é 2222-2222-2222-2222 e foi comprado em 11/2010. A propósito, meu visto de viagem já foi aprovado?

Consulte [definições de entidades de tipo](sensitive-information-type-entity-definitions.md) de informações confidenciais que explicam como cada tipo de informação é detectado.

## <a name="where-to-start-with-data-loss-prevention"></a>Por onde começar com a prevenção de perda de dados

Quando os riscos de vazamento de dados não são totalmente óbvios, é difícil descobrir onde exatamente você deve começar com a implementação de DLP. Felizmente, as políticas DLP podem ser executadas no "modo de teste", permitindo que você avalie sua eficácia e precisão antes de atuá-las.

As políticas de DLP para Exchange Online podem ser gerenciadas através do centro administrativo Exchange. Mas você pode configurar políticas DLP para todas as cargas de trabalho através do Security & Compliance Center, de modo que é isso que eu vou usar para demonstrações neste artigo. No Centro de Conformidade de segurança &, você encontrará as políticas de DLP sob a Política **de Prevenção de Perdas de**  >  **Dados**. Escolha **Criar uma política** para começar.

Microsoft 365 fornece uma série de modelos de [políticas DLP](what-the-dlp-policy-templates-include.md) que você pode usar para criar políticas. Digamos que você é um negócio australiano. Você pode filtrar os modelos na Austrália e escolher Finanças, Médica e Saúde e Privacidade.

![Opção para escolher país ou região](../media/DLP-create-test-tune-choose-country.png)

Para esta demonstração, escolherei dados pii (Informações Pessoais Identificáveis) australianos, que incluem os tipos de informações do Australian Tax File Number (TFN) e do Número da Carteira de Motorista.

![Opção para escolher um modelo de política](../media/DLP-create-test-tune-choose-policy-template.png)

Dê um nome à sua nova política DLP. O nome padrão corresponderá ao modelo de diretiva DLP, mas você deve escolher um nome mais descritivo do seu próprio, porque várias políticas podem ser criadas a partir do mesmo modelo.

![Opção para nomear sua apólice](../media/DLP-create-test-tune-name-policy.png)

Escolha os locais a que a política se aplicará. As políticas de DLP podem se aplicar a Exchange Online, SharePoint Online e OneDrive for Business. Vou deixar esta política configurada para aplicar a todos os locais.

![Opção para escolher todos os locais](../media/DLP-create-test-tune-choose-locations.png)

Na primeira Configurações de **Política,** basta aceitar os padrões por enquanto. Você pode personalizar as políticas DLP, mas os padrões são um bom lugar para começar.

![Opções para personalizar o tipo de conteúdo para proteger](../media/DLP-create-test-tune-default-customization-settings.png)

Depois de clicar em Next** você será presenteado com uma página mais **Configurações de Política** com mais opções de personalização. Para uma política que você está apenas testando, aqui é onde você pode começar a fazer alguns ajustes.

- Desliguei as dicas de política por enquanto, o que é um passo razoável a ser dados se você está apenas testando as coisas e não quer exibir nada para os usuários ainda. As dicas de política exibem avisos aos usuários de que eles estão prestes a violar uma política de DLP. Por exemplo, um usuário Outlook verá um aviso de que o arquivo que anexou contém números de cartão de crédito e fará com que seu e-mail seja rejeitado. O objetivo das dicas políticas é parar o comportamento não compatível antes que isso aconteça.
- Eu também diminuí o número de instâncias de 10 para 1, de modo que esta política detectará qualquer compartilhamento de dados pii australianos, não apenas compartilhamento em massa dos dados.
- Eu também adicionei outro destinatário ao e-mail do relatório de incidentes.

![Configurações adicionais de políticas](../media/DLP-create-test-tune-more-policy-settings.png)

Finalmente, eu configurei esta política para ser executada no modo de teste inicialmente. Observe que também há uma opção aqui para desativar dicas de política enquanto estiver no modo de teste. Isso lhe dá a flexibilidade de ter dicas de política habilitadas na política, mas depois decide se as mostra ou as suprime durante o teste.

![Opção para testar a política primeiro](../media/DLP-create-test-tune-test-mode.png)

Na tela de revisão final, clique em **Criar** para concluir a criação da política.

## <a name="test-a-dlp-policy"></a>Teste uma política DLP

Sua nova política de DLP começará a entrar em vigor em cerca de 1 hora. Você pode sentar e esperar que ele seja acionado pela atividade normal do usuário, ou você mesmo pode tentar acioná-lo. Mais cedo, vinculei-me a [definições de entidades do tipo de informações confidenciais,](sensitive-information-type-entity-definitions.md)que fornecem informações sobre como acionar partidas DLP.

Como exemplo, a política DLP que criei para este artigo detectará números de arquivos fiscais australianos (TFN). De acordo com a documentação, a partida é baseada nos seguintes critérios.

![Documentação no número do arquivo fiscal da Austrália](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Para demonstrar a detecção de TFN de forma bastante contundente, um e-mail com as palavras "Número de arquivo fiscal" e uma sequência de nove dígitos nas proximidades navegará sem problemas. A razão pela qual ele não aciona a política DLP é que a sequência de nove dígitos deve passar o cheque que indica que é um TFN válido e não apenas uma sequência inofensiva de números.

![Número de arquivo fiscal da Austrália que não passa checksum](../media/DLP-create-test-tune-email-test1.png)

Em comparação, um e-mail com as palavras "Número de arquivo fiscal" e um TFN válido que passa o checkum acionará a política. Para registro aqui, a TFN que estou usando foi tirada de um site que gera TFNs válidos, mas não genuínos. Esses sites são úteis porque um dos erros mais comuns ao testar uma política de DLP é usar um número falso que não é válido e não passará no checkum (e, portanto, não acionará a política).

![Número de arquivo fiscal da Austrália que passa o cheque](../media/DLP-create-test-tune-email-test2.png)

O e-mail do relatório de incidentes inclui o tipo de informação sensível detectada, quantas instâncias foram detectadas e o nível de confiança da detecção.

![Relatório de incidente mostrando número de arquivo fiscal detectado](../media/DLP-create-test-tune-email-incident-report.png)

Se você deixar sua política DLP no modo de teste e analisar os e-mails do relatório de incidentes, você pode começar a ter uma noção da precisão da política DLP e quão eficaz ela será quando for aplicada. Além dos relatórios de incidentes, você pode [usar os relatórios DLP](view-the-dlp-reports.md) para ver uma visão agregada das correspondências de políticas em seu inquilino.

## <a name="tune-a-dlp-policy"></a>Ajustar uma política DLP

À medida que você analisa seus hits de política, você pode querer fazer alguns ajustes na forma como as políticas se comportam. Como um exemplo simples, você pode determinar que um TFN em um e-mail não é um problema (eu acho que ainda é, mas vamos com ele por causa da demonstração), mas duas ou mais instâncias são um problema. Várias instâncias podem ser um cenário arriscado, como um funcionário enviar um e-mail para uma exportação de CSV do banco de dados de RH para uma parte externa, por exemplo, um serviço de contabilidade externo. Definitivamente algo que você prefere detectar e bloquear.

No Compliance Center você pode editar uma política existente para ajustar o comportamento.

![Opção para editar a política](../media/DLP-create-test-tune-edit-policy.png)
 
Você pode ajustar as configurações de localização para que a política seja aplicada apenas a cargas de trabalho específicas ou a sites e contas específicos.

![Opções para escolher locais específicos](../media/DLP-create-test-tune-edit-locations.png)

Você também pode ajustar as configurações da política e editar as regras para melhor atender às suas necessidades.

![Opção para editar regra](../media/DLP-create-test-tune-edit-rule.png)

Ao editar uma regra dentro de uma política DLP, você pode alterar:

- As condições, incluindo o tipo e o número de instâncias de dados confidenciais que acionarão a regra.
- As ações que são tomadas, como restringir o acesso ao conteúdo.
- Notificações do usuário, que são dicas de política que são exibidas ao usuário em seu cliente de e-mail ou navegador da Web.
- As substituições do usuário determinam se os usuários podem optar por prosseguir com seu e-mail ou compartilhamento de arquivos de qualquer maneira.
- Relatórios de incidentes, para notificar os administradores.

![Opções para editar partes de uma regra](../media/DLP-create-test-tune-editing-options.png)

Para esta demonstração, adicionei notificações de usuários à política (tenha cuidado ao fazer isso sem treinamento adequado de conscientização do usuário) e permiti que os usuários anulassem a política com uma justificativa de negócio ou sinalizando-a como um falso positivo. Você também pode personalizar o texto de dica de e-mail e política se quiser incluir qualquer informação adicional sobre as políticas da sua organização ou solicitar que os usuários entrem em contato com o suporte se eles tiverem dúvidas.

![Opções para notificações e substituições de usuários](../media/DLP-create-test-tune-user-notifications.png)

A política contém duas regras para manuseio de alto volume e baixo volume, por isso não deixe de editar ambas com as ações que você deseja. Esta é uma oportunidade de tratar os casos de forma diferente, dependendo de suas características. Por exemplo, você pode permitir substituições por violações de baixo volume, mas não permitir substituições por violações de alto volume.

![Uma regra para alto volume e uma regra para baixo volume](../media/DLP-create-test-tune-two-rules.png)

Além disso, se você quiser realmente bloquear ou restringir o acesso ao conteúdo que está violando a política, você precisa configurar uma ação sobre a regra para fazê-lo.

![Opção para restringir o acesso ao conteúdo](../media/DLP-create-test-tune-restrict-access-action.png)

Depois de salvar essas alterações nas configurações da política, também preciso retornar à página de configurações principais da política e habilitar a opção de mostrar dicas de política aos usuários enquanto a política estiver no modo de teste. Esta é uma maneira eficaz de introduzir políticas DLP para seus usuários finais, e fazer treinamento de conscientização do usuário, sem arriscar muitos falsos positivos que impactam sua produtividade.

![Opção para mostrar dicas de política no modo de teste](../media/DLP-create-test-tune-show-policy-tips.png)

No lado do servidor (ou lado da nuvem, se preferir), a alteração pode não ter efeito imediatamente, devido a vários intervalos de processamento. Se você está fazendo uma mudança de política DLP que exibirá novas dicas de política para um usuário, o usuário pode não ver as alterações entrar em vigor imediatamente em seu Outlook cliente, que verifica mudanças de política a cada 24 horas. Se você quiser acelerar as coisas para testes, você pode usar esta correção de registro para [limpar o último carimbo de tempo de download da chave PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook baixará as informações mais recentes da política da próxima vez que reiniciar e começar a compor uma mensagem de e-mail.

Se você tiver dicas de política habilitadas, o usuário começará a ver as dicas em Outlook, e poderá relatar falsos positivos para você quando eles ocorrem.

![Dica de política com opção de denunciar falso positivo](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Investigue falsos positivos

Os modelos de diretiva DLP não são perfeitos diretamente para fora da caixa. É provável que você encontre alguns falsos positivos ocorrendo em seu ambiente, e é por isso que é tão importante facilitar seu caminho para uma implantação de DLP, tendo tempo para testar e ajustar adequadamente suas políticas.

Aqui está um exemplo de falso positivo. Este e-mail é inofensivo. O usuário está fornecendo seu número de telefone celular para alguém, e incluindo sua assinatura de e-mail.

![E-mail mostrando informações falsas positivas](../media/DLP-create-test-tune-false-positive-email.png)
 
Mas o usuário vê uma dica de política avisando que o e-mail contém informações confidenciais, especificamente, um número de carteira de motorista australiano.

![Opção para denunciar falso positivo na dica de política](../media/DLP-create-test-tune-policy-tip-closeup.png)

O usuário pode denunciar o falso positivo, e o administrador pode investigar por que ocorreu. No e-mail do relatório do incidente, o e-mail é sinalizado como um falso positivo.

![Relatório de incidente mostrando falso positivo](../media/DLP-create-test-tune-false-positive-incident-report.png)

Este caso de carteira de motorista é um bom exemplo para investigar. A razão pela qual esse falso positivo ocorreu é que o tipo "Australian Driver's License" será acionado por qualquer string de 9 dígitos (mesmo uma que faz parte de uma sequência de 10 dígitos), dentro de 300 caracteres perto das palavras-chave "Sydney nsw" (não sensível ao caso). Então é acionado pelo número de telefone e assinatura de e-mail, só porque o usuário está em Sydney.


Uma opção é remover o tipo de informações da carteira de motorista australiana da apólice. Está lá porque faz parte do modelo de política da DLP, mas não somos forçados a usá-lo. Se você só está interessado em números de arquivos fiscais e não em carteiras de motorista, você pode simplesmente removê-lo. Por exemplo, você pode removê-lo da regra de baixo volume na apólice, mas deixá-lo na regra de alto volume para que as listas de várias carteiras de motorista ainda sejam detectadas.
 
Outra opção é aumentar a contagem de ocorrências, de modo que um baixo volume de carteiras de motorista só seja detectado quando houver várias instâncias.

![Opção para editar a contagem de instâncias](../media/DLP-create-test-tune-edit-instance-count.png)

Além de alterar a contagem de instâncias, você também pode ajustar a precisão da partida (ou nível de confiança). Se o seu tipo de informação sensível tiver vários padrões, você pode ajustar a precisão da correspondência em sua regra, de modo que sua regra corresponda apenas a padrões específicos. Por exemplo, para ajudar a reduzir os falsos positivos, você pode definir a precisão da correspondência de sua regra para que ela corresponda apenas ao padrão com o nível mais alto de confiança. Para obter mais informações sobre os níveis de confiança, consulte [Como usar o nível de confiança para ajustar suas regras](data-loss-prevention-policies.md#match-accuracy).

Finalmente, se você quiser ficar ainda mais avançado, você pode personalizar qualquer tipo de informação sensível - por exemplo, você pode remover "Sydney NSW" da lista de palavras-chave para o [número da carteira de motorista da Austrália](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), para eliminar o falso positivo acionado acima. Para aprender a fazer isso usando XML e PowerShell, consulte [personalizando um tipo de informação sensível incorporada](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-on-a-dlp-policy"></a>Ligue uma política DLP

Quando você está feliz que sua política de DLP está detectando com precisão e eficácia tipos de informações confidenciais, e que seus usuários finais estão prontos para lidar com as políticas que estão em vigor, então você pode habilitar a política.

![Opção para ativar a política](../media/DLP-create-test-tune-turn-on-policy.png)
 
Se você estiver esperando para ver quando a política entrará em vigor, [Conexão ao PowerShell do Centro de Conformidade de Segurança &](/powershell/exchange/connect-to-scc-powershell) e execute o [cmdlet Get-DlpCompliancePolicy](/powershell/module/exchange/get-dlpcompliancepolicy) para ver o DistributionStatus.

![Ccdlet em execução no PowerShell](../media/DLP-create-test-tune-PowerShell.png)

Depois de ligar a política do DLP, você deve executar alguns testes finais por conta própria para garantir que as ações políticas esperadas estejam ocorrendo. Se você está tentando testar coisas como dados de cartão de crédito, existem sites on-line com informações sobre como gerar cartão de crédito de amostra ou outras informações pessoais que passarão cheques e acionarão suas apólices.

As políticas que permitem substituições de usuários apresentarão essa opção ao usuário como parte da dica da política.

![Dica de política que permite a substituição do usuário](../media/DLP-create-test-tune-override-option.png)

As políticas que restringem o conteúdo apresentarão o aviso ao usuário como parte da dica da política e os impedirão de enviar o e-mail.

![Dica de política de que o conteúdo é restrito](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Resumo

As políticas de prevenção de perda de dados são úteis para organizações de todos os tipos. Testar algumas políticas de DLP é um exercício de baixo risco devido ao controle que você tem sobre coisas como dicas de política, substituições de usuários finais e relatórios de incidentes. Você pode testar silenciosamente algumas políticas de DLP para ver que tipo de violações já estão ocorrendo em sua organização e, em seguida, criar políticas com baixas taxas falsas positivas, educar seus usuários sobre o que é permitido e não permitido e, em seguida, implementar suas políticas de DLP para a organização.