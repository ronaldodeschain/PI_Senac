
# SERVIÇO NACIONAL DE APRENDIZAGEM COMERCIAL - SENAC 

## CURSO TÉCNICO EM DESENVOLVIMENTO DE SISTEMAS 

 

 

 

 

## Ronaldo Lemos da Silva 

 


 

 

# PROJETO INTEGRADOR 

# NOME DO PROJETO 

 

 

 

 

 

 

 

Porto Alegre 

2025 AGRADECIMENTOS 

 

XXXXXXXXXXXXXXXXX 

 

. 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

# 1. INTRODUÇÃO 

 

 

 

Sistema de monitoramento de buracos no perímetro urbano 

 

## Apresentação Geral do Projeto 

 

Visando ter um controle e mapear os buracos de Porto Alegre surgiu a ideia de criar uma aplicação onde os usuários podem enviar fotos dos locais onde há buracos na via publica. 
O usuário poderá verificar os buracos em um raio a partir da sua geolocalização e evitar vias acidentadas ou usar como uma ferramenta para solicitar intervenção da prefeitura. 

 

# Objetivos 

 

## Objetivo Geral 

Mapear os buracos de Porto Alegre em um mapa interativo em tempo real. 

 

## Objetivos Específicos 

Permitir a inserção de novos dados do usuário e visualizar os buracos já mapeados pela comunidade utilizadora do sistema 

 

# Arquitetura do Sistema (Modelagem) 

 

 

- Incluir o banco de dados. 

- Api Waze ou Google maps 

- Api para validar imagens 

- Api para compressão de imagens - Pillow 

- Api para extrair metadata das imagens 

- Django 

 

 

 

 

# 3.1 Requisitos  

 

## Requisitos Funcionais 

 

- Efetuar login – manter seção 

- Enviar fotografias de buracos 

- Tratamento das imagens 

- Enviar notificação para a prefeitura 

- Requisitos Não Funcionais 

 

O tempo de desenvolvimento não deve ultrapassar 24 meses. 

O sistema deve estar disponível 7 por 7. 

 

## 3.2 Modelagem Funcional 

## Lista dos Atores 



Administrador 

Controle sobre ferramentas do sistema – editar, apagar e verificar fotos  

 

Usuário 

Envia fotografias dos buracos para o sistema, navega e interage com as marcações nos mapas 

 

## Diagrama de Casos de Uso 

 

 

 

 

 

 

 

 

 

 

# Detalhamento dos casos de uso 

 

Nesta seção será apresentado o detalhamento dos seguintes casos de uso: 

- Efetuar Login. 

- Manter Cadastro. 

- Enviar fotografias de Buracos. 

- Manter Fotos do Usuário. 

- Manter Fotos de Local. 

 

 

 

CSU01 – Efetuar login 

Caso de Uso  1 

Efetuar Login 

Objetivo 

Permitir que o usuário interaja com o Sistema 

Ator 

Administrador/Usuario 

Pré-condições 

Conta cadastrada 

Cenário Principal 

1. A página solicita que o usuário preencha seus dados de acesso 

2. O usuário preenche os campos 

3. O usuário clica em login 

4. A página realiza o processo. 

5. Fim do caso de uso 

 

Cenário Alternativo 

 

1. O usuário clica no botão Criar conta 

2. A página realiza o processo de abrir página de cadastro 

3. Fim do caso de uso 

 

Cenário de Exceção Principal 

 

1.Um ou mais dados do login está em branco 

1.1.Retorna a mensagem "Preencha os campos para login" 

1.2.Retorna ao passo 1 

2.Um ou mais dados estão incorretos 

2.1.Retorna a mensagem "Login ou senha inválidos" 

2.2.Retorna ao Passo 1 

2.3. Fim do caso de uso 

 

 

 

 

 

 

CSU02 – Manter Cadastro 

Caso de Uso  2 

Manter Cadastro 

Objetivo 

Permitir que o usuário altere, visualize e apague os dados do seu cadastro 

Ator 

Usuário/Administrador 

Pré-condições 

Conta cadastrada 

1. A página exibe os dados cadastrais 

2. O usuário seleciona um dos campos de dados para fazer alteração 

3. O usuário altera os dados do campo 

4. O usuário clica em "atualizar dados cadastrais" 

5. A página realiza o processo 

6. A página volta a tela de exibição dos dados cadastrais. 

7. fim do caso de uso 

 

Cenário Alternativo 

 

1. A página exibe os dados cadastrais 

2. O usuário seleciona "apagar minha conta" 

