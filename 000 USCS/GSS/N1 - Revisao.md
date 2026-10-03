---

materia: Gestão de Serviços de TI 
fonte: Revisão.pdf 
tags:

- atividade
- revisao
- n1

---
# 📝 Atividade — Revisão para a N1

## 👁️ Visão geral

Atividade de revisão da disciplina **Gestão de Serviços e Segurança em Sistemas Computacionais**: 55 questões de múltipla escolha, feita em grupo, que vale para a **AF (Avaliação Formativa, 2 pontos)** e serve de estudo para a **N1**. As questões 1–40 são diretas; as 41–55 ("transformadas") cobram os mesmos conceitos em casos práticos e asserções.

Cobre tudo o que foi resumido nas aulas 1 a 6 — [[Introdução à Gestão de Serviços de TI]], [[ITIL 4 e o Sistema de Valor de Serviço]], [[Central de Serviços, Incidentes e Requisições]], [[Problemas, Mudanças e Acordos de Nível de Serviço]], [[Governança Corporativa de TI e COBIT 2019]] e [[Tríade CID e Princípios de Segurança da Informação]] —, a aula 7 ([[Legislação, Governança de Dados e LGPD]]: questões 31 a 35, 53 e 54) e mais **PSI, ISO 27001/27002 e fator humano**, assuntos cujos slides não vieram para mim. Para esses últimos, as explicações estão no [[REVIEW — Gestão de Serviços e Segurança (N1)]].

A professora depois divulgou o **gabarito oficial**, e as 55 respostas abaixo batem com ele. O quiz interativo com estas questões e as 91 do Wayground está no arquivo `Quiz — Revisões GSTI e Segurança.html`, e o resumo geral para a prova em [[REVIEW — Gestão de Serviços e Segurança (Geral)]].

> [!tip] Três questões pedem a alternativa errada
> As questões **11**, **34** e **39** pedem a alternativa que **NÃO** é correta ou que é **inadequada**. Leia o enunciado inteiro antes de marcar.

## 📋 Questões

### Parte 1 — Questões diretas (1 a 40)

**1. [GSTI — Evolução]** Na evolução histórica da Tecnologia da Informação nas organizações, a TI deixou de ser vista puramente como um centro de custos operacional e passou a ser reconhecida como uma parceira estratégica principal. Sobre essa evolução, assinale a alternativa que apresenta a principal característica dessa nova visão moderna:

A) Atuação estritamente reativa às solicitações manuais de manutenção de computadores.
B) Foco exclusivo no suporte técnico de hardware sem alinhamento com o faturamento.
C) Agente fundamental de inovação, transformação digital e foco na geração contínua de valor de negócio.
D) Isolamento completo em relação aos objetivos de expansão e metas comerciais da empresa.
E) Redução da TI a uma despesa administrativa fixa e inevitável.

> [!success]- Resposta
> **C.** É a definição da TI na visão estratégica (aula 1): parceira estratégica, **agente de inovação e transformação digital**, focada na **geração contínua de valor**. As alternativas A, B, D e E descrevem a visão **antiga** (reativa, só suporte, isolada, centro de custos).

**2. [GSTI — Produto vs Serviço]** Compreender a diferença funcional entre Produto e Serviço é indispensável para a governança moderna de TI baseada na ITIL. Assinale a alternativa que descreve corretamente um atributo característico de um Serviço:

A) Possui tangibilidade física e pode ser estocado em inventário antes do uso.
B) É produzido antes do momento de uso, transferindo imediatamente a propriedade do bem ao cliente.
C) É intangível, consumido simultaneamente à sua produção e oferece acesso a benefícios sem transferência de propriedade.
D) Representa um item estático, como um notebook ou licença gravada em disco.
E) Elimina inteiramente a responsabilidade de suporte, recaindo o risco de paradas de forma integral sobre o comprador.

> [!success]- Resposta
> **C.** Serviço = **intangível**, **produzido e consumido simultaneamente**, dá **acesso a benefícios sem transferência de posse**. A, B e D descrevem **produto** (tangível, estocável, produzido antes, transfere posse; notebook e licença em disco são os exemplos de produto da aula 1). E inverte a ideia: é justamente **sem** o serviço que o risco de paradas recai sobre o comprador.

**3. [ITIL — Conceito de Valor]** Segundo a visão do ITIL (Information Technology Infrastructure Library), o Valor gerado por um serviço é a combinação de dois fatores principais. Assinale a alternativa que define corretamente esses dois pilares:

A) Custo Operacional e Retorno Financeiro (ROI).
B) Utilidade (adequação ao propósito) e Garantia (disponibilidade, capacidade, segurança e continuidade).
C) Infraestrutura Física e Licenciamento de Software.
D) Velocidade de Atendimento do Service Desk e Quantidade de Chamados Encerrados.
E) Conformidade com a LGPD e Redução de Pessoal Técnico.

> [!success]- Resposta
> **B.** **Valor = Utilidade + Garantia**. Utilidade = *fit for purpose* (o que o serviço faz); Garantia = *fit for use* (disponibilidade, capacidade, segurança e continuidade).

**4. [Governança vs Gestão]** A Governança de TI especifica os direitos de decisão e o arcabouço de responsabilidades para encorajar comportamentos desejáveis no uso da TI, diferenciando-se da Gestão Operacional. Analise as alternativas abaixo e assinale a que descreve corretamente a atribuição da Governança:

A) Executar o plano alinhado e determinar como as atividades diárias de suporte são feitas pelos técnicos.
B) Direcionar, avaliar e monitorar o alinhamento estratégico, a gestão de riscos e a conformidade regulatória.
C) Codificar soluções tecnológicas, instalar sistemas operacionais e realizar a manutenção preventiva de impressoras.
D) Atender chamados de usuários no balcão de atendimento e registrar incidentes operacionais de rede.
E) Comprar ativos de hardware e negociar prazos de entrega com transportadoras terceirizadas.

> [!success]- Resposta
> **B.** Governança **direciona, avalia e monitora**, cuidando de **alinhamento estratégico, riscos e conformidade** (os papéis da governança na aula 1). A alternativa A é a **gestão** ("executa o plano", "determina **como**"); C, D e E são atividades operacionais.

**5. [Ciclo de Vida do Serviço]** O Ciclo de Vida dos Serviços de TI exige rigor em suas etapas para garantir o sucesso operacional. Dentre as fases abaixo, assinale a que corresponde ao estágio responsável por garantir que serviços novos ou modificados sejam colocados em produção com o mínimo de impacto e máximo de segurança (incluindo testes rigorosos e homologação):

A) Planejamento
B) Projeto
C) Transição
D) Operação
E) Melhoria Contínua

> [!success]- Resposta
> **C.** A **Transição** coloca serviços novos, modificados ou reconfigurados em produção com **mínimo impacto e máximo de segurança**: testes, treinamento, homologação e implantação. Projeto (B) é arquitetura, SLA e segurança; Operação (D) é o dia a dia.

