# Projeto ERP — Multiplikar Automóveis

**Projeto Integrador — Modelagem de Dados - Primeira Entrega**  
**Primeira entrega: modelo conceitual**

## Sumário

1. [Identificação da equipe](#secao-1)
2. [Caracterização da empresa](#secao-2)
3. [Justificativa da escolha](#secao-3)
4. [Problemas identificados](#secao-4)
5. [Processos de negócio](#secao-5)
6. [Requisitos funcionais](#secao-6)
7. [Requisitos não funcionais](#secao-7)
8. [Regras de negócio](#secao-8)
9. [Restrições e políticas organizacionais](#secao-9)
10. [Fluxogramas](#secao-10)
11. [Entidades](#secao-11)
12. [Atributos](#secao-12)
13. [Relacionamentos](#secao-13)
14. [Cardinalidades](#secao-14)
15. [Dicionário de dados conceitual](#secao-15)
16. [DER](#secao-16)
17. [Justificativas técnicas](#secao-17)
18. [Conclusão](#secao-18)

<a id="secao-1"></a>

## 1. Identificação da equipe

### 1.1. Integrantes

1. Ana Beatriz Morais Lessa
2. Andrey Azevedo Veloso
3. Aquiles Santana da Silva
4. Brenno Lima do Vale
5. Caique Martins Santos
6. David Alejandro Delgado
7. Erin Jesus Olivera
8. Jocerlan Diniz dos Santos
9. Nicolas Dias da Silva

| Campo | Informação |
|---|---|
| Projeto | Projeto Integrador — Modelagem de Dados |
| Empresa analisada | Multiplikar Automóveis |
| Turma | Engenharia de Software - Manhã/Matutino |
| Disciplina |MODELAGEM DE BANCO DE DADOS |
| Professor(a) | Clóvis Ferraro |
| Instituição | UNICID |
| Data de submissão |2° Semestre - Eng. Software |
| Repositório GitHub | Inserir endereço após publicação |

Observação: As informações acadêmicas e a estrutura do repositório foram revisadas pelo grupo para a submissão desta primeira entrega.

### 1.2. Contribuições da equipe

| Integrante | Contribuição realizada | Evidência |
|---|---|---|
| Ana Beatriz Morais Lessa | Organização das regras de negócio e políticas organizacionais. | Seções 8 e 9 |
| Andrey Azevedo Veloso | Caracterização da empresa, justificativa, levantamento de problemas, especificação de requisitos funcionais e não funcionais, identificação de entidades, atributos, relacionamentos e conclusão do projeto. | Seções 1, 2, 3, 4, 6, 7, 11, 12, 13 e 18 |
| Aquiles Santana da Silva | Descrição dos processos P01 a P04 e dos fluxogramas correspondentes. | Seções 5 e 10 |
| Brenno Lima do Vale | Elaboração do DER em notação de Chen e organização e registro do Diário de Bordo. | Seção 16, Seção 1.3 e pasta `docs/der` |
| Caique Martins Santos | Descrição das entidades E01 a E05 no dicionário conceitual. | Seção 15 |
| David Alejandro Delgado | Descrição das entidades E06 a E10 no dicionário conceitual. | Seção 15 |
| Erin Jesus Olivera | Justificativas técnicas e consolidação da documentação. | Seção 17 |
| Jocerlan Diniz dos Santos | Análise de cardinalidades pelo Método Vá e Volte. | Seção 14 |
| Nicolas Dias da Silva | Descrição dos processos P05 a P08 e seus fluxogramas. | Seções 5 e 10 |

As responsabilidades foram divididas entre os integrantes para cobrir todas as etapas solicitadas no manual, e realizamos reuniões conjuntas para alinhar o DER e validar a coerência geral do modelo.

### 1.3. Diário de bordo

Parte do Brenno

<a id="secao-2"></a>

## 2. Caracterização da empresa

### 2.1. Identificação

| Aspecto | Informação disponível no levantamento |
|---|---|
| Nome | Multiplikar Automóveis. |
| Segmento | Comércio de veículos. |
| Localização | Bairro Vila São Geraldo; cidade e endereço não informados. |
| Atuação | Aproximadamente dois anos na data do briefing. |
| Equipe | Cerca de seis funcionários. |
| Produtos | Veículos novos, seminovos e usados. |
| Controle atual | Sistema RevendaMais (briefing, p. 7); este projeto propõe a modelagem de um banco relacional integrado próprio. |

A Multiplikar Automóveis é uma loja de veículos (novos, seminovos e usados) localizada no bairro Vila São Geraldo. Com cerca de dois anos de mercado e uma equipe enxuta de seis colaboradores, a empresa atua na compra, venda e intermediação de veículos consignados.

### 2.2. Atividades e público

A loja atende clientes interessados em comprar, vender ou trocar veículos. As operações incluem aquisição direta e recebimento de automóveis em consignação. O levantamento também prevê o atendimento a pessoas físicas e jurídicas.

Os processos descritos envolvem colaboradores, especialistas em vistoria técnica, mecânicos parceiros para garantia e instituições financeiras. As atividades incluem atendimento, avaliação, negociação, formalização de contratos, conferência documental, preparação para entrega e assistência de garantia.

### 2.3. Setores e modo de operação

A partir dos processos levantados, organizamos a operação em três frentes práticas:
1. **Comercial / Vendas:** atendimento inicial aos clientes, apresentação dos veículos do estoque, negociação de propostas, fechamento de vendas e prospecção de veículos para troca ou consignação.
2. **Avaliação Técnica e Pátio:** inspeção física e mecânica dos automóveis ofertados, conferência de laudos cautelares, testes de scanner eletrônico e preparação dos veículos para entrega.
3. **Administrativo / Financeiro e Pós-Venda:** conferência de documentos, formalização de contratos, acompanhamento dos repasses de financiamento, registro de despesas e atendimento de ocorrências de garantia.

O fluxo começa com o atendimento e a avaliação do veículo oferecido. Quando há aprovação e interesse comercial, o veículo é registrado como compra própria, consignação ou entrada em troca. Na venda, relacionamos o veículo ao comprador e às condições acordadas. A conclusão e a entrega consideram as condições financeiras, o laudo e a documentação; a entrega marca o início da garantia prevista no modelo.

### 2.4. Fontes e delimitação do estudo

Para realizar este trabalho, nosso grupo analisou o [Briefing Inicial Completo](docs/fontes/briefing-completo.pdf) da empresa e seguiu as diretrizes do [Manual da Primeira Entrega](docs/fontes/manual-primeira-entrega.pdf). O levantamento aponta que a empresa utiliza a ferramenta comercial RevendaMais no balcão (página 7, item 12 do briefing). Entretanto, o sistema atual não centraliza adequadamente as avaliações mecânicas, os laudos cautelares, o recebimento de mais de um carro como entrada em negociações e as ordens de garantia pós-venda. O objetivo do nosso projeto é justamente estruturar um banco de dados relacional integrado para conectar todas essas pontas.

O escopo desta primeira entrega cobre: cadastro de pessoas e colaboradores, atendimento a interessados, avaliação técnica e laudos de vistoria, modalidades de entrada (compra direta, consignação e troca), fechamento de vendas com controle documental e formas de pagamento, ocorrências de garantia e rateio de despesas por veículo. Outros módulos, como folha de pagamento e comissões externas, não fazem parte do escopo inicial e serão tratados em etapas posteriores do curso.

Todas as decisões tomadas pelo grupo estão justificadas na Seção 17. Como solicitado nesta fase, focamos na construção do modelo conceitual (diagrama DER e dicionário de dados); as tabelas físicas, tipos SQL e normalização serão feitos nas próximas entregas.

<a id="secao-3"></a>

## 3. Justificativa da escolha

Escolhemos a Multiplikar Automóveis porque o comércio automotivo de seminovos oferece um cenário muito prático e interessante para a modelagem de banco de dados. Diferente de um comércio tradicional com vendas simples de produtos de prateleira, uma revenda lida com transações complexas: veículos são comprados de particulares, deixados por clientes em consignação ou aceitos como parte do pagamento (troca).

Além disso, a existência de vistorias técnicas com laudos cautelares, aprovação de financiamento bancário e atendimento de garantia na própria loja faz com que o fluxo de informações seja intenso. Atualmente, os controles descentralizados geram retrabalho e risco de informações desencontradas entre o pátio, a oficina e a parte financeira. A modelagem de um banco relacional integrado é fundamental para organizar essas rotinas e dar confiabilidade à gestão da loja.

<a id="secao-4"></a>

## 4. Problemas identificados

O uso de planilhas sem integração pode levar a retrabalho, divergências entre registros e dificuldade para acompanhar veículos e atendimentos ao longo das etapas. Com base no briefing e nos processos descritos, organizamos os problemas e as necessidades correspondentes:

| ID | Problema Operacional Identificado | Consequência no Negócio | Necessidade do Sistema | RF |
|---|---|---|---|---|
| PROB01 | Registros de uma pessoa podem ficar separados quando ela compra, vende ou consigna. | Cadastros repetidos, histórico fragmentado e retrabalho de digitação. | Unificar o cadastro com múltiplos papéis associados à mesma pessoa. | RF01–RF03 |
| PROB02 | Falta de vínculo entre laudo técnico, avaliação e aceitação do veículo. | Dificuldade para consultar o histórico da avaliação e do estado informado do carro. | Vincular a avaliação técnica e o laudo cautelar à entrada do veículo. | RF04–RF06 |
| PROB03 | Coexistência de modalidades distintas de entrada (compra própria, consignação e troca). | Confusão sobre titularidade do bem, prazos e regras específicas de repasse financeiro. | Distinguir as modalidades de entrada e seus respectivos contratos. | RF07–RF08 |
| PROB04 | Acompanhamento manual da disponibilidade de veículos no pátio. | Possibilidade de divergência de status ou de negociações simultâneas para o mesmo automóvel. | Controle centralizado de disponibilidade e bloqueio de vendas conflitantes. | RF09–RF10 |
| PROB05 | Recebimento de múltiplos veículos como parte do pagamento na mesma venda. | Inconsistência na composição do saldo da venda e perda do vínculo individual de cada entrada. | Registrar múltiplos veículos de troca vinculados à mesma transação. | RF11 |
| PROB06 | Descasamento entre aprovação de crédito e efetivo recebimento bancário. | Baixa prematura de valores não compensados e divergências financeiras. | Distinguir aprovação bancária do efetivo repasse à loja. | RF12–RF13 |
| PROB07 | Dificuldade para acompanhar pendências documentais ou de laudo antes da entrega. | Risco de desencontro entre a situação documental e a liberação do veículo. | Validar requisitos documentais e técnicos antes da liberação da entrega. | RF14 |
| PROB08 | Descontrole de prazos de garantia e procedimentos de devolução em vendas desfeitas. | Insegurança no pós-venda, perda do histórico de manutenções e desorganização na devolução de bens. | Controlar ocorrências de garantia e registrar as restituições em cancelamentos. | RF15–RF16 |
| PROB09 | Dificuldade na apuração de despesas por veículo e consolidação de relatórios gerenciais. | Falta de clareza sobre o lucro real de cada automóvel comercializado. | Vincular custos diretamente ao veículo e gerar relatórios gerenciais. | RF17–RF18 |
| PROB10 | Falta de integração entre condições contratuais acordadas e registros operacionais. | Divergência entre valores negociados, taxas discriminadas e contratos formalizados. | Associar os dados contratuais às operações de compra, venda e consignação. | RF08, RF10–RF14 |
| PROB11 | Dependência de planilhas sem integração entre registros. | Retrabalho de consolidação manual, risco de divergências e lentidão nas consultas. | Centralizar as informações em banco de dados relacional integrado. | RF01–RF18 |

<a id="secao-5"></a>

## 5. Processos de negócio

### Processos P01 a P04

Parte do Aquiles

### Processos P05 a P08

Parte do Nicolas

<a id="secao-6"></a>

## 6. Requisitos funcionais

São capacidades propostas a partir do levantamento para organizar as informações do negócio em um futuro sistema.

| ID | Requisito | Rastreabilidade |
|---|---|---|
| RF01 | O sistema deverá cadastrar pessoas por CPF/CNPJ e contato, reutilizando o cadastro nos diferentes papéis. | P01; PROB01; RN01–RN02 |
| RF02 | O sistema deverá registrar o vínculo funcional, com cargo, admissão e situação. | P01; PROB01; RN03 |
| RF03 | O sistema deverá registrar atendimentos com interessado, funcionário, data, interesse e situação. | P01; PROB01; RN03 |
| RF04 | O sistema deverá cadastrar veículos distinguindo avaliação preliminar de entrada aceita no estoque. | P02; PROB02; RN04–RN05 |
| RF05 | O sistema deverá registrar avaliação, responsável, condições, decisão técnica e interesse comercial. | P02–P04; PROB02; RN06–RN07 |
| RF06 | O sistema deverá registrar laudos por veículo e sua consulta nas avaliações. | P02–P06; PROB02; RN08 |
| RF07 | O sistema deverá registrar cada entrada aceita como compra própria, consignação ou troca. | P02–P04; PROB03; RN09 |
| RF08 | O sistema deverá registrar contraparte, valores, contrato e condições específicas de cada entrada. | P02–P03; PROB03/10; RN10–RN12 |
| RF09 | O sistema deverá apresentar a disponibilidade dos veículos e impedir vendas simultâneas incompatíveis. | P04; PROB04; RN13 |
| RF10 | O sistema deverá registrar venda com comprador, funcionário, veículo principal, valores e contrato. | P04; PROB04/10; RN14–RN15 |
| RF11 | O sistema deverá vincular todos os veículos aceitos como entrada à mesma venda, com avaliações e valores individuais, sem terceiros. | P04; PROB05; RN16–RN18 |
| RF12 | O sistema deverá registrar em VENDA o conjunto de formas de pagamento e, separadamente, total recebido, data mais recente e situação financeira. | P05; PROB06; RN19–RN20 |
| RF13 | O sistema deverá registrar em VENDA o único financiamento e distinguir aprovação do recebimento, sem controlar parcelas do cliente. | P05; PROB06; RN21 |
| RF14 | O sistema deverá registrar documentos conferidos, reconhecimento aplicável, laudo, scanner, conclusão e entrega, verificando as condições de cada marco. | P06; PROB07/10; RN22–RN24 |
| RF15 | O sistema deverá registrar garantia e ocorrências com diagnóstico, mecânico principal, atendimento externo informado e solução. | P07; PROB08; RN25–RN27 |
| RF16 | O sistema deverá registrar cancelamento, retorno do veículo e devoluções, com comunicação ao consignante e observações da tratativa bancária quando aplicáveis. | P07; PROB08; RN28–RN31 |
| RF17 | O sistema deverá registrar despesas com data, categoria, descrição, valor e veículo. | P08; PROB09; RN32 |
| RF18 | O sistema deverá apresentar consultas de leads, disponibilidade, histórico comercial, despesas e posição financeira resumida das vendas. | P08; PROB09; RN33 |

Os requisitos RF09 e RF14 asseguram a integridade operacional das vendas e entregas, enquanto o RF18 concentra as consultas operacionais essenciais ao escopo delimitado nesta primeira etapa.

<a id="secao-7"></a>

## 7. Requisitos não funcionais

Os requisitos não funcionais definem os parâmetros essenciais de segurança, integridade, desempenho e usabilidade que orientarão o projeto lógico e a implementação do sistema:

| ID | Condição proposta | Verificação |
|---|---|---|
| RNF01 | O acesso a dados pessoais e financeiros deverá respeitar perfis autorizados. | Testar operações permitidas e negadas após definição dos perfis. |
| RNF02 | Documentos e informações pessoais deverão ser protegidos contra consulta/exportação não autorizadas. | Verificar restrições sobre CPF/CNPJ, contato, endereço e referências documentais. |
| RNF03 | Alterações de valores, situação financeira e cancelamento deverão ser rastreáveis. | Reconstruir autor, momento e conteúdo alterado; retenção a definir. |
| RNF04 | Operações concorrentes não deverão permitir vendas incompatíveis do mesmo veículo. | Testar tentativas simultâneas de conclusão. |
| RNF05 | Vínculos entre veículo, avaliação, entrada e venda deverão permanecer íntegros. | Rejeitar associações contraditórias e preservar histórico. |
| RNF06 | Consultas deverão ter desempenho adequado ao atendimento. | Definir volume, concorrência e tempo aceitável antes de implementar. |
| RNF07 | Dados deverão ser recuperáveis após falha. | Definir perda máxima e prazo de recuperação; testar restauração. |
| RNF08 | A interface deverá distinguir os estados comercial, financeiro, documental e de entrega. | Validar tarefas e navegação por teclado, com rótulos claros. |

Tabelas e controles estritamente técnicos de infraestrutura (como logs detalhados de auditoria e segurança) serão detalhados nas etapas de modelo lógico e físico.

<a id="secao-8"></a>

8. Regras de negócio
 
8.1. Pessoas, veículos e entrada

| ID | Regra | Origem |
|---|---|---|
| RN01 | Clientes, proprietários e fornecedores são identificados por CPF ou CNPJ. | Briefing da loja (p. 7) — Atendimento de pessoas físicas e jurídicas |
| RN02 | Uma pessoa pode exercer vários papéis com um único cadastro. | Decisão de modelagem da equipe — Cadastro unificado para evitar duplicidades |
| RN03 | Cada atendimento tem um interessado e um funcionário; ambos podem participar de vários atendimentos. | Briefing da loja (p. 4–6) — Rotina comercial de atendimento e histórico de contatos |
| RN04 | Cada veículo tem identidade própria; placa e chassi podem não estar disponíveis no cadastro inicial. | Briefing da loja (p. 3) — Prospecção preliminar antes da checagem física |
| RN05 | Cadastro preliminar não significa aceitação no estoque. | Regra prática da equipe — Separação entre consulta inicial e estoque físico |
| RN06 | Entrada aceita exige avaliação aprovada do mesmo veículo. | Briefing da loja — Política de vistoria técnica e mecânica obrigatória |
| RN07 | A aceitação também exige interesse comercial da loja. | Esclarecimento da loja — Validação de viabilidade e giro comercial de revenda |
| RN08 | O laudo cautelar consultado em uma avaliação deve pertencer obrigatoriamente ao mesmo veículo avaliado (AVALIACAO.veiculo == LAUDO.veiculo). Uma avaliação consulta no máximo um laudo (0,1) e o laudo pode subsidiar reavaliações do mesmo veículo (0,N). | Briefing da loja (p. 4) e regra de integridade — Vínculo estrito com o mesmo veículo e suporte a reavaliações |
| RN09 | A modalidade da entrada é compra própria, consignação ou troca. | Briefing da loja — As três vias operacionais de abastecimento de estoque |
| RN10 | Cada entrada identifica um veículo e uma contraparte. | Regra contábil e jurídica — Identificação formal do bem e de quem o entregou à loja |
| RN11 | Na consignação, o veículo fica vinculado ao proprietário até a conclusão da venda. | Briefing da loja (p. 3) — Titularidade legal do bem permanece com o consignante |
| RN12 | Consignação é formalizada com reconhecimento de firma e normalmente sem prazo; exceções registram o término. | Briefing da loja (p. 7) — Segurança jurídica formal e vigência por prazo indeterminado |

8.2. Venda e troca

| ID | Regra | Origem |
|---|---|---|
| RN13 | Bloqueio de vendas simultâneas e unicidade de comercialização: cada entrada aceita só pode ser comercializada em no máximo uma venda ativa/concluída (cardinalidade operacional 0,1). O sistema impede vendas simultâneas do mesmo veículo. Caso a venda seja desfeita e o veículo retorne ao pátio, a nova comercialização encerra a entrada anterior ou, se mantida a mesma entrada por acúmulo histórico temporal (0,N), no máximo uma venda pode estar ativa. | Briefing da loja (p. 3, 6) e regra de integridade — Bloqueio de vendas concorrentes para o mesmo veículo no pátio |
| RN14 | Cada venda tem um comprador, um responsável e um veículo principal. | Briefing da loja (p. 4–5) e decisão da equipe — Identificação obrigatória do comprador, vendedor e veículo vendido |
| RN15 | Descontos, acréscimos e taxas são discriminados na operação e no contrato. | Briefing da loja (p. 7) — Discriminação transparente de valores, descontos, acréscimos e taxas no contrato |
| RN16 | Uma venda recebe zero, um ou vários veículos como entrada. | Esclarecimento prático da loja (p. 5–7) — Permissão comercial para receber múltiplos veículos como parte do pagamento |
| RN17 | Cada veículo oferecido passa por nova avaliação e depende de aprovação e interesse da loja. | Briefing da loja e esclarecimento operacional — Avaliação técnica individual e aprovação comercial para cada carro de troca |
| RN18 | A troca pertence ao mesmo contrato; cada veículo tem valor discriminado e pertence ao comprador, sem terceiros. | Briefing da loja e esclarecimento operacional — Todos os carros de troca constam no mesmo contrato e pertencem ao comprador |

8.3. Pagamento, documentação e entrega

| ID | Regra | Origem |
|---|---|---|
| RN19 | Pagamento não é entidade; formas_pagamento é somente multivalorado, com valores simples e sem componentes. | Diretriz do projeto e delimitação de escopo — Formas de pagamento registradas como atributo multivalorado simples, sem tabela financeira complexa |
| RN20 | Formas podem ser combinadas; total recebido, data mais recente e situação financeira são atributos separados de VENDA. | Briefing da loja e decisão de modelagem — Registro direto em VENDA do total recebido, data mais recente e situação financeira |
| RN21 | Há no máximo um financiamento por venda; aprovação difere de recebimento pela loja; não se acompanham parcelas pagas pelo cliente. | Briefing da loja e esclarecimento operacional — No máximo um financiamento por venda, diferenciando aprovação de crédito e repasse à loja |
| RN22 | Conclusão exige cumprimento do pagamento acordado, financiamento recebido quando houver, documentos necessários e reconhecimento aplicável, além de laudo cautelar realizado. | Esclarecimento da rotina da loja — Conclusão da venda exige quitação, crédito do financiamento, documentos conferidos e laudo cautelar |
| RN23 | Scanner antecede a entrega. | Briefing da loja (p. 7) — Rastreamento eletrônico por scanner veicular obrigatoriamente realizado antes da entrega |
| RN24 | Recebimento, conclusão comercial e entrega são registrados separadamente. | Decisão de modelagem apoiada na rotina da loja — Registro em momentos distintos para pagamento, conclusão documental e entrega física |

Documentos exigidos para formalização da venda: **CNH, laudo cautelar, CRLV, ATPV e comprovante de residência com nome e endereço** (por exemplo, conta de consumo). O reconhecimento de firma aplica-se aos instrumentos cabíveis de transferência e contrato.

O valor aceito dos veículos de troca compõe o cumprimento econômico da venda, mas não é somado ao total de dinheiro recebido.

 8.4. Garantia e desfazimento

| ID | Regra | Origem |
|---|---|---|
| RN25 | A garantia concedida tem prazo informado de dois meses e começa na entrega ao cliente. | Briefing da loja e esclarecimento operacional — Prazo de garantia de 2 meses iniciado exatamente na data de entrega ao cliente |
| RN26 | A política declarada exige atendimento pela loja; a empresa informa considerar a garantia sem efeito se o cliente encaminhar o veículo a mecânico externo. | Esclarecimento da gerência da loja — Manutenção de garantia condicionada ao reparo exclusivo na oficina parceira da loja |
| RN27 | A ocorrência registra diagnóstico e análise de responsabilidade ou mau uso. | Briefing da loja (p. 4) e proposta técnica — Registro de diagnóstico mecânico e apuração de mau uso na ocorrência de garantia |
| RN28 | Cancelamento preserva a negociação e registra motivo, devoluções e resultado. | Decisão da equipe para auditoria — Registro histórico do cancelamento preservando o contrato original da venda e os motivos do distrato |
| RN29 | No desfazimento com troca, a loja recebe o veículo vendido e devolve os recebidos. | Esclarecimento operacional da loja — Devolução recíproca dos bens: o comprador devolve o carro comprado e a loja devolve os veículos recebidos na troca |
| RN30 | Na consignação, a loja devolve sua parte e avisa o proprietário para devolver o restante ao cliente. | Esclarecimento operacional da loja — No cancelamento de consignado, a loja restitui sua comissão e notifica o proprietário para estorno do saldo |
| RN31 | No financiamento, a loja trata com o banco e registra a orientação/solução; não se define procedimento bancário adicional. | Esclarecimento da loja e delimitação de escopo — Cancelamento de financiamento tratado como orientação administrativa registrada, sem módulo bancário complexo |

A regra RN26 documenta a política da empresa de que qualquer reparo de garantia deve ser avaliado e feito na própria oficina da loja.

Troca, consignação e financiamento podem coexistir em uma mesma negociação. O registro de cancelamento documenta o histórico do desfazimento e as etapas de restituição executadas.

8.5. Despesas e integridade

| ID | Regra | Origem |
|---|---|---|
| RN32 | Cada despesa do escopo pertence a um veículo. | Decisão de modelagem da equipe (p. 7, item 13) — Associação direta de despesas ao veículo para apuração do custo real por unidade |
| RN33 | Relatórios ficam limitados aos dados representados. | Delimitação de escopo da equipe — Relatórios gerenciais consolidados a partir dos dados conceituais de veículos, entradas, vendas e despesas |

Restrições complementares:

- ENTRADA por troca tem exatamente uma VENDA de origem; compra própria e consignação não têm esse vínculo.
- O veículo principal não pode ser um dos veículos recebidos na mesma venda.
- Avaliação, entrada e laudo vinculados referem-se ao veículo correto.
- A contraparte de cada entrada por troca é o comprador da venda de origem.
- Valor aceito da troca fica na ENTRADA, sem cópia independente em VENDA.
- No máximo uma entrada operacional vigente por veículo nesta proposta; entradas históricas não autorizam venda simultânea duplicada.
- Retorno físico não significa automaticamente disponibilidade: a situação deve refletir a regularização do desfazimento.
- Aprovação de crédito não altera automaticamente o total recebido.

<a id="secao-9"></a>

9. Restrições e políticas organizacionais

| ID | Restrição/política | Situação e Fundamentação |
|---|---|---|
| RO01 | Operação comercial apoiada no sistema RevendaMais com controles complementares; modelagem acadêmica de um banco integrado próprio. | Fato do Briefing (p. 7, item 12) e premissa acadêmica do projeto. |
| RO02 | Coleta de nome, CPF/CNPJ, telefone, e-mail, endereço, cidade e estado nos contratos. | Fato confirmado no Briefing da loja (p. 7). |
| RO03 | Consignação com reconhecimento de firma e prazo normalmente indeterminado. | Fato confirmado no Briefing da loja (p. 7). |
| RO04 | Documentos: CNH, laudo, CRLV, ATPV e comprovante de residência com nome/endereço. | Esclarecimento operacional obtido no levantamento com a loja. |
| RO05 | Conclusão condicionada a pagamento, documentação reconhecida quando aplicável e laudo. | Esclarecimento operacional obtido no levantamento com a loja. |
| RO06 | Scanner antes da entrega; repasse registrado no contrato. | Fato confirmado no Briefing da loja (p. 7). |
| RO07 | Garantia a partir da entrega, com condições declaradas pela empresa. | Fato do Briefing confirmado por esclarecimento operacional da loja. |
| RO08 | Um financiamento por venda e ausência de controle de parcelas. | Fato do Briefing e esclarecimento operacional da loja. |
| RO09 | Veículos de entrada pertencem ao comprador, sem terceiros. | Esclarecimento operacional obtido no levantamento com a loja. |
| RO10 | Aprovação de aquisição, descontos, entrega e cancelamento depende dos responsáveis definidos pela empresa. | Política operacional da loja a detalhar nas próximas etapas. |
| RO11 | Perfis de acesso e permissões de alteração são propostas a validar. | Hipótese de trabalho da equipe a ser validada na implementação. |
| RO12 | Pagamento como informação de VENDA, com atributo de formas somente multivalorado. | Delimitação de escopo e diretriz do projeto. |
| RO13 | Reserva, indicação e comissão excluídas. | Delimitação de escopo da equipe para esta primeira etapa. |

Instituições citadas: Itaú, BV, Bradesco Financiamentos, Daycoval, Santander Financiamentos, Banco PAN, C6 Bank, Banco Safra e Banco Volkswagen. A lista não foi declarada exclusiva ou permanente. *(Briefing da loja, p. 7)*

<a id="secao-10"></a>

## 10. Fluxogramas

### Fluxogramas P01 a P04

Parte do Aquiles

### Fluxogramas P05 a P08

Parte do Nicolas

<a id="secao-11"></a>

## 11. Entidades

### 11.1. Entidades selecionadas

| ID | Entidade | Propósito |
|---|---|---|
| E01 | PESSOA | Identifica participantes em diferentes papéis, evitando duplicação cadastral. |
| E02 | FUNCIONARIO | Registra dados próprios do vínculo de trabalho; nome e contato permanecem em PESSOA. |
| E03 | VEICULO | Identifica o automóvel ao longo de avaliações, entradas, vendas e despesas. |
| E04 | ATENDIMENTO | Preserva contatos e interesses, inclusive quando não resultam em venda. |
| E05 | AVALIACAO | Registra análise técnica e interesse comercial para fundamentar a aceitação. |
| E06 | LAUDO | Preserva o documento cautelar, sua emissão e seu resultado. |
| E07 | ENTRADA | Registra cada disponibilização aceita: compra própria, consignação ou troca. |
| E08 | VENDA | Representa negociação, contrato, valores, condições de conclusão, entrega e desfazimento. |
| E09 | OCORRENCIA_GARANTIA | Registra cada reclamação, diagnóstico, serviço e solução vinculados à venda. |
| E10 | DESPESA | Registra custos individualizados associados a cada veículo. |


Todas as entidades possuem identificador conceitual. Os atributos são apresentados na seção 12 e descritos no dicionário da seção 15.

### 11.2. Candidatas avaliadas

| Conceito | Decisão e fundamento |
|---|---|
| Cliente, proprietário, fornecedor | Papéis de PESSOA; evita duplicar identificação e contato. |
| Especialista e mecânico | Papéis de PESSOA nos relacionamentos técnicos; FUNCIONARIO se houver vínculo de trabalho. |
| Estoque | Não é entidade: disponibilidade deriva das entradas e vendas. |
| Compra própria e consignação | Modalidades de ENTRADA, com condições próprias. |
| Troca | ENTRADAS relacionadas à mesma VENDA; não cria segunda negociação. |
| Item de venda | Desnecessário para o único veículo principal adotado. |
| Contrato | Atributo composto da operação; não há ciclo independente de versões/aditivos descrito. |
| Financiamento | Atributos simples de VENDA; um por venda confirmado. |
| Instituição financeira | Nome do banco na venda; sem gestão de instituições neste escopo. |
| Garantia concedida | Atributo de VENDA; atendimentos repetíveis em OCORRENCIA_GARANTIA. |
| Preparação | Informação de VENDA, laudo relacionado e scanner registrado. |
| Lead | PESSOA e ATENDIMENTO; não exige novo cadastro quando compra. |
| Pagamento | Não é entidade; formas somente multivaloradas e totais em VENDA. |
| Parcela | Não incluída: não há acompanhamento individual de quitação. |
| Reserva, indicação, comissão | Excluídas desta primeira entrega. |

### 11.3. Estado atual e histórico

Cadastro, avaliações, entradas, vendas e ocorrências preservam o histórico do veículo. A situação atual é derivada das operações vigentes. Não foi criada uma entidade genérica para cada mudança de situação. Auditoria de alterações é uma qualidade exigida por RNF03, a detalhar na implementação.

<a id="secao-12"></a>

## 12. Atributos

### 12.1. Critérios de identificação

Os atributos foram selecionados a partir das informações registradas nos processos P01–P08. Cada um deve descrever a entidade à qual pertence. Os vínculos com pessoas, veículos e operações são representados por relacionamentos, sem antecipar chaves estrangeiras.

### 12.2. Classificação conceitual

| Classificação | Significado | Exemplo no modelo |
|---|---|---|
| Identificador | Distingue uma ocorrência. | identificador de VENDA. |
| Descritivo | Caracteriza um objeto ou participante. | marca de VEICULO. |
| Temporal | Registra uma data ou marco. | data_entrega de VENDA. |
| Estado | Indica uma situação operacional. | situacao de ATENDIMENTO. |
| Medida/valor | Registra uma quantidade ou valor monetário. | quilometragem de AVALIACAO; valor de DESPESA. |
| Composto | Reúne componentes conceitualmente identificáveis. | endereco de PESSOA. |
| Multivalorado | Admite vários valores simples para uma ocorrência. | formas_pagamento de VENDA. |
| Derivado | É obtido a partir de outras informações. | valor_total de VENDA. |

### 12.3. Atributos por entidade

| Entidade | Principais grupos de atributos |
|---|---|
| PESSOA | Identificação, documento, contato, endereço e informação sobre CNH. |
| FUNCIONARIO | Cargo, admissão e situação do vínculo. |
| VEICULO | Características, placa, chassi e situação atual derivada. |
| ATENDIMENTO | Data, interesse, situação e observações. |
| AVALIACAO | Finalidade, quilometragem, condições, decisão e interesse comercial. |
| LAUDO | Referência documental, emissão, situação e resultado. |
| ENTRADA | Modalidade, datas, valor acordado, preço anunciado, contrato e condições de consignação. |
| VENDA | Valores, formas de pagamento, financiamento, documentação, conclusão, entrega, garantia e cancelamento. |
| OCORRENCIA_GARANTIA | Problema, diagnóstico, atendimento externo, responsabilidade, serviço e solução. |
| DESPESA | Data, categoria, descrição e valor. |

### 12.4. Tratamento das formas de pagamento

`formas_pagamento` é **somente multivalorado**: pode conter, por exemplo, `{Pix, financiamento}`. Não possui componentes de valor ou data e não é entidade. Total recebido, data mais recente e situação financeira são atributos separados de VENDA.

Essa representação resume a posição financeira e não permite reconstruir recebimentos individuais nem valores por forma. A limitação é assumida para respeitar a orientação acadêmica. A seção 15 descreve todos os atributos, sua obrigatoriedade e suas regras.

<a id="secao-13"></a>

## 13. Relacionamentos

### 13.1. Relacionamentos identificados

Os relacionamentos expressam a participação de pessoas e veículos nas operações da empresa. As multiplicidades são apresentadas separadamente na seção 14.

| ID | Entidade A | Relacionamento | Entidade B |
|---|---|---|---|
| R01 | PESSOA | possui vínculo | FUNCIONARIO |
| R02 | PESSOA | recebe | ATENDIMENTO |
| R03 | FUNCIONARIO | realiza | ATENDIMENTO |
| R04 | VEICULO | passa por | AVALIACAO |
| R05 | PESSOA | responde por | AVALIACAO |
| R06 | VEICULO | possui | LAUDO |
| R07 | AVALIACAO | consulta | LAUDO |
| R08 | VEICULO | possui | ENTRADA |
| R09 | PESSOA | fornece ou consigna | ENTRADA |
| R10 | AVALIACAO | fundamenta | ENTRADA |
| R11 | PESSOA | compra em | VENDA |
| R12 | FUNCIONARIO | responde por | VENDA |
| R13 | ENTRADA | é comercializada em | VENDA |
| R14 | VENDA | recebe em troca | ENTRADA |
| R15 | LAUDO | documenta | VENDA |
| R16 | VENDA | possui | OCORRENCIA_GARANTIA |
| R17 | PESSOA | mecânico principal | OCORRENCIA_GARANTIA |
| R18 | VEICULO | possui | DESPESA |

### 13.2. Integração das operações

- Principal: **VENDA → R13 → ENTRADA → R08 → VEICULO**.
- Recebidos: **VENDA → R14 → ENTRADA → R08 → VEICULO**.
- Avaliação de aceitação: **ENTRADA → R10 → AVALIACAO**.
- Cliente da ocorrência: **OCORRENCIA_GARANTIA → VENDA → PESSOA**.
- Veículo da ocorrência: **OCORRENCIA_GARANTIA → VENDA → ENTRADA → VEICULO**.

Não se repete um vínculo direto de veículo na venda ou na ocorrência, evitando associações contraditórias.

### 13.3. Análise da relação AVALIAÇÃO — LAUDO e atributos de relacionamento

A relação **R07 (AVALIAÇÃO — consulta — LAUDO)** foi definida como **1:N** (onde AVALIAÇÃO consulta `0,1` LAUDO e LAUDO é consultado por `0,N` AVALIAÇÕES), e não como N:N. Essa definição decorre da realidade operacional: em uma análise técnica, o avaliador examina no máximo o laudo cautelar de referência daquele veículo (ou nenhum, caso ainda esteja pendente de emissão). Por outro lado, um mesmo laudo válido pode subsidiar reavaliações do mesmo veículo ao longo do tempo. Além disso, vigora a restrição semântica de integridade de que o laudo consultado deve pertencer obrigatoriamente ao mesmo veículo avaliado (`AVALIACAO.veiculo == LAUDO.veiculo`).

**PESSOA — VEICULO** é mediada por ENTRADA porque data, modalidade, valor e contrato descrevem uma operação concreta, e não uma característica permanente da pessoa ou do automóvel.

Na troca, o valor aceito pertence à ENTRADA daquele veículo na negociação. A identidade do veículo continua a mesma; seu valor pode variar entre operações. ENTRADA tem identidade de evento comercial, não é apenas uma ligação sem conteúdo.

<a id="secao-14"></a>

## 14. Cardinalidades

Parte do Jocerlan

<a id="secao-15"></a>

## 15. Dicionário de dados conceitual

### Entidades E01 a E05

Parte do Caique

### Entidades E06 a E10 e Detalhamento de Componentes

Parte do David

<a id="secao-16"></a>

## 16. DER

Parte do Brenno

<a id="secao-17"></a>

## 17. Justificativas técnicas

Parte do Erin

<a id="secao-18"></a>

## 18. Conclusão

### 18.1. Considerações Finais do Grupo

A elaboração desta primeira entrega permitiu ao nosso grupo aplicar na prática os conceitos fundamentais de modelagem de dados ensinados pelo professor Clóvis. Ao analisar os processos reais da Multiplikar Automóveis, compreendemos que modelar um banco de dados não é simplesmente desenhar caixas e losangos, mas entender a fundo como a empresa opera, quais são seus problemas reais e quais regras precisam ser garantidas pelo sistema.

Conseguimos resolver desafios importantes levantados no briefing, tais como: permitir que múltiplos carros sejam dados em troca na mesma venda, unificar o cadastro de pessoas para evitar redundâncias, diferenciar a aprovação do crédito do efetivo recebimento do dinheiro pela loja e estruturar o controle de garantia pós-venda. O modelo conceitual desenvolvido fornece uma base sólida e sem contradições para a evolução do sistema.

### 18.2. Checklist de Validação da Primeira Entrega

Conforme orientado no checklist final do manual (página 21 e 22), verificamos todos os itens antes da publicação:

| Área Avaliada | Itens Verificados e Cumpridos | Onde Conferir |
|---|---|---|
| **Contexto** | Empresa caracterizada, escolha justificada, problemas e necessidades descritos. | Seções 2, 3 e 4 |
| **Processos** | 8 processos mapeados detalhadamente e 8 fluxogramas desenhados com visão geral. | Seções 5 e 10 |
| **Requisitos** | 18 requisitos funcionais (RF01 a RF18) e 8 não funcionais (RNF01 a RNF08) organizados. | Seções 6 e 7 |
| **Regras e Políticas** | 33 regras de negócio (RN01 a RN33) e 13 restrições organizacionais (RO01 a RO13). | Seções 8 e 9 |
| **Dados e Entidades** | 10 entidades definidas, atributos conceituais classificados e dicionário de dados completo. | Seções 11, 12 e 15 |
| **Relacionamentos** | 18 relacionamentos nomeados por verbos e análise de relacionamentos N:N. | Seção 13 |
| **Cardinalidades** | Mínimos e máximos calculados pelo Método Vá e Volte com justificativas. | Seção 14 |
| **Diagrama (DER)** | Diagrama em notação de Chen com todas as entidades, atributos e relações coerentes. | Seção 16 e `docs/der/` |
| **Justificativas** | Decisões de modelagem e abstração fundamentadas técnica e operacionalmente. | Seção 17 |
| **Documentação** | Repositório estruturado, arquivos editáveis `.drawio` e exportações em PNG/SVG. | Raiz e pasta `docs/` |
| **Equipe e Diário** | Identificação dos 9 integrantes, divisão das contribuições e registro do Diário de Bordo. | Seção 1 |

### 18.3. Próximos Passos do Projeto

Para as etapas seguintes da disciplina, utilizaremos este modelo conceitual como ponto de partida para:
1. Transformar as entidades e relacionamentos no **Modelo Lógico Relacional** (tabelas, chaves primárias e chaves estrangeiras);
2. Aplicar as regras de **Normalização** (1FN, 2FN e 3FN) para eliminar possíveis redundâncias e anomalias de atualização;
3. Desenvolver o **Modelo Físico** com scripts SQL de criação de tabelas (DDL), tipos de dados específicos do SGBD e restrições de integridade (`PRIMARY KEY`, `FOREIGN KEY`, `CHECK`);


