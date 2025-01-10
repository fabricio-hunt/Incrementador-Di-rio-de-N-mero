# Incrementador Diário de Números

Este é um script Python que incrementa automaticamente um número em um arquivo de texto (`number.txt`), realiza um commit no Git com a data do dia e configura um job no cron para executar o script em um horário aleatório no dia seguinte. É perfeito para manter uma sequência de commits diários ou acompanhar números de forma automática.

---

## Configuração Inicial

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/Shogun89/fancy_job
   cd fancy_job
   ```

2. **Execute o script manualmente pela primeira vez:**

   Antes de configurar o cron, execute o script para garantir que ele está funcionando corretamente:

   ```bash
   python update_number.py
   ```

3. **(Opcional)** Configure o cron manualmente:

   Se preferir configurar o cron para rodar em um horário fixo (por exemplo, às 6h), edite o crontab:

   ```bash
   crontab -e
   ```

   Adicione a seguinte linha ao crontab:

   ```bash
   0 6 * * * cd /caminho/para/seu/repo && python update_number.py
   ```

---

## Funcionamento do Script

1. **Leitura e Incremento do Número:**
   - O script lê o número do arquivo `number.txt`.
   - Incrementa o valor em +1.

2. **Commit no Git:**
   - Realiza um commit com a mensagem "Update number: <data_atual>".

3. **Push para o Repositório Remoto:**
   - Envia as alterações para o repositório no GitHub.

4. **Atualização do Cron:**
   - Configura um job no cron para executar o script novamente em um horário aleatório do dia seguinte.

---

## Requisitos

- **Python 3**
- **Git** (configurado com acesso ao repositório remoto)
- Permissões para editar o crontab no sistema

---

## Arquivo `number.txt`

Certifique-se de que o arquivo `number.txt` existe na raiz do repositório e contém um número inicial (exemplo: `1`). O script utiliza esse arquivo para armazenar e atualizar o número.

---

## Mensagens de Commit

Os commits realizados pelo script seguem o formato:

```
Update number: YYYY-MM-DD
```

Onde `YYYY-MM-DD` é a data atual no momento da execução do script.

---

## Exemplo de Uso

1. Crie o arquivo `number.txt` com um valor inicial:

   ```bash
   echo 1 > number.txt
   ```

2. Execute o script manualmente:

   ```bash
   python update_number.py
   ```

3. Verifique os commits no repositório remoto após o push:

   ```bash
   git log
   ```

4. O cron será automaticamente atualizado para um horário aleatório do dia seguinte.

---

## Suporte

Se você encontrar problemas ou precisar de ajuda com este script, entre em contato ou abra uma issue no repositório.