**6. [ITIL v4 — SVS]** A ITIL v4 introduziu o conceito de Sistema de Valor de Serviço (SVS) para descrever como todos os componentes e atividades de uma organização trabalham juntos para criar valor. O componente central que define as 6 atividades operacionais interconectadas para responder à demanda é denominado:

A) As Quatro Dimensões da Gestão.
B) Princípios Orientadores.
C) Cadeia de Valor do Serviço (Service Value Chain).
D) Acordo de Nível de Serviço (SLA).
E) Governança Corporativa EDM.

> [!success]- Resposta
> **C.** A **Cadeia de Valor do Serviço** é o modelo operacional do SVS, com as **6 atividades** (Planejar, Melhorar, Engajar, Desenhar e Transitar, Obter/Construir, Entregar e Suportar). As 4 dimensões (A) sustentam o serviço; os princípios (B) orientam decisões.

**7. [ITIL v4 — 4 Dimensões]** Para entregar serviços com qualidade e eficácia, a ITIL v4 estabelece que a organização deve equilibrar quatro dimensões fundamentais. A dimensão que aborda a estrutura organizacional formal, a cultura corporativa, os papéis, as responsabilidades e as competências individuais é:

A) Informação e Tecnologia.
B) Organizações e Pessoas.
C) Parceiros e Fornecedores.
D) Fluxos de Valor e Processos.
E) Infraestrutura e Redes em Nuvem.

> [!success]- Resposta
> **B.** **Organizações e Pessoas** = estrutura formal, cultura, papéis, responsabilidades, competências. "Infraestrutura e Redes em Nuvem" (E) nem é uma das 4 dimensões.

**8. [ITIL v4 — Princípios]** Dentre os Sete Princípios Orientadores da ITIL v4, existe um que estabelece que toda e qualquer atividade realizada pela organização deve estar direta ou indiretamente vinculada à geração de valor para os clientes e stakeholders. Esse princípio é conhecido como:

A) Comece de onde você está.
B) Progredir iterativamente com feedback.
C) Foco no Valor.
D) Pensar e trabalhar holisticamente.
E) Manter simples e prático.

> [!success]- Resposta
> **C.** **Foco no Valor** — pergunta-chave: "como esta atividade gera valor?". Se a resposta for "nenhum", a atividade deve ser reavaliada ou eliminada.

**9. [ITIL v4 — Princípios]** Um dos princípios orientadores da ITIL v4 recomenda que a organização não deve descartar o que já existe sem antes analisar o cenário atual, aproveitando serviços, processos e ferramentas que já funcionam bem para evitar desperdícios. Esse princípio é denominado:

A) Otimizar e Automatizar.
B) Colaborar e promover visibilidade.
C) Comece de onde você está.
D) Foco no Valor.
E) Pensar e trabalhar holisticamente.

> [!success]- Resposta
> **C.** **Comece de onde você está**: avaliar o cenário atual e reaproveitar o que funciona; recriar do zero gera custo e resistência cultural.

**10. [ITIL v4 — Service Value Chain]** Na Cadeia de Valor do Serviço da ITIL v4, a atividade específica que tem como objetivo assegurar a melhoria contínua de serviços e práticas em todos os níveis da organização é chamada de:

A) Planejar.
B) Engajar.
C) Desenhar e Transitar.
D) Obter / Construir.
E) Melhorar.

> [!success]- Resposta
> **E.** **Melhorar** = melhoria contínua de serviços e práticas **em todos os níveis**. Planejar = visão e direção; Engajar = partes interessadas; Desenhar e Transitar = qualidade e custo; Obter/Construir = componentes.

**11. [Práticas ITIL — Service Desk]** A Central de Serviços (Service Desk) atua como o Ponto Único de Contato (SPOC) entre os usuários e a equipe de TI. Dentre as alternativas abaixo, qual **NÃO** representa um objetivo fundamental do Service Desk:

A) Registrar e capturar todas as demandas e interrupções.
B) Restaurar a operação normal dos serviços no menor tempo possível.
C) Definir unilateralmente as diretrizes macroeconômicas e o orçamento estratégico global da corporação.
D) Manter o usuário informado sobre o andamento e status de seus chamados.
E) Medir continuamente a satisfação dos usuários através de pesquisas de feedback.

> [!success]- Resposta
> **C** (é a que **não** representa). Definir diretrizes e orçamento estratégico é papel da **alta administração / governança**, não da Central de Serviços. A, B, D e E são funções da Central vistas na aula 3: receber e registrar, resolver incidentes, comunicar e medir satisfação.

**12. [Práticas ITIL — Service Desk]** Existem diferentes modelos estruturais para a Central de Serviços segundo a ITIL. Aquele em que equipes de suporte são alocadas presencialmente em cada unidade física ou prédio da organização, garantindo proximidade com o usuário, porém com maior custo operacional, é denominado:

A) Service Desk Centralizado.
B) Service Desk Virtual (Follow-the-Sun).
C) Service Desk Local.
D) Service Desk Terceirizado em Nuvem Global.
E) Service Desk Automatizado por IA Pura.

> [!success]- Resposta
> **C.** **Local** = equipe presencial em cada unidade; vantagem: proximidade; desvantagens: **custo** (mão de obra duplicada) e despadronização. D e E não são modelos da ITIL.

**13. [Práticas ITIL — Incidente]** De acordo com a taxonomia da ITIL v4, um Incidente difere essencialmente de uma Requisição de Serviço. Assinale a alternativa que caracteriza corretamente um Incidente:

A) Solicitação de criação e concessão de novo usuário no domínio.
B) Pedido padronizado para instalação de um software homologado.
C) Uma interrupção não planejada de um serviço de TI ou a redução da qualidade de um serviço.
D) Solicitação de alteração ou redefinição de senha esquecida.
E) Compra programada e entrega de um novo notebook corporativo.

> [!success]- Resposta
> **C.** É a definição ITIL v4 de incidente. A, B, D e E são os **quatro exemplos de requisição** da aula 3 (novo usuário, software homologado, senha, notebook).

**14. [Práticas ITIL — Priorização]** Para a determinação da prioridade de atendimento de um chamado de TI, a ITIL utiliza a fórmula baseada no cruzamento de dois eixos fundamentais:

A) Custo do Hardware e Tempo de Garantia.
B) Impacto (extensão e gravidade no negócio) e Urgência (tempo máximo suportável antes de prejuízos graves).
C) Número de Versões do Software e Complexidade do Código-Fonte.
D) Quantidade de Colaboradores na Empresa e Faturamento Bruto Anual.
E) Nível de Escolaridade do Usuário e Localização Geográfica.

> [!success]- Resposta
> **B.** **Prioridade = Impacto × Urgência**. Impacto = extensão (quantos usuários/processos); urgência = tempo máximo suportável.

**15. [Práticas ITIL — Requisição]** Dentre os chamados recebidos por uma Central de Serviços, analise as opções abaixo e indique qual delas configura estritamente uma Requisição de Serviço e não um incidente:

