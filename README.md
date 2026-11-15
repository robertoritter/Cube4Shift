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
- **Schedule:** automatic weekly or monthly generation that balances hours across people and respects restrictions, limits and rest. Coverage gaps are listed.
- **Manual adjustments:** change the person on a shift (swapping automatically if the other person already works that day), change times, schedule someone on a day off, add or remove people from the schedule. Conflicts raise a warning.
- **Views:**
  - Detailed: person by day, with hours and coverage.
  - Simplified (print): Morning, Midday, Afternoon and Day off for each week, in the printed-sheet format.
  - Board (cards): weekly columns with color-coded cards per person and coverage per day.
- **Language:** English and Portuguese (BR), switchable from the header.
- **Theme:** button in the header switches between light and dark (the choice is saved; without a choice it follows the system).
- **Data:** saved in the browser (localStorage), with JSON backup and import, and CSV copy of the schedule.

### How to use

Open `index.html` in a browser, keeping `cube4code.png` in the same folder. No build, server or login.

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
- **Escala:** geração automática semanal ou mensal, equilibrando horas entre as pessoas e respeitando restrições, limites e descanso. Lacunas de cobertura são listadas.
- **Ajuste manual:** trocar a pessoa de um turno (com troca automática se a outra já tiver turno no dia), mudar horário, escalar alguém na folga, adicionar ou tirar pessoas da escala. Conflitos geram aviso.
- **Visualizações:**
  - Detalhada: pessoa por dia, com horas e cobertura.
  - Simplificada (impressão): Manhã, Intermediário, Tarde e Folga por semana, no formato da planilha impressa.
  - Quadro (cartões): colunas por dia com cartões coloridos por pessoa e cobertura de cada dia.
- **Idioma:** inglês e português (BR), com menu no cabeçalho.
- **Tema:** botão no topo para alternar entre claro e escuro (a escolha fica salva; sem escolha, segue o sistema).
- **Dados:** salvos no navegador (localStorage), com backup e importação em JSON e cópia da escala em CSV.

### Como usar

Abra `index.html` no navegador, mantendo `cube4code.png` na mesma pasta. Não há build, servidor nem login.

### Limitações atuais

- Os dados ficam só no navegador de quem usa; não são compartilhados entre pessoas ou aparelhos.
- Gerar a escala de novo descarta os ajustes manuais da escala anterior.
- No modo mensal, a primeira e a última semana aparecem cortadas no limite do mês.
