---

materia: Gestão de Serviços de TI 
tags:

- review
- n1

---
# GSTI e valor
→ [[Introdução à Gestão de Serviços de TI]]

- **TI moderna** = **parceira estratégica**, agente de **inovação** e **transformação digital**, foco em **valor contínuo**. TI antiga = **centro de custos**, **reativa**, **isolada** do negócio.
- **Serviço** = entrega **valor**, facilita **resultados** **sem** o cliente assumir **custos e riscos** específicos.

| | Produto | Serviço |
| :--- | :--- | :--- |
| Tangibilidade | **Tangível** | **Intangível** |
| Estoque | **Estocável** | Consumido **no uso** |
| Produção | **Antes** do uso | **Simultânea** ao uso |
| Posse | **Transfere** | **Não transfere** (acesso a benefícios) |
| Exemplo | Notebook, licença em disco | Suporte, nuvem, SLA |

- **Valor = Utilidade + Garantia**.
  - **Utilidade** = *fit for **purpose*** = **o que faz** (adequação ao propósito).
  - **Garantia** = *fit for **use*** = **como se comporta**: **disponibilidade, capacidade, segurança, continuidade**.
  - Sistema ótimo mas **fora do ar** → **sem garantia** → **valor destruído**. Utilidade **não compensa** falta de garantia.
- **Governança** = **direcionar, avaliar, monitorar** → **alinhamento**, **riscos**, **conformidade**; decide **quem** decide; **Alta Administração/Conselho**.
- **Gestão** = **executa** o plano; decide **como**; **gerentes e técnicos**.
- **Ciclo de vida (5 fases)**: Planejamento → Projeto (arquitetura, **SLA**, segurança) → **Transição** → Operação (fase **mais visível**) → Melhoria (**PDCA**).
  - **Transição** = pôr serviço **novo/modificado** em **produção** com **mínimo impacto** e **máxima segurança**: testes, **homologação**, implantação.

# ITIL 4
→ [[ITIL 4 e o Sistema de Valor de Serviço]]

- **SVS**: entrada **demanda e oportunidade** → saída **valor**. **5 componentes**: princípios orientadores, governança, **cadeia de valor**, práticas, melhoria contínua.
- **Princípios orientadores** = recomendações **universais e duradouras**, valem **em qualquer circunstância**.
- **Cadeia de Valor** = componente central, **6 atividades**: Planejar, **Melhorar**, Engajar, Desenhar e Transitar, Obter/Construir, Entregar e Suportar. **Flexível, não linear**.
  - **Melhorar** = melhoria contínua de serviços e práticas **em todos os níveis**.
- **Macete dos números**: **4** dimensões · **5** componentes · **6** atividades · **7** princípios.

| 4 dimensões | Abrange |
| :--- | :--- |
| **Organizações e Pessoas** | **estrutura formal, cultura, papéis, responsabilidades, competências** |
| Informação e Tecnologia | sistemas, dados, nuvem, segurança, ferramentas ITSM |
| Parceiros e Fornecedores | contratos, terceiros, SLAs com fornecedores |
| Fluxos de Valor e Processos | procedimentos, automação, KPIs |

- Tecnologia avançada **sem** pessoas treinadas e papéis definidos = **ineficaz** (dimensões precisam de **equilíbrio**).

| 7 princípios | Gatilho na questão |
| :--- | :--- |
| **Foco no Valor** | **toda atividade** ligada a **valor** para clientes/stakeholders |
| **Comece de onde você está** | **não descartar** o que existe; **reaproveitar**; evitar desperdício |
| Progredir iterativamente com feedback | etapas **menores**, feedback a cada ciclo |
| Colaborar e promover visibilidade | **fim dos silos**, transparência |
| Pensar e trabalhar holisticamente | **nenhum serviço é isolado** |
| Manter simples e prático | cortar **burocracia** sem valor |
| Otimizar e automatizar | **otimizar primeiro**, **depois** automatizar |

# Service Desk, incidente e requisição
→ [[Central de Serviços, Incidentes e Requisições]]

- **Service Desk** = **SPOC** (ponto único de contato) usuários ↔ TI.
  - Faz: **registrar** demandas, **restaurar** serviço rápido, **escalar** (N2/N3), **informar** status, **medir satisfação**.
  - **Não** faz: definir **orçamento/estratégia** da empresa.