A) Queda total do link de internet da filial principal.
B) Servidor de banco de dados central inativo, paralisando as vendas.
C) Solicitação de criação de novo acesso e perfil para um colaborador recém-contratado.
D) Estação de trabalho do diretor executivo que não liga por defeito na placa-mãe.
E) Lentidão extrema generalizada no sistema ERP durante o fechamento contábil.

> [!success]- Resposta
> **C.** Criar acesso para recém-contratado é **pedido padrão**, nada falhou. As demais são **incidentes**: queda (A, B), falha de hardware (D) e lentidão (E — **redução da qualidade** também é incidente).

**16. [Práticas ITIL — Problemas]** O Gerenciamento de Problemas busca investigar a fundo a causa raiz das falhas na infraestrutura de TI. Assinale a alternativa que diferencia corretamente um Incidente de um Problema:

A) O incidente foca na investigação de longo prazo, enquanto o problema foca na restauração imediata por meio de soluções de contorno temporárias.
B) O incidente foca na restauração rápida do serviço afetado (solução de contorno), enquanto o problema foca na investigação aprofundada para eliminar definitivamente a causa raiz.
C) O incidente trata exclusivamente de erros de software, enquanto o problema trata apenas de compras de hardware.
D) O incidente é gerido pela Alta Administração, enquanto o problema é tratado por analistas de nível operacional básico.
E) Não há distinção conceitual entre ambos na ITIL v4.

> [!success]- Resposta
> **B.** Incidente = **restaurar rápido** (contorno, curto prazo); problema = **eliminar a causa raiz** (investigação, médio/longo prazo). A é a pegadinha: **inverte** os dois.

**17. [Práticas ITIL — Causa Raiz]** Para realizar a análise de causa raiz de um problema complexo de forma interativa, perguntando repetidamente o motivo de uma falha para ultrapassar sintomas superficiais, utiliza-se amplamente a técnica conhecida como:

A) Matriz de Impacto e Urgência.
B) Técnica dos 5 Porquês.
C) Análise de Custo-Benefício ROI.
D) Diagrama de Forças de Porter.
E) Acordo de Nível Operacional (OLA).

> [!success]- Resposta
> **B.** Os **5 Porquês**: perguntar "por quê?" repetidamente (geralmente cinco vezes) até sair do sintoma e chegar à causa raiz. A matriz de impacto e urgência (A) serve para **priorizar**, não para achar causa.

**18. [Práticas ITIL — Mudanças]** Na prática de Habilitação de Mudanças (Change Enablement) da ITIL v4, as mudanças são classificadas de acordo com seu risco e impacto. Aquela que apresenta baixo risco, é bem compreendida, pré-autorizada e segue um procedimento documentado e rotineiro (como a instalação de uma impressora) é chamada de:

A) Mudança Normal.
B) Mudança Emergencial.
C) Mudança Padrão (Standard).
D) Mudança Crítica do ECAB.
E) Mudança Estratégica de Diretoria.

> [!success]- Resposta
> **C.** **Padrão** = baixo risco, **pré-autorizada**, procedimento documentado e rotineiro (instalar impressora é exemplo do próprio slide). D e E não existem como tipos.

**19. [Práticas ITIL — CAB]** O Comitê Consultivo de Mudanças (Change Advisory Board — CAB) é um grupo multidisciplinar fundamental na governança de TI. Sua principal responsabilidade no fluxo de mudanças normais é:

A) Executar manualmente códigos de atualização de servidores em ambiente produtivo.
B) Avaliar o impacto no negócio, analisar planos de mitigação de riscos e verificar janelas de manutenção de mudanças de médio e alto impacto.
C) Atender ligações de usuários no Service Desk para redefinição de senhas.
D) Realizar auditorias contábeis e fiscais do faturamento trimestral da empresa.
E) Conceder descontos em contratos de fornecedores terceirizados de links de internet.

> [!success]- Resposta
> **B.** É a frase das responsabilidades do CAB na aula 4: avaliar **impacto no negócio**, analisar **mitigação de riscos** e verificar **janela de manutenção**, para mudanças **normais de médio/alto impacto**. O CAB **avalia e autoriza**, não executa (A).

**20. [Acordos de Nível de Serviço]** No contexto dos acordos de nível de serviço, o documento formal e juridicamente vinculante firmado entre a organização corporativa e um Fornecedor Externo (como uma operadora de telecomunicações ou provedor de nuvem) é denominado:

A) SLA (Service Level Agreement).
B) OLA (Operational Level Agreement).
C) UC (Underpinning Contract ou Contrato de Apoio Subjacente).
D) RFC (Request for Change).
E) KEDB (Known Error Database).

> [!success]- Resposta
> **C.** **UC** = contrato **juridicamente vinculante** com **fornecedor externo**. SLA = TI × cliente; OLA = entre equipes **internas**; RFC = solicitação de mudança; KEDB = base de erros conhecidos.

**21. [COBIT 2019 — Objetivos]** O COBIT 2019, desenvolvido pela ISACA, é um framework de referência mundialmente reconhecido para a governança e gestão da informação e tecnologia corporativa. Dentre os objetivos fundamentais do COBIT, destaca-se:

A) Substituir completamente a necessidade de frameworks operacionais como a ITIL e a ISO 20000.
B) Conectar metas de negócios aos processos de TI, assegurando gestão de riscos, otimização de recursos e geração de valor.
C) Controlar exclusivamente a folha de pagamento e o departamento de recursos humanos das empresas.
D) Estabelecer regras estritamente técnicas para fiação de redes locais de computadores.
E) Regulamentar o direito penal brasileiro em crimes cibernéticos.

> [!success]- Resposta
> **B.** É a frase do slide do COBIT: **conecta metas de negócio aos processos de TI**, com **riscos, recursos e valor**. A é a pegadinha: o COBIT **se integra** à ITIL e à ISO 20000, não as substitui.

**22. [COBIT 2019 — Governança EDM]** O COBIT 2019 estabelece uma distinção rigorosa entre Governança e Gestão. O modelo de governança EDM (Evaluate, Direct and Monitor) define as responsabilidades essenciais atribuídas a qual esfera organizacional?

A) Aos técnicos de suporte de Nível 1 do Service Desk.
B) À Alta Administração e ao Conselho de Administração.
C) Aos estagiários de desenvolvimento de software.
D) Aos fornecedores externos de hardware.
E) Aos operadores de entrada de dados em planilhas.

> [!success]- Resposta
> **B.** EDM é **governança**: responsabilidade **indelegável** da **Alta Administração / Conselho**.

**23. [COBIT 2019 — Domínios]** Dentro do sistema de gestão estruturado pelo COBIT 2019, os domínios operacionais e táticos são divididos em quatro grandes siglas que cobrem o ciclo de planejamento, construção, execução e monitoramento. O domínio focado especificamente em Operações, Suporte e Segurança de Dados é o:

