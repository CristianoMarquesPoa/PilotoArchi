# Arquitetura de Solução-Geral V2[^1]

* [Introduction](#introduction)
* [Origens de Pessoas (Diagram Model Group)](#origens-de-pessoas-diagram-model-group)
  * [Gupy (Application Component)](#gupy-application-component)
  * [Listing Applications (Application Service)](#listing-applications-application-service)
* [OPT-IN & OPT-OUT AS-IS (Diagram Model Group)](#opt-in-&-opt-out-as-is-diagram-model-group)
  * [Portal E-Commerce (Device)](#portal-e-commerce-device)
  * [Contact List (Data Object)](#contact-list-data-object)
  * [Carga manual para enriquecimento de dados cadastrais (Business Function)](#carga-manual-para-enriquecimento-de-dados-cadastrais-business-function)
  * [Oracle Responsys (Application Component)](#oracle-responsys-application-component)
* [CANAIS (Diagram Model Group)](#canais-diagram-model-group)
  * [Portal Desktop (Device)](#portal-desktop-device)
    * [Renner (Application Interface)](#renner-application-interface)
    * [Camicado (Application Interface)](#camicado-application-interface)
    * [Realize (Application Interface)](#realize-application-interface)
    * [YouCom (Application Interface)](#youcom-application-interface)
  * [Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)
* [SERVIÇOS DE APLICAÇÃO (Diagram Model Group)](#serviços-de-aplicação-diagram-model-group)
  * [Aplica Consentimento/Marca (Application Service)](#aplica-consentimentomarca-application-service)
  * [Publica Extrato Titular/Marca (Application Service)](#publica-extrato-titularmarca-application-service)
  * [Publica Consentimentos Marca (Application Service)](#publica-consentimentos-marca-application-service)
  * [Publica Compartilhamentos/Marca (Application Service)](#publica-compartilhamentosmarca-application-service)
  * [Abertura de Ticket (Application Service)](#abertura-de-ticket-application-service)
  * [Consulta status Ticket (Application Service)](#consulta-status-ticket-application-service)
  * [Decisões Automatizadas (Application Service)](#decisões-automatizadas-application-service)
  * [Finalidade (Application Service)](#finalidade-application-service)
* [SERVIÇOS DE NEGÓCIO (Diagram Model Group)](#serviços-de-negócio-diagram-model-group)
  * [Gestão Consentimento (Business Service)](#gestão-consentimento-business-service)
  * [Extrato de Dados (Business Service)](#extrato-de-dados-business-service)
  * [Extrato de Compartilhamento de Dados (Business Service)](#extrato-de-compartilhamento-de-dados-business-service)
  * [Retificação de Dados (Business Service)](#retificação-de-dados-business-service)
  * [Esclarecimento Decisões Automatizadas (Business Service)](#esclarecimento-decisões-automatizadas-business-service)
  * [Eliminação e Anomização (Business Service)](#eliminação-e-anomização-business-service)
  * [Portabilidade de Dados (Business Service)](#portabilidade-de-dados-business-service)
  * [Dúvidas Gerais LGPD (Business Service)](#dúvidas-gerais-lgpd-business-service)
  * [Gestão LGPD (Business Service)](#gestão-lgpd-business-service)
* [SERVIÇOS DE NEGÓCIO IMPACTADOS (Diagram Model Group)](#serviços-de-negócio-impactados-diagram-model-group)
  * [Campaing Management (Business Service)](#campaing-management-business-service)
  * [CRM - Inteligência de Mercado (Business Service)](#crm---inteligência-de-mercado-business-service)
  * [Atendimento Cliente (Business Service)](#atendimento-cliente-business-service)
* [PROCESSOS DE NEGÓCIO (Diagram Model Group)](#processos-de-negócio-diagram-model-group)
  * [Extrato Simplificado (Business Process)](#extrato-simplificado-business-process)
  * [Extrato Completo (Business Process)](#extrato-completo-business-process)
  * [Gestão do Consentimento (Business Process)](#gestão-do-consentimento-business-process)
  * [Extrato de Compartilhamento de Dados (Business Process)](#extrato-de-compartilhamento-de-dados-business-process)
  * [Petição Não Automatizada (Business Process)](#petição-não-automatizada-business-process)
  * [Atualização Dados Cliente (Business Process)](#atualização-dados-cliente-business-process)
  * [Atualização Dados Fornecedor (Business Process)](#atualização-dados-fornecedor-business-process)
  * [Atualização dados Funcionário (Business Process)](#atualização-dados-funcionário-business-process)
  * [Gestão Petição (Business Process)](#gestão-petição-business-process)
* [WSO2 (Application Component)](#wso2-application-component)
* [Virtualização (Application Component)](#virtualização-application-component)
  * [Kafka (Application Component)](#kafka-application-component)
  * [WSO2 (Application Component) 2](#wso2-application-component-2)
* [ORIGEM CLIENTES (Diagram Model Group)](#origem-clientes-diagram-model-group)
  * [DBM (Application Component)](#dbm-application-component)
  * [HTC (Application Component)](#htc-application-component)
* [SOLUÇÕES LGPD (Diagram Model Group)](#soluções-lgpd-diagram-model-group)
  * [Orchestra LGPD (Application Component)](#orchestra-lgpd-application-component)
    * [Workflow de Deduplicação, Normalização e Limpeza de Titularidade (Application Service)](#workflow-de-deduplicação,-normalização-e-limpeza-de-titularidade-application-service)
    * [Publica Consentimento (Application Service)](#publica-consentimento-application-service)
    * [Publica Pessoa (Application Service)](#publica-pessoa-application-service)
    * [Atualizar Consentimento (Application Service)](#atualizar-consentimento-application-service)
  * [ZenDesk (Application Component)](#zendesk-application-component)
* [OUTBOUND MDM (Diagram Model Group)](#outbound-mdm-diagram-model-group)
  * [Cache MDM Titulares (Application Component)](#cache-mdm-titulares-application-component)
    * [MongoDB (System Software)](#mongodb-system-software)
      * [Titular (Data Object)](#titular-data-object)
      * [Consentimentos (Data Object)](#consentimentos-data-object)
  * [Consumir Consentimento Cache (Application Service)](#consumir-consentimento-cache-application-service)
  * [Consumir Titular Cache (Application Service)](#consumir-titular-cache-application-service)
* [FPW (Application Component)](#fpw-application-component)
  * [MView Funcionários (Data Object)](#mview-funcionários-data-object)
* [GIA (Application Component)](#gia-application-component)
  * [MView Fornecedores (Data Object)](#mview-fornecedores-data-object)
* [LGPD MDM Stage (Application Component)](#lgpd-mdm-stage-application-component)
  * [Carga Dados Titular MDM (Application Service)](#carga-dados-titular-mdm-application-service)

## Introduction

![Arquitetura de Solução-Geral V2][embedView]

## Origens de Pessoas (Diagram Model Group)

### Gupy (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Gupy|Serving Relationship|[Listing Applications (Application Service)](#listing-applications-application-service)|||

### Listing Applications (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Listing Applications|Serving Relationship|[LGPD MDM Stage (Application Component)](#lgpd-mdm-stage-application-component)|||

## OPT-IN & OPT-OUT AS-IS (Diagram Model Group)

### Portal E-Commerce (Device)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Portal E-Commerce|Access Relationship (write)|[Contact List (Data Object)](#contact-list-data-object)|1 - Cadastramento no Portal||

### Contact List (Data Object)

### Carga manual para enriquecimento de dados cadastrais (Business Function)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Carga manual para enriquecimento de dados cadastrais|Access Relationship (write)|[Contact List (Data Object)](#contact-list-data-object)|||

### Oracle Responsys (Application Component)

## CANAIS (Diagram Model Group)

### Portal Desktop (Device)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Portal Desktop|Realization Relationship|[Camicado (Application Interface)](#camicado-application-interface)|||
|Portal Desktop|Realization Relationship|[Renner (Application Interface)](#renner-application-interface)|||
|Portal Desktop|Realization Relationship|[Realize (Application Interface)](#realize-application-interface)|||
|Portal Desktop|Realization Relationship|[YouCom (Application Interface)](#youcom-application-interface)|||

Plataforma prioritária para atendimento das petições, sendo disponibilizado neste serviço de autoatendimento para a maioria das petições. 

#### Renner (Application Interface)

#### Camicado (Application Interface)

#### Realize (Application Interface)

#### YouCom (Application Interface)

### Web Application Multi-Marca (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Web Application Multi-Marca|Serving Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||

Aplicação multi-marca embarcada dentro dos sites de cada marca. Canal preferencial de auto-atendimento LGPD.

## SERVIÇOS DE APLICAÇÃO (Diagram Model Group)

### Aplica Consentimento/Marca (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Aplica Consentimento/Marca|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||
|Aplica Consentimento/Marca|Flow Relationship|[WSO2 (Application Component)](#wso2-application-component)|||

API responsável por aplicar o consentimento (opt-in e opt-out do titular por marca.

### Publica Extrato Titular/Marca (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Publica Extrato Titular/Marca|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

API responsável por expor os dados do titular/cliente de acordo com a empresa/marca.

### Publica Consentimentos Marca (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Publica Consentimentos Marca|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

API responsável por expor ao titular os consentimentos do uso dos seus dados. Finalidades são mantidas dentro da plataforma LGPD.

### Publica Compartilhamentos/Marca (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Publica Compartilhamentos/Marca|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

API responsável por expor ao titular os compartilhamentos que a marca faz dos seus dados (compartilhamento com Facebook, Google e etc.). Compartilhamentos são mantidos dentro da plataforma LGPD.

### Abertura de Ticket (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Abertura de Ticket|Flow Relationship|[Consulta status Ticket (Application Service)](#consulta-status-ticket-application-service)|||
|Abertura de Ticket|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|||
|Abertura de Ticket|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

### Consulta status Ticket (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Consulta status Ticket|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|||
|Consulta status Ticket|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

### Decisões Automatizadas (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Decisões Automatizadas|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|||
|Decisões Automatizadas|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

### Finalidade (Application Service)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Finalidade|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|||
|Finalidade|Serving Relationship|[Web Application Multi-Marca (Application Component)](#web-application-multi-marca-application-component)|||

## SERVIÇOS DE NEGÓCIO (Diagram Model Group)

### Gestão Consentimento (Business Service)

Opt-in e Opto-out para os dados tratados pela base legal consentimento. 

### Extrato de Dados (Business Service)

Informação demosntrada através de extrato com os dados em formato simplificado (formato e dados a definir) e a opção de declaração completa.

### Extrato de Compartilhamento de Dados (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Retificação de Dados (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Esclarecimento Decisões Automatizadas (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Eliminação e Anomização (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Portabilidade de Dados (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Dúvidas Gerais LGPD (Business Service)

Informação das empresas, orgãos e instituições com os quais as marcas realizam compartilhamento, finalidade principal e categorias dos dados.

### Gestão LGPD (Business Service)

## SERVIÇOS DE NEGÓCIO IMPACTADOS (Diagram Model Group)

### Campaing Management (Business Service)

### CRM - Inteligência de Mercado (Business Service)

### Atendimento Cliente (Business Service)

## PROCESSOS DE NEGÓCIO (Diagram Model Group)

### Extrato Simplificado (Business Process)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Extrato Simplificado|Realization Relationship|[Extrato de Dados (Business Service)](#extrato-de-dados-business-service)|||
|Extrato Simplificado|Association Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||

### Extrato Completo (Business Process)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Extrato Completo|Realization Relationship|[Extrato de Dados (Business Service)](#extrato-de-dados-business-service)|||
|Extrato Completo|Association Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||

### Gestão do Consentimento (Business Process)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Gestão do Consentimento|Realization Relationship|[Gestão Consentimento (Business Service)](#gestão-consentimento-business-service)|||
|Gestão do Consentimento|Association Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||

### Extrato de Compartilhamento de Dados (Business Process)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Extrato de Compartilhamento de Dados|Realization Relationship|[Extrato de Compartilhamento de Dados (Business Service)](#extrato-de-compartilhamento-de-dados-business-service)|||
|Extrato de Compartilhamento de Dados|Association Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||

### Petição Não Automatizada (Business Process)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Petição Não Automatizada|Realization Relationship|[Dúvidas Gerais LGPD (Business Service)](#dúvidas-gerais-lgpd-business-service)|||
|Petição Não Automatizada|Realization Relationship|[Retificação de Dados (Business Service)](#retificação-de-dados-business-service)|||
|Petição Não Automatizada|Realization Relationship|[Esclarecimento Decisões Automatizadas (Business Service)](#esclarecimento-decisões-automatizadas-business-service)|||
|Petição Não Automatizada|Realization Relationship|[Eliminação e Anomização (Business Service)](#eliminação-e-anomização-business-service)|||
|Petição Não Automatizada|Realization Relationship|[Portabilidade de Dados (Business Service)](#portabilidade-de-dados-business-service)|||
|Petição Não Automatizada|Association Relationship|[Portal Desktop (Device)](#portal-desktop-device)|||
|Petição Não Automatizada|Composition Relationship|[Atualização dados Funcionário (Business Process)](#atualização-dados-funcionário-business-process)|||
|Petição Não Automatizada|Composition Relationship|[Atualização Dados Fornecedor (Business Process)](#atualização-dados-fornecedor-business-process)|||
|Petição Não Automatizada|Composition Relationship|[Atualização Dados Cliente (Business Process)](#atualização-dados-cliente-business-process)|||
|Petição Não Automatizada|Composition Relationship|[Gestão Petição (Business Process)](#gestão-petição-business-process)|||

### Atualização Dados Cliente (Business Process)

Processo manual de atualização de dados do cliente nos diversos sistemas que forem necessários.

### Atualização Dados Fornecedor (Business Process)

Processo manual de atualização de dados do fornecedor nos diversos sistemas que forem necessários.

### Atualização dados Funcionário (Business Process)

Processo para resolver petição de funcionário/ex-funcionário.

### Gestão Petição (Business Process)

Processo manual de atualização de dados do cliente nos diversos sistemas que forem necessários.

## WSO2 (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|WSO2|Flow Relationship|[Publica Compartilhamentos/Marca (Application Service)](#publica-compartilhamentosmarca-application-service)|||
|WSO2|Serving Relationship|[Publica Consentimentos Marca (Application Service)](#publica-consentimentos-marca-application-service)|||
|WSO2|Serving Relationship|[Publica Extrato Titular/Marca (Application Service)](#publica-extrato-titularmarca-application-service)|||
|WSO2|Flow Relationship|[Orchestra LGPD (Application Component)](#orchestra-lgpd-application-component)|||

## Virtualização (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Virtualização|Flow Relationship|[Cache MDM Titulares (Application Component)](#cache-mdm-titulares-application-component)|Load||
|Virtualização|Flow Relationship|[Orchestra LGPD (Application Component)](#orchestra-lgpd-application-component)|||

### Kafka (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Kafka|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|Consumer||

### WSO2 (Application Component) 2

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|WSO2|Serving Relationship|[Kafka (Application Component)](#kafka-application-component)|Publisher||
|WSO2|Serving Relationship|[Orchestra LGPD (Application Component)](#orchestra-lgpd-application-component)|Consumer|Cadastro|

## ORIGEM CLIENTES (Diagram Model Group)

### DBM (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|DBM|Flow Relationship|[LGPD MDM Stage (Application Component)](#lgpd-mdm-stage-application-component)|||

Database marketing corporativo. Xpto

### HTC (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|HTC|Serving Relationship|[DBM (Application Component)](#dbm-application-component)|||

## SOLUÇÕES LGPD (Diagram Model Group)

### Orchestra LGPD (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Orchestra LGPD|Assignment Relationship|[Publica Consentimento (Application Service)](#publica-consentimento-application-service)|||
|Orchestra LGPD|Serving Relationship|[WSO2 (Application Component)](#wso2-application-component)|Publisher|Consentimento|
|Orchestra LGPD|Assignment Relationship|[Workflow de Deduplicação, Normalização e Limpeza de Titularidade (Application Service)](#workflow-de-deduplicação,-normalização-e-limpeza-de-titularidade-application-service)|||

Sistema adquirido para ser o gerenciador de meta-dados e respositório LGPD.

#### Workflow de Deduplicação, Normalização e Limpeza de Titularidade (Application Service)

#### Publica Consentimento (Application Service)

#### Publica Pessoa (Application Service)

#### Atualizar Consentimento (Application Service)

### ZenDesk (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|ZenDesk|Specialization Relationship|[WSO2 (Application Component)](#wso2-application-component)|||

Plataforma de atendimento do centro de serviços compartilhados.

## OUTBOUND MDM (Diagram Model Group)

### Cache MDM Titulares (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|Cache MDM Titulares|Assignment Relationship|[Consumir Consentimento Cache (Application Service)](#consumir-consentimento-cache-application-service)|||
|Cache MDM Titulares|Assignment Relationship|[Consumir Titular Cache (Application Service)](#consumir-titular-cache-application-service)|||

#### MongoDB (System Software)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|MongoDB|Access Relationship (write)|[Titular (Data Object)](#titular-data-object)|||

##### Titular (Data Object)

##### Consentimentos (Data Object)

### Consumir Consentimento Cache (Application Service)

### Consumir Titular Cache (Application Service)

## FPW (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|FPW|Access Relationship (write)|[MView Funcionários (Data Object)](#mview-funcionários-data-object)|||

### MView Funcionários (Data Object)

## GIA (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|GIA|Access Relationship (write)|[MView Fornecedores (Data Object)](#mview-fornecedores-data-object)|||

### MView Fornecedores (Data Object)

## LGPD MDM Stage (Application Component)

**Relationships**
|From|Relationship|To|Name|Description|
|---|---|---|---|---|
|LGPD MDM Stage|Access Relationship (write)|[MView Funcionários (Data Object)](#mview-funcionários-data-object)|||
|LGPD MDM Stage|Access Relationship (write)|[MView Fornecedores (Data Object)](#mview-fornecedores-data-object)|||
|LGPD MDM Stage|Flow Relationship|[WSO2 (Application Component)](#wso2-application-component)|||

### Carga Dados Titular MDM (Application Service)

API responsável por integrar o dados financeiros e complementares do cliente/titular para plataforma LGPD.

[embedView]: LGPD-Arquitetura%20de%20Solução-Geral%20V2.png
[^1]: Generated: Fri Jul 31 2020 14:24:42 GMT-0300 (BRT)
