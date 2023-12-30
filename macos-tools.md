<!--- #macos-tools --->
# Tooling

## Pre-requisite
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

## General (System)

```
brew install --cask \
  iterm2 \
  alfred \
  kap \
  vlc \
  alt-tab \
  raycast \
  the-unarchiver \
  karabiner-elements \
  rectangle \
  eqmac \
  arc \
  betterdisplay \
  MonitorControl
  <!-- slack \ -->
  <!-- visual-studio-code \ -->
  <!-- zoom -->

brew tap localsend/localsend
brew install localsend
```
### Take care
```
brew install --no-quarantine stretchly 
brew install --cask obsidian logseq
```
### Menu bar/Utility
```
brew install stats \
  itsycal \
  ffmpeg \ 
  maccy \
  <!-- imagemagick \ -->
```
#### Configuration

```
git config --global user.name Jun Kin

git config --global user.email chaijunkin@gmail.com

git config --global core.editor nano
```
## Recommended

```
brew install \
  node \
  yarn \
  tfenv \
  tgenv \
  ansible \
  awscli \
  aws-shell \
  git \
  jq \
  nvm
```

You should create NVM's working directory if it doesn't exist:
mkdir ~/.nvm

Add the following to your shell profile e.g. ~/.profile or ~/.zshrc:
export NVM_DIR="$HOME/.nvm"
[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
[ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"  # This loads nvm bash_completion


TESTING
```
aws s3 ls --profile individual-jkchai

aws-vault login individual-jkchai
aws-vault exec individual-jkchai -- aws s3 ls
aws-vault exec individual-jkchai -- fish
```

```
[profile localstack]
region=us-east-1
output=json
endpoint_url = http://localhost:4566
```

```
brew install --cask 1password \
  aws-vault \
  jetbrains-toolbox \
```
## Shell customization


[Modern Unix](https://github.com/ibraheemdev/modern-unix)


| Classic Utilities | Modern Counterparts |
| --- | --- |
| `find` | `fd` |
| `cat` | `bat` |
| `ls` (first) | `exa` |
| `ls` (second) | `lsd` |
| `git diff` | `git-delta` |
| `du` | `dust` |
| `df` | `duf` |
| `tree` | `broot` |
| `grep` | `ripgrep` |
| `ack` | `ag` |
| `man` | `tldr` |
| `htop` | `glances` |

```
brew install fd bat exa lsd git-delta dust duf broot ripgrep ag tldr glances fzf
```
### Install fish and starship

```
curl -sS https://starship.rs/install.sh | sh

brew install fish atuin
fish
fish_add_path /opt/homebrew/bin
echo "/opt/homebrew/bin/fish" | sudo tee -a /etc/shells
chsh -s /opt/homebrew/bin/fish

echo "starship init fish | source" | sudo tee -a ~/.config/fish/config.fish
echo "test -f ~/.kubectl_aliases.fish && source ~/.kubectl_aliases.fish" | sudo tee -a ~/.config/fish/config.fish
echo "atuin init fish | source" | sudo tee -a ~/.config/fish/config.fish
```

Go to Vscode --> Settings --> Settings --> Search for "terminal profile" --> Look for Osx profile

{
"editor.linkedEditing": true,
"editor.snippetSuggestions": "top",
}


VSCODE EXTENSION
Terraform
![](../images/fish-vscode-extension.png)
### Install attuin

```
atuin register -u jkchai -e chaijunkin@gmail.com
atuin import fish
atuin sync
```
## Kubernetes related stuff
### CLI System

```
brew install \
  kubectl \
  helm \
  minikube \
  stern \
  kubectx \
  k9s \
  skaffold \
  kind \
  vcluster \
  kustomize \
  vlt \
```
    buildah \
        colima \
            docker \
### GUI System

```
brew install --cask openlens headlamp
```
#### Reference 

[Running docker on MacOS (ARM)](https://dev.to/elliotalexander/how-to-use-docker-without-docker-desktop-on-macos-217m)
## DevSecOps tools
### GitOps/Pipeline/IaC

```
brew tap hashicorp/tap

brew install hashicorp/tap/terraform terraform-docs tflint terragrunt terratest 

brew install pre-commit aquasecurity/trivy/trivy checkov gitleaks kube-score/tap/kube-score glab sops age yq jq
```
#### Githooks
### Localstack Experiment

localstack start -d

[localstack desktop install](https://github.com/localstack/localstack-desktop/releases/download/1.0.1/LocalStack-Desktop-community-1.0.1.AppImage)
## Others

brew install eksctl amazon-ecs-cli rancher-cli adr-tools go localstack/tap/localstack-cli terraform-local
go install github.com/onsi/ginkgo/ginkgo@latest
<!-- go get github.com/smartystreets/goconvey  -->

<!--- #macos-tools --->