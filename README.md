# 🌐 Linux Web Server — Deploy Automático com Apache2

Projeto criado por **[Gusbaido](https://github.com/Gusbaido)** para automatizar a configuração de um **servidor web Apache2** no Linux/WSL e o deploy de uma aplicação web hospedada no GitHub.

---

## 🧩 Descrição do Projeto

Este script automatiza o **provisionamento e deploy** de um site em um servidor **Apache2**, garantindo um ambiente pronto para uso em poucos segundos.

Ele faz:
1. Instalação e configuração do **Apache2**
2. Clonagem da aplicação de exemplo do professor **Denilson Bonatti**  
   → [https://github.com/denilsonbonatti/linux-site-dio](https://github.com/denilsonbonatti/linux-site-dio)
3. Publicação automática em `/var/www/html`
4. Ajuste de permissões e reinício do serviço
5. Verificação HTTP automática (`curl`)

---

## 🔄 Fluxo do Projeto

┌─────────────┐ HTTP Request ┌────────────────────┐
│ Navegador │ ───────────────────────▶ │ Servidor Apache2 │
│ (Cliente) │ │ Linux / WSL │
└─────────────┘ HTTP Response │ Porta 80 (localhost)│
◀─────────────────┤ │
└──────────┬──────────┘
│
▼
/var/www/html (Site Ativo)

yaml
Copiar código

> 💡 O Apache2 recebe as requisições HTTP e entrega os arquivos da aplicação clonado para `/var/www/html`.

---

## 🚀 Como executar

### 1️⃣ Clonar o repositório
```bash
git clone https://github.com/Gusbaido/LinuxWebServer.git
cd LinuxWebServer
2️⃣ Tornar o script executável
bash
Copiar código
chmod +x deploy_site.sh
3️⃣ Executar com privilégios administrativos
bash
Copiar código
sudo ./deploy_site.sh
✅ Testar o resultado
Abra no navegador:

arduino
Copiar código
http://localhost
ou teste pelo terminal:

bash
Copiar código
curl -I http://127.0.0.1
Se o retorno for HTTP/1.1 200 OK, o servidor está funcional ✅

📂 Estrutura do Projeto
/tmp/linux-site-dio/       → repositório clonado temporariamente
/var/www/html/             → diretório principal do Apache
/var/www/html_backup/      → backup da versão anterior (se existir)
deploy_site.sh             → script de automação do deploy

🛠️ Requisitos

Debian/Ubuntu/WSL

sudo

Conexão com a Internet

Pacotes: git, apache2, unzip, curl

🧠 Autor

Desenvolvido por Gusbaido

Curso: Linux Experience - DIO
Projeto: Servidor Web Automatizado (Apache2)

🧾 Licença

MIT © 2025 Gusbaido
