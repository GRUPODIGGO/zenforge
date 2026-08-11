# Zenforge — regras e contexto para o Claude Code

Este arquivo é carregado automaticamente em toda sessão neste repositório.

## Identidade do projeto

- Nome: **Zenforge** — unidade de criação de apps e sites com IA do Grupo Diggo.
- Origem do nome: fusão de *Zenith* (ápice) + *Forge* (forjar/criar). Escolhido entre três finalistas (Foundra, Artifex, Diggo Forge) — Zenforge venceu por ser autoral, único e fácil de marcar.
- Domínio: **zenforge.grupodiggo.com.br** (migrado de `zenforge.testaapp.live` em 10/08/2026, quando o hub [[grupodiggo]] entrou no ar — ver aquele CLAUDE.md pra contexto completo da migração).
- Repositório: https://github.com/GRUPODIGGO/zenforge (conta GRUPODIGGO, mesma usada no repo do TestaApp)
- Hospedagem: **GitHub Pages** (gratuito) — não está no Lovable. Foi uma decisão explícita do Diogo (não queria criar projeto novo no Lovable pra isso).
- Fundador exibido na página: Diogo B. Lima (mesma pessoa por trás do Grupo Diggo/TestaApp).

## Stack e estrutura

- Site estático de uma página só: `index.html` (HTML + CSS inline + JS vanilla, sem build step, sem framework).
- `CNAME` na raiz do repo com o valor `zenforge.grupodiggo.com.br` — é isso que diz ao GitHub Pages qual domínio customizado servir.
- Imagens, vídeo e logos ficam em `assets/` (subpastas `img/` e `logo/`), a maioria em WebP. Essa pasta existe desde 10/08/2026; antes disso as imagens ficavam embutidas em base64 direto no HTML — decisão pontual daquele momento, não uma regra fixa do projeto. Em 11/08/2026 o restante das imagens em base64 (fundador, logos da faixa "Empresas do grupo") também foi migrado pra `assets/img/` em WebP, reduzindo o `index.html` de ~1.9 MB pra ~56 KB.

## Como publicar mudanças

1. Editar `index.html` direto (é o único arquivo de conteúdo).
2. `git add index.html && git commit -m "..." && git push origin main`
3. O GitHub Pages rebuilda sozinho, geralmente em 1-2 minutos. Não precisa de nenhum passo manual extra.
4. Pra confirmar que subiu: `curl https://zenforge.grupodiggo.com.br` e conferir o conteúdo esperado. HTTPS já está ativo (certificado Let's Encrypt confirmado em 11/08/2026).

Identidade git usada nos commits deste repo: `Diogo B. Lima` / `skatista.mano.diggo@gmail.com` (mesma do TestaApp).

## DNS e domínio

- Registro configurado pelo Diogo (fora do meu alcance — não sei em qual provedor/painel): `CNAME zenforge → grupodiggo.github.io` (agora sob a zona `grupodiggo.com.br`, não mais `testaapp.live`).
- **HTTPS já está ativo.** Certificado Let's Encrypt confirmado pra `zenforge.grupodiggo.com.br` (emitido 11/08/2026, válido até 09/11/2026). Tanto `http://` quanto `https://` respondem 200.
- **Importante sobre nomenclatura do GitHub Pages:** o valor `grupodiggo.github.io` é o destino de DNS padrão pra **qualquer** repositório com domínio customizado dentro da conta `GRUPODIGGO` — não é um repositório específico, e não muda se o nome do repo `zenforge` for alterado. Um repositório chamado literalmente `grupodiggo.github.io` (nome exato) está **reservado pra um futuro site raiz do Grupo Diggo** e não conflita com este projeto.

## Contato / WhatsApp

- Todos os botões de contato ("Forjar meu projeto", "Falar com a Zenforge") e o ícone flutuante apontam pra `https://wa.me/5573988398108` com uma mensagem pré-preenchida.
- Se o número mudar no futuro, buscar por `5573988398108` no `index.html` — aparece em 3 lugares (2 botões + ícone flutuante).

## Marcas do Grupo Diggo referenciadas na página

- **TestaApp** → https://testaapp.live (linkado)
- **BuildSpeed A.I.** → https://buildspeed.testaapp.live (linkado)
- **Grupo Diggo** → mostrado como identidade, sem link (é o grupo em si, não tem site próprio ainda)

## Sistema de design (pra manter consistência em mudanças futuras)

- **Conceito**: metáfora de forja — blocos de cor cheios (sem gradiente), tom vibrante/criativo pedido pelo Diogo.
- **Paleta**: `--ember` (#E15A2A, cor dominante do hero), `--plum` (#1E1420, seções escuras), `--stone` (#F3ECE4, seções claras), `--gold` (#E8A93D, destaque/CTA), `--cream` (#FBF3EA, texto claro sobre fundo escuro).
- **Tipografia**: display em `Arial Black` (caixa alta, condensado, sensação "forjada"), corpo em stack system-ui, rótulos técnicos em monoespaçada.
- **Diferencial de negócio** (seção "Por que Zenforge"): preço baixo + entrega rápida, possibilitados por especialistas em IA e engenheiros de prompt no time — este é o argumento central de venda, não mexer no racional sem o Diogo confirmar.

## Regras de trabalho

- Site simples, de uma página — mudanças aqui são mais leves que no TestaApp (sem banco de dados, sem regras de negócio complexas). Ainda assim: **sempre confirmar mudanças de conteúdo/preço/contato antes de aplicar**, só corrigir bug óbvio direto.
- Nunca reintroduzir texto colado bruto do Diogo sem reescrever pra tom profissional — ele já pediu isso uma vez explicitamente.
- Não expandir escopo (ex: não adicionar formulário de contato, blog, etc.) sem pedir.