A) APO (Align, Plan & Organize).
B) BAI (Build, Acquire & Implement).
C) DSS (Deliver, Service & Support).
D) MEA (Monitor, Evaluate & Assess).
E) EDM (Evaluate, Direct & Monitor).

> [!success]- Resposta
> **C.** **DSS** = operações, suporte e segurança de dados. APO = estratégia, arquitetura, riscos; BAI = desenvolvimento e mudanças; MEA = controles internos e auditoria. EDM (E) é **governança**, não gestão.

**24. [COBIT 2019 — Tríplice de Valor]** O primeiro princípio de governança do COBIT 2019 trata da Geração de Valor para as partes interessadas (stakeholders). Esse princípio exige o equilíbrio contínuo de um tríplice de valor composto por:

A) Realização de Benefícios, Otimização de Riscos e Otimização de Recursos.
B) Faturamento Bruto, Redução de Impostos e Lucro Líquido.
C) Velocidade de Impressão, Quantidade de Monitores e Espaço em Disco.
D) Número de Colaboradores CLT, Horas Extras e Férias Vencidas.
E) Custo de Licenciamento, Despesas de Viagem e Manutenção Predial.

> [!success]- Resposta
> **A.** Equilíbrio triplo: **benefícios, riscos e recursos** (que correspondem aos objetivos EDM02, EDM03 e EDM04).

**25. [COBIT 2019 — Princípios]** O princípio do COBIT 2019 que determina que o sistema de governança deve ser ajustado de acordo com o porte, setor regulatório, estratégia competitiva, perfil de risco e cultura específica da organização é chamado de:

A) Sistema Dinâmico.
B) Abordagem Ponta a Ponta.
C) Distinção Clarividente entre Governança e Gestão.
D) Sob Medida (Tailored).
E) Visão Holística de Ativos.

> [!success]- Resposta
> **D.** **Sob Medida** (*Tailored*) = ajustado a porte, setor regulatório, estratégia, perfil de risco e cultura. **Sistema Dinâmico** (A) é o que se readapta quando os **fatores de design mudam** — parecido, mas é outro princípio.

**26. [Segurança — Tríade CID]** A Segurança da Informação é sustentada pela espinha dorsal conhecida como Tríade CID. O pilar fundamental que garante que a informação seja acessível exclusivamente por pessoas, processos ou sistemas devidamente autorizados, prevenindo divulgação indevida, chama-se:

A) Integridade.
B) Disponibilidade.
C) Confidencialidade.
D) Autenticidade.
E) Não-Repúdio.

> [!success]- Resposta
> **C.** **Confidencialidade** = acesso **só para autorizados**, prevenindo **divulgação** não autorizada. Autenticidade (D) e não-repúdio (E) são atributos complementares, não pilares da tríade.

**27. [Segurança — Tríade CID]** O pilar da Tríade CID que assegura que a informação permaneça exata, completa e protegida contra modificações ou exclusões não autorizadas ou acidentais (utilizando, por exemplo, funções Hash criptográficas) é a:

A) Confidencialidade.
B) Disponibilidade.
C) Integridade.
D) Auditabilidade.
E) Autorização Baseada em Papéis.

> [!success]- Resposta
> **C.** **Integridade** = exata, completa, protegida contra **alteração ou exclusão**. **Hash** é o mecanismo típico de integridade.

**28. [Segurança — Autenticidade]** No escopo da Segurança da Informação, o atributo complementar que garante que a entidade (usuário ou sistema) é realmente quem alega ser, podendo ser validado por meio de certificados digitais ou Autenticação Multifator (MFA), denomina-se:

A) Não-Repúdio.
B) Autenticidade.
C) Confidencialidade Absoluta.
D) Disponibilidade Redundante.
E) Criptografia Simétrica de Repouso.

> [!success]- Resposta
> **B.** **Autenticidade** = é **quem alega ser** (certificado ICP-Brasil, biometria, MFA). Não-repúdio (A) = **não poder negar** a autoria depois.

**29. [Segurança — Equação do Risco]** A equação fundamental do risco na Segurança da Informação estabelece que o risco surge da interação entre determinados elementos essenciais. Assinale a alternativa que expressa corretamente essa relação conceitual:

A) Risco = Custo de Hardware × Quantidade de Licenças.
B) Risco = Probabilidade de uma Ameaça explorar uma Vulnerabilidade de um Ativo, gerando um Impacto ao negócio.
C) Risco = Faturamento Anual dividido pelo Número de Incidentes.
D) Risco = Velocidade de Conexão da Internet mais o Salário dos Técnicos.
E) Risco = Grau de Escolaridade dos Usuários menos o Número de Senhas.

> [!success]- Resposta
> **B.** Risco = **probabilidade** de uma **ameaça** explorar uma **vulnerabilidade** de um **ativo**, gerando **impacto**. É a única alternativa com os quatro elementos da cadeia de risco da aula 6.

**30. [Segurança — Vulnerabilidade]** Uma empresa possui um banco de dados de clientes armazenado em um servidor local. Devido à falta de atualizações de segurança e ausência de patches, o sistema foi invadido por um software de resgate que criptografou todos os arquivos e exigiu pagamento financeiro. Na análise de risco corporativa, a ausência de patches e a fraqueza explorada no sistema representam tecnicamente:

A) Um Ativo de Informação Humano.
B) Uma Vulnerabilidade.
C) Uma Medida de Governança EDM.
D) Um Acordo de Nível Operacional (OLA).
E) Uma Mudança Padrão pré-autorizada.

> [!success]- Resposta
> **B.** A **fraqueza** explorada (falta de patches) é a **vulnerabilidade**. O ransomware é a **ameaça**; o banco de dados é o **ativo**.

**31. [LGPD — Conceito]** A Lei Geral de Proteção de Dados (LGPD — Lei nº 13.709/2018) regulamenta o tratamento de dados pessoais no Brasil. Um "Dado Pessoal" é definido legalmente como:

A) Qualquer informação econômica referente exclusivamente a empresas multinacionais de capital aberto.
B) Toda informação relacionada a uma pessoa natural identificada ou identificável.
C) Dados estritamente estatísticos e anônimos que não possuem nenhuma relação com seres humanos.
D) Documentos públicos arquivados em repartições federais sem vínculo com cidadãos.
E) Códigos de servidores em nuvem corporativa.

> [!success]- Resposta
> **B.** Dado pessoal = informação relacionada a **pessoa natural identificada ou identificável** (art. 5º da LGPD). Dado **anônimo** (C) não é dado pessoal; dados de **empresas** (A) também não. Ver [[Legislação, Governança de Dados e LGPD#🗂️ Tipos de dado]].

**32. [LGPD — Dados Sensíveis]** A LGPD estabelece proteção reforçada a uma categoria específica de dados devido ao alto potencial de discriminação ou impacto à intimidade do titular. Essa categoria é denominada:

A) Dado Pessoal Comum.
B) Dado Pessoal Sensível (como origem racial, convicção religiosa, dados de saúde e biométricos).
C) Dado Anonimizado Irreversível.
D) Dado de IP e Geolocalização de Navegação.
E) Dado de Placa de Veículo Comercial.

