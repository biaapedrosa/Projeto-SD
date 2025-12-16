# Projeto-SD
🔐 **SafeCrack Pro – FSM para Cofre Digital (DE2-115)**

Projeto desenvolvido para a disciplina de Sistemas Digitais, com o objetivo de evoluir o SafeCrack FSM apresentado em sala de aula.
O sistema foi implementado em SystemVerilog, utilizando uma Máquina de Estados Finitos (FSM) para controlar um cofre digital com feedback visual por LEDs.

---

# 👩‍💻 Integrantes

- Beatriz Pandolfi Maroja  
- Beatriz Freitas Souza Pedrosa  
- Luísa Bispo Lócio  
- Marina Cabral Nogueira Lima  

---

# 🎯 Objetivo

Implementar um cofre digital que:

- Verifique uma senha composta por três dígitos  
- Indique o progresso da senha com LEDs verdes  
- Indique erro com LED vermelho  
- Utilize temporização para sinalizar erro e sucesso  
- Possa ser simulado no Quartus e executado na placa DE2-115  

---

# 🧠 Descrição do Sistema

O **SafeCrack Pro** funciona a partir da pressão de três botões físicos, que representam os três dígitos da senha.

O funcionamento geral é:

- O sistema inicia aguardando o primeiro dígito  
- Cada dígito correto faz a FSM avançar para o próximo estado  
- A quantidade de LEDs verdes acesos indica qual dígito está sendo aguardado  
- Caso um botão errado seja pressionado, o sistema entra em estado de erro  
- Após erro ou sucesso, o sistema retorna automaticamente ao estado inicial  

Todo o controle é feito por uma **FSM sincronizada por clock**.

---

# 💡 Feedback Visual (LEDs)

- 🟢 **1 LED verde** → aguardando o primeiro dígito  
- 🟢🟢 **2 LEDs verdes** → aguardando o segundo dígito  
- 🟢🟢🟢 **3 LEDs verdes** → aguardando o terceiro dígito  
- 🔴 **LED vermelho** → erro por 3 segundos  
- 🟢🟢🟢🟢🟢 **Todos os LEDs verdes** → cofre aberto por 5 segundos  

---

# 🔁 Máquina de Estados Finitos (FSM)

O diagrama de estados foi desenvolvido manualmente pelas integrantes do grupo e guiou toda a implementação do projeto.

---

# 🧩 Entradas e Saídas

- Botões físicos representam os dígitos da senha  
- LEDs verdes indicam o progresso da verificação  
- LED vermelho indica erro  
- O sistema utiliza o clock de **50 MHz** da placa **DE2-115**  

---

# 🐞 Possíveis Bugs (Known Issues)

- Botões “tremem” (*bounce*), podendo gerar múltiplos pulsos indesejados  
- Pressionar dois botões ao mesmo tempo pode gerar comportamento indefinido  
- Botões são ignorados durante os períodos de 3s (erro) e 5s (sucesso)  
- A temporização depende do clock utilizado  
- Cliques muito rápidos podem não ser detectados corretamente  
- Simulação e hardware real podem apresentar pequenas diferenças  

---
