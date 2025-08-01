-----

# Conectando e Configurando sua VM Linux

Este guia mostra como se conectar à sua VM Linux, verificar sua configuração e instalar o Docker.

-----

## Conexão com a VM Linux

Você pode se conectar à sua VM Linux usando o comando `ssh` no terminal.

```bash
ssh [usuario]@[host]
```

**Exemplo:**

```bash
ssh svc_cpe@vm1166
```

-----

## Verificando a Configuração da VM

Para verificar a distribuição e versão do sistema operacional da sua VM, use o comando abaixo no terminal:

```bash
cat /etc/*release
```

Este comando exibirá informações sobre a versão do sistema operacional Linux que está rodando na VM.

-----

## Instalação do Docker

Siga os passos abaixo para instalar o Docker Engine na sua VM Linux.

### 1\. Removendo Instalações Anteriores (se houver)

É uma boa prática remover quaisquer instalações anteriores do Docker antes de prosseguir com uma nova instalação.

```bash
sudo yum remove docker \
              docker-client \
              docker-client-latest \
              docker-common \
              docker-latest \
              docker-latest-logrotate \
              docker-logrotate \
              docker-engine
```

### 2\. Instalando o Docker Engine

Depois de remover quaisquer versões antigas, você pode instalar o Docker Engine.

```bash
sudo yum install -y docker-engine
```

O comando `-y` aprova automaticamente todas as solicitações de instalação.

### 3\. Iniciando e Habilitando o Docker

Após a instalação, você precisará iniciar o serviço Docker e configurá-lo para iniciar automaticamente na inicialização do sistema. Também é recomendável adicionar seu usuário ao grupo `docker` para que você possa executar comandos Docker sem `sudo`.

```bash
sudo systemctl start docker           # Inicia o serviço Docker
sudo systemctl enable docker          # Habilita o Docker para iniciar na inicialização

sudo usermod -aG docker svc_cpe       # Adiciona o usuário 'svc_cpe' ao grupo 'docker'
```

**Importante:** Após adicionar o usuário ao grupo `docker`, você pode precisar **sair da sessão SSH e se reconectar** para que as alterações de grupo entrem em vigor.

-----
