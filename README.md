# Cube4Shift

Aplicação web para montar escalas de trabalho semanais e mensais.

## Funcionalidades

- **Empresa:** horário de funcionamento por dia da semana (pode passar da meia-noite), pessoas necessárias ao mesmo tempo, duração do turno, turno parcial mínimo e descanso mínimo entre jornadas.
- **Funcionários (CRUD):** nome, cargo, limite de horas e dias por semana, situação ativo/inativo.
  - Restrições fixas (toda semana): dia todo, não depois de, não antes de, intervalo.
  - Entraves pontuais (data ou período): folga, consulta, curso etc.
- **Escala:** geração automática semanal ou mensal, equilibrando horas entre as pessoas e respeitando restrições, limites e descanso. Lacunas de cobertura são listadas.
- **Ajuste manual:** trocar a pessoa de um turno (com troca automática se a outra já tiver turno no dia), mudar horário, escalar alguém na folga, adicionar ou tirar pessoas da escala. Conflitos geram aviso.
- **Visualizações:** detalhada (pessoa por dia) e simplificada (Manhã, Intermediário, Tarde e Folga por semana, no formato da planilha impressa).
- **Tema:** botão no topo para alternar entre claro e escuro (a escolha fica salva; sem escolha, segue o sistema).
- **Dados:** salvos no navegador (localStorage), com backup e importação em JSON e cópia da escala em CSV.

## Como usar

Abra `index.html` no navegador. Não há build, servidor nem login.

## Limitações atuais

- Os dados ficam só no navegador de quem usa; não são compartilhados entre pessoas ou aparelhos.
- Gerar a escala de novo descarta os ajustes manuais da escala anterior.
- No modo mensal, a primeira e a última semana aparecem cortadas no limite do mês.
