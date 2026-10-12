# favorecidos-gasto-publico
Analysis of public spending by recipient (CPF or CNPJ)

# Data exploration

- There are four main sources in "Dados Abertos → Despesas Públicas":
	- "Documentos de empenho, liquidação e pagamento": This set comprises several CSV files, broken down by day. Since that would be very laborious, I chose to leave this dataset out.
	- "Execução da despesa": It is the one I used in the project "transparencia-primeiros-passos". It does not have information about the recipient.
	- "Recursos transferidos": the CSV file is called "Transferencias". Sum: R$ 26,466,883,982.22; Count: 206,196
	- "Recebimento de recursos por favorecido": Sum: R$ 91,271,810,659.01; Count: 736,840.
- Since the set "Recebimento de recursos por favorecido" is the most comprehensive one and is organised by month, I chose it.
- Dataset information:
	- Link: https://portaldatransparencia.gov.br/download-de-dados/despesas-favorecidos
	- Year: 2026
	- Month: September

# Findings

- The three recipients who received the most:
	- PAGAMENTO DA DIVIDA INTERNA → 2.529064e+11
	- PAGAMENTO DE BENEFICIOS - INSS/FRGPS → 8.503565e+10
	- PAGAMENTOS DO TESOURO AO INSS → 5.707347e+10
- The top value (2.529064e+11) is larger than the overall sum of 'Valor Recebido' (91,271,810,658.97) because the data contains both positive and negative values:
	- Sum of positive numbers → 657,440,705,131.76
	- Sum of negative numbers → -566,168,894,472.79
	- Total → 91,271,810,658.97
- Impact of the top three positive recipients (share of the positive sum):
	- PAGAMENTO DA DIVIDA INTERNA → 38.5%
	- PAGAMENTO DE BENEFICIOS - INSS/FRGPS → 12.9%
	- PAGAMENTOS DO TESOURO AO INSS → 8.7%
- Impact of the top three negative recipients (payers to the Brazilian treasury; share of the negative sum):
	- RECEBIMENTO DE EMISSAO DE TITULOS → 49.8%
	- RESGATE DE APLIC. DISPONIB. TN - ADM. DIV. PUBL → 39.9%
	- PAGAMENTOS DO INSS AO TESOURO NACIONAL → 9.9%
- A large proportion of the total financial transactions relates to the management of the public debt. In absolute terms, the Brazilian government received more than it paid on bonds (2.820507e+11 > 2.529064e+11). On the other hand, it paid more in social benefits than it received in contributions (5.580225e+10 < 8.503565e+10) — a pattern consistent with a deficit situation, where funds must be raised to cover welfare spending.
- There is a recipient called 'FOLHA DE PAGAMENTO', which totals R$ 1.234510e+10 (12.3 billion reais). Extrapolated over a year (12.3 × 12 ≈ 147.6 billion reais), this is of the same order of magnitude as the reported annual payroll spending of ~138 billion reais (source: Portal da Transparência), though the ~7% gap would warrant further checking (scope, partial-year effects). It also appears that individual public servant names are not displayed; payroll is aggregated under this single label.
- There is a notably high count (2,493 entries) for the recipient 'SEM INFORMACAO', totalling 6.330973e+09 (6.3 billion reais) — around 6.9% of the positive total. An amount of this size recorded without an identified recipient is a transparency gap worth flagging.