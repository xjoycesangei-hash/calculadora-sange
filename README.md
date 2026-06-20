# Calculadora de Precificação — Sange do Brasil

Calculadora interativa de precificação para Atacado e Tampografia, com cálculo de margem em tempo real.

## 🔒 Acesso

O site é protegido por senha. Acesse `index.html` e digite a senha para entrar.

> **Nota de segurança:** esta é uma proteção simples no navegador (client-side), suficiente para evitar acesso casual ao link. Não use para dados sigilosos ou financeiros críticos — qualquer pessoa com conhecimento técnico pode contornar essa proteção inspecionando o código-fonte.

## 📁 Estrutura do projeto

```
Calculadora_Site/
├── index.html      → tela de login (senha)
├── app.html         → calculadora (protegida)
└── README.md        → este arquivo
```

## 🚀 Como hospedar no GitHub Pages

1. Crie um repositório no GitHub (pode ser privado ou público)
2. Suba estes arquivos para o repositório
3. Vá em **Settings → Pages**
4. Em "Source", selecione a branch `main` e a pasta `/ (root)`
5. Salve — o GitHub gera um link tipo `https://seu-usuario.github.io/nome-do-repo/`
6. Acesse esse link — ele abre automaticamente a tela de senha (`index.html`)

## 🔑 Alterar a senha

A senha não fica em texto puro no código — está como um hash SHA-256, dentro de `index.html`.

Para trocar a senha:

1. Abra um terminal e gere o novo hash:
   ```bash
   python3 -c "import hashlib; print(hashlib.sha256('NOVA_SENHA_AQUI'.encode()).hexdigest())"
   ```
2. Copie o resultado (uma sequência de letras e números)
3. Abra `index.html`, encontre a linha:
   ```js
   const HASH_CORRETO = "...";
   ```
4. Substitua pelo novo hash gerado
5. Salve e suba a alteração para o GitHub (`git add`, `git commit`, `git push`)

## ⏱️ Sessão

O acesso expira automaticamente após **2 horas** de inatividade, exigindo nova senha. Esse tempo pode ser ajustado em `app.html`, na constante `DUAS_HORAS`.

## 🛠️ Atualizando produtos e custos

A lista de produtos está dentro de `app.html`, na constante `produtos` (início do `<script>`). Cada item segue o formato:

```js
{ sku:"173C", nome:"Escova Onda", custo:2.22 },
```

Para atualizar um custo ou adicionar produto novo, edite essa lista e suba a alteração para o GitHub — o GitHub Pages atualiza o site automaticamente em poucos minutos.
