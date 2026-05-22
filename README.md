# Tela de Login — Estudo de Caso ES

Simulação interativa de uma tela de login desenvolvida como estudo de caso para a disciplina de **Engenharia de Software** do CEUB, implementando os Casos de Teste definidos na especificação de Caso de Uso.

🔗 **[Acesse a demonstração ao vivo](https://gustavolg95.github.io/Tela_de_login/)**

---

## Demonstração

| Estado             | Descrição                                           |
| ------------------ | ----------------------------------------------------- |
| Formulário ativo  | Campos de login e senha com validação em tempo real |
| Usuário bloqueado | Exibido após 3 tentativas incorretas (RN01)          |
| Acesso concedido   | Exibido após autenticação bem-sucedida (US01)      |

---

## Casos de Teste implementados

| CT | Nome                      | Descrição                                                    |
| -- | ------------------------- | -------------------------------------------------------------- |
| 01 | Campo obrigatório        | Submeter sem preencher login e/ou senha exibe mensagem de erro |
| 02 | Login inválido           | Login inexistente com senha válida é rejeitado               |
| 03 | Senha inválida           | Login válido com senha incorreta é rejeitado                 |
| 04 | Bloqueio — RN01          | 3 tentativas erradas consecutivas bloqueiam o acesso           |
| 05 | Login com sucesso — US01 | Login case-insensitive; senha case-sensitive                   |

---

## Credenciais de teste

```
Login:  admin       (case insensitive — ADMIN, Admin, etc.)
Senha:  Abc123      (case sensitive)
```

---

## Regras de negócio

* **RN01** — Após 3 tentativas de autenticação incorretas, o usuário é bloqueado e deve contatar o administrador do sistema.
* **US01** — O campo login não diferencia maiúsculas de minúsculas; o campo senha é sensível a maiúsculas/minúsculas.

---

## Estrutura do projeto

```
tela-de-login/
├── index.html   # Estrutura, formulário e lógica de autenticação (JavaScript)
└── style.css    # Estilos, tema dark, animações e layout responsivo
```

---

## Como executar

Nenhuma dependência ou ferramenta de build é necessária. Basta abrir o arquivo diretamente no navegador:

```bash
# Opção 1 — abrir diretamente
Abra o arquivo index.html no navegador

# Opção 2 — servidor local (recomendado)
npx serve .
# ou
python -m http.server
```

---

## Tecnologias utilizadas

* **HTML5** — Estrutura semântica e acessibilidade (`aria-live`, `autocomplete`)
* **CSS3** — Variáveis CSS, animações, grid responsivo, tema dark
* **JavaScript (Vanilla)** — Lógica de autenticação, controle de tentativas, manipulação do DOM
* **Google Fonts** — DM Serif Display + DM Sans

---

## Funcionalidades da interface

* Indicador visual de tentativas restantes (bolinhas)
* Mensagens de erro por campo e toast de feedback global
* Botão para mostrar/ocultar senha
* Overlay de bloqueio animado após RN01
* Overlay de sucesso animado após autenticação válida
* Botão "Reiniciar demonstração" para resetar o estado
* Suporte a `Enter` para submeter o formulário
* Layout responsivo (painel informativo oculto em telas pequenas)

---

## Contexto acadêmico

> Disciplina: Engenharia de Software
>
> Instituição: CEUB — Centro Universitário de Brasília
>
> Objetivo: Demonstrar na prática a execução de casos de teste sobre um caso de uso de autenticação
>
