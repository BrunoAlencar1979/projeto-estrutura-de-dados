# projeto-estrutura-de-dados

ABK Bus Lines - Sistema de Vendas de Passagens de Ônibus
Descrição
Este projeto é um sistema de vendas de passagens de ônibus, desenvolvido em C, que simula uma experiência de compra de passagens de ônibus para a empresa fictícia ABK Bus Lines. Ele foi construído com o objetivo de praticar lógica de programação e conceitos de sistemas embarcados.

O sistema permite que os usuários realizem cadastros, façam login e comprem passagens para diferentes destinos. Além disso, administradores podem visualizar relatórios detalhados de vendas. O código foi criado para rodar em ambiente terminal e não requer interfaces gráficas, tornando-o ideal para sistemas simples ou dispositivos com recursos limitados.

Funcionalidades
Para Usuários:
Cadastro de usuário: Nome, e-mail, senha, CPF e endereço completo (CEP, rua, cidade e bairro).
Login de usuário: Autenticação com e-mail e senha previamente cadastrados.
Compra de passagens:
Usuários podem selecionar uma viagem entre três rotas diferentes.
Inserir a data e horário de embarque.
Receber um ticket detalhado com todas as informações da viagem.
Notificações de atrasos para algumas viagens (exemplo: acréscimo de 4 horas na rota Vitória-Linhares).
Para Administradores:
Relatório de vendas:
Exibe um relatório com todos os passageiros que compraram passagens.
Exibe o total arrecadado com as vendas.
Somente administradores com a senha correta podem acessar o relatório.
Fluxo do Sistema
1. Menu Principal
Ao abrir o programa, o usuário é saudado com o menu principal, onde pode escolher entre as seguintes opções:

bash
Copiar código
--- Menu Principal | ABK Bus Lines ---
1. Login como Usuário
2. Login como Administrador
3. Cadastro de Usuário
0. Sair
2. Cadastro de Usuário
Na opção 3, o usuário pode se cadastrar no sistema, fornecendo os seguintes dados:

Nome: Nome completo do usuário.
E-mail: O e-mail deve conter um '@' para ser considerado válido.
Senha: O usuário precisará digitar e confirmar sua senha.
CPF: Deve conter exatamente 11 dígitos numéricos.
Endereço completo: CEP, rua, cidade e bairro.
Após o cadastro, o usuário será redirecionado de volta ao menu de login para acessar sua conta.

3. Login de Usuário
Na opção 1, o usuário pode fazer login com o e-mail e senha fornecidos no cadastro. Se o login for bem-sucedido, ele verá uma mensagem de boas-vindas com seu nome.

4. Menu de Passagens
Após o login, o usuário acessará o menu de passagens com três opções de viagens:

bash
Copiar código
--- Menu de Passagens ---
1. Vitória -> Linhares (R$ 78.05, 2h30min)
2. Vitória -> Jaguaré (R$ 113.88, 3h45min)
3. Vitória -> São Mateus (R$ 123.49, 4h)
0. Voltar ao Menu Principal
O usuário escolherá uma viagem, e o sistema solicitará as seguintes informações:

Data de embarque (no formato dd/mm/aaaa)
Horário de embarque (no formato hh:mm)
Se a viagem escolhida for a rota Vitória-Linhares, o sistema informará ao usuário sobre um atraso de 4 horas e ajustará o horário de chegada.

5. Confirmação de Compra
Após fornecer as informações de viagem, o sistema exibirá um resumo da compra e pedirá a confirmação do usuário. Se o usuário confirmar, o sistema emitirá um ticket com todas as informações da viagem, incluindo o nome da empresa, nome do passageiro, CPF, horário de embarque, duração e horário de chegada. Além disso, o ticket exibirá o atraso de 4 horas, se aplicável.

6. Relatório de Vendas (Administrador)
Somente o administrador, usando a senha admin, pode acessar o relatório de vendas. Este relatório exibe:

Lista de passagens vendidas com nome dos passageiros, rota, valor e horários.
Total arrecadado com as vendas de passagens.
Exemplo de Uso
Cadastro de Usuário
bash
Copiar código
--- Cadastro de Usuário ---
Nome: João Silva
E-mail: joao@exemplo.com
Senha: ****
Confirme a senha: ****
CPF: 12345678910
CEP: 29100-000
Rua: Avenida Central
Cidade: Vitória
Bairro: Centro
Usuário cadastrado com sucesso!
Login de Usuário
bash
Copiar código
--- Login de Usuário ---
Digite o seu e-mail: joao@exemplo.com
Digite a sua senha: ****
Bem-vindo(a), João Silva! Login efetuado com sucesso.
Compra de Passagem
bash
Copiar código
--- Menu de Passagens ---
1. Vitória -> Linhares (R$ 78.05, 2h30min)
2. Vitória -> Jaguaré (R$ 113.88, 3h45min)
3. Vitória -> São Mateus (R$ 123.49, 4h)
Escolha uma viagem: 1
Digite a data de embarque (dd/mm/aaaa): 10/09/2024
Digite o horário de embarque (hh:mm): 14:30
Atenção: Esta viagem tem um atraso de 4 horas!
Confirmar compra? (s/n): s
--- Ticket de Viagem ---
Empresa: ABK Bus Lines
Nome do Passageiro: João Silva
CPF: 12345678910
Origem: Vitória
Destino: Linhares
Valor da Passagem: R$ 78.05
Horário de Embarque: 14:30
Horário de Chegada: 21:00
Atenção: Esta viagem tem um atraso de 4 horas!
Relatório de Vendas (Administrador)
bash
Copiar código
--- Relatório de Vendas ---
Passagem 1: João Silva - Vitória -> Linhares - R$ 78.05
Passagem 2: Maria Souza - Vitória -> Jaguaré - R$ 113.88
Total arrecadado: R$ 191.93
Estrutura de Dados
O projeto usa structs simples para representar o usuário e a viagem:

c
Copiar código
typedef struct {
    char nome[MAX_NOME];
    char email[MAX_EMAIL];
    char senha[MAX_SENHA];
    char cpf[MAX_CPF];
    char cep[MAX_CEP];
    char rua[MAX_ENDERECO];
    char cidade[MAX_CIDADE];
    char bairro[MAX_BAIRRO];
} Usuario;
Como Compilar e Executar
Clone o repositório:

bash
Copiar código
git clone https://github.com/seu-usuario/abk-bus-lines.git
cd abk-bus-lines
Compile o programa:

bash
Copiar código
gcc main.c -o abk_buslines
Execute o programa:

bash
Copiar código
./abk_buslines
Contribuição
Se você deseja contribuir para este projeto:

Faça um fork do repositório.
Crie um branch para sua modificação: git checkout -b minha-modificacao.
Faça as alterações desejadas e faça o commit: git commit -m 'Minha modificação'.
Faça um push para o branch: git push origin minha-modificacao.
Abra um Pull Request.
Licença
Este projeto está sob a licença MIT. Sinta-se à vontade para usá-lo, modificá-lo e distribuí-lo.