> [!success]- Resposta
> **B.** **Dado pessoal sensível**: origem racial ou étnica, convicção religiosa, opinião política, filiação sindical, **saúde** (inclusive dados de convênio, pelo slide da aula 7), vida sexual, dado **genético** ou **biométrico**.
> As alternativas D e E são pegadinha: **IP, geolocalização e placa de veículo** aparecem na aula 7 como dados pessoais **comuns**, não sensíveis.

**33. [LGPD — Agentes de Tratamento]** Segundo a LGPD, o agente de tratamento encarregado de tomar as principais decisões referentes ao tratamento de dados pessoais, definindo finalidades e meios de coleta, é o:

A) Operador.
B) Controlador.
C) DPO (Data Protection Officer / Encarregado).
D) Auditor Externo da ANPD.
E) Usuário Titular dos Dados.

> [!success]- Resposta
> **B.** **Controlador** = **decide** (finalidade e meios). **Operador** (A) = trata os dados **em nome** do controlador. **Encarregado/DPO** (C) = **canal de comunicação** entre controlador, titulares e ANPD. Cuidado com a palavra "encarregado" no enunciado: ali significa "responsável", não o cargo.

**34. [LGPD — Bases Legais]** Todo tratamento de dados pessoais sob a égide da LGPD exige obrigatoriamente o amparo de uma base legal válida. Dentre as opções abaixo, qual **NÃO** constitui uma base legal prevista na legislação brasileira:

A) O consentimento expresso e destacado do titular.
B) O cumprimento de obrigação legal ou regulatória pelo controlador.
C) A execução de contrato ou procedimentos preliminares relacionados a contrato do qual seja parte o titular.
D) A aquisição e revenda de dados de navegação para fins de lucro ilimitado sem consentimento ou justificativa.
E) O legítimo interesse do controlador, precedido de teste de balanceamento (LIA).

> [!success]- Resposta
> **D** (é a que **não** é base legal). Revender dados **sem consentimento ou justificativa** não tem amparo na lei. Consentimento (A), obrigação legal (B), execução de contrato (C) e legítimo interesse (E) estão entre as **10 bases legais** do art. 7º. **LIA** = *Legitimate Interest Assessment*, o teste que pondera o interesse da empresa contra os direitos do titular.

**35. [LGPD — Privacy by Design]** O conceito desenvolvido por Ann Cavoukian que estabelece que a proteção de dados e a privacidade devem ser arquitetadas desde a fase inicial de concepção de um projeto, produto ou sistema (sendo proativo e não reativo) é chamado de:

A) ITIL v4 Service Value System.
B) Privacy by Design.
C) Change Enablement Normal.
D) COBIT Domain EDM05.
E) Tríade CID de Disponibilidade.

> [!success]- Resposta
> **B.** **Privacy by Design** (privacidade desde a concepção), de **Ann Cavoukian**: privacidade embutida **desde o início**, **proativa, não reativa**.

**36. [PSI — Conceito]** A Política de Segurança da Informação (PSI) é o documento formal que estabelece as diretrizes, princípios e regras institucionais para proteger os ativos de informação de uma organização. Pode-se afirmar corretamente que a PSI funciona como:

A) Um manual de instruções puramente estético para montagem de computadores pessoais.
B) A "lei interna" da organização, orientando colaboradores, gestores e terceiros sobre o uso seguro dos recursos tecnológicos.
C) Um contrato comercial de compra e venda de licenças de software com fornecedores estrangeiros.
D) Uma planilha contábil de apuração de impostos federais.
E) Um cronograma de férias obrigatórias dos funcionários da área de marketing.

> [!success]- Resposta
> **B.** A PSI é a **"lei interna"** de segurança: vale para **colaboradores, gestores e terceiros**.

**37. [ISO 27001 — Escopo]** Dentre as normas internacionais de segurança, a ABNT NBR ISO/IEC 27001 destaca-se por ter uma finalidade muito específica em relação ao Sistema de Gestão da Segurança da Informação (SGSI). Assinale a alternativa que descreve corretamente esse papel:

A) Fornecer um guia técnico opcional e informal de dicas de navegação na web.
B) Especificar os requisitos obrigatórios e auditáveis para estabelecer, implementar, manter e certificar um SGSI orientado a riscos com base no ciclo PDCA.
C) Regulamentar o código penal brasileiro para crimes de furto de hardware.
D) Substituir integralmente as diretrizes da LGPD perante a ANPD.
E) Definir tabelas de preços de servidores em nuvem da AWS e Microsoft Azure.

> [!success]- Resposta
> **B.** A **ISO 27001** traz os **requisitos** do **SGSI**: **auditáveis**, **certificáveis**, **orientados a riscos**, com ciclo **PDCA**. Norma não substitui lei (D).

**38. [ISO 27001 vs 27002]** No tocante à aplicação prática das normas da família ISO 27000, existe uma diferença fundamental de escopo entre a ISO/IEC 27001 e a ISO/IEC 27002. Assinale a alternativa que diferencia corretamente ambas:

A) A ISO 27001 define os REQUISITOS obrigatórios do SGSI, focando em gestão e governança, enquanto a ISO 27002 fornece o código de práticas e diretrizes detalhadas para a implementação dos controles de segurança.
B) A ISO 27001 trata de finanças corporativas, enquanto a ISO 27002 trata de manutenção predial.
C) A ISO 27001 é aplicada apenas a pequenas empresas, enquanto a ISO 27002 é exclusiva para governos federais.
D) Não há qualquer distinção técnica entre as duas normas.
E) A ISO 27002 é auditável para certificação internacional, ao passo que a ISO 27001 serve apenas como leitura recreativa.

> [!success]- Resposta
> **A.** **27001 = requisitos** do SGSI (o que é obrigatório, **certifica**). **27002 = código de práticas** (como implementar os controles, **não certifica**). E é a pegadinha: **inverte** as duas.

**39. [PSI — Segurança de Acesso]** Ao estruturar as diretrizes de uma PSI robusta corporativa, a política de senhas é um dos pilares tecnológicos e comportamentais mais relevantes. Dentre as recomendações modernas de segurança, qual prática é considerada **inadequada** e contrária à boa governança?

A) Exigir comprimento mínimo elevado (ex: 12 a 16 caracteres) com combinação de complexidade.
B) Tornar obrigatória a Autenticação Multifator (MFA) para acessos remotos e sistemas críticos.
C) Permitir o compartilhamento de senhas de acesso administrativo entre múltiplos colaboradores para agilizar o suporte operacional.
D) Estabelecer bloqueio automático da conta após repetidas tentativas incorretas de login.
E) Utilizar cofres de senha institucionais homologados.

> [!success]- Resposta
> **C** (é a **inadequada**). Senha compartilhada destrói a **rastreabilidade** (não se sabe quem fez o quê), fere **autenticidade** e **não-repúdio** e amplia o acesso contra o **menor privilégio**. A, B, D e E são boas práticas.

