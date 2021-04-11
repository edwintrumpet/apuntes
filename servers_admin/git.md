<h1 align="center">Git y Github</h1>

## Índice

- [Configuraciones](#configuraciones)
- [Conexión de GitHub por medio de SSH](#conexión-de-github-por-medio-de-ssh)
- [Tags](#tags)
- [Alias](#alias)

## Configuraciones

Ver lista de configuraciones aplicadas

```shell
git config --list
```

Configuración de usuario inicial

```shell
git config --global user.name "<nombre de usuario>"
```

```shell
git config --global user.email "<email>"
```

## Conexión de GitHub por medio de SSH

### Crear el par de llaves

```shell
ssh-keygen -t rsa -b 4096 -C "<email>"
```

Se almacena en el directorio y con el nombre que indica por defecto

### Agregar keys al agente de llaves

#### MacOs

Evaluar que el agente de llaves SSH esté corriendo

```shell
eval "$(ssh-agent -s)"
```

Crear el archivo `~/.ssh/config`

```
Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ~/.ssh/id_rsa
```

Agregar llave

```shell
ssh-add -K ~/.ssh/id_rsa
```

#### Windows y Linux

Evaluar que el agente de llaves SSH esté corriendo

```shell
eval $(ssh-agent -s)
```

Agregar llave

```shell
ssh-add ~/.ssh/id_rsa
```

## Tags

Crear tag

```shell
git tag -a <nombre del tag (v0.0.1)> -m "<mensaje del tag>"
```

Subir tags a GitHub

```shell
git push origin --tags
```

Borrar tag en local

```shell
git tag -d <nombre del tag>
```

Borrar tag en GitHub

```shell
git push origin :refs/tags/<nombre del tag>
```

[Volver al índice](../README.md)

## Alias

Ver la lista de alias que he creado

```shell
git config --get-regexp 'alias\.'
```

Crear alias

```shell
git config --global alias.<nombre del alias> "<script>"
```

### Algunos aliases últiles

Listar logs en una sola línea

```shell
git config --global alias.list "log --oneline"
```

Ver logs de todas las ramas

```shell
git config --global alias.map "log --oneline --graph --decorate --all"
```

Borrar el último commit sin perder los cambios

```shell
git config --global alias.rmlast "reset --soft HEAD~1"
```
