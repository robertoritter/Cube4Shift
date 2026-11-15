# Cube4Shift (Cube4Code)

Instruções permanentes para agentes de código neste repositório (Codex, Copilot, Cursor e outros que leem `AGENTS.md`).

## Padrões Cube4Code (obrigatórios)

Antes de qualquer trabalho, leia e siga estes arquivos:

- `docs/standards/BEHAVIOR.md`: como trabalhar e se comunicar.
- `docs/standards/GIT.md`: identidade, commits, aprovação e push.
- `docs/standards/BRAND.md`: logomarca, nome, cores e composição.

Resumo do que nunca pode faltar:

- Responder em português do Brasil, sem travessão (—).
- Commits com `Roberto Ritter <4182132+robertoritter@users.noreply.github.com>`, nunca e-mail pessoal. Conferir `git config user.email` antes do primeiro commit.
- Commit e push só com pedido ou autorização do Roberto. Nada de `push --force` ou reescrita de histórico enviado sem aprovação.
- Nunca versionar segredos (`.env`, chaves, senhas), dados reais (dumps, bancos locais, exportações) nem arquivos gerados; documentar variáveis em `.env.example`. Revisar `git diff --staged` antes de cada commit.
- Evidência antes de conclusão; o que não foi verificado é "Não validado".
- Marca: símbolo `cube4code.png` à esquerda, nome Cube4Shift em Manrope com o "4" violeta (`#8523D1` claro, `#A889FF` escuro), assinatura "by Cube4Code.com" com link.

## Sobre este projeto

- **O que é:** Cube4Shift, aplicação web para montar escalas de trabalho semanais e mensais a partir da lista de funcionários, do horário da empresa e das restrições de dia e horário de cada pessoa. Sem login.
- **Stack:** página única em HTML, CSS e JavaScript puro (`index.html`), sem build e sem servidor. Dados no `localStorage` do navegador, com backup em JSON.
- **Como rodar:** abrir `index.html` no navegador. É um arquivo único autossuficiente (símbolo embutido); `cube4code.png` é o ativo canônico.
- **Como testar:** gerar a escala semanal e mensal com os dados de exemplo e conferir cobertura completa, restrições respeitadas e as três visualizações (Detalhada, Simplificada e Quadro) nos dois idiomas e nos dois temas.
- **Decisões:** inglês como idioma padrão com menu para português (BR); motor de escala equilibra horas por semana e encaixa turnos parciais quando há restrição; a escala editada fica salva e é descartada ao gerar de novo.
- **Repositório:** https://github.com/robertoritter/Cube4Shift