**40. [Segurança — Fator Humano]** O fator humano é frequentemente apontado como o elo mais fraco na corrente de segurança da informação. Para mitigar esse risco e transformar colaboradores em um "Firewall Humano", as organizações implementam estrategicamente:

A) Demissões em massa de todos os funcionários administrativos.
B) Treinamentos contínuos de conscientização, simulações de phishing e campanhas educativas periódicas.
C) Isenção total de regras de acesso a sites maliciosos na internet.
D) Ocultação deliberada de qualquer política interna de segurança para evitar preocupações.
E) Delegação total da segurança para que cada usuário decida suas próprias senhas livremente.

> [!success]- Resposta
> **B.** **Firewall humano** = **conscientização contínua**, **simulações de phishing** e campanhas educativas. Na aula 6, "falta de treino" aparece como **vulnerabilidade**; o treinamento é o controle que a corrige.

### Parte 2 — Questões transformadas (41 a 55)

**41. [GSTI & Produto vs Serviço]** No contexto da Gestão de Serviços de TI (GSTI), a evolução da TI de centro de custo operacional para parceira estratégica alterou profundamente a forma como organizações entregam valor. Considerando a diferenciação conceitual entre Produto e Serviço na GSTI, avalie as asserções a seguir e a relação proposta entre elas:

I. Um serviço de TI proporciona valor ao cliente permitindo o alcance de resultados desejados sem que este precise gerenciar custos e riscos específicos.

**PORQUE**

II. Ao contrário dos produtos, os serviços são bens tangíveis, estocáveis e implicam a transferência definitiva de posse e propriedade do bem ao consumidor.

A respeito dessas asserções, assinale a opção correta:

A) As asserções I e II são proposições verdadeiras, e a II é uma justificativa correta da I.
B) As asserções I e II são proposições verdadeiras, mas a II não é uma justificativa correta da I.
C) A asserção I é uma proposição verdadeira, e a II é uma proposição falsa.
D) A asserção I é uma proposição falsa, e a II é uma proposição verdadeira.
E) As asserções I e II são proposições falsas.

> [!success]- Resposta
> **C.**
> - **I — verdadeira**: é a definição de serviço da aula 1 (entregar valor, facilitar resultados, sem que o cliente assuma custos e riscos específicos).
> - **II — falsa**: descreve **produto**. Serviço é **intangível**, **não estocável** e **não transfere posse**.
> - Como II é falsa, a relação de justificativa nem precisa ser analisada.

**42. [Utilidade e Garantia]** Em um evento promocional de grande porte (como a Black Friday), uma plataforma de e-commerce apresentou falha total em seus servidores, ficando indisponível durante todo o período. O sistema possuía excelentes funcionalidades de busca e recomendação, porém o cliente não conseguiu concluir nenhuma compra. Analisando a geração de valor sob o prisma da ITIL v4 (Utilidade e Garantia), assinale a opção correta:

A) O valor do serviço foi mantido plenamente, pois a Utilidade do sistema permaneceu intacta perante as regras de negócio.
B) A ausência do pilar de Garantia (indisponibilidade) destruiu o valor percebido do serviço, inviabilizando os resultados do negócio apesar da Utilidade teórica.
C) A Garantia do serviço foi atendida, uma vez que a falha de hardware é considerada risco exclusivo do cliente consumidor.
D) Utilidade e Garantia são conceitos independentes e o insucesso das vendas não possui relação com os pilares de valor da ITIL.
E) A plataforma demonstrou alta adequação ao propósito (Fit for Purpose), o que compensa a falta de adequação ao uso (Fit for Use).

> [!success]- Resposta
> **B.** Valor exige **os dois** pilares. Havia utilidade (boas funções), mas faltou **garantia** (**disponibilidade**) — e sem garantia o valor percebido é destruído. E é a pegadinha: utilidade **não compensa** falta de garantia.

**43. [ITIL v4 SVS]** O Sistema de Valor de Serviço (SVS) da ITIL v4 descreve como os componentes organizacionais interagem para criar valor. O SVS é estruturado por cinco elementos principais: Princípios Orientadores, Governança, Cadeia de Valor do Serviço, Práticas e Melhoria Contínua. Nesse contexto, qual é o papel desempenhado pelos Princípios Orientadores no SVS?

A) Substituir os processos operacionais e eliminar a necessidade de comitês de governança corporativa.
B) Servir como recomendações universais e duradouras que guiam as decisões e ações da organização em qualquer circunstância.
C) Definir a arquitetura técnica de hardware e os padrões de cabeamento estruturado do data center.
D) Gerenciar exclusivamente a alocação do orçamento anual de TI e a contratação de fornecedores.
E) Determinar a sequência rígida e imutável de etapas em todos os fluxos de trabalho da TI.

> [!success]- Resposta
> **B.** É a definição do slide: **recomendações universais e duradouras** que orientam decisões **em qualquer circunstância**. E contradiz a ITIL 4, que é **flexível**.

**44. [4 Dimensões da Gestão]** Para garantir uma abordagem holística na gestão de serviços, a ITIL v4 estabelece as "Quatro Dimensões da Gestão": (1) Organizações e Pessoas, (2) Informação e Tecnologia, (3) Parceiros e Fornecedores, e (4) Fluxos de Valor e Processos. Sobre o alinhamento entre as dimensões "Organizações e Pessoas" e "Informação e Tecnologia", assinale a alternativa correta:

A) O investimento em tecnologias avançadas garante o sucesso da entrega do serviço, independentemente de treinamento ou cultura organizacional.
B) A dimensão de Informação e Tecnologia deve ser gerenciada isoladamente para evitar contaminação por falhas de processos humanos.
C) Ferramentas tecnológicas avançadas tornam-se ineficazes se as pessoas não possuírem competências adequadas, papéis definidos e alinhamento cultural.
D) A definição de papéis e responsabilidades estruturais pertence exclusivamente à dimensão de Parceiros e Fornecedores.
E) As Quatro Dimensões aplicam-se apenas à fase de desenho, sendo ignoradas na operação contínua do serviço.

> [!success]- Resposta
> **C.** As dimensões precisam ser **equilibradas**: tecnologia sem pessoas preparadas não entrega valor. A e B contradizem a visão holística; papéis (D) são da dimensão **Organizações e Pessoas**.

**45. [Modelos de Service Desk]** Uma multinacional precisa reestruturar sua Central de Serviços para atender unidades em três continentes com diferentes fusos horários. A diretoria busca um modelo que garanta suporte contínuo 24/7 sem inflacionar custos com equipes noturnas locais em cada país. Assinale a opção que indica o modelo de Service Desk adequado e sua respectiva característica:

