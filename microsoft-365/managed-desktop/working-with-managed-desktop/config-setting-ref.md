---
title: Referência de configurações configuráveis para a área de trabalho gerenciada da Microsoft
description: Definindo categorias para definições configuráveis na área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8839be023844ae4de17972790ec9d02b82c75244
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414189"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referência de configurações configuráveis-Microsoft Managed desktop

Este tópico lista as categorias de configurações que os clientes podem configurar com a área de trabalho gerenciada da Microsoft. Cada categoria de configuração inclui informações sobre requisitos, práticas recomendadas e como personalizar a categoria de configuração. 

## <a name="desktop-background-picture"></a>Imagem de fundo da área de trabalho
Você pode personalizar a imagem de plano de fundo da área de trabalho para dispositivos de área de trabalho gerenciado da Microsoft em sua organização. Você pode usá-lo para aplicar uma marca da empresa ou um marketing 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para uma imagem de plano de fundo da área de trabalho:
- Formato de arquivo de imagem-. jpg, JPEG ou. png
- Local de arquivo-host em um local de http seguro (https) confiável. 
- Não é permitido-não há suporte para locais de http e de compartilhamento de arquivos (UNC). 

### <a name="customize-and-deploy-desktop-background-picture"></a>Personalizar e implantar imagem de plano de fundo da área de trabalho

**Para adicionar uma imagem de plano de fundo da área de trabalho personalizada**
1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho **configurável** , selecione **imagem de fundo da área de trabalho**. 
4. Insira o local da imagem que você deseja usar. 
5. Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste. 

## <a name="browser-start-pages"></a>Páginas iniciais do navegador
As páginas iniciais do navegador são abertas em guias individuais quando os usuários iniciam o Microsoft Edge. Se você quiser tornar mais fácil para os usuários abrir um conjunto de sites que eles usam com frequência, adicione uma página inicial de navegador para cada site. 

### <a name="requirements"></a>Requisitos

Você deve fornecer o nome de domínio totalmente qualificado (FQDN) para sites de intranet ou Internet para as páginas iniciais do seu navegador. Se os sites internos estiverem configurados, permita que os usuários saibam que o acesso a esses sites só será permitido quando você estiver conectado à rede interna no escritório ou quando estiver conectado a uma conexão VPN. 

### <a name="customize-and-deploy-browser-start-pages"></a>Personalizar e implantar páginas iniciais do navegador

**Para adicionar uma página inicial do navegador**
1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho **configurável** , selecione **páginas iniciais do navegador**. 
4. Selecione **Adicionar página inicial**.
5. Na **página Adicionar do navegador**, digite a URL do site que você deseja usar e, em seguida, selecione **Adicionar página inicial**. 
6. Repita as etapas 1-5 para as páginas iniciais adicionais do navegador. 
7. Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.

## <a name="enterprise-mode-site-list-location"></a>Local da lista de sites do modo empresarial

