# Scalable WYSIWYG Editor: Editor de Conteúdo Escalável e Sistema de Gerenciamento (CMS)

## Descrição do Projeto

O **Scalable WYSIWYG Editor** é uma solução completa de gerenciamento de conteúdo e documentação, centrada em um **Editor WYSIWYG (What You See Is What You Get) escalável e modular**. O projeto foi desenvolvido com uma arquitetura *full-stack* robusta, separando claramente as responsabilidades entre o Front-end (Editor) e o Backend (API) para garantir alta manutenibilidade e escalabilidade.

Este sistema é projetado para facilitar a criação, edição e organização de documentos internos, oferecendo uma experiência de usuário intuitiva e um controle de acesso rigoroso baseado em permissões.

## Arquitetura e Componentes Principais

O projeto é dividido em duas camadas principais, comunicando-se via RESTful API:

### 1. Backend (API)

Desenvolvido em **.NET 8.0 (C#)**, o backend atua como o motor de persistência e segurança do sistema.

*   **Tecnologia:** .NET 8.0 (C#)
*   **Funções Chave:**
    *   **Autenticação e Autorização:** Gerenciamento completo de usuários, incluindo login, registro e recuperação de senha. Implementação de um sistema de **controle de acesso baseado em papéis (RBAC)** para verificar o nível de permissão do usuário em cada requisição.
    *   **Persistência de Dados:** Responsável por receber, validar e armazenar de forma segura todo o conteúdo gerado pelo editor WYSIWYG.
    *   **Comunicação Bidirecional:** API RESTful para comunicação eficiente e padronizada com o Front-end, garantindo a integridade e a atualização em tempo real dos dados.

### 2. Front-end (Editor WYSIWYG)

A interface do usuário é uma aplicação web leve e responsiva, focada na experiência de edição.

*   **Tecnologias:** HTML5, CSS3, JavaScript (Vanilla JS/jQuery)
*   **Recursos do Editor:**
    *   **Edição Direta (WYSIWYG):** Utilização da propriedade `contentEditable` para permitir a edição de conteúdo diretamente na página, simulando a experiência de um processador de texto.
    *   **Modularidade de Conteúdo:** Implementação de uma classe `SimpleEditor` em JavaScript para gerenciar a adição e manipulação de blocos de conteúdo (títulos `<h2>`, parágrafos `<p>`, e blocos de código `<pre><code>`).
    *   **Estrutura de Código:** O editor é capaz de estruturar blocos de código com a sintaxe `<pre><code>...</code></pre>`, facilitando a formatação e o destaque de código.
    *   **Fluxo de Autenticação:** Páginas dedicadas para login, cadastro e recuperação de senha, integradas à API para validação de credenciais e obtenção de tokens de sessão.

## Tecnologias Utilizadas

| Categoria | Tecnologia | Versão/Framework | Propósito no Projeto |
| :--- | :--- | :--- | :--- |
| **Backend** | C# | .NET 8.0 | Desenvolvimento da API RESTful, lógica de negócios e segurança. |
| **Segurança** | BCrypt.Net-Next | 4.0.3 | Hashing seguro de senhas. |
| **Front-end** | HTML, CSS, JavaScript | ES6+ | Interface do usuário e lógica do editor WYSIWYG. |
| **Bibliotecas JS** | jQuery, Magnific Popup | Diversas | Manipulação do DOM e recursos de UI/UX. |

## Como Executar

Para executar o projeto, siga os passos abaixo:

1.  **Clone o Repositório:**
    ```bash
    git clone [URL_DO_SEU_REPOSITORIO]
    ```
2.  **Configuração do Backend (API):**
    *   Navegue até o diretório da API.
    *   Configure a string de conexão com o banco de dados no arquivo `appsettings.json`.
    *   Restaure as dependências e compile o projeto:
        ```bash
        dotnet restore
        dotnet build
        ```
    *   Execute a API:
        ```bash
        dotnet run
        ```
3.  **Configuração do Front-end:**
    *   O Front-end é composto por arquivos estáticos.
    *   Certifique-se de que os arquivos JavaScript de autenticação e edição (`auth.js`, `editor.js`) estejam configurados para apontar para o endpoint correto da sua API.
    *   Abra o arquivo `login.html` ou `index.html` em seu navegador, ou sirva os arquivos estáticos através de um servidor web simples.

---
*Desenvolvido por Luiz para fins de portfólio e currículo.*
"# Editor-WYSIWYG" 
