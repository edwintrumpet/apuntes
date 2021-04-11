<h1 align="center">Configuración inicial de entorno de desarrollo para MacOs</h1>

## Índice

- [Configuración de la terminal](#configuración-de-la-terminal)
- [Instalar nvm](<#instalar-nvm-(gestor-de-versiones-de-node.js)>)

## Configuración de la terminal

Descargar [Hyper](https://hyper.is/)

Instalar el manejador de paquetes **Homebrew**

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Usando Homebrew nstalar **zsh**

```shell
brew install zsh
```

Instalar [Oh my zsh](https://ohmyz.sh/)

```shell
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Configurar un tema, hay varios temas disponibles en [el repositorio de Oh my zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

Actualmente estoy usando el tema **zhann**

Para configurar un tema solo tenemos que entrar en el archivo `~/.zshrc` y modificar el tema en la línea

```shell
ZSH_THEME=<theme>
```

Instalar el plugin autosuggestions, clonando el [repositorio](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md) en la ruta `~/.oh-my-zsh/custom/plugins` con el comando

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Agregar el plugin a la lista de plugins en el archivo `~/.zshrc` dejando un espacio entre plugin y plugin

```shell
plugins(git zsh-autosuggestions)
```

## Instalar nvm (gestor de versiones de Node.js)

Decargar [nvm](https://github.com/nvm-sh/nvm) con el comando

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

Al final del archivo `~/.zshrc` agregar

```shell
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

Instalamos la versión de Node.js con la que queremos trabajar usando **nvm**

```shell
nvm install v<versión de node>
```

Si por algún motivo Node.js no funciona debemos agregar nvm a la lista de plugins en el archivo `~/.zshrc`

[Volver al índice](../README.md)
