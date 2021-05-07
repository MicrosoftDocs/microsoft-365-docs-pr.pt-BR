---
title: Saiba mais sobre verificação local de prevenção contra perda de dados do Microsoft 365 (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: O verificação local de prevenção contra perda de dados do Microsoft 365 estende o monitoramento de atividades de arquivo e ações de proteção para esses arquivos para compartilhamentos locais de arquivos, pastas e bibliotecas de documentos do SharePoint. Os arquivos são verificados e protegidos pelo verificador de Proteção de Informações do Azure (AIP)
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114159"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Saiba mais sobre a verificação local de prevenção contra perda de dados do Microsoft 365 (visualização)

A verificação local de prevenção contra perda de dados da Microsoft faz parte do conjunto de recursos de prevenção contra perda de dados (DLP) do Microsoft 365 que você pode usar para descobrir e proteger itens confidenciais em todos os serviços do Microsoft 365. Para obter mais informações sobre todas as ofertas de DLP da Microsoft, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md).

A **verificação local DLP** rastreia os dados em repouso no local em compartilhamentos de arquivos, bibliotecas de documentos e pastas de documentos para itens confidenciais do Microsoft Office SharePoint Online que, se vazados, representariam um risco para sua organização ou representariam um risco de violação da política de conformidade. Isso dá a você a visibilidade e o controle necessários para garantir que itens confidenciais sejam usados e protegidos corretamente, e para ajudar a evitar comportamentos de risco que possam comprometê-los. O verificação DLP local detecta informações confidenciais usando os tipos [interno](sensitive-information-type-entity-definitions.md) ou [informações confidenciais personalizadas](create-a-custom-sensitive-information-type.md), [rótulos de confidencialidade](sensitivity-labels.md) ou propriedades de arquivo. As informações sobre o que os usuários estão fazendo com itens confidenciais se tornam visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você pode impor ações de proteção para estes itens por meio de [políticas DLP](create-test-tune-dlp-policy.md).

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>A verificação DLP local conta com o verificador de Proteção de Informações do Microsoft Azure

A verificação DLP local conta com uma implementação completa do verificador de Proteção de Informações do Microsoft Azure (AIP) para monitorar, rotular e proteger itens confidenciais. Se não estiver familiarizado com o verificador AIP, recomendamos fortemente que você se familiarize com ele. Veja estes artigos:

- [O que é a Proteção de Informações do Microsoft Azure](/azure/information-protection/what-is-information-protection)
- [O que é a verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner)
- [Requisitos para instalar e implementar a verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-prereqs)
- [Tutorial: Instalando a verificação de rotulagem unificada da Proteção de Informações do Azure (AIP)](/azure/information-protection/tutorial-install-scanner)
- [Configurando e Instalando a verificação de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Cliente de rotulagem unificada da Proteção de Informações do Azure - Versão do histórico de lançamento e política de suporte](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>Ações da verificação DLP local

A verificação DLP local detecta arquivos por um desses quatro métodos:

- tipos de informações confidenciais
- rótulos de confidencialidade
- extensão do arquivo
- propriedades de documentos personalizados apenas em arquivos do Office 

Quando um arquivo detectado representa um risco potencial se vazou ou violou uma política de conformidade, a verificação DLP local pode tomar uma dessas quatro ações.

|Ação |Descrição  |
|---------|---------|
|**Bloquear o acesso destas pessoas aos arquivo armazenado na  verificação local - Todos** | Quando aplicada, essa ação bloqueia o acesso para todas as contas, exceto para o proprietário do conteúdo, para a última conta que modificou o item e para o administrador. Ele faz isso removendo todas as contas a partir das permissões NTFS/SharePoint no nível do arquivo, exceto a do proprietário do arquivo, proprietário do repositório (estabelecido em [Definir proprietário do repositório](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) configurado no trabalho de verificação de conteúdo), do último modificador (pode ser identificado apenas no Microsoft Office SharePoint Online) e do administrador. A conta do verificador também recebe os direitos FC no arquivo.|
|**Bloquear o acesso destas pessoas aos arquivo armazenado na  verificação local - bloquear todo o acesso (público) da organização**    |Quando imposta, esta ação remove a **_Todos_*_, _*_NT AUTHORITY\authenticated users_*_, e _*_Usuários de Domínio_** SIDs a partir da lista de controle de acesso de arquivos (ACL). Somente usuários e grupos que foram explicitamente direitos concedidos para o arquivo ou pasta pai poderão acessar o arquivo.|
|**Definir as permissões no arquivo**|Quando imposta, esta ação força o arquivo a herdar as permissões da sua pasta pai. Seja o padrão, essa ação só será aplicada se as permissões na pasta pai forem mais restritivas do que as permissões que já estão no arquivo. Por exemplo, se a LCA no arquivo estiver definida para permitir apenas **_usuários específicos_*_ e a pasta pai estiver configurada para permitir um grupo de _*_Usuários do Domínio_*_, as permissões da pasta pai não serão herdadas pelo arquivo. Você pode ignorar este comportamento selecionando a opção _* Herdar mesmo que as permissões dos pais sejam menos restritivas**.|
|**Remover o arquivo de uma localização inadequada**|Quando imposta, esta ação substitui o arquivo original por um arquivo stub com extensão .txt e coloca uma cópia do arquivo original em uma pasta de quarentena. 

## <a name="whats-different-in-the-on-premises-scanner"></a>O que há de diferente na verificação local

Existem alguns conceitos extras que você precisa estar ciente antes de mergulhar na verificação local.

### <a name="aip-repositories-and-content-scan-jobs"></a>Repositórios AIP e trabalhos de verificação de conteúdo

Você deve criar um trabalho de verificação de conteúdo AIP e identificar os repositórios que hospedam os arquivos que você deseja que sejam avaliados pelo mecanismo DLP. Certifique-se de ativar as regras DLP no trabalho de verificação de conteúdo AIP criado.

### <a name="policy-tips"></a>Dicas de política

[Dicas de políticas](use-notifications-and-policy-tips.md) não estão disponíveis na verificação local.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Exibição DLP em eventos de verificação local

Você exibindo dados de verificação DLP local no Centro de Conformidade do M365 do [explorador de atividades](data-classification-activity-explorer.md). 

## <a name="next-steps"></a>Próximas etapas

Agora que você aprendeu sobre a verificação DLP local, seus próximos passos são:

1. [Começar com a verificação DLP local](dlp-on-premises-scanner-get-started.md)
2. [Usar a verificação DLP local](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Confira também

- [Começando com a verificação local de prevenção contra perda de dados da Microsoft](dlp-on-premises-scanner-get-started.md)
- [Usar a verificação local de prevenção contra perda de dados da Microsoft](dlp-on-premises-scanner-use.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)