# NPM

[NPM](https://www.npmjs.com) (_Node Package Manager_) é o gerenciador de pacotes do _Node_. Com ele, é possível baixar ou publicar pacotes de código.

## Comandos

A interação com o NPM é normalmente feita através de interfaces de linha de comando.

Todos os comandos devem ser precedidos por _npm_.

```
npm [comando]
```

## Comandos



- [Comando _audit_](#comando-audit)
- [Comando _bin_](#comando-bin)
- [Comando _dedupe_](#comando-dedupe)
- [Comando _docs_](#comando-docs)
- [Comando _doctor_](#comando-doctor)
- [Comando _init_](#comando-init)
- [Comando _install_](#comando-install)
- [Comando _ls_](#comando-ls)
- [Comando _root_](#comando-root)
- [Comando _run_](#comando-run)
- [Comando _uninstall_](#comando-uninstall)
- [Comando _update_](#comando-update)
- [Comando _view_](#comando-view)

### Comando _audit_

Comando _audit_ escaneia o projeto procurando por vulnerabilidades.

```
npm audit
npm audit fix
```

### Comando _bin_

Comando _bin_ exibe o local de instalação dos pacotes.

```
npm bin
npm bin -g
```

### Comando _dedupe_

Comando _dedupe_ escaneia os pacotes do projeto e tenta simplificar a estrutura de dependências.

```
npm dedupe
npm ddp
```

### Comando _docs_

Comando _docs_ exibe a documentação de um pacote.

```
npm docs [pacote]
```

### Comando _doctor_

Comando _doctor_ checa a instalação do NPM e ferramentas relacionadas.

```
npm doctor
```

### Comando _init_

Comando _init_ cria um arquivo _package.json_ no diretório.

```
npm init
npm init -y
```

### Comando _install_

Comando _install_ instala os pacotes escritos no arquivo _package.json_, ou apenas um pacote especificado.

```
npm install
npm install [pacote]
npm install [pacote] -g
```

### Comando _ls_

Comando _ls_ exibe uma lista de pacotes instalados.

```
npm ls
npm ls -g
```

### Comando _root_

Comando _root_ exibe o caminho da pasta de pacotes do NPM.

```
npm root
npm root -g
```

### Comando _run_

Comando _run_ executa um _script_ determinado no arquivo _package.json_.

```
npm run [script]
```

### Comando _uninstall_

Comando _uninstall_ desinstala um pacote.

```
npm uninstall [pacote]
npm uninstall [pacote] -g
```

### Comando _update_

Comando _update_ atualiza os pacotes descritos no arquivo _package.json_, ou apenas um pacote especificado.

```
npm update
npm update [pacote]
npm update [pacote] -g
```

### Comando _view_

Comando _view_ exibe informações de um determinado pacote.

```
npm view [pacote]
```
