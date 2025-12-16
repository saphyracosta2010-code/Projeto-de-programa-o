catalogo = [{"livro": "O Pequeno Príncipe", "autor": "Antoine de Saint-Exupéry"},
{"livro": "Percy Jackson e os Olimpianos", "autor": "Rick Riordan"},
{"livro": "Harry Potter e o Prisioneiro de Azkaban", "autor": "J. K. Rowling"},
{"livro": "Sherlock Holmes e o Cão dos Baskerville", "autor": "Arthur Conan Doyle"},
{"livro": "O Senhor dos Anéis", "autor": "J. R. R. Tolkien"},
{"livro": "Guerra e Paz", "autor": "Liev Tolstói"},
{"livro": "Memórias Póstumas de Brás Cubas", "autor": "Machado de Assis"},
{"livro": "Jogos Vorazes: O Amanhecer na Colheita", "autor": "Suzanne Collins"},
{"livro": "Revolução dos Bichos", "autor": "George Orwell"},
{"livro": "O Diário de Anne Frank", "autor": "Anne Frank"},
{"livro": "Alice no País das Maravilhas", "autor": "Lewis Carroll"},
{"livro": "As Crônicas de Nárnia: O Leão, a Feiticeira e o Guarda-Roupa", "autor": "C. S. Lewis"}]


generos = {"fantasia": ["Harry Potter e o Prisioneiro de Azkaban", "O Senhor dos Anéis", "As Crônicas de Nárnia: O Leão, a Feiticeira e o Guarda-Roupa"],
"aventura": ["Percy Jackson e os Olimpianos","Jogos Vorazes: O Amanhecer na Colheita"],
"romance histórico": ["Guerra e Paz"],
"romance / realismo":["Memórias Póstumas de Brás Cubas"],
"distopia / ficção científica": ["Jogos Vorazes: O Amanhecer na Colheita"],
"mistério / romance policial": ["Sherlock Holmes e o Cão dos Baskerville"],
"sátira política / alegoria": ["Revolução dos Bichos"],
"autobiografia / diário": ["O Diário de Anne Frank"],
"literatura infantil-juvenil": ["O Pequeno Príncipe","Alice no País das Maravilhas"]}

favoritos = []

def listar_livros():
    print("Estes são os livros da biblioteca:")
    for registro in catalogo:
        print(f"Livro: {registro['livro']} | Autor: {registro['autor']}")


def cadastrar():
    livro = input("Digite seu livro: ").strip()
    autor = input("Digite o nome do autor do livro: ").strip()
    genero = input("Digite o genero do livro: ").strip().lower()
    cadastro = {"livro": livro, "autor": autor, "genero": genero}
    catalogo.append({"livro": livro, "autor": autor})
    if genero in generos:
        generos[genero].append(livro)
    else:
        generos[genero] = [livro]

    print("Cadastro realizado")
    print("livro:", cadastro["livro"])
    print("autor:", cadastro["autor"])
    print("genero:", cadastro["genero"])



def remover():
    livro = input("Digite o nome do livro: ").strip().lower()

    for registro in catalogo[:]:
        if registro["livro"].strip().lower() == livro:
            catalogo.remove(registro)
            
            for genero in generos:
                if registro["livro"] in generos[genero]:
                    generos[genero].remove(registro["livro"])

            if registro["livro"] in favoritos:
                favoritos.remove(registro["livro"])

            print("Livro removido")
            return

    print("Livro não encontrado")

    

def buscar_livros():
    genero = input("Digite o gênero literário: ").strip().lower()
    if genero in generos:
        print("Livros encontrados:")
        for livro in generos[genero]:
            print(livro)
    else:
        print("Gênero não encontrado.")


def adicionar_favorito():
    livro = input("Digite o nome do livro que deseja adicionar aos favoritos: ").strip().lower()
    for registro in catalogo:
        if registro["livro"].strip().lower() == livro:
            if registro["livro"] in favoritos:
                print("Este livro já está nos favoritos!")
            else:
                favoritos.append(registro["livro"])
                print(f"Livro '{registro['livro']}' adicionado aos favoritos!")
            return

    print("Livro não encontrado no catálogo. Não é possível adicionar.")

def listar_favoritos():
    if not favoritos:
        print("Nenhum livro favorito adicionado.")
        return

    print("=== LIVROS FAVORITOS ===")
    for livro in favoritos:
        print(livro)


        
def menu():
    while True:
        print("=== SISTEMA DA BIBLIOTECA ===")
        print("1 - Listar acervo")
        print("2 - Cadastrar")
        print("3 - Remover")
        print("4 - Buscar livros")
        print("5 - Adicionar livro aos favoritos")
        print("6 - Listar favoritos")
        print("7 - Sair")

        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            listar_livros()
        elif opcao == "2":
            cadastrar()
        elif opcao == "3":
            remover()
        elif opcao == "4":
            buscar_livros()
        elif opcao == "5":
            adicionar_favorito()
        elif opcao == "6":
            listar_favoritos()
        elif opcao == "7":
            print("Encerrando o sistema")
            break
        else:
            print("Opção inválida Tente novamente")


menu()


        