A) Service Desk Local — aloca equipes físicas em cada prédio, reduzindo custos de comunicação e links de dados.
B) Service Desk Centralizado — mantém uma única equipe física em uma única sede, operando apenas em horário comercial local.
C) Service Desk Virtual (modelo Follow-the-Sun) — utiliza analistas distribuídos geograficamente que repassam chamados conforme a luz do dia avança.
D) Service Desk Outsourced Estático — elimina o uso de sistemas em nuvem e restringe o suporte ao atendimento presencial.
E) Service Desk Descentralizado Fechado — proíbe a integração de processos e exige bancos de dados independentes por país.

> [!success]- Resposta
> **C.** **Virtual / Follow-the-Sun**: equipes em fusos diferentes passam o atendimento adiante, cobrindo **24/7** sem turno noturno. A erra na característica (Local **aumenta** custos); D e E não são modelos da ITIL.

**46. [Incidente vs Requisição]** Na rotina de TI de um hospital, a equipe recebeu dois chamados: Chamado 1: Médico solicita a instalação do leitor de PDF homologado em seu novo computador; Chamado 2: O sistema principal de prontuário eletrônico da UTI caiu repentinamente. De acordo com a ITIL v4 e a matriz de priorização, como esses chamados devem ser classificados e tratados?

A) Chamado 1 é Incidente (alta prioridade); Chamado 2 é Requisição de Serviço (baixa prioridade).
B) Chamado 1 é Requisição de Serviço (atendimento padronizado); Chamado 2 é Incidente Crítico (prioridade máxima por alto impacto e urgência).
C) Ambos são Incidentes de Prioridade 1 (P1) e devem ser atendidos por ordem estrita de chegada.
D) Chamado 2 configura um Problema Não Planejado e não deve ser atendido pela equipe de suporte operacional.
E) Chamado 1 é uma Mudança Emergencial e o Chamado 2 é um Evento de Rotina sem impacto no negócio.

> [!success]- Resposta
> **B.** Instalar software **homologado** = **requisição** padrão. Prontuário da **UTI** fora do ar = **incidente** de impacto alto (vidas em risco) e urgência alta → **P1**. A é a pegadinha: **inverte** os dois.

**47. [Causa Raiz & 5 Porquês]** Após repetidas paradas não planejadas no sistema de faturamento de uma distribuidora, a equipe de TI aplicou a técnica dos "5 Porquês" para investigar a causa raiz. O fluxo identificou que o servidor caiu por superaquecimento; a refrigeração falhou por falta de manutenção; a manutenção não ocorreu porque não havia cronograma formalizado. Com base na gestão de problemas, qual a conclusão correta?

A) A causa raiz é puramente individual e a solução definitiva é a demissão do técnico responsável pelo ar-condicionado.
B) A causa raiz reside na ausência de governança e processos preventivos, exigindo a formalização de rotinas para evitar a reincidência.
C) O problema foi resolvido com o reinício do servidor (solução de contorno), tornando desnecessária qualquer ação sobre a manutenção.
D) A técnica dos 5 Porquês deve ser aplicada apenas para falhas de software, não sendo aplicável a infraestrutura física.
E) O encerramento do chamado de incidente elimina automaticamente o problema na base de dados de erros conhecidos (KEDB).

> [!success]- Resposta
> **B.** É o exemplo da aula 4: a raiz é a **ausência de cronograma formalizado** — falha de **processo**, não de pessoa. A contraria o "foco em processos, sem culpados"; C confunde **contorno** com solução definitiva; E confunde encerrar o incidente com resolver o problema.

**48. [Gestão de Mudanças]** Durante uma atualização emergencial de segurança em um servidor central (Mudança Emergencial), a aplicação apresentou incompatibilidade severa, interrompendo as operações. A equipe acionou o plano de "Rollback" (retorno ao estado anterior seguro). No âmbito da Habilitação de Mudanças (Change Enablement), analise as afirmativas:

I. Mudanças Emergenciais dispensam qualquer tipo de avaliação de risco ou plano de contingência antes de sua execução.
II. O Comitê Consultivo de Mudanças de Emergência (ECAB) deve atuar para autorizar e avaliar com rapidez mudanças críticas de alto impacto.
III. O plano de Rollback (fallback) é requisito essencial na avaliação de mudanças para garantir a restauração do serviço em caso de falha.

É correto o que se afirma em:

A) I, apenas.
B) III, apenas.
C) I e II, apenas.
D) II e III, apenas.
E) I, II e III.

> [!success]- Resposta
> **D.**
> - **I — falsa**: a mudança emergencial tem fluxo **simplificado**, mas **não dispensa** avaliação — ela passa pelo **ECAB**. O que pode ficar para depois é a **documentação detalhada** e parte dos testes.
> - **II — verdadeira**: o **ECAB** autoriza e avalia rapidamente mudanças emergenciais.
> - **III — verdadeira**: o **rollback** é essencial para restaurar o serviço se a mudança falhar — foi o que salvou o caso do enunciado.

**49. [COBIT 2019 Governança vs Gestão]** O COBIT 2019 estabelece uma separação clara entre Governança e Gestão. Enquanto a Governança é responsabilidade do Conselho/Alta Administração sob o modelo EDM, a Gestão é executada por líderes operacionais/táticos. Em relação aos papéis dessas esferas, assinale a opção correta:

A) A Governança executa o planejamento detalhado, codificação de software e suporte ao usuário final.
B) A Gestão é responsável por Avaliar as necessidades dos stakeholders, Dirigir a estratégia e Monitorar a conformidade (EDM).
C) A Governança define o direcionamento estratégico, avalia opções e monitora o desempenho (EDM), enquanto a Gestão planeja, constrói, executa e monitora as atividades operacionais (APO, BAI, DSS, MEA).
D) Governança e Gestão representam o mesmo nível hierárquico e possuem atribuições idênticas no modelo COBIT 2019.
E) A Gestão possui autoridade superior à Governança no que tange à alocação de investimentos financeiros de longo prazo.

> [!success]- Resposta
> **C.** Governança = **EDM** (avaliar, dirigir, monitorar); Gestão = **APO, BAI, DSS, MEA** (planejar, construir, executar, monitorar). B é a pegadinha: atribui o **EDM** à **gestão**.

**50. [COBIT 2019 Triplo de Valor]** O Princípio 1 do COBIT 2019 estabelece que o sistema de governança deve criar valor para os stakeholders ao transformar objetivos corporativos em metas de I&T. Essa geração de valor é alcançada mantendo o equilíbrio do "Triplo de Valor", formado por:

A) Aumento de Vendas, Redução de Impostos e Diminuição de Pessoal.
B) Realização de Benefícios, Otimização de Riscos e Otimização de Recursos.
C) Aquisição de Hardware, Licenciamento de Software e Instalação de Redes.
D) Conformidade Trabalhista, Auditoria Contábil e Redução de Custos de Viagem.
E) Treinamento Técnico, Terceirização e Automação de Processos.

> [!success]- Resposta
> **B.** Mesmo conteúdo da questão 24 (lá era a letra A): **benefícios, riscos e recursos**.

