# 🚀 Zsh + Oh My Zsh + Ghostty + Starship: Master Cheatsheet (Universal: Linux & macOS)

Guia definitivo com **todos** os atalhos de teclado, aliases manuais, comandos de plugins do Oh My Zsh (Arch Linux e macOS/Homebrew), funções de produtividade e guia de provisionamento do seu ambiente.

---

## 📍 1. Localização dos Arquivos de Configuração

| Componente | Caminho no Linux | Caminho no macOS | Descrição |
| :--- | :--- | :--- | :--- |
| **Zsh Config Principal** | [`~/.zshrc`](file:///home/fabricio-silva/.zshrc) | `~/.zshrc` | Aliases, funções (`f`, `rgf`, etc.), integrações e plugins |
| **Oh My Zsh Core** | [`~/.oh-my-zsh/`](file:///home/fabricio-silva/.oh-my-zsh) | `~/.oh-my-zsh/` | Pasta base do framework Oh My Zsh |
| **Oh My Zsh Plugins** | [`~/.oh-my-zsh/custom/plugins/`](file:///home/fabricio-silva/.oh-my-zsh/custom/plugins) | `~/.oh-my-zsh/custom/plugins/` | Plugins adicionais (`autosuggestions`, `syntax-highlighting`, etc.) |
| **Ghostty Terminal** | [`~/.config/ghostty/config`](file:///home/fabricio-silva/.config/ghostty/config) | `~/.config/ghostty/config` | Tema Catppuccin, fontes, atalhos de split e janela |
| **Starship Prompt** | [`~/.config/starship.toml`](file:///home/fabricio-silva/.config/starship.toml) | `~/.config/starship.toml` | Tema do prompt, ícones de linguagens, git e hora à direita |
| **Mise (Node/Ruby)** | [`~/.config/mise/config.toml`](file:///home/fabricio-silva/.config/mise/config.toml) | `~/.config/mise/config.toml` | Ferramentas globais gerenciadas pelo Mise |
| **Ambiente Zsh (Arch)**| [`~/.zshenv`](file:///home/fabricio-silva/.zshenv) | *(não necessário no Mac)* | Define `ZDOTDIR="$HOME"` para compatibilidade com Arch Linux |

---

## ⚡ 2. Atalhos de Teclado no Terminal (Keybindings)

| Atalho | Plugin / Recurso | Ação |
| :--- | :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>S</kbd> *(ou <kbd>Alt</kbd>+<kbd>s</kbd>)* | **`sudo`** | Insere `sudo ` na linha vazia, ou alterna `sudo` no comando digitado |
| <kbd>Ctrl</kbd> + <kbd>F</kbd> | **FZF Custom** | Abre o FZF e insere o caminho do arquivo selecionado na linha de comando |
| <kbd>Ctrl</kbd> + <kbd>R</kbd> | **FZF** | Busca interativa no histórico de comandos com preview |
| <kbd>Ctrl</kbd> + <kbd>T</kbd> | **FZF** | Localiza qualquer arquivo recursivamente e cola na posição do cursor |
| <kbd>Alt</kbd> + <kbd>C</kbd> | **FZF** | Busca pastas interativamente e faz `cd` direto para ela |
| `**` + <kbd>Tab</kbd> | **FZF Fuzzy Completion** | Ativa busca fuzzy em comandos (`cd **<Tab>`, `nvim **<Tab>`, `kill -9 **<Tab>`) |
| <kbd>↑</kbd> / <kbd>↓</kbd> | **`substring-search`** | Digite parte de um comando e use as setas para filtrar o histórico |
| <kbd>→</kbd> *(ou <kbd>Tab</kbd>)* | **`autosuggestions`** | Aceita a sugestão de autocompletar em cinza claro |
| <kbd>Alt</kbd> + <kbd>a</kbd> *(ou <kbd>Alt</kbd>+<kbd>A</kbd>)* | **`autosuggestions`** | Liga / desliga as sugestões automáticas (`autosuggest-toggle`) |
| <kbd>Ctrl</kbd> + <kbd>←</kbd> / <kbd>→</kbd> | **Zsh Core** | Pula uma palavra para trás / para frente |
| <kbd>Tab</kbd> *(2x)* | **`menu select`** | Abre o menu interativo de autocompletar navegável pelas setas |

---

## 🔍 3. Super Funções de Busca & Navegação Interativa (FZF + Neovim + Bat)

| Comando | Descrição |
| :--- | :--- |
| `f` | Navega interativamente pelos arquivos com **preview do código** em tempo real |
| `fv` | Busca arquivos no FZF e **abre direto no Neovim** (`nvim`) |
| `fo` | Busca arquivos no FZF e **abre no app padrão** (`xdg-open` no Linux / `open` no macOS) |
| `fcat` | Busca arquivos no FZF e imprime o conteúdo formatado com `bat` |
| `rgf "termo"` | Busca texto dentro dos arquivos com `ripgrep` e abre o arquivo no Neovim |
| `rgfa "termo"` | Busca texto em **todos** os arquivos (inclusive ignorados no `.gitignore`) |
| `zd` | Busca diretórios frequentes (`zoxide`) e abre a pasta no Neovim |
| `lf` | Gerenciador de arquivos terminal; ao sair, muda o terminal para o diretório navegado |

---

## 📂 4. Navegação em Diretórios & Histórico de Pastas

| Alias / Atalho | Comando Real | Descrição |
| :--- | :--- | :--- |
| `z <pasta>` | `zoxide` | Salto inteligente para pastas frequentes ou recentes |
| `zz` | `zi` | Seleção interativa de pastas recentes com FZF |
| `-` | `cd -` | Retorna imediatamente ao diretório anterior |
| `..` | `cd ..` | Sobe 1 nível de pasta |
| `...` | `cd ../..` | Sobe 2 níveis de pasta |
| `....` | `cd ../../..` | Sobe 3 níveis de pasta |
| `.....` | `cd ../../../..` | Sobe 4 níveis de pasta |
| `1` até `9` | `cd -1` até `cd -9` | Pula para o 1º até o 9º diretório do histórico de navegação |
| `d` | `dirs -v` | Exibe a pilha com os últimos diretórios visitados numerados |

---

## 🛠️ 5. Utilitários Modernos de Linha de Comando (Aliases Manuais)

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `ls` | `eza --icons` | Listagem moderna de arquivos com ícones |
| `ll` | `eza -lh --icons --git` | Listagem detalhada com permissões, tamanho e status do Git |
| `la` | `eza -lah --icons --git` | Listagem completa incluindo todos os arquivos ocultos |
| `tree` | `eza --tree --icons` | Exibição em árvore de diretórios com ícones |
| `cat` | `bat --style=auto --paging=never` | Cat com syntax highlighting e cores automáticas |
| `cata` | `bat --style=auto --paging=always`| Cat com paginação automática estilo `less` |
| `catl` | `bat --style=plain` | Cat simples sem bordas ou números de linha |
| `catn` | `bat --style=numbers` | Cat exibindo apenas a numeração de linhas |
| `grep` | `rg --color=auto` | Busca de texto ultra-rápida com `ripgrep` |
| `find` | `fd --hidden --exclude .git` | Busca rápida de arquivos no disco com `fd` |
| `df` | `df -h` | Exibe uso de espaço em disco em formato legível (GB/MB) |
| `diff` | `diff --color=auto` | Comparador de diferenças colorido |
| `v` / `vi` / `vim` | `nvim` | Abre o Neovim |
| `cs` / `cu` / `code` | `cursor` | Abre o editor de código Cursor |
| `lg` / `lzg` | `lazygit` | Abre a interface de terminal TUI do Lazygit |
| `o <arquivo>` | `xdg-open` *(Linux)* / `open` *(macOS)* | Abre o arquivo no programa padrão do sistema operacional |

---

## 📋 6. Utilitários de Produtividade do Oh My Zsh

| Comando | Plugin | Descrição |
| :--- | :--- | :--- |
| `extract <arquivo>` *(ou `x`)* | **`extract`** | Descompacta qualquer formato (`.tar.gz`, `.zip`, `.tar.xz`, `.7z`, `.rar`, `.tar.zst`, etc.) |
| `copypath` | **`copypath`** | Copia o caminho absoluto do diretório atual para a área de transferência |
| `copypath <arquivo>` | **`copypath`** | Copia o caminho absoluto de um arquivo específico para a área de transferência |
| `copyfile <arquivo>` | **`copyfile`** | Copia todo o conteúdo de um arquivo de texto para a área de transferência |
| *(automático)* | **`you-should-use`** | Exibe lembretes úteis quando você digita um comando longo que possui alias |

---

## 🐧 7. Plugin Arch Linux: Pacman & Yay *(Ativo no Linux)*

### 📦 Pacman (Repositórios Oficiais)

| Alias / Função | Comando Real | Descrição |
| :--- | :--- | :--- |
| `pacupg` | `sudo pacman -Syu` | Atualiza todos os pacotes oficiais do sistema |
| `pacin <pkg>` | `sudo pacman -S <pkg>` | Instala um ou mais pacotes |
| `pacrem <pkg>` | `sudo pacman -Rns <pkg>` | Remove o pacote e todas as dependências que ficaram órfãs |
| `pacre <pkg>` | `sudo pacman -R <pkg>` | Remove apenas o pacote especificado |
| `pacreps <termo>` | `pacman -Ss <termo>` | Busca pacotes nos repositórios oficiais |
| `pacrep <pkg>` | `pacman -Si <pkg>` | Exibe informações detalhadas de um pacote remoto |
| `pacloc <pkg>` | `pacman -Qi <pkg>` | Exibe informações detalhadas de um pacote instalado localmente |
| `paclocs <termo>` | `pacman -Qs <termo>` | Busca termos entre os pacotes instalados localmente |
| `pacins <arquivo>` | `sudo pacman -U <pkg.tar.zst>` | Instala pacote a partir de arquivo compilado local |
| `paclean` | `sudo pacman -Sc` | Limpa o cache de pacotes antigos/não instalados |
| `paclr` | `sudo pacman -Scc` | Limpa completamente todo o cache de pacotes do pacman |
| `pacupd` | `sudo pacman -Sy` | Sincroniza o banco de dados dos repositórios |
| `pacmir` | `sudo pacman -Syy` | Força a atualização completa da lista de mirrors |
| `pacls <pkg>` | `pacman -Ql <pkg>` | Lista todos os arquivos instalados por determinado pacote |
| `pacown <arquivo>` | `pacman -Qo <arquivo>` | Descobre a qual pacote pertence determinado arquivo no sistema |
| `paclsorphans` | `pacman -Qdt` | Lista todos os pacotes órfãos do sistema |
| `pacrmorphans` | `sudo pacman -Rs $(pacman -Qtdq)` | Remove automaticamente todos os pacotes órfãos |
| `pacweb <pkg>` | *(função)* | Abre a página oficial do pacote no archlinux.org no navegador |

### 🚀 Yay (Gerenciamento do AUR)

| Alias / Função | Comando Real | Descrição |
| :--- | :--- | :--- |
| `yaupg` | `yay -Syu` | Atualiza todos os pacotes do sistema (oficiais + AUR) |
| `yasu` | `yay -Syu --noconfirm` | Atualiza o sistema completo sem pedir confirmações |
| `yain <pkg>` | `yay -S <pkg>` | Instala pacote oficial ou do AUR via Yay |
| `yains <arquivo>` | `yay -U <arquivo>` | Instala pacote a partir de arquivo local compilado via Yay |
| `yarem <pkg>` | `yay -Rns <pkg>` | Remove pacote e dependências órfãs via Yay |
| `yare <pkg>` | `yay -R <pkg>` | Remove apenas o pacote via Yay |
| `yareps <termo>` | `yay -Ss <termo>` | Busca termos nos repositórios oficiais e no AUR |
| `yarep <pkg>` | `yay -Si <pkg>` | Exibe informações detalhadas de pacote remoto via Yay |
| `yaloc <pkg>` | `yay -Qi <pkg>` | Exibe informações detalhadas de pacote instalado via Yay |
| `yaorph` | `yay -Qtd` | Lista pacotes órfãos via Yay |
| `yaclean` | `yay -Sc` | Limpa cache de compilação e pacotes antigos do Yay |
| `yaclr` | `yay -Scc` | Limpa completamente todo o cache do Yay |
| `upgrade` | *(função inteligente)* | Valida o chaveiro PGP (`archlinux-keyring`) e faz o upgrade completo |

---

## 🍏 8. Plugins macOS & Homebrew *(Ativos automaticamente no Mac)*

### 🍺 Homebrew (Plugin `brew`)

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `bin <pkg>` | `brew install <pkg>` | Instala uma fórmula ou CLI via Homebrew |
| `bcas <app>` | `brew install --cask <app>` | Instala aplicativo gráfico no macOS (Ghostty, Cursor, etc.) |
| `bug` | `brew upgrade` | Atualiza todos os pacotes e casks instalados |
| `bup` | `brew update` | Atualiza a lista de fórmulas do Homebrew |
| `bout` | `brew outdated` | Lista pacotes que possuem atualizações disponíveis |
| `brm <pkg>` | `brew uninstall <pkg>` | Remove um pacote ou aplicativo |
| `bcl` | `brew cleanup` | Limpa caches e downloads antigos do Homebrew |
| `bsr <termo>` | `brew search <termo>` | Busca pacotes e casks no repositório |
| `binf <pkg>` | `brew info <pkg>` | Exibe detalhes, dependências e status do pacote |
| `bls` | `brew list` | Lista todos os pacotes e casks instalados |
| `bdoc` | `brew doctor` | Diagnóstica e verifica a saúde da instalação do Homebrew |
| `bsvc` | `brew services` | Gerencia daemons/serviços em segundo plano |
| `bsvcl` | `brew services list` | Lista status de todos os serviços (Postgres, Redis, etc.) |
| `bsvcst <svc>` | `brew services start <svc>` | Inicia um serviço em segundo plano |
| `bsvcsp <svc>` | `brew services stop <svc>` | Para um serviço em segundo plano |
| `bsvcr <svc>` | `brew services restart <svc>` | Reinicia um serviço em segundo plano |

### 🍏 Integrações Nativas macOS (Plugin `macos`)

| Comando / Função | Descrição |
| :--- | :--- |
| `cdf` | Faz `cd` imediato para a **pasta que estiver atualmente aberta no Finder** |
| `quick-look <arq>` *(ou `ql`)* | Abre o visualizador **Quick Look** nativo do macOS para qualquer arquivo |
| `pfd` | Imprime o caminho absoluto da pasta atualmente aberta no Finder |
| `pfs` | Imprime a lista de arquivos atualmente selecionados no Finder |
| `pushdf` | Adiciona o diretório ativo do Finder na pilha de navegação |
| `trash <arq/pasta>` | Move arquivos/pastas com segurança para a **Lixeira do macOS** |
| `showfiles` / `hidefiles` | Mostra ou oculta arquivos invisíveis no Finder |
| `music` *(ou `itunes`)* | Controla o Apple Music/Spotify pelo terminal (`music play`, `pause`, `next`, `prev`) |
| `bspd` / `bspc` | Exibe ou altera o volume do som do Mac pelo terminal |

---

## 🌿 9. Atalhos de Git (Plugin `git` + Extras Manuais)

### 📌 Status, Add & Commit

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `gst` | `git status` | Exibe o status do repositório |
| `gss` | `git status -s` | Exibe o status resumido em formato curto |
| `ga <arq>` | `git add <arq>` | Adiciona arquivo para a área de stage |
| `ga .` / `gaa` | `git add .` / `git add --all` | Adiciona todas as alterações para stage |
| `gapa` | `git add --patch` | Adiciona partes/hunks de arquivos interativamente |
| `gcmsg "msg"` | `git commit -m "msg"` | Cria commit com mensagem |
| `gcam "msg"` | `git commit -a -m "msg"` | Adiciona rastreados e cria commit |
| `gcoma` | `git commit --amend` | Edita o último commit |
| `gcomane` | `git commit --amend --no-edit` | Inclui mudanças no último commit mantendo a mensagem |
| `gundo` | `git reset --soft HEAD~1` | Desfaz o último commit mantendo alterações no stage |
| `gundosoft` | `git reset HEAD~1` | Desfaz o último commit mantendo alterações desmarcadas |

### 🌿 Branches, Checkout & Switch

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `gb` | `git branch` | Lista branches locais |
| `gba` | `git branch -a` | Lista todas as branches (locais e remotas) |
| `gbd <branch>` | `git branch -d <branch>` | Remove branch com segurança (se já mesclada) |
| `gbD <branch>` | `git branch -D <branch>` | Força a remoção de branch |
| `gsw <branch>` | `git switch <branch>` | Troca para outra branch |
| `gswc <branch>` | `git switch -c <branch>` | Cria e muda imediatamente para a nova branch |
| `gswp` | `git switch -` | Retorna à branch anterior |
| `gco <branch>` | `git checkout <branch>` | Faz checkout de branch ou arquivo |
| `gcb <branch>` | `git checkout -b <branch>` | Cria e troca para nova branch (checkout) |
| `gprune` | *(script de limpeza)* | Deleta branches locais cujas remotas já foram apagadas |

### 🔄 Pull, Push & Remotes

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `gp` / `gps` | `git push` | Envia commits locais para o repositório remoto |
| `gpsup` | `git push --set-upstream origin ...` | Envia e vincula a branch atual com a remota |
| `gpf!` | `git push --force` | Força envio de commits para a remota |
| `gl` / `gpl` | `git pull` | Puxa alterações do repositório remoto |
| `gpr` | `git pull --rebase` | Puxa alterações aplicando rebase |
| `gf` / `gfa` | `git fetch` / `git fetch --all --prune` | Busca atualizações remotas e limpa referências |
| `grv` | `git remote -v` | Lista repositórios remotos configurados |
| `grao <url>` | `git remote add origin <url>` | Vincula remote origin |
| `gin` | `git init` | Inicializa novo repositório Git |

### 📜 Diff, Logs & Visualização

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `gd` | `git diff` | Exibe alterações não adicionadas ao stage |
| `gds` / `gdca` | `git diff --staged` / `--cached` | Exibe alterações prontas para commit (staged) |
| `glg` | `git log --stat` | Exibe histórico detalhado com lista de arquivos alterados |
| `glo` | `git log --oneline --decorate` | Exibe histórico em linhas resumidas |
| `glog` | `PAGER="less -F -X" git log` | Log formatado paginado |
| `gadog` | `git log --all --decorate --oneline --graph` | Grafo visual completo de todas as branches |
| `dotfiles` | `git --git-dir=...` | Gerenciador de dotfiles via repositório bare |

### 📦 Stash & Merge

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `gst` / `gsta` | `git stash` / `git stash apply` | Guarda alterações no stash / restaura |
| `gstp` | `git stash pop` | Restaura e remove o item do stash |
| `gstl` | `git stash list` | Lista todos os stashes salvos |
| `gstd` | `git stash drop` | Descarta um stash |
| `gm <branch>` | `git merge <branch>` | Mescla uma branch na atual |
| `gma` | `git merge --abort` | Aborta um merge em andamento com conflitos |
| `grb <branch>` | `git rebase <branch>` | Aplica rebase sobre outra branch |
| `grba` / `grbc` | `git rebase --abort` / `--continue` | Aborta ou continua um rebase com conflitos |

---

## 🐳 10. Docker & Docker Compose (Plugins Oficiais do Oh My Zsh)

### 📦 Docker Containers

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `dps` | `docker ps` | Lista contêineres em execução |
| `dpsa` / `dclsa` | `docker ps -a` | Lista todos os contêineres (ativos e parados) |
| `dst <id>` | `docker container start` | Inicia um ou mais contêineres parados |
| `dstp <id>` | `docker container stop` | Para um ou mais contêineres em execução |
| `drs <id>` | `docker container restart` | Reinicia um contêiner |
| `drm <id>` | `docker container rm` | Remove um contêiner |
| `drm! <id>` | `docker container rm -f` | Força a remoção imediata de um contêiner |
| `dxcit <id> sh` | `docker container exec -it <id> sh` | Abre shell interativo dentro do contêiner |
| `dlo <id>` / `dclf` | `docker container logs` | Exibe logs do contêiner |
| `dpo <id>` | `docker container port` | Exibe portas mapeadas do contêiner |
| `dtop <id>` | `docker top` | Exibe processos em execução dentro do contêiner |
| `dsts` | `docker stats` | Monitor de uso de CPU, Memória e Rede em tempo real |
| `dcin <id>` | `docker container inspect` | Exibe JSON detalhado de configuração do contêiner |
| `dcprune` | `docker container prune` | Remove todos os contêineres que estão parados |
| `dsta` | `docker stop $(docker ps -q)` | Para todos os contêineres em execução de uma só vez |

### 🖼️ Docker Imagens, Volumes, Redes & Sistema

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `dils` | `docker image ls` | Lista imagens Docker locais |
| `dii <img>` | `docker image inspect` | Inspeciona detalhes de uma imagem |
| `dirm <img>` | `docker image rm` | Remove uma imagem |
| `dbl` | `docker build` | Constrói uma imagem Docker a partir do Dockerfile |
| `dpu` | `docker pull` | Baixa uma imagem do Docker Hub ou Registro |
| `dipu` | `docker image push` | Envia imagem para o registro remoto |
| `dipru` | `docker image prune -a` | Remove todas as imagens não utilizadas |
| `dsprune` | `docker system prune` | Limpeza profunda de containers, imagens e redes órfãs |
| `dvls` | `docker volume ls` | Lista todos os volumes criados |
| `dvi <vol>` | `docker volume inspect` | Inspeciona detalhes de um volume |
| `dvprune` | `docker volume prune` | Remove volumes que não estão vinculados a contêineres |
| `dnls` | `docker network ls` | Lista redes virtuais do Docker |
| `dni <rede>` | `docker network inspect` | Inspeciona configurações de uma rede |
| `dnprune` | `docker network prune` | Remove redes virtuais não utilizadas |

### 🐙 Docker Compose

| Alias | Comando Real | Descrição |
| :--- | :--- | :--- |
| `dcup` | `docker compose up` | Inicia os serviços definidos no `docker-compose.yml` |
| `dcupd` | `docker compose up -d` | Inicia serviços em segundo plano (detached mode) |
| `dcdn` | `docker compose down` | Para e remove contêineres, redes e volumes criados pelo Compose |
| `dcl` / `dclf` | `docker compose logs -f` | Acompanha logs de todos os serviços em tempo real |
| `dcb` | `docker compose build` | Constrói ou reconstrói as imagens dos serviços |
| `dcps` | `docker compose ps` | Lista status de todos os serviços do Compose |
| `dcrestart` | `docker compose restart` | Reinicia todos os serviços do Compose |
| `dcstop` | `docker compose stop` | Para os serviços do Compose |
| `dcstart` | `docker compose start` | Inicia os serviços parados do Compose |
| `dce <serviço> sh` | `docker compose exec <serviço> sh` | Abre terminal interativo no serviço do Compose |
| `dcr <serviço> <cmd>`| `docker compose run <serviço> <cmd>` | Executa comando avulso em um serviço |
| `dck` | `docker compose kill` | Força a parada imediata dos serviços |
| `dcrm` | `docker compose rm` | Remove contêineres parados do Compose |

---

## 🪟 11. Atalhos do Terminal Ghostty

| Atalho | Ação no Ghostty |
| :--- | :--- |
| <kbd>Ctrl</kbd> + <kbd>\\</kbd> | Cria um novo split de terminal automaticamente |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>H</kbd> | Focar no split da **esquerda** |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>L</kbd> | Focar no split da **direita** |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>K</kbd> | Focar no split de **cima** |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>J</kbd> | Focar no split de **baixo** |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>Setas</kbd> | Redimensiona a área do split ativo em 10px |
| <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>W</kbd> | Fecha a janela / split atual |

---

## 🍏 12. Gestão com Chezmoi & Provisionamento no macOS

Os seus dotfiles estão versionados no repositório: **[`faahiero/dotfiles`](https://github.com/faahiero/dotfiles)**.

### 🚀 Provisionamento no Mac Novo (Passo a Passo)

#### Passo 1: Instalar Homebrew, CLIs e Chezmoi
Abra o Terminal padrão do Mac e execute:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
eval "$(/opt/homebrew/bin/brew shellenv)"
brew install eza bat ripgrep fd fzf zoxide mise starship neovim lazygit ghostty chezmoi
```

#### Passo 2: Instalar Oh My Zsh e Plugins Customizados
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
git clone https://github.com/MichaelAquilina/zsh-you-should-use.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/you-should-use
```

#### Passo 3: Aplicar as Configurações via Chezmoi (Automático)
```bash
chezmoi init --apply faahiero
```
*(O Chezmoi clona automaticamente o seu repositório `faahiero/dotfiles` e aplica `.zshrc`, `ghostty`, `starship`, `mise` e `CHEATSHEET_ZSH.md` no lugar certo).*

#### Passo 4: Instalar ferramentas do Mise no Mac
```bash
mise install
```

---

### 🔄 Comandos Chezmoi para o Dia a Dia (Sincronização)

| Comando | O que faz |
| :--- | :--- |
| `chezmoi status` | Mostra se há diferenças entre seus arquivos no `$HOME` e o repositório |
| `chezmoi diff` | Exibe o `diff` exato das alterações pendentes |
| `chezmoi re-add` | Atualiza o repositório com as modificações que você fez nos arquivos locais |
| `chezmoi add <arquivo>` | Adiciona um novo arquivo de configuração ao monitoramento do Chezmoi |
| `chezmoi git commit -m "msg"` | Cria um commit no repositório de dotfiles |
| `chezmoi git push` | Envia as alterações para o GitHub (`faahiero/dotfiles`) |
| `chezmoi update` | Puxa as novidades do GitHub e aplica imediatamente no sistema |
