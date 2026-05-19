# Tempos_Correcao

Nessa iniciativa, tem dois códigos no formato notebook. O Extracao_Meses contém um pipeline para extração dos dados através do próprio site da RED1000, portanto precisa atualizar o token sempre que for fazer a extração. O passo a passo para extrair esse token é: ir no dashboard de correções, inspecionar a página, ir na aba de rede, procurar a requisição que a página faz para API (começa com "correcoes?"), ir no cabeçalho de requisições (aba cabeçalho) e procurar o campo "authorization"; vai ser uma string grande que começa com "RED1000". Basta então copiar e colar esse token na função principal do código de extração:

if __name__ == "__main__":
    # Carrega o token de variável de ambiente ou define inline
    token = os.getenv("RED1000_TOKEN")
    if not token:
        token = 

Por fim, o arquivo Analises.ipynb possui as análises estatísticas da comparação entre os tempos de correção e revisão humanas. No código, está especificado o período de Março e Outubro em que era certeza de ser exclusivamente correção humana, portanto os datasets foram meclados para formar o conjunto amostral de redações corrigidas por humanos e comparar com o período de Novembro em que também era certeza de a correção automatizada estar operando e existia apenas a revisão humana.
