# **Guia de instalação Docker**
## **O que é o docker ?**

Em breves palavras, Docker é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração.
#
> Dica: Use no **linux**, pelo bem da sua saúde mental.

> A instalação segue a documentação oficial do Docker. 
#
## Passo a passo para a instalação:

### Realize uma limpeza

```console
rm -r $HOME/.docker/desktop
sudo rm /usr/local/bin/com.docker.cli
sudo apt purge docker-desktop
```
### Prepare o repositório:

```console
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
### Adicione a chave GPG oficial
```console
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
### 
```console
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```console
sudo apt-get update
```
```console
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
### Baixe o `.deb` mais recente do docker e instale
```console
sudo apt-get update
sudo apt-get install ./docker-desktop-<version>-<arch>.deb
```


