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
- **Schedule check:** coverage, role minimum/maximum, restrictions, weekly limits and rest are verified continuously, including after manual changes. Conflicts are allowed but flagged on screen (cell outline, day marker and a summary panel) and never printed.
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
- Generating the schedule again discards manual adjustments made to the previous one.
- In monthly mode, the first and last weeks are cut at the month boundary.

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
- **Verificação da escala:** cobertura, mínimo e máximo por cargo, restrições, limites semanais e descanso são verificados o tempo todo, inclusive após ajustes manuais. Conflitos são permitidos, mas sinalizados na tela (borda na célula, marcador no dia e painel de resumo) e nunca saem na impressão.
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
- Gerar a escala de novo descarta os ajustes manuais da escala anterior.
- No modo mensal, a primeira e a última semana aparecem cortadas no limite do mês.
