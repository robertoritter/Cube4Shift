# Cube4Shift

*by [Cube4Code.com](https://cube4code.com/)*

**English** | [Português](#português)

## English

A web app for building weekly and monthly work schedules.

### Features

- **Company:** opening hours for each weekday (may run past midnight), how many people must work at the same time, shift length, minimum partial shift and minimum rest between shifts.
- **Employees (CRUD):** name, role, weekly hour and day limits, active/inactive status.
  - Recurring restrictions (every week): unavailable all day, not after, not before, unavailable between two times.
  - One-off constraints (a date or a period): day off, appointment, course etc.
- **Restriction types per person:** unavailable all day, not after, not before, unavailable between, **can only work between** (e.g. nights only), and **alternating days** (e.g. works Saturday one week and Sunday the next). Recurring or one-off.
- **Rules by role:** minimum and maximum people of each role at the same time (e.g. at least 1 cashier, at most 1 supervisor). The generator respects them, trimming a shift when needed to stay under the maximum.
- **Schedule:** automatic weekly or monthly generation that balances hours across people and respects restrictions, role rules, limits and rest.
- **Weekly hours:** after covering the minimum, each person is topped up to their contracted weekly hours (e.g. 5 × 7.5 h + 6.5 h = 44 h), where fewer people are working and avoiding holidays.
- **Weekly day off in rotation (optional):** each person's day off moves to the next allowed day every week (Mon, Tue, Wed...), people start on different days and the sequence continues from the previous saved schedule. Each person can have preferred days to rotate among (one day = fixed day off). Coverage comes first; when a rotation day has to be used, the schedule check says so.
- **Sundays off:** every person gets at least N Sundays off per month (default 1), planned in rotation so no Sunday is left short; people already off on Sundays by restriction count automatically.
- **Holidays:** Brazilian national holidays are calculated automatically every year (including Good Friday), with optional days (Carnival, Corpus Christi) and custom state/city holidays. Each holiday can be marked as closed. With internet access, the official list is downloaded from BrasilAPI (fallback: Nager.Date); offline, the built-in calculation is used.
- **Compensatory day off:** whoever works on a holiday gets one extra day off in the following week (Monday to Sunday), with that week's hours goal reduced proportionally. The schedule check flags it if a manual change removes that day off.
- **Schedule check:** coverage, role minimum/maximum, restrictions, weekly limits and rest are verified continuously, including after manual changes. Conflicts are allowed but flagged on screen (cell outline, day marker and a summary panel) and never printed.
- **Saved schedules:** every generated month or week is saved with its manual changes. Monthly schedules use complete weeks (Monday to Sunday); the week shared with a neighbouring saved schedule is taken from it, so holidays worked, compensatory days off and rest carry over from one month to the next.
- **Generate, recalculate, close:** if the period already has a schedule, Generate asks whether to open it, recalculate keeping manual changes, or start from scratch. Recalculate redoes only the automatic part. Closing a schedule makes it final (read-only until reopened) and the reference for the following ones.
- **Manual adjustments:** change the person on a shift (swapping automatically if the other person already works that day), change times, schedule someone on a day off, add or remove people from the schedule. Conflicts raise a warning.
- **Views:**
  - Detailed: person by day, with hours and coverage.
  - Simplified (print): Morning, Midday, Afternoon and Day off for each week, in the printed-sheet format.
  - Board (cards): weekly columns with color-coded cards per person and coverage per day.
- **Printing:** Print button on the schedule, with A4 or Letter paper and landscape or portrait orientation. "Fit to one page" (default) compacts the layout and scales it so the whole period, even a full month, fits one sheet; the brand and print date go in a tiny footer. Menus and buttons are left out. Inside the published artifact (where the browser blocks printing) it saves a printable HTML file that prints itself when opened.
- **Language:** English and Portuguese (BR), switchable from the header.
- **Theme:** button in the header switches between light and dark (the choice is saved; without a choice it follows the system).
- **Data export/import:**
  - Employees: CSV (opens in Excel, UTF-8) and JSON, with a template. Import from file or pasted text, with a preview and two modes: merge (update by name, add new) or replace the whole list. Rows with errors are skipped so nobody loses data silently.
  - Company: opening hours, coverage and rules as JSON.
  - Full backup: everything as JSON.
  - Data lives in the browser (localStorage); the schedule can also be copied as CSV.

### How to use

Open `index.html` in a browser. It is a single self-contained file (the Cube4Code symbol is embedded); `cube4code.png` is kept in the repository as the canonical asset. No build, server or login.

### Current limitations

- Data lives only in the browser of whoever uses it; it is not shared between people or devices.
- Manual changes are kept unless you explicitly choose to generate from scratch.

---

## Português

Aplicação web para montar escalas de trabalho semanais e mensais.

### Funcionalidades

- **Empresa:** horário de funcionamento por dia da semana (pode passar da meia-noite), pessoas necessárias ao mesmo tempo, duração do turno, turno parcial mínimo e descanso mínimo entre jornadas.
- **Funcionários (CRUD):** nome, cargo, limite de horas e dias por semana, situação ativo/inativo.
  - Restrições fixas (toda semana): dia todo, não depois de, não antes de, intervalo.
  - Entraves pontuais (data ou período): folga, consulta, curso etc.
- **Tipos de restrição por pessoa:** indisponível o dia todo, não depois de, não antes de, indisponível no intervalo, **só pode trabalhar entre** (ex.: só à noite) e **dias alternados** (ex.: sábado numa semana, domingo na outra). Fixas ou pontuais.
- **Regras por cargo:** mínimo e máximo de pessoas de cada cargo ao mesmo tempo (ex.: pelo menos 1 caixa, no máximo 1 supervisor). A geração respeita, encurtando um turno quando preciso para não passar do máximo.
- **Escala:** geração automática semanal ou mensal, equilibrando horas entre as pessoas e respeitando restrições, regras por cargo, limites e descanso.
- **Carga horária semanal:** depois de cobrir o mínimo, cada pessoa recebe turnos até completar a carga contratada (ex.: 5 × 7,5 h + 6,5 h = 44 h), onde há menos gente e evitando feriados.
- **Folga semanal em rodízio (opcional):** a folga de cada pessoa passa para o próximo dia permitido a cada semana (segunda, terça, quarta...), as pessoas começam em dias diferentes e a sequência continua da escala anterior salva. Cada pessoa pode ter dias preferidos para revezar (um dia só = folga fixa). A cobertura vem primeiro; quando um dia do rodízio precisa ser usado, a verificação avisa.
- **Domingos de folga:** cada pessoa tem pelo menos N domingos de folga por mês (padrão 1), planejados em rodízio para nenhum domingo ficar desfalcado; quem já folga aos domingos por restrição conta automaticamente.
- **Feriados:** feriados nacionais calculados automaticamente todo ano (inclusive Paixão de Cristo), com pontos facultativos opcionais (Carnaval, Corpus Christi) e feriados estaduais e municipais cadastráveis. Cada feriado pode ser marcado como empresa fechada. Com internet, a lista oficial é baixada da BrasilAPI (reserva: Nager.Date); sem internet, vale o cálculo automático.
- **Folga compensatória:** quem trabalha no feriado ganha uma folga a mais na semana seguinte (segunda a domingo), com a meta de horas da semana reduzida na mesma proporção. A verificação avisa se um ajuste manual tirar essa folga.
- **Verificação da escala:** cobertura, mínimo e máximo por cargo, restrições, limites semanais e descanso são verificados o tempo todo, inclusive após ajustes manuais. Conflitos são permitidos, mas sinalizados na tela (borda na célula, marcador no dia e painel de resumo) e nunca saem na impressão.
- **Escalas salvas:** cada mês ou semana gerada fica salva com seus ajustes manuais. A escala mensal usa semanas completas (segunda a domingo); a semana compartilhada com uma escala vizinha salva vem dela, então feriados trabalhados, folgas compensatórias e descanso passam de um mês para o outro.
- **Gerar, recalcular, fechar:** se o período já tem escala, Gerar pergunta se é para abrir a salva, recalcular mantendo os ajustes manuais ou gerar do zero. Recalcular refaz só a parte automática. Fechar deixa a escala definitiva (sem alterações até reabrir) e referência para as próximas.
- **Ajuste manual:** trocar a pessoa de um turno (com troca automática se a outra já tiver turno no dia), mudar horário, escalar alguém na folga, adicionar ou tirar pessoas da escala. Conflitos geram aviso.
- **Visualizações:**
  - Detalhada: pessoa por dia, com horas e cobertura.
  - Simplificada (impressão): Manhã, Intermediário, Tarde e Folga por semana, no formato da planilha impressa.
  - Quadro (cartões): colunas por dia com cartões coloridos por pessoa e cobertura de cada dia.
- **Impressão:** botão Imprimir na escala, com papel A4 ou Letter e orientação paisagem ou retrato. "Caber em uma página" (padrão) compacta o layout e ajusta a escala para o período inteiro, inclusive o mês, caber numa folha; marca e data de impressão vão num rodapé minúsculo. Menus e botões ficam de fora. Dentro do artefato publicado (onde o navegador bloqueia a impressão), salva um arquivo HTML que imprime sozinho ao ser aberto.
- **Idioma:** inglês e português (BR), com menu no cabeçalho.
- **Tema:** botão no topo para alternar entre claro e escuro (a escolha fica salva; sem escolha, segue o sistema).
- **Exportação/importação de dados:**
  - Funcionários: CSV (abre no Excel, UTF-8) e JSON, com modelo. Importação por arquivo ou texto colado, com pré-visualização e dois modos: mesclar (atualiza pelo nome, inclui novos) ou substituir a lista inteira. Linhas com erro não entram, para ninguém perder dados sem perceber.
  - Empresa: horários, cobertura e regras em JSON.
  - Backup completo: tudo em JSON.
  - Os dados ficam no navegador (localStorage); a escala também pode ser copiada em CSV.

### Como usar

Abra `index.html` no navegador. É um arquivo único e autossuficiente (o símbolo Cube4Code está embutido); `cube4code.png` fica no repositório como ativo canônico. Não há build, servidor nem login.

### Limitações atuais

- Os dados ficam só no navegador de quem usa; não são compartilhados entre pessoas ou aparelhos.
- Os ajustes manuais só se perdem se você escolher explicitamente gerar do zero.
