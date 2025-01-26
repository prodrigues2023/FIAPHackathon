# FIAPHackathon
Grupo 46 POS TECH - Hackathon

# Detecção de materiais cortantes    

A FIAP VisionGuard, empresa de monitoramento de câmeras de segurança, está analisando a viabilidade de uma nova funcionalidade para otimizar o seu software.  
O objetivo da empresa é usar de novas tecnologias para identificar situações atípicas e que possam colocar em risco a segurança de  estabelecimentos e comércios que utilizam suas câmeras.  
Um dos principais desafios da empresa é utilizar Inteligência Artificial para identificar objetos cortantes (facas, tesouras e similares) e emitir alertas para a central de segurança.  
A empresa tem o objetivo de validar a viabilidade dessa feature, e para isso, será necessário fazer um MVP para detecção supervisionada desses objetos. 

# Objetivos 
* Construir ou buscar um dataset contendo imagens de facas, tesouras e outros objetos cortantes em diferentes condições de ângulo e iluminação; 
* Anotar o dataset para treinar o modelo supervisionado, incluindo imagens negativas (sem objetos perigosos) para reduzir falsos positivos; 
* Treinar o modelo; 
* Desenvolver um sistema de alertas (pode ser um e-mail). 

# Etapas da solução
## Obtenção do Dataset
Foi utilizado datasets do Roboflow, disponível em: https://universe.roboflow.com/, sendo eles:
* dataset de facas -> https://universe.roboflow.com/br-wjiqt/knife-epqzp-0rybq

* dataset de tesouras -> https://universe.roboflow.com/x-j1nva/b-7elht

* dataset de foice e espada -> https://universe.roboflow.com/data-zygje/sajam

## Normatização dos dados
Para normatilizaçaõ dos dados foi realizado os seguintes processos:

* remoção de imagens que não possuiam label de mapeamento.
* remoção de label de mapeamento que não possuíam imagens.
* padronização dos nomes dos arquivos de imagens e labels sequenciamente.
* alteração dos labels de mapeamento para o formato yolo do dataset foice e espada.

## Treinamento e Teste do modelo
Foi criado o arquivo main.ipynb para realizar o treinamento e teste do modelo.

No próprio notebook tem detalhes de como o treinamento foi realizado.

## Criação do sistema de alertas
Foi criado o arquivo visionguard-mail.ipynb para realizar o envio de alertas por e-mail.


# Instruções para execução do projeto
## Instalação do ambiente
* Descompactar o arquivo zip no diretório do projeto.

## Outras dependências
* Durante a execução do arquivo de treinamento modifique o caminho do dataset caso esteja usando um caminho diferente do atribuido na variável HOME.

* Durante a execução do arquivo de treinamento modifique o parâmetro de device=0 para device='CPU' caso não tenha uma GPU disponível.

* Durante a execução do arquivo de envio de alertas modifique o parâmetro do servidor de e-mail para os dados de acesso do seu email.