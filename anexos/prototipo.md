# Protótipo de Interface — DoaTroca (DTC)

Descrição das 14 telas do protótipo construído no Figma e do design system utilizado. As telas
cobrem todos os requisitos funcionais com interação de usuário (RF01–RF14), incluindo as duas
telas do administrador. A relação completa entre telas, requisitos e casos de uso está na
Tabela 10 do [documento de requisitos](../README.md#5-protótipo-de-interface).

## Design System

**Paleta de cores**

| Cor | Hex | Uso |
|---|---|---|
| Creme | `#F9ECE5` | Fundo de todas as telas |
| Verde-petróleo escuro | `#014B43` | Cabeçalhos, textos de destaque, barra de navegação |
| Verde-petróleo | `#099078` | Ações primárias (botões, links, valores positivos) |
| Terracota | `#9C2113` | Alerta e perigo (denunciar, bloquear, cabeçalhos de avaliação e denúncia) |
| Rosa claro | `#FFD6D1` | Destaque suave (chips de filtro, avisos, indicador de itens ativos) |

**Componentes padronizados**

- **Cabeçalho**: barra de 64 px em verde-petróleo escuro (terracota nas telas de avaliação e
  denúncia), título branco em negrito e seta "←" quando há navegação de volta.
- **Campo de formulário**: rótulo em negrito verde-petróleo escuro e caixa branca com borda
  clara, cantos arredondados e texto de exemplo em cinza.
- **Botão primário**: fundo verde-petróleo, texto branco, cantos arredondados.
- **Botão secundário**: fundo transparente com borda verde-petróleo escuro.
- **Botão de perigo**: fundo terracota, texto branco (enviar denúncia, bloquear).
- **Chip**: cantos totalmente arredondados, preenchido quando ativo e com borda quando inativo
  (filtros, categorias, estado de conservação, tipo de anúncio).
- **Cartão**: fundo branco, cantos arredondados, título em negrito e subtítulo em cinza.
- **Barra de navegação inferior**: fundo verde-petróleo escuro com cinco itens — Início,
  Publicar, Chat, Notificações e Perfil — e o item ativo em destaque.
- **Moldura**: cada tela tem 340 × 780 px, cantos arredondados e fundo creme, simulando um
  smartphone.

## Telas

| Nº | Tela | Requisitos | Conteúdo |
|---|---|---|---|
| 01 | [Cadastro / Login](telas/tela-01.png) | RF01, RSEG01, RUSA01 | Nome completo, bairro/rua, telefone ou e-mail e senha em uma única etapa; botão "Criar conta" e link "Já tenho conta" |
| 02 | [Feed / Busca](telas/tela-02.png) | RF03, RPER01 | Campo de busca, filtros de categoria e proximidade e cartões de itens com foto, categoria, estado e distância |
| 03 | [Cadastrar item](telas/tela-03.png) | RF02, RF11 | Foto, título, categoria, descrição, estado de conservação (novo/usado/avariado), tipo (doação/troca) e o que deseja receber na troca; indicador "3/10 itens ativos" no cabeçalho |
| 04 | [Detalhe do item](telas/tela-04.png) | RF03, RF04, RF14 | Foto, título, categoria, estado, descrição e dados do doador com reputação; botões "Tenho interesse" e, para o doador, "Marcar como retirado" |
| 05 | [Chat](telas/tela-05.png) | RF04, RSEG01, RF07 | Conversa entre doador e interessado, aviso "Combine local neutro. Evite endereço exato.", sugestões de local (Portaria, Praça Central) e link "Denunciar usuário" |
| 06 | [Confirmar retirada](telas/tela-06.png) | RF05 | Confirmação de que o item foi retirado e sairá da busca; botões "Confirmar retirada" e "Cancelar" |
| 07 | [Avaliar usuário](telas/tela-07.png) | RF06 | Nota de 1 a 5 estrelas, comentário opcional, "Enviar avaliação" e "Pular" |
| 08 | [Denunciar usuário](telas/tela-08.png) | RF07 | Motivo (não compareceu, item golpe, comportamento inadequado, outro), descrição e "Enviar denúncia" |
| 09 | [Notificações](telas/tela-09.png) | RF08 | Novos itens nas categorias de interesse, item retirado, avaliação recebida, lembrete de anúncio parado e resultado de denúncia |
| 10 | [Painel de moderação](telas/tela-10.png) | RF09 | Denúncias recebidas com usuário, data e motivo; ações "Bloquear" e "Arquivar" |
| 11 | [Relatório](telas/tela-11.png) | RF10 | Itens doados, categoria mais comum, usuários ativos e gráfico de itens reaproveitados por categoria |
| 12 | [Perfil](telas/tela-12.png) | RF14, RF06 | Nome, bairro, data de entrada, itens doados, nota média e acesso às preferências de notificação |
| 13 | [Preferências de notificação](telas/tela-13.png) | RF13 | Seleção das categorias de interesse (roupas, móveis, eletrônicos, livros, outros) e "Salvar preferências" |
| 14 | [Confirmar recebimento](telas/tela-14.png) | RF12 | Pergunta ao recebedor se recebeu o item; botões "Sim, recebi" e "Não recebi" |

## Navegação

O protótipo é navegável no modo de apresentação do Figma, com dois pontos de início:
**Morador** (Tela 01) e **Administrador** (Tela 10).

```
Cadastro/Login (01)
      │
      ▼
Feed/Busca (02) ──► Perfil (12) ──► Preferências (13)
   │        │  └──► Notificações (09)
   ▼        ▼
Publicar (03)  Detalhe do item (04) ──► Chat (05) ──► Denunciar (08)
                    │
                    ▼
           Confirmar retirada (06) ──► Confirmar recebimento (14) ──► Avaliar usuário (07)

Administrador: Painel de moderação (10) ◄──► Relatório (11)
```

A barra de navegação inferior dá acesso direto a Início (02), Publicar (03), Chat (05),
Notificações (09) e Perfil (12).
