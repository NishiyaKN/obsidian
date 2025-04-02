## 🧠 **Memória Virtual: Conceitos e Configuração**

### 📌 **O que é Memória Virtual?**
- **Definição**: Extensão da RAM física usando espaço em disco (arquivo `pagefile.sys` no Windows ou `swap.img` no Linux).
- **Objetivo**: Permitir que o SO execute mais programas do que a RAM física suportaria, movendo dados pouco usados para o disco.

---

### 🖥️ **Arquivo de Paginação no Windows**
- **Localização**: `C:\pagefile.sys` (oculto por padrão).
- **Como visualizar**:
  - Explorer → Opções de Pasta → Exibir → Desmarque "Ocultar arquivos protegidos do sistema".
- **Comando CLI**:  
```cmd  
  wmic pagefile list /format:list  
```

#### ⚙️ **Configuração**
1. Acesse:  
   `Painel de Controle → Sistema → Configurações avançadas → Desempenho (Avançado) → Memória Virtual`.
2. Opções:
   - **Tamanho personalizado**: Defina valores iguais para "Tamanho inicial" e "Máximo" (ex: 1.5x da RAM física).
   - **Gerenciamento automático**: Desativado para controle manual.

---

### 🐧 **Swap no Linux**
- **Verificar uso**:  
 ```bash  
  swapon -s  
  free -h  
  cat /proc/swaps  
  ```

- **Arquivo de swap**: `/swap.img` (pode ser ajustado via `mkswap` e `swapon`).

---

### ⚠️ **Problemas Comuns**
1. **Baixa memória física + Swap intenso**:
   - Sintomas: Lentidão extrema, travamentos.
   - Solução: Aumentar RAM física ou reduzir carga de programas.
2. **Espaço em disco insuficiente**:
   - Garanta sempre 10% de espaço livre no disco onde reside o arquivo de paginação.

---

### 📊 **Monitoramento**
- **Windows**:  
  - Gerenciador de Tarefas → Aba "Desempenho" → Memória.
  - **Alerta crítico**: Uso acima de 90% da RAM + alta atividade de disco.
- **Linux**:  
  - Comando `top` ou `htop` (verifique a linha `Swap`).

---

### 🔧 **Boas Práticas**
- **Windows**:
  - Defina um tamanho fixo para `pagefile.sys` (ex: 1.5x da RAM) para evitar fragmentação.
  - Evite desativar totalmente a memória virtual (pode causar instabilidade).
- **Linux**:
  - Para servidores, considere um partitionamento dedicado para swap (melhor desempenho que arquivos).

---

### 🚨 **Cenários Críticos**
- **Erro "Computador com pouca memória"**:
  - Feche programas não essenciais.
  - Aumente o tamanho do arquivo de paginação ou adicione mais RAM.
- **Swap excessivo no Linux**:
  - Verifique processos com `ps aux --sort=-%mem | head`.

---

### 📚 **Links Úteis**
- [Microsoft: Gerenciamento do Arquivo de Paginação](https://learn.microsoft.com/pt-br/windows/client-management/introduction-page-file)
- [Linux: Como ajustar a swap](https://www.cyberciti.biz/faq/linux-check-swap-usage-command/)

---

### 🛠️ **Tarefa Prática (Windows)**
1. Abra `msconfig.exe`.
2. Em **Opções de Inicialização → Avançadas**, limite a memória máxima para 4096MB.
3. Teste abertura gradual de aplicativos até aparecer erros de memória.
4. **Dica**: Não reduza abaixo de 3072MB para evitar travamentos.