3. A página envia uma mensagem de confirmação 

4. O cliente confirma a ação 

5. A página realiza o processo 

6. A página redireciona para home. 

7. Fim do caso de uso 

 

Cenário Exceção Principal 

 

4. O usuário tenta enviar o campo em branco 

4.1.1 A página exibe a mensagem "preencha os dados" 

4.1.2 A página retorna para "2" 

4.2.1 O usuário envia dados não permitidos 

4.2.2 A página exibe a mensagem "dados inválidos". 

4.2.3 A página retorna para "2". 

4.3 Fim do caso de uso 

 

 

 

 

CSU03 – Enviar fotografias de buracos 

Caso de Uso  3 

Enviar fotografias de buracos 

Objetivo 

Permitir que o usuário envie fotos dos buracos para alimentar o sistema 

Ator 

Usuário 

Pré-condições 

Conta cadastrada 

Cenário Principal 

 

1. A página solicita que o usuário carregue uma foto para ser enviada 

2. O usuário clica no botão "Selecionar foto" 

3. O usuário clica em "Enviar foto". 

4. A página realiza o processo. 

5. Fim do caso de uso 

 

Cenário Alternativo 

 

1. A página solicita que o usuário carregue uma foto para ser enviada 

2. O usuário clica no botão "Selecionar foto" 

3. O usuário clica em "Cancelar envio". 

4. A página realiza o processo. 

5. Fim do caso de uso 

 

Cenário de Exceção Principal 

 

1.A foto enviada é irregular 

1.1. A página envia a mensagem "Envie apenas foto de buraco em via pública" 

1.2. Retorna ao passo 1. 

2. Falha ao salvar o arquivo no banco de dados 

2.1.A página envia a mensagem “Falha ao carregar imagem, tente novamente.” 

2.2.A página retorna a etapa 1. 

1.3. Fim do caso de uso 

 

 

CSU04 – Manter Fotos do Usuário 

Caso de Uso  4 

Manter Fotos 

Objetivo 

Permitir que seja apagada a foto e editado o texto 

Ator 

Usuário/Administrador 

Pré-condições 

Conta cadastrada 

Cenário Principal – Editar Texto 

 

A página exibe as fotos enviadas do usuário. 

O usuário seleciona a foto a editar. 

O usuário clica em “editar descrição”. 

A página realiza o processo. 

O usuário altera o texto descritivo. 

O usuário clica em “confirmar edição”. 

A página realiza o processo. 

A página retorna para a galeria de fotos do usuário 

Fim do caso de uso 

 

Cenário Alternativo – Excluir Foto 

 

A página exibe as fotos enviadas do usuário. 

O usuário seleciona a foto a excluir. 

A página envia a mensagem “deseja excluir ‘nome_do-arquivo'”? 

O usuário clica em “confirmar”. 

A página realiza o processo. 

A página retorna para a galeria de fotos do usuário 

Fim do caso de uso. 

 

Cenário de Exceção Principal  

 

O usuário coloca dados sensíveis da conta na descrição. 

1.1 A página retorna a mensagem “não envie dados pessoais neste campo.” 

1.2. A página retorna para o passo 1. 

        2.     O usuário fecha o aplicativo. 
                2.1 O arquivo não é alterado 

        3.    Fim do caso de uso. 

         

        

 

 

CSU05 – Manter Fotos de Local 

Caso de Uso  5 

Manter Fotos 

Objetivo 

Permitir que seja apagada a foto e editado o texto 

Ator 

Administrador 

Pré-condições 

Conta cadastrada 

Cenário Principal 

 

1. A página solicita que o usuário carregue uma foto para ser enviada 

2. O usuário clica no botão "Selecionar foto" 

3. O usuário clica em "Enviar foto". 

4. A página realiza o processo. 

5. Fim do caso de uso 

 

Cenário Alternativo 

 

1. A página solicita que o usuário carregue uma foto para ser enviada 

2. O usuário clica no botão "Selecionar foto" 

3. O usuário clica em "Cancelar envio". 

4. A página realiza o processo. 

5. Fim do caso de uso 

 

Cenário de Exceção Principal 

 

1.A foto enviada é irregular 

1.1. A página envia a mensagem "Envie apenas foto de buraco em via pública" 

1.2. Retorna ao passo 1. 

2. Falha ao salvar o arquivo no banco de dados 

2.1.A página envia a mensagem “Falha ao carregar imagem, tente novamente.” 

2.2.A página retorna a etapa 1. 

1.3. Fim do caso de uso 

 

 

 

 

 