| Modelo | Gatilho | Contra |
| :--- | :--- | :--- |
| **Local** | equipe **presencial em cada prédio**, **proximidade** | **custo alto**, despadronização |
| **Centralizado** | **uma equipe** num **único local físico**, padronização | pouco contato presencial |
| **Virtual** | **distribuído**, unidade **lógica** em nuvem, **24/7 Follow-the-Sun** | depende da **rede** |

- **Incidente** = **interrupção não planejada** **ou** **redução da qualidade** (lentidão conta).
- **Requisição** = pedido **padrão**, **previamente acordado**, **nada quebrou**: novo usuário, **software homologado**, senha, notebook.
- **Prioridade = Impacto × Urgência**.
  - **Impacto** = **extensão** (quantos usuários/processos).
  - **Urgência** = **tempo máximo suportável**.
- Sistema crítico (ex.: **UTI**) fora do ar = **incidente P1**. Instalar programa homologado = **requisição**.

| Impacto \ Urgência | Alta | Média | Baixa |
| :--- | :---: | :---: | :---: |
| **Alto** | P1 | P2 | P3 |
| **Médio** | P2 | P3 | P4 |
| **Baixo** | P3 | P4 | P4 |

# Problemas e causa raiz
→ [[Problemas, Mudanças e Acordos de Nível de Serviço]]

| | Incidente | Problema |
| :--- | :--- | :--- |
| Foco | **restaurar rápido** | **eliminar causa raiz** |
| Resposta | **contorno** (*workaround*) | **investigação** |
| Horizonte | **curto** (reativo) | **médio/longo** (preventivo) |

- **5 Porquês** = perguntar **"por quê?" repetidamente** até sair do **sintoma**. Raiz = falha de **processo/governança**, **não culpado**.
  - Ex.: servidor caiu → **superaquecimento** → refrigeração falhou → **sem manutenção** → **sem cronograma formalizado** (**raiz**).
- **Reiniciar** = contorno, **não resolve** o problema. **Encerrar incidente ≠ eliminar problema**.
- **Ishikawa** (espinha de peixe): **Pessoas, Métodos, Tecnologia, Equipamento, Ambiente, Medição**. Para problema **complexo**, vários fatores.
- **Erro conhecido** = causa achada, ainda não eliminada → **KEDB**.

# Mudanças
→ [[Problemas, Mudanças e Acordos de Nível de Serviço]]

| Tipo | Gatilho | Aprovação |
| :--- | :--- | :--- |
| **Padrão** | **baixo risco**, **rotineira**, procedimento documentado (ex.: **impressora**) | **pré-autorizada**, sem CAB |
| **Normal** | análise de risco, **RFC**, testes, **rollback** | **CAB** (médio/alto impacto) |
| **Emergencial** | **urgente**: incidente grave, **vulnerabilidade** | **ECAB** (rápido); documentação **depois** |

- Emergencial **não dispensa** avaliação de risco — só **simplifica** o fluxo.
- **CAB** = grupo **multidisciplinar**: avalia **impacto no negócio**, **mitigação de riscos**, **janela de manutenção**. **Não executa** a mudança.
- **Rollback** = plano de **retorno** ao estado anterior; **requisito essencial**.
- **RFC** = *Request for Change* (solicitação de mudança).

# SLA, OLA e UC
→ [[Problemas, Mudanças e Acordos de Nível de Serviço]]

| Acordo | Entre | Natureza |
| :--- | :--- | :--- |
| **SLA** | TI × **cliente/negócio** | formal / comercial |
| **OLA** | TI × **equipes internas** | operacional interno |
| **UC** | empresa × **fornecedor externo** (operadora, nuvem) | **contrato jurídico** (juridicamente vinculante) |

# COBIT 2019
→ [[Governança Corporativa de TI e COBIT 2019]]

- **ISACA**. Objetivo: **conectar metas de negócio aos processos de TI**, com **riscos**, **recursos** e **valor**. **Não substitui** ITIL/ISO 20000 — **integra**.
- **EDM** (*Evaluate, Direct, Monitor*) = **governança** = **Alta Administração / Conselho**.

| Domínio | Esfera | Foco |
| :--- | :--- | :--- |
| **EDM** | **Governança** | avaliar, dirigir, monitorar |
| APO | Gestão | estratégia, arquitetura, **riscos** |
| BAI | Gestão | desenvolvimento, **mudanças** |
| **DSS** | Gestão | **operações, suporte, segurança de dados** |
| MEA | Gestão | **controles internos, auditoria** |

