<h1 align="center">Configuración inicial de entorno de desarrollo</h1>

## Configuración de la terminal

<details>
  <summary>MacOs</summary>

Descargar [Hyper](https://hyper.is/)

Instalar el manejador de paquetes **Homebrew**

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Usando Homebrew instalar **zsh**

```shell
brew install zsh
```

</details>

<details>
  <summary>Linux</summary>

Instalar **zsh**

```shell
sudo apt install zsh
```

</details>

---

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

```
plugins(git zsh-autosuggestions)
```
