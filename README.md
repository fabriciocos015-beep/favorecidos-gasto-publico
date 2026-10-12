# favorecidos-gasto-publico
Analysis of public spending by recipient (CPF or CNPJ)

# Data exploration

- There are four main sources in "Dados Abertos → Despesas Públicas":
	- "Documentos de empenho, liquidação e pagamento": This set comprises several CSV files, broken down by day. Since that would be very laborious, I preferred to let this dataset out.
	- "Execução da despesa": Is is the one I used in the project "transparencia-primeiros-passos". It does not have information about the recipient.
	- "Recursos transferidos": the CSV file is called "Transferencias". Sum: R$ 26,466,883,982.22; Count: 206,196
	- "Recebimento de recursos por favorecido":  Sum: R$ 91,271,810,659.01; Count: 736,840. 
		- Obs.: I did not find my own name. Since I am a civil servant, I thought my monthly payment would be here.
- Since the set "==Recebimento de recursos por favorecido==" is the most comprehensive one and it is by month, it was chosen. 
- Dataset information:
	- Link: https://portaldatransparencia.gov.br/download-de-dados/despesas-favorecidos
	- Year: 2026
	- Month: September

# Findings

- The three recipients who received the most:
	- PAGAMENTO DA DIVIDA INTERNA → 2.529064e+11
	- PAGAMENTO DE BENEFICIOS - INSS/FRGPS → 8.503565e+10
	- PAGAMENTOS DO TESOURO AO INSS → 5.707347e+10
- 2.529064e+11 is bigger than the sum of 'Valor Recebido' (91,271,810,658.97) because there are positive and negative values.
	- Sum of positive numbers → 657,440,705,131.76
	- Sum of negative numbers → -566,168,894,472.79
	- Total → 91,271,810,658.97
- Impact of the top three positive recipients (over positive sum):
	- PAGAMENTO DA DIVIDA INTERNA → 38.5%
	- PAGAMENTO DE BENEFICIOS - INSS/FRGPS → 12.9%
	- PAGAMENTOS DO TESOURO AO INSS → 8.7%
- Impact of the top three negative recipients (payers to the Brazilian treasury; over negative sum):
	- RECEBIMENTO DE EMISSAO DE TITULOS → 49.8%
	- RESGATE DE APLIC. DISPONIB. TN - ADM. DIV. PUBL → 39.9% 
	- PAGAMENTOS DO INSS AO TESOURO NACIONAL → 9.9%
- As can be seen, a large proportion of the total financial transactions has to with the management of the public debt. In absolute numbers, the Brazilian government is receiving more than paying for bonds (2.820507e+11 > 2.529064e+11). On the other hand, it is paying more for social benefits than receiving contributions (5.580225e+10 < 8.503565e+10). It is symptomatic of a deficit situation, where money is demanded to pay for welfare.
- My name was not listed directly, but there is a recipiente called 'FOLHA DE PAGAMENTO', which totals R$ 1.234510e+10 (12.3 billion reais). 12.3 x 12 = 147.6 billion reais per year, which is consisted with the annual amount spent of 138 billion reais (source: Portal da Transparência).
- There is a large number (2493) for the recipient 'SEM INFORMACAO', which totals 6.330973e+09 (6.3 billion reais). It looks like a considerable amount (6.9%) without adequate transparency.