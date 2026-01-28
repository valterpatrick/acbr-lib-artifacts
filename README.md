# ACBr Libs - CI/CD Pipeline & DevOps Automation (Unofficial)

![Build Status](https://github.com/drungrin/acbr-lib-artifacts/actions/workflows/sync-and-build.yml/badge.svg)
![License](https://img.shields.io/badge/license-LGPL-blue.svg)

> ⚠️ **AVISO:** A distribuição pública dos binários compilados (.dll/.so) foi descontinuada neste repositório em apoio ao modelo de sustentabilidade do Projeto ACBr oficial. Este repositório permanece ativo como uma **demonstração técnica de DevOps**, focada na automação de builds Lazarus em ambientes Docker.

---

## 🚀 Sobre o Projeto

Este repositório contém uma implementação de **Integração Contínua (CI)** para o código fonte do componente ACBr, utilizando GitHub Actions.

O objetivo principal é demonstrar como automatizar o ciclo de vida de desenvolvimento em projetos **Lazarus/Pascal**, resolvendo desafios como:
* Configuração de ambiente de compilação em container (Docker).
* Gerenciamento de dependências nativas Linux/Windows.
* Automação de builds cross-platform.

### Como funciona a Automação?

1.  **Sincronização:** Diariamente, um script verifica novos commits no [repositório oficial do ACBr](https://github.com/ProjetoACBr/ACBr).
2.  **Ambiente:** Um container Docker (`drungrin/lazarus-builder`) é provisionado com o ambiente Lazarus pré-configurado.
3.  **Compilação:** O pipeline executa a compilação das bibliotecas nativas para **Linux (x64)** e **Windows (x64)**, garantindo a integridade do código.
4.  **Verificação:** O processo valida se o código atual do *upstream* é compilável em um ambiente limpo, servindo como um "Health Check" do projeto.

---

## 📥 Onde Baixar os Binários?

Para obter as bibliotecas compiladas, assinadas digitalmente e com suporte oficial, utilize os canais do mantenedor do projeto:

* **Site Oficial:** [Projeto ACBr](https://www.projetoacbr.com.br/)
* **Fórum:** [Fórum ACBr](https://www.projetoacbr.com.br/forum/)

---

## 🛠️ Detalhes Técnicos (DevOps)

A infraestrutura como código (IaC) deste repositório utiliza a seguinte stack:

* **CI/CD:** GitHub Actions.
* **Ambiente de Build:** Docker.
* **Imagem Base:** `drungrin/lazarus-builder:1.0.0` (Imagem customizada mantida por mim para build de Lazarus).
* **Script de Build:** Shell scripts otimizados para detecção de mudanças e compilação condicional.

### Estrutura do Workflow

* O sistema mantém o fork sincronizado via `git merge upstream/master`.
* A compilação é feita em ambiente efêmero (limpo) a cada execução.
* Estratégias de cache são utilizadas para otimizar o tempo de execução do runner.

---

## ⚖️ Licença e Créditos

Todo o código fonte do componente ACBr pertence ao **Projeto ACBr** e seus colaboradores.

* **Código Fonte Original:** [github.com/ProjetoACBr/ACBr](https://github.com/ProjetoACBr/ACBr)
* **Licença:** LGPL (Lesser General Public License).

Este repositório respeita a licença original e o trabalho dos autores. O foco aqui é estritamente nas práticas de Engenharia de Software e Automação.
