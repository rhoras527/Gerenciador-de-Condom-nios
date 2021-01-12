# Gerenciador-de-Condom-nios



#Nomes: Raiara Horas e Vagner Aquino

#Menu de Opções
def menu():
    print('''
-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
|            TELA INICIAL               |
-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
|    1. CADASTRO DE FUNCIONÁRIOS        |
|    2. Listar Funcionários             |
|    3. Consulta Funcionários por ID    |
|    4. CADASTRO DE DESPESAS            |
|    5. Listar Despesas                 |
|    6. Consultar Despesas por ID       |
|    7. CADASTRO DE MORADORES           |
|    8. Listar Moradores                |
|    9. Consultar Moradores por ID      |
|   10. Sair                            |
-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
    ''')

    
#Cadastro de Funcionários
def cadastrar(funcionarios):
    print('''

****************************************
       Cadastro de Funcionários
****************************************
''')
    codigo = input('Código: ') 
    nome = input('Nome: ')
    função = input('Função: ')
    salario = input('Salario: ')
    setor = input('Setor: ')
    admissão = input('Data Admissão: ')
    funcionarios.append((codigo, nome, função, salario, setor, admissão))
    print('''
****************************************

''')


#Cadastro de Despesas
def cadastrar1(despesas):
    print('''

****************************************
        Cadastro de Despesas
****************************************

''')
    codigo = input('Código: ')
    descrição = input('Descrição: ')
    valor = float(input('Valor: R$'))
    data = input('Data: ')
    despesas.append((codigo, descrição, valor, data))
    print('''
****************************************

''')


#Cadastro de Moradores   
def cadastrar2(moradores):
    print('''

****************************************
         Cadastro de Moradores
****************************************
''')
    codigo = input('Código: ')
    nome = input('Nome: ')
    casa = int(input('Número da Casa: '))
    moradores.append((codigo, nome, casa))
    print('''
****************************************

''')


#Listagem de Funcionários
def listar(funcionarios):
    print('''
                
++++++++++++++++++++++++++++++++++++++++
          Lista de Funcionários:
++++++++++++++++++++++++++++++++++++++++
''')
    for funcionario in funcionarios:
        codigo, nome, função, salario, setor, admissão = funcionario
        print(f'\n Código: {codigo} | Nome: {nome} | Função: {função} | Sálario: R${salario} | Setor: {setor} | Data Admissão: {admissão} ')
    print('''
++++++++++++++++++++++++++++++++++++++++
                  
''')


#Listagem de Despesas
def listar1(despesas):
    print('''
                    
++++++++++++++++++++++++++++++++++++++++
             Lista de Despesas:
++++++++++++++++++++++++++++++++++++++++
''')
    for despesa in despesas:
        codigo, descrição, valor, data = despesa
        print(f'\nCódigo: {codigo} | Descrição: {descrição} | Valor: {valor} | Data: {data}')
    print('''
++++++++++++++++++++++++++++++++++++++++
                   
''')


#Listagem de Moradores      
def listar2(moradores):
    print('''
                     
++++++++++++++++++++++++++++++++++++++++
            Lista de Moradores:
++++++++++++++++++++++++++++++++++++++++
''')
    for morador in moradores:
        codigo, nome, casa = morador
        print(f'\nCódigo: {codigo} | Nome: {nome} | Casa: {casa}')
    print('''
++++++++++++++++++++++++++++++++++++++++  
                   
''')


#Consulta por ID Funcionários
def buscar(funcionarios):
    codigo_desejado = input('Id? ')
    for funcionario in funcionarios:
        codigo, nome, função, salario, setor, admissão = funcionario
        if codigo == codigo_desejado:
            print('''
                 
 ººººººººººººººººººººººººººººººººººººººº                 
               Consulta:
 ººººººººººººººººººººººººººººººººººººººº
''')
            print(f' Nome: {nome} | Função: {função} | Código: {codigo} | Salário: R$ {salario} | Data Admissão: {admissão}')
            break
    else:
        print(f'Funcionario com Código {codigo_desejado} não encontrada')
    print('''
 ººººººººººººººººººººººººººººººººººººººº
                 
''')


#Consulta por ID Despesas
def buscar1(despesas):
    print('-' * 79)
    codigo_desejado = input('Id? ')
    for despesa in despesas:
        codigo, descrição, valor, data = despesa
        if codigo == codigo_desejado:
            print('''
                 
 ººººººººººººººººººººººººººººººººººººººº
               Consulta:
 ººººººººººººººººººººººººººººººººººººººº
''')
            print(f' Descrição: {descrição} | Valor: R$ {valor} | Código: {codigo} | Data: {data}')
            break
    else:
        print(f'Despesa com código {codigo_desejado} não encontrada')
    print('''
 ººººººººººººººººººººººººººººººººººººººº
                 
''')


#Consulta por ID Moradores
def buscar2(moradores):
    print('-' * 79)
    codigo_desejado = input('Id? ')
    for morador in moradores:
        codigo, nome, casa = morador
        if codigo == codigo_desejado:
            print('''
                 
 ººººººººººººººººººººººººººººººººººººººº 
                Consulta:
 ººººººººººººººººººººººººººººººººººººººº
''')
            print(f' Nome: {nome} | Casa: {casa} | Código: {codigo}')
            break
    else:
        print(f'Morador com código {codigo_desejado} não encontrada')
    print('''
 ººººººººººººººººººººººººººººººººººººººº
                   
''')


#Função Principal
def main():
    funcionarios = []
    despesas = []
    moradores = []

    while True:
        menu()
        opcao = int(input('''
        Escolha uma opção:

'''))
        if opcao == 1:
            cadastrar(funcionarios)
        elif opcao == 2:
            listar(funcionarios)
        elif opcao == 3:
            buscar(funcionarios)
        elif opcao == 4:
            cadastrar1(despesas)
        elif opcao == 5:
            listar1(despesas)
        elif opcao == 6:
            buscar1(despesas)
        elif opcao == 7:
            cadastrar2(moradores)
        elif opcao == 8:
            listar2(moradores)
        elif opcao == 9:
            buscar2(moradores)
        elif opcao == 10:
            print('Saindo do Sistema')
            break
        else:
            print('Opção inválida')

main()
