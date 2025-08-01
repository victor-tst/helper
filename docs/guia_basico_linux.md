-----

# Guia de Comandos Básicos do Linux

Este guia fornecerá uma visão geral dos comandos Linux essenciais para gerenciar diretórios, arquivos, espaço em disco e consumo de memória.

-----

## Navegação e Gerenciamento de Diretórios

Dominar estes comandos é fundamental para se movimentar e organizar sua estrutura de arquivos no Linux.

  * **`pwd` (Print Working Directory):** Mostra o caminho completo do diretório atual em que você está.

    ```bash
    pwd
    ```

  * **`ls` (List):** Lista o conteúdo de um diretório.

      * `ls`: Lista arquivos e diretórios no diretório atual.
      * `ls -l`: Fornece uma listagem longa, mostrando permissões, proprietário, tamanho, data de modificação, etc.
      * `ls -a`: Exibe todos os arquivos, incluindo arquivos ocultos (que começam com um ponto).
      * `ls -lh`: Lista em formato longo e mostra tamanhos de arquivo em um formato legível por humanos (ex: 1K, 234M, 2G).

    <!-- end list -->

    ```bash
    ls
    ls -l
    ls -a
    ls -lh
    ```

  * **`cd` (Change Directory):** Muda o diretório de trabalho.

      * `cd [diretorio]`: Navega para o diretório especificado.
      * `cd ..`: Volta um nível no diretório (para o diretório pai).
      * `cd ~`: Volta para o diretório inicial do usuário (home directory).
      * `cd -`: Volta para o diretório anterior.

    <!-- end list -->

    ```bash
    cd /home/usuario/documentos
    cd ..
    cd ~
    cd -
    ```

  * **`mkdir` (Make Directory):** Cria um novo diretório.

    ```bash
    mkdir novo_diretorio
    ```

  * **`rmdir` (Remove Directory):** Remove um diretório vazio.

    ```bash
    rmdir diretorio_vazio
    ```

-----

## Gerenciamento de Arquivos

Estes comandos são essenciais para criar, visualizar, copiar, mover e remover arquivos.

  * **`touch`:** Cria um novo arquivo vazio ou atualiza o carimbo de data/hora de um arquivo existente.

    ```bash
    touch meu_arquivo.txt
    ```

  * **`cp` (Copy):** Copia arquivos ou diretórios.

      * `cp [origem] [destino]`: Copia um arquivo.
      * `cp -r [origem_diretorio] [destino_diretorio]`: Copia um diretório e seu conteúdo recursivamente.

    <!-- end list -->

    ```bash
    cp meu_arquivo.txt /tmp/backup/
    cp -r meu_diretorio /tmp/backup/
    ```

  * **`mv` (Move):** Move ou renomeia arquivos e diretórios.

      * `mv [origem] [destino]`: Move um arquivo.
      * `mv [nome_antigo] [novo_nome]`: Renomeia um arquivo ou diretório.

    <!-- end list -->

    ```bash
    mv documento.txt /home/usuario/arquivados/
    mv meu_arquivo.txt meu_arquivo_renomeado.txt
    ```

  * **`rm` (Remove):** Remove arquivos e diretórios.

      * `rm [arquivo]`: Remove um arquivo.
      * `rm -r [diretorio]`: Remove um diretório e seu conteúdo recursivamente (cuidado com este comando\!).
      * `rm -f [arquivo]`: Força a remoção sem pedir confirmação.
      * `rm -rf [diretorio]`: Remove um diretório e seu conteúdo recursivamente e força a remoção (use com extrema cautela\!).

    <!-- end list -->

    ```bash
    rm arquivo_velho.txt
    rm -r diretorio_antigo/
    ```

  * **`cat` (Concatenate):** Exibe o conteúdo de um arquivo no terminal.

    ```bash
    cat meu_arquivo.txt
    ```

  * **`less`:** Exibe o conteúdo de um arquivo página por página, permitindo rolagem. Pressione `q` para sair.

    ```bash
    less arquivo_grande.log
    ```

  * **`head`:** Exibe as primeiras linhas de um arquivo (por padrão, as 10 primeiras).

      * `head -n [numero] [arquivo]`: Exibe o número especificado de linhas.

    <!-- end list -->

    ```bash
    head -n 5 meu_arquivo.txt
    ```

  * **`tail`:** Exibe as últimas linhas de um arquivo (por padrão, as 10 últimas).

      * `tail -f [arquivo]`: Segue o arquivo, exibindo novas linhas conforme elas são adicionadas (útil para logs). Pressione `Ctrl+C` para sair.

    <!-- end list -->

    ```bash
    tail -n 15 meu_log.log
    tail -f /var/log/syslog
    ```

-----

## Verificação de Espaço em Disco

Estes comandos te ajudarão a entender o uso do disco em seu sistema.

  * **`df` (Disk Free):** Exibe o uso do espaço em disco dos sistemas de arquivos montados.

      * `df -h`: Exibe o uso do disco em um formato legível por humanos.

    <!-- end list -->

    ```bash
    df
    df -h
    ```

  * **`du` (Disk Usage):** Estima o espaço em disco usado por arquivos e diretórios.

      * `du -h`: Exibe o uso do disco em um formato legível por humanos.
      * `du -sh [diretorio]`: Exibe o tamanho total de um diretório específico.

    <!-- end list -->

    ```bash
    du -h /home/usuario/documentos
    du -sh /var/log/
    ```

-----

## Verificação de Consumo de Memória e Processos

Estes comandos são úteis para monitorar a memória e os processos em execução.

  * **`free`:** Exibe a quantidade de memória livre e usada no sistema.

      * `free -h`: Exibe a memória em um formato legível por humanos.

    <!-- end list -->

    ```bash
    free
    free -h
    ```

  * **`top`:** Exibe uma visão dinâmica e em tempo real dos processos em execução no sistema. É uma ferramenta muito poderosa para monitoramento. Pressione `q` para sair.

    ```bash
    top
    ```

  * **`htop`:** Uma alternativa interativa e mais visual ao `top` (pode precisar ser instalada com `sudo apt install htop` ou `sudo yum install htop`).

    ```bash
    htop
    ```

  * **`ps` (Process Status):** Exibe informações sobre os processos em execução.

      * `ps aux`: Mostra todos os processos em execução para todos os usuários com detalhes completos.

    <!-- end list -->

    ```bash
    ps aux
    ```

  * **`kill`:** Envia um sinal para um processo (geralmente para encerrá-lo).

      * `kill [PID]`: Envia o sinal padrão (TERM, encerramento suave) para o processo com o ID (PID) especificado.
      * `kill -9 [PID]`: Envia o sinal de "morte" (KILL, encerramento forçado) para o processo. Use com cautela.

    <!-- end list -->

    ```bash
    kill 12345
    kill -9 54321
    ```

    *Para encontrar o PID de um processo, você pode usar `ps aux | grep [nome_do_processo]`.*

-----

Este guia cobre os comandos mais básicos e úteis para começar no Linux. 