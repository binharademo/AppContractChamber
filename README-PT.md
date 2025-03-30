# Câmara de Contratos - Documentação Técnica

## Visão Geral do Aplicativo

Câmara de Contratos é uma aplicação móvel multiplataforma desenvolvida para gerenciar, visualizar e assinar contratos digitalmente. O aplicativo permite que usuários criem, compartilhem, assinem e gerenciem contratos de forma segura e eficiente, eliminando a necessidade de documentos físicos e assinaturas em papel.

## Período de Desenvolvimento

- **Data de Início:** Junho de 2020
- **Data de Conclusão:** Junho de 2020

## Linguagens de Programação

- **C#**: Linguagem principal utilizada para o desenvolvimento do aplicativo
- **XAML**: Utilizada para definição das interfaces de usuário

## Tecnologias Principais

- **Xamarin.Forms**: Framework para desenvolvimento de aplicativos móveis multiplataforma
- **Prism**: Framework MVVM para Xamarin.Forms que facilita o desenvolvimento de aplicativos testáveis e de fácil manutenção
- **Microsoft AppCenter**: Utilizado para monitoramento de erros e análise de uso
- **ASP.NET Core 2.0**: Utilizado para o backend (API)
- **Swagger/OpenAPI**: Utilizado para documentação e geração de clientes da API

## Plataformas Suportadas

- **Android**
- **iOS**
- **UWP (Universal Windows Platform)**

## Arquitetura do Aplicativo

O aplicativo segue o padrão de arquitetura MVVM (Model-View-ViewModel), implementado através do framework Prism, com a seguinte estrutura:

### Estrutura do Projeto

1. **AppCamaraDeContratos**: Projeto principal Xamarin.Forms
   - **AppCamaraDeContratos.Android**: Projeto específico para Android
   - **AppCamaraDeContratos.iOS**: Projeto específico para iOS
   - **AppCamaraDeContratos.UWP**: Projeto específico para Windows

2. **AppCamaraPrism**: Projeto alternativo utilizando Prism Framework
   - **AppCamara**: Implementação principal com Prism
   - **AppCamara.Shared**: Código compartilhado entre plataformas
   - **AppCamaraLib.Shared**: Bibliotecas compartilhadas

3. **Testes**
   - **XUnitTestModel**: Testes unitários para os modelos
   - **XUnitTestProject1**: Testes unitários adicionais

### Camadas da Aplicação

1. **Models**: Define as entidades de negócio
   - Contrato
   - Signatario
   - Assinantes
   - ContratoFinalizado
   - Indicacao

2. **ViewModels**: Implementa a lógica de apresentação
   - BaseViewModel: Classe base que implementa INotifyPropertyChanged
   - ViewModels específicos para cada funcionalidade

3. **Views**: Define as interfaces de usuário
   - Páginas para cadastro de usuário
   - Páginas para visualização de contratos
   - Páginas para assinatura de contratos
   - Páginas para gerenciamento de perfil

4. **Services**: Implementa a lógica de negócios e comunicação com APIs
   - MockDataStore: Armazenamento de dados simulado para desenvolvimento
   - AppCenterMethod: Integração com Microsoft AppCenter para monitoramento

## Banco de Dados

O aplicativo utiliza:
- **Armazenamento local**: Para dados temporários e cache
- **API REST**: Para persistência de dados no servidor

Não há evidência de uso direto de um banco de dados local como SQLite, sugerindo que a maioria dos dados é obtida e persistida através da API.

## Camada de Persistência

- **REST API**: O aplicativo se comunica com um backend através de uma API REST documentada com Swagger
- **Serialização JSON**: Utiliza Newtonsoft.Json para serialização/deserialização de dados
- **Armazenamento em memória**: Para dados temporários durante a execução do aplicativo

## APIs e Integrações

- **API de Contratos**: API REST para gerenciamento de contratos, usuários e assinaturas
- **API de CEP**: Integração para busca de endereços a partir do CEP
- **Microsoft AppCenter**: Para telemetria e monitoramento de erros

