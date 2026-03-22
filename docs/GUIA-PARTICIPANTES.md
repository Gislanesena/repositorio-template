# 📘 Guia do GitHub — 1º Hackathon FATEC Itaquera

Tudo que você precisa saber para usar o GitHub durante o evento.

---

## Sumário

1. [Criar o repositório do time](#1-criar-o-repositório-do-time)
2. [Configurar o repositório](#2-configurar-o-repositório)
3. [Trabalhar com branches e commits](#3-trabalhar-com-branches-e-commits)
4. [Usar as Issues como tasks](#4-usar-as-issues-como-tasks)
5. [Montar o Kanban (Project Board)](#5-montar-o-kanban-project-board)
6. [Fazer Pull Requests e revisão de código](#6-fazer-pull-requests-e-revisão-de-código)
7. [Usar as Discussions para dúvidas](#7-usar-as-discussions-para-dúvidas)
8. [Entrega final](#8-entrega-final)
9. [Erros comuns que desclassificam](#9-erros-comuns-que-desclassificam)

---

## 1. Criar o repositório do time

### Usando o template oficial

O repositório deste hackathon é um **template** — isso significa que você não precisa começar do zero.

**Passo a passo:**

1. Acesse: [github.com/hackathon-FATEC/repositorio-template](https://github.com/hackathon-FATEC/repositorio-template)
2. Clique no botão verde **"Use this template"**
3. Clique em **"Create a new repository"**

   ![Use this template → Create a new repository]

4. Preencha as informações:
   - **Owner:** sua conta pessoal ou uma organização do time
   - **Repository name:** `fatec-hack-nome-do-time` (ex: `fatec-hack-equipe-alpha`)
   - **Visibility:** obrigatoriamente **Public** ⚠️
5. Clique em **"Create repository"**

> ⚠️ **Repositório privado = desclassificação.** O repositório precisa ser público durante toda a avaliação.

---

### Clonar o repositório na sua máquina

Após criar, todos do time precisam clonar:

```bash
git clone https://github.com/SEU-USUARIO/fatec-hack-nome-do-time
cd fatec-hack-nome-do-time
```

---

## 2. Configurar o repositório

### Adicionar os membros do time como colaboradores

Só quem é colaborador pode fazer push diretamente no repositório.

1. Vá em **Settings → Collaborators → Add people**
2. Adicione o usuário GitHub de cada membro do time
3. Cada membro aceita o convite pelo e-mail ou pela notificação no GitHub

### Preencher o README do time

O template já vem com um README pré-preenchido. Edite com as informações do time:

- Nome do time
- Nome e papel de cada membro
- Stack tecnológica escolhida
- Como rodar o projeto localmente (atualize conforme forem construindo)

### Adicionar a licença de Software Livre

O edital exige que o projeto tenha uma licença open source.

1. Na página do repositório, clique em **"Add file" → "Create new file"**
2. Nomeie o arquivo como `LICENSE`
3. À direita aparecerá o botão **"Choose a license template"** — clique nele
4. Escolha **MIT License** (a mais simples), preencha o ano e seu nome
5. Clique em **"Review and submit"** e depois em **"Commit changes"**

---

## 3. Trabalhar com branches e commits

### Por que usar branches?

Sem branches, todo mundo editando o mesmo arquivo ao mesmo tempo gera conflitos e código perdido. Com branches, cada pessoa trabalha no seu "rascunho" e só junta quando está pronto.

### O fluxo básico

```
main  ← branch principal, sempre com código funcionando
  └── feature/carteirinha-digital   ← sua branch de trabalho
  └── feature/tela-de-notas         ← branch de outro membro
```

### Passo a passo para trabalhar em uma task

**1. Antes de começar qualquer coisa, atualize o main:**
```bash
git checkout main
git pull
```

**2. Crie uma branch para a sua task:**
```bash
git checkout -b feature/nome-da-feature
```

Exemplos de nomes de branch:
```
feature/tela-de-login
feature/carteirinha-digital
feature/grade-de-aulas
fix/corrigir-redirect-login
chore/configurar-banco
```

**3. Trabalhe no código e faça commits com frequência:**
```bash
git add .
git commit -m "feat: adicionar formulário de login"
```

```bash
git add .
git commit -m "feat: validar campos do formulário"
```

**4. Suba sua branch para o GitHub:**
```bash
git push origin feature/nome-da-feature
```

**5. Abra um Pull Request** (veja a seção 6).

---

### Como escrever mensagens de commit

Mensagens de commit são critério de avaliação. Use o padrão:

```
tipo: descrição curta no imperativo
```

| Tipo | Quando usar | Exemplo |
|------|-------------|---------|
| `feat` | Nova funcionalidade | `feat: adicionar carteirinha digital` |
| `fix` | Correção de bug | `fix: corrigir token expirado no login` |
| `chore` | Configuração, setup | `chore: configurar banco de dados` |
| `docs` | Documentação | `docs: atualizar README com instruções` |
| `style` | Ajustes visuais sem mudar lógica | `style: centralizar botão do dashboard` |

**✅ Exemplos de bons commits:**
```
feat: adicionar tela de login com validação
fix: corrigir redirecionamento após sessão expirada
feat: integrar endpoint de notas com a tela de desempenho
chore: adicionar variáveis de ambiente ao .env.example
docs: documentar como rodar o seed do banco
```

**❌ O que não fazer:**
```
update
ajustes
wip
correção
final
final2
agora vai
commit
```

> 💡 **Dica:** commit pequeno e frequente é muito melhor do que um commit gigante no final. Mostra a evolução do projeto — e é exatamente isso que o júri vai olhar.

---

## 4. Usar as Issues como tasks

As issues deste repositório são o **backlog oficial** do desafio. Cada issue é uma task que o time pode pegar.

### Durante o Sprint Planning

1. Acesse as issues em: [github.com/hackathon-FATEC/repositorio-template/issues](https://github.com/hackathon-FATEC/repositorio-template/issues)
2. Leia todas as issues disponíveis com o time
3. Decida quais fazem sentido para a solução que o time vai construir
4. Para cada issue que o time vai fazer:
   - Abra a issue
   - No painel direito, clique em **"Assignees"** e atribua ao membro responsável
   - Adicione ao Project Board do time (veja seção 5)

### Criar issues novas

O time pode e deve criar issues para features criativas que inventar. Isso demonstra autonomia e organização.

1. Clique em **"New issue"** no repositório **do time** (não no repositório oficial)
2. Use o template de task disponível
3. Preencha título, descrição, critérios de aceite e estimativa de esforço
4. Adicione as labels adequadas

### Labels importantes

| Label | O que significa |
|-------|----------------|
| `obrigatório` | Precisa estar no Done para o projeto ser avaliado |
| `sugerido` | Recomendado para um MVP sólido |
| `bonus` | Extra: diferencial na avaliação |

### Fechar uma issue

Quando a task está pronta e o código foi aprovado no Pull Request, feche a issue:
- Pelo PR: escreva `Closes #numero` na descrição do PR — a issue fecha automaticamente no merge
- Ou manualmente: abra a issue e clique em **"Close issue"**

---

## 5. Montar o Kanban (Project Board)

O Kanban é onde o time visualiza o andamento da sprint. **Deve ser mantido atualizado** — o júri vai olhar.

### Criar o Project Board do time

1. No repositório do time, clique em **"Projects"**
2. Clique em **"Link a project" → "New project"**
3. Escolha o template **"Board"**
4. Nomeie como `Sprint — [Nome do Time]`
5. Crie as 5 colunas clicando em **"+ Add column"**:

```
📋 Backlog  |  📌 To Do  |  ⚙️ In Progress  |  🔎 Review  |  ✅ Done
```

6. Torne o board público: **Settings → Visibility → Public**

### Adicionar as issues ao board

1. No board, clique em **"+ Add item"** na coluna **Backlog**
2. Digite `#` para buscar as issues do repositório
3. Adicione todas as issues que o time comprometeu para a sprint

### Mover os cards durante o evento

| Situação | Mova o card para |
|----------|-----------------|
| Time decidiu fazer a task | **To Do** |
| Membro começou a trabalhar | **In Progress** |
| Código feito, abriu PR | **Review** |
| PR aprovado e mergeado | **Done** |

> ⚠️ **WIP Limit:** cada membro pode ter no máximo **2 cards em "In Progress"** ao mesmo tempo. Terminem o que começaram antes de pegar uma task nova.

## 6. Fazer Pull Requests e revisão de código

### O que é um Pull Request (PR)?

É o processo de propor que o código da sua branch entre na branch `main`. Antes de entrar, um colega revisa.

### Como abrir um PR

1. Após dar `git push` da sua branch, acesse o repositório no GitHub
2. Aparecerá um banner amarelo: **"Compare & pull request"** — clique nele
3. Preencha a descrição seguindo este modelo:

```markdown
## O que esta PR faz?
Adiciona a tela de login com validação de campos.

## Issue relacionada
Closes #3

## Como testar?
1. Rode o projeto com `npm run dev`
2. Acesse http://localhost:3000/login
3. Tente fazer login com campo vazio: deve aparecer mensagem de erro
4. Faça login com aluno@fatec.sp.gov.br / demo1234:  deve ir para o dashboard


4. Em **"Reviewers"**, selecione pelo menos **1 colega do time**
5. Clique em **"Create pull request"**

### Como revisar o PR de um colega

1. Acesse a aba **"Pull requests"** no repositório
2. Abra o PR do colega
3. Clique em **"Files changed"** para ver o que mudou
4. Deixe comentários clicando no `+` ao lado de uma linha de código
5. Quando terminar, clique em **"Review changes"** e escolha:
   - ✅ **Approve** — está bom, pode fazer merge
   - 💬 **Comment** — tem dúvidas mas não bloqueia
   - ❌ **Request changes** — precisa ajustar antes de mergear

### Fazer o merge

Após aprovação:
1. Clique em **"Merge pull request"**
2. Clique em **"Confirm merge"**
3. Delete a branch usada (o GitHub vai oferecer o botão)
4. Mova o card no Kanban para **Done**

---

## 7. Usar as Discussions para dúvidas

As Discussions são o fórum oficial do hackathon para tirar dúvidas.

### Acessar

[github.com/hackathon-FATEC/repositorio-template/discussions](https://github.com/hackathon-FATEC/repositorio-template/discussions)

### Antes de perguntar

Confira se a dúvida já foi respondida:
- Leia o [Edital completo](EDITAL.md)
- Leia o [README principal](../README.md)
- Pesquise nas Discussions se alguém já perguntou a mesma coisa

### Como abrir uma boa dúvida

1. Clique em **"New discussion"**
2. Escolha a categoria **"Q&A"**
3. Escreva um título específico:
   - ✅ `Como funciona o critério de acessibilidade na avaliação?`
   - ✅ `A issue #12 (QR Code) é realmente obrigatória?`
   - ❌ `Dúvida sobre o hackathon`
4. No corpo, explique com detalhes:
   - O que você já leu/tentou
   - O que exatamente não ficou claro

### Dúvida técnica urgente no dia do evento

Se for uma dúvida técnica urgente durante o evento, chame um mentor presencialmente: é mais rápido do que esperar uma resposta online.

---

## 8. Entrega final

### O que entregar

Antes do **code freeze** (horário definido no cronograma):

- [ ] Repositório **público** no GitHub com todo o código
- [ ] README com instruções de como rodar e tecnologias usadas
- [ ] Licença de Software Livre no repositório (MIT, GPLv3 ou Apache 2.0)
- [ ] Histórico de commits demonstrando evolução do projeto
- [ ] Screenshot ou link do Kanban atualizado
- [ ] Demo funcionando (local ou deploy público)

Envie o link do repositório pelo formulário oficial dentro do prazo.

### Verificar antes de entregar

```bash
# Certifique-se que o .env não está no repositório
git status
# Não deve aparecer .env na lista

# Veja se o histórico de commits está bom
git log --oneline

# Faça um teste de instalação limpa
# (clone em outra pasta e siga o README do zero)
```

No GitHub, confirme:
- O repositório está **público** (Settings → Danger Zone → Change visibility)
- O README está atualizado e as instruções funcionam
- A licença aparece na página inicial do repositório

---

## 9. Erros comuns que desclassificam

| ❌ Erro | ✅ Como evitar |
|---------|--------------|
| Repositório privado na hora da avaliação | Deixe público desde o início e não altere |
| Sem histórico de commits (tudo em 1 commit) | Commit pequeno e frequente durante todo o evento |
| Commitar o arquivo `.env` com senhas | Adicione `.env` ao `.gitignore` antes do primeiro commit |
| README sem instruções de instalação | Atualize o README conforme constroem |
| Sem licença no repositório | Adicione MIT License no início do evento |
| Usar código de projeto anterior | Todo o código deve ser produzido no dia |
| Conduta desrespeitosa | Trate todos com respeito |

---

*Dúvidas sobre este guia? Abra uma [Discussion](https://github.com/hackathon-FATEC/repositorio-template/discussions) ou fale com um mentor no evento.*
