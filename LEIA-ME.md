# TV Corporativa — Fase 2 (nuvem)

## Arquivos
| Arquivo | Para quê |
|---|---|
| `schema.sql` | Cria o banco no Supabase (rodar 1 vez; pode rodar de novo sem problema) |
| `config.js` | URL e anon key do seu Supabase (já preenchidos) |
| `player.html` | Abrir na **TV** |
| `admin.html` | Abrir no **computador/celular** para gerenciar |

## Instalação (uma vez)
1. **Banco:** Supabase → *SQL Editor* → *New query* → cole todo o `schema.sql` → **Run**. Deve terminar sem erro.
2. **Publicar:** coloque `player.html`, `admin.html` e `config.js` na mesma pasta de um repositório GitHub com *Pages* ligado (como nos outros apps). As URLs ficam `https://SEU-USUARIO.github.io/REPO/player.html` e `.../admin.html`.
3. **Endereço do site no Supabase:** *Authentication → URL Configuration → Site URL* = a URL do GitHub Pages (usada nos e-mails de confirmação e de "esqueci a senha").
4. **Sua conta:** abra `admin.html` → *Criar conta* → confirme o e-mail (se pedir) → entre → informe o nome da organização.
5. **Feche o cadastro público:** depois de criar sua conta, em *Authentication → Sign In / Providers* desmarque **Allow new users to sign up**. Assim ninguém mais consegue criar conta no seu painel. (Quando for vender, você reabre ou muda para convite.)

## Atualizando de versão anterior
1. Rode o `schema.sql` de novo no SQL Editor (adiciona as colunas de agendamento sem apagar nada).
2. Suba `player.html` e `admin.html` novos no GitHub (a TV recarrega sozinha às 04:00; ou recarregue na hora).

## Uso diário
- **Parear uma TV:** abra `player.html` na TV → aparece um código de 6 dígitos → no painel, aba **TVs**, digite o código e dê um nome.
- **Conteúdo:** abas Mídia, Avisos, Ticker. Cada item vale para *Todas as TVs* ou para *uma TV só*. É possível **desativar** sem apagar.
- **Agendamento:** em cada item, abra **Agendamento** e escolha início/fim (data), **dias da semana** (atalhos Todos / Seg–Sex / Fim de semana) e **horário** (de–até; precisa preencher os dois). Vale o fuso de *Configurações*. Janela que passa da meia-noite (ex.: 22:00–06:00 na sexta) continua valendo até o fim na madrugada de sábado.
- **Prévia:** aba **Prévia** mostra a TV exatamente como ela vai exibir, por TV. Use *Simular data e hora* (ex.: sábado 10:00) para conferir os agendamentos sem esperar.
- **Tempos de espera:** aba *Espera e emergência*. Sem atualização por 4 h a TV mostra "—" (ajustável em Configurações).
- **Emergência:** ativa nas TVs em até ~20 s; pode encerrar sozinha.
- **Marca:** aba Configurações (nome, rodapé, logo, clima).

## Limites e cuidados
- Plano grátis do Supabase: **50 MB por arquivo** e **1 GB** no total de mídias.
- A **anon key** em `config.js` é pública por projeto. **Nunca** coloque a `service_role key` em nenhum arquivo.
- A TV precisa de navegador moderno (Chrome 60+ / Tizen 4+ / webOS 5+). Em TV antiga, use TV Box/Fire Stick com Chrome ou Silk.
- Remover uma TV no painel a devolve à tela de pareamento e apaga os itens exclusivos dela.
- O `index.html` antigo (TV única, sem nuvem) continua funcionando separado; mídias e avisos dele **não** são migrados automaticamente.