## Bibliotecas Utilizadas

### Principais Pacotes NuGet:

- **Xamarin.Forms (4.7.0.968)**: Framework principal para UI multiplataforma
- **Prism.Unity.Forms (7.2.0.1422)**: Implementação MVVM e injeção de dependência
- **Newtonsoft.Json (12.0.3)**: Serialização e deserialização JSON
- **Xamarin.Essentials (1.5.3.2)**: APIs essenciais para acesso a recursos do dispositivo
- **Xam.Plugin.Media (5.0.1)**: Acesso à câmera e galeria de fotos
- **Plugin.Permissions (6.0.1)**: Gerenciamento de permissões
- **Microsoft.AppCenter (3.2.2)**: Telemetria e monitoramento
- **Xamarin.Forms.PinchZoomImage (1.0.0)**: Funcionalidade de zoom em imagens

## Padrões de Programação

- **MVVM (Model-View-ViewModel)**: Padrão arquitetural principal
- **Dependency Injection**: Implementado através do Prism.Unity
- **Repository Pattern**: Para acesso a dados
- **Command Pattern**: Para binding de comandos na UI
- **Observer Pattern**: Implementado através de INotifyPropertyChanged

## Metodologia de Testes

- **Testes Unitários**: Implementados com XUnit
- **Testes Manuais**: Evidências de testes manuais em dispositivos iOS (documentados em DadosTestes.txt)
- **Mock Data**: Utilização de dados simulados para testes

## Funcionalidades Principais

1. **Autenticação e Registro de Usuários**
   - Login/Logout
   - Registro de novos usuários
   - Recuperação de senha
   - Validação via SMS

2. **Gerenciamento de Contratos**
   - Criação de novos contratos
   - Visualização de contratos pendentes
   - Visualização de contratos finalizados
   - Adição de signatários

3. **Assinatura Digital**
   - Visualização de documentos para assinatura
   - Assinatura digital de contratos
   - Verificação de signatários

4. **Gerenciamento de Perfil**
   - Visualização e edição de dados pessoais
   - Alteração de senha
   - Upload de documentos e fotos

5. **Indicação de Amigos**
   - Sistema de convites para novos usuários

## Qualidade do Código

### Pontos Fortes

1. **Organização Estruturada**: O código segue uma estrutura clara e organizada, com separação adequada de responsabilidades.

2. **Uso de Padrões**: Implementação consistente do padrão MVVM, facilitando manutenção e testabilidade.

3. **Multiplataforma**: Desenvolvimento eficiente para múltiplas plataformas com compartilhamento de código.

4. **Documentação da API**: API bem documentada usando Swagger/OpenAPI.

5. **Tratamento de Erros**: Implementação de monitoramento de erros com AppCenter.

6. **UI Consistente**: Interface de usuário consistente com padrões visuais bem definidos.

### Áreas para Melhoria

1. **Modelos Simplificados**: Os modelos encontrados são bastante simplificados, podendo ser expandidos para maior robustez.

2. **Testes Automatizados**: Embora existam projetos de teste, a cobertura poderia ser ampliada.

3. **Documentação de Código**: Comentários e documentação inline poderiam ser mais abrangentes.

## Segurança

- **Autenticação via Token**: Implementação de autenticação baseada em token
- **Validação de Usuário**: Processo de validação de usuário via SMS
- **Verificação de Identidade**: Upload de documentos para verificação de identidade

## Conclusão

O aplicativo Câmara de Contratos é uma solução completa para gerenciamento e assinatura digital de contratos, desenvolvida com tecnologias modernas e seguindo boas práticas de desenvolvimento. A arquitetura MVVM com Prism proporciona uma base sólida para manutenção e expansão, enquanto o uso do Xamarin.Forms permite alcançar múltiplas plataformas com uma única base de código.

O aplicativo demonstra um bom equilíbrio entre funcionalidade, usabilidade e segurança, oferecendo uma alternativa digital eficiente para processos tradicionais de assinatura de contratos em papel.
