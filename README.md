# Análise de Tentativas de Login Suspeitas em Linux

Este repositório apresenta um laboratório prático de análise de eventos de autenticação falhos em um servidor Linux, com foco na identificação de padrões suspeitos a partir de logs do sistema.  

O projeto foi desenvolvido com a mentalidade de um analista SOC N1, priorizando investigação, correlação de eventos e documentação adequada do incidente.

---

## Objetivo
Demonstrar a capacidade de:
- analisar logs de autenticação em ambientes Linux;
- identificar padrões compatíveis com tentativas de acesso não autorizado;
- correlacionar eventos envolvendo usuários válidos e inválidos;
- classificar incidentes e propor ações iniciais de resposta.

---

## Cenário
Foram observadas múltiplas falhas de autenticação via SSH em curto intervalo de tempo, direcionadas a usuários inexistentes e a um usuário legítimo do sistema, todas originadas do mesmo endereço IP.

O padrão identificado é compatível com enumeração de usuários associada a tentativa de força bruta, sem evidência de autenticação bem-sucedida.

---

---

## Metodologia
A análise foi conduzida a partir da observação e filtragem do arquivo de logs de autenticação do sistema (`/var/log/auth.log`), utilizando técnicas básicas de investigação para isolar eventos relevantes, identificar padrões temporais e correlacionar tentativas de autenticação entre usuários distintos.

As evidências coletadas foram organizadas separadamente do relatório analítico, seguindo boas práticas de documentação de incidentes.

---

## Resultado da Análise
- Identificação de padrão compatível com tentativa de acesso não autorizado;
- Ausência de impacto confirmado no ambiente analisado;
- Proposição de ações iniciais de contenção e monitoramento.

---

## Observação
Este projeto foi desenvolvido em ambiente controlado e tem finalidade exclusivamente educacional, com foco em análise defensiva e simulação de cenários comuns enfrentados por analistas de segurança.

---

## Autor
Erick Alves
Projeto desenvolvido como parte de estudos práticos em cibersegurança, com foco em atuação em Security Operations Center (SOC).
