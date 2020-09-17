---
title: Integre as permissões do ServiceNow no centro de segurança e centro de conformidade do Microsoft 365
description: Saiba como criar e acompanhar tíquetes no ServiceNow no centro de segurança e centro de conformidade do Microsoft 365.
keywords: segurança, Microsoft 365, M365, conformidade, centro de conformidade, central de segurança, ServiceNow, tíquetes, tarefas, NEVEr, conexão
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: b9e900baf02e9fc866fe6fe520ad1e40ccd565de
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950695"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integre as permissões do ServiceNow no centro de segurança e centro de conformidade do Microsoft 365

[!include[Prerelease information](../includes/prerelease.md)]

O ServiceNow é uma plataforma de computação em nuvem popular que ajuda as empresas a gerenciar fluxos de trabalho digitais para operações corporativas. A plataforma atual tem fluxos de trabalho de ti, fluxos de trabalho de funcionários e fluxos de trabalho de cliente. [Saiba mais sobre o ServiceNow](https://www.servicenow.com/)

A Microsoft fez uma parceria com o ServiceNow para tornar mais fácil para os administradores de ti gerenciar suas permissões e tarefas em ambas as plataformas. O centro de [segurança do microsoft 365](overview-security-center.md) e o [centro de conformidade da Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) estão sendo aprimorados com a capacidade de criar e controlar de forma nativa as permissões no ServiceNow.

- [**Gerenciar tíquetes do ServiceNow na central de segurança**](tickets-security-center.md)
- **Gerenciar tíquetes do ServiceNow no centro de conformidade** (em breve)

## <a name="prerequisites"></a>Pré-requisitos

Ter acesso ao centro de segurança ou ao centro de conformidade do Microsoft 365 e a uma instância do ServiceNow com:  

* Kingston ou versão superior
* Ter credenciais do administrador HI
* Ter privilégios de administrador na instância de fornecedor de destino

O ServiceNow recomenda que os usuários mantenham as configurações padrão em sua instância do ServiceNow. Ter personalizações pode causar erros ao concluir a lista de verificação de instalação e integração com a central de segurança do Microsoft 365.

## <a name="data-exchange"></a>Troca de dados

Quando você conecta o centro de segurança ou o centro de conformidade do Microsoft 365 ao ServiceNow, a Microsoft recebe os seguintes dados adicionais:

* Nome da instância do ServiceNow
* ID do cliente do ServiceNow
* Segredo do cliente do ServiceNow
* Tokens de atualização & Access

Quando você cria uma permissão do ServiceNow no centro de segurança ou centro de conformidade do Microsoft 365, os dados a seguir são enviados para o ServiceNow:

* ID de usuário que inicia a criação de tíquete
* Nome da tarefa
* Descrição da tarefa
* Priority
* Data de conclusão
* Fonte de recomendação (recomendação do usuário ou recomendação da Microsoft)
* Categoria de recomendação (dispositivos, dados, aplicativos, identidade, infraestrutura)

## <a name="connect-to-servicenow"></a>Conectar-se ao ServiceNow

Vá para [criar e acompanhar tíquetes do ServiceNow no centro de segurança do Microsoft 365](tickets-security-center.md) para saber como se conectar ao ServiceNow. A conexão com o centro de conformidade da Microsoft 365 estará disponível em breve.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Você recebe um erro na primeira etapa da lista de verificação de instalação (criação de OAuth)

**Mensagem de erro**: a operação de leitura em relação a ' oauth_entity ' do escopo ' x_mioms_m365ticket ' foi recusada devido à política de acesso entre escopos da tabela

O aplicativo presume que qualquer administrador na instância do ServiceNow possa criar e ler entidades OAuth. Esse erro pode ser causado por uma personalização na instância do ServiceNow que restringe quem pode criar ou ler entidades OAuth.

**O ServiceNow recomenda que os usuários mantenham a funcionalidade padrão.**

Defina as configurações de tabela "registros de aplicativos" como padrão:

* Rótulo = registradores de aplicativos
* Nome = oauth_entity
* Acessível a partir de = todos os escopos do aplicativo
* Caixa de seleção pode ler = marcada

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Como validar a entidade OAuth criada para o conector de conformidade de & de segurança do Microsoft 365

Vá para a tabela registros de aplicativos (**Menu > sistema OAuth > registro de aplicativo**) no ServiceNow. Encontre a entidade OAuth criada por você, com o nome que você atribuiu a ela.

### <a name="signing-in-as-the-integration-user"></a>Entrar como o usuário de integração

Antes de autorizar a conexão entre o centro de segurança do Microsoft 365 e o ServiceNow, certifique-se de usar o logon e a senha do usuário de integração criados nas etapas de instalação. Não use suas credenciais pessoais.

1. Vá para a página autorização no ServiceNow.
2. Se você estiver conectado com suas credenciais pessoais, selecione o **não é possível** vincular no canto superior direito.
3. Entre no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.  
4. Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.
5. Continue com as etapas de configuração.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Como validar o usuário de integração criado com a lista de verificação de instalação do conector de conformidade do & de segurança do Microsoft 365

Vá para a tabela usuários **(Menu > administração de usuário > usuários**) no ServiceNow e localize o usuário de integração criado por você, com o nome atribuído a ele.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Sua empresa tem o logon único habilitado, o que impede que você se conecte ao ServiceNow através da central de segurança do Microsoft 365

Se sua empresa tiver habilitado o logon único e você receber um erro ou se não tiver êxito, siga uma das duas soluções.

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>Entrar no ServiceNow como o usuário de integração

1. Volte para a página autorização no ServiceNow.
2. Selecione o **não é possível** vincular no canto superior direito.
3. Entre no ServiceNow como o usuário de integração que você criou anteriormente na lista de verificação de instalação.  
4. Selecione **permitir** na página do servicenow que pergunta se o conector de segurança + conformidade pode se conectar à sua conta do servicenow.
5. Continue com as etapas de configuração.

#### <a name="create-a-security-admin-user"></a>Criar um usuário de administrador de segurança

1. Criar um usuário com privilégios de administrador de segurança no Azure Active Directory. O usuário precisa ter o mesmo nome e endereço de email do usuário de integração que você criou na lista de verificação de instalação. Você pode remover a função de administrador de segurança após a entrada e a conexão ter sido concluída.
2. Entre no centro de segurança do Microsoft 365 como este usuário e siga as etapas de configuração.

### <a name="ip-filtering"></a>Filtragem de IP

Se você habilitou a filtragem de IP, talvez seja necessário permitir explicitamente endereços IP. Consulte [controle de acesso de endereço IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obter informações sobre como permitir intervalos IP no ServiceNow. Consulte [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obter uma lista de endereços IP para permitir.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>A instalação está concluída, mas não vê tíquetes e não pode ser compartilhada

Se as etapas de instalação e configuração tiverem sido concluídas, mas você não vir os cartões do ServiceNow na Home Page e não puder compartilhar o ServiceNow pela pontuação segura da Microsoft, verifique o status da página de provisionamento em https://security.microsoft.com/ticketProvisioning . Selecione **autorizar** e retornar para a página inicial. Os cartões devem ser exibidos.

## <a name="resources"></a>Recursos

- [Gerenciar tíquetes do ServiceNow na central de segurança](tickets-security-center.md)