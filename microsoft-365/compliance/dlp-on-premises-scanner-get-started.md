---
title: Obter o scanner local de prevenção contra perda de dados do Microsoft 365 (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: Configurar o scanner local de prevenção contra perda de dados do Microsoft 365
ms.openlocfilehash: 7e190a1d6e902af3406f7e8f317efe80e825e7f2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917827"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>Obter o scanner local de prevenção contra perda de dados (visualização)

Este artigo apresenta os pré-requisitos e a configuração do scanner local de prevenção de perda de dados do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de obter o scanner DLP local, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos. Para participar da visualização, a conta de administrador que configura as regras de DLP deve atribuir uma das seguintes licenças:

- Microsoft 365 E5
- Conformidade do Microsoft 365 E5
- Microsoft 365 E5 Proteção da Informação & Governança 


Para obter os detalhes completos do licenciamento, consulte: [Orientação de licenciamento do Microsoft 365 para segurança & conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="permissions"></a>Permissões


Os dados do scanner DLP local podem ser visualizados no [Explorador de atividades](data-classification-activity-explorer.md). Há quatro funções que concedem permissão para o explorador de atividades, a conta que você usa para acessar os dados deve ser um membro de qualquer uma delas.

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade

### <a name="dlp-on-premises-scanner-prerequisites"></a>Pré-requisitos do scanner DLP local

- O scanner de Proteção de Informações do Azure (AIP) implementa a correspondência e a aplicação de políticas de DLP. O scanner é instalado como parte do cliente AIP, portanto, sua instalação deve atender a todos os pré-requisitos para AIP, o cliente AIP e o scanner de etiquetagem unificado AIP.
- Implantar o cliente e scanner AIP. Para mais informações [Instalar o cliente de rotulagem unificada AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) e [], consulte [Configurando e instalando o scanner de rotulagem unificada da Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install).
- Deve haver pelo menos um rótulo e uma política publicados no locatário, mesmo se todas as suas regras de detecção forem baseadas apenas em tipos de informações confidenciais.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Implantar o scanner DLP local

1. Seguir os procedimentos em [Instalar o cliente de rotulagem unificada AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Segui os procedimentos em [Configurando e instalando o scanner de rotulagem unificada do Proteção de Informações do Azure](/azure/information-protection/deploy-aip-scanner-configure-install) para concluir a instalação do scanner.
    1. Configuração dos trabalhos de descoberta de rede é uma etapa opcional. Você pode ignorá-lo e definir repositórios específicos a serem verificados em seu trabalho de exame de conteúdo.
    2. Você deve criar um trabalho de exame de conteúdo e especificar os repositórios que hospedam arquivos que precisam ser avaliados pelo mecanismo DLP.
    3. Habilitar as regras de DLP no trabalho de exame de conteúdo criado e defina a opção **Aplicar** como **Desligado**, a menos que você queira prosseguir diretamente para o estágio de aplicação de DLP.
3. Verificar se o trabalho de exame de conteúdo está atribuído ao cluster correto. Se você ainda não criou um trabalho de exame de conteúdo, crie um novo e atribua-o ao cluster que contém os nós do scanner que executam a versão de visualização pública.

4. Conecte-se à extensão [Proteção de Informações do Azure no portal do Azure](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) e adicione seus repositórios ao trabalho de exame de conteúdo que executará a verificação.

5. Siga um destes procedimentos para executar seu exame:
    1. conjunto o programação do scanner
    1. use a opção manual **Digitalizar Agora** no portal
    1. ou execute **Iniciar-AIPScan** Windows PowerShell cmdlet

   > [!IMPORTANT]
   > Lembre-se de que o scanner executa uma varredura delta do repositório por padrão e os arquivos que já foram varridos no ciclo de exame anterior serão ignorados, a menos que o arquivo seja alterado ou você inicie uma nova varredura completa. A nova verificação completa pode ser iniciada usando a opção **Verificar novamente todos os arquivos** na IU ou executando **Iniciar-AIPScan-Redefinir**.

6.  Abra a [Página de prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies) no Centro de conformidade do Microsoft 365.

7. Escolher **Criar política** e criar uma política DLP de teste. Consulte [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md) se precisar de ajuda para criar uma política. Certifique-se de executá-lo em teste até que você se sinta confortável com este recurso. Usar estes parâmetros para sua política:
    1. Defina o escopo da regra de varredura local do DLP para locais específicos, se necessário. Se você definir o escopo **loalização** para **Todos**, todos os arquivos verificados pelo scanner estarão sujeitos à correspondência e aplicação da regra DLP.
    1. Ao especificar os locais, você pode usar a lista de exclusão ou inclusão. Durante a visualização pública, você não pode definir os dois conjuntos. Você pode definir que a regra é relevante apenas para caminhos que correspondem a um dos padrões listados na lista de inclusão ou, todos os arquivos, exceto os arquivos que correspondem ao padrão listado na lista de inclusão. Nenhum caminho local é suportado. Aqui estão alguns exemplos de caminhos válidos:
      - \\\\servidor\compartilhamento
      - \\\server\share\folder1\subfolderabc
      - \*\\pasta1
      - \*secret\*.docx
      - \*Secreta\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Aqui estão alguns exemplos de uso de valores inaceitáveis:
      - \*
      - \*\\a.
      - Aaa
      - c:\
      - C:\teste

> [!IMPORTANT]
> A lista de exclusão tem precedência sobre a lista de inclusões.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>Visualização de alertas de scanner locais de DLP no painel de gerenciamento de Alertas de DLP

1. Abra a [Página de prevenção de perda de dados](https://compliance.microsoft.com/datalossprevention?viewid=policies) no Centro de Conformidade do Microsoft 365 e selecione **Alertas**.

2. Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do Ponto de extremidade.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>Visualização do scanner DLP local no explorador de atividades e registro de auditoria

> [!NOTE]
> O verificador local requer que a auditoria esteja habilitada. No Microsoft 365, a auditoria é habilitada por padrão.

1. Abra a [Página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) para seu domínio no Centro de Conformidade do Microsoft 365 e selecione explorador de Atividades.

2. Consulte os procedimentos em [Introdução ao explorador de Atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados para os locais do scanner local.

3. Abra o [Registro de Auditoria no centro de Conformidade](https://security.microsoft.com/auditlogsearch). Durante a visualização pública, as correspondências de regras de DLP estão disponíveis na IU do log de Auditoria ou acessíveis por [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) Windows PowerShell 


## <a name="next-steps"></a>Próximas etapas
Agora que implantou uma política de teste para locais DLP locais e pode visualizar os dados de atividade no Explorador de atividades, você está pronto para passar para a próxima etapa, onde criará políticas DLP que protegem seus itens confidenciais.

- [Usando DLP local (visualização)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Confira também

- [Saiba mais sobre o scanner local DLP (visualização)](dlp-on-premises-scanner-learn.md)
- [Use o scanner local DLP (visualização)](dlp-on-premises-scanner-use.md)
- [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)