Se você tiver sites e aplicativos específicos que sabe que têm problemas de compatibilidade com o Microsoft Edge, poderá usar a lista de sites do modo empresarial para que os sites sejam abertos automaticamente usando o Internet Explorer 11. Além disso, se você souber que seus sites de intranet não funcionarão corretamente com o Microsoft Edge, você pode definir todos os sites de intranet para serem abertos usando o Internet Explorer 11 automaticamente. O uso do modo empresarial significa que você pode continuar a usar o Microsoft Edge como navegador padrão e, ao mesmo tempo, garantir que seus aplicativos continuem funcionando no Internet Explorer 11. Para obter mais informações sobre as listas de sites do modo empresarial, consulte [Enterprise Mode e Enterprise Mode site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Você pode especificar um local do https://ou o local de um compartilhamento interno onde você tenha hospedado sua lista de sites do modo empresarial. 

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para o arquivo de lista de sites do modo empresarial:
- Formato de arquivo-arquivo XML que atende [aos requisitos de arquivo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Local do arquivo-arquivo host em um local interno HTTPS. 
- Não é permitido-a hospedagem em um compartilhamento de arquivo interno, como *//ShareName*, não é permitida

### <a name="best-practices"></a>Práticas recomendadas

Essas práticas recomendadas são oferecidas para ajudar os clientes a tomar decisões para modernizar sua infraestrutura de ti:
- **Escolha um número limitado de sites** – o Microsoft Managed desktop usa o Microsoft Edge como o navegador preferencial para melhorar a segurança geral da sua organização e usabilidade para seus usuários. A maioria dos sites nessa lista são aplicativos Web herdados que precisam de uma versão mais antiga de um navegador que não inclua tantos recursos de segurança. 
- **Considere uma alternativa** – considere um site diferente ou um aplicativo Web que não exija um navegador mais antigo. Ou, considere atualizar o site para que ele possa usar navegadores mais recentes. Navegadores mais recentes usam a tecnologia mais recente e ajudam a melhorar a segurança.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Personalizar e implantar o local da lista de modo de site corporativo

**Para adicionar um local de lista de modo de site corporativo**

1.  Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2.  Em **configurações**, selecione **configurável**.
3.  Em espaço de trabalho **configurável** , selecione **local da lista de sites do modo empresarial**. 
4.  Insira o local https da sua lista de sites. 
5.  Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.

## <a name="trusted-sites"></a>Sites confiáveis

Os sites confiáveis permitem que você personalize as zonas de segurança ou onde um site pode ser usado, para sites diferentes. As zonas de segurança incluem: 
- Zona 1 – zona da intranet local
- Zona 2 – zona de sites confiáveis
- Zona 3 – zona da Internet
- Zona 4 – zona de sites restritos

### <a name="requirements"></a>Requisitos

Forneça o nome de domínio totalmente qualificado (FQDN) para sites de intranet ou Internet para cada site confiável. 

### <a name="customize-and-deploy-trusted-sites"></a>Personalizar e implantar sites confiáveis

**Para adicionar um site confiável**

1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho **configurável** , selecione **sites confiáveis**e, em seguida, selecione **Adicionar site confiável**. 
4. Em **Adicionar site confiável**, digite a URL, escolha uma zona de segurança e, em seguida, selecione **Adicionar site confiável**. 
5. Repita as etapas 1-4 para cada site confiável que você deseja adicionar. 
6. Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.

**Para remover um site confiável**

1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho **configurável** , selecione **sites confiáveis**. 
4. Selecione o site que você deseja excluir e, em seguida, selecione **excluir**. 
5. Repita as etapas 1-4 para cada site confiável que você deseja excluir. 
6. Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.

## <a name="proxy"></a>Acionista
Você pode gerenciar as configurações de proxy de rede para sua organização. Adicione o seu servidor proxy e o número da porta e, em seguida, adicione suas exceções de site de proxy. A área de trabalho gerenciada da Microsoft inclui um conjunto de exceções de proxy padrão necessárias para que o serviço funcione. A lista de exclusão padrão só pode ser modificada pelo serviço de área de trabalho gerenciada da Microsoft.  Para obter mais informações, consulte [configuração de rede para a área de trabalho gerenciada da Microsoft](../get-ready/network.md). 

As exceções de site de proxy adicionadas no portal de área de trabalho gerenciada da Microsoft são adicionadas às exceções de proxy padrão incluídas no serviço de área de trabalho gerenciada da Microsoft. 

> [!NOTE]
> A atualização da lista de exceções de proxy padrão é sempre priorizada em implantações de cliente. Isso significa que sua implantação em estágios será pausada se houver uma implantação para a lista de exceções de proxy padrão.  

### <a name="requirements"></a>Requisitos

Esses requisitos devem ser atendidos para exceções de servidor proxy e site de proxy:
- Deve ser um endereço de servidor válido e um número de porta
- As URLs devem ser um site http válido 

### <a name="customize-and-deploy-proxies"></a>Personalizar e implantar proxies

**Para adicionar uma exceção de site de proxy individual**

1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho **configurável** , selecione **proxy**. 
4. Insira o **endereço** e o **número da porta** para o servidor de proxy e, em seguida, selecione **Adicionar exceção de proxy**. 
5. Insira a URL de um site http válido e, em seguida, selecione **Adicionar exceção de proxy**. 
6. Repita as etapas 1-5 para cada site confiável que você deseja adicionar. 
7. Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md) 
- [Implantar configurações configuráveis](config-setting-deploy.md)