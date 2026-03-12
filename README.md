# SISTEMA DE GESTÃO DE ESTOQUE - SUZUKI SÃO JOÃO DA BOA VISTA
# Desenvolvido por Elias Pires

def exibir_menu():
    print("\n" + "="*40)
    print("      SUZUKI INVENTORY MANAGER 1.0")
    print("="*40)
    print("1. Cadastrar Veículo")
    print("2. Listar Estoque Atual")
    print("3. Valor Total em Pátio (R$)")
    print("4. Sair")
    print("="*40)

def sistema_gestao():
    estoque = []
    
    while True:
        exibir_menu()
        opcao = input("Escolha uma opção: ")

        if opcao == '1':
            modelo = input("Modelo da Moto: ")
            cor = input("Cor: ")
            preco = float(input("Preço (R$): "))
            estoque.append({"modelo": modelo, "cor": cor, "preco": preco})
            print(f"\n✅ {modelo} adicionada ao estoque!")

        elif opcao == '2':
            print("\n--- RELATÓRIO DE ESTOQUE ---")
            if not estoque:
                print("O pátio está vazio no momento.")
            for i, moto in enumerate(estoque, 1):
                print(f"{i}. {moto['modelo']} | Cor: {moto['cor']} | Valor: R$ {moto['preco']:,.2f}")

        elif opcao == '3':
            total = sum(moto['preco'] for moto in estoque)
            print(f"\n💰 Investimento Total em Pátio: R$ {total:,.2f}")

        elif opcao == '4':
            print("Encerrando sistema... Boas vendas!")
            break
        else:
            print("Opção inválida!")

if __name__ == "__main__":
    sistema_gestao()
