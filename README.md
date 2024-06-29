# Desafio Dio - Criando um App de Lembretes e Tarefas com Swift



### **Projeto para criar um aplicativo de lembretes e tarefas com Swift:**



Neste projeto, vamos criar um aplicativo de lembretes e tarefas simples usando Swift. O aplicativo permitirá que os usuários criem, visualizem, marquem como concluídas e excluam tarefas e lembretes.



### **Pré-requisitos**

- Xcode 14 ou superior
- Swift 5.7 ou superior



### **Criando o Projeto**



1. Abra o Xcode e clique em "Criar um novo projeto".
2. Selecione o modelo "Aplicativo de visualização única".
3. Insira um nome para o seu projeto (por exemplo, "Lembretes") e clique em "Avançar".
4. Selecione um local para o seu projeto e clique em "Criar".



### **Interface do Usuário**



Vamos criar uma interface de usuário simples com um campo de texto para inserir novas tarefas, uma tabela para exibir as tarefas e botões para adicionar, marcar como concluída e excluir tarefas.



No arquivo `ContentView.swift`, adicione o seguinte código:

swift



```swift
import SwiftUI

struct ContentView: View {
    @State private var tasks = [""]

    var body: some View {
        NavigationView {
            List {
                ForEach(tasks, id: \.self) { task in
                    Text(task)
                }
            }
            .toolbar {
                ToolbarItem(placement: .navigationBarTrailing) {
                    Button(action: addTask) {
                        Label("Adicionar", systemImage: "plus")
                    }
                }
                ToolbarItem(placement: .navigationBarLeading) {
                    EditButton()
                }
            }
        }
    }

    func addTask() {
        tasks.append("")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```



### **Lógica do Aplicativo**



Agora, vamos adicionar a lógica do aplicativo para adicionar, marcar como concluída e excluir tarefas.

No arquivo `ContentView.swift`, adicione as seguintes funções:

swift



```swift
func addTask() {
    tasks.append("")
}

func markTaskAsDone(at index: Int) {
    tasks[index] = "~~\(tasks[index])~~"
}

func deleteTask(at index: Int) {
    tasks.remove(at: index)
}
```



#### **Executando o Aplicativo**

Para executar o aplicativo, clique no botão "Executar" no Xcode. O aplicativo será executado no simulador ou dispositivo conectado.



### **Conclusão**

Neste projeto, criamos um aplicativo de lembretes e tarefas simples usando Swift. O aplicativo permite que os usuários criem, visualizem, marquem como concluídas e excluam tarefas e lembretes. Este é apenas um exemplo básico e você pode personalizar o aplicativo para atender às suas necessidades específicas.