- Gestão = **planejar, construir, executar, monitorar** (APO → BAI → DSS → MEA).
- **Princípio 1 — triplo de valor**: **benefícios**, **riscos**, **recursos**.
- **5 princípios** (material): partes interessadas · ponta a ponta · sistema dinâmico · distinção governança × gestão · **sob medida**.
  - **Sob medida** (*Tailored*) = ajustado a **porte, setor regulatório, estratégia, perfil de risco, cultura**.
  - **Sistema dinâmico** = **se readapta** quando mudam os **fatores de design**.

# Segurança da informação
→ [[Tríade CID e Princípios de Segurança da Informação]]

| Pilar | Gatilho |
| :--- | :--- |
| **Confidencialidade** | **só autorizados**; **divulgação**/**vazamento**; criptografia, MFA, RBAC |
| **Integridade** | **exata, completa**; **alteração/exclusão**; **hash**, assinatura digital |
| **Disponibilidade** | **acessível quando preciso**; backup, redundância, PCN |

- Vazou sem alterar nem derrubar → **só Confidencialidade**.
- **Complementares**:
  - **Autenticidade** = é **quem alega ser** (certificado digital, **MFA**, biometria).
  - **Autorização** = **o que pode** fazer (RBAC, **menor privilégio**).
  - **Não-repúdio** = **não pode negar** a autoria (assinatura digital, carimbo do tempo).
  - **Auditabilidade** = **registrar e rastrear** (logs, SIEM).
- **Ativo** = recurso com valor. **Ameaça** = **agente/evento** (ransomware, phishing). **Vulnerabilidade** = **fraqueza** (**sem patch**, senha fraca, **falta de treino**).
- **Risco** = **probabilidade** de uma **ameaça** explorar uma **vulnerabilidade** de um **ativo**, gerando **impacto**.
  - Slide: "**A × V × I**" (letras não expandidas). Revisão Q52: "**Ativo × Ameaça × Vulnerabilidade**". Decore a **frase** acima, não as letras.
- **Aplicar patch** = reduz a **vulnerabilidade**. **Seguro** = só **transfere** o prejuízo.

# LGPD e Privacy by Design
→ [[Legislação, Governança de Dados e LGPD]]

- **Lei 13.709/2018**; setores **público e privado**. Fiscalização: **ANPD**.
- **Dado pessoal** = pessoa natural **identificada** (CPF) **ou identificável** (cargo + empresa). Inclui **IP, geolocalização, placa de veículo** (são **comuns**, não sensíveis).
- **Dado sensível** = **biometria** (digital, facial), **DNA**, **saúde** (prontuário, exames, **convênio**), vida sexual, origem **racial/étnica**, opinião **política**, **religião**, filiação **sindical**.
- **Anonimizado** = não identifica, **irreversível** → **fora** da LGPD.
- **Pseudonimizado** ("pseudoanonimização" no slide) = troca por código (hash), chave guardada à parte → reidentificável → **LGPD se aplica**.
- **Tratamento** = **qualquer operação**: coleta, armazenamento, uso, compartilhamento, **eliminação**.
- **Ciclo de vida (5)**: coleta → armazenamento → utilização → compartilhamento → arquivamento & exclusão.

| Agente | Papel |
| :--- | :--- |
| **Titular** | a **pessoa natural** a quem os dados se referem |
| **Controlador** | **decide** (ex.: instituição de ensino) |
| **Operador** | trata **em nome** do controlador (ex.: **nuvem**, consultoria de folha) |
| **Encarregado (DPO)** | **ponte** controlador ↔ titulares ↔ ANPD · **orientador** interno · **gestor de crise** |

- **10 bases legais** (art. 7º): **consentimento**, **obrigação legal**, políticas públicas, pesquisa, **execução de contrato**, exercício de direitos, **proteção da vida** (titular **ou terceiros**), **tutela da saúde**, **legítimo interesse**, proteção do crédito.
  - **Sensível** → **art. 11**: sem legítimo interesse e sem proteção do crédito.
  - **Revender dados sem consentimento/justificativa** = **não** é base legal.

| Exemplo | Base |
| :--- | :--- |
| NF-e, eSocial | **obrigação legal** |
| Cadastro para entrega no e-commerce | **contrato** |
| Registros médicos, atendimento emergencial | **tutela da saúde** |
| Prevenção à fraude | **legítimo interesse** |
| Marketing | **consentimento** |

- **Consentimento** = **livre, informado, inequívoco**, **destacado**. **Caixa pré-marcada = opt-out automático = proibido**. Revogação **gratuita e facilitada**, a qualquer momento.
- **Legítimo interesse** = exige **LIA** (teste de balanceamento) + **expectativa do titular** (compatível com a relação).
- **Princípios**: **finalidade & adequação** (propósito explícito) · **necessidade = minimização** (mínimo de dados) · **transparência & livre acesso** · **segurança & prevenção**.
  - Coletar para um fim e usar para outro, sem avisar → fere **finalidade, adequação, transparência**.
- **Privacy by Design** = **Ann Cavoukian**: **desde a concepção**, **proativo, não reativo**, privacidade como padrão, segurança **ponta a ponta**.
- **Privacy by Default** = **maior privacidade por padrão**, compartilhamento **desligado de fábrica**, formulário só com o **indispensável**.
- **Práticas**: criptografia **TLS/HTTPS** (trânsito) + **AES-256** (descanso) · **RBAC** / menor privilégio · **DPIA = RIPD** (relatório de impacto, sistemas de **alto risco**).

# PSI, ISO 27001/27002 e fator humano
*Sem resumo de aula: os slides não vieram.*

- **PSI** (Política de Segurança da Informação) = **"lei interna"**; vale para **colaboradores, gestores e terceiros**.
- **Senhas** — certo: **12–16 caracteres** + complexidade, **MFA** em acesso remoto/crítico, **bloqueio** após tentativas, **cofre de senhas**. Errado: **compartilhar senha** (sobretudo de administrador).

| | ISO 27001 | ISO 27002 |
| :--- | :--- | :--- |
| O que é | **Requisitos** do **SGSI** | **Código de práticas** |
| Certifica? | **Sim** (auditável) | **Não** |
| Foco | gestão, **riscos**, **PDCA** | **como implementar os controles** |

- Macete: **27001 certifica**; **27002 explica como fazer**.
- **Fator humano** = **elo mais fraco**. **Firewall humano** = **conscientização contínua**, **simulação de phishing**, campanhas.

# ⚠️ Não confundir

| Par                                  | Diferença                                                                         |
| :----------------------------------- | :-------------------------------------------------------------------------------- |
| Incidente × Problema                 | **restaurar** × **eliminar causa raiz**                                           |
| Incidente × Requisição               | **falhou/degradou** × **pedido padrão**                                           |
| Governança × Gestão                  | **o quê/quem** (EDM, conselho) × **como** (APO/BAI/DSS/MEA, gerentes)             |
| Utilidade × Garantia                 | **o que faz** × **disponível, capaz, seguro, contínuo**                           |
| Sob medida × Dinâmico                | **porte, setor, cultura** × **readapta a mudanças**                               |
| Autenticidade × Não-repúdio          | **quem é** × **não pode negar depois**                                            |
| Autenticação × Autorização           | **quem é** × **o que pode**                                                       |
| Ameaça × Vulnerabilidade             | **agente/evento** × **fraqueza**                                                  |
| Confidencialidade × Integridade      | **vazou** × **alterou**                                                           |
| SLA × OLA × UC                       | **cliente** × **interno** × **fornecedor externo**                                |
| CAB × ECAB                           | mudança **normal** × **emergencial**                                              |
| Controlador × Operador × Encarregado | **decide** × **executa** × **canal**                                              |
| ISO 27001 × 27002                    | **requisitos/certifica** × **práticas/controles**                                 |
| Privacy by Design × by Default       | **desde a concepção** × **padrão mais restritivo**                                |
| Anonimizado × Pseudonimizado         | **irreversível, fora da LGPD** × **reidentificável, dentro da LGPD**              |
| Dado comum × sensível                | **IP, geolocalização, placa** = comum × **biometria, saúde, convênio** = sensível |
| Local × Centralizado × Virtual       | **presencial por prédio** × **um local** × **distribuído 24/7**                   |

# 🎯 Eliminar alternativas

- **Absurdas** (demissões, folha de pagamento, direito penal, cabeamento, escolaridade, férias) → descarte na hora.
- "**Exclusivamente**", "**totalmente**", "**dispensa qualquer**", "**independentemente**" → quase sempre errada.
- "**Substitui** a ITIL / a LGPD" → errada: frameworks **se integram**; norma **não substitui** lei.
- **Inversões** que caem: incidente ↔ problema, requisição ↔ incidente, EDM atribuído à gestão, **27001 ↔ 27002**, "utilidade compensa garantia".
- Perguntas de **NÃO / inadequada**: **Q11, Q34, Q39** — marque a errada.
- **Asserção-razão**: julgue **I**, julgue **II**; se **II é falsa**, nem precisa analisar se justifica.