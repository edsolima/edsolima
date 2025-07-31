<div align="center">
  <h1>Olá, eu sou o Ewerton! 👋</h1>
  <h3>Desenvolvedor Backend com foco em Inteligência Artificial</h3>
</div>

<div align="center">
  <a href="https://www.linkedin.com/in/ewerton-oliveira-65aa4a31b/" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:ewerton.silva.o.lima@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
</div>

---

### 🌟 Sobre Mim

Cursando **Análise e Desenvolvimento de Sistemas**, sou um desenvolvedor apaixonado por resolver problemas complexos e construir soluções eficientes. Minha jornada em projetos pessoais e acadêmicos me proporcionou uma base sólida em **desenvolvimento backend**, com um interesse especial em integrar **Inteligência Artificial** para criar aplicações mais inteligentes e inovadoras.

Estou sempre em busca de aprendizado contínuo para me manter atualizado com as tecnologias mais recentes do mercado.

---

### 🛠️ Habilidades Técnicas

Minhas compétences estão organizadas abaixo para que você possa ter uma visão clara do meu stack tecnológico.

| Categoria                | Tecnologias                                                                                                                                                                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Linguagens** | <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"> <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white"> <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white"> <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=microsoft-sql-server&logoColor=white"> <img src="https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white"> |
| **Backend** | <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white"> <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=json-web-tokens&logoColor=white"> <img src="https://img.shields.io/badge/APIs_RESTful-000?style=for-the-badge&logo=databricks&logoColor=white"> |
| **Banco de Dados** | <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"> <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white"> |
| **IA & Análise de Dados** | <img src="https://img.shields.io/badge/Inteligência_Artificial-grey?style=for-the-badge&logo=openai&logoColor=white"> <img src="https://img.shields.io/badge/ETL-blue?style=for-the-badge&logo=apache-airflow&logoColor=white"> <img src="https://img.shields.io/badge/RAG-orange?style=for-the-badge"> <img src="https://img.shields.io/badge/Análise_de_Dados-yellow?style=for-the-badge&logo=google-analytics&logoColor=black"> |
| **Frontend Básico** | <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white"> <img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white"> |
| **Ferramentas & Outros** | <img src="https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white"> <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white"> <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"> <img src="https://img.shields.io/badge/POO-blue?style=for-the-badge"> |

---

### Minhas Estatísticas no GitHub

<div align="center">
  <a href="https://github.com/edsolima">
    <img height="180em" src="https://github-readme-stats.vercel.app/api?username=edsolima&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
    <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=edsolima&layout=compact&langs_count=7&theme=dracula"/>
  </a>
</div>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/edsolima/maurodesouz/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/edsolima/maurodesouz/output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/edsolima/edsolima/output/pacman-contribution-graph.svg">
</picture>

name: Generate pacman animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}


      - name: push pacman-contribution-graph.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

---