**51. [Tríade CID & Incidentes]** Uma empresa de e-commerce sofreu um incidente em que atacantes invadiram o banco de dados. Os invasores não alteraram e não apagaram nenhum dado, mas copiaram e vazaram a lista completa de cartões de crédito dos clientes na internet. Sob o prisma da Tríade CID e dos conceitos de segurança, assinale a análise correta:

A) Houve quebra de Disponibilidade, pois o banco de dados ficou inacessível aos usuários legítimos.
B) Houve violação do pilar de Confidencialidade, pois informações sigilosas foram expostas a pessoas não autorizadas.
C) A Integridade dos dados foi comprometida, uma vez que os números dos cartões foram alterados na base.
D) O incidente não representa falha de segurança, pois não houve dano físico aos servidores da empresa.
E) O ataque violou exclusivamente o pilar de Não-Repúdio da infraestrutura de rede.

> [!success]- Resposta
> **B.** Dados **copiados e vazados**, sem alteração nem indisponibilidade → só a **confidencialidade** foi violada. O enunciado exclui de propósito a integridade ("não alteraram") e a disponibilidade.

**52. [Análise e Mitigação de Riscos]** Em um estudo de análise de riscos em uma instituição financeira, identificou-se que servidores antigos rodavam sistemas sem os patches de correção de segurança mais recentes (Vulnerabilidade). A equipe alertou sobre o risco de infecção por Ransomware (Ameaça). Considerando a equação conceitual do risco (Risco = Ativo × Ameaça × Vulnerabilidade), qual medida reduz diretamente a Vulnerabilidade?

A) Contratar um seguro financeiro contra ataques cibernéticos.
B) Aplicar os patches de correção e atualizações de segurança nos sistemas operacionais dos servidores.
C) Aumentar o valor contábil do ativo de informação cadastrado na empresa.
D) Ignorar a falha e aguardar a ocorrência do incidente para acionar a equipe de suporte.
E) Aumentar a largura de banda da conexão de internet da instituição.

> [!success]- Resposta
> **B.** A vulnerabilidade **é** a falta de patches; aplicá-los **fecha a brecha**. O seguro (A) **não reduz** a vulnerabilidade — só **transfere** o prejuízo financeiro para a seguradora.
> ⚠️ No PDF, a fórmula saiu com a formatação quebrada ("Ativo imes Ameaça imes Vulnerabilidade"); o "imes" é o símbolo de multiplicação que não foi impresso. Repare que aqui a professora escreve **Ativo × Ameaça × Vulnerabilidade**, enquanto o slide da aula 6 mostra "A × V × I" sem expandir as letras — atualizei o resumo da aula 6 com essa observação.

**53. [LGPD Prática]** Uma farmácia solicita aos clientes o número do CPF no balcão no momento do pagamento, alegando concessão de descontos. O dado é armazenado e compartilhado com empresas de análise de crédito sem a informação clara ou consentimento do cliente. À luz da LGPD (Lei nº 13.709/2018), avalie a conduta da empresa:

A) A conduta é plenamente legal, pois farmácias possuem isenção total quanto às regras da LGPD.
B) A conduta viola os princípios da LGPD (como finalidade, transparência e adequação) e carece de base legal válida para o compartilhamento não informado.
C) O CPF é um dado anonimizado por natureza, portanto seu tratamento é livre e não regulado pela LGPD.
D) O compartilhamento de dados é permitido desde que o valor final das compras seja reduzido em pelo menos 10%.
E) A farmácia atua como Encarregado (DPO) do cliente, tendo autoridade irrestrita sobre seus dados pessoais.

> [!success]- Resposta
> **B.** O CPF foi coletado para **desconto** e usado para **análise de crédito** (fere a **finalidade** e a **adequação**), **sem informar** o cliente (fere a **transparência**) e **sem base legal** para o compartilhamento. CPF identifica a pessoa, então **é dado pessoal**, não anonimizado (C).

**54. [Privacy by Design]** A arquitetura de sistemas modernos deve incorporar os preceitos do "Privacy by Design" (Privacidade desde a Concepção). Assinale a alternativa que exemplifica a aplicação correta desse conceito no desenvolvimento de um aplicativo mobile de entregas:

A) Coletar todos os dados possíveis do smartphone do usuário (fotos, contatos, histórico) para posterior uso comercial.
B) Configurar as opções de privacidade por padrão no nível mais restritivo, solicitando apenas os dados estritamente necessários para a entrega (Privacy by Default).
C) Implementar os mecanismos de segurança de dados somente após o surgimento de multas pela autoridade reguladora (ANPD).
D) Ocultar os termos de uso e a política de privacidade para não poluir a interface visual do aplicativo.
E) Armazenar senhas de usuários em texto simples sem criptografia no banco de dados do aplicativo.

> [!success]- Resposta
> **B.** **Privacy by Default** (um dos princípios do Privacy by Design): configuração **mais protetiva por padrão** e coleta **apenas do necessário** (princípio da necessidade da LGPD). C é **reativo** — o oposto do conceito.

**55. [ISO 27001 & ISO 27002]** Uma grande corporação está estruturando sua governança de segurança da informação. A diretoria busca certificar a empresa internacionalmente e, ao mesmo tempo, fornecer um guia prático detalhado para a implementação dos controles técnicos pelas equipes de TI. Para atender a esses dois objetivos, a empresa deve adotar, respectivamente:

A) A ISO/IEC 27002 para obter a certificação auditável e a ISO/IEC 27001 para o guia de práticas.
B) A ISO/IEC 27001 para estabelecer e certificar o SGSI e a ISO/IEC 27002 como código de prática para implementação dos controles.
C) O framework ITIL v4 exclusivamente, uma vez que as normas ISO foram descontinuadas.
D) A LGPD para certificação internacional e a NBR ISO 9001 para gestão de ativos digitais.
E) O COBIT 2019 para controles operacionais de hardware e a ISO 27002 para auditoria contábil.

> [!success]- Resposta
> **B.** **Certificar → 27001**; **guia prático dos controles → 27002**. A é a pegadinha: **inverte** as duas (mesmo erro da alternativa E da questão 38).

> [!abstract]- Gabarito rápido
> | Q | R | Q | R | Q | R | Q | R | Q | R |
> | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
> | 1 | C | 12 | C | 23 | C | 34 | D | 45 | C |
> | 2 | C | 13 | C | 24 | A | 35 | B | 46 | B |
> | 3 | B | 14 | B | 25 | D | 36 | B | 47 | B |
> | 4 | B | 15 | C | 26 | C | 37 | B | 48 | D |
> | 5 | C | 16 | B | 27 | C | 38 | A | 49 | C |
> | 6 | C | 17 | B | 28 | B | 39 | C | 50 | B |
> | 7 | B | 18 | C | 29 | B | 40 | B | 51 | B |
> | 8 | C | 19 | B | 30 | B | 41 | C | 52 | B |
> | 9 | C | 20 | C | 31 | B | 42 | B | 53 | B |
> | 10 | E | 21 | B | 32 | B | 43 | B | 54 | B |
> | 11 | C | 22 | B | 33 | B | 44 | C | 55 | B |