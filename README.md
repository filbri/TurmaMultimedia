# Projeto de Colaboração Git: Pesquisa Estruturada em Markdown

No âmbito da nossa aprendizagem sobre Git e fluxos de trabalho colaborativos, este repositório serve como espaço prático para simularmos um ambiente real de desenvolvimento em equipa. Cada estudante irá contribuir com uma pesquisa individual, integrando o seu trabalho através de um fluxo de ramos (*branches*) e pedidos de integração (*Pull Requests* / *Merge Requests*).

---


![Git](https://img.shields.io/badge/Git-Colaboração-F05032?logo=git&logoColor=white&style=for-the-badge)
![Markdown](https://img.shields.io/badge/Markdown-Estruturado-000000?logo=markdown&logoColor=white&style=for-the-badge)
![GitHub](https://img.shields.io/badge/Plataforma-GitHub%20%2F%20GitLab-181717?logo=github&logoColor=white&style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Em%20Curso-brightgreen?style=for-the-badge)

---

## 🎯 Objetivo do Trabalho

O objetivo principal é exercitar a colaboração distribuída. Para tal, cada aluno deverá:
1. Escolher um tema de pesquisa único (que não tenha sido selecionado por outro colega).
2. Criar um ficheiro Markdown individual com o seu nome (exemplo: `nome-sobrenome.md`).
3. Estruturar a pesquisa utilizando elementos básicos de Markdown (títulos, listas, negrito, links e citações).
4. Submeter a contribuição através do fluxo de trabalho correto baseado em *Branches* e *Pull Requests*.

---

## Temas

### Tecnologia e Multimédia
- A evolução da Inteligência Artificial.
- A história da Internet.
- O que é a Realidade Virtual (VR).
- O que é a Realidade Aumentada (AR).
- Impressão 3D.
- Computação na Cloud.
- Cibersegurança: boas práticas.
- Como funciona o GPS.
- A evolução dos videojogos.
- O impacto das redes sociais na comunicação.

### Design e Comunicação
- História do design gráfico.
- Psicologia das cores.
- Tipografia: importância e tipos de letra.
- Design de logótipos.
- Princípios de UX/UI.
- Identidade visual de uma marca.
- Fotografia digital: regras de composição.
- Storytelling digital.
- Infografia: o que é e para que serve.
- A evolução da publicidade.

### Áudio e Vídeo
- História do cinema.
- Evolução da fotografia.
- Como funciona uma câmara digital.
- Técnicas básicas de edição de vídeo.
- Podcast: origem e crescimento.
- Streaming: como funciona.
- Efeitos especiais no cinema.
- Animação 2D vs. 3D.
- História da televisão.
- Direitos de autor em conteúdos multimédia.

### Ciência e Tecnologia
- Energias renováveis.
- Exploração espacial.
- Alterações climáticas.
- Robótica.
- Biometria.
- Veículos elétricos.
- Computadores quânticos.
- Internet das Coisas (IoT).
- Nanotecnologia.
- Drones: aplicações atuais.

### Cultura Digital
- Fake News e desinformação.
- Influenciadores digitais.
- O fenómeno do TikTok.
- Cultura dos memes.
- E-sports.
- Streaming de música.
- Privacidade online.
- Pegada digital.
- Economia dos criadores de conteúdo.
- Ética na Inteligência Artificial.

### Empresas e Inovação
- História da Google.
- História da Apple.
- História da Microsoft.
- História da Adobe.
- História da Netflix.
- História da Spotify.
- Open Source: o que é.
- Linux.
- GitHub.
- Software livre vs. software proprietário.

### Temas Criativos
- A evolução dos emojis.
- História dos videojogos retro.
- O impacto do YouTube na educação.
- Como nasceu a Wikipédia.
- A evolução dos telemóveis.
- O futuro da Inteligência Artificial.
- Como funciona um motor de pesquisa.
- O que é um algoritmo.
- O papel da multimédia na educação.
- Profissões do futuro na área da multimédia.


---

## 🚀 Como Participar (Passo a Passo)

Para garantir que o repositório principal se mantém íntegro e organizado, deves seguir estritamente o fluxo de trabalho abaixo:

### 1. Preparar o Ambiente Local
Clona este repositório para o teu computador e acede à pasta do projeto:
```bash
git clone <URL_DESTE_REPOSITORIO>
cd <nome-da-pasta>
```

### 2. Criar um Novo Ramo (Branch)
Importante: Nunca faças alterações diretamente na linha principal (main ou master). Cria um branch dedicado com o teu nome:

```bash
git checkout -b adicionar-pesquisa-teu-nome
```

### 3. Criar e Editar o Teu Ficheiro
Cria um ficheiro na raiz do projeto com o padrão de nome primeironome-ultimonome.md e desenvolve a tua pesquisa de forma estruturada.

### 4. Gravar e Enviar as Alterações
Adiciona o ficheiro à área de preparação, faz o registo local (commit) e envia o branch para o servidor remoto:
```bash
git status
git add primeironome-ultimonome.md
git commit -m "Adiciona pesquisa de [Teu Nome] sobre [Teu Tema]"
git push origin adicionar-pesquisa-teu-nome
```

### 5. Abrir um Pull Request (PR)
Acede à página deste repositório no navegador, onde verás um aviso sugerindo a criação de um Pull Request. Clica nele, preenche a descrição sumária do teu trabalho e envia a tua proposta de integração.
```markdown
📝 Modelo de Estrutura do Ficheiro
Garante que o teu ficheiro Markdown segue uma estrutura organizada semelhante a esta:
code
Markdown
# Título Principal do Tema

## 1. Introdução
Breve contextualização do assunto selecionado.

## 2. Pontos-Chave
- Ponto importante A;
- Ponto importante B;
- Ponto importante C.

## 3. Conclusão
Resumo das descobertas ou reflexão final.

## 4. Referências e Fontes
- [Nome do Site/Artigo](https://link-da-fonte.com)
```

