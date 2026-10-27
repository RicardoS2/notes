# Tutorial de Participação

> **Nota prévia:** Solicite ao **Rick** o convite de acesso ao repositório no GitHub antes de iniciar.

Este tutorial explica como participar da pesquisa, criar notas e contribuir para o projeto utilizando **Obsidian + Git**. O objetivo é manter as notas organizadas, padronizar os registros por meio de *templates* e sincronizar as alterações com o repositório compartilhado.

---

## 1. Configuração inicial

### 1.1. Clonar o repositório

1. Abra o terminal ou o Git Bash.
2. Execute:

   ```bash
   git clone https://github.com/RicardoS2/notes.git
   ```

3. Entre na pasta clonada, se necessário:

   ```bash
   cd notes
   ```

Se o repositório for privado, confirme que sua conta tem acesso e autentique-se por um método autorizado pelo GitHub, como SSH ou um Personal Access Token (PAT), quando aplicável.

### 1.2. Abrir o cofre no Obsidian

1. Inicie o **Obsidian**.
2. Selecione **Open folder as vault** (*Abrir pasta como cofre*).
3. Escolha a pasta `notes` que acabou de clonar.

---

## 2. Configurar o plugin Obsidian Git

1. No Obsidian, acesse **Settings** (ícone de engrenagem) > **Community plugins**.
2. Instale e ative o plugin **Obsidian Git**, caso ainda não esteja instalado.
3. Nas opções do plugin, configure os parâmetros abaixo, se estiverem disponíveis na sua versão:

   - **Vault backup interval (minutes):** `5` a `10`
   - **Auto pull interval (minutes):** `5` a `10`
   - **Auto pull on startup:** ativado (**ON**)
   - **Push on backup:** ativado (**ON**)
   - **Commit message on auto backup:** `Atualização automática do Vault`

> A sincronização automática depende da configuração do plugin e do acesso ao repositório. Antes de começar a editar, confirme que o pull e o push funcionam corretamente.

---

## 3. Estrutura do repositório

A estrutura sugerida para o cofre é:

```text
notes/
├── pastas/            # Pastas e subpastas para os tópicos de pesquisa
├── assets/
│   ├── pdfs/          # Documentos PDF
│   └── imagens/       # Imagens e gráficos
├── Templates/         # Modelos padronizados de notas
└── .obsidian/         # Configurações do Obsidian
```

Organize os arquivos nas pastas correspondentes e mantenha os nomes claros e consistentes.

---

## 4. Utilizar templates

### 4.1. Configurar o plugin Templates

1. No Obsidian, confirme que o plugin nativo **Templates** está ativado.
2. Nas configurações do plugin, defina **Template folder location** como `Templates/`.
3. Para inserir um modelo em uma nota, abra a paleta de comandos com `Ctrl + P` (ou `Cmd + P` no macOS) e selecione **Insert template**.
4. Se preferir usar um atalho de teclado, configure-o nas opções de atalhos do Obsidian. `Ctrl + T` não é necessariamente o atalho padrão.

### 4.2. Modelo base de nota

Crie o arquivo `Templates/Nova Nota.md` com o conteúdo abaixo:

```markdown
---
tags:
  - template
  - colaboracao
---

# Título da Nota

> [!TIP] Dica
> Preencha esta nota com as informações relevantes.

## Objetivo

Descreva o objetivo desta nota.

## Detalhes

Adicione links internos, arquivos PDF, imagens ou outras informações relevantes.

## Referências

- [[Outra Nota]]
- ![[assets/pdfs/exemplo.pdf]]
```

Ao criar uma nota, substitua os textos de orientação pelo conteúdo da pesquisa e mantenha as seções que forem pertinentes.

---

## 5. Regras de edição e colaboração

- Crie e edite as notas diretamente no Obsidian.
- **Identificação de edições:** ao alterar uma nota criada por outro autor, identifique sua contribuição com a notação `et al. + [Seu Nome]` no trecho modificado, conforme o padrão combinado pela equipe.
- **Evite edições simultâneas:** sempre que possível, combine com os demais colaboradores antes de editar o mesmo arquivo, reduzindo o risco de conflitos no Git.
- **Revise antes de sincronizar:** confira o conteúdo e os arquivos alterados antes de realizar o commit e o push.

### 5.1. Sincronização manual

Se precisar sincronizar manualmente:

1. Abra a paleta de comandos com `Ctrl + P` (ou `Cmd + P` no macOS).
2. Execute **Obsidian Git: Commit all changes**.
3. Informe uma mensagem de commit, se solicitado.
4. Execute **Obsidian Git: Push**.

Para receber as alterações dos outros colaboradores, execute **Obsidian Git: Pull** quando necessário. Se houver conflitos, resolva-os antes de continuar a sincronização.

### 5.2. Registrar sugestões com callouts

Use *callouts* para destacar comentários e sugestões dentro das notas. Exemplo:

```markdown
> [!INFO] Sugestão por Rick
> Adicionar uma seção de resumo no final desta nota.
```

---

## 6. Gerenciar anexos (PDFs e imagens)

Guarde os arquivos de apoio na pasta `assets/`, preferencialmente em subpastas organizadas.

- **Incorporar um PDF à nota:**

  ```markdown
  ![[assets/pdfs/manual.pdf]]
  ```

- **Criar um link para abrir ou baixar um PDF:**

  ```markdown
  [Abrir PDF](assets/pdfs/manual.pdf)
  ```

- **Incorporar uma imagem à nota:**

  ```markdown
  ![[assets/imagens/grafico.png]]
  ```

Verifique se os caminhos e nomes dos arquivos correspondem exatamente aos arquivos existentes no repositório.

---

## 7. Utilizar links internos (wikilinks)

Os *wikilinks* conectam notas e materiais dentro do Obsidian.

- **Link para outra nota:**

  ```markdown
  [[Nome da Nota]]
  ```

- **Link para uma seção específica:**

  ```markdown
  [[Nome da Nota#Nome da Secção]]
  ```

- **Incorporar um arquivo PDF ou outro anexo compatível:**

  ```markdown
  ![[assets/ficheiro.pdf]]
  ```

Use nomes de notas consistentes e confirme que os destinos dos links existem.

---

## 8. Checklist antes de terminar

- [ ] As notas estão nas pastas corretas.
- [ ] O template foi preenchido e os textos de orientação foram removidos.
- [ ] Links internos e caminhos dos anexos foram conferidos.
- [ ] As alterações foram revisadas.
- [ ] As alterações foram sincronizadas com o repositório, por meio do plugin ou manualmente.
